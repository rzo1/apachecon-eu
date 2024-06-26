---
title: "Let’s see how fast Impala runs on Iceberg"
slug: lets-see-how-fast-impala-runs-on-iceberg
speakers:
 - Gabor Kaszab
 - Zoltan Borok-Nagy
time_start: 2024-06-05 12:30:00
time_end: 2024-06-05 13:00:00
track: Performance Engineering
day: 3
timeslot: 7
room: Symphony

---

Apache Impala is a distributed massively parallel query engine designed for high-performance querying of large-scale data. There has been a long list of new features recently around supporting Apache Iceberg tables such as reading, writing, time traveling, and so on. However, in a big data environment it is also a must to be performant. Since Impala has been designed to be fast, it has its own way of reading Iceberg tables. Other engines might simply use the Iceberg library to perform reads, while Impala has a C++ implementation itself optimized for speed.
 
 
 
 Nowadays, even big data storage techniques have to offer the possibility not just to store data but also to alter and delete data on a row level. Apache Iceberg solves this by using delete files that live alongside the data files. It is the responsibility of the query engines to then apply the delete files on the data files when querying the data. To efficiently read the data of such tables we implemented new Iceberg-specific operators in Impala.
 
 
 
 In this talk we will go into the implementation details and reveal what is the secret behind Impala’s great performance in general and also when reading Iceberg tables with position delete files. We will also show some measurements where we compare Impala’s performance with other open-source query engines.
 
 
 
 By the end of this talk, you should have a high-level understanding of Impala’s and Iceberg’s architecture, the performance tricks we implemented in Impala specifically for Iceberg, and you will see how Impala competes with other engines.