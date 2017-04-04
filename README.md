# Building a Scalable Pub/Sub System with UpRing

The world is real-time: our users expect to receive live notifications, updates, and use extremely reactive interfaces. In a real-time world, we might want to connect physical things, each of them with their own live connection to the cloud. Delivering live notifications has always been a complex task, but tools like WebSockets and Socket.io have enabled a wide range of applications to flourish. Scaling those systems has often turns out to be problematic, and they generally leverage an external publish/subscribe broker to deliver the messages, with our application or the framework to act as a proxy. Those brokers are usually central points of failure, and are extremely hard to scale. UpRing is a distributed system framework for building applications on top of a Consistent Hashring. In other words, UpRing is a P2P system for cloud applications. With UpRing, all the notifications for a single element are routed through the same server, removing the central point of failure and allowing for fine-grained elastic scalability in ratio to the amount of current users.

[**UpRing**][upring] provides application-level sharding, based on node.js streams. UpRing allocates some resources to a node, based on the hash of a `key`, and allows you to query the node using a request response pattern (based on JS objects) which can embed streams.

[**UpRing**][upring] simplifies the implementation and deployment of a cluster of nodes using a gossip membership protocol and a [consistent hashing](https://en.wikipedia.org/wiki/Consistent_hashing) scheme (see [swim-hashring](https://github.com/mcollina/swim-hashring)). It uses [tentacoli](https://github.com/mcollina/tentacoli) as a transport layer.

## View slides locally

First, ensure you have the following installed:

1. [Node.js](http://nodejs.org)
2. [Bower](http://bower.io): `$ npm install -g bower`
3. [Gulp](http://gulpjs.com): `$ npm install -g gulp`

Then, install dependencies and run the preview server:

```bash
$ npm install && bower install
$ gulp serve
```

[upring]: https://github.com/mcollina/upring
