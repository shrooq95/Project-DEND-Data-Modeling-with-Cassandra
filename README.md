# Project-DEND-Data-Modeling-with-Cassandra
Sparkify is a startup with a music streaming app. Data scientists at Sparkify are particularly interested in understanding what songs users are listening to.

## Goal
The goal of this project is to define a data model that will help our data scientists answer questions about user activity. In this case, we are working with a NoSQL database, Apache Cassandra, which means we have to be especially intentional in our data modeling. We first need to understand what queries our data scientists would like to run, and then we can design tables to fit those queries. We will be aiming for "1 query, 1 table".

## Why choose a NoSQL Database?

To get experience with a NoSQL database. But if think about this as if it were a real production system, we might ask:

### When would we want NoSQL over a relational DB?

Perhaps you have LARGE amounts of data. Because a relational database can only be scaled by adding machine memory, its very possible to have a table too large for a single machine. So if you want distributed tables, NoSQL is what you want. Some other potential reasons are: need for high throughput that isn't slowed down by ACID transactions or high availability. In our case Apache Cassandra is an AP tolerant system, so we're optimizing for availability and partition tolerance.

### What are the caveats of a NoSQL database like Apache Cassandra?

So first off, based on CAP Theorem, we know that what's being sacrificed by our AP tolerant system is consistency. Which means it's possible that a read from our DB might not give us the most up to date information, instead we settle for eventual consistency. Another thing we must take into account is the lack of JOINs. One of the nice aspects of a relational database is the query flexibility and capability to do aggregations. With Cassandra, we don't have that ability, so instead we must know about the queries our Data Scientists would like before hand so we can model our tables to fit them. And if our queries change, so must our tables.
