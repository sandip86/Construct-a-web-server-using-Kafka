# Construct-a-web-server-using-Kafka

## In this project, you will be working with Kafka, one of the most successful applications for handling streaming data at scale. You will use a Docker image created by Confluent that installs all of the necessary Kafka components including, among others, the broker and ZooKeeper. Kafka allows you to store messages in topics, which are distributed across multiple brokers by splitting topics into data partitions that save you from unfortunate broker failures.
## To get started with this project, you will begin with a simple Kafka implementation. With this implementation, you will create a Python application that publishes vehicle location longitude-latitude data to a Kafka topic. Next, you will use Node.js to start a web server that acts as a consumer for the messages received from the Kafka application.

1.	In a Terminal window, create a new folder called Project_24_Docker. Download the docker-compose.yml file and place it inside the Project_24_Docker folder. Inside the Project_24_Docker folder, create a folder titled mosquitto. Inside the mosquitto folder, create three more subfolders titled as follows: config, data, and log. Download the mosquitto.config file and place it inside the config folder.
See the image below, which depicts the required folders and files:
  
Provide a screenshot to show that you correctly created all of the required folders and that you placed the docker-compose.yml and mosquitto.config files in the Project_24_Docker and config folders, respectively.
 
<img width="476" alt="image" src="https://github.com/sandip86/Construct-a-web-server-using-Kafka/assets/153111110/e7fcaff8-4251-40ab-a8e0-54ff51c9af5f">


2.	In a Terminal window, navigate to the Project_24_Docker folder and run the command below to initialize your Mosquitto container:
docker-compose up
Provide a screenshot of your Docker GUI to show that you have successfully initialized the Mosquitto container.
 
<img width="520" alt="image" src="https://github.com/sandip86/Construct-a-web-server-using-Kafka/assets/153111110/b3c9bec9-adb5-4494-bcfc-2437997e5e84">

<img width="563" alt="image" src="https://github.com/sandip86/Construct-a-web-server-using-Kafka/assets/153111110/deede6f2-ac21-46dc-aa9c-8f9420656c9d">


 
3.	In a local Terminal window, run the command below to install the Paho MQTT Python client library locally:
pip install paho-mqtt
Provide a screenshot to show that you have successfully installed the Paho MQTT Python client library.
 
<img width="563" alt="image" src="https://github.com/sandip86/Construct-a-web-server-using-Kafka/assets/153111110/6b8dbf84-9717-43a9-8f35-b523111891e4">


4.	In a Terminal window, navigate to your home folder.
For Mac users:
Enter the command below to navigate the your home folder:
cd
Inside of your home folder, create two folders named .mytb-data and .mytb-logs.
Provide a screenshot to show that you created the .mytb-data and .mytb-logs folders in your home folder.

<img width="444" alt="image" src="https://github.com/sandip86/Construct-a-web-server-using-Kafka/assets/153111110/d2b3e57c-fc4f-4a72-9660-4b9e5175cb31">

5.	Inside the same location where you created the Project_24_Docker folder, create a new folder titled Project_24_MQTT. Inside the Project_24_MQTT folder, create a new subfolder titled ThingsBoard. Download the docker-compose.yml file and place it inside the ThingsBoard folder. Also inside of the ThingsBoard folder, create two folders named .mytb-data and .mytb-logs.
See the image below, which depicts the required folders and files:
  
Provide a screenshot to show that you correctly created all of the required folders and that you placed the docker-compose.yml inside the ThingsBoard folder.

<img width="473" alt="image" src="https://github.com/sandip86/Construct-a-web-server-using-Kafka/assets/153111110/a92a96d7-deb6-4cff-9b33-673a319eaf56">

6.	In a Terminal window, navigate to the ThingsBoard folder that you created in Step 4 and run the command below to initialize your ThingsBoard container:
docker-compose up
If the ThingsBoard container does not spin up correctly, then change the ports on line 8 to 1883:1883 and try to spin up the container again.
Provide a screenshot of your Docker GUI to show that you have successfully initialized the ThingsBoard container.

