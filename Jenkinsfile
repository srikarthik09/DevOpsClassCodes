
pipeline{
    tools{
        jdk 'myjava'
        maven 'my'
    }
    agent none
      stages{
           stage('Checkout'){
               agent any
               steps{
		                  git 'https://github.com/srikarthik09/DevOpsClassCodes.git'
              }
          }
          stage('Compile'){
              agent any
              steps{
                                    sh 'mvn compile'
	      }
          }
          stage('CodeReview'){
              agent any
              steps{
		                    sh 'mvn pmd:pmd'
              }
          }
           stage('UnitTest'){
               agent any
              steps{
                  sh 'mvn test'
              }
          }
           stage('MetricCheck'){
               agent any
              steps{
                  sh 'mvn cobertura:cobertura -Dcobertura.report.format=xml'
              }
          }
          stage('Package'){
              agent any
              steps{
                  sh 'mvn package'
              }
          }
          
      }
}
