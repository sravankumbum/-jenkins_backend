pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/sravankumbum/-jenkins_backend'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Start Backend') {
            steps {
                sh 'pm2 restart backend || pm2 start app.py --name backend --interpreter python3'
            }
        }
    }
}