<img width="408" alt="image" src="https://github.com/sandip86/Construct-a-web-server-using-Kafka/assets/153111110/098154ec-76a9-4381-9d0b-064582479fbd">

7.	Inside the Project_24_MQTT folder, create a new subfolder titled paho-mqtt. Download the TBPublish.py file and place it inside the paho-mqtt folder. Open the TBPublish.py file in VS Code.
See the image below, which depicts the required folders and files:
 
Modify the sensor_data dictionary by adding another key, humidity, with a corresponding value equal to 0. Inside the while loop, add a statement to generate random integer values between 50 and 100. Assign these values to the humidity variable.
Provide a screenshot to show that you created the paho-mqtt folder and modified the code inside the TBPublish.py file to add the humidity key with the correct values assigned to the humidity variable.

<img width="519" alt="image" src="https://github.com/sandip86/Construct-a-web-server-using-Kafka/assets/153111110/de17140a-2047-4eea-abaf-18bcc647c4f3">

8.	Open a Terminal window in VS Code. Run the TBPublish.py file.
Provide a screenshot to show that your code is correctly producing temperature and humidity data.

<img width="354" alt="image" src="https://github.com/sandip86/Construct-a-web-server-using-Kafka/assets/153111110/052e9bbf-cc57-4f92-ab6a-a7753977b3b8">

9.	In a browser window, navigate to http://localhost:8080/ to ThingsBoard using the credentials below:
Login: tenant@thingsboard.org
Password: tenant
Provide a screenshot to show that you successfully logged in to ThingsBoard by using the credentials provided.

<img width="472" alt="image" src="https://github.com/sandip86/Construct-a-web-server-using-Kafka/assets/153111110/e7ed80fb-fba6-4a9c-9076-a22b0216b8c3">

10.	In ThingsBoard, from the menu on the left, select “Devices”. You should see an existing device called DHT11 Demo Device. This device publishes data produced by an MQTT protocol to ThingsBoard. In other words, this device is able to read the data produced by the TBPublish.py file and send it to ThingsBoard.
Open the DHT11 Demo Device by selecting it. Navigate to the Latest Telemetry tab to see the latest telemetry.
Provide a screenshot of the data in the latest telemetry tab to show that the DHT11 Demo Device is publishing the data produced by the TBPublish.py file to ThingsBoard.

<img width="535" alt="image" src="https://github.com/sandip86/Construct-a-web-server-using-Kafka/assets/153111110/7bf5a1d2-68a1-4161-bf7d-8d77218f58a5">

11.	Navigate to the main page of Firebase. Follow the steps in Video 24.3 to add a new project called module24Project.
Provide a screenshot to show that you created the module24Project project in Firebase.
 
12.	Follow the steps in Video 24.3 to create a Realtime database in Firebase. Add a field in your database titled temperature and initialize the corresponding field to zero.
Provide a screenshot to show that you created the temperature field inside your Realtime database.

<img width="475" alt="image" src="https://github.com/sandip86/Construct-a-web-server-using-Kafka/assets/153111110/57160408-6455-4f01-bf76-f84fb33602b1">

13.	Navigate to the Root Rule Chain in ThingsBoard. Add a “rest API call” node and name it Firebase. In the “Endpoint URL pattern” field, paste the link to your Realtime database from Firebase followed by "/temperature.json". Connect the “Firebase” node to the “Message Type Switch” node. Add “Post telemetry” as the link label.
Provide a screenshot to show that you have created the Firebase node correctly, connected it to the “Message Type Switch” node, and added “Post telemetry” as the link label.

<img width="563" alt="image" src="https://github.com/sandip86/Construct-a-web-server-using-Kafka/assets/153111110/9d74d1ad-2106-4392-8fa0-4ff73b9036ff">

14.	Navigate to Firebase and display your temperature and humidity data by expanding the entries in your Realtime database.
Provide a screenshot to show that your Realtime database is updating correctly and displaying your temperature and humidity data.
 
![image](https://github.com/sandip86/Construct-a-web-server-using-Kafka/assets/153111110/0a72e368-e5aa-480a-bdc3-47f00ba9df01)
