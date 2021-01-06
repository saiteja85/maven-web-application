node
{
//properties([[$class: 'JiraProjectProperty'], buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * * ')])])
    def mavenhome = tool name:"maven3.6.3"
stage('checkoutcode')
{
git branch: 'development', credentialsId: '3f47d095-6cef-401a-95a0-1a26631eca1d', url: 'https://github.com/saiteja85/maven-web-application.git'
}
/*    
stage('build')
{
sh "${mavenhome}/bin/mvn clean package"
}
stage('executesonarqubeReort')
{
sh "${mavenhome}/bin/mvn sonar:sonar"
}
*/
stage('uploadartifactintonexus')
{
sh "${mavenhome}/bin/mvn clean deploy"
}
/*
stage('deploytotomcat')
{
sshagent(['0e93f2a5-6556-46a6-ab61-024a7c36b3d2']) {
sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@13.234.33.173:/opt/apache-tomcat-9.0.41/webapps"
}
}
stage('sendemailnotification')
{
mail bcc: 'saitejaaa85@gmail.com', body: 'done by sai', cc: 'saitejaaa85@gmail.com', from: '', replyTo: '', subject: 'build over', to: 'saitejaaa85@gmail.com'
}
*/
}
