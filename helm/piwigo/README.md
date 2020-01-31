# Piwigo Helm Chart

This directory contains a Kubernetes chart to deploy Piwigo.

## Prerequisites Details

* Kubernetes 1.6+

## Chart Details

This chart will do the following:

* Implement a Piwigo deployment

## Installing the Chart
```console
$ helm install --name piwigo https://raw.githubusercontent.com/trankchung/piwigo/master/helm/piwigo-1.0.0.tgz
```

## Configuration

The following table lists the configurable parameters for the Piwigo chart and their default values.

|             Parameter                |              Description                  |               Default               |
|--------------------------------------|-------------------------------------------|-------------------------------------|
| `image.registry`                     | Container registry                        | `docker.io`                         |
| `image.repository`                   | Container image to use                    | `mathieuruellan/piwigo`             |
| `image.tag`                          | Container image tag to deploy             | `release-2.9.4`                     |
| `image.pullPolicy`                   | Container pull policy                     | `IfNotPresent`                      |
| `replicas`                           | Number of pods                            | `1`                                 |
| `service.type`                       | Service type                              | `ClusterIP`                         |
| `service.port`                       | Service port                              | `80`                                |
| `service.loadBalancerIP`             | Load balancer IP if `type=LoadBalancer`   | `""`                                |
| `service.nodePort`                   | Node port if `type=NodePort`              | `""`                                |
| `service.externalTrafficPolicy`      | External traffic policy                   | `Cluster`                           |
| `service.annotations`                | Service annotations                       | `{}`                                |
| `persistence.enabled`                | Persistent volume for Piwigo              | `true`                              |
| `persistence.accessMode`             | Persistent volume access mode             | `ReadWriteOnce`                     |
| `persistence.size`                   | Persistent volume size                    | `10Gi`                              |
| `persistence.storageClass`           | Persistent volume storage class           | `""`                                |
| `ingress.enabled`                    | Enable ingress generation                 | `false`                             |
| `ingress.annotations`                | Ingress annotations                       | `{}`                                |
| `ingress.hosts[0].name`              | Host DNS name                             | `piwigo.local`                      |
| `ingress.hosts[0].path`              | Host path                                 | `/`                                 |
| `ingress.hosts[0].tls`               | Enable TLS security                       | `true`                              |
| `ingress.hosts[0].tlsHosts`          | Additional TSL host names                 | `[]`                                |
| `ingress.hosts[0].tlsSecret`         | TLS secret name                           | `qbittorent-tls-cert`               |
| `extraEnvVars`                       | Additional env variables for deployment   | `{}`                                |
| `strategy`                           | Pod upgrade strategy                      | `{}`                                |
| `securityContext`                    | Pod security context                      | `{}`                                |
| `resources`                          | Pod resource requests/limts               | `{}`                                |
| `nodeSelector`                       | Pod node selector                         | `{}`                                |
| `affinity`                           | Pod affinity                              | `{}`                                |

