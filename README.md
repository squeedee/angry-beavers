# Angry Beavers

Spoot!

I'm observing an [nginx app and service](./control/control-service.yaml) coming up within a few seconds, and the
health check endpoint showing in the logs:

```
10.244.0.1 - - [26/Jan/2024:13:11:58 +0000] "GET /ready HTTP/1.1" 200 4 "-" "kube-probe/1.27"
```

However curling from another pod to the service `control` it takes a long time from the curl request to the first time the 
server logs:

```
10.244.0.113 - - [26/Jan/2024:13:12:05 +0000] "GET /info HTTP/1.1" 200 1424 "-" "curl/8.5.0"
```


[run-local](./run-local) executes this scenario with a local curl and port forward. So far, *this does not* evidence the issue.

