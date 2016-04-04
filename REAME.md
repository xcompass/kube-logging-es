ElasicSearch for Kubernetes Logging
===================================

This image is based on the code in Kubernetes addon: https://github.com/kubernetes/kubernetes/tree/master/cluster/addons/fluentd-elasticsearch, with updated to latest version of Elasticsearch and official base image.

# Run on OSX
Because of the permission issue (AccessDenied message): See comments here: `https://hub.docker.com/_/elasticsearch/`, we need to change elasticsearch user to uid 1000.

```
docker run -it --rm -v `pwd`/data:/data es /bin/bash -c 'usermod -u 1000 elasticsearch; gosu elasticsearch elasticsearch'
```

# Limitations:

* This repo includes a pre-compiled version of elasticsearch_logging_discovery. Because it doesn't compile right now due to an error from upstream repos.
```
../../../src/k8s.io/kubernetes/pkg/util/parsers/parsers.go:30: undefined: parsers.ParseRepositoryTag
```
