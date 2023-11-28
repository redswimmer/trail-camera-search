# Trail Camera Image and Video Search with Meta AI ImageBind
This example demonstrates how to build a multi-modal search (image and video) using the [Meta AI ImageBind](https://videobind.metademolab.com/) and the [Weaviate](https://weaviate.io/) vector database and was based off an example from [Weaviate here](https://github.com/weaviate/recipes/blob/main/media-search/media_search_bind.ipynb).

Querying using one modality (e.g. text) will include results in all available modalities (e.g. images and video), as all objects will be encoded into a single vector space.

Here is a link to a [demo video](https://www.loom.com/share/a272c0c08ae74b1db778c63934d17fc9?sid=9d35af16-dcbf-4313-9fb9-ecad34e12b11) I recorded if you don't want to play with the code.

## Weaviate Setup

The ImageBind model is only available with local Weaviate deployments with Docker or Kubernetes.

ImageBind is not supported with Weaviate Cloud Services (WCS).

### Steps to deploy Weaviate locally with ImageBind

1. Install Docker.
    
   > If you are new to `Docker Compose`, [here are instructions on how to install it](https://docs.docker.com/compose/install/).

2. Run Weaviate+Bind with Docker Compose

     In the terminal, navigate to the root director of this project and locate the file `docker-compose.yml` and call:

    ```
    docker compose up
    ```
    
    > Note #1 - the first time you run the command, Docker will download a ~6GB image.
  
    > Note #2 – running this Docker image requires 12GB of RAM.  If you're in Windows you'll need to adjust your .wslconfig to include the following:

    ```
    [wsl2]
    memory=12GB
    ```
