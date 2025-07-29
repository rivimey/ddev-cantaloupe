[![add-on registry](https://img.shields.io/badge/DDEV-Add--on_Registry-blue)](https://addons.ddev.com)
[![tests](https://github.com/rivimey/ddev-cantaloupe/actions/workflows/tests.yml/badge.svg?branch=main)](https://github.com/rivimey/ddev-cantaloupe/actions/workflows/tests.yml?query=branch%3Amain)
[![last commit](https://img.shields.io/github/last-commit/rivimey/ddev-cantaloupe)](https://github.com/rivimey/ddev-cantaloupe/commits)
[![release](https://img.shields.io/github/v/release/rivimey/ddev-cantaloupe)](https://github.com/rivimey/ddev-cantaloupe/releases/latest)

# DDEV Cantaloupe

## Overview

This add-on integrates Cantaloupe into your [DDEV](https://ddev.com/) project.

**TESTING**
The dockerfiles here are not expected to work as-is.

``islandora-Dockerfile`` is from https://hub.docker.com/r/islandora/cantaloupe
which has been updated for version 5 of Cantaloupe, but is also for a tuned
version of the Islandora application and so may have dependencies on that.

``ivanwissen-Dockerfile`` is from https://github.com/LvanWissen/docker-cantaloupe
which is intended as a general purpose thing but is for pre-v5 Cantaloupe on
ubuntu 18.04 (which at time of writing is very old).

I am not sure if either represents a good starting point for ddev-cantaloupe.

Cantaloupe in general will need a data directory for image cache, which could
grow very big. Ideally a ddev version will do something automagically but it
may need tuning.

## Installation

```bash
ddev add-on get rivimey/ddev-cantaloupe
ddev restart
```

After installation, make sure to commit the `.ddev` directory to version control.

## Usage

| Command | Description |
| ------- | ----------- |
| `ddev describe` | View service status and used ports for Cantaloupe |
| `ddev logs -s cantaloupe` | Check Cantaloupe logs |

## Advanced Customization

To change the Docker image:

```bash
ddev dotenv set .ddev/.env.cantaloupe --cantaloupe-docker-image="busybox:stable"
ddev add-on get rivimey/ddev-cantaloupe
ddev restart
```

Make sure to commit the `.ddev/.env.cantaloupe` file to version control.

All customization options (use with caution):

| Variable | Flag | Default |
| -------- | ---- | ------- |
| `CANTALOUPE_DOCKER_IMAGE` | `--cantaloupe-docker-image` | `busybox:stable` |

## Credits

**Contributed and maintained by [@rivimey](https://github.com/rivimey)**
