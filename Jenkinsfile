@Library('nx@master') _

pipeline {
  agent any

  stages {
    stage('install') {
      steps {
        sh 'yarn install'
        stash name: 'repo'
        node('Slave') {
          unstash name: 'repo'
        }
        node('master') {
          unstash name: 'repo'
        }
      }
    }

    stage('test') {
      steps {
        affected('somethign slfsd')
      }
    }
  }
}