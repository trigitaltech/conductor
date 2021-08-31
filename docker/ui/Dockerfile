#
# conductor:ui - Netflix conductor UI
#
FROM node:14-alpine
LABEL maintainer="Netflix OSS <conductor@netflix.com>"

# Install the required packages for the node build
# to run on alpine
RUN apk update && apk add python make g++
 
# A directory within the virtualized Docker environment
# Becomes more relevant when using Docker Compose later
WORKDIR /usr/src/app
 
# Copies package.json and package-lock.json to Docker environment
COPY ./ui/package.json ./
 
# Installs all node packages
RUN yarn install
 
# Copies everything over to Docker environment
COPY ./ui .
 
# Uses port which is used by the actual application
EXPOSE 3000
 
# Finally runs the application
CMD [ "yarn", "start" ]
