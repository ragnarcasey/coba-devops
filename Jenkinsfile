pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                echo 'Lagi ngetes kode...'
            }
        }
        stage('Build') {
            steps {
                sh 'docker build -t app-jenkins .'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker stop app-container || true'
                sh 'docker rm app-container || true'
                sh 'docker run -d -p 8082:80 --name app-container app-jenkins'
            }
        }
    }
}
