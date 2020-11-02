pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                sh "mvn clean package"
            }
        }
        stage('Deploy'){
            steps{
                deploy adapters: [tomcat7(credentialsId: '9b156e6e-7980-41f7-96de-dbe1b922e9a7', path: '', 
                url: 'http://ec2-3-128-204-155.us-east-2.compute.amazonaws.com:8080/')], 
                contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }
    }
}
