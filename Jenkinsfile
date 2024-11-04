pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/troycdev/lbg-vat-calculator.git'
      }
    }

    stage('SonarQube Analysis') {
      environment {
        scannerHome = tool 'sonarqube'
      }
      steps {
        withSonarQubeEnv('sonarqube-15') {
          sh "${scannerHome}/bin/sonar-scanner"
        }
      }
    }
  }
}