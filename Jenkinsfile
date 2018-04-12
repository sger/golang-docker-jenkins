// this will start an executor on a Jenkins agent with the docker label
pipeline {
  agent {
    docker 'sger/go-docker-ubuntu'
  }
  stages {
    stage('build base image') {
      steps {
        sh 'make build-base'
      }
    }
    stage('run tests') {
      steps {
        sh 'make build-test'
        sh 'make test-unit'
        sh 'ls'
      }
    }
    stage('build image') {
      steps {
        sh 'make build'
      }
    }
  }
}