# Drone.io

[Drone](http://readme.drone.io/) is a Continuous Integration platform built on container technology.

## TL;DR;

```console
$ helm install incubator/drone
```

## Installing the Chart

To install the chart with the release name `my-release`:

```console
$ helm install --name my-release incubator/drone
```

## Uninstalling the Chart

To uninstall/delete the `my-release` deployment:

```console
$ helm delete my-release
```

The command removes nearly all the Kubernetes components associated with the
chart and deletes the release.

## Configuration

The following tables lists the configurable parameters of the drone charts and their default values.

| Parameter                   | Description                                                                                   | Default                     |
|-----------------------------|-----------------------------------------------------------------------------------------------|-----------------------------|
| `images.server.repository`  | Drone **server** image                                                                        | `docker.io/drone/drone`     |
| `images.server.tag`         | Drone **server** image tag                                                                    | `0.8.2`                     |
| `images.server.pullPolicy`  | Drone **server** image pull policy                                                            | `IfNotPresent`              |
| `images.agent.repository`   | Drone **agent** image                                                                         | `docker.io/drone/agent`     |
| `images.agent.tag`          | Drone **agent** image tag                                                                     | `0.8.2`                     |
| `images.agent.pullPolicy`   | Drone **agent** image pull policy                                                             | `IfNotPresent`              |
| `images.dind.repository`    | Docker **dind** image                                                                         | `docker.io/library/docker`  |
| `images.dind.tag`           | Docker **dind** image tag                                                                     | `17.12.0-ce-dind`           |
| `images.dind.pullPolicy`    | Docker **dind** image pull policy                                                             | `IfNotPresent`              |
| `service.httpPort`          | Drone's Web GUI HTTP port                                                                     | `80`                        |
| `service.httpPort`          | Drone's Web GUI HTTP port                                                                     | `80`                        |
| `service.nodePort`          | If `service.type` is `NodePort` and this is non-empty, sets the http node port of the service | `32015`                     |
| `service.type`              | Service type (ClusterIP, NodePort or LoadBalancer)                                            | `ClusterIP`                 |
| `ingress.enabled`           | Enables Ingress for Drone                                                                     | `false`                     |
| `ingress.annotations`       | Ingress annotations                                                                           | `{}`                        |
| `ingress.hosts`             | Ingress accepted hostnames                                                                    | `nil`                       |
| `ingress.tls`               | Ingress TLS configuration                                                                     | `[]`                        |
| `server.host`               | Drone **server** hostname                                                                     | `(internal hostname)`       |
| `server.env`                | Drone **server** environment variables                                                        | `(default values)`          |
| `server.resources`          | Drone **server** pod resource requests & limits                                               | `{}`                        |
| `agent.env`                 | Drone **agent** environment variables                                                         | `(default values)`          |
| `agent.resources`           | Drone **agent** pod resource requests & limits                                                | `{}`                        |
| `dind.driver`               | **DinD** storage driver                                                                       | `overlay2`                  |
| `dind.resources`            | **DinD** pod resource requests & limits                                                       | `{}`                        |
| `persistence.enabled`       | Use a PVC to persist data                                                                     | `true`                      |
| `persistence.existingClaim` | Use an existing PVC to persist data                                                           | `nil`                       |
| `persistence.storageClass`  | Storage class of backing PVC                                                                  | `nil`                       |
| `persistence.accessMode`    | Use volume as ReadOnly or ReadWrite                                                           | `ReadWriteOnce`             |
| `persistence.size`          | Size of data volume                                                                           | `1Gi`                       |
| `sharedSecret`              | Drone server and agent shared secret                                                          | `(random value)`            |
