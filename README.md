# psawsdynamodbdd
## 3. Getting Started with DynamoDB
### 2 Basic Concepts
Key Types
- Simple key (partition)
- composite (partition and sort)  


key attributes should be decided in advance and cant be changed


### 5 DynamoDB Internals
Partition Size Limit
- Partition can store up to 10GB
- Items with different ids are moved to different partitions
- Range key is limited to max size of a partition

### 6 Data Consistency
- Strongly consistent read - returns the most recent write
- (require 1 RCU , should be used if you cant tolerate stale data)
- Eventually consistent read - may return some stale data
- (require 0.5 RCU, can be used when stale data is not an issue, help to reduce cost)


### 7 Secondary Indexes
Querys they dont support
- Sort posts from a user by rating or time
- Find all posts for topic/user

Types
- Local secondary (select a different sort order for a partition key) values can be duplicated,limited by size of partition
- Global secondary (Access data using a different partition key) copy with different partition key,always eventially consistent unlimited size, can store subset of attributes. You can emulate LSI using GSI  


limitations
- 5 GSI LSI per table
- Single LSI can only be up to 10GB


### 9 Pricing
