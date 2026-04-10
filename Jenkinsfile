pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t demo-app:v1 .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker rm -f demo-container || true
                docker run -d --name demo-container -p 8090:80 demo-app:v1
                '''
            }
        }
    }
}
