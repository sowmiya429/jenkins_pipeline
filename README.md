# jenkins_pipeline
create the EC2 INSTANCE
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/7b4a6980-ccab-4beb-aa68-2b784b0a9904)
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/9c9ef122-4073-47f8-8598-de9e0f004c30)
#create inbound rules to allow jenkins to use EC2 Instance
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/4a038110-bce3-4e18-87ba-9647ad4bf801)
#connect to EC2 Instance
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/09d15963-992f-4d71-9b82-1a9352540a57)
#update the system
```
sudo apt update
```
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/88d2ed00-b8e0-4a91-a5e3-5b290da97666)
#Install the java
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/0671bca5-c56f-4857-a11a-ef7158899cde)
#Install jenkins
```
curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins -y
```
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/6d80345e-c536-40e2-91ef-ea2f0d9c57f0)
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/d858042e-c7f0-4515-a2ae-840a5c12ea0e)
#To extract the password for jenkins
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/beb0eacd-f72d-4eb8-9e1d-08b0e49ac5c3)
#Install the suggessted plugins
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/b935af3d-e8e1-4b3a-b411-137a4985a738)
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/a4494704-a1f0-41fd-9a58-01efc06be541)
#Run as ADMIN
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/84f0c0d6-6f64-4b4d-a407-b7aac8caa59d)
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/28a97e3e-798f-4187-bf9f-4b38bb18729b)
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/cfa6cc23-093c-4318-9dce-61369723e159)
#Now needs to create three jobs and these three jobs should be dependent on eachother. Before that needs to install the plugin  
*Delivery pipeline plugin
*Build pipeline plugin
Go to manage_jenkins--->plugin--->Available plugin--->Delivery pipeline
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/535c953f-e428-4318-9828-0431b27d3381)
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/b2a65554-6110-43c2-9f4b-88d95f770129)
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/4f045eff-8993-43c0-befb-ea17d4dbd796)
Go to manage_jenkins--->plugin--->Available plugin--->Build pipeline
<img width="960" alt="image" src="https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/def7b382-6816-4434-aeab-973d8e35d8b3">
Create job1,job2,job3
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/aad94a03-79dc-4244-a097-289b5f04ba1c)
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/e783309a-ecd8-4720-a4ba-57f61a59710d)
#Now create a new view for all these jobs to create a dellivery pipeline. 
#The delivery pipeline is the one runs the job automatically once the first job finishes it will trigger the second job and the second one runs successfully the third one runs automatically. 
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/a274d8ff-fadf-4ee2-81e4-37acd9f906d1)
Needs to tell the JOB2 that it should run only if the JOB1 runs successful using trigger.
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/3c91e07a-c587-4433-9019-cadfb4b5dd84)
#There are two types of streams 
*UPSTREAM PROJECT
*DOWNSTREAM PROJECT
For JOB1 there will be downstream project is JOB2.
For JOB2 the UPSTREAM project JOB1 and DOWNSTREAM PROJECT is JOB3.
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/98000198-b7b3-4bec-b25c-ecab99571977)
This is how they relate to eachother.
#Now you see the pipeline working good
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/cd87de28-716f-4657-b3f2-cff798de9128)
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/1c89f166-9394-47ff-baf2-d2f3ce8f375c)
#Now create a BUILD PIPELINE which is similar to DELIVERY PIPELINE but in build pipeline it has more features and GUI
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/a10f2e29-865d-4740-8dfe-a5d91962c55d)
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/c316cc7e-c52f-41d5-ba96-b5cb93df5f69)
Comparing to delivery pipeline In build pipeline is more userfriendly and also we can build the jobs individually.
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/5ebf53f9-8410-4faa-9385-4072611b8b47)
![image](https://github.com/sowmiya429/jenkins_pipeline/assets/80743760/82d21db7-7f3e-4de9-ac4d-c32c210fe780)
