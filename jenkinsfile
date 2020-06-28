pipeline {
   agent any

   stages {
      
	  stage('Get Code') {
         steps {
            git 'https://github.com/iamdevopstrainer/DevOpsClassCodes.git'
         }
      }	  
	  stage('Compile') {
         steps {
           sh '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/maven361/bin/mvn compile'
               }
      }
          stage('Test') {
         steps {
            sh '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/maven361/bin/mvn test'
         }
      }
          stage('Package') {
         steps {
            sh '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/maven361/bin/mvn package'
               }
      }
          stage('Deploy') {
         steps {
           
	   sh 'cp /var/lib/jenkins/workspace/packagejob/target/addressbook.war /usr/local/tomcat9/webapps'

               }
      }
               
   }

}
