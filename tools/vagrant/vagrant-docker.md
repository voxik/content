---
title: Vagrant with Docker provider
page: vagrant
---

## Vagrant with Docker support installation


To use Vagrant with Docker, you need to install the `vagrant` and `docker` packages:

```
# dnf install vagrant docker
```

And start `docker` service:

```
# systemctl start docker
```

Vagrant itself comes with the support for Docker baked-in. By installing Docker alongside
Vagrant you can start using Docker both as a provider and a provisioner. Please refer to
the official documentation at https://docs.vagrantup.com/v2/ for more.

And do not forget that when using Docker as a Vagrant provider, all Vagrant commands have to
be ran as root (e.g. with `sudo`). This is similar to running Docker commands directly.

### Using Docker as a default

To use Docker provider with any Vagrant commands, one has to explicitly append `--provider=docker`.

To avoid this, you can set the default provider for your project in the beginning of your
Vagrantfile as:

```
# Vagrantfile
ENV['VAGRANT_DEFAULT_PROVIDER'] = 'docker'
...
```

Or set it for your environment with:

```
export VAGRANT_DEFAULT_PROVIDER=docker
```