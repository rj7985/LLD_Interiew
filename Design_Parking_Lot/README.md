# Design Parking Lot — Low-Level Design

## Problem Statement

Design a **Parking Lot System** that can manage vehicles entering and exiting a parking lot, allocate suitable parking spots, generate parking tickets, and calculate parking fees.

The design should be flexible enough to support different types of vehicles, parking spots, and pricing strategies.

## Functional Requirements

* Support multiple floors in the parking lot.
* Support different types of vehicles such as:

  * Bike
  * Car
  * Truck
* Support different types of parking spots.
* Assign an appropriate parking spot when a vehicle enters.
* Generate a parking ticket for the vehicle.
* Release the parking spot when the vehicle exits.
* Calculate parking fees based on the parking duration.
* Display available parking spots.
* Support different pricing strategies.

## High-Level Design

The main entities in the system are:

ParkingLot
    |
    ├── ParkingFloor
    │      |
    │      └── ParkingSpot
    |
    ├── Vehicle
    |
    ├── Ticket
    |
    └── Payment


## Core Classes

### Vehicle

Represents a vehicle entering the parking lot.

Possible vehicle types:

Vehicle
   |
   ├── Bike
   ├── Car
   └── Truck


### ParkingSpot

Represents an individual parking spot.


ParkingSpot
   |
   ├── BikeSpot
   ├── CarSpot
   └── TruckSpot


### ParkingFloor

Manages parking spots available on a particular floor.

### ParkingLot

Acts as the main entry point and manages multiple parking floors.

### Ticket

Contains information about the parked vehicle, assigned spot, entry time, and exit time.

### Payment

Handles payment and parking fee calculation.

## Design Patterns

The following design patterns can be used to make the system flexible and maintainable.

### 1. Strategy Pattern

Used for different parking fee calculation strategies.


PricingStrategy
      |
      ├── HourlyPricingStrategy
      ├── WeekendPricingStrategy
      └── DynamicPricingStrategy


This allows the pricing algorithm to be changed without modifying the core parking logic.

### 2. Factory Pattern

Used to create different types of vehicles or parking spots based on the required type.


VehicleFactory
      |
      ├── Bike
      ├── Car
      └── Truck

### 3. Singleton Pattern

`ParkingLot` can be designed as a Singleton when the application requires a single parking lot instance.

### 4. Observer Pattern

Can be used to notify displays or monitoring systems whenever the availability of parking spots changes.

## OOP Concepts Used

* **Encapsulation** — Keep vehicle, ticket, parking spot, and payment data within their respective classes.
* **Abstraction** — Define common behavior through interfaces or abstract classes.
* **Inheritance** — Model different vehicle and parking spot types.
* **Polymorphism** — Allow different implementations of pricing and parking strategies.

## SOLID Principles

The design aims to follow:

* **Single Responsibility Principle**
* **Open/Closed Principle**
* **Liskov Substitution Principle**
* **Interface Segregation Principle**
* **Dependency Inversion Principle**

## Technologies

* Java
* Object-Oriented Programming
* SOLID Principles
* Design Patterns

## Objective

The primary objective of this project is to practice **Low-Level Design**, object-oriented modeling, SOLID principles, and design patterns by solving a real-world system design problem.
