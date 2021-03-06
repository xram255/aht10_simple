### aht10_simple

 aht10 temperature and rh light weight as possible.   
 - This library tested with AHT10 and AHT15 sensors
---
 #### Available Functions

 - [x] Temperature reading
 - [x] Humidity reading 
 - [ ] Soft reset
 - [ ] Status read
---

#### Example code:

```
#include "aht10.h"

void setup() 
{
  Serial.begin(9600);
  aht.begin(); // or Wire.begin()
  delay(200);
}

void loop() 
{
  aht.trigMeasure(); // Trigger a measurement
  delay(100); // Have to wait more than 75millis until preparing the data
  aht.reqData(); // Requsts all(6) bytes 
  Serial.print(aht.tempRead()); // Print temperature value
  Serial.print(" | ");
  Serial.println(aht.rhRead()); // Print humidity value
  
  delay(10000); // If data request interval smaller than 2S internal temperature of the sensor could go high
}
```
---
#### Output -> Serial print 
    The first column shows temperature and the second columns shows humidity.
![Serial print](https://i.ibb.co/tsyZgbx/th-data.jpg)

