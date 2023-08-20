#! /usr/bin/env groovy

 

pipeline {

 

  agent any
  environment {
    SPECTRAL_DSN = 'https://spu-8b39d10b9d1d4fa198c76bb048feb633@spectral-eu.checkpoint.com'
  }
  stages {
    stage('install Spectral') {
      steps {
        sh "curl -L 'https://spectral-eu.checkpoint.com/latest/x/sh?dsn=$SPECTRAL_DSN' | sh"
      }
    }
    stage('scan for issues') {
      steps {
        sh "$HOME/.spectral/spectral scan --fail-on-error  --engines oss"
      }
    }
  }
}
