Using Docker:

Start all the Containers
$ docker-compose up

Open another terminal

Shell into the container running Kafka:

$ docker exec -it starter_kafka0_1 /bin/sh

Create your first topic:

# kafka-topics --create --zookeeper zookeeper:2181 --topic sean.test.topic --replication-factor 1 --partitions 10

Write a message to the topic:

# kafka-console-producer --broker-list localhost:9092 --topic sean.test.topic
>{"sensorpayload":test}

Hit CTRL+C to exit console.

Create a consumer of your topic:

# kafka-console-consumer --bootstrap-server localhost:9092 --topic sean.test.topic --from-beginning

Watch for the message you sent earlier.

Open another terminal

Shell into the container running Kafka:

$ docker exec -it starter_kafka0_1 /bin/sh

Write another message to the topic

# kafka-console-producer --broker-list localhost:9092 --topic sean.test.topic
>{"sensorpayload":test2}

Watch the consumer for the new message to appear.






# Using the Workspace:

Run the startup script

$ ./startup.sh

Create your first topic:

# kafka-topics --create --zookeeper localhost:2181 --topic sean.test.topic --replication-factor 1 --partitions 10

# kafka-console-producer --broker-list localhost:9092 --topic sean.test.topic
>{"sensorpayload":test}
>^C

Hit CTRL+C to exit console.

Create a consumer of your test topic:

# kafka-console-consumer --bootstrap-server localhost:9092 --topic sean.test.topic --from-beginning

Watch for the message you sent earlier.

Open another terminal

Write another message to the topic:

# kafka-console-producer --broker-list localhost:9092 --topic sean.test.topic
>{"sensorpayload":test2}

Watch the consumer terminal for the new message to appear
