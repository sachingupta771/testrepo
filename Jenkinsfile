

node {
   def GIT_URL
   def CREDS
   stage('Preparation') { 
	  
			script {
				echo "preparing for pipeline";
				CREDS = 'GITHUB'
				def Application = params.Application
				echo Application
				if ( Application == "Party") 
					{
					GIT_URL='https://github.com/sachingupta771/party.git'

					}
			  else if ( Application == "HeadFund") 
					{
					GIT_URL='https://github.com/sachingupta771/headfund.git'

					}
			  
			}
		
	}
    stage('Checkout') {
		
			script {
				echo 'Checkout the source code..'
				echo "${GIT_URL}  $GIT_URL	 env.GIT_URL params.GIT_URL ";
				//def t = new GitCheckout()
				def Branch = params.Branch
				echo Branch
				echo 'Taking Checkout of Application Repo ';
				checkout([$class: 'GitSCM', branches: [[name: Branch]], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: "${CREDS}", url: "${GIT_URL}"]]]) 
				
		    }
		
	}
 
}