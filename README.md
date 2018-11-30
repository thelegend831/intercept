# Intercept

Machinery for `telepresence intercept`

## Quick and dirty demo

Here's the setup for the demo I did over Zoom on Friday afternoon.

### The Application

The application is a [simple echo server](https://github.com/jmalloc/echo-server) for HTTP requests. It responds to requests on port 8080 with its hostname and the headers it received.

#### Local

I have the application running on my local machine in Docker with the port published.

```shell
$ docker run --rm -d -h container_on_laptop -p 8080:8080 jmalloc/echo-server
06c51f70a36037e3b94bfb413148129b8ac97fecdc4ebff96d0f4ea437496181
$ curl localhost:8080/foo/bar
Request served by container_on_laptop

HTTP/1.1 GET /foo/bar

Host: localhost:8080
User-Agent: curl/7.54.0
Accept: */*

$ 
```

#### Cluster

I have the application running in the cluster as the-app. The manifests I used to launch it are in example/the-app.yaml.


