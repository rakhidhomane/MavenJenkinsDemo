pipeline {
    agent any
    stages {
        stage('Cleanup') {
            steps {
                deleteDir() // Clean up the workspace
            }
        }
        stage('github') {
            steps {
                git branch: 'main', credentialsId: 'rakhidhomane-ssh', url: 'https://github.com/rakhidhomane/MavenJenkinsDemo.git'
            }
        }
        stage('maven build') {
            steps {
                bat 'mvn clean install'
                archiveArtifacts 'target/*.jar'
            }
        }
    }
}
