properties([
  parameters([
    string(name: 'payload', defaultValue: '{}', description: 'All of the values needed to run the job')
  ])
])
node {
	echo 'Parsing JSON Payload parameter into environment variables'
	def jsonPayloadObj = readJSON text: params.payload
		
	def envVarsList = []
	map.each{ k, v -> envVarsList.add("${kv[0].toUpperCase()}=\"${kv[1]}\"")
	}
	withEnv(envVarsList) {
		stage('setup') {
			echo 'Setup Stage!'
			echo printenv
		}
		stage('execute') {
			echo 'Execute Stage!'
			echo printenv
		}
		stage('cleanup') {
			echo 'Cleanup Stage!'
		}
	}
}
