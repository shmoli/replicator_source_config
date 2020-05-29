# replicator_source_config

Example config to replicate data from an external cluster (OSS or Confluent Cloud) to a local confluent platform docker repo.

Instructions

* Stand up the environment

```docker-compose up -d --build```

This creates a 3 node cluster, replicator, connect, C3, schema registry etc.

* Wait a few moments for the components to start

* Edit cloud_to_local_repl.json or oss_to_local_repl.json to add the bootstrap servers and authentication details for an unsecured cluster or confluent cloud cluster.

* Send the edited replicator config to the replicator instance

```curl -X POST -H "Content-Type: application/json" --data "@cloud_to_local_repl.json" http://localhost:28083/connectors -v```

* All topics should now be present.  Browse to C3 to view replica topics etc.

[http://localhost:9021](http://localhost:9021)
