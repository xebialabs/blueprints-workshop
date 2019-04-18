# Local Docker Deployment

## Introduction

Use this blueprint to deploy a Docker application with front-end and back-end services to Docker running locally. The release template that the blueprint generates will deploy the application and optionally undeploy it.

## Before you get started

If you're new to XebiaLabs blueprints, check out:

* [Get started with DevOps as Code](https://docs.xebialabs.com/xl-platform/concept/get-started-with-devops-as-code.html)
* [Get started with blueprints](https://docs.xebialabs.com/xl-platform/concept/get-started-with-blueprints.html)
* [Get started with XL JetPack](https://docs.xebialabs.com/xl-platform/concept/get-started-with-xl-jetpack.html)

## How to use this example:

### 1. Start the XLD/XLR Docker images
```
cd docker
docker-compose up
```

### 2. Create a temporare 'scratch' directory next to this one for the blueprint's output files
```
mkdir blueprints-workshop-scratch
cd blueprints-workshop-scratch
```

### 3. Run the blueprint

#### Linux / Mac
```
xl blueprint -b /path/to/blueprints-workshop/repository/example-0[1|2|3|4]
```

#### Windows
```
xl.exe blueprint -b \path\to\blueprints-workshop\repository\example-0[1|2|3|4]
```

### 4. Answer the prompts
Follow the instructions and fill in the questions

### 5. Apply the configs to XLR / XLD
```
xl apply -f xebialabs.yaml
```

## Tools and technologies

This blueprint includes the following tools and technologies:

* Target:
    * [Docker](https://www.docker.com/)
* Tools:
    * [XebiaLabs Release Orchestration](https://xebialabs.com/products/xl-release/)
    * [XebiaLabs Deployment Automation](https://xebialabs.com/products/xl-deploy/)
* Application or framework:
    * [Sample application API component](https://hub.docker.com/r/xebialabsunsupported/rest-o-rant-api)
    * [Sample application web component](https://hub.docker.com/r/xebialabsunsupported/rest-o-rant-web)

## Minimum Required versions

This blueprint version requires at least the below versions of the specified tools to work properly.

XL Release: Version 8.6
XL Deploy: Version 8.6.1
XL CLI: Version 8.6

## Prerequisites

To run the YAML that this blueprint generates, you need:

* XebiaLabs Release Orchestration and Deployment Automation up and running
* A local Docker installation up and running

## Information required

This blueprint requires:

* The application name
* The port where the application should be exposed
* Docker images for a front-end and back-end service

## Output

This blueprint will output:

* Release template
* Docker infrastructure
* A docker-compose setup for XL Release, XL Deploy & Docker proxy

## Tips and tricks

* Before using this blueprint, ensure that you have a front-end and a back-end application service packaged in Docker containers.
* The YAML that the blueprint generates includes optional steps to remove the application.

## Basic structure of a blueprint directory

    [blueprint directory/]
    ├── xebialabs/
    │   └── USAGE.md
    │
    ├── blueprint.yaml
    ├── README.md
    └── xebialabs.yaml

## Examples

This project consists of 4 examples, each building on the previous and showcasing a different aspect of blueprints. Though not comprehensive, they should serve as a springboard.

### example-01
* Introduces a basic blueprint taken from [Simple Demo App](https://github.com/xebialabs/blueprints/tree/development/docker/simple-demo-app)
  * Basic template (`.tmpl` file)
  * Variable interpolation
  * Text `Input` type
* Deploys a simple backend and frontend

### example-02
* Introduces the blueprint concepts of:
  * Patterns
  * boolean `Confirm`
  * `dependsOn` logic

### example-03
* Introduces the blueprint concepts of:
  * `Select` type
  * Default values

### example-04
* Introduces the blueprint concepts of:
  * Non-interactive fields using `value`
  * Basic `!expression`s

## Further reading

* [Get started with XebiaLabs blueprints](https://docs.xebialabs.com/xl-platform/concept/get-started-with-blueprints.html)
* [Blueprint YAML format](https://docs.xebialabs.com/xl-platform/concept/blueprint-yaml-format.html)
* [Tutorial for deploying an application to AWS using a blueprint](https://docs.xebialabs.com/xl-platform/how-to/deploy-to-aws-using-blueprints.html)

## Labels

* Docker
