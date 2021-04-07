<p align="center">
  <img alt="logo" src="https://hsto.org/webt/83/nk/0y/83nk0ym623xt8yit1b3pq9tj4cs.png" width="128" />
</p>

# `node` image with additional useful apps installed

[![Build Status][badge_build_minor]][link_actions]
[![Build Status][badge_build_major]][link_actions]
[![Docker Pulls][badge_pulls]][link_hub]
[![Issues][badge_issues]][link_issues]
[![License][badge_license]][link_license]

## Why this image created?

Base [`node`][link_base_node_image] images does not contains installed `git`, for example ([issue][node-586]).

Applications from base images:

- `node`
- `yarn`
- `npm`

Installed applications list:

- `git`
- `bash`
- `openssh`
- `chromium`

> Page on `hub.docker.com` can be [found here][link_hub].

New **minor** `alpine`-based images _(e.g. `tarampampam/node:13.1-alpine`, if it does not exists previously)_ builds automatically every hour, **major** _(e.g. `tarampampam/node:13-alpine`)_ and `latest` rebuilds every 3 days.

## Supported tags

[![image stats](https://dockeri.co/image/tarampampam/node)][link_docker_tags]

All supported image tags [can be found here][link_docker_tags].

## How can I use this?

For example:

```bash
$ docker run --rm \
    --volume "$(pwd):/app" \
    --workdir "/app" \
    --user "$(id -u):$(id -g)" \
    tarampampam/node:13-alpine \
    npm install
```

Or using with `docker-compose.yml`:

```yml
services:
  node:
    image: sovanyio/node:13-alpine
    volumes:
    - ./src:/app:rw
    working_dir: /app
    command: []
```

### License

WTFPL. Use anywhere for your pleasure.
