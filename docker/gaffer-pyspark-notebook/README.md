gafferpy Jupyter Notebook
==========================
In this folder you can find the required files for building and running a Gaffer PySpark Jupyter Notebook.

This extends [scipy-notebook](https://github.com/jupyter/docker-stacks/tree/master/scipy-notebook) to include:
* OpenJDK 11 JRE
* AWS CLI
* Hadoop
* Spark
* `kubectl` and the `kubernetes` python package
* [gafferpy](https://github.com/gchq/gaffer-tools/tree/master/python-shell)

Some example notebooks that demonstrate how to query Gaffer and use Spark are available at [`/examples`](examples/).

## Running Locally on a Single Node
The easiest way to build and run these services locally is to use docker compose, by running the following from this directory:
```bash
docker compose up
```

## Containers that are started:
* Zookeeper
* HDFS
  * Datanode
  * Namenode
* Accumulo
  * Monitor
  * GC
  * tserver
  * Master
* Gaffer REST
* Jupyter Notebook

Access the HDFS NameNode web UI at: http://localhost:9870

Access the Accumulo Monitor UI at: http://localhost:9995

Access the Gaffer REST API at: http://localhost:8080/rest/

Access the Jupyter Notebook at: http://localhost:8888

To access the notebook, you have to produce an autogenerated token. You can retrieve this token by running `docker compose exec notebook jupyter notebook list`

## Running on a Kubernetes cluster

See the [gaffer-jhub Helm Chart](../../kubernetes/gaffer-jhub/)
