node {
    
stage('checkout')
git 'https://github.com/g0t4/jenkins2-course-spring-boot.git'

stage('cleaning')
sh 'mvn -f spring-boot-samples/spring-boot-sample-atmosphere/pom.xml clean'

stage('package')
sh 'mvn -f spring-boot-samples/spring-boot-sample-atmosphere/pom.xml package'

stage('Artifacts')
archiveArtifacts 'spring-boot-samples/spring-boot-sample-atmosphere/target/*.jar'

stage('Report')
step([$class: 'JUnitResultArchiver', testResults: 'spring-boot-samples/spring-boot-sample-atmosphere/target/surefire-reports/TEST-*.xml'])
 
}
