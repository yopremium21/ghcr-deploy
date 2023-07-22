

# Push a image to Github Packages (GHCR)
1. Create image
2. Create PAT on Github
3. Authenticate GHCR
4. Tag and push our image to GHCR

```
export CR_PAT=<TOKEN>
echo $CR_PAT | docker login ghcr.io -u USERNAME --password-stdin
```

# Use Github Actions to Publish a Docker image to Github Packages (GHCR)


Steps To create and push to ghcr.io
1. sudo docker pull ubuntu:latest
2. sudo docker images
3. sudo docker run -it [IMAGE ID] bin/bash
4. install all packages you need
5. exit
6. sudo docker ps -a
7. sudo docker commit [CONTAINER_ID] [ghcr.io/yopremium21/botstatus:main]
8. sudo docker images
9. Login to ghcr.io
  1.Generate personal access token from github setting-> Developer setting -> New personal access token (classic)
  2.Name Token and check box write:packages and delete:packages
  3. Copy generated token like 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
  4. sudo docker login --username yopremium21 --password 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 ghcr.io
  5. Login Succeeded
10.sudo docker push ghcr.io/yopremium21/botstatus:main
1. Create repo - and Checkin our Dockerfile
2. Build your Github action workflow
3. Trigger our workflow
