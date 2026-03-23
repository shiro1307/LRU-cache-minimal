# LRU Cache - basic implementation in Python

## Overview

This project implements a Least Recently Used (LRU) cache using a combination of a hash map and a doubly linked list. The design ensures constant time complexity for both read and write operations.

## Design

* Hash map stores key to node mappings for O(1) access
* Doubly linked list maintains usage order

  * Front represents most recently used
  * Back represents least recently used
* When capacity is reached, the least recently used item is evicted

## Operations

* `get(key)`

  * Returns the value if the key exists
  * Updates the key as most recently used
  * Returns `None` if the key is not present

* `put(key, value)`

  * Inserts a new key or updates an existing key
  * Moves the key to most recently used position
  * Evicts the least recently used item if capacity is exceeded

## Complexity

* Time: O(1) for both `get` and `put`
* Space: O(n) where n is the cache capacity

## Structure

* `LRUnode`: Node for doubly linked list
* `LRUchain`: Doubly linked list with sentinel nodes
* `LRUcache`: Main cache implementation

## Usage

```python
cache = LRUcache()

cache.put(1, 1)
cache.put(2, 2)

print(cache.get(1))  # 1

cache.put(3, 3)      # evicts key 2

print(cache.get(2))  # None
```

## Notes

* Capacity is fixed at initialization
* Implementation uses sentinel nodes to simplify edge cases
* No external dependencies
