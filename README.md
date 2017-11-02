# Varnish

The Varnish setup we at Livingdocs currently use for the delivery.

## Configuration options

All configuration is done via environment variables.

### Build

* (optional) `VARNISH_CONFIG`
    * defaults to `/etc/varnish/default.vcl`
    * use this if you'd like to mount a config file to another location
* (optional) `VARNISH_CACHE_SIZE`
    * defaults to `512m`
* (optional) `VARNISH_PORT`
    * defaults to `80`

### Run

* `BACKEND` the hostname:port of the backend, supports comma delimited values


## Create a container and give it a name

```bash
docker run -p 80:80 --env BACKEND=backend:9090 --name varnish livingdocs/varnish
```

## Start an existing container

```bash
docker start varnish
```


## To build this image manually

```bash
docker build \
#    --env VARNISH_CONFIG=/etc/varnish/default.vcl \
#    --env VARNISH_CACHE_SIZE=512m \
#    --env VARNISH_PORT=80 \
    --tag livingdocs/varnish .
```
