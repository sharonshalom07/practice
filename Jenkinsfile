pipeline {
  agents any

  tools{
  maven 'maven'
  jdk 'java'
  }
  
  
  stages {
    stage('Checkout commands') {
      steps{
        git branch:'main' url:'https://github.com/sharonshalom07/practice.git'
      } 
    }
    stage('Maven') {
      steps{
        bat 'mvn clean package'
      }
    }
    stage('Tomcat') {
      steps{
        deploy adapters: [
          tomcat9(
            credentialsId:'tomcat_creds',
              path:''
            url:'http://localhost:8081'
            )
          ],
          contextpath:'my-web-app',
          war:'target/*my-web-app.war'
      }}}}
            
