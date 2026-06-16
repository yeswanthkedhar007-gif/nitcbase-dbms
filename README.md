# NITCbase DBMS

### A Mini Relational Database Engine Built from Scratch in C++

This project is a complete implementation of a lightweight **Relational Database Management System (RDBMS)** developed in **C++**, following the NITCbase roadmap.

It simulates the internal working of real-world database systems by implementing core modules such as **disk block management**, **buffer handling**, **catalog management**, **query execution**, and **B+ Tree indexing**.

The goal of this project was to gain a deep understanding of how databases work internally beyond SQL-level abstraction.

---

## Project Overview

Modern DBMS systems hide complex internal mechanisms such as storage management, indexing, and query processing. This project rebuilds those core components from scratch.

This database engine supports:

* Relation creation and deletion
* Record insertion
* Record retrieval
* Projection
* Selection
* Join operations
* B+ Tree based indexing

The architecture is modular and closely resembles the layered design used in production DBMS systems.

---

## Core Features

### 1. Disk Management

Implemented a block-based storage layer to simulate persistent disk storage.

Features:

* Fixed-size disk blocks
* Block allocation management
* Disk read/write abstraction
* Persistent relation storage

---

### 2. Buffer Management

Designed an in-memory buffer manager to reduce disk I/O.

Features:

* Static buffer pool
* Block buffering
* Efficient block retrieval
* Cache-based disk access optimization

---

### 3. Catalog Management

Built metadata management modules for relations and attributes.

Includes:

* Relation Catalog
* Attribute Catalog
* Open Relation Table
* Relation Cache Table
* Attribute Cache Table

Purpose:

* Stores schema information
* Tracks active relations
* Improves metadata lookup efficiency

---

### 4. Query Processing Engine

Implemented relational algebra operations.

Supported Operations:

#### SELECT

Filters records based on conditions.

Example:

```sql
SELECT * FROM STUDENTS WHERE AGE > 20;
```

#### PROJECT

Retrieves specific attributes.

Example:

```sql
SELECT NAME FROM STUDENTS;
```

#### INSERT

Adds new records into relations.

Example:

```sql
INSERT INTO STUDENTS VALUES (...);
```

#### JOIN

Combines records from multiple relations.

Example:

```sql
JOIN STUDENTS AND MARKS;
```

---

### 5. B+ Tree Indexing

Implemented B+ Tree data structure for optimized search.

Features:

* Index creation
* Index deletion
* Indexed search
* Faster lookup compared to linear search

Benefits:

* Reduces search complexity
* Improves query performance

---

## System Architecture

```text
User Query
   ↓
Frontend Interface
   ↓
Query Processor (Algebra)
   ↓
Schema Manager
   ↓
Cache Manager
   ↓
Buffer Manager
   ↓
Disk Layer
```

This layered architecture improves modularity and maintainability.

---

## Project Structure

```text
nitcbase-dbms/
├── Algebra/              # Query execution logic
├── BPlusTree/            # Indexing implementation
├── BlockAccess/          # Block-level record access
├── Buffer/               # Buffer pool management
├── Cache/                # Relation & attribute caching
├── Disk_Class/           # Disk abstraction layer
├── Frontend/             # Query input handling
├── FrontendInterface/    # Interface layer
├── Schema/               # Relation/schema management
├── define/               # Constants and identifiers
├── main.cpp              # Entry point
├── Makefile              # Build configuration
└── README.md
```

---

## Technologies Used

* **C++**
* File-based Storage System
* Data Structures
* B+ Trees
* Relational Algebra
* Buffer Management
* Indexing Techniques
* Makefile Build System

---

## NITCbase Roadmap Completion

This implementation covers all major roadmap stages:

* Disk Layer
* Buffer Layer
* Block Access Layer
* Relation Cache Management
* Attribute Cache Management
* Linear Search
* Insert Operation
* Select Operation
* Project Operation
* B+ Tree Search
* Index Management
* Join Operation

**Roadmap Completion: 100%**

---

## How to Build and Run

Clone repository:

```bash
git clone https://github.com/yeswanthkedhar007-gif/nitcbase-dbms.git
cd nitcbase-dbms
```

Compile:

```bash
make
```

Run:

```bash
./nitcbase
```

---

## Performance Insight

The project demonstrates the performance improvement of indexed search over linear search using B+ Trees.

Comparison:

* Linear Search → O(n)
* B+ Tree Search → O(log n)

This highlights the importance of indexing in database systems.

---

## Learning Outcomes

This project helped me gain practical experience in:

* Internal DBMS architecture
* Query execution flow
* File organization and storage
* Memory and buffer management
* B+ Tree indexing
* Schema management
* Relational algebra implementation
* System-level programming in C++

---

## Future Enhancements

Planned improvements:

* DELETE operation
* UPDATE operation
* ORDER BY support
* Aggregate functions (COUNT, SUM, AVG)
* GROUP BY support
* Query optimization
* Transaction management

---

## Reference

Official NITCbase Roadmap:

https://nitcbase.github.io/
