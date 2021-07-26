pipeline {
agent any
  stages {
    stage('Run Neoload') {
      steps {
          echo "Hello World"
          neoloadRun executable: '/Users/sa20099277/.jenkins/workspace/Common_Performance_Testing/Library/Python/3.8/bin/neoload', project: '/Users/sa20099277/neoload_projects/sample/sample.nlp', testDescription: 'To check its working', scenario: 'scenario 1', trendGraphs: ['AvgResponseTime', 'ErrorRate']
      }
    }
  }
}
// pipeline {
//   agent any

//   parameters {
//     string(defaultValue: "b2ac016f35d29e188f02956368e99dc62f2954d8e424e9c1", description: 'Neoload Web Token', name: 'token')
//     string(defaultValue: "defaultzone", description: 'Zone identifier', name: 'zone_id')
//     string(defaultValue: "https://neoload-api.saas.neotys.com/", description: 'NeoLoad Web Api Url', name: 'api_url')
//   }
//   stages {
//         stage('Get NeoLoad CLI') {
//           steps {
//               sh 'echo "Hello World"'
//               sh 'pip3 install --upgrade pip --user'
//               sh 'pip3 install -U --pre neoload --user'
//               sh '$NEOLOAD --version'
//               echo "${BUILD_URL}"
              
//           }
//           environment {
//             NEOLOAD="${WORKSPACE}/Library/Python/3.8/bin/neoload"
//             HOME="${WORKSPACE}"
//           }
//         }
//         stage('Prepare NeoLoad test') {
//           steps {
//               sh """$NEOLOAD \
//                      login --url ${params.api_url} ${params.token} \
//                      test-settings --zone ${params.zone_id} --scenario 'simpledemo' createorpatch "My Jenkins Test With CLI" \
//                      project --path simpledemo.yml upload
//                 """
//           }
//         }
//         stage('Run Test') {
//           steps {
//               sh """$NEOLOAD run \
//                   --name "Jenkins pipeline performance regression test ${BUILD_NUMBER}" \
//                   --external-url '${BUILD_URL}' \
//                   --external-url-label 'Jenkins build ${BUILD_NUMBER}' \
//                   --description "Jenkins result description" \
//                   --return-0 \
//                   --web-vu 50 \
//                  """
//           }
//         }
//         stage('Generate Test Report') {
//           steps {
//              sh "$NEOLOAD test-results junitsla"
//           }
//           post {
//               always {
//                   junit 'junit-sla.xml'
//               }
//           }
//         }
//       }
//     }
