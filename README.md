Here is a quick start guide for using Docker:

## Installing Docker

1. Download and install Docker Desktop for your operating system (Windows, macOS, or Linux) from the official Docker website: https://www.docker.com/products/docker-desktop

2. Once installed, open a terminal and verify Docker is running correctly by running:

```bash
docker run hello-world
```

You should see a message printed indicating that Docker is installed and running successfully. [1]

## Building Your First Docker Image

1. Create a new directory and navigate into it.

2. Create a file named `Dockerfile` with the following content:

```dockerfile
# Use the official Node.js image 
FROM node:18

# Create app directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install app dependencies
RUN npm install

# Copy app source code 
COPY . .

# Expose the port the app runs on
EXPOSE 3000

# Start the app
CMD [ "npm", "start" ]
```

3. Create a `package.json` file for your Node.js app.

4. Build the Docker image by running:

```bash
docker build -t my-node-app .
```

5. Run the Docker container with:

```bash
docker run -p 3000:3000 my-node-app
```

This will start your Node.js app in a Docker container mapped to port 3000 on your host machine. [2]

## Using Docker Hub

Docker Hub is a cloud-based registry service for finding and sharing container images.

1. Create a free Docker Hub account at https://hub.docker.com

2. Log in to the Docker Hub from the command line:

```bash
docker login
```

3. After building an image, you can push it to Docker Hub:

```bash 
docker push username/my-node-app
```

This allows you to share your Docker images publicly or pull them from any Docker environment. [5]

This covers the basics of installing Docker, building your first image, running a container, and using Docker Hub to share images. The Docker documentation has many more guides to explore more advanced Docker features and workflows. [1][2][4][5]

Citations:
[1] https://docker-curriculum.com
[2] https://blog.packagecloud.io/docker-quick-start-guide/
[3] https://www.simplilearn.com/tutorials/docker-tutorial/getting-started-with-docker
[4] https://docs.docker.com/get-started/
[5] https://docs.docker.com/docker-hub/quickstart/
[6] https://docs.docker.com/desktop/extensions-sdk/quickstart/
[7] https://github.com/docker/getting-started
[8] https://www.reddit.com/r/webdev/comments/fca48o/docker_quickstart_guide_for_developers/
