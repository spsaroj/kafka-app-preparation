
# Preparation for Kafka App

  

[Apache Kafka](https://kafka.apache.org/) is an open-source stream-processing software platform widely used in data science.

  

Before creating a Kafka app, we need to download Kafka. Easy installation guide can be found [here](https://kafka.apache.org/quickstart).

  

## Kafka Commands

  

Before running all the below commands, go to the folder where you have saved and un-tar ed Kafka. Go to bin folder within it.

  

### Start the zookeeper service

Open Powershell in the bin folder and run:

``` .\windows\zookeeper-server-start.bat .\config\zookeeper.properties```

**Do Not** close the powershell window.

  

### Start the kafka service

Open Powershell in the bin folder again and run:

``` .\windows\kafka-server-start.bat .\config\server.properties```

**Do Not** close the powershell window.

  

### Create a unique topic

Open Powershell in the bin folder again and run:

``` .\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --create --topic <topic-name> ```

The topic name can be any unique name you want to create. For example: community-messaging-app, university-mailing-tracker, my-todo etc.

  

I created app called help-desk-log-system.

  

### List all created topics

You can run the following command after the previous command gets executed.

``` .\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --list ```

This will list all the topics you have created.

  

### Start a Kafka producer for writing messages to your unique topic

Open a new powershell window in bin folder if you have closed the window where you created a topic and displayed them. Type the following command:

  

``` .\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic <topic-name> ```

  

### Start a Kafka consumer for retrieving messages from your unique topic

Open a new Powershell in the bin folder again and run:

  

``` .\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic <topic-name> --from-beginning```

This will display all the messages received from producer from the beginning.

### How it looks:
![screen capture](https://raw.githubusercontent.com/spsaroj/kafka-app-preparation/master/kafka-installation.PNG)