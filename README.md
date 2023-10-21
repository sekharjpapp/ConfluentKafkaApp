# ConfluentKafkaApp

How to Run Confluent on Windows in Minutes

1. Install Windows Subsystem for Linux 2
   
https://www.confluent.io/blog/set-up-and-run-kafka-on-windows-and-wsl-2/

$wget https://packages.confluent.io/archive/6.1/confluent-6.1.0.tar.gz

$tar -xvf confluent-6.1.0.tar.gz

Set the CONFLUENT_HOME environment variable
To preserve the CONFLUENT_HOME setting between terminal sessions, add the previous export commands to your .bashrc file.
$vi .bashrc
export CONFLUENT_HOME=~/confluent-6.1.0
export PATH=$CONFLUENT_HOME/bin:$PATH

restart ubuntu terminal 
$confluent-hub install --no-prompt confluentinc/kafka-connect-datagen:latest
Running in a "--no-prompt" mode
Implicit acceptance of the license below:
Apache License 2.0
https://www.apache.org/licenses/LICENSE-2.0
Downloading component Kafka Connect Datagen 0.4.0, provided by Confluent, Inc. from Confluent Hub and installing into /home/jim/confluent-6.1.0/share/confluent-hub-components
Adding installation directory to plugin path in the following files:
  /home/jim/confluent-6.1.0/etc/kafka/connect-distributed.properties
  /home/jim/confluent-6.1.0/etc/kafka/connect-standalone.properties
  /home/jim/confluent-6.1.0/etc/schema-registry/connect-avro-distributed.properties
  /home/jim/confluent-6.1.0/etc/schema-registry/connect-avro-standalone.properties
Completed

$confluent local services start

The local commands are intended for a single-node development environment only,
NOT for production usage. https://docs.confluent.io/current/cli/index.html
Using CONFLUENT_CURRENT: /tmp/confluent.485994
Starting ZooKeeper
ZooKeeper is [UP]
Starting Kafka
Kafka is [UP]
Starting Schema Registry
Schema Registry is [UP]
Starting Kafka REST
Kafka REST is [UP]
Connect is [UP]
ksqlDB Server is [UP]
Control Center is [UP]

-----
Use Confluent Control Center to view your cluster

To inspect and manage your cluster, open a web browser to http://localhost:9021/. You’ll see the “Clusters” page, which shows your running Kafka cluster and the attached Kafka Connect and ksqlDB clusters.



