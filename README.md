# Challenge for SALIDO Platform Engineer

This challenge is provided to help assess a candidate's development skills. There is no time limit, but we ask that you be prompt in submitting your solution.

## Submission Instructions

1. Complete the challenge according to the Challenge Instructions below.
1. Deploy your code on the internets so we can see it in action.
1. Create a GitHub repository and push your code to it.
1. Include a README in your repository to explain and document your solution.
1. Send an email to challenge-accepted@salido.com that includes links to your live solution and to your GitHub repository.

## Tech Stack Requirements

* Database: **MongoDB** (https://www.mongodb.org)
* Language: **Ruby** (https://www.ruby-lang.org)
* Framework: **Rails or similar** (http://rubyonrails.org)
* Object Document Mapper: **Mongoid** (http://mongoid.org)

## Challenge Instructions

### Objective
Create a set of data models that facilitate menu item pricing determined by a combination of 3 factors: restaurant location, order type, and time of day.

### Business Requirements
* Each restaurant brand using the SALIDO platform has multiple locations that may share the same menu items (e.g. Cafe Bangarang's FiDi and SoHo locations both sell a "Spicy Reuben").
* Restaurant locations utilize various order types (e.g. "Dine In" or "Delivery").
* For reporting purposes, each location has a concept of "day parts" (e.g. "Lunch" and "Dinner").
* When calculating a menu item's price, these factors must be taken into account:
  * Current location.
  * Current order type.
  * Current day part.
* Menu items have one or more prices defined as different "price levels" (e.g. a Spicy Reuben might have the following price levels: "Regular" => $10, "Happy Hour" => $6, "Delivery" => $11).
* To determine which of a menu item's price levels to apply:
  * If the menu item has a price specified for the price level that correlates with the current **location** + **order type** + **day part** combination, use that price level.
  * Else, if the menu item has a price specified for the price level that correlates with the current **location** + **order type** combination, use that price level.
  * Otherwise, the menu item has no price.

### To Do
1. Create data models for the following (each model should have at least a "name" attribute):
  * Brands
  * Locations
  * Menu Items
  * Day Parts
  * Order Types
  * Price Levels
  * **Any additional models necessary to support relationships between these models.**

2. Define models and relationships as follows:
  * Locations belong to a Brand.
  * Menu Items belong to a Brand.
  * Day Parts belong to a Location.
  * Order Types belong to a Brand.
  * Price Levels belong to a Brand.
  * There are price level associations defined for each Location that tie together an Order Type, a Day Part, and a Price Level.
  * Each Menu Item may have a price specified for each Price Level in the Brand.

3. Create a very basic web UI that allows a user to do the following:
  * CRUD a Brand.
  * CRUD a Location (and define the price level associations).
  * CRUD a Day Part.
  * CRUD an Order Type.
  * CRUD a Price Level.
  * CRUD a Menu Item (and specify a price for each available price level).
  * Present a form that allows a user to select Brand, Location, Day Part, Order Type, and Menu Item. Then display the resulting price.
