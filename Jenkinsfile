pipeline {
    agent any

    environment {
        PATH = "/Users/zalifixter/.nvm/versions/node/v24.20.0/bin:${env.PATH}"
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/zaliiiiii/8.2CDevSecOps.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test || true'
            }
        }

        stage('Generate Coverage Report') {
            steps {
                sh 'npm run coverage || true'
            }
        }

        stage('NPM Audit (Security Scan)') {
            steps {
                sh 'npm audit || true'
            }
        }
        stage('Test SonarScanner') {
    steps {
        sh '/opt/sonar-scanner/bin/sonar-scanner --version'
    }
}
    }
}
