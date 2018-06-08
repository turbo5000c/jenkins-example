pipeline {
    agent {
        docker { image 'j-slave1' }
    }

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'maven_3_3_9') {
                    sh '$MVN_CMD clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'maven_3_3_9') {
                    sh '$MVN_CMD test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'maven_3_3_9') {
                    sh '$MVN_CMD deploy'
                }
            }
        }
    }
}
