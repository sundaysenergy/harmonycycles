## Product Variation - Prototype

Format independent. Json or Yaml or database entity.

* [uuid] **UUID**
* [upc] **UPC**
* [ean] **EAN**
* [ean2] **EAN2**
* [mfrs_sku] **Manufacturers Part Number**
* [sku] **SKU** - Based on Make Model MSRP Color Title?
* [brand] Make/Brand
* [model] Model
* [title] Title
* [ref_type] Reference - Product Type
* [body] Body description
* [images] Image(s)
* [msrp] MSRP
* [map] MAP
* [wholesale_avg] = Average Wholesale
* [pieces_per] Pieces Per
* [physical] Weight
* [physical] Length
* [physical] Width
* [physical] Height
* [volume] Volume
* [volume_units] Volume Units
* [orm_d] ORM-D (hazardous material)
* [color] Color
* [size] Size
* [fits_for] Fits/For
* [use_type] Use Type
* [gender] Gender
* [material] Primary Material
* [year] Year
* [updated] Price Updated Timestamp

### Product Variation - Vendor Pricing

* [uuid] **UUID**
* [sku] **Vendor SKU**
* [ref_prod_proto] Reference - **Product Prototype**
* [part_id] Vendor Part Number (if different from vendor sku)
* [ref_vendor] Reference - Vendor ID
* [title] Title
* [price] Vendor Base Price
* [msrp] MSRP
* [map] MAP
* [qty] Qty on Hand (Availibility)
* [updated] Price Updated Timestamp

### Product Variation - Commerce Product (SKU Item)

A new product variation is added when product is added to the system.

* [uuid] **UUID**
* [ref_prod_proto] Reference - **Product Prototype Product Variation**
* [sku] Store Product SKU
* [serial_num] Serial Number (Automatic or Manual) Manual requires QTY 1.
* [state] State (calculated?)
* [qty] Quantity Calculation - SKU Item Adjustments
* [price] Commerce Price

#### SKU Item - Qty/Cost Adjustment

One SKU Item per product?

[ref_prod_uuid] **UUID**
[sku_item_code] **SKU Item Code** SKU of ref_prod + code
[ref_prod_proto] Reference - **Product Prototype Product Variation**
[ref_vendor] Reference - **Vendor UUID**
[received] **Received Date**
[serial_num] Serial Number (Automatic or Manual) Manual requires QTY 1.
[state] State
[cost] Total Product Cost - Calculated off SKU Item Adjustments
[location] Location (Zone, Aisle, Bay, Shelf/Bin, ID)
[qty] Quantity Calculation - SKU Item Adjustments

#### SKU Transaction (or vote)

Examples Price: rental, open box, cleaned it up, repaired it
Examples Qty: sold, lost, found

* [ref_sku_item] **uuid of sku item**
* [entity_id] **Commerce Product uuid**
* [adjust] (float) Signed float
* [adjust_calc] The calculation used to change SKU Item. (+1, -20%, X2)
* [value_type] Field to apply change to. QTY or PRICE
* [activity] Machine readable activity code (purchase, sold)
* [ref_activity_id] (line_item_id)
* [description] Description of why or what.


### Product Display - Drupal Node

Description Override
Reference - Display Prototype
Reference - Store Product(s)


______________________

## Display Prototype

Reference - Product Prototype(s)
Description



### Price Qty Breaks

* [ref_vendor_prod_uuid] Reference - **Vendor Pricing UUID**
* [qty] Break Qty
* [price] Break Price

### Account Level Breaks

* [ref_vendor_prod_uuid] Reference - **Vendor Pricing UUID**
* [level] * Pricing level
* [price] * Price

### Product Type

* UUID
* Name
* Vocabularies
?Serial Numbers (bool)
Product Statuses (list)

## First In First Out (fifo)

## Printing Tags

### Serial Number Products

If a barcode is getting printed it prints with the SKU Item Code.
