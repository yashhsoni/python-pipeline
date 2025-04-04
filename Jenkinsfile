pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/your/repo.git' // Replace with your repo
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'pytest --junitxml=report.xml'
            }
        }

        stage('Run Script') {
            steps {
                sh 'python main.py'
            }
        }
    }

    post {
        always {
            junit 'report.xml'
        }
    }
}
