pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // 소스코드 체크아웃
                git branch: 'main', url: 'https://github.com/spenshark/calculator.git'
            }
        }
        stage('Set Permission') {
            steps {
                // gradlew에 실행 권한 부여
                sh 'chmod +x gradlew'
            }
        }
        stage("Compile") {
            steps {
                sh "./gradlew compileJava"
            }
        }
        stage("Build") {
            steps {
                sh "./gradlew build"
            }
        }
        stage("Unit test") {
            steps {
                sh "./gradlew test"
            }
        }
    }
}