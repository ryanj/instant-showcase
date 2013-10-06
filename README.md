#Meteor.js on OpenShift
Deploy [meteor.js](http://meteor.com/) application bundles on [OpenShift](http://openshift.com/)

This repo includes the expanded output from a meteor application bundle generated via the following process: [openshift-meteorjs-quickstart](https://github.com/ryanj/openshift-meteorjs-quickstart)

<a href='https://openshift.redhat.com/community/blogs/cloudy-with-a-chance-of-meteorjs'><img src='https://openshift.redhat.com/community/sites/default/files/meteorshift_1.png'/></a>

If this is your first time using [OpenShift Online](http://openshift.com/) or [Meteor](http://meteor.com/), skip down to the "[Basic Setup Notes](https://github.com/openshift-quickstart/openshift-meteorjs-quickstart#basic-setup-notes)" below.

## Showcase Instant App 
First, register a new application on GitHub: [https://github.com/settings/applications/new](https://github.com/settings/applications/new).

You'll need the Github tokens for the next step, so fill in your expected application url, and callback address.

[This showcase application](https://github.com/ryanj/meteor-showcase) has been bundled and re-packed in the following repo, allowing for instant deployment: [https://github.com/ryanj/instant-showcase](https://github.com/ryanj/instant-showcase)

    rhc app create showcase nodejs-0.10 mongodb-2.2 --no-git --from-code=https://github.com/ryanj/instant-showcase.git --env GITHUB_CLIENT=$YOUR_GITHUB_CLIENT_TOKEN --env GITHUB_SECRET=$YOUR_GITHUB_CLIENT_SECRET

The above command will return a live url where your copy of the application can be accessed.

## Basic Setup Notes
You'll need an OpenShift Online account, and the `rhc` command-line tools in order to follow this guide.  You'll also need to have [Node.js](http://nodejs.org), [MongoDB](http://mongodb.org), and **Meteor** available in your application developement environment. 

### Installing meteor.js

    curl https://install.meteor.com | sh

### OpenShift Online Setup
In this quickstart guide, we'll be using OpenShift Online to host our application.

Sign up for an account at http://openshift.redhat.com/app/account/new

If you don't already have the `rhc` [(Red Hat Cloud) command-line tools](https://openshift.redhat.com/community/get-started#cli), install them:

    sudo gem install rhc

You'll need to run `rhc setup` to link your OpenShift Online account with your local development environment, and to select an application namespace:

    rhc setup

If you need any additional assistance setting up `rhc`, this doc may come in handy: https://openshift.redhat.com/community/developers/rhc-client-tools-install
