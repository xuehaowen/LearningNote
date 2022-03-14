# Reliable, Scalable, and Maintainable Applications

Data-intensive applications need to:
* Store data so that they, or another application, can find it again later (databases)
* Remember the result of an expensive operation, to speed up reads (caches)
* Allow user to search data by keyword or filter it in various ways (search indexes)
* Send a message to another process, to be handled asynchronously (stream processing)
* Periodically crunch a large amount of accumulated data (batch processing)

Tools for data storage and processing have merged:
* There are datastores that are also used as message queues (Redis)
* There are message queues with database-like durability guarantees (Apache Kafka)

A single tool can no longer meet all of its data processing and storage needs. Instead, the work is broken down into tasks that can be performed on a single tool, and those different tools are stitched together using application code.

#### Reliability
The system should continue to work **correctly** (performing the correct function at the desired level of performance) even in the face of adversity (hardware or software faults, and even human error).

#### Scalability
As the system **grows** (in data volume, traffic volume, or complexity), there should be reasonable ways of dealing with that growth.

#### Maintainability
Over time, many different people will work on the system (engineering and operations, both maintaining current behavior and adapting the system to new use cases), and they should all be able to work on it **productively**.

Percentiles: e.g., p99 = 1.5s, means 99 out of 100 requests take less than 1.5s, and 1 out of 100 requests take 1.5s or more. 

Tail Latency Amplification: When several backend calls are needed to serve a request, it takes just a single slow backend request to slow down the entire end-user request.

