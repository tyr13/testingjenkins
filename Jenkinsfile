pipeline {
    agent any

    stages {
        stage('Verify Branch') {
            steps {
                echo "$GIT_BRANCH"
            }
        }
        stage('DOcker Build') {
            steps {
                sh 'docker images -a'
                sh '"""
                    cd azure-vote
                    docker images -a
                    docker build -t jenkins-pipline
                    docker images -a
                    cd ..
                """'
            }
        }
    }
}
