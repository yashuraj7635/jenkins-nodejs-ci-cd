pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/yashuraj7635/jenkins-nodejs-ci-cd.git'
            }
        }

        stage('Build') {
            steps {
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test || true'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t jenkins-nodejs-app .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker run -d -p 3001:3000 jenkins-nodejs-app || true'
            }
        }
    }
}
