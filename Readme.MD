Run kafka using Docker

Ref:https://medium.com/@amberkakkar01/getting-started-with-apache-kafka-on-docker-a-step-by-step-guide-48e71e241cf2

docker-compose up -d
docker ps 
docker exec -it 6903ba08fa29 /opt/kafka/bin/kafka-topics.sh --create --zookeeper zookeeper:2181 --replication-factor 1 --partitions 1 --topic my-topic1  
docker exec -it 6903ba08fa29 /opt/kafka/bin/kafka-console-producer.sh --broker-list localhost:9092 --topic my-topic1
docker exec -it  6903ba08fa29  /opt/kafka/bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic my-topic1 --from-beginning
docker-compose down
