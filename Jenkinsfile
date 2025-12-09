pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "todo-app"
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/yosrhaddar3-gif/app1.git'
            }
        }

        stage('Install dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run tests') {
            steps {
                sh 'npm test'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE .'
            }
        }
    }

    post {
        success {
            echo 'Pipeline terminé avec succès ! ✅'
        }
        failure {
            echo 'Erreur dans le pipeline ❌'
        }
    }
}
