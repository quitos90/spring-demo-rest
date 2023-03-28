pipeline {
    agent any
    tools {
        maven 'Maven 3.9.1'
        jdk 'jdk11'
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
                sh 'export JAVA_HOME=/var/jenkins_home/tools/hudson.model.JDK/jdk11'
            }
        }

        stage ('Install') {
            steps {
                sh 'env'
                sh 'mvn -Dmaven.test.failure.ignore=true install'
            }
        }
    }
}