---
title: APItude BookingAPI v1.0
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
toc_footers: []
includes: []
search: true
highlight_theme: darkula
---

# APItude BookingAPI v1.0

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

BookingAPI covers the complete booking process; it
									allows generating lists of hotels, confirming bookings, getting
									lists of bookings, making cancellations and obtaining booking
									information.

Base URLs:

* <a href="https://api.test.hotelbeds.com/hotel-api">https://api.test.hotelbeds.com/hotel-api</a>


<a href="https://developer.hotelbeds.com/getting_started">Terms of service</a>
Email: <a href="mailto:apitude@hotelbeds.com">Hotelbeds APItude team</a> Web: <a href="https://developer.hotelbeds.com">Hotelbeds APItude team</a> 
License: <a href="http://www.apache.org/licenses/LICENSE-2.0.html">Apache 2.0</a>

# status

## status

> Code samples

```shell
# You can also use wget
curl -X GET https://api.test.hotelbeds.com/hotel-api/{version}/status

```

```http
GET https://api.test.hotelbeds.com/hotel-api/{version}/status HTTP/1.1
Host: api.test.hotelbeds.com


```

```javascript

$.ajax({
  url: 'https://api.test.hotelbeds.com/hotel-api/{version}/status',
  method: 'get',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

fetch('https://api.test.hotelbeds.com/hotel-api/{version}/status',
{
  method: 'GET'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'


result = RestClient.get 'https://api.test.hotelbeds.com/hotel-api/{version}/status',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.get('https://api.test.hotelbeds.com/hotel-api/{version}/status', params={

)

print r.json()
```

```java
URL obj = new URL("https://api.test.hotelbeds.com/hotel-api/{version}/status");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /{version}/status`

*Check API status*

Returns the status of the API

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
version|path|string|true|Specification version


#### Enumerated Values

|Parameter|Value|
|---|---|
version|1.0|
version|1.1|
version|1.2|

### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|None
500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Unexpected error|None

<aside class="success">
This operation does not require authentication
</aside>

# hotels

## availability

> Code samples

```shell
# You can also use wget
curl -X POST https://api.test.hotelbeds.com/hotel-api/{version}/hotels \
  -H 'Content-Type: application/xml' \
  -H 'Accept: application/xml'

```

```http
POST https://api.test.hotelbeds.com/hotel-api/{version}/hotels HTTP/1.1
Host: api.test.hotelbeds.com
Content-Type: application/xml
Accept: application/xml

```

```javascript
var headers = {
  'Content-Type':'application/xml',
  'Accept':'application/xml'

};

$.ajax({
  url: 'https://api.test.hotelbeds.com/hotel-api/{version}/hotels',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "echoToken": "string",
  "stay": {
    "checkIn": "2017-09-21",
    "checkOut": "2017-09-23",
    "shiftDays": 3,
    "allowOnlyShift": false
  },
  "geolocation": {
    "longitude": 2.62155,
    "latitude": 39.5554,
    "radius": 0,
    "unit": "mi",
    "secondaryLatitude": 0,
    "secondaryLongitude": 0
  },
  "destination": {
    "code": "PMI",
    "zone": 10
  },
  "filter": {
    "maxHotels": 1000,
    "maxRooms": 10,
    "minRate": 0,
    "maxRate": 1000,
    "maxRatesPerRoom": 1,
    "packaging": false,
    "paymentType": "AT_WEB",
    "hotelPackage": "BOTH",
    "minCategory": 1,
    "maxCategory": 5,
    "contract": "CG-VARIOS"
  },
  "boards": {
    "board": [
      "string"
    ],
    "included": false
  },
  "rooms": {
    "room": [
      "string"
    ],
    "included": false
  },
  "dailyRate": false,
  "sourceMarket": "ES",
  "source": {
    "channel": "B2B",
    "device": "WEB",
    "deviceInfo": "string"
  },
  "aifUse": false,
  "platform": 0,
  "language": "ENG",
  "occupancy": [
    {
      "rooms": 1,
      "adults": 2,
      "children": 0,
      "pax": [
        {
          "roomId": 1,
          "type": "AD",
          "age": 20,
          "name": "string",
          "surname": "string"
        }
      ]
    }
  ],
  "keywords": {
    "allIncluded": false,
    "keyword": [
      0
    ]
  },
  "hotels": {
    "included": false,
    "type": "HOTELBEDS",
    "hotel": [
      0
    ]
  },
  "review": [
    {
      "type": "TRIPADVISOR",
      "minRate": 0,
      "maxRate": 1,
      "minReviewCount": 1
    }
  ],
  "accommodation": [
    "HOTEL"
  ]
}';
const headers = {
  'Content-Type':'application/xml',
  'Accept':'application/xml'

};

fetch('https://api.test.hotelbeds.com/hotel-api/{version}/hotels',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/xml',
  'Accept' => 'application/xml'
}

result = RestClient.post 'https://api.test.hotelbeds.com/hotel-api/{version}/hotels',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/xml',
  'Accept': 'application/xml'
}

r = requests.post('https://api.test.hotelbeds.com/hotel-api/{version}/hotels', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://api.test.hotelbeds.com/hotel-api/{version}/hotels");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /{version}/hotels`

*Hotel availability*

This method is used to request room availability. Some filters and special features can be applied before sending an availability request. 

A flexible date search allows customers to retrieve available rates for a specified number of days prior to and post check-in.

The response generated is a list of hotels with the different room types, board types, and rates available for those hotels; but not only restricted to the dates selected.

BookingAPI prices are final. Our rates include supplements and discounts and no additional price calculations are required.

It can also return cancellation fees in the availability response, providing amounts and dates at the first step of the booking.

> Body parameter

```json
{
  "echoToken": "string",
  "stay": {
    "checkIn": "2017-09-21",
    "checkOut": "2017-09-23",
    "shiftDays": 3,
    "allowOnlyShift": false
  },
  "geolocation": {
    "longitude": 2.62155,
    "latitude": 39.5554,
    "radius": 0,
    "unit": "mi",
    "secondaryLatitude": 0,
    "secondaryLongitude": 0
  },
  "destination": {
    "code": "PMI",
    "zone": 10
  },
  "filter": {
    "maxHotels": 1000,
    "maxRooms": 10,
    "minRate": 0,
    "maxRate": 1000,
    "maxRatesPerRoom": 1,
    "packaging": false,
    "paymentType": "AT_WEB",
    "hotelPackage": "BOTH",
    "minCategory": 1,
    "maxCategory": 5,
    "contract": "CG-VARIOS"
  },
  "boards": {
    "board": [
      "string"
    ],
    "included": false
  },
  "rooms": {
    "room": [
      "string"
    ],
    "included": false
  },
  "dailyRate": false,
  "sourceMarket": "ES",
  "source": {
    "channel": "B2B",
    "device": "WEB",
    "deviceInfo": "string"
  },
  "aifUse": false,
  "platform": 0,
  "language": "ENG",
  "occupancy": [
    {
      "rooms": 1,
      "adults": 2,
      "children": 0,
      "pax": [
        {
          "roomId": 1,
          "type": "AD",
          "age": 20,
          "name": "string",
          "surname": "string"
        }
      ]
    }
  ],
  "keywords": {
    "allIncluded": false,
    "keyword": [
      0
    ]
  },
  "hotels": {
    "included": false,
    "type": "HOTELBEDS",
    "hotel": [
      0
    ]
  },
  "review": [
    {
      "type": "TRIPADVISOR",
      "minRate": 0,
      "maxRate": 1,
      "minReviewCount": 1
    }
  ],
  "accommodation": [
    "HOTEL"
  ]
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<availabilityRQ>
  <echoToken>string</echoToken>
  <stay>
    <checkIn>2017-09-21</checkIn>
    <checkOut>2017-09-23</checkOut>
    <shiftDays>3</shiftDays>
    <allowOnlyShift>false</allowOnlyShift>
  </stay>
  <geolocation>
    <longitude>2.62155</longitude>
    <latitude>39.5554</latitude>
    <radius>0</radius>
    <unit>mi</unit>
    <secondaryLatitude>0</secondaryLatitude>
    <secondaryLongitude>0</secondaryLongitude>
  </geolocation>
  <destination>
    <code>PMI</code>
    <zone>10</zone>
  </destination>
  <filter>
    <maxHotels>1000</maxHotels>
    <maxRooms>10</maxRooms>
    <minRate>0</minRate>
    <maxRate>1000</maxRate>
    <maxRatesPerRoom>1</maxRatesPerRoom>
    <packaging>false</packaging>
    <paymentType>AT_WEB</paymentType>
    <hotelPackage>BOTH</hotelPackage>
    <minCategory>1</minCategory>
    <maxCategory>5</maxCategory>
    <contract>CG-VARIOS</contract>
  </filter>
  <boards>
    <board>string</board>
    <included>false</included>
  </boards>
  <rooms>
    <room>string</room>
    <included>false</included>
  </rooms>
  <dailyRate>false</dailyRate>
  <sourceMarket>ES</sourceMarket>
  <source>
    <channel>B2B</channel>
    <device>WEB</device>
    <deviceInfo>string</deviceInfo>
  </source>
  <aifUse>false</aifUse>
  <platform>0</platform>
  <language>ENG</language>
  <occupancy>
    <rooms>1</rooms>
    <adults>2</adults>
    <children>0</children>
    <pax>
      <roomId>1</roomId>
      <type>AD</type>
      <age>20</age>
      <name>string</name>
      <surname>string</surname>
    </pax>
  </occupancy>
  <keywords>
    <allIncluded>false</allIncluded>
    <keyword>0</keyword>
  </keywords>
  <hotels>
    <included>false</included>
    <type>HOTELBEDS</type>
    <hotel>0</hotel>
  </hotels>
  <review>
    <type>TRIPADVISOR</type>
    <minRate>0</minRate>
    <maxRate>1</maxRate>
    <minReviewCount>1</minReviewCount>
  </review>
  <accommodation>HOTEL</accommodation>
</availabilityRQ>
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
version|path|string|true|Specification version
body|body|[availabilityRQ](#schemaavailabilityrq)|false|Request body
» echoToken|body|string|false|No description
» stay|body|[ApiStay](#schemaapistay)|true|No description
»» checkIn|body|string(date)|true|Check-in date
»» checkOut|body|string(date)|true|Check-out date
»» shiftDays|body|integer(int32)|false|No description
»» allowOnlyShift|body|boolean|false|No description
» geolocation|body|[ApiGeoLocation](#schemaapigeolocation)|false|No description
»» longitude|body|number|true|No description
»» latitude|body|number|true|No description
»» radius|body|number|false|No description
»» unit|body|string|false|No description
»» secondaryLatitude|body|number|false|No description
»» secondaryLongitude|body|number|false|No description
» destination|body|[ApiDestination](#schemaapidestination)|false|No description
»» code|body|string|true|No description
»» zone|body|integer(int32)|false|No description
» filter|body|[ApiFilter](#schemaapifilter)|false|No description
»» maxHotels|body|integer(int32)|false|No description
»» maxRooms|body|integer(int32)|false|No description
»» minRate|body|number|false|No description
»» maxRate|body|number|false|No description
»» maxRatesPerRoom|body|integer(int32)|false|No description
»» packaging|body|boolean|false|No description
»» paymentType|body|string|false|No description
»» hotelPackage|body|string|false|No description
»» minCategory|body|integer(int32)|false|No description
»» maxCategory|body|integer(int32)|false|No description
»» contract|body|string|false|No description
» boards|body|[ApiBoards](#schemaapiboards)|false|No description
»» included|body|boolean|true|No description
»» board|body|[string]|false|No description
» rooms|body|[ApiRooms](#schemaapirooms)|false|No description
»» included|body|boolean|true|No description
»» room|body|[string]|false|No description
» dailyRate|body|boolean|false|Display the rate day-by-day
» sourceMarket|body|string|false|No description
» source|body|[ApiSource](#schemaapisource)|false|No description
»» channel|body|string|true|No description
»» device|body|string|true|No description
»» deviceInfo|body|string|false|No description
» aifUse|body|boolean|false|No description
» platform|body|integer(int32)|false|No description
» language|body|string|false|No description
» keywords|body|[ApiKeywordsFilter](#schemaapikeywordsfilter)|false|No description
»» allIncluded|body|boolean|false|No description
»» keyword|body|[integer(int32)]|false|No description
» hotels|body|[ApiHotelsFilter](#schemaapihotelsfilter)|false|No description
»» included|body|boolean|false|No description
»» type|body|string|false|No description
»» hotel|body|[integer(int32)]|false|No description
» occupancy|body|[[ApiOccupancy](#schemaapioccupancy)]|false|No description
»» rooms|body|integer(int32)|true|No description
»» adults|body|integer(int32)|true|No description
»» children|body|integer(int32)|true|No description
»» pax|body|[[ApiPax](#schemaapipax)]|false|No description
»»» roomId|body|integer(int32)|false|No description
»»» type|body|string|true|No description
»»» age|body|integer(int32)|false|No description
»»» name|body|string|false|No description
»»» surname|body|string|false|No description
» review|body|[[ApiReviewFilter](#schemaapireviewfilter)]|false|No description
»» type|body|string|true|No description
»» minRate|body|number|false|No description
»» maxRate|body|number|false|No description
»» minReviewCount|body|integer(int32)|false|No description
» accommodation|body|[string]|false|No description


#### Enumerated Values

|Parameter|Value|
|---|---|
version|1.0|
version|1.1|
version|1.2|
»» unit|mi|
»» unit|km|
»» paymentType|AT_HOTEL|
»» paymentType|AT_WEB|
»» paymentType|BOTH|
»» hotelPackage|YES|
»» hotelPackage|NO|
»» hotelPackage|BOTH|
»» channel|B2B|
»» channel|B2C|
»» channel|META|
»» channel|NEWSLETTER|
»» device|MOBILE|
»» device|WEB|
»» device|TABLET|
»» type|HOTELBEDS|
»» type|GIATA|
»»» type|AD|
»»» type|CH|
»» type|TRIPADVISOR|
»» type|HOTELBEDS|
» accommodation|HOTEL|
» accommodation|APARTMENT|
» accommodation|RURAL|
» accommodation|HOSTEL|
» accommodation|APTHOTEL|
» accommodation|CAMPING|
» accommodation|HISTORIC|
» accommodation|PENDING|
» accommodation|RESORT|
» accommodation|HOMES|

> Example responses

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<availabilityRS>
  <echoToken>string</echoToken>
  <auditData>
    <processTime>string</processTime>
    <timestamp>string</timestamp>
    <requestHost>string</requestHost>
    <serverId>string</serverId>
    <environment>string</environment>
    <release>string</release>
    <token>string</token>
  </auditData>
  <error>
    <code>string</code>
    <message>string</message>
  </error>
  <hotels>
    <checkIn>2017-10-21</checkIn>
    <checkOut>2017-10-21</checkOut>
    <hotel>
      <checkOut>2017-10-21</checkOut>
      <checkIn>2017-10-21</checkIn>
      <code>0</code>
      <name>string</name>
      <description>string</description>
      <image>string</image>
      <categoryCode>string</categoryCode>
      <categoryName>string</categoryName>
      <destinationCode>string</destinationCode>
      <destinationName>string</destinationName>
      <zoneCode>0</zoneCode>
      <zoneName>string</zoneName>
      <latitude>string</latitude>
      <longitude>string</longitude>
      <giata>string</giata>
      <minRate>0</minRate>
      <maxRate>0</maxRate>
      <totalSellingRate>0</totalSellingRate>
      <totalNet>0</totalNet>
      <pendingAmount>0</pendingAmount>
      <currency>string</currency>
      <supplier>
        <name>string</name>
        <vatNumber>string</vatNumber>
      </supplier>
      <clientComments>string</clientComments>
      <cancellationAmount>0</cancellationAmount>
      <upselling>
        <room>
          <status>NEW</status>
          <id>0</id>
          <code>string</code>
          <name>string</name>
          <pax>
            <roomId>1</roomId>
            <type>AD</type>
            <age>20</age>
            <name>string</name>
            <surname>string</surname>
          </pax>
          <rate>
            <rateKey>string</rateKey>
            <rateClass>string</rateClass>
            <rateType>BOOKABLE</rateType>
            <net>0</net>
            <discount>0</discount>
            <discountPCT>0</discountPCT>
            <sellingRate>0</sellingRate>
            <hotelSellingRate>0</hotelSellingRate>
            <amount>0</amount>
            <hotelCurrency>string</hotelCurrency>
            <hotelMandatory>false</hotelMandatory>
            <allotment>0</allotment>
            <commission>0</commission>
            <commissionVAT>0</commissionVAT>
            <commissionPCT>0</commissionPCT>
            <cost>
              <amount>0</amount>
              <currency>string</currency>
            </cost>
            <rateCommentsId>string</rateCommentsId>
            <rateComments>string</rateComments>
            <paymentType>AT_HOTEL</paymentType>
            <packaging>false</packaging>
            <boardCode>string</boardCode>
            <boardName>string</boardName>
            <rateBreakDown>
              <rateDiscount>
                <code>string</code>
                <name>string</name>
                <amount>0</amount>
              </rateDiscount>
              <rateSupplement>
                <code>string</code>
                <name>string</name>
                <from>2017-10-21</from>
                <to>2017-10-21</to>
                <amount>0</amount>
                <nights>0</nights>
                <paxNumber>0</paxNumber>
              </rateSupplement>
            </rateBreakDown>
            <rooms>0</rooms>
            <adults>0</adults>
            <children>0</children>
            <childrenAges>string</childrenAges>
            <rateup>0</rateup>
            <comment>
              <type>string</type>
              <text>string</text>
            </comment>
            <cancellationPolicy>
              <amount>0</amount>
              <hotelAmount>0</hotelAmount>
              <hotelCurrency>string</hotelCurrency>
              <from>string</from>
            </cancellationPolicy>
            <taxes>
              <allIncluded>false</allIncluded>
              <tax>
                <included>false</included>
                <percent>0</percent>
                <amount>0</amount>
                <currency>string</currency>
                <type>TAX</type>
                <clientAmount>0</clientAmount>
                <clientCurrency>string</clientCurrency>
              </tax>
            </taxes>
            <promotion>
              <code>string</code>
              <name>string</name>
              <remark>string</remark>
            </promotion>
            <offer>
              <code>string</code>
              <name>string</name>
              <amount>0</amount>
            </offer>
            <shiftRate>
              <rateKey>string</rateKey>
              <rateClass>string</rateClass>
              <rateType>BOOKABLE</rateType>
              <net>0</net>
              <discount>0</discount>
              <discountPCT>0</discountPCT>
              <sellingRate>0</sellingRate>
              <hotelSellingRate>0</hotelSellingRate>
              <amount>0</amount>
              <hotelCurrency>string</hotelCurrency>
              <hotelMandatory>false</hotelMandatory>
              <allotment>0</allotment>
              <commission>0</commission>
              <commissionVAT>0</commissionVAT>
              <commissionPCT>0</commissionPCT>
              <cost>
                <amount>0</amount>
                <currency>string</currency>
              </cost>
              <checkIn>2017-10-21</checkIn>
              <checkOut>2017-10-21</checkOut>
            </shiftRate>
            <dailyRate>
              <offset>0</offset>
              <dailyNet>0</dailyNet>
              <dailySellingRate>0</dailySellingRate>
            </dailyRate>
          </rate>
        </room>
      </upselling>
      <keyword>
        <code>0</code>
        <rating>0</rating>
      </keyword>
      <review>
        <rate>0</rate>
        <reviewCount>0</reviewCount>
        <type>string</type>
      </review>
      <room>
        <status>NEW</status>
        <id>0</id>
        <code>string</code>
        <name>string</name>
        <pax>
          <roomId>1</roomId>
          <type>AD</type>
          <age>20</age>
          <name>string</name>
          <surname>string</surname>
        </pax>
        <rate>
          <rateKey>string</rateKey>
          <rateClass>string</rateClass>
          <rateType>BOOKABLE</rateType>
          <net>0</net>
          <discount>0</discount>
          <discountPCT>0</discountPCT>
          <sellingRate>0</sellingRate>
          <hotelSellingRate>0</hotelSellingRate>
          <amount>0</amount>
          <hotelCurrency>string</hotelCurrency>
          <hotelMandatory>false</hotelMandatory>
          <allotment>0</allotment>
          <commission>0</commission>
          <commissionVAT>0</commissionVAT>
          <commissionPCT>0</commissionPCT>
          <cost>
            <amount>0</amount>
            <currency>string</currency>
          </cost>
          <rateCommentsId>string</rateCommentsId>
          <rateComments>string</rateComments>
          <paymentType>AT_HOTEL</paymentType>
          <packaging>false</packaging>
          <boardCode>string</boardCode>
          <boardName>string</boardName>
          <rateBreakDown>
            <rateDiscount>
              <code>string</code>
              <name>string</name>
              <amount>0</amount>
            </rateDiscount>
            <rateSupplement>
              <code>string</code>
              <name>string</name>
              <from>2017-10-21</from>
              <to>2017-10-21</to>
              <amount>0</amount>
              <nights>0</nights>
              <paxNumber>0</paxNumber>
            </rateSupplement>
          </rateBreakDown>
          <rooms>0</rooms>
          <adults>0</adults>
          <children>0</children>
          <childrenAges>string</childrenAges>
          <rateup>0</rateup>
          <comment>
            <type>string</type>
            <text>string</text>
          </comment>
          <cancellationPolicy>
            <amount>0</amount>
            <hotelAmount>0</hotelAmount>
            <hotelCurrency>string</hotelCurrency>
            <from>string</from>
          </cancellationPolicy>
          <taxes>
            <allIncluded>false</allIncluded>
            <tax>
              <included>false</included>
              <percent>0</percent>
              <amount>0</amount>
              <currency>string</currency>
              <type>TAX</type>
              <clientAmount>0</clientAmount>
              <clientCurrency>string</clientCurrency>
            </tax>
          </taxes>
          <promotion>
            <code>string</code>
            <name>string</name>
            <remark>string</remark>
          </promotion>
          <offer>
            <code>string</code>
            <name>string</name>
            <amount>0</amount>
          </offer>
          <shiftRate>
            <rateKey>string</rateKey>
            <rateClass>string</rateClass>
            <rateType>BOOKABLE</rateType>
            <net>0</net>
            <discount>0</discount>
            <discountPCT>0</discountPCT>
            <sellingRate>0</sellingRate>
            <hotelSellingRate>0</hotelSellingRate>
            <amount>0</amount>
            <hotelCurrency>string</hotelCurrency>
            <hotelMandatory>false</hotelMandatory>
            <allotment>0</allotment>
            <commission>0</commission>
            <commissionVAT>0</commissionVAT>
            <commissionPCT>0</commissionPCT>
            <cost>
              <amount>0</amount>
              <currency>string</currency>
            </cost>
            <checkIn>2017-10-21</checkIn>
            <checkOut>2017-10-21</checkOut>
          </shiftRate>
          <dailyRate>
            <offset>0</offset>
            <dailyNet>0</dailyNet>
            <dailySellingRate>0</dailySellingRate>
          </dailyRate>
        </rate>
      </room>
      <creditCard>
        <code>string</code>
        <name>string</name>
        <paymentType>AT_HOTEL</paymentType>
      </creditCard>
    </hotel>
    <total>0</total>
  </hotels>
  <source>
    <channel>B2B</channel>
    <device>WEB</device>
    <deviceInfo>string</deviceInfo>
  </source>
</availabilityRS>
```
```json
{
  "echoToken": "string",
  "auditData": {
    "processTime": "string",
    "timestamp": "string",
    "requestHost": "string",
    "serverId": "string",
    "environment": "string",
    "release": "string",
    "token": "string"
  },
  "error": {
    "code": "string",
    "message": "string"
  },
  "hotels": {
    "checkIn": "2017-10-21",
    "checkOut": "2017-10-21",
    "hotel": [
      {
        "checkOut": "2017-10-21",
        "checkIn": "2017-10-21",
        "code": 0,
        "name": "string",
        "description": "string",
        "image": "string",
        "categoryCode": "string",
        "categoryName": "string",
        "destinationCode": "string",
        "destinationName": "string",
        "zoneCode": 0,
        "zoneName": "string",
        "latitude": "string",
        "longitude": "string",
        "giata": "string",
        "minRate": 0,
        "maxRate": 0,
        "totalSellingRate": 0,
        "totalNet": 0,
        "pendingAmount": 0,
        "currency": "string",
        "supplier": {
          "name": "string",
          "vatNumber": "string"
        },
        "clientComments": "string",
        "cancellationAmount": 0,
        "upselling": {
          "room": [
            {
              "status": "NEW",
              "id": 0,
              "code": "string",
              "name": "string",
              "pax": [
                {
                  "roomId": 1,
                  "type": "AD",
                  "age": 20,
                  "name": "string",
                  "surname": "string"
                }
              ],
              "rate": [
                {
                  "rateKey": "string",
                  "rateClass": "string",
                  "rateType": "BOOKABLE",
                  "net": 0,
                  "discount": 0,
                  "discountPCT": 0,
                  "sellingRate": 0,
                  "hotelSellingRate": 0,
                  "amount": 0,
                  "hotelCurrency": "string",
                  "hotelMandatory": false,
                  "allotment": 0,
                  "commission": 0,
                  "commissionVAT": 0,
                  "commissionPCT": 0,
                  "cost": {
                    "amount": 0,
                    "currency": "string"
                  },
                  "rateCommentsId": "string",
                  "rateComments": "string",
                  "paymentType": "AT_HOTEL",
                  "packaging": false,
                  "boardCode": "string",
                  "boardName": "string",
                  "rateBreakDown": {
                    "rateDiscount": [
                      {
                        "code": "string",
                        "name": "string",
                        "amount": 0
                      }
                    ],
                    "rateSupplement": [
                      {
                        "code": "string",
                        "name": "string",
                        "from": "2017-10-21",
                        "to": "2017-10-21",
                        "amount": 0,
                        "nights": 0,
                        "paxNumber": 0
                      }
                    ]
                  },
                  "rooms": 0,
                  "adults": 0,
                  "children": 0,
                  "childrenAges": "string",
                  "rateup": 0,
                  "comment": [
                    {
                      "type": "string",
                      "text": "string"
                    }
                  ],
                  "cancellationPolicy": [
                    {
                      "amount": 0,
                      "hotelAmount": 0,
                      "hotelCurrency": "string",
                      "from": "string"
                    }
                  ],
                  "taxes": {
                    "allIncluded": false,
                    "tax": [
                      {
                        "included": false,
                        "percent": 0,
                        "amount": 0,
                        "currency": "string",
                        "type": "TAX",
                        "clientAmount": 0,
                        "clientCurrency": "string"
                      }
                    ]
                  },
                  "promotion": [
                    {
                      "code": "string",
                      "name": "string",
                      "remark": "string"
                    }
                  ],
                  "offer": [
                    {
                      "code": "string",
                      "name": "string",
                      "amount": 0
                    }
                  ],
                  "shiftRate": [
                    {
                      "rateKey": "string",
                      "rateClass": "string",
                      "rateType": "BOOKABLE",
                      "net": 0,
                      "discount": 0,
                      "discountPCT": 0,
                      "sellingRate": 0,
                      "hotelSellingRate": 0,
                      "amount": 0,
                      "hotelCurrency": "string",
                      "hotelMandatory": false,
                      "allotment": 0,
                      "commission": 0,
                      "commissionVAT": 0,
                      "commissionPCT": 0,
                      "cost": {
                        "amount": 0,
                        "currency": "string"
                      },
                      "checkIn": "2017-10-21",
                      "checkOut": "2017-10-21"
                    }
                  ],
                  "dailyRate": [
                    {
                      "offset": 0,
                      "dailyNet": 0,
                      "dailySellingRate": 0
                    }
                  ]
                }
              ]
            }
          ]
        },
        "keyword": [
          {
            "code": 0,
            "rating": 0
          }
        ],
        "review": [
          {
            "rate": 0,
            "reviewCount": 0,
            "type": "string"
          }
        ],
        "room": [
          {
            "status": "NEW",
            "id": 0,
            "code": "string",
            "name": "string",
            "pax": [
              {
                "roomId": 1,
                "type": "AD",
                "age": 20,
                "name": "string",
                "surname": "string"
              }
            ],
            "rate": [
              {
                "rateKey": "string",
                "rateClass": "string",
                "rateType": "BOOKABLE",
                "net": 0,
                "discount": 0,
                "discountPCT": 0,
                "sellingRate": 0,
                "hotelSellingRate": 0,
                "amount": 0,
                "hotelCurrency": "string",
                "hotelMandatory": false,
                "allotment": 0,
                "commission": 0,
                "commissionVAT": 0,
                "commissionPCT": 0,
                "cost": {
                  "amount": 0,
                  "currency": "string"
                },
                "rateCommentsId": "string",
                "rateComments": "string",
                "paymentType": "AT_HOTEL",
                "packaging": false,
                "boardCode": "string",
                "boardName": "string",
                "rateBreakDown": {
                  "rateDiscount": [
                    {
                      "code": "string",
                      "name": "string",
                      "amount": 0
                    }
                  ],
                  "rateSupplement": [
                    {
                      "code": "string",
                      "name": "string",
                      "from": "2017-10-21",
                      "to": "2017-10-21",
                      "amount": 0,
                      "nights": 0,
                      "paxNumber": 0
                    }
                  ]
                },
                "rooms": 0,
                "adults": 0,
                "children": 0,
                "childrenAges": "string",
                "rateup": 0,
                "comment": [
                  {
                    "type": "string",
                    "text": "string"
                  }
                ],
                "cancellationPolicy": [
                  {
                    "amount": 0,
                    "hotelAmount": 0,
                    "hotelCurrency": "string",
                    "from": "string"
                  }
                ],
                "taxes": {
                  "allIncluded": false,
                  "tax": [
                    {
                      "included": false,
                      "percent": 0,
                      "amount": 0,
                      "currency": "string",
                      "type": "TAX",
                      "clientAmount": 0,
                      "clientCurrency": "string"
                    }
                  ]
                },
                "promotion": [
                  {
                    "code": "string",
                    "name": "string",
                    "remark": "string"
                  }
                ],
                "offer": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "shiftRate": [
                  {
                    "rateKey": "string",
                    "rateClass": "string",
                    "rateType": "BOOKABLE",
                    "net": 0,
                    "discount": 0,
                    "discountPCT": 0,
                    "sellingRate": 0,
                    "hotelSellingRate": 0,
                    "amount": 0,
                    "hotelCurrency": "string",
                    "hotelMandatory": false,
                    "allotment": 0,
                    "commission": 0,
                    "commissionVAT": 0,
                    "commissionPCT": 0,
                    "cost": {
                      "amount": 0,
                      "currency": "string"
                    },
                    "checkIn": "2017-10-21",
                    "checkOut": "2017-10-21"
                  }
                ],
                "dailyRate": [
                  {
                    "offset": 0,
                    "dailyNet": 0,
                    "dailySellingRate": 0
                  }
                ]
              }
            ]
          }
        ],
        "creditCard": [
          {
            "code": "string",
            "name": "string",
            "paymentType": "AT_HOTEL"
          }
        ]
      }
    ],
    "total": 0
  },
  "source": {
    "channel": "B2B",
    "device": "WEB",
    "deviceInfo": "string"
  }
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[availabilityRS](#schemaavailabilityrs)

<aside class="success">
This operation does not require authentication
</aside>

# checkrates

## checkRate2

> Code samples

```shell
# You can also use wget
curl -X POST https://api.test.hotelbeds.com/hotel-api/{version}/checkrates \
  -H 'Content-Type: application/xml' \
  -H 'Accept: application/xml'

```

```http
POST https://api.test.hotelbeds.com/hotel-api/{version}/checkrates HTTP/1.1
Host: api.test.hotelbeds.com
Content-Type: application/xml
Accept: application/xml

```

```javascript
var headers = {
  'Content-Type':'application/xml',
  'Accept':'application/xml'

};

$.ajax({
  url: 'https://api.test.hotelbeds.com/hotel-api/{version}/checkrates',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "echoToken": "string",
  "upselling": false,
  "language": "ENG",
  "room": [
    {
      "rateKey": "string",
      "pax": [
        {
          "roomId": 1,
          "type": "AD",
          "age": 20,
          "name": "string",
          "surname": "string"
        }
      ]
    }
  ]
}';
const headers = {
  'Content-Type':'application/xml',
  'Accept':'application/xml'

};

fetch('https://api.test.hotelbeds.com/hotel-api/{version}/checkrates',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/xml',
  'Accept' => 'application/xml'
}

result = RestClient.post 'https://api.test.hotelbeds.com/hotel-api/{version}/checkrates',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/xml',
  'Accept': 'application/xml'
}

r = requests.post('https://api.test.hotelbeds.com/hotel-api/{version}/checkrates', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://api.test.hotelbeds.com/hotel-api/{version}/checkrates");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /{version}/checkrates`

*Check Availability Rates*

The checkrates method can complement the booking process, as it returns additional information to the availability request. However, when the rateType value is "RECHECK", the checkrates method is mandatory.

The rateType value "RECHECK" is returned for rates that do not have real-time availability. This is, that come from accommodation partners that update their products in our system periodically, with varying frequency depending on the supplier itself, the destination, hotels, etc.

The checkrates method response contains the same information provided in the availability response, but returns information only for a specific hotel and rate. The purpose of this method is double check availability and prices for any particular hotel/rate.

The prices obtained via this method are always up-to-date; along with some other information: rate breakdown, rate comments and upselling options.

> Body parameter

```json
{
  "echoToken": "string",
  "upselling": false,
  "language": "ENG",
  "room": [
    {
      "rateKey": "string",
      "pax": [
        {
          "roomId": 1,
          "type": "AD",
          "age": 20,
          "name": "string",
          "surname": "string"
        }
      ]
    }
  ]
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<checkRateRQ>
  <echoToken>string</echoToken>
  <upselling>false</upselling>
  <language>ENG</language>
  <room>
    <rateKey>string</rateKey>
    <pax>
      <roomId>1</roomId>
      <type>AD</type>
      <age>20</age>
      <name>string</name>
      <surname>string</surname>
    </pax>
  </room>
</checkRateRQ>
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
version|path|string|true|Specification version
body|body|[checkRateRQ](#schemacheckraterq)|false|Request body
» echoToken|body|string|false|No description
» upselling|body|boolean|false|No description
» language|body|string|false|No description
» room|body|[[ApiBookingRoom](#schemaapibookingroom)]|false|No description
»» rateKey|body|string|true|No description
»» pax|body|[[ApiPax](#schemaapipax)]|false|No description
»»» roomId|body|integer(int32)|false|No description
»»» type|body|string|true|No description
»»» age|body|integer(int32)|false|No description
»»» name|body|string|false|No description
»»» surname|body|string|false|No description


#### Enumerated Values

|Parameter|Value|
|---|---|
version|1.0|
version|1.1|
version|1.2|
»»» type|AD|
»»» type|CH|

> Example responses

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<checkRateRS>
  <echoToken>string</echoToken>
  <auditData>
    <processTime>string</processTime>
    <timestamp>string</timestamp>
    <requestHost>string</requestHost>
    <serverId>string</serverId>
    <environment>string</environment>
    <release>string</release>
    <token>string</token>
  </auditData>
  <error>
    <code>string</code>
    <message>string</message>
  </error>
  <hotel>
    <checkOut>2017-10-21</checkOut>
    <checkIn>2017-10-21</checkIn>
    <code>0</code>
    <name>string</name>
    <description>string</description>
    <image>string</image>
    <categoryCode>string</categoryCode>
    <categoryName>string</categoryName>
    <destinationCode>string</destinationCode>
    <destinationName>string</destinationName>
    <zoneCode>0</zoneCode>
    <zoneName>string</zoneName>
    <latitude>string</latitude>
    <longitude>string</longitude>
    <giata>string</giata>
    <minRate>0</minRate>
    <maxRate>0</maxRate>
    <totalSellingRate>0</totalSellingRate>
    <totalNet>0</totalNet>
    <pendingAmount>0</pendingAmount>
    <currency>string</currency>
    <supplier>
      <name>string</name>
      <vatNumber>string</vatNumber>
    </supplier>
    <clientComments>string</clientComments>
    <cancellationAmount>0</cancellationAmount>
    <upselling>
      <room>
        <status>NEW</status>
        <id>0</id>
        <code>string</code>
        <name>string</name>
        <pax>
          <roomId>1</roomId>
          <type>AD</type>
          <age>20</age>
          <name>string</name>
          <surname>string</surname>
        </pax>
        <rate>
          <rateKey>string</rateKey>
          <rateClass>string</rateClass>
          <rateType>BOOKABLE</rateType>
          <net>0</net>
          <discount>0</discount>
          <discountPCT>0</discountPCT>
          <sellingRate>0</sellingRate>
          <hotelSellingRate>0</hotelSellingRate>
          <amount>0</amount>
          <hotelCurrency>string</hotelCurrency>
          <hotelMandatory>false</hotelMandatory>
          <allotment>0</allotment>
          <commission>0</commission>
          <commissionVAT>0</commissionVAT>
          <commissionPCT>0</commissionPCT>
          <cost>
            <amount>0</amount>
            <currency>string</currency>
          </cost>
          <rateCommentsId>string</rateCommentsId>
          <rateComments>string</rateComments>
          <paymentType>AT_HOTEL</paymentType>
          <packaging>false</packaging>
          <boardCode>string</boardCode>
          <boardName>string</boardName>
          <rateBreakDown>
            <rateDiscount>
              <code>string</code>
              <name>string</name>
              <amount>0</amount>
            </rateDiscount>
            <rateSupplement>
              <code>string</code>
              <name>string</name>
              <from>2017-10-21</from>
              <to>2017-10-21</to>
              <amount>0</amount>
              <nights>0</nights>
              <paxNumber>0</paxNumber>
            </rateSupplement>
          </rateBreakDown>
          <rooms>0</rooms>
          <adults>0</adults>
          <children>0</children>
          <childrenAges>string</childrenAges>
          <rateup>0</rateup>
          <comment>
            <type>string</type>
            <text>string</text>
          </comment>
          <cancellationPolicy>
            <amount>0</amount>
            <hotelAmount>0</hotelAmount>
            <hotelCurrency>string</hotelCurrency>
            <from>string</from>
          </cancellationPolicy>
          <taxes>
            <allIncluded>false</allIncluded>
            <tax>
              <included>false</included>
              <percent>0</percent>
              <amount>0</amount>
              <currency>string</currency>
              <type>TAX</type>
              <clientAmount>0</clientAmount>
              <clientCurrency>string</clientCurrency>
            </tax>
          </taxes>
          <promotion>
            <code>string</code>
            <name>string</name>
            <remark>string</remark>
          </promotion>
          <offer>
            <code>string</code>
            <name>string</name>
            <amount>0</amount>
          </offer>
          <shiftRate>
            <rateKey>string</rateKey>
            <rateClass>string</rateClass>
            <rateType>BOOKABLE</rateType>
            <net>0</net>
            <discount>0</discount>
            <discountPCT>0</discountPCT>
            <sellingRate>0</sellingRate>
            <hotelSellingRate>0</hotelSellingRate>
            <amount>0</amount>
            <hotelCurrency>string</hotelCurrency>
            <hotelMandatory>false</hotelMandatory>
            <allotment>0</allotment>
            <commission>0</commission>
            <commissionVAT>0</commissionVAT>
            <commissionPCT>0</commissionPCT>
            <cost>
              <amount>0</amount>
              <currency>string</currency>
            </cost>
            <checkIn>2017-10-21</checkIn>
            <checkOut>2017-10-21</checkOut>
          </shiftRate>
          <dailyRate>
            <offset>0</offset>
            <dailyNet>0</dailyNet>
            <dailySellingRate>0</dailySellingRate>
          </dailyRate>
        </rate>
      </room>
    </upselling>
    <keyword>
      <code>0</code>
      <rating>0</rating>
    </keyword>
    <review>
      <rate>0</rate>
      <reviewCount>0</reviewCount>
      <type>string</type>
    </review>
    <room>
      <status>NEW</status>
      <id>0</id>
      <code>string</code>
      <name>string</name>
      <pax>
        <roomId>1</roomId>
        <type>AD</type>
        <age>20</age>
        <name>string</name>
        <surname>string</surname>
      </pax>
      <rate>
        <rateKey>string</rateKey>
        <rateClass>string</rateClass>
        <rateType>BOOKABLE</rateType>
        <net>0</net>
        <discount>0</discount>
        <discountPCT>0</discountPCT>
        <sellingRate>0</sellingRate>
        <hotelSellingRate>0</hotelSellingRate>
        <amount>0</amount>
        <hotelCurrency>string</hotelCurrency>
        <hotelMandatory>false</hotelMandatory>
        <allotment>0</allotment>
        <commission>0</commission>
        <commissionVAT>0</commissionVAT>
        <commissionPCT>0</commissionPCT>
        <cost>
          <amount>0</amount>
          <currency>string</currency>
        </cost>
        <rateCommentsId>string</rateCommentsId>
        <rateComments>string</rateComments>
        <paymentType>AT_HOTEL</paymentType>
        <packaging>false</packaging>
        <boardCode>string</boardCode>
        <boardName>string</boardName>
        <rateBreakDown>
          <rateDiscount>
            <code>string</code>
            <name>string</name>
            <amount>0</amount>
          </rateDiscount>
          <rateSupplement>
            <code>string</code>
            <name>string</name>
            <from>2017-10-21</from>
            <to>2017-10-21</to>
            <amount>0</amount>
            <nights>0</nights>
            <paxNumber>0</paxNumber>
          </rateSupplement>
        </rateBreakDown>
        <rooms>0</rooms>
        <adults>0</adults>
        <children>0</children>
        <childrenAges>string</childrenAges>
        <rateup>0</rateup>
        <comment>
          <type>string</type>
          <text>string</text>
        </comment>
        <cancellationPolicy>
          <amount>0</amount>
          <hotelAmount>0</hotelAmount>
          <hotelCurrency>string</hotelCurrency>
          <from>string</from>
        </cancellationPolicy>
        <taxes>
          <allIncluded>false</allIncluded>
          <tax>
            <included>false</included>
            <percent>0</percent>
            <amount>0</amount>
            <currency>string</currency>
            <type>TAX</type>
            <clientAmount>0</clientAmount>
            <clientCurrency>string</clientCurrency>
          </tax>
        </taxes>
        <promotion>
          <code>string</code>
          <name>string</name>
          <remark>string</remark>
        </promotion>
        <offer>
          <code>string</code>
          <name>string</name>
          <amount>0</amount>
        </offer>
        <shiftRate>
          <rateKey>string</rateKey>
          <rateClass>string</rateClass>
          <rateType>BOOKABLE</rateType>
          <net>0</net>
          <discount>0</discount>
          <discountPCT>0</discountPCT>
          <sellingRate>0</sellingRate>
          <hotelSellingRate>0</hotelSellingRate>
          <amount>0</amount>
          <hotelCurrency>string</hotelCurrency>
          <hotelMandatory>false</hotelMandatory>
          <allotment>0</allotment>
          <commission>0</commission>
          <commissionVAT>0</commissionVAT>
          <commissionPCT>0</commissionPCT>
          <cost>
            <amount>0</amount>
            <currency>string</currency>
          </cost>
          <checkIn>2017-10-21</checkIn>
          <checkOut>2017-10-21</checkOut>
        </shiftRate>
        <dailyRate>
          <offset>0</offset>
          <dailyNet>0</dailyNet>
          <dailySellingRate>0</dailySellingRate>
        </dailyRate>
      </rate>
    </room>
    <creditCard>
      <code>string</code>
      <name>string</name>
      <paymentType>AT_HOTEL</paymentType>
    </creditCard>
  </hotel>
  <source>
    <channel>B2B</channel>
    <device>WEB</device>
    <deviceInfo>string</deviceInfo>
  </source>
</checkRateRS>
```
```json
{
  "echoToken": "string",
  "auditData": {
    "processTime": "string",
    "timestamp": "string",
    "requestHost": "string",
    "serverId": "string",
    "environment": "string",
    "release": "string",
    "token": "string"
  },
  "error": {
    "code": "string",
    "message": "string"
  },
  "hotel": {
    "checkOut": "2017-10-21",
    "checkIn": "2017-10-21",
    "code": 0,
    "name": "string",
    "description": "string",
    "image": "string",
    "categoryCode": "string",
    "categoryName": "string",
    "destinationCode": "string",
    "destinationName": "string",
    "zoneCode": 0,
    "zoneName": "string",
    "latitude": "string",
    "longitude": "string",
    "giata": "string",
    "minRate": 0,
    "maxRate": 0,
    "totalSellingRate": 0,
    "totalNet": 0,
    "pendingAmount": 0,
    "currency": "string",
    "supplier": {
      "name": "string",
      "vatNumber": "string"
    },
    "clientComments": "string",
    "cancellationAmount": 0,
    "upselling": {
      "room": [
        {
          "status": "NEW",
          "id": 0,
          "code": "string",
          "name": "string",
          "pax": [
            {
              "roomId": 1,
              "type": "AD",
              "age": 20,
              "name": "string",
              "surname": "string"
            }
          ],
          "rate": [
            {
              "rateKey": "string",
              "rateClass": "string",
              "rateType": "BOOKABLE",
              "net": 0,
              "discount": 0,
              "discountPCT": 0,
              "sellingRate": 0,
              "hotelSellingRate": 0,
              "amount": 0,
              "hotelCurrency": "string",
              "hotelMandatory": false,
              "allotment": 0,
              "commission": 0,
              "commissionVAT": 0,
              "commissionPCT": 0,
              "cost": {
                "amount": 0,
                "currency": "string"
              },
              "rateCommentsId": "string",
              "rateComments": "string",
              "paymentType": "AT_HOTEL",
              "packaging": false,
              "boardCode": "string",
              "boardName": "string",
              "rateBreakDown": {
                "rateDiscount": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "rateSupplement": [
                  {
                    "code": "string",
                    "name": "string",
                    "from": "2017-10-21",
                    "to": "2017-10-21",
                    "amount": 0,
                    "nights": 0,
                    "paxNumber": 0
                  }
                ]
              },
              "rooms": 0,
              "adults": 0,
              "children": 0,
              "childrenAges": "string",
              "rateup": 0,
              "comment": [
                {
                  "type": "string",
                  "text": "string"
                }
              ],
              "cancellationPolicy": [
                {
                  "amount": 0,
                  "hotelAmount": 0,
                  "hotelCurrency": "string",
                  "from": "string"
                }
              ],
              "taxes": {
                "allIncluded": false,
                "tax": [
                  {
                    "included": false,
                    "percent": 0,
                    "amount": 0,
                    "currency": "string",
                    "type": "TAX",
                    "clientAmount": 0,
                    "clientCurrency": "string"
                  }
                ]
              },
              "promotion": [
                {
                  "code": "string",
                  "name": "string",
                  "remark": "string"
                }
              ],
              "offer": [
                {
                  "code": "string",
                  "name": "string",
                  "amount": 0
                }
              ],
              "shiftRate": [
                {
                  "rateKey": "string",
                  "rateClass": "string",
                  "rateType": "BOOKABLE",
                  "net": 0,
                  "discount": 0,
                  "discountPCT": 0,
                  "sellingRate": 0,
                  "hotelSellingRate": 0,
                  "amount": 0,
                  "hotelCurrency": "string",
                  "hotelMandatory": false,
                  "allotment": 0,
                  "commission": 0,
                  "commissionVAT": 0,
                  "commissionPCT": 0,
                  "cost": {
                    "amount": 0,
                    "currency": "string"
                  },
                  "checkIn": "2017-10-21",
                  "checkOut": "2017-10-21"
                }
              ],
              "dailyRate": [
                {
                  "offset": 0,
                  "dailyNet": 0,
                  "dailySellingRate": 0
                }
              ]
            }
          ]
        }
      ]
    },
    "keyword": [
      {
        "code": 0,
        "rating": 0
      }
    ],
    "review": [
      {
        "rate": 0,
        "reviewCount": 0,
        "type": "string"
      }
    ],
    "room": [
      {
        "status": "NEW",
        "id": 0,
        "code": "string",
        "name": "string",
        "pax": [
          {
            "roomId": 1,
            "type": "AD",
            "age": 20,
            "name": "string",
            "surname": "string"
          }
        ],
        "rate": [
          {
            "rateKey": "string",
            "rateClass": "string",
            "rateType": "BOOKABLE",
            "net": 0,
            "discount": 0,
            "discountPCT": 0,
            "sellingRate": 0,
            "hotelSellingRate": 0,
            "amount": 0,
            "hotelCurrency": "string",
            "hotelMandatory": false,
            "allotment": 0,
            "commission": 0,
            "commissionVAT": 0,
            "commissionPCT": 0,
            "cost": {
              "amount": 0,
              "currency": "string"
            },
            "rateCommentsId": "string",
            "rateComments": "string",
            "paymentType": "AT_HOTEL",
            "packaging": false,
            "boardCode": "string",
            "boardName": "string",
            "rateBreakDown": {
              "rateDiscount": [
                {
                  "code": "string",
                  "name": "string",
                  "amount": 0
                }
              ],
              "rateSupplement": [
                {
                  "code": "string",
                  "name": "string",
                  "from": "2017-10-21",
                  "to": "2017-10-21",
                  "amount": 0,
                  "nights": 0,
                  "paxNumber": 0
                }
              ]
            },
            "rooms": 0,
            "adults": 0,
            "children": 0,
            "childrenAges": "string",
            "rateup": 0,
            "comment": [
              {
                "type": "string",
                "text": "string"
              }
            ],
            "cancellationPolicy": [
              {
                "amount": 0,
                "hotelAmount": 0,
                "hotelCurrency": "string",
                "from": "string"
              }
            ],
            "taxes": {
              "allIncluded": false,
              "tax": [
                {
                  "included": false,
                  "percent": 0,
                  "amount": 0,
                  "currency": "string",
                  "type": "TAX",
                  "clientAmount": 0,
                  "clientCurrency": "string"
                }
              ]
            },
            "promotion": [
              {
                "code": "string",
                "name": "string",
                "remark": "string"
              }
            ],
            "offer": [
              {
                "code": "string",
                "name": "string",
                "amount": 0
              }
            ],
            "shiftRate": [
              {
                "rateKey": "string",
                "rateClass": "string",
                "rateType": "BOOKABLE",
                "net": 0,
                "discount": 0,
                "discountPCT": 0,
                "sellingRate": 0,
                "hotelSellingRate": 0,
                "amount": 0,
                "hotelCurrency": "string",
                "hotelMandatory": false,
                "allotment": 0,
                "commission": 0,
                "commissionVAT": 0,
                "commissionPCT": 0,
                "cost": {
                  "amount": 0,
                  "currency": "string"
                },
                "checkIn": "2017-10-21",
                "checkOut": "2017-10-21"
              }
            ],
            "dailyRate": [
              {
                "offset": 0,
                "dailyNet": 0,
                "dailySellingRate": 0
              }
            ]
          }
        ]
      }
    ],
    "creditCard": [
      {
        "code": "string",
        "name": "string",
        "paymentType": "AT_HOTEL"
      }
    ]
  },
  "source": {
    "channel": "B2B",
    "device": "WEB",
    "deviceInfo": "string"
  }
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[checkRateRS](#schemacheckraters)

<aside class="success">
This operation does not require authentication
</aside>

# bookings

## booking

> Code samples

```shell
# You can also use wget
curl -X POST https://api.test.hotelbeds.com/hotel-api/{version}/bookings \
  -H 'Content-Type: application/xml' \
  -H 'Accept: application/xml'

```

```http
POST https://api.test.hotelbeds.com/hotel-api/{version}/bookings HTTP/1.1
Host: api.test.hotelbeds.com
Content-Type: application/xml
Accept: application/xml

```

```javascript
var headers = {
  'Content-Type':'application/xml',
  'Accept':'application/xml'

};

$.ajax({
  url: 'https://api.test.hotelbeds.com/hotel-api/{version}/bookings',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "echoToken": "string",
  "holder": {
    "name": "string",
    "surname": "string"
  },
  "paymentData": {
    "paymentCard": {
      "cardType": "string",
      "cardNumber": "string",
      "cardHolderName": "string",
      "expiryDate": "string",
      "cardCVC": "string"
    },
    "contactData": {
      "email": "string",
      "phoneNumber": "string"
    },
    "billingAddress": {
      "address1": "string",
      "address2": "string",
      "city": "string",
      "state": "string",
      "postalCode": "string",
      "countryCode": "string"
    },
    "webPartner": 0,
    "device": {
      "id": "string",
      "ip": "string"
    }
  },
  "clientReference": "string",
  "remark": "string",
  "voucher": {
    "language": "string",
    "email": {
      "to": "string",
      "from": "string",
      "title": "string",
      "body": "string"
    }
  },
  "language": "ENG",
  "room": [
    {
      "rateKey": "string",
      "pax": [
        {
          "roomId": 1,
          "type": "AD",
          "age": 20,
          "name": "string",
          "surname": "string"
        }
      ]
    }
  ]
}';
const headers = {
  'Content-Type':'application/xml',
  'Accept':'application/xml'

};

fetch('https://api.test.hotelbeds.com/hotel-api/{version}/bookings',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/xml',
  'Accept' => 'application/xml'
}

result = RestClient.post 'https://api.test.hotelbeds.com/hotel-api/{version}/bookings',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/xml',
  'Accept': 'application/xml'
}

r = requests.post('https://api.test.hotelbeds.com/hotel-api/{version}/bookings', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://api.test.hotelbeds.com/hotel-api/{version}/bookings");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /{version}/bookings`

*Booking confirm*

Description.....

> Body parameter

```json
{
  "echoToken": "string",
  "holder": {
    "name": "string",
    "surname": "string"
  },
  "paymentData": {
    "paymentCard": {
      "cardType": "string",
      "cardNumber": "string",
      "cardHolderName": "string",
      "expiryDate": "string",
      "cardCVC": "string"
    },
    "contactData": {
      "email": "string",
      "phoneNumber": "string"
    },
    "billingAddress": {
      "address1": "string",
      "address2": "string",
      "city": "string",
      "state": "string",
      "postalCode": "string",
      "countryCode": "string"
    },
    "webPartner": 0,
    "device": {
      "id": "string",
      "ip": "string"
    }
  },
  "clientReference": "string",
  "remark": "string",
  "voucher": {
    "language": "string",
    "email": {
      "to": "string",
      "from": "string",
      "title": "string",
      "body": "string"
    }
  },
  "language": "ENG",
  "room": [
    {
      "rateKey": "string",
      "pax": [
        {
          "roomId": 1,
          "type": "AD",
          "age": 20,
          "name": "string",
          "surname": "string"
        }
      ]
    }
  ]
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<bookingRQ>
  <echoToken>string</echoToken>
  <holder>
    <name>string</name>
    <surname>string</surname>
  </holder>
  <paymentData>
    <paymentCard>
      <cardType>string</cardType>
      <cardNumber>string</cardNumber>
      <cardHolderName>string</cardHolderName>
      <expiryDate>string</expiryDate>
      <cardCVC>string</cardCVC>
    </paymentCard>
    <contactData>
      <email>string</email>
      <phoneNumber>string</phoneNumber>
    </contactData>
    <billingAddress>
      <address1>string</address1>
      <address2>string</address2>
      <city>string</city>
      <state>string</state>
      <postalCode>string</postalCode>
      <countryCode>string</countryCode>
    </billingAddress>
    <webPartner>0</webPartner>
    <device>
      <id>string</id>
      <ip>string</ip>
    </device>
  </paymentData>
  <clientReference>string</clientReference>
  <remark>string</remark>
  <voucher>
    <language>string</language>
    <email>
      <to>string</to>
      <from>string</from>
      <title>string</title>
      <body>string</body>
    </email>
  </voucher>
  <language>ENG</language>
  <room>
    <rateKey>string</rateKey>
    <pax>
      <roomId>1</roomId>
      <type>AD</type>
      <age>20</age>
      <name>string</name>
      <surname>string</surname>
    </pax>
  </room>
</bookingRQ>
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
version|path|string|true|Specification version
body|body|[bookingRQ](#schemabookingrq)|false|No description
» echoToken|body|string|false|No description
» holder|body|[ApiHolder](#schemaapiholder)|true|No description
»» name|body|string|true|No description
»» surname|body|string|true|No description
» paymentData|body|[ApiPaymentData](#schemaapipaymentdata)|false|No description
»» paymentCard|body|[ApiPaymentCard](#schemaapipaymentcard)|true|No description
»»» cardType|body|string|false|No description
»»» cardNumber|body|string|false|No description
»»» cardHolderName|body|string|false|No description
»»» expiryDate|body|string|false|No description
»»» cardCVC|body|string|false|No description
»» contactData|body|[ApiPaymentContactData](#schemaapipaymentcontactdata)|true|No description
»»» email|body|string|false|No description
»»» phoneNumber|body|string|false|No description
»» billingAddress|body|[ApiBillingAddress](#schemaapibillingaddress)|false|No description
»»» address1|body|string|false|No description
»»» address2|body|string|false|No description
»»» city|body|string|false|No description
»»» state|body|string|false|No description
»»» postalCode|body|string|false|No description
»»» countryCode|body|string|false|No description
»» webPartner|body|integer(int32)|false|No description
»» device|body|[ApiBookingDevice](#schemaapibookingdevice)|false|No description
»»» id|body|string|false|No description
»»» ip|body|string|false|No description
» clientReference|body|string|true|No description
» remark|body|string|false|No description
» voucher|body|[ApiVoucher](#schemaapivoucher)|false|No description
»» language|body|string|false|No description
»» email|body|[ApiVoucherEmail](#schemaapivoucheremail)|false|No description
»»» to|body|string|false|No description
»»» from|body|string|false|No description
»»» title|body|string|false|No description
»»» body|body|string|false|No description
» language|body|string|false|No description
» room|body|[[ApiBookingRoom](#schemaapibookingroom)]|false|No description
»» rateKey|body|string|true|No description
»» pax|body|[[ApiPax](#schemaapipax)]|false|No description
»»» roomId|body|integer(int32)|false|No description
»»» type|body|string|true|No description
»»» age|body|integer(int32)|false|No description
»»» name|body|string|false|No description
»»» surname|body|string|false|No description


#### Enumerated Values

|Parameter|Value|
|---|---|
version|1.0|
version|1.1|
version|1.2|
»»» type|AD|
»»» type|CH|

> Example responses

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<bookingRS>
  <echoToken>string</echoToken>
  <auditData>
    <processTime>string</processTime>
    <timestamp>string</timestamp>
    <requestHost>string</requestHost>
    <serverId>string</serverId>
    <environment>string</environment>
    <release>string</release>
    <token>string</token>
  </auditData>
  <error>
    <code>string</code>
    <message>string</message>
  </error>
  <source>
    <channel>B2B</channel>
    <device>WEB</device>
    <deviceInfo>string</deviceInfo>
  </source>
  <booking>
    <reference>string</reference>
    <cancellationReference>string</cancellationReference>
    <clientReference>string</clientReference>
    <creationDate>2017-10-21</creationDate>
    <status>NEW</status>
    <modificationPolicies>
      <cancellation>false</cancellation>
      <modification>false</modification>
    </modificationPolicies>
    <agCommision>0</agCommision>
    <commisionVAT>0</commisionVAT>
    <creationUser>string</creationUser>
    <holder>
      <name>string</name>
      <surname>string</surname>
    </holder>
    <remark>string</remark>
    <totalSellingRate>0</totalSellingRate>
    <totalNet>0</totalNet>
    <pendingAmount>0</pendingAmount>
    <currency>string</currency>
    <hotel>
      <checkOut>2017-10-21</checkOut>
      <checkIn>2017-10-21</checkIn>
      <code>0</code>
      <name>string</name>
      <description>string</description>
      <image>string</image>
      <categoryCode>string</categoryCode>
      <categoryName>string</categoryName>
      <destinationCode>string</destinationCode>
      <destinationName>string</destinationName>
      <zoneCode>0</zoneCode>
      <zoneName>string</zoneName>
      <latitude>string</latitude>
      <longitude>string</longitude>
      <giata>string</giata>
      <minRate>0</minRate>
      <maxRate>0</maxRate>
      <totalSellingRate>0</totalSellingRate>
      <totalNet>0</totalNet>
      <pendingAmount>0</pendingAmount>
      <currency>string</currency>
      <supplier>
        <name>string</name>
        <vatNumber>string</vatNumber>
      </supplier>
      <clientComments>string</clientComments>
      <cancellationAmount>0</cancellationAmount>
      <upselling>
        <room>
          <status>NEW</status>
          <id>0</id>
          <code>string</code>
          <name>string</name>
          <pax>
            <roomId>1</roomId>
            <type>AD</type>
            <age>20</age>
            <name>string</name>
            <surname>string</surname>
          </pax>
          <rate>
            <rateKey>string</rateKey>
            <rateClass>string</rateClass>
            <rateType>BOOKABLE</rateType>
            <net>0</net>
            <discount>0</discount>
            <discountPCT>0</discountPCT>
            <sellingRate>0</sellingRate>
            <hotelSellingRate>0</hotelSellingRate>
            <amount>0</amount>
            <hotelCurrency>string</hotelCurrency>
            <hotelMandatory>false</hotelMandatory>
            <allotment>0</allotment>
            <commission>0</commission>
            <commissionVAT>0</commissionVAT>
            <commissionPCT>0</commissionPCT>
            <cost>
              <amount>0</amount>
              <currency>string</currency>
            </cost>
            <rateCommentsId>string</rateCommentsId>
            <rateComments>string</rateComments>
            <paymentType>AT_HOTEL</paymentType>
            <packaging>false</packaging>
            <boardCode>string</boardCode>
            <boardName>string</boardName>
            <rateBreakDown>
              <rateDiscount>
                <code>string</code>
                <name>string</name>
                <amount>0</amount>
              </rateDiscount>
              <rateSupplement>
                <code>string</code>
                <name>string</name>
                <from>2017-10-21</from>
                <to>2017-10-21</to>
                <amount>0</amount>
                <nights>0</nights>
                <paxNumber>0</paxNumber>
              </rateSupplement>
            </rateBreakDown>
            <rooms>0</rooms>
            <adults>0</adults>
            <children>0</children>
            <childrenAges>string</childrenAges>
            <rateup>0</rateup>
            <comment>
              <type>string</type>
              <text>string</text>
            </comment>
            <cancellationPolicy>
              <amount>0</amount>
              <hotelAmount>0</hotelAmount>
              <hotelCurrency>string</hotelCurrency>
              <from>string</from>
            </cancellationPolicy>
            <taxes>
              <allIncluded>false</allIncluded>
              <tax>
                <included>false</included>
                <percent>0</percent>
                <amount>0</amount>
                <currency>string</currency>
                <type>TAX</type>
                <clientAmount>0</clientAmount>
                <clientCurrency>string</clientCurrency>
              </tax>
            </taxes>
            <promotion>
              <code>string</code>
              <name>string</name>
              <remark>string</remark>
            </promotion>
            <offer>
              <code>string</code>
              <name>string</name>
              <amount>0</amount>
            </offer>
            <shiftRate>
              <rateKey>string</rateKey>
              <rateClass>string</rateClass>
              <rateType>BOOKABLE</rateType>
              <net>0</net>
              <discount>0</discount>
              <discountPCT>0</discountPCT>
              <sellingRate>0</sellingRate>
              <hotelSellingRate>0</hotelSellingRate>
              <amount>0</amount>
              <hotelCurrency>string</hotelCurrency>
              <hotelMandatory>false</hotelMandatory>
              <allotment>0</allotment>
              <commission>0</commission>
              <commissionVAT>0</commissionVAT>
              <commissionPCT>0</commissionPCT>
              <cost>
                <amount>0</amount>
                <currency>string</currency>
              </cost>
              <checkIn>2017-10-21</checkIn>
              <checkOut>2017-10-21</checkOut>
            </shiftRate>
            <dailyRate>
              <offset>0</offset>
              <dailyNet>0</dailyNet>
              <dailySellingRate>0</dailySellingRate>
            </dailyRate>
          </rate>
        </room>
      </upselling>
      <keyword>
        <code>0</code>
        <rating>0</rating>
      </keyword>
      <review>
        <rate>0</rate>
        <reviewCount>0</reviewCount>
        <type>string</type>
      </review>
      <room>
        <status>NEW</status>
        <id>0</id>
        <code>string</code>
        <name>string</name>
        <pax>
          <roomId>1</roomId>
          <type>AD</type>
          <age>20</age>
          <name>string</name>
          <surname>string</surname>
        </pax>
        <rate>
          <rateKey>string</rateKey>
          <rateClass>string</rateClass>
          <rateType>BOOKABLE</rateType>
          <net>0</net>
          <discount>0</discount>
          <discountPCT>0</discountPCT>
          <sellingRate>0</sellingRate>
          <hotelSellingRate>0</hotelSellingRate>
          <amount>0</amount>
          <hotelCurrency>string</hotelCurrency>
          <hotelMandatory>false</hotelMandatory>
          <allotment>0</allotment>
          <commission>0</commission>
          <commissionVAT>0</commissionVAT>
          <commissionPCT>0</commissionPCT>
          <cost>
            <amount>0</amount>
            <currency>string</currency>
          </cost>
          <rateCommentsId>string</rateCommentsId>
          <rateComments>string</rateComments>
          <paymentType>AT_HOTEL</paymentType>
          <packaging>false</packaging>
          <boardCode>string</boardCode>
          <boardName>string</boardName>
          <rateBreakDown>
            <rateDiscount>
              <code>string</code>
              <name>string</name>
              <amount>0</amount>
            </rateDiscount>
            <rateSupplement>
              <code>string</code>
              <name>string</name>
              <from>2017-10-21</from>
              <to>2017-10-21</to>
              <amount>0</amount>
              <nights>0</nights>
              <paxNumber>0</paxNumber>
            </rateSupplement>
          </rateBreakDown>
          <rooms>0</rooms>
          <adults>0</adults>
          <children>0</children>
          <childrenAges>string</childrenAges>
          <rateup>0</rateup>
          <comment>
            <type>string</type>
            <text>string</text>
          </comment>
          <cancellationPolicy>
            <amount>0</amount>
            <hotelAmount>0</hotelAmount>
            <hotelCurrency>string</hotelCurrency>
            <from>string</from>
          </cancellationPolicy>
          <taxes>
            <allIncluded>false</allIncluded>
            <tax>
              <included>false</included>
              <percent>0</percent>
              <amount>0</amount>
              <currency>string</currency>
              <type>TAX</type>
              <clientAmount>0</clientAmount>
              <clientCurrency>string</clientCurrency>
            </tax>
          </taxes>
          <promotion>
            <code>string</code>
            <name>string</name>
            <remark>string</remark>
          </promotion>
          <offer>
            <code>string</code>
            <name>string</name>
            <amount>0</amount>
          </offer>
          <shiftRate>
            <rateKey>string</rateKey>
            <rateClass>string</rateClass>
            <rateType>BOOKABLE</rateType>
            <net>0</net>
            <discount>0</discount>
            <discountPCT>0</discountPCT>
            <sellingRate>0</sellingRate>
            <hotelSellingRate>0</hotelSellingRate>
            <amount>0</amount>
            <hotelCurrency>string</hotelCurrency>
            <hotelMandatory>false</hotelMandatory>
            <allotment>0</allotment>
            <commission>0</commission>
            <commissionVAT>0</commissionVAT>
            <commissionPCT>0</commissionPCT>
            <cost>
              <amount>0</amount>
              <currency>string</currency>
            </cost>
            <checkIn>2017-10-21</checkIn>
            <checkOut>2017-10-21</checkOut>
          </shiftRate>
          <dailyRate>
            <offset>0</offset>
            <dailyNet>0</dailyNet>
            <dailySellingRate>0</dailySellingRate>
          </dailyRate>
        </rate>
      </room>
      <creditCard>
        <code>string</code>
        <name>string</name>
        <paymentType>AT_HOTEL</paymentType>
      </creditCard>
    </hotel>
  </booking>
</bookingRS>
```
```json
{
  "echoToken": "string",
  "auditData": {
    "processTime": "string",
    "timestamp": "string",
    "requestHost": "string",
    "serverId": "string",
    "environment": "string",
    "release": "string",
    "token": "string"
  },
  "error": {
    "code": "string",
    "message": "string"
  },
  "source": {
    "channel": "B2B",
    "device": "WEB",
    "deviceInfo": "string"
  },
  "booking": {
    "reference": "string",
    "cancellationReference": "string",
    "clientReference": "string",
    "creationDate": "2017-10-21",
    "status": "NEW",
    "modificationPolicies": {
      "cancellation": false,
      "modification": false
    },
    "agCommision": 0,
    "commisionVAT": 0,
    "creationUser": "string",
    "holder": {
      "name": "string",
      "surname": "string"
    },
    "remark": "string",
    "totalSellingRate": 0,
    "totalNet": 0,
    "pendingAmount": 0,
    "currency": "string",
    "hotel": {
      "checkOut": "2017-10-21",
      "checkIn": "2017-10-21",
      "code": 0,
      "name": "string",
      "description": "string",
      "image": "string",
      "categoryCode": "string",
      "categoryName": "string",
      "destinationCode": "string",
      "destinationName": "string",
      "zoneCode": 0,
      "zoneName": "string",
      "latitude": "string",
      "longitude": "string",
      "giata": "string",
      "minRate": 0,
      "maxRate": 0,
      "totalSellingRate": 0,
      "totalNet": 0,
      "pendingAmount": 0,
      "currency": "string",
      "supplier": {
        "name": "string",
        "vatNumber": "string"
      },
      "clientComments": "string",
      "cancellationAmount": 0,
      "upselling": {
        "room": [
          {
            "status": "NEW",
            "id": 0,
            "code": "string",
            "name": "string",
            "pax": [
              {
                "roomId": 1,
                "type": "AD",
                "age": 20,
                "name": "string",
                "surname": "string"
              }
            ],
            "rate": [
              {
                "rateKey": "string",
                "rateClass": "string",
                "rateType": "BOOKABLE",
                "net": 0,
                "discount": 0,
                "discountPCT": 0,
                "sellingRate": 0,
                "hotelSellingRate": 0,
                "amount": 0,
                "hotelCurrency": "string",
                "hotelMandatory": false,
                "allotment": 0,
                "commission": 0,
                "commissionVAT": 0,
                "commissionPCT": 0,
                "cost": {
                  "amount": 0,
                  "currency": "string"
                },
                "rateCommentsId": "string",
                "rateComments": "string",
                "paymentType": "AT_HOTEL",
                "packaging": false,
                "boardCode": "string",
                "boardName": "string",
                "rateBreakDown": {
                  "rateDiscount": [
                    {
                      "code": "string",
                      "name": "string",
                      "amount": 0
                    }
                  ],
                  "rateSupplement": [
                    {
                      "code": "string",
                      "name": "string",
                      "from": "2017-10-21",
                      "to": "2017-10-21",
                      "amount": 0,
                      "nights": 0,
                      "paxNumber": 0
                    }
                  ]
                },
                "rooms": 0,
                "adults": 0,
                "children": 0,
                "childrenAges": "string",
                "rateup": 0,
                "comment": [
                  {
                    "type": "string",
                    "text": "string"
                  }
                ],
                "cancellationPolicy": [
                  {
                    "amount": 0,
                    "hotelAmount": 0,
                    "hotelCurrency": "string",
                    "from": "string"
                  }
                ],
                "taxes": {
                  "allIncluded": false,
                  "tax": [
                    {
                      "included": false,
                      "percent": 0,
                      "amount": 0,
                      "currency": "string",
                      "type": "TAX",
                      "clientAmount": 0,
                      "clientCurrency": "string"
                    }
                  ]
                },
                "promotion": [
                  {
                    "code": "string",
                    "name": "string",
                    "remark": "string"
                  }
                ],
                "offer": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "shiftRate": [
                  {
                    "rateKey": "string",
                    "rateClass": "string",
                    "rateType": "BOOKABLE",
                    "net": 0,
                    "discount": 0,
                    "discountPCT": 0,
                    "sellingRate": 0,
                    "hotelSellingRate": 0,
                    "amount": 0,
                    "hotelCurrency": "string",
                    "hotelMandatory": false,
                    "allotment": 0,
                    "commission": 0,
                    "commissionVAT": 0,
                    "commissionPCT": 0,
                    "cost": {
                      "amount": 0,
                      "currency": "string"
                    },
                    "checkIn": "2017-10-21",
                    "checkOut": "2017-10-21"
                  }
                ],
                "dailyRate": [
                  {
                    "offset": 0,
                    "dailyNet": 0,
                    "dailySellingRate": 0
                  }
                ]
              }
            ]
          }
        ]
      },
      "keyword": [
        {
          "code": 0,
          "rating": 0
        }
      ],
      "review": [
        {
          "rate": 0,
          "reviewCount": 0,
          "type": "string"
        }
      ],
      "room": [
        {
          "status": "NEW",
          "id": 0,
          "code": "string",
          "name": "string",
          "pax": [
            {
              "roomId": 1,
              "type": "AD",
              "age": 20,
              "name": "string",
              "surname": "string"
            }
          ],
          "rate": [
            {
              "rateKey": "string",
              "rateClass": "string",
              "rateType": "BOOKABLE",
              "net": 0,
              "discount": 0,
              "discountPCT": 0,
              "sellingRate": 0,
              "hotelSellingRate": 0,
              "amount": 0,
              "hotelCurrency": "string",
              "hotelMandatory": false,
              "allotment": 0,
              "commission": 0,
              "commissionVAT": 0,
              "commissionPCT": 0,
              "cost": {
                "amount": 0,
                "currency": "string"
              },
              "rateCommentsId": "string",
              "rateComments": "string",
              "paymentType": "AT_HOTEL",
              "packaging": false,
              "boardCode": "string",
              "boardName": "string",
              "rateBreakDown": {
                "rateDiscount": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "rateSupplement": [
                  {
                    "code": "string",
                    "name": "string",
                    "from": "2017-10-21",
                    "to": "2017-10-21",
                    "amount": 0,
                    "nights": 0,
                    "paxNumber": 0
                  }
                ]
              },
              "rooms": 0,
              "adults": 0,
              "children": 0,
              "childrenAges": "string",
              "rateup": 0,
              "comment": [
                {
                  "type": "string",
                  "text": "string"
                }
              ],
              "cancellationPolicy": [
                {
                  "amount": 0,
                  "hotelAmount": 0,
                  "hotelCurrency": "string",
                  "from": "string"
                }
              ],
              "taxes": {
                "allIncluded": false,
                "tax": [
                  {
                    "included": false,
                    "percent": 0,
                    "amount": 0,
                    "currency": "string",
                    "type": "TAX",
                    "clientAmount": 0,
                    "clientCurrency": "string"
                  }
                ]
              },
              "promotion": [
                {
                  "code": "string",
                  "name": "string",
                  "remark": "string"
                }
              ],
              "offer": [
                {
                  "code": "string",
                  "name": "string",
                  "amount": 0
                }
              ],
              "shiftRate": [
                {
                  "rateKey": "string",
                  "rateClass": "string",
                  "rateType": "BOOKABLE",
                  "net": 0,
                  "discount": 0,
                  "discountPCT": 0,
                  "sellingRate": 0,
                  "hotelSellingRate": 0,
                  "amount": 0,
                  "hotelCurrency": "string",
                  "hotelMandatory": false,
                  "allotment": 0,
                  "commission": 0,
                  "commissionVAT": 0,
                  "commissionPCT": 0,
                  "cost": {
                    "amount": 0,
                    "currency": "string"
                  },
                  "checkIn": "2017-10-21",
                  "checkOut": "2017-10-21"
                }
              ],
              "dailyRate": [
                {
                  "offset": 0,
                  "dailyNet": 0,
                  "dailySellingRate": 0
                }
              ]
            }
          ]
        }
      ],
      "creditCard": [
        {
          "code": "string",
          "name": "string",
          "paymentType": "AT_HOTEL"
        }
      ]
    }
  }
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Sample|[bookingRS](#schemabookingrs)
500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Unexpected error|None

<aside class="success">
This operation does not require authentication
</aside>

## bookingDetail

> Code samples

```shell
# You can also use wget
curl -X GET https://api.test.hotelbeds.com/hotel-api/{version}/bookings/{bookingId} \
  -H 'Accept: application/xml'

```

```http
GET https://api.test.hotelbeds.com/hotel-api/{version}/bookings/{bookingId} HTTP/1.1
Host: api.test.hotelbeds.com

Accept: application/xml

```

```javascript
var headers = {
  'Accept':'application/xml'

};

$.ajax({
  url: 'https://api.test.hotelbeds.com/hotel-api/{version}/bookings/{bookingId}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/xml'

};

fetch('https://api.test.hotelbeds.com/hotel-api/{version}/bookings/{bookingId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/xml'
}

result = RestClient.get 'https://api.test.hotelbeds.com/hotel-api/{version}/bookings/{bookingId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/xml'
}

r = requests.get('https://api.test.hotelbeds.com/hotel-api/{version}/bookings/{bookingId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://api.test.hotelbeds.com/hotel-api/{version}/bookings/{bookingId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /{version}/bookings/{bookingId}`

*Booking detail*

Description.....

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
version|path|string|true|Specification version
bookingId|path|string|true|No description
language|query|string|false|No description


#### Enumerated Values

|Parameter|Value|
|---|---|
version|1.0|
version|1.1|
version|1.2|

> Example responses

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<bookingDetailRS>
  <echoToken>string</echoToken>
  <auditData>
    <processTime>string</processTime>
    <timestamp>string</timestamp>
    <requestHost>string</requestHost>
    <serverId>string</serverId>
    <environment>string</environment>
    <release>string</release>
    <token>string</token>
  </auditData>
  <error>
    <code>string</code>
    <message>string</message>
  </error>
  <booking>
    <reference>string</reference>
    <cancellationReference>string</cancellationReference>
    <clientReference>string</clientReference>
    <creationDate>2017-10-21</creationDate>
    <status>NEW</status>
    <modificationPolicies>
      <cancellation>false</cancellation>
      <modification>false</modification>
    </modificationPolicies>
    <agCommision>0</agCommision>
    <commisionVAT>0</commisionVAT>
    <creationUser>string</creationUser>
    <holder>
      <name>string</name>
      <surname>string</surname>
    </holder>
    <remark>string</remark>
    <totalSellingRate>0</totalSellingRate>
    <totalNet>0</totalNet>
    <pendingAmount>0</pendingAmount>
    <currency>string</currency>
    <hotel>
      <checkOut>2017-10-21</checkOut>
      <checkIn>2017-10-21</checkIn>
      <code>0</code>
      <name>string</name>
      <description>string</description>
      <image>string</image>
      <categoryCode>string</categoryCode>
      <categoryName>string</categoryName>
      <destinationCode>string</destinationCode>
      <destinationName>string</destinationName>
      <zoneCode>0</zoneCode>
      <zoneName>string</zoneName>
      <latitude>string</latitude>
      <longitude>string</longitude>
      <giata>string</giata>
      <minRate>0</minRate>
      <maxRate>0</maxRate>
      <totalSellingRate>0</totalSellingRate>
      <totalNet>0</totalNet>
      <pendingAmount>0</pendingAmount>
      <currency>string</currency>
      <supplier>
        <name>string</name>
        <vatNumber>string</vatNumber>
      </supplier>
      <clientComments>string</clientComments>
      <cancellationAmount>0</cancellationAmount>
      <upselling>
        <room>
          <status>NEW</status>
          <id>0</id>
          <code>string</code>
          <name>string</name>
          <pax>
            <roomId>1</roomId>
            <type>AD</type>
            <age>20</age>
            <name>string</name>
            <surname>string</surname>
          </pax>
          <rate>
            <rateKey>string</rateKey>
            <rateClass>string</rateClass>
            <rateType>BOOKABLE</rateType>
            <net>0</net>
            <discount>0</discount>
            <discountPCT>0</discountPCT>
            <sellingRate>0</sellingRate>
            <hotelSellingRate>0</hotelSellingRate>
            <amount>0</amount>
            <hotelCurrency>string</hotelCurrency>
            <hotelMandatory>false</hotelMandatory>
            <allotment>0</allotment>
            <commission>0</commission>
            <commissionVAT>0</commissionVAT>
            <commissionPCT>0</commissionPCT>
            <cost>
              <amount>0</amount>
              <currency>string</currency>
            </cost>
            <rateCommentsId>string</rateCommentsId>
            <rateComments>string</rateComments>
            <paymentType>AT_HOTEL</paymentType>
            <packaging>false</packaging>
            <boardCode>string</boardCode>
            <boardName>string</boardName>
            <rateBreakDown>
              <rateDiscount>
                <code>string</code>
                <name>string</name>
                <amount>0</amount>
              </rateDiscount>
              <rateSupplement>
                <code>string</code>
                <name>string</name>
                <from>2017-10-21</from>
                <to>2017-10-21</to>
                <amount>0</amount>
                <nights>0</nights>
                <paxNumber>0</paxNumber>
              </rateSupplement>
            </rateBreakDown>
            <rooms>0</rooms>
            <adults>0</adults>
            <children>0</children>
            <childrenAges>string</childrenAges>
            <rateup>0</rateup>
            <comment>
              <type>string</type>
              <text>string</text>
            </comment>
            <cancellationPolicy>
              <amount>0</amount>
              <hotelAmount>0</hotelAmount>
              <hotelCurrency>string</hotelCurrency>
              <from>string</from>
            </cancellationPolicy>
            <taxes>
              <allIncluded>false</allIncluded>
              <tax>
                <included>false</included>
                <percent>0</percent>
                <amount>0</amount>
                <currency>string</currency>
                <type>TAX</type>
                <clientAmount>0</clientAmount>
                <clientCurrency>string</clientCurrency>
              </tax>
            </taxes>
            <promotion>
              <code>string</code>
              <name>string</name>
              <remark>string</remark>
            </promotion>
            <offer>
              <code>string</code>
              <name>string</name>
              <amount>0</amount>
            </offer>
            <shiftRate>
              <rateKey>string</rateKey>
              <rateClass>string</rateClass>
              <rateType>BOOKABLE</rateType>
              <net>0</net>
              <discount>0</discount>
              <discountPCT>0</discountPCT>
              <sellingRate>0</sellingRate>
              <hotelSellingRate>0</hotelSellingRate>
              <amount>0</amount>
              <hotelCurrency>string</hotelCurrency>
              <hotelMandatory>false</hotelMandatory>
              <allotment>0</allotment>
              <commission>0</commission>
              <commissionVAT>0</commissionVAT>
              <commissionPCT>0</commissionPCT>
              <cost>
                <amount>0</amount>
                <currency>string</currency>
              </cost>
              <checkIn>2017-10-21</checkIn>
              <checkOut>2017-10-21</checkOut>
            </shiftRate>
            <dailyRate>
              <offset>0</offset>
              <dailyNet>0</dailyNet>
              <dailySellingRate>0</dailySellingRate>
            </dailyRate>
          </rate>
        </room>
      </upselling>
      <keyword>
        <code>0</code>
        <rating>0</rating>
      </keyword>
      <review>
        <rate>0</rate>
        <reviewCount>0</reviewCount>
        <type>string</type>
      </review>
      <room>
        <status>NEW</status>
        <id>0</id>
        <code>string</code>
        <name>string</name>
        <pax>
          <roomId>1</roomId>
          <type>AD</type>
          <age>20</age>
          <name>string</name>
          <surname>string</surname>
        </pax>
        <rate>
          <rateKey>string</rateKey>
          <rateClass>string</rateClass>
          <rateType>BOOKABLE</rateType>
          <net>0</net>
          <discount>0</discount>
          <discountPCT>0</discountPCT>
          <sellingRate>0</sellingRate>
          <hotelSellingRate>0</hotelSellingRate>
          <amount>0</amount>
          <hotelCurrency>string</hotelCurrency>
          <hotelMandatory>false</hotelMandatory>
          <allotment>0</allotment>
          <commission>0</commission>
          <commissionVAT>0</commissionVAT>
          <commissionPCT>0</commissionPCT>
          <cost>
            <amount>0</amount>
            <currency>string</currency>
          </cost>
          <rateCommentsId>string</rateCommentsId>
          <rateComments>string</rateComments>
          <paymentType>AT_HOTEL</paymentType>
          <packaging>false</packaging>
          <boardCode>string</boardCode>
          <boardName>string</boardName>
          <rateBreakDown>
            <rateDiscount>
              <code>string</code>
              <name>string</name>
              <amount>0</amount>
            </rateDiscount>
            <rateSupplement>
              <code>string</code>
              <name>string</name>
              <from>2017-10-21</from>
              <to>2017-10-21</to>
              <amount>0</amount>
              <nights>0</nights>
              <paxNumber>0</paxNumber>
            </rateSupplement>
          </rateBreakDown>
          <rooms>0</rooms>
          <adults>0</adults>
          <children>0</children>
          <childrenAges>string</childrenAges>
          <rateup>0</rateup>
          <comment>
            <type>string</type>
            <text>string</text>
          </comment>
          <cancellationPolicy>
            <amount>0</amount>
            <hotelAmount>0</hotelAmount>
            <hotelCurrency>string</hotelCurrency>
            <from>string</from>
          </cancellationPolicy>
          <taxes>
            <allIncluded>false</allIncluded>
            <tax>
              <included>false</included>
              <percent>0</percent>
              <amount>0</amount>
              <currency>string</currency>
              <type>TAX</type>
              <clientAmount>0</clientAmount>
              <clientCurrency>string</clientCurrency>
            </tax>
          </taxes>
          <promotion>
            <code>string</code>
            <name>string</name>
            <remark>string</remark>
          </promotion>
          <offer>
            <code>string</code>
            <name>string</name>
            <amount>0</amount>
          </offer>
          <shiftRate>
            <rateKey>string</rateKey>
            <rateClass>string</rateClass>
            <rateType>BOOKABLE</rateType>
            <net>0</net>
            <discount>0</discount>
            <discountPCT>0</discountPCT>
            <sellingRate>0</sellingRate>
            <hotelSellingRate>0</hotelSellingRate>
            <amount>0</amount>
            <hotelCurrency>string</hotelCurrency>
            <hotelMandatory>false</hotelMandatory>
            <allotment>0</allotment>
            <commission>0</commission>
            <commissionVAT>0</commissionVAT>
            <commissionPCT>0</commissionPCT>
            <cost>
              <amount>0</amount>
              <currency>string</currency>
            </cost>
            <checkIn>2017-10-21</checkIn>
            <checkOut>2017-10-21</checkOut>
          </shiftRate>
          <dailyRate>
            <offset>0</offset>
            <dailyNet>0</dailyNet>
            <dailySellingRate>0</dailySellingRate>
          </dailyRate>
        </rate>
      </room>
      <creditCard>
        <code>string</code>
        <name>string</name>
        <paymentType>AT_HOTEL</paymentType>
      </creditCard>
    </hotel>
  </booking>
</bookingDetailRS>
```
```json
{
  "echoToken": "string",
  "auditData": {
    "processTime": "string",
    "timestamp": "string",
    "requestHost": "string",
    "serverId": "string",
    "environment": "string",
    "release": "string",
    "token": "string"
  },
  "error": {
    "code": "string",
    "message": "string"
  },
  "booking": {
    "reference": "string",
    "cancellationReference": "string",
    "clientReference": "string",
    "creationDate": "2017-10-21",
    "status": "NEW",
    "modificationPolicies": {
      "cancellation": false,
      "modification": false
    },
    "agCommision": 0,
    "commisionVAT": 0,
    "creationUser": "string",
    "holder": {
      "name": "string",
      "surname": "string"
    },
    "remark": "string",
    "totalSellingRate": 0,
    "totalNet": 0,
    "pendingAmount": 0,
    "currency": "string",
    "hotel": {
      "checkOut": "2017-10-21",
      "checkIn": "2017-10-21",
      "code": 0,
      "name": "string",
      "description": "string",
      "image": "string",
      "categoryCode": "string",
      "categoryName": "string",
      "destinationCode": "string",
      "destinationName": "string",
      "zoneCode": 0,
      "zoneName": "string",
      "latitude": "string",
      "longitude": "string",
      "giata": "string",
      "minRate": 0,
      "maxRate": 0,
      "totalSellingRate": 0,
      "totalNet": 0,
      "pendingAmount": 0,
      "currency": "string",
      "supplier": {
        "name": "string",
        "vatNumber": "string"
      },
      "clientComments": "string",
      "cancellationAmount": 0,
      "upselling": {
        "room": [
          {
            "status": "NEW",
            "id": 0,
            "code": "string",
            "name": "string",
            "pax": [
              {
                "roomId": 1,
                "type": "AD",
                "age": 20,
                "name": "string",
                "surname": "string"
              }
            ],
            "rate": [
              {
                "rateKey": "string",
                "rateClass": "string",
                "rateType": "BOOKABLE",
                "net": 0,
                "discount": 0,
                "discountPCT": 0,
                "sellingRate": 0,
                "hotelSellingRate": 0,
                "amount": 0,
                "hotelCurrency": "string",
                "hotelMandatory": false,
                "allotment": 0,
                "commission": 0,
                "commissionVAT": 0,
                "commissionPCT": 0,
                "cost": {
                  "amount": 0,
                  "currency": "string"
                },
                "rateCommentsId": "string",
                "rateComments": "string",
                "paymentType": "AT_HOTEL",
                "packaging": false,
                "boardCode": "string",
                "boardName": "string",
                "rateBreakDown": {
                  "rateDiscount": [
                    {
                      "code": "string",
                      "name": "string",
                      "amount": 0
                    }
                  ],
                  "rateSupplement": [
                    {
                      "code": "string",
                      "name": "string",
                      "from": "2017-10-21",
                      "to": "2017-10-21",
                      "amount": 0,
                      "nights": 0,
                      "paxNumber": 0
                    }
                  ]
                },
                "rooms": 0,
                "adults": 0,
                "children": 0,
                "childrenAges": "string",
                "rateup": 0,
                "comment": [
                  {
                    "type": "string",
                    "text": "string"
                  }
                ],
                "cancellationPolicy": [
                  {
                    "amount": 0,
                    "hotelAmount": 0,
                    "hotelCurrency": "string",
                    "from": "string"
                  }
                ],
                "taxes": {
                  "allIncluded": false,
                  "tax": [
                    {
                      "included": false,
                      "percent": 0,
                      "amount": 0,
                      "currency": "string",
                      "type": "TAX",
                      "clientAmount": 0,
                      "clientCurrency": "string"
                    }
                  ]
                },
                "promotion": [
                  {
                    "code": "string",
                    "name": "string",
                    "remark": "string"
                  }
                ],
                "offer": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "shiftRate": [
                  {
                    "rateKey": "string",
                    "rateClass": "string",
                    "rateType": "BOOKABLE",
                    "net": 0,
                    "discount": 0,
                    "discountPCT": 0,
                    "sellingRate": 0,
                    "hotelSellingRate": 0,
                    "amount": 0,
                    "hotelCurrency": "string",
                    "hotelMandatory": false,
                    "allotment": 0,
                    "commission": 0,
                    "commissionVAT": 0,
                    "commissionPCT": 0,
                    "cost": {
                      "amount": 0,
                      "currency": "string"
                    },
                    "checkIn": "2017-10-21",
                    "checkOut": "2017-10-21"
                  }
                ],
                "dailyRate": [
                  {
                    "offset": 0,
                    "dailyNet": 0,
                    "dailySellingRate": 0
                  }
                ]
              }
            ]
          }
        ]
      },
      "keyword": [
        {
          "code": 0,
          "rating": 0
        }
      ],
      "review": [
        {
          "rate": 0,
          "reviewCount": 0,
          "type": "string"
        }
      ],
      "room": [
        {
          "status": "NEW",
          "id": 0,
          "code": "string",
          "name": "string",
          "pax": [
            {
              "roomId": 1,
              "type": "AD",
              "age": 20,
              "name": "string",
              "surname": "string"
            }
          ],
          "rate": [
            {
              "rateKey": "string",
              "rateClass": "string",
              "rateType": "BOOKABLE",
              "net": 0,
              "discount": 0,
              "discountPCT": 0,
              "sellingRate": 0,
              "hotelSellingRate": 0,
              "amount": 0,
              "hotelCurrency": "string",
              "hotelMandatory": false,
              "allotment": 0,
              "commission": 0,
              "commissionVAT": 0,
              "commissionPCT": 0,
              "cost": {
                "amount": 0,
                "currency": "string"
              },
              "rateCommentsId": "string",
              "rateComments": "string",
              "paymentType": "AT_HOTEL",
              "packaging": false,
              "boardCode": "string",
              "boardName": "string",
              "rateBreakDown": {
                "rateDiscount": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "rateSupplement": [
                  {
                    "code": "string",
                    "name": "string",
                    "from": "2017-10-21",
                    "to": "2017-10-21",
                    "amount": 0,
                    "nights": 0,
                    "paxNumber": 0
                  }
                ]
              },
              "rooms": 0,
              "adults": 0,
              "children": 0,
              "childrenAges": "string",
              "rateup": 0,
              "comment": [
                {
                  "type": "string",
                  "text": "string"
                }
              ],
              "cancellationPolicy": [
                {
                  "amount": 0,
                  "hotelAmount": 0,
                  "hotelCurrency": "string",
                  "from": "string"
                }
              ],
              "taxes": {
                "allIncluded": false,
                "tax": [
                  {
                    "included": false,
                    "percent": 0,
                    "amount": 0,
                    "currency": "string",
                    "type": "TAX",
                    "clientAmount": 0,
                    "clientCurrency": "string"
                  }
                ]
              },
              "promotion": [
                {
                  "code": "string",
                  "name": "string",
                  "remark": "string"
                }
              ],
              "offer": [
                {
                  "code": "string",
                  "name": "string",
                  "amount": 0
                }
              ],
              "shiftRate": [
                {
                  "rateKey": "string",
                  "rateClass": "string",
                  "rateType": "BOOKABLE",
                  "net": 0,
                  "discount": 0,
                  "discountPCT": 0,
                  "sellingRate": 0,
                  "hotelSellingRate": 0,
                  "amount": 0,
                  "hotelCurrency": "string",
                  "hotelMandatory": false,
                  "allotment": 0,
                  "commission": 0,
                  "commissionVAT": 0,
                  "commissionPCT": 0,
                  "cost": {
                    "amount": 0,
                    "currency": "string"
                  },
                  "checkIn": "2017-10-21",
                  "checkOut": "2017-10-21"
                }
              ],
              "dailyRate": [
                {
                  "offset": 0,
                  "dailyNet": 0,
                  "dailySellingRate": 0
                }
              ]
            }
          ]
        }
      ],
      "creditCard": [
        {
          "code": "string",
          "name": "string",
          "paymentType": "AT_HOTEL"
        }
      ]
    }
  }
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Sample|[bookingDetailRS](#schemabookingdetailrs)
500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Unexpected error|None

<aside class="success">
This operation does not require authentication
</aside>

## bookingChange

> Code samples

```shell
# You can also use wget
curl -X PUT https://api.test.hotelbeds.com/hotel-api/{version}/bookings/{bookingId} \
  -H 'Content-Type: application/xml' \
  -H 'Accept: application/xml'

```

```http
PUT https://api.test.hotelbeds.com/hotel-api/{version}/bookings/{bookingId} HTTP/1.1
Host: api.test.hotelbeds.com
Content-Type: application/xml
Accept: application/xml

```

```javascript
var headers = {
  'Content-Type':'application/xml',
  'Accept':'application/xml'

};

$.ajax({
  url: 'https://api.test.hotelbeds.com/hotel-api/{version}/bookings/{bookingId}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "echoToken": "string",
  "bookingId": "string",
  "mode": "SIMULATION",
  "language": "ENG",
  "booking": {
    "reference": "string",
    "cancellationReference": "string",
    "clientReference": "string",
    "creationDate": "2017-10-21",
    "status": "NEW",
    "modificationPolicies": {
      "cancellation": false,
      "modification": false
    },
    "agCommision": 0,
    "commisionVAT": 0,
    "creationUser": "string",
    "holder": {
      "name": "string",
      "surname": "string"
    },
    "remark": "string",
    "totalSellingRate": 0,
    "totalNet": 0,
    "pendingAmount": 0,
    "currency": "string",
    "hotel": {
      "checkOut": "2017-10-21",
      "checkIn": "2017-10-21",
      "code": 0,
      "name": "string",
      "description": "string",
      "image": "string",
      "categoryCode": "string",
      "categoryName": "string",
      "destinationCode": "string",
      "destinationName": "string",
      "zoneCode": 0,
      "zoneName": "string",
      "latitude": "string",
      "longitude": "string",
      "giata": "string",
      "minRate": 0,
      "maxRate": 0,
      "totalSellingRate": 0,
      "totalNet": 0,
      "pendingAmount": 0,
      "currency": "string",
      "supplier": {
        "name": "string",
        "vatNumber": "string"
      },
      "clientComments": "string",
      "cancellationAmount": 0,
      "upselling": {
        "room": [
          {
            "status": "NEW",
            "id": 0,
            "code": "string",
            "name": "string",
            "pax": [
              {
                "roomId": 1,
                "type": "AD",
                "age": 20,
                "name": "string",
                "surname": "string"
              }
            ],
            "rate": [
              {
                "rateKey": "string",
                "rateClass": "string",
                "rateType": "BOOKABLE",
                "net": 0,
                "discount": 0,
                "discountPCT": 0,
                "sellingRate": 0,
                "hotelSellingRate": 0,
                "amount": 0,
                "hotelCurrency": "string",
                "hotelMandatory": false,
                "allotment": 0,
                "commission": 0,
                "commissionVAT": 0,
                "commissionPCT": 0,
                "cost": {
                  "amount": 0,
                  "currency": "string"
                },
                "rateCommentsId": "string",
                "rateComments": "string",
                "paymentType": "AT_HOTEL",
                "packaging": false,
                "boardCode": "string",
                "boardName": "string",
                "rateBreakDown": {
                  "rateDiscount": [
                    {
                      "code": "string",
                      "name": "string",
                      "amount": 0
                    }
                  ],
                  "rateSupplement": [
                    {
                      "code": "string",
                      "name": "string",
                      "from": "2017-10-21",
                      "to": "2017-10-21",
                      "amount": 0,
                      "nights": 0,
                      "paxNumber": 0
                    }
                  ]
                },
                "rooms": 0,
                "adults": 0,
                "children": 0,
                "childrenAges": "string",
                "rateup": 0,
                "comment": [
                  {
                    "type": "string",
                    "text": "string"
                  }
                ],
                "cancellationPolicy": [
                  {
                    "amount": 0,
                    "hotelAmount": 0,
                    "hotelCurrency": "string",
                    "from": "string"
                  }
                ],
                "taxes": {
                  "allIncluded": false,
                  "tax": [
                    {
                      "included": false,
                      "percent": 0,
                      "amount": 0,
                      "currency": "string",
                      "type": "TAX",
                      "clientAmount": 0,
                      "clientCurrency": "string"
                    }
                  ]
                },
                "promotion": [
                  {
                    "code": "string",
                    "name": "string",
                    "remark": "string"
                  }
                ],
                "offer": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "shiftRate": [
                  {
                    "rateKey": "string",
                    "rateClass": "string",
                    "rateType": "BOOKABLE",
                    "net": 0,
                    "discount": 0,
                    "discountPCT": 0,
                    "sellingRate": 0,
                    "hotelSellingRate": 0,
                    "amount": 0,
                    "hotelCurrency": "string",
                    "hotelMandatory": false,
                    "allotment": 0,
                    "commission": 0,
                    "commissionVAT": 0,
                    "commissionPCT": 0,
                    "cost": {
                      "amount": 0,
                      "currency": "string"
                    },
                    "checkIn": "2017-10-21",
                    "checkOut": "2017-10-21"
                  }
                ],
                "dailyRate": [
                  {
                    "offset": 0,
                    "dailyNet": 0,
                    "dailySellingRate": 0
                  }
                ]
              }
            ]
          }
        ]
      },
      "keyword": [
        {
          "code": 0,
          "rating": 0
        }
      ],
      "review": [
        {
          "rate": 0,
          "reviewCount": 0,
          "type": "string"
        }
      ],
      "room": [
        {
          "status": "NEW",
          "id": 0,
          "code": "string",
          "name": "string",
          "pax": [
            {
              "roomId": 1,
              "type": "AD",
              "age": 20,
              "name": "string",
              "surname": "string"
            }
          ],
          "rate": [
            {
              "rateKey": "string",
              "rateClass": "string",
              "rateType": "BOOKABLE",
              "net": 0,
              "discount": 0,
              "discountPCT": 0,
              "sellingRate": 0,
              "hotelSellingRate": 0,
              "amount": 0,
              "hotelCurrency": "string",
              "hotelMandatory": false,
              "allotment": 0,
              "commission": 0,
              "commissionVAT": 0,
              "commissionPCT": 0,
              "cost": {
                "amount": 0,
                "currency": "string"
              },
              "rateCommentsId": "string",
              "rateComments": "string",
              "paymentType": "AT_HOTEL",
              "packaging": false,
              "boardCode": "string",
              "boardName": "string",
              "rateBreakDown": {
                "rateDiscount": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "rateSupplement": [
                  {
                    "code": "string",
                    "name": "string",
                    "from": "2017-10-21",
                    "to": "2017-10-21",
                    "amount": 0,
                    "nights": 0,
                    "paxNumber": 0
                  }
                ]
              },
              "rooms": 0,
              "adults": 0,
              "children": 0,
              "childrenAges": "string",
              "rateup": 0,
              "comment": [
                {
                  "type": "string",
                  "text": "string"
                }
              ],
              "cancellationPolicy": [
                {
                  "amount": 0,
                  "hotelAmount": 0,
                  "hotelCurrency": "string",
                  "from": "string"
                }
              ],
              "taxes": {
                "allIncluded": false,
                "tax": [
                  {
                    "included": false,
                    "percent": 0,
                    "amount": 0,
                    "currency": "string",
                    "type": "TAX",
                    "clientAmount": 0,
                    "clientCurrency": "string"
                  }
                ]
              },
              "promotion": [
                {
                  "code": "string",
                  "name": "string",
                  "remark": "string"
                }
              ],
              "offer": [
                {
                  "code": "string",
                  "name": "string",
                  "amount": 0
                }
              ],
              "shiftRate": [
                {
                  "rateKey": "string",
                  "rateClass": "string",
                  "rateType": "BOOKABLE",
                  "net": 0,
                  "discount": 0,
                  "discountPCT": 0,
                  "sellingRate": 0,
                  "hotelSellingRate": 0,
                  "amount": 0,
                  "hotelCurrency": "string",
                  "hotelMandatory": false,
                  "allotment": 0,
                  "commission": 0,
                  "commissionVAT": 0,
                  "commissionPCT": 0,
                  "cost": {
                    "amount": 0,
                    "currency": "string"
                  },
                  "checkIn": "2017-10-21",
                  "checkOut": "2017-10-21"
                }
              ],
              "dailyRate": [
                {
                  "offset": 0,
                  "dailyNet": 0,
                  "dailySellingRate": 0
                }
              ]
            }
          ]
        }
      ],
      "creditCard": [
        {
          "code": "string",
          "name": "string",
          "paymentType": "AT_HOTEL"
        }
      ]
    }
  }
}';
const headers = {
  'Content-Type':'application/xml',
  'Accept':'application/xml'

};

fetch('https://api.test.hotelbeds.com/hotel-api/{version}/bookings/{bookingId}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/xml',
  'Accept' => 'application/xml'
}

result = RestClient.put 'https://api.test.hotelbeds.com/hotel-api/{version}/bookings/{bookingId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/xml',
  'Accept': 'application/xml'
}

r = requests.put('https://api.test.hotelbeds.com/hotel-api/{version}/bookings/{bookingId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://api.test.hotelbeds.com/hotel-api/{version}/bookings/{bookingId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /{version}/bookings/{bookingId}`

*Booking change*

Description.....

> Body parameter

```json
{
  "echoToken": "string",
  "bookingId": "string",
  "mode": "SIMULATION",
  "language": "ENG",
  "booking": {
    "reference": "string",
    "cancellationReference": "string",
    "clientReference": "string",
    "creationDate": "2017-10-21",
    "status": "NEW",
    "modificationPolicies": {
      "cancellation": false,
      "modification": false
    },
    "agCommision": 0,
    "commisionVAT": 0,
    "creationUser": "string",
    "holder": {
      "name": "string",
      "surname": "string"
    },
    "remark": "string",
    "totalSellingRate": 0,
    "totalNet": 0,
    "pendingAmount": 0,
    "currency": "string",
    "hotel": {
      "checkOut": "2017-10-21",
      "checkIn": "2017-10-21",
      "code": 0,
      "name": "string",
      "description": "string",
      "image": "string",
      "categoryCode": "string",
      "categoryName": "string",
      "destinationCode": "string",
      "destinationName": "string",
      "zoneCode": 0,
      "zoneName": "string",
      "latitude": "string",
      "longitude": "string",
      "giata": "string",
      "minRate": 0,
      "maxRate": 0,
      "totalSellingRate": 0,
      "totalNet": 0,
      "pendingAmount": 0,
      "currency": "string",
      "supplier": {
        "name": "string",
        "vatNumber": "string"
      },
      "clientComments": "string",
      "cancellationAmount": 0,
      "upselling": {
        "room": [
          {
            "status": "NEW",
            "id": 0,
            "code": "string",
            "name": "string",
            "pax": [
              {
                "roomId": 1,
                "type": "AD",
                "age": 20,
                "name": "string",
                "surname": "string"
              }
            ],
            "rate": [
              {
                "rateKey": "string",
                "rateClass": "string",
                "rateType": "BOOKABLE",
                "net": 0,
                "discount": 0,
                "discountPCT": 0,
                "sellingRate": 0,
                "hotelSellingRate": 0,
                "amount": 0,
                "hotelCurrency": "string",
                "hotelMandatory": false,
                "allotment": 0,
                "commission": 0,
                "commissionVAT": 0,
                "commissionPCT": 0,
                "cost": {
                  "amount": 0,
                  "currency": "string"
                },
                "rateCommentsId": "string",
                "rateComments": "string",
                "paymentType": "AT_HOTEL",
                "packaging": false,
                "boardCode": "string",
                "boardName": "string",
                "rateBreakDown": {
                  "rateDiscount": [
                    {
                      "code": "string",
                      "name": "string",
                      "amount": 0
                    }
                  ],
                  "rateSupplement": [
                    {
                      "code": "string",
                      "name": "string",
                      "from": "2017-10-21",
                      "to": "2017-10-21",
                      "amount": 0,
                      "nights": 0,
                      "paxNumber": 0
                    }
                  ]
                },
                "rooms": 0,
                "adults": 0,
                "children": 0,
                "childrenAges": "string",
                "rateup": 0,
                "comment": [
                  {
                    "type": "string",
                    "text": "string"
                  }
                ],
                "cancellationPolicy": [
                  {
                    "amount": 0,
                    "hotelAmount": 0,
                    "hotelCurrency": "string",
                    "from": "string"
                  }
                ],
                "taxes": {
                  "allIncluded": false,
                  "tax": [
                    {
                      "included": false,
                      "percent": 0,
                      "amount": 0,
                      "currency": "string",
                      "type": "TAX",
                      "clientAmount": 0,
                      "clientCurrency": "string"
                    }
                  ]
                },
                "promotion": [
                  {
                    "code": "string",
                    "name": "string",
                    "remark": "string"
                  }
                ],
                "offer": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "shiftRate": [
                  {
                    "rateKey": "string",
                    "rateClass": "string",
                    "rateType": "BOOKABLE",
                    "net": 0,
                    "discount": 0,
                    "discountPCT": 0,
                    "sellingRate": 0,
                    "hotelSellingRate": 0,
                    "amount": 0,
                    "hotelCurrency": "string",
                    "hotelMandatory": false,
                    "allotment": 0,
                    "commission": 0,
                    "commissionVAT": 0,
                    "commissionPCT": 0,
                    "cost": {
                      "amount": 0,
                      "currency": "string"
                    },
                    "checkIn": "2017-10-21",
                    "checkOut": "2017-10-21"
                  }
                ],
                "dailyRate": [
                  {
                    "offset": 0,
                    "dailyNet": 0,
                    "dailySellingRate": 0
                  }
                ]
              }
            ]
          }
        ]
      },
      "keyword": [
        {
          "code": 0,
          "rating": 0
        }
      ],
      "review": [
        {
          "rate": 0,
          "reviewCount": 0,
          "type": "string"
        }
      ],
      "room": [
        {
          "status": "NEW",
          "id": 0,
          "code": "string",
          "name": "string",
          "pax": [
            {
              "roomId": 1,
              "type": "AD",
              "age": 20,
              "name": "string",
              "surname": "string"
            }
          ],
          "rate": [
            {
              "rateKey": "string",
              "rateClass": "string",
              "rateType": "BOOKABLE",
              "net": 0,
              "discount": 0,
              "discountPCT": 0,
              "sellingRate": 0,
              "hotelSellingRate": 0,
              "amount": 0,
              "hotelCurrency": "string",
              "hotelMandatory": false,
              "allotment": 0,
              "commission": 0,
              "commissionVAT": 0,
              "commissionPCT": 0,
              "cost": {
                "amount": 0,
                "currency": "string"
              },
              "rateCommentsId": "string",
              "rateComments": "string",
              "paymentType": "AT_HOTEL",
              "packaging": false,
              "boardCode": "string",
              "boardName": "string",
              "rateBreakDown": {
                "rateDiscount": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "rateSupplement": [
                  {
                    "code": "string",
                    "name": "string",
                    "from": "2017-10-21",
                    "to": "2017-10-21",
                    "amount": 0,
                    "nights": 0,
                    "paxNumber": 0
                  }
                ]
              },
              "rooms": 0,
              "adults": 0,
              "children": 0,
              "childrenAges": "string",
              "rateup": 0,
              "comment": [
                {
                  "type": "string",
                  "text": "string"
                }
              ],
              "cancellationPolicy": [
                {
                  "amount": 0,
                  "hotelAmount": 0,
                  "hotelCurrency": "string",
                  "from": "string"
                }
              ],
              "taxes": {
                "allIncluded": false,
                "tax": [
                  {
                    "included": false,
                    "percent": 0,
                    "amount": 0,
                    "currency": "string",
                    "type": "TAX",
                    "clientAmount": 0,
                    "clientCurrency": "string"
                  }
                ]
              },
              "promotion": [
                {
                  "code": "string",
                  "name": "string",
                  "remark": "string"
                }
              ],
              "offer": [
                {
                  "code": "string",
                  "name": "string",
                  "amount": 0
                }
              ],
              "shiftRate": [
                {
                  "rateKey": "string",
                  "rateClass": "string",
                  "rateType": "BOOKABLE",
                  "net": 0,
                  "discount": 0,
                  "discountPCT": 0,
                  "sellingRate": 0,
                  "hotelSellingRate": 0,
                  "amount": 0,
                  "hotelCurrency": "string",
                  "hotelMandatory": false,
                  "allotment": 0,
                  "commission": 0,
                  "commissionVAT": 0,
                  "commissionPCT": 0,
                  "cost": {
                    "amount": 0,
                    "currency": "string"
                  },
                  "checkIn": "2017-10-21",
                  "checkOut": "2017-10-21"
                }
              ],
              "dailyRate": [
                {
                  "offset": 0,
                  "dailyNet": 0,
                  "dailySellingRate": 0
                }
              ]
            }
          ]
        }
      ],
      "creditCard": [
        {
          "code": "string",
          "name": "string",
          "paymentType": "AT_HOTEL"
        }
      ]
    }
  }
}
```
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<bookingChangeRQ>
  <echoToken>string</echoToken>
  <bookingId>string</bookingId>
  <mode>SIMULATION</mode>
  <language>ENG</language>
  <booking>
    <reference>string</reference>
    <cancellationReference>string</cancellationReference>
    <clientReference>string</clientReference>
    <creationDate>2017-10-21</creationDate>
    <status>NEW</status>
    <modificationPolicies>
      <cancellation>false</cancellation>
      <modification>false</modification>
    </modificationPolicies>
    <agCommision>0</agCommision>
    <commisionVAT>0</commisionVAT>
    <creationUser>string</creationUser>
    <holder>
      <name>string</name>
      <surname>string</surname>
    </holder>
    <remark>string</remark>
    <totalSellingRate>0</totalSellingRate>
    <totalNet>0</totalNet>
    <pendingAmount>0</pendingAmount>
    <currency>string</currency>
    <hotel>
      <checkOut>2017-10-21</checkOut>
      <checkIn>2017-10-21</checkIn>
      <code>0</code>
      <name>string</name>
      <description>string</description>
      <image>string</image>
      <categoryCode>string</categoryCode>
      <categoryName>string</categoryName>
      <destinationCode>string</destinationCode>
      <destinationName>string</destinationName>
      <zoneCode>0</zoneCode>
      <zoneName>string</zoneName>
      <latitude>string</latitude>
      <longitude>string</longitude>
      <giata>string</giata>
      <minRate>0</minRate>
      <maxRate>0</maxRate>
      <totalSellingRate>0</totalSellingRate>
      <totalNet>0</totalNet>
      <pendingAmount>0</pendingAmount>
      <currency>string</currency>
      <supplier>
        <name>string</name>
        <vatNumber>string</vatNumber>
      </supplier>
      <clientComments>string</clientComments>
      <cancellationAmount>0</cancellationAmount>
      <upselling>
        <room>
          <status>NEW</status>
          <id>0</id>
          <code>string</code>
          <name>string</name>
          <pax>
            <roomId>1</roomId>
            <type>AD</type>
            <age>20</age>
            <name>string</name>
            <surname>string</surname>
          </pax>
          <rate>
            <rateKey>string</rateKey>
            <rateClass>string</rateClass>
            <rateType>BOOKABLE</rateType>
            <net>0</net>
            <discount>0</discount>
            <discountPCT>0</discountPCT>
            <sellingRate>0</sellingRate>
            <hotelSellingRate>0</hotelSellingRate>
            <amount>0</amount>
            <hotelCurrency>string</hotelCurrency>
            <hotelMandatory>false</hotelMandatory>
            <allotment>0</allotment>
            <commission>0</commission>
            <commissionVAT>0</commissionVAT>
            <commissionPCT>0</commissionPCT>
            <cost>
              <amount>0</amount>
              <currency>string</currency>
            </cost>
            <rateCommentsId>string</rateCommentsId>
            <rateComments>string</rateComments>
            <paymentType>AT_HOTEL</paymentType>
            <packaging>false</packaging>
            <boardCode>string</boardCode>
            <boardName>string</boardName>
            <rateBreakDown>
              <rateDiscount>
                <code>string</code>
                <name>string</name>
                <amount>0</amount>
              </rateDiscount>
              <rateSupplement>
                <code>string</code>
                <name>string</name>
                <from>2017-10-21</from>
                <to>2017-10-21</to>
                <amount>0</amount>
                <nights>0</nights>
                <paxNumber>0</paxNumber>
              </rateSupplement>
            </rateBreakDown>
            <rooms>0</rooms>
            <adults>0</adults>
            <children>0</children>
            <childrenAges>string</childrenAges>
            <rateup>0</rateup>
            <comment>
              <type>string</type>
              <text>string</text>
            </comment>
            <cancellationPolicy>
              <amount>0</amount>
              <hotelAmount>0</hotelAmount>
              <hotelCurrency>string</hotelCurrency>
              <from>string</from>
            </cancellationPolicy>
            <taxes>
              <allIncluded>false</allIncluded>
              <tax>
                <included>false</included>
                <percent>0</percent>
                <amount>0</amount>
                <currency>string</currency>
                <type>TAX</type>
                <clientAmount>0</clientAmount>
                <clientCurrency>string</clientCurrency>
              </tax>
            </taxes>
            <promotion>
              <code>string</code>
              <name>string</name>
              <remark>string</remark>
            </promotion>
            <offer>
              <code>string</code>
              <name>string</name>
              <amount>0</amount>
            </offer>
            <shiftRate>
              <rateKey>string</rateKey>
              <rateClass>string</rateClass>
              <rateType>BOOKABLE</rateType>
              <net>0</net>
              <discount>0</discount>
              <discountPCT>0</discountPCT>
              <sellingRate>0</sellingRate>
              <hotelSellingRate>0</hotelSellingRate>
              <amount>0</amount>
              <hotelCurrency>string</hotelCurrency>
              <hotelMandatory>false</hotelMandatory>
              <allotment>0</allotment>
              <commission>0</commission>
              <commissionVAT>0</commissionVAT>
              <commissionPCT>0</commissionPCT>
              <cost>
                <amount>0</amount>
                <currency>string</currency>
              </cost>
              <checkIn>2017-10-21</checkIn>
              <checkOut>2017-10-21</checkOut>
            </shiftRate>
            <dailyRate>
              <offset>0</offset>
              <dailyNet>0</dailyNet>
              <dailySellingRate>0</dailySellingRate>
            </dailyRate>
          </rate>
        </room>
      </upselling>
      <keyword>
        <code>0</code>
        <rating>0</rating>
      </keyword>
      <review>
        <rate>0</rate>
        <reviewCount>0</reviewCount>
        <type>string</type>
      </review>
      <room>
        <status>NEW</status>
        <id>0</id>
        <code>string</code>
        <name>string</name>
        <pax>
          <roomId>1</roomId>
          <type>AD</type>
          <age>20</age>
          <name>string</name>
          <surname>string</surname>
        </pax>
        <rate>
          <rateKey>string</rateKey>
          <rateClass>string</rateClass>
          <rateType>BOOKABLE</rateType>
          <net>0</net>
          <discount>0</discount>
          <discountPCT>0</discountPCT>
          <sellingRate>0</sellingRate>
          <hotelSellingRate>0</hotelSellingRate>
          <amount>0</amount>
          <hotelCurrency>string</hotelCurrency>
          <hotelMandatory>false</hotelMandatory>
          <allotment>0</allotment>
          <commission>0</commission>
          <commissionVAT>0</commissionVAT>
          <commissionPCT>0</commissionPCT>
          <cost>
            <amount>0</amount>
            <currency>string</currency>
          </cost>
          <rateCommentsId>string</rateCommentsId>
          <rateComments>string</rateComments>
          <paymentType>AT_HOTEL</paymentType>
          <packaging>false</packaging>
          <boardCode>string</boardCode>
          <boardName>string</boardName>
          <rateBreakDown>
            <rateDiscount>
              <code>string</code>
              <name>string</name>
              <amount>0</amount>
            </rateDiscount>
            <rateSupplement>
              <code>string</code>
              <name>string</name>
              <from>2017-10-21</from>
              <to>2017-10-21</to>
              <amount>0</amount>
              <nights>0</nights>
              <paxNumber>0</paxNumber>
            </rateSupplement>
          </rateBreakDown>
          <rooms>0</rooms>
          <adults>0</adults>
          <children>0</children>
          <childrenAges>string</childrenAges>
          <rateup>0</rateup>
          <comment>
            <type>string</type>
            <text>string</text>
          </comment>
          <cancellationPolicy>
            <amount>0</amount>
            <hotelAmount>0</hotelAmount>
            <hotelCurrency>string</hotelCurrency>
            <from>string</from>
          </cancellationPolicy>
          <taxes>
            <allIncluded>false</allIncluded>
            <tax>
              <included>false</included>
              <percent>0</percent>
              <amount>0</amount>
              <currency>string</currency>
              <type>TAX</type>
              <clientAmount>0</clientAmount>
              <clientCurrency>string</clientCurrency>
            </tax>
          </taxes>
          <promotion>
            <code>string</code>
            <name>string</name>
            <remark>string</remark>
          </promotion>
          <offer>
            <code>string</code>
            <name>string</name>
            <amount>0</amount>
          </offer>
          <shiftRate>
            <rateKey>string</rateKey>
            <rateClass>string</rateClass>
            <rateType>BOOKABLE</rateType>
            <net>0</net>
            <discount>0</discount>
            <discountPCT>0</discountPCT>
            <sellingRate>0</sellingRate>
            <hotelSellingRate>0</hotelSellingRate>
            <amount>0</amount>
            <hotelCurrency>string</hotelCurrency>
            <hotelMandatory>false</hotelMandatory>
            <allotment>0</allotment>
            <commission>0</commission>
            <commissionVAT>0</commissionVAT>
            <commissionPCT>0</commissionPCT>
            <cost>
              <amount>0</amount>
              <currency>string</currency>
            </cost>
            <checkIn>2017-10-21</checkIn>
            <checkOut>2017-10-21</checkOut>
          </shiftRate>
          <dailyRate>
            <offset>0</offset>
            <dailyNet>0</dailyNet>
            <dailySellingRate>0</dailySellingRate>
          </dailyRate>
        </rate>
      </room>
      <creditCard>
        <code>string</code>
        <name>string</name>
        <paymentType>AT_HOTEL</paymentType>
      </creditCard>
    </hotel>
  </booking>
</bookingChangeRQ>
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
version|path|string|true|Specification version
bookingId|path|string|true|No description
body|body|[bookingChangeRQ](#schemabookingchangerq)|false|No description
» echoToken|body|string|false|No description
» bookingId|body|string|true|No description
» mode|body|string|true|No description
» language|body|string|false|No description
» booking|body|[ApiBooking](#schemaapibooking)|true|No description
»» reference|body|string|false|No description
»» cancellationReference|body|string|false|No description
»» clientReference|body|string|false|No description
»» creationDate|body|string(date)|false|No description
»» status|body|string|false|No description
»» modificationPolicies|body|[ApiModificationPolicies](#schemaapimodificationpolicies)|false|No description
»»» cancellation|body|boolean|true|No description
»»» modification|body|boolean|true|No description
»» agCommision|body|number|false|No description
»» commisionVAT|body|number|false|No description
»» creationUser|body|string|false|No description
»» holder|body|[ApiHolder](#schemaapiholder)|false|No description
»»» name|body|string|true|No description
»»» surname|body|string|true|No description
»» remark|body|string|false|No description
»» totalSellingRate|body|number|false|No description
»» totalNet|body|number|false|No description
»» pendingAmount|body|number|false|No description
»» currency|body|string|false|No description
»» hotel|body|[ApiHotel](#schemaapihotel)|false|No description
»»» checkOut|body|string(date)|false|No description
»»» checkIn|body|string(date)|false|No description
»»» code|body|integer(int32)|false|No description
»»» name|body|string|false|No description
»»» description|body|string|false|No description
»»» image|body|string|false|No description
»»» categoryCode|body|string|false|No description
»»» categoryName|body|string|false|No description
»»» destinationCode|body|string|false|No description
»»» destinationName|body|string|false|No description
»»» zoneCode|body|integer(int32)|false|No description
»»» zoneName|body|string|false|No description
»»» latitude|body|string|false|No description
»»» longitude|body|string|false|No description
»»» giata|body|string|false|No description
»»» minRate|body|number|false|No description
»»» maxRate|body|number|false|No description
»»» totalSellingRate|body|number|false|No description
»»» totalNet|body|number|false|No description
»»» pendingAmount|body|number|false|No description
»»» currency|body|string|false|No description
»»» supplier|body|[ApiSupplier](#schemaapisupplier)|false|No description
»»»» name|body|string|false|No description
»»»» vatNumber|body|string|false|No description
»»» clientComments|body|string|false|No description
»»» cancellationAmount|body|number|false|No description
»»» upselling|body|[ApiUpselling](#schemaapiupselling)|false|No description
»»»» room|body|[[room](#schemaroom)]|false|No description
»»»»» status|body|string|false|No description
»»»»» id|body|integer(int32)|false|No description
»»»»» code|body|string|false|No description
»»»»» name|body|string|false|No description
»»»»» pax|body|[[ApiPax](#schemaapipax)]|false|No description
»»»»»» roomId|body|integer(int32)|false|No description
»»»»»» type|body|string|true|No description
»»»»»» age|body|integer(int32)|false|No description
»»»»»» name|body|string|false|No description
»»»»»» surname|body|string|false|No description
»»»»» rate|body|[[ApiRate](#schemaapirate)]|false|No description
»»»»»» rateKey|body|string|false|No description
»»»»»» rateClass|body|string|false|No description
»»»»»» rateType|body|string|false|No description
»»»»»» net|body|number|false|No description
»»»»»» discount|body|number|false|No description
»»»»»» discountPCT|body|number|false|No description
»»»»»» sellingRate|body|number|false|No description
»»»»»» hotelSellingRate|body|number|false|No description
»»»»»» amount|body|number|false|No description
»»»»»» hotelCurrency|body|string|false|No description
»»»»»» hotelMandatory|body|boolean|false|No description
»»»»»» allotment|body|integer(int32)|false|No description
»»»»»» commission|body|number|false|No description
»»»»»» commissionVAT|body|number|false|No description
»»»»»» commissionPCT|body|number|false|No description
»»»»»» cost|body|[ApiCost](#schemaapicost)|false|No description
»»»»»»» amount|body|number|false|No description
»»»»»»» currency|body|string|false|No description
»»»»»» rateCommentsId|body|string|false|No description
»»»»»» rateComments|body|string|false|No description
»»»»»» paymentType|body|string|false|No description
»»»»»» packaging|body|boolean|false|No description
»»»»»» boardCode|body|string|false|No description
»»»»»» boardName|body|string|false|No description
»»»»»» rateBreakDown|body|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»»»»» rateDiscount|body|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»»»»» code|body|string|false|No description
»»»»»»»» name|body|string|false|No description
»»»»»»»» amount|body|number|false|No description
»»»»»»» rateSupplement|body|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»»»»» code|body|string|false|No description
»»»»»»»» name|body|string|false|No description
»»»»»»»» from|body|string(date)|false|No description
»»»»»»»» to|body|string(date)|false|No description
»»»»»»»» amount|body|number|false|No description
»»»»»»»» nights|body|integer(int32)|false|No description
»»»»»»»» paxNumber|body|integer(int32)|false|No description
»»»»»» rooms|body|integer(int32)|false|No description
»»»»»» adults|body|integer(int32)|false|No description
»»»»»» children|body|integer(int32)|false|No description
»»»»»» childrenAges|body|string|false|No description
»»»»»» rateup|body|number|false|No description
»»»»»» taxes|body|[ApiTaxes](#schemaapitaxes)|false|No description
»»»»»»» allIncluded|body|boolean|false|No description
»»»»»»» tax|body|[[ApiTax](#schemaapitax)]|false|No description
»»»»»»»» included|body|boolean|false|No description
»»»»»»»» percent|body|number|false|No description
»»»»»»»» amount|body|number|false|No description
»»»»»»»» currency|body|string|false|No description
»»»»»»»» type|body|string|false|No description
»»»»»»»» clientAmount|body|number|false|No description
»»»»»»»» clientCurrency|body|string|false|No description
»»»»»» comment|body|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»»»»» type|body|string|false|No description
»»»»»»» text|body|string|false|No description
»»»»»» cancellationPolicy|body|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»»»»» amount|body|number|false|No description
»»»»»»» hotelAmount|body|number|false|No description
»»»»»»» hotelCurrency|body|string|false|No description
»»»»»»» from|body|string|false|No description
»»»»»» promotion|body|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»»»»» code|body|string|false|No description
»»»»»»» name|body|string|false|No description
»»»»»»» remark|body|string|false|No description
»»»»»» offer|body|[[ApiOffer](#schemaapioffer)]|false|No description
»»»»»»» code|body|string|false|No description
»»»»»»» name|body|string|false|No description
»»»»»»» amount|body|number|false|No description
»»»»»» shiftRate|body|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»»»»» rateKey|body|string|false|No description
»»»»»»» rateClass|body|string|false|No description
»»»»»»» rateType|body|string|false|No description
»»»»»»» net|body|number|false|No description
»»»»»»» discount|body|number|false|No description
»»»»»»» discountPCT|body|number|false|No description
»»»»»»» sellingRate|body|number|false|No description
»»»»»»» hotelSellingRate|body|number|false|No description
»»»»»»» amount|body|number|false|No description
»»»»»»» hotelCurrency|body|string|false|No description
»»»»»»» hotelMandatory|body|boolean|false|No description
»»»»»»» allotment|body|integer(int32)|false|No description
»»»»»»» commission|body|number|false|No description
»»»»»»» commissionVAT|body|number|false|No description
»»»»»»» commissionPCT|body|number|false|No description
»»»»»»» cost|body|[ApiCost](#schemaapicost)|false|No description
»»»»»»»» amount|body|number|false|No description
»»»»»»»» currency|body|string|false|No description
»»»»»»» checkIn|body|string(date)|false|No description
»»»»»»» checkOut|body|string(date)|false|No description
»»»»»» dailyRate|body|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»»»»» offset|body|integer(int32)|false|No description
»»»»»»» dailyNet|body|number|false|No description
»»»»»»» dailySellingRate|body|number|false|No description
»»» keyword|body|[[ApiKeyword](#schemaapikeyword)]|false|No description
»»»» code|body|integer(int32)|true|No description
»»»» rating|body|integer(int32)|false|No description
»»» review|body|[[ApiReview](#schemaapireview)]|false|No description
»»»» rate|body|number|false|No description
»»»» reviewCount|body|integer(int32)|false|No description
»»»» type|body|string|false|No description
»»» room|body|[[room](#schemaroom)]|false|No description
»»»» status|body|string|false|No description
»»»» id|body|integer(int32)|false|No description
»»»» code|body|string|false|No description
»»»» name|body|string|false|No description
»»»» pax|body|[[ApiPax](#schemaapipax)]|false|No description
»»»»» roomId|body|integer(int32)|false|No description
»»»»» type|body|string|true|No description
»»»»» age|body|integer(int32)|false|No description
»»»»» name|body|string|false|No description
»»»»» surname|body|string|false|No description
»»»» rate|body|[[ApiRate](#schemaapirate)]|false|No description
»»»»» rateKey|body|string|false|No description
»»»»» rateClass|body|string|false|No description
»»»»» rateType|body|string|false|No description
»»»»» net|body|number|false|No description
»»»»» discount|body|number|false|No description
»»»»» discountPCT|body|number|false|No description
»»»»» sellingRate|body|number|false|No description
»»»»» hotelSellingRate|body|number|false|No description
»»»»» amount|body|number|false|No description
»»»»» hotelCurrency|body|string|false|No description
»»»»» hotelMandatory|body|boolean|false|No description
»»»»» allotment|body|integer(int32)|false|No description
»»»»» commission|body|number|false|No description
»»»»» commissionVAT|body|number|false|No description
»»»»» commissionPCT|body|number|false|No description
»»»»» cost|body|[ApiCost](#schemaapicost)|false|No description
»»»»»» amount|body|number|false|No description
»»»»»» currency|body|string|false|No description
»»»»» rateCommentsId|body|string|false|No description
»»»»» rateComments|body|string|false|No description
»»»»» paymentType|body|string|false|No description
»»»»» packaging|body|boolean|false|No description
»»»»» boardCode|body|string|false|No description
»»»»» boardName|body|string|false|No description
»»»»» rateBreakDown|body|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»»»» rateDiscount|body|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»»»» code|body|string|false|No description
»»»»»»» name|body|string|false|No description
»»»»»»» amount|body|number|false|No description
»»»»»» rateSupplement|body|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»»»» code|body|string|false|No description
»»»»»»» name|body|string|false|No description
»»»»»»» from|body|string(date)|false|No description
»»»»»»» to|body|string(date)|false|No description
»»»»»»» amount|body|number|false|No description
»»»»»»» nights|body|integer(int32)|false|No description
»»»»»»» paxNumber|body|integer(int32)|false|No description
»»»»» rooms|body|integer(int32)|false|No description
»»»»» adults|body|integer(int32)|false|No description
»»»»» children|body|integer(int32)|false|No description
»»»»» childrenAges|body|string|false|No description
»»»»» rateup|body|number|false|No description
»»»»» taxes|body|[ApiTaxes](#schemaapitaxes)|false|No description
»»»»»» allIncluded|body|boolean|false|No description
»»»»»» tax|body|[[ApiTax](#schemaapitax)]|false|No description
»»»»»»» included|body|boolean|false|No description
»»»»»»» percent|body|number|false|No description
»»»»»»» amount|body|number|false|No description
»»»»»»» currency|body|string|false|No description
»»»»»»» type|body|string|false|No description
»»»»»»» clientAmount|body|number|false|No description
»»»»»»» clientCurrency|body|string|false|No description
»»»»» comment|body|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»»»» type|body|string|false|No description
»»»»»» text|body|string|false|No description
»»»»» cancellationPolicy|body|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»»»» amount|body|number|false|No description
»»»»»» hotelAmount|body|number|false|No description
»»»»»» hotelCurrency|body|string|false|No description
»»»»»» from|body|string|false|No description
»»»»» promotion|body|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»»»» code|body|string|false|No description
»»»»»» name|body|string|false|No description
»»»»»» remark|body|string|false|No description
»»»»» offer|body|[[ApiOffer](#schemaapioffer)]|false|No description
»»»»»» code|body|string|false|No description
»»»»»» name|body|string|false|No description
»»»»»» amount|body|number|false|No description
»»»»» shiftRate|body|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»»»» rateKey|body|string|false|No description
»»»»»» rateClass|body|string|false|No description
»»»»»» rateType|body|string|false|No description
»»»»»» net|body|number|false|No description
»»»»»» discount|body|number|false|No description
»»»»»» discountPCT|body|number|false|No description
»»»»»» sellingRate|body|number|false|No description
»»»»»» hotelSellingRate|body|number|false|No description
»»»»»» amount|body|number|false|No description
»»»»»» hotelCurrency|body|string|false|No description
»»»»»» hotelMandatory|body|boolean|false|No description
»»»»»» allotment|body|integer(int32)|false|No description
»»»»»» commission|body|number|false|No description
»»»»»» commissionVAT|body|number|false|No description
»»»»»» commissionPCT|body|number|false|No description
»»»»»» cost|body|[ApiCost](#schemaapicost)|false|No description
»»»»»»» amount|body|number|false|No description
»»»»»»» currency|body|string|false|No description
»»»»»» checkIn|body|string(date)|false|No description
»»»»»» checkOut|body|string(date)|false|No description
»»»»» dailyRate|body|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»»»» offset|body|integer(int32)|false|No description
»»»»»» dailyNet|body|number|false|No description
»»»»»» dailySellingRate|body|number|false|No description
»»» creditCard|body|[[ApiCreditCard](#schemaapicreditcard)]|false|No description
»»»» code|body|string|false|No description
»»»» name|body|string|false|No description
»»»» paymentType|body|string|false|No description


#### Enumerated Values

|Parameter|Value|
|---|---|
version|1.0|
version|1.1|
version|1.2|
» mode|SIMULATION|
» mode|UPDATE|
»» status|NEW|
»» status|PRECONFIRMED|
»» status|CONFIRMED|
»» status|TO_BE_UPDATED|
»» status|CANCELLED|
»» status|TO_BE_CANCELLED|
»»»»» status|NEW|
»»»»» status|PRECONFIRMED|
»»»»» status|CONFIRMED|
»»»»» status|TO_BE_UPDATED|
»»»»» status|CANCELLED|
»»»»» status|TO_BE_CANCELLED|
»»»»»» type|AD|
»»»»»» type|CH|
»»»»»» rateType|BOOKABLE|
»»»»»» rateType|RECHECK|
»»»»»» paymentType|AT_HOTEL|
»»»»»» paymentType|AT_WEB|
»»»»»»»» type|TAX|
»»»»»»»» type|FEE|
»»»»»»» rateType|BOOKABLE|
»»»»»»» rateType|RECHECK|
»»»» status|NEW|
»»»» status|PRECONFIRMED|
»»»» status|CONFIRMED|
»»»» status|TO_BE_UPDATED|
»»»» status|CANCELLED|
»»»» status|TO_BE_CANCELLED|
»»»»» type|AD|
»»»»» type|CH|
»»»»» rateType|BOOKABLE|
»»»»» rateType|RECHECK|
»»»»» paymentType|AT_HOTEL|
»»»»» paymentType|AT_WEB|
»»»»»»» type|TAX|
»»»»»»» type|FEE|
»»»»»» rateType|BOOKABLE|
»»»»»» rateType|RECHECK|
»»»» paymentType|AT_HOTEL|
»»»» paymentType|AT_WEB|

> Example responses

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<bookingChangeRS>
  <echoToken>string</echoToken>
  <auditData>
    <processTime>string</processTime>
    <timestamp>string</timestamp>
    <requestHost>string</requestHost>
    <serverId>string</serverId>
    <environment>string</environment>
    <release>string</release>
    <token>string</token>
  </auditData>
  <error>
    <code>string</code>
    <message>string</message>
  </error>
  <booking>
    <reference>string</reference>
    <cancellationReference>string</cancellationReference>
    <clientReference>string</clientReference>
    <creationDate>2017-10-21</creationDate>
    <status>NEW</status>
    <modificationPolicies>
      <cancellation>false</cancellation>
      <modification>false</modification>
    </modificationPolicies>
    <agCommision>0</agCommision>
    <commisionVAT>0</commisionVAT>
    <creationUser>string</creationUser>
    <holder>
      <name>string</name>
      <surname>string</surname>
    </holder>
    <remark>string</remark>
    <totalSellingRate>0</totalSellingRate>
    <totalNet>0</totalNet>
    <pendingAmount>0</pendingAmount>
    <currency>string</currency>
    <hotel>
      <checkOut>2017-10-21</checkOut>
      <checkIn>2017-10-21</checkIn>
      <code>0</code>
      <name>string</name>
      <description>string</description>
      <image>string</image>
      <categoryCode>string</categoryCode>
      <categoryName>string</categoryName>
      <destinationCode>string</destinationCode>
      <destinationName>string</destinationName>
      <zoneCode>0</zoneCode>
      <zoneName>string</zoneName>
      <latitude>string</latitude>
      <longitude>string</longitude>
      <giata>string</giata>
      <minRate>0</minRate>
      <maxRate>0</maxRate>
      <totalSellingRate>0</totalSellingRate>
      <totalNet>0</totalNet>
      <pendingAmount>0</pendingAmount>
      <currency>string</currency>
      <supplier>
        <name>string</name>
        <vatNumber>string</vatNumber>
      </supplier>
      <clientComments>string</clientComments>
      <cancellationAmount>0</cancellationAmount>
      <upselling>
        <room>
          <status>NEW</status>
          <id>0</id>
          <code>string</code>
          <name>string</name>
          <pax>
            <roomId>1</roomId>
            <type>AD</type>
            <age>20</age>
            <name>string</name>
            <surname>string</surname>
          </pax>
          <rate>
            <rateKey>string</rateKey>
            <rateClass>string</rateClass>
            <rateType>BOOKABLE</rateType>
            <net>0</net>
            <discount>0</discount>
            <discountPCT>0</discountPCT>
            <sellingRate>0</sellingRate>
            <hotelSellingRate>0</hotelSellingRate>
            <amount>0</amount>
            <hotelCurrency>string</hotelCurrency>
            <hotelMandatory>false</hotelMandatory>
            <allotment>0</allotment>
            <commission>0</commission>
            <commissionVAT>0</commissionVAT>
            <commissionPCT>0</commissionPCT>
            <cost>
              <amount>0</amount>
              <currency>string</currency>
            </cost>
            <rateCommentsId>string</rateCommentsId>
            <rateComments>string</rateComments>
            <paymentType>AT_HOTEL</paymentType>
            <packaging>false</packaging>
            <boardCode>string</boardCode>
            <boardName>string</boardName>
            <rateBreakDown>
              <rateDiscount>
                <code>string</code>
                <name>string</name>
                <amount>0</amount>
              </rateDiscount>
              <rateSupplement>
                <code>string</code>
                <name>string</name>
                <from>2017-10-21</from>
                <to>2017-10-21</to>
                <amount>0</amount>
                <nights>0</nights>
                <paxNumber>0</paxNumber>
              </rateSupplement>
            </rateBreakDown>
            <rooms>0</rooms>
            <adults>0</adults>
            <children>0</children>
            <childrenAges>string</childrenAges>
            <rateup>0</rateup>
            <comment>
              <type>string</type>
              <text>string</text>
            </comment>
            <cancellationPolicy>
              <amount>0</amount>
              <hotelAmount>0</hotelAmount>
              <hotelCurrency>string</hotelCurrency>
              <from>string</from>
            </cancellationPolicy>
            <taxes>
              <allIncluded>false</allIncluded>
              <tax>
                <included>false</included>
                <percent>0</percent>
                <amount>0</amount>
                <currency>string</currency>
                <type>TAX</type>
                <clientAmount>0</clientAmount>
                <clientCurrency>string</clientCurrency>
              </tax>
            </taxes>
            <promotion>
              <code>string</code>
              <name>string</name>
              <remark>string</remark>
            </promotion>
            <offer>
              <code>string</code>
              <name>string</name>
              <amount>0</amount>
            </offer>
            <shiftRate>
              <rateKey>string</rateKey>
              <rateClass>string</rateClass>
              <rateType>BOOKABLE</rateType>
              <net>0</net>
              <discount>0</discount>
              <discountPCT>0</discountPCT>
              <sellingRate>0</sellingRate>
              <hotelSellingRate>0</hotelSellingRate>
              <amount>0</amount>
              <hotelCurrency>string</hotelCurrency>
              <hotelMandatory>false</hotelMandatory>
              <allotment>0</allotment>
              <commission>0</commission>
              <commissionVAT>0</commissionVAT>
              <commissionPCT>0</commissionPCT>
              <cost>
                <amount>0</amount>
                <currency>string</currency>
              </cost>
              <checkIn>2017-10-21</checkIn>
              <checkOut>2017-10-21</checkOut>
            </shiftRate>
            <dailyRate>
              <offset>0</offset>
              <dailyNet>0</dailyNet>
              <dailySellingRate>0</dailySellingRate>
            </dailyRate>
          </rate>
        </room>
      </upselling>
      <keyword>
        <code>0</code>
        <rating>0</rating>
      </keyword>
      <review>
        <rate>0</rate>
        <reviewCount>0</reviewCount>
        <type>string</type>
      </review>
      <room>
        <status>NEW</status>
        <id>0</id>
        <code>string</code>
        <name>string</name>
        <pax>
          <roomId>1</roomId>
          <type>AD</type>
          <age>20</age>
          <name>string</name>
          <surname>string</surname>
        </pax>
        <rate>
          <rateKey>string</rateKey>
          <rateClass>string</rateClass>
          <rateType>BOOKABLE</rateType>
          <net>0</net>
          <discount>0</discount>
          <discountPCT>0</discountPCT>
          <sellingRate>0</sellingRate>
          <hotelSellingRate>0</hotelSellingRate>
          <amount>0</amount>
          <hotelCurrency>string</hotelCurrency>
          <hotelMandatory>false</hotelMandatory>
          <allotment>0</allotment>
          <commission>0</commission>
          <commissionVAT>0</commissionVAT>
          <commissionPCT>0</commissionPCT>
          <cost>
            <amount>0</amount>
            <currency>string</currency>
          </cost>
          <rateCommentsId>string</rateCommentsId>
          <rateComments>string</rateComments>
          <paymentType>AT_HOTEL</paymentType>
          <packaging>false</packaging>
          <boardCode>string</boardCode>
          <boardName>string</boardName>
          <rateBreakDown>
            <rateDiscount>
              <code>string</code>
              <name>string</name>
              <amount>0</amount>
            </rateDiscount>
            <rateSupplement>
              <code>string</code>
              <name>string</name>
              <from>2017-10-21</from>
              <to>2017-10-21</to>
              <amount>0</amount>
              <nights>0</nights>
              <paxNumber>0</paxNumber>
            </rateSupplement>
          </rateBreakDown>
          <rooms>0</rooms>
          <adults>0</adults>
          <children>0</children>
          <childrenAges>string</childrenAges>
          <rateup>0</rateup>
          <comment>
            <type>string</type>
            <text>string</text>
          </comment>
          <cancellationPolicy>
            <amount>0</amount>
            <hotelAmount>0</hotelAmount>
            <hotelCurrency>string</hotelCurrency>
            <from>string</from>
          </cancellationPolicy>
          <taxes>
            <allIncluded>false</allIncluded>
            <tax>
              <included>false</included>
              <percent>0</percent>
              <amount>0</amount>
              <currency>string</currency>
              <type>TAX</type>
              <clientAmount>0</clientAmount>
              <clientCurrency>string</clientCurrency>
            </tax>
          </taxes>
          <promotion>
            <code>string</code>
            <name>string</name>
            <remark>string</remark>
          </promotion>
          <offer>
            <code>string</code>
            <name>string</name>
            <amount>0</amount>
          </offer>
          <shiftRate>
            <rateKey>string</rateKey>
            <rateClass>string</rateClass>
            <rateType>BOOKABLE</rateType>
            <net>0</net>
            <discount>0</discount>
            <discountPCT>0</discountPCT>
            <sellingRate>0</sellingRate>
            <hotelSellingRate>0</hotelSellingRate>
            <amount>0</amount>
            <hotelCurrency>string</hotelCurrency>
            <hotelMandatory>false</hotelMandatory>
            <allotment>0</allotment>
            <commission>0</commission>
            <commissionVAT>0</commissionVAT>
            <commissionPCT>0</commissionPCT>
            <cost>
              <amount>0</amount>
              <currency>string</currency>
            </cost>
            <checkIn>2017-10-21</checkIn>
            <checkOut>2017-10-21</checkOut>
          </shiftRate>
          <dailyRate>
            <offset>0</offset>
            <dailyNet>0</dailyNet>
            <dailySellingRate>0</dailySellingRate>
          </dailyRate>
        </rate>
      </room>
      <creditCard>
        <code>string</code>
        <name>string</name>
        <paymentType>AT_HOTEL</paymentType>
      </creditCard>
    </hotel>
  </booking>
</bookingChangeRS>
```
```json
{
  "echoToken": "string",
  "auditData": {
    "processTime": "string",
    "timestamp": "string",
    "requestHost": "string",
    "serverId": "string",
    "environment": "string",
    "release": "string",
    "token": "string"
  },
  "error": {
    "code": "string",
    "message": "string"
  },
  "booking": {
    "reference": "string",
    "cancellationReference": "string",
    "clientReference": "string",
    "creationDate": "2017-10-21",
    "status": "NEW",
    "modificationPolicies": {
      "cancellation": false,
      "modification": false
    },
    "agCommision": 0,
    "commisionVAT": 0,
    "creationUser": "string",
    "holder": {
      "name": "string",
      "surname": "string"
    },
    "remark": "string",
    "totalSellingRate": 0,
    "totalNet": 0,
    "pendingAmount": 0,
    "currency": "string",
    "hotel": {
      "checkOut": "2017-10-21",
      "checkIn": "2017-10-21",
      "code": 0,
      "name": "string",
      "description": "string",
      "image": "string",
      "categoryCode": "string",
      "categoryName": "string",
      "destinationCode": "string",
      "destinationName": "string",
      "zoneCode": 0,
      "zoneName": "string",
      "latitude": "string",
      "longitude": "string",
      "giata": "string",
      "minRate": 0,
      "maxRate": 0,
      "totalSellingRate": 0,
      "totalNet": 0,
      "pendingAmount": 0,
      "currency": "string",
      "supplier": {
        "name": "string",
        "vatNumber": "string"
      },
      "clientComments": "string",
      "cancellationAmount": 0,
      "upselling": {
        "room": [
          {
            "status": "NEW",
            "id": 0,
            "code": "string",
            "name": "string",
            "pax": [
              {
                "roomId": 1,
                "type": "AD",
                "age": 20,
                "name": "string",
                "surname": "string"
              }
            ],
            "rate": [
              {
                "rateKey": "string",
                "rateClass": "string",
                "rateType": "BOOKABLE",
                "net": 0,
                "discount": 0,
                "discountPCT": 0,
                "sellingRate": 0,
                "hotelSellingRate": 0,
                "amount": 0,
                "hotelCurrency": "string",
                "hotelMandatory": false,
                "allotment": 0,
                "commission": 0,
                "commissionVAT": 0,
                "commissionPCT": 0,
                "cost": {
                  "amount": 0,
                  "currency": "string"
                },
                "rateCommentsId": "string",
                "rateComments": "string",
                "paymentType": "AT_HOTEL",
                "packaging": false,
                "boardCode": "string",
                "boardName": "string",
                "rateBreakDown": {
                  "rateDiscount": [
                    {
                      "code": "string",
                      "name": "string",
                      "amount": 0
                    }
                  ],
                  "rateSupplement": [
                    {
                      "code": "string",
                      "name": "string",
                      "from": "2017-10-21",
                      "to": "2017-10-21",
                      "amount": 0,
                      "nights": 0,
                      "paxNumber": 0
                    }
                  ]
                },
                "rooms": 0,
                "adults": 0,
                "children": 0,
                "childrenAges": "string",
                "rateup": 0,
                "comment": [
                  {
                    "type": "string",
                    "text": "string"
                  }
                ],
                "cancellationPolicy": [
                  {
                    "amount": 0,
                    "hotelAmount": 0,
                    "hotelCurrency": "string",
                    "from": "string"
                  }
                ],
                "taxes": {
                  "allIncluded": false,
                  "tax": [
                    {
                      "included": false,
                      "percent": 0,
                      "amount": 0,
                      "currency": "string",
                      "type": "TAX",
                      "clientAmount": 0,
                      "clientCurrency": "string"
                    }
                  ]
                },
                "promotion": [
                  {
                    "code": "string",
                    "name": "string",
                    "remark": "string"
                  }
                ],
                "offer": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "shiftRate": [
                  {
                    "rateKey": "string",
                    "rateClass": "string",
                    "rateType": "BOOKABLE",
                    "net": 0,
                    "discount": 0,
                    "discountPCT": 0,
                    "sellingRate": 0,
                    "hotelSellingRate": 0,
                    "amount": 0,
                    "hotelCurrency": "string",
                    "hotelMandatory": false,
                    "allotment": 0,
                    "commission": 0,
                    "commissionVAT": 0,
                    "commissionPCT": 0,
                    "cost": {
                      "amount": 0,
                      "currency": "string"
                    },
                    "checkIn": "2017-10-21",
                    "checkOut": "2017-10-21"
                  }
                ],
                "dailyRate": [
                  {
                    "offset": 0,
                    "dailyNet": 0,
                    "dailySellingRate": 0
                  }
                ]
              }
            ]
          }
        ]
      },
      "keyword": [
        {
          "code": 0,
          "rating": 0
        }
      ],
      "review": [
        {
          "rate": 0,
          "reviewCount": 0,
          "type": "string"
        }
      ],
      "room": [
        {
          "status": "NEW",
          "id": 0,
          "code": "string",
          "name": "string",
          "pax": [
            {
              "roomId": 1,
              "type": "AD",
              "age": 20,
              "name": "string",
              "surname": "string"
            }
          ],
          "rate": [
            {
              "rateKey": "string",
              "rateClass": "string",
              "rateType": "BOOKABLE",
              "net": 0,
              "discount": 0,
              "discountPCT": 0,
              "sellingRate": 0,
              "hotelSellingRate": 0,
              "amount": 0,
              "hotelCurrency": "string",
              "hotelMandatory": false,
              "allotment": 0,
              "commission": 0,
              "commissionVAT": 0,
              "commissionPCT": 0,
              "cost": {
                "amount": 0,
                "currency": "string"
              },
              "rateCommentsId": "string",
              "rateComments": "string",
              "paymentType": "AT_HOTEL",
              "packaging": false,
              "boardCode": "string",
              "boardName": "string",
              "rateBreakDown": {
                "rateDiscount": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "rateSupplement": [
                  {
                    "code": "string",
                    "name": "string",
                    "from": "2017-10-21",
                    "to": "2017-10-21",
                    "amount": 0,
                    "nights": 0,
                    "paxNumber": 0
                  }
                ]
              },
              "rooms": 0,
              "adults": 0,
              "children": 0,
              "childrenAges": "string",
              "rateup": 0,
              "comment": [
                {
                  "type": "string",
                  "text": "string"
                }
              ],
              "cancellationPolicy": [
                {
                  "amount": 0,
                  "hotelAmount": 0,
                  "hotelCurrency": "string",
                  "from": "string"
                }
              ],
              "taxes": {
                "allIncluded": false,
                "tax": [
                  {
                    "included": false,
                    "percent": 0,
                    "amount": 0,
                    "currency": "string",
                    "type": "TAX",
                    "clientAmount": 0,
                    "clientCurrency": "string"
                  }
                ]
              },
              "promotion": [
                {
                  "code": "string",
                  "name": "string",
                  "remark": "string"
                }
              ],
              "offer": [
                {
                  "code": "string",
                  "name": "string",
                  "amount": 0
                }
              ],
              "shiftRate": [
                {
                  "rateKey": "string",
                  "rateClass": "string",
                  "rateType": "BOOKABLE",
                  "net": 0,
                  "discount": 0,
                  "discountPCT": 0,
                  "sellingRate": 0,
                  "hotelSellingRate": 0,
                  "amount": 0,
                  "hotelCurrency": "string",
                  "hotelMandatory": false,
                  "allotment": 0,
                  "commission": 0,
                  "commissionVAT": 0,
                  "commissionPCT": 0,
                  "cost": {
                    "amount": 0,
                    "currency": "string"
                  },
                  "checkIn": "2017-10-21",
                  "checkOut": "2017-10-21"
                }
              ],
              "dailyRate": [
                {
                  "offset": 0,
                  "dailyNet": 0,
                  "dailySellingRate": 0
                }
              ]
            }
          ]
        }
      ],
      "creditCard": [
        {
          "code": "string",
          "name": "string",
          "paymentType": "AT_HOTEL"
        }
      ]
    }
  }
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Sample|[bookingChangeRS](#schemabookingchangers)
500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Unexpected error|None

<aside class="success">
This operation does not require authentication
</aside>

## bookingCancellation

> Code samples

```shell
# You can also use wget
curl -X DELETE https://api.test.hotelbeds.com/hotel-api/{version}/bookings/{bookingId} \
  -H 'Accept: application/xml'

```

```http
DELETE https://api.test.hotelbeds.com/hotel-api/{version}/bookings/{bookingId} HTTP/1.1
Host: api.test.hotelbeds.com

Accept: application/xml

```

```javascript
var headers = {
  'Accept':'application/xml'

};

$.ajax({
  url: 'https://api.test.hotelbeds.com/hotel-api/{version}/bookings/{bookingId}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/xml'

};

fetch('https://api.test.hotelbeds.com/hotel-api/{version}/bookings/{bookingId}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/xml'
}

result = RestClient.delete 'https://api.test.hotelbeds.com/hotel-api/{version}/bookings/{bookingId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/xml'
}

r = requests.delete('https://api.test.hotelbeds.com/hotel-api/{version}/bookings/{bookingId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://api.test.hotelbeds.com/hotel-api/{version}/bookings/{bookingId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`DELETE /{version}/bookings/{bookingId}`

*Booking cancellation*

Description.....

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
version|path|string|true|Specification version
bookingId|path|string|true|No description
cancellationFlag|query|string|false|No description
language|query|string|false|No description


#### Enumerated Values

|Parameter|Value|
|---|---|
version|1.0|
version|1.1|
version|1.2|
cancellationFlag|CANCELLATION|
cancellationFlag|SIMULATION|

> Example responses

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<bookingCancellationRS>
  <echoToken>string</echoToken>
  <auditData>
    <processTime>string</processTime>
    <timestamp>string</timestamp>
    <requestHost>string</requestHost>
    <serverId>string</serverId>
    <environment>string</environment>
    <release>string</release>
    <token>string</token>
  </auditData>
  <error>
    <code>string</code>
    <message>string</message>
  </error>
  <booking>
    <reference>string</reference>
    <cancellationReference>string</cancellationReference>
    <clientReference>string</clientReference>
    <creationDate>2017-10-21</creationDate>
    <status>NEW</status>
    <modificationPolicies>
      <cancellation>false</cancellation>
      <modification>false</modification>
    </modificationPolicies>
    <agCommision>0</agCommision>
    <commisionVAT>0</commisionVAT>
    <creationUser>string</creationUser>
    <holder>
      <name>string</name>
      <surname>string</surname>
    </holder>
    <remark>string</remark>
    <totalSellingRate>0</totalSellingRate>
    <totalNet>0</totalNet>
    <pendingAmount>0</pendingAmount>
    <currency>string</currency>
    <hotel>
      <checkOut>2017-10-21</checkOut>
      <checkIn>2017-10-21</checkIn>
      <code>0</code>
      <name>string</name>
      <description>string</description>
      <image>string</image>
      <categoryCode>string</categoryCode>
      <categoryName>string</categoryName>
      <destinationCode>string</destinationCode>
      <destinationName>string</destinationName>
      <zoneCode>0</zoneCode>
      <zoneName>string</zoneName>
      <latitude>string</latitude>
      <longitude>string</longitude>
      <giata>string</giata>
      <minRate>0</minRate>
      <maxRate>0</maxRate>
      <totalSellingRate>0</totalSellingRate>
      <totalNet>0</totalNet>
      <pendingAmount>0</pendingAmount>
      <currency>string</currency>
      <supplier>
        <name>string</name>
        <vatNumber>string</vatNumber>
      </supplier>
      <clientComments>string</clientComments>
      <cancellationAmount>0</cancellationAmount>
      <upselling>
        <room>
          <status>NEW</status>
          <id>0</id>
          <code>string</code>
          <name>string</name>
          <pax>
            <roomId>1</roomId>
            <type>AD</type>
            <age>20</age>
            <name>string</name>
            <surname>string</surname>
          </pax>
          <rate>
            <rateKey>string</rateKey>
            <rateClass>string</rateClass>
            <rateType>BOOKABLE</rateType>
            <net>0</net>
            <discount>0</discount>
            <discountPCT>0</discountPCT>
            <sellingRate>0</sellingRate>
            <hotelSellingRate>0</hotelSellingRate>
            <amount>0</amount>
            <hotelCurrency>string</hotelCurrency>
            <hotelMandatory>false</hotelMandatory>
            <allotment>0</allotment>
            <commission>0</commission>
            <commissionVAT>0</commissionVAT>
            <commissionPCT>0</commissionPCT>
            <cost>
              <amount>0</amount>
              <currency>string</currency>
            </cost>
            <rateCommentsId>string</rateCommentsId>
            <rateComments>string</rateComments>
            <paymentType>AT_HOTEL</paymentType>
            <packaging>false</packaging>
            <boardCode>string</boardCode>
            <boardName>string</boardName>
            <rateBreakDown>
              <rateDiscount>
                <code>string</code>
                <name>string</name>
                <amount>0</amount>
              </rateDiscount>
              <rateSupplement>
                <code>string</code>
                <name>string</name>
                <from>2017-10-21</from>
                <to>2017-10-21</to>
                <amount>0</amount>
                <nights>0</nights>
                <paxNumber>0</paxNumber>
              </rateSupplement>
            </rateBreakDown>
            <rooms>0</rooms>
            <adults>0</adults>
            <children>0</children>
            <childrenAges>string</childrenAges>
            <rateup>0</rateup>
            <comment>
              <type>string</type>
              <text>string</text>
            </comment>
            <cancellationPolicy>
              <amount>0</amount>
              <hotelAmount>0</hotelAmount>
              <hotelCurrency>string</hotelCurrency>
              <from>string</from>
            </cancellationPolicy>
            <taxes>
              <allIncluded>false</allIncluded>
              <tax>
                <included>false</included>
                <percent>0</percent>
                <amount>0</amount>
                <currency>string</currency>
                <type>TAX</type>
                <clientAmount>0</clientAmount>
                <clientCurrency>string</clientCurrency>
              </tax>
            </taxes>
            <promotion>
              <code>string</code>
              <name>string</name>
              <remark>string</remark>
            </promotion>
            <offer>
              <code>string</code>
              <name>string</name>
              <amount>0</amount>
            </offer>
            <shiftRate>
              <rateKey>string</rateKey>
              <rateClass>string</rateClass>
              <rateType>BOOKABLE</rateType>
              <net>0</net>
              <discount>0</discount>
              <discountPCT>0</discountPCT>
              <sellingRate>0</sellingRate>
              <hotelSellingRate>0</hotelSellingRate>
              <amount>0</amount>
              <hotelCurrency>string</hotelCurrency>
              <hotelMandatory>false</hotelMandatory>
              <allotment>0</allotment>
              <commission>0</commission>
              <commissionVAT>0</commissionVAT>
              <commissionPCT>0</commissionPCT>
              <cost>
                <amount>0</amount>
                <currency>string</currency>
              </cost>
              <checkIn>2017-10-21</checkIn>
              <checkOut>2017-10-21</checkOut>
            </shiftRate>
            <dailyRate>
              <offset>0</offset>
              <dailyNet>0</dailyNet>
              <dailySellingRate>0</dailySellingRate>
            </dailyRate>
          </rate>
        </room>
      </upselling>
      <keyword>
        <code>0</code>
        <rating>0</rating>
      </keyword>
      <review>
        <rate>0</rate>
        <reviewCount>0</reviewCount>
        <type>string</type>
      </review>
      <room>
        <status>NEW</status>
        <id>0</id>
        <code>string</code>
        <name>string</name>
        <pax>
          <roomId>1</roomId>
          <type>AD</type>
          <age>20</age>
          <name>string</name>
          <surname>string</surname>
        </pax>
        <rate>
          <rateKey>string</rateKey>
          <rateClass>string</rateClass>
          <rateType>BOOKABLE</rateType>
          <net>0</net>
          <discount>0</discount>
          <discountPCT>0</discountPCT>
          <sellingRate>0</sellingRate>
          <hotelSellingRate>0</hotelSellingRate>
          <amount>0</amount>
          <hotelCurrency>string</hotelCurrency>
          <hotelMandatory>false</hotelMandatory>
          <allotment>0</allotment>
          <commission>0</commission>
          <commissionVAT>0</commissionVAT>
          <commissionPCT>0</commissionPCT>
          <cost>
            <amount>0</amount>
            <currency>string</currency>
          </cost>
          <rateCommentsId>string</rateCommentsId>
          <rateComments>string</rateComments>
          <paymentType>AT_HOTEL</paymentType>
          <packaging>false</packaging>
          <boardCode>string</boardCode>
          <boardName>string</boardName>
          <rateBreakDown>
            <rateDiscount>
              <code>string</code>
              <name>string</name>
              <amount>0</amount>
            </rateDiscount>
            <rateSupplement>
              <code>string</code>
              <name>string</name>
              <from>2017-10-21</from>
              <to>2017-10-21</to>
              <amount>0</amount>
              <nights>0</nights>
              <paxNumber>0</paxNumber>
            </rateSupplement>
          </rateBreakDown>
          <rooms>0</rooms>
          <adults>0</adults>
          <children>0</children>
          <childrenAges>string</childrenAges>
          <rateup>0</rateup>
          <comment>
            <type>string</type>
            <text>string</text>
          </comment>
          <cancellationPolicy>
            <amount>0</amount>
            <hotelAmount>0</hotelAmount>
            <hotelCurrency>string</hotelCurrency>
            <from>string</from>
          </cancellationPolicy>
          <taxes>
            <allIncluded>false</allIncluded>
            <tax>
              <included>false</included>
              <percent>0</percent>
              <amount>0</amount>
              <currency>string</currency>
              <type>TAX</type>
              <clientAmount>0</clientAmount>
              <clientCurrency>string</clientCurrency>
            </tax>
          </taxes>
          <promotion>
            <code>string</code>
            <name>string</name>
            <remark>string</remark>
          </promotion>
          <offer>
            <code>string</code>
            <name>string</name>
            <amount>0</amount>
          </offer>
          <shiftRate>
            <rateKey>string</rateKey>
            <rateClass>string</rateClass>
            <rateType>BOOKABLE</rateType>
            <net>0</net>
            <discount>0</discount>
            <discountPCT>0</discountPCT>
            <sellingRate>0</sellingRate>
            <hotelSellingRate>0</hotelSellingRate>
            <amount>0</amount>
            <hotelCurrency>string</hotelCurrency>
            <hotelMandatory>false</hotelMandatory>
            <allotment>0</allotment>
            <commission>0</commission>
            <commissionVAT>0</commissionVAT>
            <commissionPCT>0</commissionPCT>
            <cost>
              <amount>0</amount>
              <currency>string</currency>
            </cost>
            <checkIn>2017-10-21</checkIn>
            <checkOut>2017-10-21</checkOut>
          </shiftRate>
          <dailyRate>
            <offset>0</offset>
            <dailyNet>0</dailyNet>
            <dailySellingRate>0</dailySellingRate>
          </dailyRate>
        </rate>
      </room>
      <creditCard>
        <code>string</code>
        <name>string</name>
        <paymentType>AT_HOTEL</paymentType>
      </creditCard>
    </hotel>
  </booking>
</bookingCancellationRS>
```
```json
{
  "echoToken": "string",
  "auditData": {
    "processTime": "string",
    "timestamp": "string",
    "requestHost": "string",
    "serverId": "string",
    "environment": "string",
    "release": "string",
    "token": "string"
  },
  "error": {
    "code": "string",
    "message": "string"
  },
  "booking": {
    "reference": "string",
    "cancellationReference": "string",
    "clientReference": "string",
    "creationDate": "2017-10-21",
    "status": "NEW",
    "modificationPolicies": {
      "cancellation": false,
      "modification": false
    },
    "agCommision": 0,
    "commisionVAT": 0,
    "creationUser": "string",
    "holder": {
      "name": "string",
      "surname": "string"
    },
    "remark": "string",
    "totalSellingRate": 0,
    "totalNet": 0,
    "pendingAmount": 0,
    "currency": "string",
    "hotel": {
      "checkOut": "2017-10-21",
      "checkIn": "2017-10-21",
      "code": 0,
      "name": "string",
      "description": "string",
      "image": "string",
      "categoryCode": "string",
      "categoryName": "string",
      "destinationCode": "string",
      "destinationName": "string",
      "zoneCode": 0,
      "zoneName": "string",
      "latitude": "string",
      "longitude": "string",
      "giata": "string",
      "minRate": 0,
      "maxRate": 0,
      "totalSellingRate": 0,
      "totalNet": 0,
      "pendingAmount": 0,
      "currency": "string",
      "supplier": {
        "name": "string",
        "vatNumber": "string"
      },
      "clientComments": "string",
      "cancellationAmount": 0,
      "upselling": {
        "room": [
          {
            "status": "NEW",
            "id": 0,
            "code": "string",
            "name": "string",
            "pax": [
              {
                "roomId": 1,
                "type": "AD",
                "age": 20,
                "name": "string",
                "surname": "string"
              }
            ],
            "rate": [
              {
                "rateKey": "string",
                "rateClass": "string",
                "rateType": "BOOKABLE",
                "net": 0,
                "discount": 0,
                "discountPCT": 0,
                "sellingRate": 0,
                "hotelSellingRate": 0,
                "amount": 0,
                "hotelCurrency": "string",
                "hotelMandatory": false,
                "allotment": 0,
                "commission": 0,
                "commissionVAT": 0,
                "commissionPCT": 0,
                "cost": {
                  "amount": 0,
                  "currency": "string"
                },
                "rateCommentsId": "string",
                "rateComments": "string",
                "paymentType": "AT_HOTEL",
                "packaging": false,
                "boardCode": "string",
                "boardName": "string",
                "rateBreakDown": {
                  "rateDiscount": [
                    {
                      "code": "string",
                      "name": "string",
                      "amount": 0
                    }
                  ],
                  "rateSupplement": [
                    {
                      "code": "string",
                      "name": "string",
                      "from": "2017-10-21",
                      "to": "2017-10-21",
                      "amount": 0,
                      "nights": 0,
                      "paxNumber": 0
                    }
                  ]
                },
                "rooms": 0,
                "adults": 0,
                "children": 0,
                "childrenAges": "string",
                "rateup": 0,
                "comment": [
                  {
                    "type": "string",
                    "text": "string"
                  }
                ],
                "cancellationPolicy": [
                  {
                    "amount": 0,
                    "hotelAmount": 0,
                    "hotelCurrency": "string",
                    "from": "string"
                  }
                ],
                "taxes": {
                  "allIncluded": false,
                  "tax": [
                    {
                      "included": false,
                      "percent": 0,
                      "amount": 0,
                      "currency": "string",
                      "type": "TAX",
                      "clientAmount": 0,
                      "clientCurrency": "string"
                    }
                  ]
                },
                "promotion": [
                  {
                    "code": "string",
                    "name": "string",
                    "remark": "string"
                  }
                ],
                "offer": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "shiftRate": [
                  {
                    "rateKey": "string",
                    "rateClass": "string",
                    "rateType": "BOOKABLE",
                    "net": 0,
                    "discount": 0,
                    "discountPCT": 0,
                    "sellingRate": 0,
                    "hotelSellingRate": 0,
                    "amount": 0,
                    "hotelCurrency": "string",
                    "hotelMandatory": false,
                    "allotment": 0,
                    "commission": 0,
                    "commissionVAT": 0,
                    "commissionPCT": 0,
                    "cost": {
                      "amount": 0,
                      "currency": "string"
                    },
                    "checkIn": "2017-10-21",
                    "checkOut": "2017-10-21"
                  }
                ],
                "dailyRate": [
                  {
                    "offset": 0,
                    "dailyNet": 0,
                    "dailySellingRate": 0
                  }
                ]
              }
            ]
          }
        ]
      },
      "keyword": [
        {
          "code": 0,
          "rating": 0
        }
      ],
      "review": [
        {
          "rate": 0,
          "reviewCount": 0,
          "type": "string"
        }
      ],
      "room": [
        {
          "status": "NEW",
          "id": 0,
          "code": "string",
          "name": "string",
          "pax": [
            {
              "roomId": 1,
              "type": "AD",
              "age": 20,
              "name": "string",
              "surname": "string"
            }
          ],
          "rate": [
            {
              "rateKey": "string",
              "rateClass": "string",
              "rateType": "BOOKABLE",
              "net": 0,
              "discount": 0,
              "discountPCT": 0,
              "sellingRate": 0,
              "hotelSellingRate": 0,
              "amount": 0,
              "hotelCurrency": "string",
              "hotelMandatory": false,
              "allotment": 0,
              "commission": 0,
              "commissionVAT": 0,
              "commissionPCT": 0,
              "cost": {
                "amount": 0,
                "currency": "string"
              },
              "rateCommentsId": "string",
              "rateComments": "string",
              "paymentType": "AT_HOTEL",
              "packaging": false,
              "boardCode": "string",
              "boardName": "string",
              "rateBreakDown": {
                "rateDiscount": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "rateSupplement": [
                  {
                    "code": "string",
                    "name": "string",
                    "from": "2017-10-21",
                    "to": "2017-10-21",
                    "amount": 0,
                    "nights": 0,
                    "paxNumber": 0
                  }
                ]
              },
              "rooms": 0,
              "adults": 0,
              "children": 0,
              "childrenAges": "string",
              "rateup": 0,
              "comment": [
                {
                  "type": "string",
                  "text": "string"
                }
              ],
              "cancellationPolicy": [
                {
                  "amount": 0,
                  "hotelAmount": 0,
                  "hotelCurrency": "string",
                  "from": "string"
                }
              ],
              "taxes": {
                "allIncluded": false,
                "tax": [
                  {
                    "included": false,
                    "percent": 0,
                    "amount": 0,
                    "currency": "string",
                    "type": "TAX",
                    "clientAmount": 0,
                    "clientCurrency": "string"
                  }
                ]
              },
              "promotion": [
                {
                  "code": "string",
                  "name": "string",
                  "remark": "string"
                }
              ],
              "offer": [
                {
                  "code": "string",
                  "name": "string",
                  "amount": 0
                }
              ],
              "shiftRate": [
                {
                  "rateKey": "string",
                  "rateClass": "string",
                  "rateType": "BOOKABLE",
                  "net": 0,
                  "discount": 0,
                  "discountPCT": 0,
                  "sellingRate": 0,
                  "hotelSellingRate": 0,
                  "amount": 0,
                  "hotelCurrency": "string",
                  "hotelMandatory": false,
                  "allotment": 0,
                  "commission": 0,
                  "commissionVAT": 0,
                  "commissionPCT": 0,
                  "cost": {
                    "amount": 0,
                    "currency": "string"
                  },
                  "checkIn": "2017-10-21",
                  "checkOut": "2017-10-21"
                }
              ],
              "dailyRate": [
                {
                  "offset": 0,
                  "dailyNet": 0,
                  "dailySellingRate": 0
                }
              ]
            }
          ]
        }
      ],
      "creditCard": [
        {
          "code": "string",
          "name": "string",
          "paymentType": "AT_HOTEL"
        }
      ]
    }
  }
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Sample|[bookingCancellationRS](#schemabookingcancellationrs)
500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Unexpected error|None

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

## ApiAuditData

<a name="schemaapiauditdata"></a>

```json
{
  "processTime": "string",
  "timestamp": "string",
  "requestHost": "string",
  "serverId": "string",
  "environment": "string",
  "release": "string",
  "token": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
processTime|string|false|No description
timestamp|string|false|No description
requestHost|string|false|No description
serverId|string|false|No description
environment|string|false|No description
release|string|false|No description
token|string|false|No description



## ApiBillingAddress

<a name="schemaapibillingaddress"></a>

```json
{
  "address1": "string",
  "address2": "string",
  "city": "string",
  "state": "string",
  "postalCode": "string",
  "countryCode": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
address1|string|false|No description
address2|string|false|No description
city|string|false|No description
state|string|false|No description
postalCode|string|false|No description
countryCode|string|false|No description



## ApiBoards

<a name="schemaapiboards"></a>

```json
{
  "board": [
    "string"
  ],
  "included": false
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
included|boolean|true|No description
board|[string]|false|No description



## ApiBooking

<a name="schemaapibooking"></a>

```json
{
  "reference": "string",
  "cancellationReference": "string",
  "clientReference": "string",
  "creationDate": "2017-10-21",
  "status": "NEW",
  "modificationPolicies": {
    "cancellation": false,
    "modification": false
  },
  "agCommision": 0,
  "commisionVAT": 0,
  "creationUser": "string",
  "holder": {
    "name": "string",
    "surname": "string"
  },
  "remark": "string",
  "totalSellingRate": 0,
  "totalNet": 0,
  "pendingAmount": 0,
  "currency": "string",
  "hotel": {
    "checkOut": "2017-10-21",
    "checkIn": "2017-10-21",
    "code": 0,
    "name": "string",
    "description": "string",
    "image": "string",
    "categoryCode": "string",
    "categoryName": "string",
    "destinationCode": "string",
    "destinationName": "string",
    "zoneCode": 0,
    "zoneName": "string",
    "latitude": "string",
    "longitude": "string",
    "giata": "string",
    "minRate": 0,
    "maxRate": 0,
    "totalSellingRate": 0,
    "totalNet": 0,
    "pendingAmount": 0,
    "currency": "string",
    "supplier": {
      "name": "string",
      "vatNumber": "string"
    },
    "clientComments": "string",
    "cancellationAmount": 0,
    "upselling": {
      "room": [
        {
          "status": "NEW",
          "id": 0,
          "code": "string",
          "name": "string",
          "pax": [
            {
              "roomId": 1,
              "type": "AD",
              "age": 20,
              "name": "string",
              "surname": "string"
            }
          ],
          "rate": [
            {
              "rateKey": "string",
              "rateClass": "string",
              "rateType": "BOOKABLE",
              "net": 0,
              "discount": 0,
              "discountPCT": 0,
              "sellingRate": 0,
              "hotelSellingRate": 0,
              "amount": 0,
              "hotelCurrency": "string",
              "hotelMandatory": false,
              "allotment": 0,
              "commission": 0,
              "commissionVAT": 0,
              "commissionPCT": 0,
              "cost": {
                "amount": 0,
                "currency": "string"
              },
              "rateCommentsId": "string",
              "rateComments": "string",
              "paymentType": "AT_HOTEL",
              "packaging": false,
              "boardCode": "string",
              "boardName": "string",
              "rateBreakDown": {
                "rateDiscount": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "rateSupplement": [
                  {
                    "code": "string",
                    "name": "string",
                    "from": "2017-10-21",
                    "to": "2017-10-21",
                    "amount": 0,
                    "nights": 0,
                    "paxNumber": 0
                  }
                ]
              },
              "rooms": 0,
              "adults": 0,
              "children": 0,
              "childrenAges": "string",
              "rateup": 0,
              "comment": [
                {
                  "type": "string",
                  "text": "string"
                }
              ],
              "cancellationPolicy": [
                {
                  "amount": 0,
                  "hotelAmount": 0,
                  "hotelCurrency": "string",
                  "from": "string"
                }
              ],
              "taxes": {
                "allIncluded": false,
                "tax": [
                  {
                    "included": false,
                    "percent": 0,
                    "amount": 0,
                    "currency": "string",
                    "type": "TAX",
                    "clientAmount": 0,
                    "clientCurrency": "string"
                  }
                ]
              },
              "promotion": [
                {
                  "code": "string",
                  "name": "string",
                  "remark": "string"
                }
              ],
              "offer": [
                {
                  "code": "string",
                  "name": "string",
                  "amount": 0
                }
              ],
              "shiftRate": [
                {
                  "rateKey": "string",
                  "rateClass": "string",
                  "rateType": "BOOKABLE",
                  "net": 0,
                  "discount": 0,
                  "discountPCT": 0,
                  "sellingRate": 0,
                  "hotelSellingRate": 0,
                  "amount": 0,
                  "hotelCurrency": "string",
                  "hotelMandatory": false,
                  "allotment": 0,
                  "commission": 0,
                  "commissionVAT": 0,
                  "commissionPCT": 0,
                  "cost": {
                    "amount": 0,
                    "currency": "string"
                  },
                  "checkIn": "2017-10-21",
                  "checkOut": "2017-10-21"
                }
              ],
              "dailyRate": [
                {
                  "offset": 0,
                  "dailyNet": 0,
                  "dailySellingRate": 0
                }
              ]
            }
          ]
        }
      ]
    },
    "keyword": [
      {
        "code": 0,
        "rating": 0
      }
    ],
    "review": [
      {
        "rate": 0,
        "reviewCount": 0,
        "type": "string"
      }
    ],
    "room": [
      {
        "status": "NEW",
        "id": 0,
        "code": "string",
        "name": "string",
        "pax": [
          {
            "roomId": 1,
            "type": "AD",
            "age": 20,
            "name": "string",
            "surname": "string"
          }
        ],
        "rate": [
          {
            "rateKey": "string",
            "rateClass": "string",
            "rateType": "BOOKABLE",
            "net": 0,
            "discount": 0,
            "discountPCT": 0,
            "sellingRate": 0,
            "hotelSellingRate": 0,
            "amount": 0,
            "hotelCurrency": "string",
            "hotelMandatory": false,
            "allotment": 0,
            "commission": 0,
            "commissionVAT": 0,
            "commissionPCT": 0,
            "cost": {
              "amount": 0,
              "currency": "string"
            },
            "rateCommentsId": "string",
            "rateComments": "string",
            "paymentType": "AT_HOTEL",
            "packaging": false,
            "boardCode": "string",
            "boardName": "string",
            "rateBreakDown": {
              "rateDiscount": [
                {
                  "code": "string",
                  "name": "string",
                  "amount": 0
                }
              ],
              "rateSupplement": [
                {
                  "code": "string",
                  "name": "string",
                  "from": "2017-10-21",
                  "to": "2017-10-21",
                  "amount": 0,
                  "nights": 0,
                  "paxNumber": 0
                }
              ]
            },
            "rooms": 0,
            "adults": 0,
            "children": 0,
            "childrenAges": "string",
            "rateup": 0,
            "comment": [
              {
                "type": "string",
                "text": "string"
              }
            ],
            "cancellationPolicy": [
              {
                "amount": 0,
                "hotelAmount": 0,
                "hotelCurrency": "string",
                "from": "string"
              }
            ],
            "taxes": {
              "allIncluded": false,
              "tax": [
                {
                  "included": false,
                  "percent": 0,
                  "amount": 0,
                  "currency": "string",
                  "type": "TAX",
                  "clientAmount": 0,
                  "clientCurrency": "string"
                }
              ]
            },
            "promotion": [
              {
                "code": "string",
                "name": "string",
                "remark": "string"
              }
            ],
            "offer": [
              {
                "code": "string",
                "name": "string",
                "amount": 0
              }
            ],
            "shiftRate": [
              {
                "rateKey": "string",
                "rateClass": "string",
                "rateType": "BOOKABLE",
                "net": 0,
                "discount": 0,
                "discountPCT": 0,
                "sellingRate": 0,
                "hotelSellingRate": 0,
                "amount": 0,
                "hotelCurrency": "string",
                "hotelMandatory": false,
                "allotment": 0,
                "commission": 0,
                "commissionVAT": 0,
                "commissionPCT": 0,
                "cost": {
                  "amount": 0,
                  "currency": "string"
                },
                "checkIn": "2017-10-21",
                "checkOut": "2017-10-21"
              }
            ],
            "dailyRate": [
              {
                "offset": 0,
                "dailyNet": 0,
                "dailySellingRate": 0
              }
            ]
          }
        ]
      }
    ],
    "creditCard": [
      {
        "code": "string",
        "name": "string",
        "paymentType": "AT_HOTEL"
      }
    ]
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
reference|string|false|No description
cancellationReference|string|false|No description
clientReference|string|false|No description
creationDate|string(date)|false|No description
status|string|false|No description
modificationPolicies|[ApiModificationPolicies](#schemaapimodificationpolicies)|false|No description
» cancellation|boolean|true|No description
» modification|boolean|true|No description
agCommision|number|false|No description
commisionVAT|number|false|No description
creationUser|string|false|No description
holder|[ApiHolder](#schemaapiholder)|false|No description
» name|string|true|No description
» surname|string|true|No description
remark|string|false|No description
totalSellingRate|number|false|No description
totalNet|number|false|No description
pendingAmount|number|false|No description
currency|string|false|No description
hotel|[ApiHotel](#schemaapihotel)|false|No description
» checkOut|string(date)|false|No description
» checkIn|string(date)|false|No description
» code|integer(int32)|false|No description
» name|string|false|No description
» description|string|false|No description
» image|string|false|No description
» categoryCode|string|false|No description
» categoryName|string|false|No description
» destinationCode|string|false|No description
» destinationName|string|false|No description
» zoneCode|integer(int32)|false|No description
» zoneName|string|false|No description
» latitude|string|false|No description
» longitude|string|false|No description
» giata|string|false|No description
» minRate|number|false|No description
» maxRate|number|false|No description
» totalSellingRate|number|false|No description
» totalNet|number|false|No description
» pendingAmount|number|false|No description
» currency|string|false|No description
» supplier|[ApiSupplier](#schemaapisupplier)|false|No description
»» name|string|false|No description
»» vatNumber|string|false|No description
» clientComments|string|false|No description
» cancellationAmount|number|false|No description
» upselling|[ApiUpselling](#schemaapiupselling)|false|No description
»» room|[[room](#schemaroom)]|false|No description
»»» status|string|false|No description
»»» id|integer(int32)|false|No description
»»» code|string|false|No description
»»» name|string|false|No description
»»» pax|[[ApiPax](#schemaapipax)]|false|No description
»»»» roomId|integer(int32)|false|No description
»»»» type|string|true|No description
»»»» age|integer(int32)|false|No description
»»»» name|string|false|No description
»»»» surname|string|false|No description
»»» rate|[[ApiRate](#schemaapirate)]|false|No description
»»»» rateKey|string|false|No description
»»»» rateClass|string|false|No description
»»»» rateType|string|false|No description
»»»» net|number|false|No description
»»»» discount|number|false|No description
»»»» discountPCT|number|false|No description
»»»» sellingRate|number|false|No description
»»»» hotelSellingRate|number|false|No description
»»»» amount|number|false|No description
»»»» hotelCurrency|string|false|No description
»»»» hotelMandatory|boolean|false|No description
»»»» allotment|integer(int32)|false|No description
»»»» commission|number|false|No description
»»»» commissionVAT|number|false|No description
»»»» commissionPCT|number|false|No description
»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»» amount|number|false|No description
»»»»» currency|string|false|No description
»»»» rateCommentsId|string|false|No description
»»»» rateComments|string|false|No description
»»»» paymentType|string|false|No description
»»»» packaging|boolean|false|No description
»»»» boardCode|string|false|No description
»»»» boardName|string|false|No description
»»»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» amount|number|false|No description
»»»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» from|string(date)|false|No description
»»»»»» to|string(date)|false|No description
»»»»»» amount|number|false|No description
»»»»»» nights|integer(int32)|false|No description
»»»»»» paxNumber|integer(int32)|false|No description
»»»» rooms|integer(int32)|false|No description
»»»» adults|integer(int32)|false|No description
»»»» children|integer(int32)|false|No description
»»»» childrenAges|string|false|No description
»»»» rateup|number|false|No description
»»»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»»»» allIncluded|boolean|false|No description
»»»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»»»» included|boolean|false|No description
»»»»»» percent|number|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»»» type|string|false|No description
»»»»»» clientAmount|number|false|No description
»»»»»» clientCurrency|string|false|No description
»»»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»»» type|string|false|No description
»»»»» text|string|false|No description
»»»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»»» amount|number|false|No description
»»»»» hotelAmount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» from|string|false|No description
»»»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» remark|string|false|No description
»»»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» amount|number|false|No description
»»»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»»» rateKey|string|false|No description
»»»»» rateClass|string|false|No description
»»»»» rateType|string|false|No description
»»»»» net|number|false|No description
»»»»» discount|number|false|No description
»»»»» discountPCT|number|false|No description
»»»»» sellingRate|number|false|No description
»»»»» hotelSellingRate|number|false|No description
»»»»» amount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» hotelMandatory|boolean|false|No description
»»»»» allotment|integer(int32)|false|No description
»»»»» commission|number|false|No description
»»»»» commissionVAT|number|false|No description
»»»»» commissionPCT|number|false|No description
»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»» checkIn|string(date)|false|No description
»»»»» checkOut|string(date)|false|No description
»»»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»»» offset|integer(int32)|false|No description
»»»»» dailyNet|number|false|No description
»»»»» dailySellingRate|number|false|No description
» keyword|[[ApiKeyword](#schemaapikeyword)]|false|No description
»» code|integer(int32)|true|No description
»» rating|integer(int32)|false|No description
» review|[[ApiReview](#schemaapireview)]|false|No description
»» rate|number|false|No description
»» reviewCount|integer(int32)|false|No description
»» type|string|false|No description
» room|[[room](#schemaroom)]|false|No description
»» status|string|false|No description
»» id|integer(int32)|false|No description
»» code|string|false|No description
»» name|string|false|No description
»» pax|[[ApiPax](#schemaapipax)]|false|No description
»»» roomId|integer(int32)|false|No description
»»» type|string|true|No description
»»» age|integer(int32)|false|No description
»»» name|string|false|No description
»»» surname|string|false|No description
»» rate|[[ApiRate](#schemaapirate)]|false|No description
»»» rateKey|string|false|No description
»»» rateClass|string|false|No description
»»» rateType|string|false|No description
»»» net|number|false|No description
»»» discount|number|false|No description
»»» discountPCT|number|false|No description
»»» sellingRate|number|false|No description
»»» hotelSellingRate|number|false|No description
»»» amount|number|false|No description
»»» hotelCurrency|string|false|No description
»»» hotelMandatory|boolean|false|No description
»»» allotment|integer(int32)|false|No description
»»» commission|number|false|No description
»»» commissionVAT|number|false|No description
»»» commissionPCT|number|false|No description
»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»» amount|number|false|No description
»»»» currency|string|false|No description
»»» rateCommentsId|string|false|No description
»»» rateComments|string|false|No description
»»» paymentType|string|false|No description
»»» packaging|boolean|false|No description
»»» boardCode|string|false|No description
»»» boardName|string|false|No description
»»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» amount|number|false|No description
»»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» from|string(date)|false|No description
»»»»» to|string(date)|false|No description
»»»»» amount|number|false|No description
»»»»» nights|integer(int32)|false|No description
»»»»» paxNumber|integer(int32)|false|No description
»»» rooms|integer(int32)|false|No description
»»» adults|integer(int32)|false|No description
»»» children|integer(int32)|false|No description
»»» childrenAges|string|false|No description
»»» rateup|number|false|No description
»»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»»» allIncluded|boolean|false|No description
»»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»»» included|boolean|false|No description
»»»»» percent|number|false|No description
»»»»» amount|number|false|No description
»»»»» currency|string|false|No description
»»»»» type|string|false|No description
»»»»» clientAmount|number|false|No description
»»»»» clientCurrency|string|false|No description
»»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»» type|string|false|No description
»»»» text|string|false|No description
»»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»» amount|number|false|No description
»»»» hotelAmount|number|false|No description
»»»» hotelCurrency|string|false|No description
»»»» from|string|false|No description
»»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»» code|string|false|No description
»»»» name|string|false|No description
»»»» remark|string|false|No description
»»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»»» code|string|false|No description
»»»» name|string|false|No description
»»»» amount|number|false|No description
»»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»» rateKey|string|false|No description
»»»» rateClass|string|false|No description
»»»» rateType|string|false|No description
»»»» net|number|false|No description
»»»» discount|number|false|No description
»»»» discountPCT|number|false|No description
»»»» sellingRate|number|false|No description
»»»» hotelSellingRate|number|false|No description
»»»» amount|number|false|No description
»»»» hotelCurrency|string|false|No description
»»»» hotelMandatory|boolean|false|No description
»»»» allotment|integer(int32)|false|No description
»»»» commission|number|false|No description
»»»» commissionVAT|number|false|No description
»»»» commissionPCT|number|false|No description
»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»» amount|number|false|No description
»»»»» currency|string|false|No description
»»»» checkIn|string(date)|false|No description
»»»» checkOut|string(date)|false|No description
»»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»» offset|integer(int32)|false|No description
»»»» dailyNet|number|false|No description
»»»» dailySellingRate|number|false|No description
» creditCard|[[ApiCreditCard](#schemaapicreditcard)]|false|No description
»» code|string|false|No description
»» name|string|false|No description
»» paymentType|string|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
status|NEW|
status|PRECONFIRMED|
status|CONFIRMED|
status|TO_BE_UPDATED|
status|CANCELLED|
status|TO_BE_CANCELLED|
»»» status|NEW|
»»» status|PRECONFIRMED|
»»» status|CONFIRMED|
»»» status|TO_BE_UPDATED|
»»» status|CANCELLED|
»»» status|TO_BE_CANCELLED|
»»»» type|AD|
»»»» type|CH|
»»»» rateType|BOOKABLE|
»»»» rateType|RECHECK|
»»»» paymentType|AT_HOTEL|
»»»» paymentType|AT_WEB|
»»»»»» type|TAX|
»»»»»» type|FEE|
»»»»» rateType|BOOKABLE|
»»»»» rateType|RECHECK|
»» status|NEW|
»» status|PRECONFIRMED|
»» status|CONFIRMED|
»» status|TO_BE_UPDATED|
»» status|CANCELLED|
»» status|TO_BE_CANCELLED|
»»» type|AD|
»»» type|CH|
»»» rateType|BOOKABLE|
»»» rateType|RECHECK|
»»» paymentType|AT_HOTEL|
»»» paymentType|AT_WEB|
»»»»» type|TAX|
»»»»» type|FEE|
»»»» rateType|BOOKABLE|
»»»» rateType|RECHECK|
»» paymentType|AT_HOTEL|
»» paymentType|AT_WEB|


## ApiBookingDevice

<a name="schemaapibookingdevice"></a>

```json
{
  "id": "string",
  "ip": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
id|string|false|No description
ip|string|false|No description



## ApiBookingRoom

<a name="schemaapibookingroom"></a>

```json
{
  "rateKey": "string",
  "pax": [
    {
      "roomId": 1,
      "type": "AD",
      "age": 20,
      "name": "string",
      "surname": "string"
    }
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
rateKey|string|true|No description
pax|[[ApiPax](#schemaapipax)]|false|No description
» roomId|integer(int32)|false|No description
» type|string|true|No description
» age|integer(int32)|false|No description
» name|string|false|No description
» surname|string|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
» type|AD|
» type|CH|


## ApiBookings

<a name="schemaapibookings"></a>

```json
{
  "from": 0,
  "to": 0,
  "total": 0,
  "booking": [
    {
      "reference": "string",
      "cancellationReference": "string",
      "clientReference": "string",
      "creationDate": "2017-10-21",
      "status": "NEW",
      "modificationPolicies": {
        "cancellation": false,
        "modification": false
      },
      "agCommision": 0,
      "commisionVAT": 0,
      "creationUser": "string",
      "holder": {
        "name": "string",
        "surname": "string"
      },
      "remark": "string",
      "totalSellingRate": 0,
      "totalNet": 0,
      "pendingAmount": 0,
      "currency": "string",
      "hotel": {
        "checkOut": "2017-10-21",
        "checkIn": "2017-10-21",
        "code": 0,
        "name": "string",
        "description": "string",
        "image": "string",
        "categoryCode": "string",
        "categoryName": "string",
        "destinationCode": "string",
        "destinationName": "string",
        "zoneCode": 0,
        "zoneName": "string",
        "latitude": "string",
        "longitude": "string",
        "giata": "string",
        "minRate": 0,
        "maxRate": 0,
        "totalSellingRate": 0,
        "totalNet": 0,
        "pendingAmount": 0,
        "currency": "string",
        "supplier": {
          "name": "string",
          "vatNumber": "string"
        },
        "clientComments": "string",
        "cancellationAmount": 0,
        "upselling": {
          "room": [
            {
              "status": "NEW",
              "id": 0,
              "code": "string",
              "name": "string",
              "pax": [
                {
                  "roomId": 1,
                  "type": "AD",
                  "age": 20,
                  "name": "string",
                  "surname": "string"
                }
              ],
              "rate": [
                {
                  "rateKey": "string",
                  "rateClass": "string",
                  "rateType": "BOOKABLE",
                  "net": 0,
                  "discount": 0,
                  "discountPCT": 0,
                  "sellingRate": 0,
                  "hotelSellingRate": 0,
                  "amount": 0,
                  "hotelCurrency": "string",
                  "hotelMandatory": false,
                  "allotment": 0,
                  "commission": 0,
                  "commissionVAT": 0,
                  "commissionPCT": 0,
                  "cost": {
                    "amount": 0,
                    "currency": "string"
                  },
                  "rateCommentsId": "string",
                  "rateComments": "string",
                  "paymentType": "AT_HOTEL",
                  "packaging": false,
                  "boardCode": "string",
                  "boardName": "string",
                  "rateBreakDown": {
                    "rateDiscount": [
                      {
                        "code": "string",
                        "name": "string",
                        "amount": 0
                      }
                    ],
                    "rateSupplement": [
                      {
                        "code": "string",
                        "name": "string",
                        "from": "2017-10-21",
                        "to": "2017-10-21",
                        "amount": 0,
                        "nights": 0,
                        "paxNumber": 0
                      }
                    ]
                  },
                  "rooms": 0,
                  "adults": 0,
                  "children": 0,
                  "childrenAges": "string",
                  "rateup": 0,
                  "comment": [
                    {
                      "type": "string",
                      "text": "string"
                    }
                  ],
                  "cancellationPolicy": [
                    {
                      "amount": 0,
                      "hotelAmount": 0,
                      "hotelCurrency": "string",
                      "from": "string"
                    }
                  ],
                  "taxes": {
                    "allIncluded": false,
                    "tax": [
                      {
                        "included": false,
                        "percent": 0,
                        "amount": 0,
                        "currency": "string",
                        "type": "TAX",
                        "clientAmount": 0,
                        "clientCurrency": "string"
                      }
                    ]
                  },
                  "promotion": [
                    {
                      "code": "string",
                      "name": "string",
                      "remark": "string"
                    }
                  ],
                  "offer": [
                    {
                      "code": "string",
                      "name": "string",
                      "amount": 0
                    }
                  ],
                  "shiftRate": [
                    {
                      "rateKey": "string",
                      "rateClass": "string",
                      "rateType": "BOOKABLE",
                      "net": 0,
                      "discount": 0,
                      "discountPCT": 0,
                      "sellingRate": 0,
                      "hotelSellingRate": 0,
                      "amount": 0,
                      "hotelCurrency": "string",
                      "hotelMandatory": false,
                      "allotment": 0,
                      "commission": 0,
                      "commissionVAT": 0,
                      "commissionPCT": 0,
                      "cost": {
                        "amount": 0,
                        "currency": "string"
                      },
                      "checkIn": "2017-10-21",
                      "checkOut": "2017-10-21"
                    }
                  ],
                  "dailyRate": [
                    {
                      "offset": 0,
                      "dailyNet": 0,
                      "dailySellingRate": 0
                    }
                  ]
                }
              ]
            }
          ]
        },
        "keyword": [
          {
            "code": 0,
            "rating": 0
          }
        ],
        "review": [
          {
            "rate": 0,
            "reviewCount": 0,
            "type": "string"
          }
        ],
        "room": [
          {
            "status": "NEW",
            "id": 0,
            "code": "string",
            "name": "string",
            "pax": [
              {
                "roomId": 1,
                "type": "AD",
                "age": 20,
                "name": "string",
                "surname": "string"
              }
            ],
            "rate": [
              {
                "rateKey": "string",
                "rateClass": "string",
                "rateType": "BOOKABLE",
                "net": 0,
                "discount": 0,
                "discountPCT": 0,
                "sellingRate": 0,
                "hotelSellingRate": 0,
                "amount": 0,
                "hotelCurrency": "string",
                "hotelMandatory": false,
                "allotment": 0,
                "commission": 0,
                "commissionVAT": 0,
                "commissionPCT": 0,
                "cost": {
                  "amount": 0,
                  "currency": "string"
                },
                "rateCommentsId": "string",
                "rateComments": "string",
                "paymentType": "AT_HOTEL",
                "packaging": false,
                "boardCode": "string",
                "boardName": "string",
                "rateBreakDown": {
                  "rateDiscount": [
                    {
                      "code": "string",
                      "name": "string",
                      "amount": 0
                    }
                  ],
                  "rateSupplement": [
                    {
                      "code": "string",
                      "name": "string",
                      "from": "2017-10-21",
                      "to": "2017-10-21",
                      "amount": 0,
                      "nights": 0,
                      "paxNumber": 0
                    }
                  ]
                },
                "rooms": 0,
                "adults": 0,
                "children": 0,
                "childrenAges": "string",
                "rateup": 0,
                "comment": [
                  {
                    "type": "string",
                    "text": "string"
                  }
                ],
                "cancellationPolicy": [
                  {
                    "amount": 0,
                    "hotelAmount": 0,
                    "hotelCurrency": "string",
                    "from": "string"
                  }
                ],
                "taxes": {
                  "allIncluded": false,
                  "tax": [
                    {
                      "included": false,
                      "percent": 0,
                      "amount": 0,
                      "currency": "string",
                      "type": "TAX",
                      "clientAmount": 0,
                      "clientCurrency": "string"
                    }
                  ]
                },
                "promotion": [
                  {
                    "code": "string",
                    "name": "string",
                    "remark": "string"
                  }
                ],
                "offer": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "shiftRate": [
                  {
                    "rateKey": "string",
                    "rateClass": "string",
                    "rateType": "BOOKABLE",
                    "net": 0,
                    "discount": 0,
                    "discountPCT": 0,
                    "sellingRate": 0,
                    "hotelSellingRate": 0,
                    "amount": 0,
                    "hotelCurrency": "string",
                    "hotelMandatory": false,
                    "allotment": 0,
                    "commission": 0,
                    "commissionVAT": 0,
                    "commissionPCT": 0,
                    "cost": {
                      "amount": 0,
                      "currency": "string"
                    },
                    "checkIn": "2017-10-21",
                    "checkOut": "2017-10-21"
                  }
                ],
                "dailyRate": [
                  {
                    "offset": 0,
                    "dailyNet": 0,
                    "dailySellingRate": 0
                  }
                ]
              }
            ]
          }
        ],
        "creditCard": [
          {
            "code": "string",
            "name": "string",
            "paymentType": "AT_HOTEL"
          }
        ]
      }
    }
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
from|integer(int32)|false|No description
to|integer(int32)|false|No description
total|number|false|No description
booking|[[ApiBooking](#schemaapibooking)]|false|No description
» reference|string|false|No description
» cancellationReference|string|false|No description
» clientReference|string|false|No description
» creationDate|string(date)|false|No description
» status|string|false|No description
» modificationPolicies|[ApiModificationPolicies](#schemaapimodificationpolicies)|false|No description
»» cancellation|boolean|true|No description
»» modification|boolean|true|No description
» agCommision|number|false|No description
» commisionVAT|number|false|No description
» creationUser|string|false|No description
» holder|[ApiHolder](#schemaapiholder)|false|No description
»» name|string|true|No description
»» surname|string|true|No description
» remark|string|false|No description
» totalSellingRate|number|false|No description
» totalNet|number|false|No description
» pendingAmount|number|false|No description
» currency|string|false|No description
» hotel|[ApiHotel](#schemaapihotel)|false|No description
»» checkOut|string(date)|false|No description
»» checkIn|string(date)|false|No description
»» code|integer(int32)|false|No description
»» name|string|false|No description
»» description|string|false|No description
»» image|string|false|No description
»» categoryCode|string|false|No description
»» categoryName|string|false|No description
»» destinationCode|string|false|No description
»» destinationName|string|false|No description
»» zoneCode|integer(int32)|false|No description
»» zoneName|string|false|No description
»» latitude|string|false|No description
»» longitude|string|false|No description
»» giata|string|false|No description
»» minRate|number|false|No description
»» maxRate|number|false|No description
»» totalSellingRate|number|false|No description
»» totalNet|number|false|No description
»» pendingAmount|number|false|No description
»» currency|string|false|No description
»» supplier|[ApiSupplier](#schemaapisupplier)|false|No description
»»» name|string|false|No description
»»» vatNumber|string|false|No description
»» clientComments|string|false|No description
»» cancellationAmount|number|false|No description
»» upselling|[ApiUpselling](#schemaapiupselling)|false|No description
»»» room|[[room](#schemaroom)]|false|No description
»»»» status|string|false|No description
»»»» id|integer(int32)|false|No description
»»»» code|string|false|No description
»»»» name|string|false|No description
»»»» pax|[[ApiPax](#schemaapipax)]|false|No description
»»»»» roomId|integer(int32)|false|No description
»»»»» type|string|true|No description
»»»»» age|integer(int32)|false|No description
»»»»» name|string|false|No description
»»»»» surname|string|false|No description
»»»» rate|[[ApiRate](#schemaapirate)]|false|No description
»»»»» rateKey|string|false|No description
»»»»» rateClass|string|false|No description
»»»»» rateType|string|false|No description
»»»»» net|number|false|No description
»»»»» discount|number|false|No description
»»»»» discountPCT|number|false|No description
»»»»» sellingRate|number|false|No description
»»»»» hotelSellingRate|number|false|No description
»»»»» amount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» hotelMandatory|boolean|false|No description
»»»»» allotment|integer(int32)|false|No description
»»»»» commission|number|false|No description
»»»»» commissionVAT|number|false|No description
»»»»» commissionPCT|number|false|No description
»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»» rateCommentsId|string|false|No description
»»»»» rateComments|string|false|No description
»»»»» paymentType|string|false|No description
»»»»» packaging|boolean|false|No description
»»»»» boardCode|string|false|No description
»»»»» boardName|string|false|No description
»»»»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»»»» code|string|false|No description
»»»»»»» name|string|false|No description
»»»»»»» amount|number|false|No description
»»»»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»»»» code|string|false|No description
»»»»»»» name|string|false|No description
»»»»»»» from|string(date)|false|No description
»»»»»»» to|string(date)|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» nights|integer(int32)|false|No description
»»»»»»» paxNumber|integer(int32)|false|No description
»»»»» rooms|integer(int32)|false|No description
»»»»» adults|integer(int32)|false|No description
»»»»» children|integer(int32)|false|No description
»»»»» childrenAges|string|false|No description
»»»»» rateup|number|false|No description
»»»»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»»»»» allIncluded|boolean|false|No description
»»»»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»»»»» included|boolean|false|No description
»»»»»»» percent|number|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» currency|string|false|No description
»»»»»»» type|string|false|No description
»»»»»»» clientAmount|number|false|No description
»»»»»»» clientCurrency|string|false|No description
»»»»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»»»» type|string|false|No description
»»»»»» text|string|false|No description
»»»»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»»»» amount|number|false|No description
»»»»»» hotelAmount|number|false|No description
»»»»»» hotelCurrency|string|false|No description
»»»»»» from|string|false|No description
»»»»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» remark|string|false|No description
»»»»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» amount|number|false|No description
»»»»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»»»» rateKey|string|false|No description
»»»»»» rateClass|string|false|No description
»»»»»» rateType|string|false|No description
»»»»»» net|number|false|No description
»»»»»» discount|number|false|No description
»»»»»» discountPCT|number|false|No description
»»»»»» sellingRate|number|false|No description
»»»»»» hotelSellingRate|number|false|No description
»»»»»» amount|number|false|No description
»»»»»» hotelCurrency|string|false|No description
»»»»»» hotelMandatory|boolean|false|No description
»»»»»» allotment|integer(int32)|false|No description
»»»»»» commission|number|false|No description
»»»»»» commissionVAT|number|false|No description
»»»»»» commissionPCT|number|false|No description
»»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» currency|string|false|No description
»»»»»» checkIn|string(date)|false|No description
»»»»»» checkOut|string(date)|false|No description
»»»»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»»»» offset|integer(int32)|false|No description
»»»»»» dailyNet|number|false|No description
»»»»»» dailySellingRate|number|false|No description
»» keyword|[[ApiKeyword](#schemaapikeyword)]|false|No description
»»» code|integer(int32)|true|No description
»»» rating|integer(int32)|false|No description
»» review|[[ApiReview](#schemaapireview)]|false|No description
»»» rate|number|false|No description
»»» reviewCount|integer(int32)|false|No description
»»» type|string|false|No description
»» room|[[room](#schemaroom)]|false|No description
»»» status|string|false|No description
»»» id|integer(int32)|false|No description
»»» code|string|false|No description
»»» name|string|false|No description
»»» pax|[[ApiPax](#schemaapipax)]|false|No description
»»»» roomId|integer(int32)|false|No description
»»»» type|string|true|No description
»»»» age|integer(int32)|false|No description
»»»» name|string|false|No description
»»»» surname|string|false|No description
»»» rate|[[ApiRate](#schemaapirate)]|false|No description
»»»» rateKey|string|false|No description
»»»» rateClass|string|false|No description
»»»» rateType|string|false|No description
»»»» net|number|false|No description
»»»» discount|number|false|No description
»»»» discountPCT|number|false|No description
»»»» sellingRate|number|false|No description
»»»» hotelSellingRate|number|false|No description
»»»» amount|number|false|No description
»»»» hotelCurrency|string|false|No description
»»»» hotelMandatory|boolean|false|No description
»»»» allotment|integer(int32)|false|No description
»»»» commission|number|false|No description
»»»» commissionVAT|number|false|No description
»»»» commissionPCT|number|false|No description
»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»» amount|number|false|No description
»»»»» currency|string|false|No description
»»»» rateCommentsId|string|false|No description
»»»» rateComments|string|false|No description
»»»» paymentType|string|false|No description
»»»» packaging|boolean|false|No description
»»»» boardCode|string|false|No description
»»»» boardName|string|false|No description
»»»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» amount|number|false|No description
»»»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» from|string(date)|false|No description
»»»»»» to|string(date)|false|No description
»»»»»» amount|number|false|No description
»»»»»» nights|integer(int32)|false|No description
»»»»»» paxNumber|integer(int32)|false|No description
»»»» rooms|integer(int32)|false|No description
»»»» adults|integer(int32)|false|No description
»»»» children|integer(int32)|false|No description
»»»» childrenAges|string|false|No description
»»»» rateup|number|false|No description
»»»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»»»» allIncluded|boolean|false|No description
»»»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»»»» included|boolean|false|No description
»»»»»» percent|number|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»»» type|string|false|No description
»»»»»» clientAmount|number|false|No description
»»»»»» clientCurrency|string|false|No description
»»»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»»» type|string|false|No description
»»»»» text|string|false|No description
»»»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»»» amount|number|false|No description
»»»»» hotelAmount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» from|string|false|No description
»»»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» remark|string|false|No description
»»»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» amount|number|false|No description
»»»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»»» rateKey|string|false|No description
»»»»» rateClass|string|false|No description
»»»»» rateType|string|false|No description
»»»»» net|number|false|No description
»»»»» discount|number|false|No description
»»»»» discountPCT|number|false|No description
»»»»» sellingRate|number|false|No description
»»»»» hotelSellingRate|number|false|No description
»»»»» amount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» hotelMandatory|boolean|false|No description
»»»»» allotment|integer(int32)|false|No description
»»»»» commission|number|false|No description
»»»»» commissionVAT|number|false|No description
»»»»» commissionPCT|number|false|No description
»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»» checkIn|string(date)|false|No description
»»»»» checkOut|string(date)|false|No description
»»»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»»» offset|integer(int32)|false|No description
»»»»» dailyNet|number|false|No description
»»»»» dailySellingRate|number|false|No description
»» creditCard|[[ApiCreditCard](#schemaapicreditcard)]|false|No description
»»» code|string|false|No description
»»» name|string|false|No description
»»» paymentType|string|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
» status|NEW|
» status|PRECONFIRMED|
» status|CONFIRMED|
» status|TO_BE_UPDATED|
» status|CANCELLED|
» status|TO_BE_CANCELLED|
»»»» status|NEW|
»»»» status|PRECONFIRMED|
»»»» status|CONFIRMED|
»»»» status|TO_BE_UPDATED|
»»»» status|CANCELLED|
»»»» status|TO_BE_CANCELLED|
»»»»» type|AD|
»»»»» type|CH|
»»»»» rateType|BOOKABLE|
»»»»» rateType|RECHECK|
»»»»» paymentType|AT_HOTEL|
»»»»» paymentType|AT_WEB|
»»»»»»» type|TAX|
»»»»»»» type|FEE|
»»»»»» rateType|BOOKABLE|
»»»»»» rateType|RECHECK|
»»» status|NEW|
»»» status|PRECONFIRMED|
»»» status|CONFIRMED|
»»» status|TO_BE_UPDATED|
»»» status|CANCELLED|
»»» status|TO_BE_CANCELLED|
»»»» type|AD|
»»»» type|CH|
»»»» rateType|BOOKABLE|
»»»» rateType|RECHECK|
»»»» paymentType|AT_HOTEL|
»»»» paymentType|AT_WEB|
»»»»»» type|TAX|
»»»»»» type|FEE|
»»»»» rateType|BOOKABLE|
»»»»» rateType|RECHECK|
»»» paymentType|AT_HOTEL|
»»» paymentType|AT_WEB|


## ApiCancellationPolicy

<a name="schemaapicancellationpolicy"></a>

```json
{
  "amount": 0,
  "hotelAmount": 0,
  "hotelCurrency": "string",
  "from": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
amount|number|false|No description
hotelAmount|number|false|No description
hotelCurrency|string|false|No description
from|string|false|No description



## ApiCost

<a name="schemaapicost"></a>

```json
{
  "amount": 0,
  "currency": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
amount|number|false|No description
currency|string|false|No description



## ApiCreditCard

<a name="schemaapicreditcard"></a>

```json
{
  "code": "string",
  "name": "string",
  "paymentType": "AT_HOTEL"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
code|string|false|No description
name|string|false|No description
paymentType|string|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
paymentType|AT_HOTEL|
paymentType|AT_WEB|


## ApiDailyRate

<a name="schemaapidailyrate"></a>

```json
{
  "offset": 0,
  "dailyNet": 0,
  "dailySellingRate": 0
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
offset|integer(int32)|false|No description
dailyNet|number|false|No description
dailySellingRate|number|false|No description



## ApiDestination

<a name="schemaapidestination"></a>

```json
{
  "code": "PMI",
  "zone": 10
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
code|string|true|No description
zone|integer(int32)|false|No description



## ApiFilter

<a name="schemaapifilter"></a>

```json
{
  "maxHotels": 1000,
  "maxRooms": 10,
  "minRate": 0,
  "maxRate": 1000,
  "maxRatesPerRoom": 1,
  "packaging": false,
  "paymentType": "AT_WEB",
  "hotelPackage": "BOTH",
  "minCategory": 1,
  "maxCategory": 5,
  "contract": "CG-VARIOS"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
maxHotels|integer(int32)|false|No description
maxRooms|integer(int32)|false|No description
minRate|number|false|No description
maxRate|number|false|No description
maxRatesPerRoom|integer(int32)|false|No description
packaging|boolean|false|No description
paymentType|string|false|No description
hotelPackage|string|false|No description
minCategory|integer(int32)|false|No description
maxCategory|integer(int32)|false|No description
contract|string|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
paymentType|AT_HOTEL|
paymentType|AT_WEB|
paymentType|BOTH|
hotelPackage|YES|
hotelPackage|NO|
hotelPackage|BOTH|


## ApiGeoLocation

<a name="schemaapigeolocation"></a>

```json
{
  "longitude": 2.62155,
  "latitude": 39.5554,
  "radius": 0,
  "unit": "mi",
  "secondaryLatitude": 0,
  "secondaryLongitude": 0
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
longitude|number|true|No description
latitude|number|true|No description
radius|number|false|No description
unit|string|false|No description
secondaryLatitude|number|false|No description
secondaryLongitude|number|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
unit|mi|
unit|km|


## ApiHolder

<a name="schemaapiholder"></a>

```json
{
  "name": "string",
  "surname": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
name|string|true|No description
surname|string|true|No description



## ApiHotel

<a name="schemaapihotel"></a>

```json
{
  "checkOut": "2017-10-21",
  "checkIn": "2017-10-21",
  "code": 0,
  "name": "string",
  "description": "string",
  "image": "string",
  "categoryCode": "string",
  "categoryName": "string",
  "destinationCode": "string",
  "destinationName": "string",
  "zoneCode": 0,
  "zoneName": "string",
  "latitude": "string",
  "longitude": "string",
  "giata": "string",
  "minRate": 0,
  "maxRate": 0,
  "totalSellingRate": 0,
  "totalNet": 0,
  "pendingAmount": 0,
  "currency": "string",
  "supplier": {
    "name": "string",
    "vatNumber": "string"
  },
  "clientComments": "string",
  "cancellationAmount": 0,
  "upselling": {
    "room": [
      {
        "status": "NEW",
        "id": 0,
        "code": "string",
        "name": "string",
        "pax": [
          {
            "roomId": 1,
            "type": "AD",
            "age": 20,
            "name": "string",
            "surname": "string"
          }
        ],
        "rate": [
          {
            "rateKey": "string",
            "rateClass": "string",
            "rateType": "BOOKABLE",
            "net": 0,
            "discount": 0,
            "discountPCT": 0,
            "sellingRate": 0,
            "hotelSellingRate": 0,
            "amount": 0,
            "hotelCurrency": "string",
            "hotelMandatory": false,
            "allotment": 0,
            "commission": 0,
            "commissionVAT": 0,
            "commissionPCT": 0,
            "cost": {
              "amount": 0,
              "currency": "string"
            },
            "rateCommentsId": "string",
            "rateComments": "string",
            "paymentType": "AT_HOTEL",
            "packaging": false,
            "boardCode": "string",
            "boardName": "string",
            "rateBreakDown": {
              "rateDiscount": [
                {
                  "code": "string",
                  "name": "string",
                  "amount": 0
                }
              ],
              "rateSupplement": [
                {
                  "code": "string",
                  "name": "string",
                  "from": "2017-10-21",
                  "to": "2017-10-21",
                  "amount": 0,
                  "nights": 0,
                  "paxNumber": 0
                }
              ]
            },
            "rooms": 0,
            "adults": 0,
            "children": 0,
            "childrenAges": "string",
            "rateup": 0,
            "comment": [
              {
                "type": "string",
                "text": "string"
              }
            ],
            "cancellationPolicy": [
              {
                "amount": 0,
                "hotelAmount": 0,
                "hotelCurrency": "string",
                "from": "string"
              }
            ],
            "taxes": {
              "allIncluded": false,
              "tax": [
                {
                  "included": false,
                  "percent": 0,
                  "amount": 0,
                  "currency": "string",
                  "type": "TAX",
                  "clientAmount": 0,
                  "clientCurrency": "string"
                }
              ]
            },
            "promotion": [
              {
                "code": "string",
                "name": "string",
                "remark": "string"
              }
            ],
            "offer": [
              {
                "code": "string",
                "name": "string",
                "amount": 0
              }
            ],
            "shiftRate": [
              {
                "rateKey": "string",
                "rateClass": "string",
                "rateType": "BOOKABLE",
                "net": 0,
                "discount": 0,
                "discountPCT": 0,
                "sellingRate": 0,
                "hotelSellingRate": 0,
                "amount": 0,
                "hotelCurrency": "string",
                "hotelMandatory": false,
                "allotment": 0,
                "commission": 0,
                "commissionVAT": 0,
                "commissionPCT": 0,
                "cost": {
                  "amount": 0,
                  "currency": "string"
                },
                "checkIn": "2017-10-21",
                "checkOut": "2017-10-21"
              }
            ],
            "dailyRate": [
              {
                "offset": 0,
                "dailyNet": 0,
                "dailySellingRate": 0
              }
            ]
          }
        ]
      }
    ]
  },
  "keyword": [
    {
      "code": 0,
      "rating": 0
    }
  ],
  "review": [
    {
      "rate": 0,
      "reviewCount": 0,
      "type": "string"
    }
  ],
  "room": [
    {
      "status": "NEW",
      "id": 0,
      "code": "string",
      "name": "string",
      "pax": [
        {
          "roomId": 1,
          "type": "AD",
          "age": 20,
          "name": "string",
          "surname": "string"
        }
      ],
      "rate": [
        {
          "rateKey": "string",
          "rateClass": "string",
          "rateType": "BOOKABLE",
          "net": 0,
          "discount": 0,
          "discountPCT": 0,
          "sellingRate": 0,
          "hotelSellingRate": 0,
          "amount": 0,
          "hotelCurrency": "string",
          "hotelMandatory": false,
          "allotment": 0,
          "commission": 0,
          "commissionVAT": 0,
          "commissionPCT": 0,
          "cost": {
            "amount": 0,
            "currency": "string"
          },
          "rateCommentsId": "string",
          "rateComments": "string",
          "paymentType": "AT_HOTEL",
          "packaging": false,
          "boardCode": "string",
          "boardName": "string",
          "rateBreakDown": {
            "rateDiscount": [
              {
                "code": "string",
                "name": "string",
                "amount": 0
              }
            ],
            "rateSupplement": [
              {
                "code": "string",
                "name": "string",
                "from": "2017-10-21",
                "to": "2017-10-21",
                "amount": 0,
                "nights": 0,
                "paxNumber": 0
              }
            ]
          },
          "rooms": 0,
          "adults": 0,
          "children": 0,
          "childrenAges": "string",
          "rateup": 0,
          "comment": [
            {
              "type": "string",
              "text": "string"
            }
          ],
          "cancellationPolicy": [
            {
              "amount": 0,
              "hotelAmount": 0,
              "hotelCurrency": "string",
              "from": "string"
            }
          ],
          "taxes": {
            "allIncluded": false,
            "tax": [
              {
                "included": false,
                "percent": 0,
                "amount": 0,
                "currency": "string",
                "type": "TAX",
                "clientAmount": 0,
                "clientCurrency": "string"
              }
            ]
          },
          "promotion": [
            {
              "code": "string",
              "name": "string",
              "remark": "string"
            }
          ],
          "offer": [
            {
              "code": "string",
              "name": "string",
              "amount": 0
            }
          ],
          "shiftRate": [
            {
              "rateKey": "string",
              "rateClass": "string",
              "rateType": "BOOKABLE",
              "net": 0,
              "discount": 0,
              "discountPCT": 0,
              "sellingRate": 0,
              "hotelSellingRate": 0,
              "amount": 0,
              "hotelCurrency": "string",
              "hotelMandatory": false,
              "allotment": 0,
              "commission": 0,
              "commissionVAT": 0,
              "commissionPCT": 0,
              "cost": {
                "amount": 0,
                "currency": "string"
              },
              "checkIn": "2017-10-21",
              "checkOut": "2017-10-21"
            }
          ],
          "dailyRate": [
            {
              "offset": 0,
              "dailyNet": 0,
              "dailySellingRate": 0
            }
          ]
        }
      ]
    }
  ],
  "creditCard": [
    {
      "code": "string",
      "name": "string",
      "paymentType": "AT_HOTEL"
    }
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
checkOut|string(date)|false|No description
checkIn|string(date)|false|No description
code|integer(int32)|false|No description
name|string|false|No description
description|string|false|No description
image|string|false|No description
categoryCode|string|false|No description
categoryName|string|false|No description
destinationCode|string|false|No description
destinationName|string|false|No description
zoneCode|integer(int32)|false|No description
zoneName|string|false|No description
latitude|string|false|No description
longitude|string|false|No description
giata|string|false|No description
minRate|number|false|No description
maxRate|number|false|No description
totalSellingRate|number|false|No description
totalNet|number|false|No description
pendingAmount|number|false|No description
currency|string|false|No description
supplier|[ApiSupplier](#schemaapisupplier)|false|No description
» name|string|false|No description
» vatNumber|string|false|No description
clientComments|string|false|No description
cancellationAmount|number|false|No description
upselling|[ApiUpselling](#schemaapiupselling)|false|No description
» room|[[room](#schemaroom)]|false|No description
»» status|string|false|No description
»» id|integer(int32)|false|No description
»» code|string|false|No description
»» name|string|false|No description
»» pax|[[ApiPax](#schemaapipax)]|false|No description
»»» roomId|integer(int32)|false|No description
»»» type|string|true|No description
»»» age|integer(int32)|false|No description
»»» name|string|false|No description
»»» surname|string|false|No description
»» rate|[[ApiRate](#schemaapirate)]|false|No description
»»» rateKey|string|false|No description
»»» rateClass|string|false|No description
»»» rateType|string|false|No description
»»» net|number|false|No description
»»» discount|number|false|No description
»»» discountPCT|number|false|No description
»»» sellingRate|number|false|No description
»»» hotelSellingRate|number|false|No description
»»» amount|number|false|No description
»»» hotelCurrency|string|false|No description
»»» hotelMandatory|boolean|false|No description
»»» allotment|integer(int32)|false|No description
»»» commission|number|false|No description
»»» commissionVAT|number|false|No description
»»» commissionPCT|number|false|No description
»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»» amount|number|false|No description
»»»» currency|string|false|No description
»»» rateCommentsId|string|false|No description
»»» rateComments|string|false|No description
»»» paymentType|string|false|No description
»»» packaging|boolean|false|No description
»»» boardCode|string|false|No description
»»» boardName|string|false|No description
»»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» amount|number|false|No description
»»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» from|string(date)|false|No description
»»»»» to|string(date)|false|No description
»»»»» amount|number|false|No description
»»»»» nights|integer(int32)|false|No description
»»»»» paxNumber|integer(int32)|false|No description
»»» rooms|integer(int32)|false|No description
»»» adults|integer(int32)|false|No description
»»» children|integer(int32)|false|No description
»»» childrenAges|string|false|No description
»»» rateup|number|false|No description
»»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»»» allIncluded|boolean|false|No description
»»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»»» included|boolean|false|No description
»»»»» percent|number|false|No description
»»»»» amount|number|false|No description
»»»»» currency|string|false|No description
»»»»» type|string|false|No description
»»»»» clientAmount|number|false|No description
»»»»» clientCurrency|string|false|No description
»»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»» type|string|false|No description
»»»» text|string|false|No description
»»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»» amount|number|false|No description
»»»» hotelAmount|number|false|No description
»»»» hotelCurrency|string|false|No description
»»»» from|string|false|No description
»»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»» code|string|false|No description
»»»» name|string|false|No description
»»»» remark|string|false|No description
»»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»»» code|string|false|No description
»»»» name|string|false|No description
»»»» amount|number|false|No description
»»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»» rateKey|string|false|No description
»»»» rateClass|string|false|No description
»»»» rateType|string|false|No description
»»»» net|number|false|No description
»»»» discount|number|false|No description
»»»» discountPCT|number|false|No description
»»»» sellingRate|number|false|No description
»»»» hotelSellingRate|number|false|No description
»»»» amount|number|false|No description
»»»» hotelCurrency|string|false|No description
»»»» hotelMandatory|boolean|false|No description
»»»» allotment|integer(int32)|false|No description
»»»» commission|number|false|No description
»»»» commissionVAT|number|false|No description
»»»» commissionPCT|number|false|No description
»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»» amount|number|false|No description
»»»»» currency|string|false|No description
»»»» checkIn|string(date)|false|No description
»»»» checkOut|string(date)|false|No description
»»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»» offset|integer(int32)|false|No description
»»»» dailyNet|number|false|No description
»»»» dailySellingRate|number|false|No description
keyword|[[ApiKeyword](#schemaapikeyword)]|false|No description
» code|integer(int32)|true|No description
» rating|integer(int32)|false|No description
review|[[ApiReview](#schemaapireview)]|false|No description
» rate|number|false|No description
» reviewCount|integer(int32)|false|No description
» type|string|false|No description
room|[[room](#schemaroom)]|false|No description
» status|string|false|No description
» id|integer(int32)|false|No description
» code|string|false|No description
» name|string|false|No description
» pax|[[ApiPax](#schemaapipax)]|false|No description
»» roomId|integer(int32)|false|No description
»» type|string|true|No description
»» age|integer(int32)|false|No description
»» name|string|false|No description
»» surname|string|false|No description
» rate|[[ApiRate](#schemaapirate)]|false|No description
»» rateKey|string|false|No description
»» rateClass|string|false|No description
»» rateType|string|false|No description
»» net|number|false|No description
»» discount|number|false|No description
»» discountPCT|number|false|No description
»» sellingRate|number|false|No description
»» hotelSellingRate|number|false|No description
»» amount|number|false|No description
»» hotelCurrency|string|false|No description
»» hotelMandatory|boolean|false|No description
»» allotment|integer(int32)|false|No description
»» commission|number|false|No description
»» commissionVAT|number|false|No description
»» commissionPCT|number|false|No description
»» cost|[ApiCost](#schemaapicost)|false|No description
»»» amount|number|false|No description
»»» currency|string|false|No description
»» rateCommentsId|string|false|No description
»» rateComments|string|false|No description
»» paymentType|string|false|No description
»» packaging|boolean|false|No description
»» boardCode|string|false|No description
»» boardName|string|false|No description
»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»» code|string|false|No description
»»»» name|string|false|No description
»»»» amount|number|false|No description
»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»» code|string|false|No description
»»»» name|string|false|No description
»»»» from|string(date)|false|No description
»»»» to|string(date)|false|No description
»»»» amount|number|false|No description
»»»» nights|integer(int32)|false|No description
»»»» paxNumber|integer(int32)|false|No description
»» rooms|integer(int32)|false|No description
»» adults|integer(int32)|false|No description
»» children|integer(int32)|false|No description
»» childrenAges|string|false|No description
»» rateup|number|false|No description
»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»» allIncluded|boolean|false|No description
»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»» included|boolean|false|No description
»»»» percent|number|false|No description
»»»» amount|number|false|No description
»»»» currency|string|false|No description
»»»» type|string|false|No description
»»»» clientAmount|number|false|No description
»»»» clientCurrency|string|false|No description
»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»» type|string|false|No description
»»» text|string|false|No description
»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»» amount|number|false|No description
»»» hotelAmount|number|false|No description
»»» hotelCurrency|string|false|No description
»»» from|string|false|No description
»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»» code|string|false|No description
»»» name|string|false|No description
»»» remark|string|false|No description
»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»» code|string|false|No description
»»» name|string|false|No description
»»» amount|number|false|No description
»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»» rateKey|string|false|No description
»»» rateClass|string|false|No description
»»» rateType|string|false|No description
»»» net|number|false|No description
»»» discount|number|false|No description
»»» discountPCT|number|false|No description
»»» sellingRate|number|false|No description
»»» hotelSellingRate|number|false|No description
»»» amount|number|false|No description
»»» hotelCurrency|string|false|No description
»»» hotelMandatory|boolean|false|No description
»»» allotment|integer(int32)|false|No description
»»» commission|number|false|No description
»»» commissionVAT|number|false|No description
»»» commissionPCT|number|false|No description
»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»» amount|number|false|No description
»»»» currency|string|false|No description
»»» checkIn|string(date)|false|No description
»»» checkOut|string(date)|false|No description
»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»» offset|integer(int32)|false|No description
»»» dailyNet|number|false|No description
»»» dailySellingRate|number|false|No description
creditCard|[[ApiCreditCard](#schemaapicreditcard)]|false|No description
» code|string|false|No description
» name|string|false|No description
» paymentType|string|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
»» status|NEW|
»» status|PRECONFIRMED|
»» status|CONFIRMED|
»» status|TO_BE_UPDATED|
»» status|CANCELLED|
»» status|TO_BE_CANCELLED|
»»» type|AD|
»»» type|CH|
»»» rateType|BOOKABLE|
»»» rateType|RECHECK|
»»» paymentType|AT_HOTEL|
»»» paymentType|AT_WEB|
»»»»» type|TAX|
»»»»» type|FEE|
»»»» rateType|BOOKABLE|
»»»» rateType|RECHECK|
» status|NEW|
» status|PRECONFIRMED|
» status|CONFIRMED|
» status|TO_BE_UPDATED|
» status|CANCELLED|
» status|TO_BE_CANCELLED|
»» type|AD|
»» type|CH|
»» rateType|BOOKABLE|
»» rateType|RECHECK|
»» paymentType|AT_HOTEL|
»» paymentType|AT_WEB|
»»»» type|TAX|
»»»» type|FEE|
»»» rateType|BOOKABLE|
»»» rateType|RECHECK|
» paymentType|AT_HOTEL|
» paymentType|AT_WEB|


## ApiHotels

<a name="schemaapihotels"></a>

```json
{
  "checkIn": "2017-10-21",
  "checkOut": "2017-10-21",
  "hotel": [
    {
      "checkOut": "2017-10-21",
      "checkIn": "2017-10-21",
      "code": 0,
      "name": "string",
      "description": "string",
      "image": "string",
      "categoryCode": "string",
      "categoryName": "string",
      "destinationCode": "string",
      "destinationName": "string",
      "zoneCode": 0,
      "zoneName": "string",
      "latitude": "string",
      "longitude": "string",
      "giata": "string",
      "minRate": 0,
      "maxRate": 0,
      "totalSellingRate": 0,
      "totalNet": 0,
      "pendingAmount": 0,
      "currency": "string",
      "supplier": {
        "name": "string",
        "vatNumber": "string"
      },
      "clientComments": "string",
      "cancellationAmount": 0,
      "upselling": {
        "room": [
          {
            "status": "NEW",
            "id": 0,
            "code": "string",
            "name": "string",
            "pax": [
              {
                "roomId": 1,
                "type": "AD",
                "age": 20,
                "name": "string",
                "surname": "string"
              }
            ],
            "rate": [
              {
                "rateKey": "string",
                "rateClass": "string",
                "rateType": "BOOKABLE",
                "net": 0,
                "discount": 0,
                "discountPCT": 0,
                "sellingRate": 0,
                "hotelSellingRate": 0,
                "amount": 0,
                "hotelCurrency": "string",
                "hotelMandatory": false,
                "allotment": 0,
                "commission": 0,
                "commissionVAT": 0,
                "commissionPCT": 0,
                "cost": {
                  "amount": 0,
                  "currency": "string"
                },
                "rateCommentsId": "string",
                "rateComments": "string",
                "paymentType": "AT_HOTEL",
                "packaging": false,
                "boardCode": "string",
                "boardName": "string",
                "rateBreakDown": {
                  "rateDiscount": [
                    {
                      "code": "string",
                      "name": "string",
                      "amount": 0
                    }
                  ],
                  "rateSupplement": [
                    {
                      "code": "string",
                      "name": "string",
                      "from": "2017-10-21",
                      "to": "2017-10-21",
                      "amount": 0,
                      "nights": 0,
                      "paxNumber": 0
                    }
                  ]
                },
                "rooms": 0,
                "adults": 0,
                "children": 0,
                "childrenAges": "string",
                "rateup": 0,
                "comment": [
                  {
                    "type": "string",
                    "text": "string"
                  }
                ],
                "cancellationPolicy": [
                  {
                    "amount": 0,
                    "hotelAmount": 0,
                    "hotelCurrency": "string",
                    "from": "string"
                  }
                ],
                "taxes": {
                  "allIncluded": false,
                  "tax": [
                    {
                      "included": false,
                      "percent": 0,
                      "amount": 0,
                      "currency": "string",
                      "type": "TAX",
                      "clientAmount": 0,
                      "clientCurrency": "string"
                    }
                  ]
                },
                "promotion": [
                  {
                    "code": "string",
                    "name": "string",
                    "remark": "string"
                  }
                ],
                "offer": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "shiftRate": [
                  {
                    "rateKey": "string",
                    "rateClass": "string",
                    "rateType": "BOOKABLE",
                    "net": 0,
                    "discount": 0,
                    "discountPCT": 0,
                    "sellingRate": 0,
                    "hotelSellingRate": 0,
                    "amount": 0,
                    "hotelCurrency": "string",
                    "hotelMandatory": false,
                    "allotment": 0,
                    "commission": 0,
                    "commissionVAT": 0,
                    "commissionPCT": 0,
                    "cost": {
                      "amount": 0,
                      "currency": "string"
                    },
                    "checkIn": "2017-10-21",
                    "checkOut": "2017-10-21"
                  }
                ],
                "dailyRate": [
                  {
                    "offset": 0,
                    "dailyNet": 0,
                    "dailySellingRate": 0
                  }
                ]
              }
            ]
          }
        ]
      },
      "keyword": [
        {
          "code": 0,
          "rating": 0
        }
      ],
      "review": [
        {
          "rate": 0,
          "reviewCount": 0,
          "type": "string"
        }
      ],
      "room": [
        {
          "status": "NEW",
          "id": 0,
          "code": "string",
          "name": "string",
          "pax": [
            {
              "roomId": 1,
              "type": "AD",
              "age": 20,
              "name": "string",
              "surname": "string"
            }
          ],
          "rate": [
            {
              "rateKey": "string",
              "rateClass": "string",
              "rateType": "BOOKABLE",
              "net": 0,
              "discount": 0,
              "discountPCT": 0,
              "sellingRate": 0,
              "hotelSellingRate": 0,
              "amount": 0,
              "hotelCurrency": "string",
              "hotelMandatory": false,
              "allotment": 0,
              "commission": 0,
              "commissionVAT": 0,
              "commissionPCT": 0,
              "cost": {
                "amount": 0,
                "currency": "string"
              },
              "rateCommentsId": "string",
              "rateComments": "string",
              "paymentType": "AT_HOTEL",
              "packaging": false,
              "boardCode": "string",
              "boardName": "string",
              "rateBreakDown": {
                "rateDiscount": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "rateSupplement": [
                  {
                    "code": "string",
                    "name": "string",
                    "from": "2017-10-21",
                    "to": "2017-10-21",
                    "amount": 0,
                    "nights": 0,
                    "paxNumber": 0
                  }
                ]
              },
              "rooms": 0,
              "adults": 0,
              "children": 0,
              "childrenAges": "string",
              "rateup": 0,
              "comment": [
                {
                  "type": "string",
                  "text": "string"
                }
              ],
              "cancellationPolicy": [
                {
                  "amount": 0,
                  "hotelAmount": 0,
                  "hotelCurrency": "string",
                  "from": "string"
                }
              ],
              "taxes": {
                "allIncluded": false,
                "tax": [
                  {
                    "included": false,
                    "percent": 0,
                    "amount": 0,
                    "currency": "string",
                    "type": "TAX",
                    "clientAmount": 0,
                    "clientCurrency": "string"
                  }
                ]
              },
              "promotion": [
                {
                  "code": "string",
                  "name": "string",
                  "remark": "string"
                }
              ],
              "offer": [
                {
                  "code": "string",
                  "name": "string",
                  "amount": 0
                }
              ],
              "shiftRate": [
                {
                  "rateKey": "string",
                  "rateClass": "string",
                  "rateType": "BOOKABLE",
                  "net": 0,
                  "discount": 0,
                  "discountPCT": 0,
                  "sellingRate": 0,
                  "hotelSellingRate": 0,
                  "amount": 0,
                  "hotelCurrency": "string",
                  "hotelMandatory": false,
                  "allotment": 0,
                  "commission": 0,
                  "commissionVAT": 0,
                  "commissionPCT": 0,
                  "cost": {
                    "amount": 0,
                    "currency": "string"
                  },
                  "checkIn": "2017-10-21",
                  "checkOut": "2017-10-21"
                }
              ],
              "dailyRate": [
                {
                  "offset": 0,
                  "dailyNet": 0,
                  "dailySellingRate": 0
                }
              ]
            }
          ]
        }
      ],
      "creditCard": [
        {
          "code": "string",
          "name": "string",
          "paymentType": "AT_HOTEL"
        }
      ]
    }
  ],
  "total": 0
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
checkIn|string(date)|false|No description
checkOut|string(date)|false|No description
total|integer(int32)|false|No description
hotel|[[ApiHotel](#schemaapihotel)]|false|No description
» checkOut|string(date)|false|No description
» checkIn|string(date)|false|No description
» code|integer(int32)|false|No description
» name|string|false|No description
» description|string|false|No description
» image|string|false|No description
» categoryCode|string|false|No description
» categoryName|string|false|No description
» destinationCode|string|false|No description
» destinationName|string|false|No description
» zoneCode|integer(int32)|false|No description
» zoneName|string|false|No description
» latitude|string|false|No description
» longitude|string|false|No description
» giata|string|false|No description
» minRate|number|false|No description
» maxRate|number|false|No description
» totalSellingRate|number|false|No description
» totalNet|number|false|No description
» pendingAmount|number|false|No description
» currency|string|false|No description
» supplier|[ApiSupplier](#schemaapisupplier)|false|No description
»» name|string|false|No description
»» vatNumber|string|false|No description
» clientComments|string|false|No description
» cancellationAmount|number|false|No description
» upselling|[ApiUpselling](#schemaapiupselling)|false|No description
»» room|[[room](#schemaroom)]|false|No description
»»» status|string|false|No description
»»» id|integer(int32)|false|No description
»»» code|string|false|No description
»»» name|string|false|No description
»»» pax|[[ApiPax](#schemaapipax)]|false|No description
»»»» roomId|integer(int32)|false|No description
»»»» type|string|true|No description
»»»» age|integer(int32)|false|No description
»»»» name|string|false|No description
»»»» surname|string|false|No description
»»» rate|[[ApiRate](#schemaapirate)]|false|No description
»»»» rateKey|string|false|No description
»»»» rateClass|string|false|No description
»»»» rateType|string|false|No description
»»»» net|number|false|No description
»»»» discount|number|false|No description
»»»» discountPCT|number|false|No description
»»»» sellingRate|number|false|No description
»»»» hotelSellingRate|number|false|No description
»»»» amount|number|false|No description
»»»» hotelCurrency|string|false|No description
»»»» hotelMandatory|boolean|false|No description
»»»» allotment|integer(int32)|false|No description
»»»» commission|number|false|No description
»»»» commissionVAT|number|false|No description
»»»» commissionPCT|number|false|No description
»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»» amount|number|false|No description
»»»»» currency|string|false|No description
»»»» rateCommentsId|string|false|No description
»»»» rateComments|string|false|No description
»»»» paymentType|string|false|No description
»»»» packaging|boolean|false|No description
»»»» boardCode|string|false|No description
»»»» boardName|string|false|No description
»»»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» amount|number|false|No description
»»»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» from|string(date)|false|No description
»»»»»» to|string(date)|false|No description
»»»»»» amount|number|false|No description
»»»»»» nights|integer(int32)|false|No description
»»»»»» paxNumber|integer(int32)|false|No description
»»»» rooms|integer(int32)|false|No description
»»»» adults|integer(int32)|false|No description
»»»» children|integer(int32)|false|No description
»»»» childrenAges|string|false|No description
»»»» rateup|number|false|No description
»»»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»»»» allIncluded|boolean|false|No description
»»»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»»»» included|boolean|false|No description
»»»»»» percent|number|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»»» type|string|false|No description
»»»»»» clientAmount|number|false|No description
»»»»»» clientCurrency|string|false|No description
»»»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»»» type|string|false|No description
»»»»» text|string|false|No description
»»»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»»» amount|number|false|No description
»»»»» hotelAmount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» from|string|false|No description
»»»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» remark|string|false|No description
»»»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» amount|number|false|No description
»»»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»»» rateKey|string|false|No description
»»»»» rateClass|string|false|No description
»»»»» rateType|string|false|No description
»»»»» net|number|false|No description
»»»»» discount|number|false|No description
»»»»» discountPCT|number|false|No description
»»»»» sellingRate|number|false|No description
»»»»» hotelSellingRate|number|false|No description
»»»»» amount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» hotelMandatory|boolean|false|No description
»»»»» allotment|integer(int32)|false|No description
»»»»» commission|number|false|No description
»»»»» commissionVAT|number|false|No description
»»»»» commissionPCT|number|false|No description
»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»» checkIn|string(date)|false|No description
»»»»» checkOut|string(date)|false|No description
»»»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»»» offset|integer(int32)|false|No description
»»»»» dailyNet|number|false|No description
»»»»» dailySellingRate|number|false|No description
» keyword|[[ApiKeyword](#schemaapikeyword)]|false|No description
»» code|integer(int32)|true|No description
»» rating|integer(int32)|false|No description
» review|[[ApiReview](#schemaapireview)]|false|No description
»» rate|number|false|No description
»» reviewCount|integer(int32)|false|No description
»» type|string|false|No description
» room|[[room](#schemaroom)]|false|No description
»» status|string|false|No description
»» id|integer(int32)|false|No description
»» code|string|false|No description
»» name|string|false|No description
»» pax|[[ApiPax](#schemaapipax)]|false|No description
»»» roomId|integer(int32)|false|No description
»»» type|string|true|No description
»»» age|integer(int32)|false|No description
»»» name|string|false|No description
»»» surname|string|false|No description
»» rate|[[ApiRate](#schemaapirate)]|false|No description
»»» rateKey|string|false|No description
»»» rateClass|string|false|No description
»»» rateType|string|false|No description
»»» net|number|false|No description
»»» discount|number|false|No description
»»» discountPCT|number|false|No description
»»» sellingRate|number|false|No description
»»» hotelSellingRate|number|false|No description
»»» amount|number|false|No description
»»» hotelCurrency|string|false|No description
»»» hotelMandatory|boolean|false|No description
»»» allotment|integer(int32)|false|No description
»»» commission|number|false|No description
»»» commissionVAT|number|false|No description
»»» commissionPCT|number|false|No description
»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»» amount|number|false|No description
»»»» currency|string|false|No description
»»» rateCommentsId|string|false|No description
»»» rateComments|string|false|No description
»»» paymentType|string|false|No description
»»» packaging|boolean|false|No description
»»» boardCode|string|false|No description
»»» boardName|string|false|No description
»»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» amount|number|false|No description
»»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» from|string(date)|false|No description
»»»»» to|string(date)|false|No description
»»»»» amount|number|false|No description
»»»»» nights|integer(int32)|false|No description
»»»»» paxNumber|integer(int32)|false|No description
»»» rooms|integer(int32)|false|No description
»»» adults|integer(int32)|false|No description
»»» children|integer(int32)|false|No description
»»» childrenAges|string|false|No description
»»» rateup|number|false|No description
»»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»»» allIncluded|boolean|false|No description
»»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»»» included|boolean|false|No description
»»»»» percent|number|false|No description
»»»»» amount|number|false|No description
»»»»» currency|string|false|No description
»»»»» type|string|false|No description
»»»»» clientAmount|number|false|No description
»»»»» clientCurrency|string|false|No description
»»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»» type|string|false|No description
»»»» text|string|false|No description
»»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»» amount|number|false|No description
»»»» hotelAmount|number|false|No description
»»»» hotelCurrency|string|false|No description
»»»» from|string|false|No description
»»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»» code|string|false|No description
»»»» name|string|false|No description
»»»» remark|string|false|No description
»»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»»» code|string|false|No description
»»»» name|string|false|No description
»»»» amount|number|false|No description
»»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»» rateKey|string|false|No description
»»»» rateClass|string|false|No description
»»»» rateType|string|false|No description
»»»» net|number|false|No description
»»»» discount|number|false|No description
»»»» discountPCT|number|false|No description
»»»» sellingRate|number|false|No description
»»»» hotelSellingRate|number|false|No description
»»»» amount|number|false|No description
»»»» hotelCurrency|string|false|No description
»»»» hotelMandatory|boolean|false|No description
»»»» allotment|integer(int32)|false|No description
»»»» commission|number|false|No description
»»»» commissionVAT|number|false|No description
»»»» commissionPCT|number|false|No description
»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»» amount|number|false|No description
»»»»» currency|string|false|No description
»»»» checkIn|string(date)|false|No description
»»»» checkOut|string(date)|false|No description
»»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»» offset|integer(int32)|false|No description
»»»» dailyNet|number|false|No description
»»»» dailySellingRate|number|false|No description
» creditCard|[[ApiCreditCard](#schemaapicreditcard)]|false|No description
»» code|string|false|No description
»» name|string|false|No description
»» paymentType|string|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
»»» status|NEW|
»»» status|PRECONFIRMED|
»»» status|CONFIRMED|
»»» status|TO_BE_UPDATED|
»»» status|CANCELLED|
»»» status|TO_BE_CANCELLED|
»»»» type|AD|
»»»» type|CH|
»»»» rateType|BOOKABLE|
»»»» rateType|RECHECK|
»»»» paymentType|AT_HOTEL|
»»»» paymentType|AT_WEB|
»»»»»» type|TAX|
»»»»»» type|FEE|
»»»»» rateType|BOOKABLE|
»»»»» rateType|RECHECK|
»» status|NEW|
»» status|PRECONFIRMED|
»» status|CONFIRMED|
»» status|TO_BE_UPDATED|
»» status|CANCELLED|
»» status|TO_BE_CANCELLED|
»»» type|AD|
»»» type|CH|
»»» rateType|BOOKABLE|
»»» rateType|RECHECK|
»»» paymentType|AT_HOTEL|
»»» paymentType|AT_WEB|
»»»»» type|TAX|
»»»»» type|FEE|
»»»» rateType|BOOKABLE|
»»»» rateType|RECHECK|
»» paymentType|AT_HOTEL|
»» paymentType|AT_WEB|


## ApiHotelsFilter

<a name="schemaapihotelsfilter"></a>

```json
{
  "included": false,
  "type": "HOTELBEDS",
  "hotel": [
    0
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
included|boolean|false|No description
type|string|false|No description
hotel|[integer(int32)]|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
type|HOTELBEDS|
type|GIATA|


## ApiKeyword

<a name="schemaapikeyword"></a>

```json
{
  "code": 0,
  "rating": 0
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
code|integer(int32)|true|No description
rating|integer(int32)|false|No description



## ApiKeywordsFilter

<a name="schemaapikeywordsfilter"></a>

```json
{
  "allIncluded": false,
  "keyword": [
    0
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
allIncluded|boolean|false|No description
keyword|[integer(int32)]|false|No description



## ApiModificationPolicies

<a name="schemaapimodificationpolicies"></a>

```json
{
  "cancellation": false,
  "modification": false
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
cancellation|boolean|true|No description
modification|boolean|true|No description



## ApiOccupancy

<a name="schemaapioccupancy"></a>

```json
{
  "rooms": 1,
  "adults": 2,
  "children": 0,
  "pax": [
    {
      "roomId": 1,
      "type": "AD",
      "age": 20,
      "name": "string",
      "surname": "string"
    }
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
rooms|integer(int32)|true|No description
adults|integer(int32)|true|No description
children|integer(int32)|true|No description
pax|[[ApiPax](#schemaapipax)]|false|No description
» roomId|integer(int32)|false|No description
» type|string|true|No description
» age|integer(int32)|false|No description
» name|string|false|No description
» surname|string|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
» type|AD|
» type|CH|


## ApiOffer

<a name="schemaapioffer"></a>

```json
{
  "code": "string",
  "name": "string",
  "amount": 0
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
code|string|false|No description
name|string|false|No description
amount|number|false|No description



## ApiPax

<a name="schemaapipax"></a>

```json
{
  "roomId": 1,
  "type": "AD",
  "age": 20,
  "name": "string",
  "surname": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
roomId|integer(int32)|false|No description
type|string|true|No description
age|integer(int32)|false|No description
name|string|false|No description
surname|string|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
type|AD|
type|CH|


## ApiPaymentCard

<a name="schemaapipaymentcard"></a>

```json
{
  "cardType": "string",
  "cardNumber": "string",
  "cardHolderName": "string",
  "expiryDate": "string",
  "cardCVC": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
cardType|string|false|No description
cardNumber|string|false|No description
cardHolderName|string|false|No description
expiryDate|string|false|No description
cardCVC|string|false|No description



## ApiPaymentContactData

<a name="schemaapipaymentcontactdata"></a>

```json
{
  "email": "string",
  "phoneNumber": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
email|string|false|No description
phoneNumber|string|false|No description



## ApiPaymentData

<a name="schemaapipaymentdata"></a>

```json
{
  "paymentCard": {
    "cardType": "string",
    "cardNumber": "string",
    "cardHolderName": "string",
    "expiryDate": "string",
    "cardCVC": "string"
  },
  "contactData": {
    "email": "string",
    "phoneNumber": "string"
  },
  "billingAddress": {
    "address1": "string",
    "address2": "string",
    "city": "string",
    "state": "string",
    "postalCode": "string",
    "countryCode": "string"
  },
  "webPartner": 0,
  "device": {
    "id": "string",
    "ip": "string"
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
paymentCard|[ApiPaymentCard](#schemaapipaymentcard)|true|No description
» cardType|string|false|No description
» cardNumber|string|false|No description
» cardHolderName|string|false|No description
» expiryDate|string|false|No description
» cardCVC|string|false|No description
contactData|[ApiPaymentContactData](#schemaapipaymentcontactdata)|true|No description
» email|string|false|No description
» phoneNumber|string|false|No description
billingAddress|[ApiBillingAddress](#schemaapibillingaddress)|false|No description
» address1|string|false|No description
» address2|string|false|No description
» city|string|false|No description
» state|string|false|No description
» postalCode|string|false|No description
» countryCode|string|false|No description
webPartner|integer(int32)|false|No description
device|[ApiBookingDevice](#schemaapibookingdevice)|false|No description
» id|string|false|No description
» ip|string|false|No description



## ApiPromotion

<a name="schemaapipromotion"></a>

```json
{
  "code": "string",
  "name": "string",
  "remark": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
code|string|false|No description
name|string|false|No description
remark|string|false|No description



## ApiRate

<a name="schemaapirate"></a>

```json
{
  "rateKey": "string",
  "rateClass": "string",
  "rateType": "BOOKABLE",
  "net": 0,
  "discount": 0,
  "discountPCT": 0,
  "sellingRate": 0,
  "hotelSellingRate": 0,
  "amount": 0,
  "hotelCurrency": "string",
  "hotelMandatory": false,
  "allotment": 0,
  "commission": 0,
  "commissionVAT": 0,
  "commissionPCT": 0,
  "cost": {
    "amount": 0,
    "currency": "string"
  },
  "rateCommentsId": "string",
  "rateComments": "string",
  "paymentType": "AT_HOTEL",
  "packaging": false,
  "boardCode": "string",
  "boardName": "string",
  "rateBreakDown": {
    "rateDiscount": [
      {
        "code": "string",
        "name": "string",
        "amount": 0
      }
    ],
    "rateSupplement": [
      {
        "code": "string",
        "name": "string",
        "from": "2017-10-21",
        "to": "2017-10-21",
        "amount": 0,
        "nights": 0,
        "paxNumber": 0
      }
    ]
  },
  "rooms": 0,
  "adults": 0,
  "children": 0,
  "childrenAges": "string",
  "rateup": 0,
  "comment": [
    {
      "type": "string",
      "text": "string"
    }
  ],
  "cancellationPolicy": [
    {
      "amount": 0,
      "hotelAmount": 0,
      "hotelCurrency": "string",
      "from": "string"
    }
  ],
  "taxes": {
    "allIncluded": false,
    "tax": [
      {
        "included": false,
        "percent": 0,
        "amount": 0,
        "currency": "string",
        "type": "TAX",
        "clientAmount": 0,
        "clientCurrency": "string"
      }
    ]
  },
  "promotion": [
    {
      "code": "string",
      "name": "string",
      "remark": "string"
    }
  ],
  "offer": [
    {
      "code": "string",
      "name": "string",
      "amount": 0
    }
  ],
  "shiftRate": [
    {
      "rateKey": "string",
      "rateClass": "string",
      "rateType": "BOOKABLE",
      "net": 0,
      "discount": 0,
      "discountPCT": 0,
      "sellingRate": 0,
      "hotelSellingRate": 0,
      "amount": 0,
      "hotelCurrency": "string",
      "hotelMandatory": false,
      "allotment": 0,
      "commission": 0,
      "commissionVAT": 0,
      "commissionPCT": 0,
      "cost": {
        "amount": 0,
        "currency": "string"
      },
      "checkIn": "2017-10-21",
      "checkOut": "2017-10-21"
    }
  ],
  "dailyRate": [
    {
      "offset": 0,
      "dailyNet": 0,
      "dailySellingRate": 0
    }
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
rateKey|string|false|No description
rateClass|string|false|No description
rateType|string|false|No description
net|number|false|No description
discount|number|false|No description
discountPCT|number|false|No description
sellingRate|number|false|No description
hotelSellingRate|number|false|No description
amount|number|false|No description
hotelCurrency|string|false|No description
hotelMandatory|boolean|false|No description
allotment|integer(int32)|false|No description
commission|number|false|No description
commissionVAT|number|false|No description
commissionPCT|number|false|No description
cost|[ApiCost](#schemaapicost)|false|No description
» amount|number|false|No description
» currency|string|false|No description
rateCommentsId|string|false|No description
rateComments|string|false|No description
paymentType|string|false|No description
packaging|boolean|false|No description
boardCode|string|false|No description
boardName|string|false|No description
rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»» code|string|false|No description
»» name|string|false|No description
»» amount|number|false|No description
» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»» code|string|false|No description
»» name|string|false|No description
»» from|string(date)|false|No description
»» to|string(date)|false|No description
»» amount|number|false|No description
»» nights|integer(int32)|false|No description
»» paxNumber|integer(int32)|false|No description
rooms|integer(int32)|false|No description
adults|integer(int32)|false|No description
children|integer(int32)|false|No description
childrenAges|string|false|No description
rateup|number|false|No description
taxes|[ApiTaxes](#schemaapitaxes)|false|No description
» allIncluded|boolean|false|No description
» tax|[[ApiTax](#schemaapitax)]|false|No description
»» included|boolean|false|No description
»» percent|number|false|No description
»» amount|number|false|No description
»» currency|string|false|No description
»» type|string|false|No description
»» clientAmount|number|false|No description
»» clientCurrency|string|false|No description
comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
» type|string|false|No description
» text|string|false|No description
cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
» amount|number|false|No description
» hotelAmount|number|false|No description
» hotelCurrency|string|false|No description
» from|string|false|No description
promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
» code|string|false|No description
» name|string|false|No description
» remark|string|false|No description
offer|[[ApiOffer](#schemaapioffer)]|false|No description
» code|string|false|No description
» name|string|false|No description
» amount|number|false|No description
shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
» rateKey|string|false|No description
» rateClass|string|false|No description
» rateType|string|false|No description
» net|number|false|No description
» discount|number|false|No description
» discountPCT|number|false|No description
» sellingRate|number|false|No description
» hotelSellingRate|number|false|No description
» amount|number|false|No description
» hotelCurrency|string|false|No description
» hotelMandatory|boolean|false|No description
» allotment|integer(int32)|false|No description
» commission|number|false|No description
» commissionVAT|number|false|No description
» commissionPCT|number|false|No description
» cost|[ApiCost](#schemaapicost)|false|No description
»» amount|number|false|No description
»» currency|string|false|No description
» checkIn|string(date)|false|No description
» checkOut|string(date)|false|No description
dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
» offset|integer(int32)|false|No description
» dailyNet|number|false|No description
» dailySellingRate|number|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
rateType|BOOKABLE|
rateType|RECHECK|
paymentType|AT_HOTEL|
paymentType|AT_WEB|
»» type|TAX|
»» type|FEE|
» rateType|BOOKABLE|
» rateType|RECHECK|


## ApiRateBreakDown

<a name="schemaapiratebreakdown"></a>

```json
{
  "rateDiscount": [
    {
      "code": "string",
      "name": "string",
      "amount": 0
    }
  ],
  "rateSupplement": [
    {
      "code": "string",
      "name": "string",
      "from": "2017-10-21",
      "to": "2017-10-21",
      "amount": 0,
      "nights": 0,
      "paxNumber": 0
    }
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
» code|string|false|No description
» name|string|false|No description
» amount|number|false|No description
rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
» code|string|false|No description
» name|string|false|No description
» from|string(date)|false|No description
» to|string(date)|false|No description
» amount|number|false|No description
» nights|integer(int32)|false|No description
» paxNumber|integer(int32)|false|No description



## ApiRateDiscount

<a name="schemaapiratediscount"></a>

```json
{
  "code": "string",
  "name": "string",
  "amount": 0
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
code|string|false|No description
name|string|false|No description
amount|number|false|No description



## ApiRateSupplement

<a name="schemaapiratesupplement"></a>

```json
{
  "code": "string",
  "name": "string",
  "from": "2017-10-21",
  "to": "2017-10-21",
  "amount": 0,
  "nights": 0,
  "paxNumber": 0
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
code|string|false|No description
name|string|false|No description
from|string(date)|false|No description
to|string(date)|false|No description
amount|number|false|No description
nights|integer(int32)|false|No description
paxNumber|integer(int32)|false|No description



## ApiReview

<a name="schemaapireview"></a>

```json
{
  "rate": 0,
  "reviewCount": 0,
  "type": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
rate|number|false|No description
reviewCount|integer(int32)|false|No description
type|string|false|No description



## ApiReviewFilter

<a name="schemaapireviewfilter"></a>

```json
{
  "type": "TRIPADVISOR",
  "minRate": 0,
  "maxRate": 1,
  "minReviewCount": 1
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
type|string|true|No description
minRate|number|false|No description
maxRate|number|false|No description
minReviewCount|integer(int32)|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
type|TRIPADVISOR|
type|HOTELBEDS|


## ApiRooms

<a name="schemaapirooms"></a>

```json
{
  "room": [
    "string"
  ],
  "included": false
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
included|boolean|true|No description
room|[string]|false|No description



## ApiShiftRate

<a name="schemaapishiftrate"></a>

```json
{
  "rateKey": "string",
  "rateClass": "string",
  "rateType": "BOOKABLE",
  "net": 0,
  "discount": 0,
  "discountPCT": 0,
  "sellingRate": 0,
  "hotelSellingRate": 0,
  "amount": 0,
  "hotelCurrency": "string",
  "hotelMandatory": false,
  "allotment": 0,
  "commission": 0,
  "commissionVAT": 0,
  "commissionPCT": 0,
  "cost": {
    "amount": 0,
    "currency": "string"
  },
  "checkIn": "2017-10-21",
  "checkOut": "2017-10-21"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
rateKey|string|false|No description
rateClass|string|false|No description
rateType|string|false|No description
net|number|false|No description
discount|number|false|No description
discountPCT|number|false|No description
sellingRate|number|false|No description
hotelSellingRate|number|false|No description
amount|number|false|No description
hotelCurrency|string|false|No description
hotelMandatory|boolean|false|No description
allotment|integer(int32)|false|No description
commission|number|false|No description
commissionVAT|number|false|No description
commissionPCT|number|false|No description
cost|[ApiCost](#schemaapicost)|false|No description
» amount|number|false|No description
» currency|string|false|No description
checkIn|string(date)|false|No description
checkOut|string(date)|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
rateType|BOOKABLE|
rateType|RECHECK|


## ApiSource

<a name="schemaapisource"></a>

```json
{
  "channel": "B2B",
  "device": "WEB",
  "deviceInfo": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
channel|string|true|No description
device|string|true|No description
deviceInfo|string|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
channel|B2B|
channel|B2C|
channel|META|
channel|NEWSLETTER|
device|MOBILE|
device|WEB|
device|TABLET|


## ApiStay

<a name="schemaapistay"></a>

```json
{
  "checkIn": "2017-09-21",
  "checkOut": "2017-09-23",
  "shiftDays": 3,
  "allowOnlyShift": false
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
checkIn|string(date)|true|Check-in date
checkOut|string(date)|true|Check-out date
shiftDays|integer(int32)|false|No description
allowOnlyShift|boolean|false|No description



## ApiSupplier

<a name="schemaapisupplier"></a>

```json
{
  "name": "string",
  "vatNumber": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
name|string|false|No description
vatNumber|string|false|No description



## ApiTax

<a name="schemaapitax"></a>

```json
{
  "included": false,
  "percent": 0,
  "amount": 0,
  "currency": "string",
  "type": "TAX",
  "clientAmount": 0,
  "clientCurrency": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
included|boolean|false|No description
percent|number|false|No description
amount|number|false|No description
currency|string|false|No description
type|string|false|No description
clientAmount|number|false|No description
clientCurrency|string|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
type|TAX|
type|FEE|


## ApiTaxes

<a name="schemaapitaxes"></a>

```json
{
  "allIncluded": false,
  "tax": [
    {
      "included": false,
      "percent": 0,
      "amount": 0,
      "currency": "string",
      "type": "TAX",
      "clientAmount": 0,
      "clientCurrency": "string"
    }
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
allIncluded|boolean|false|No description
tax|[[ApiTax](#schemaapitax)]|false|No description
» included|boolean|false|No description
» percent|number|false|No description
» amount|number|false|No description
» currency|string|false|No description
» type|string|false|No description
» clientAmount|number|false|No description
» clientCurrency|string|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
» type|TAX|
» type|FEE|


## ApiUpselling

<a name="schemaapiupselling"></a>

```json
{
  "room": [
    {
      "status": "NEW",
      "id": 0,
      "code": "string",
      "name": "string",
      "pax": [
        {
          "roomId": 1,
          "type": "AD",
          "age": 20,
          "name": "string",
          "surname": "string"
        }
      ],
      "rate": [
        {
          "rateKey": "string",
          "rateClass": "string",
          "rateType": "BOOKABLE",
          "net": 0,
          "discount": 0,
          "discountPCT": 0,
          "sellingRate": 0,
          "hotelSellingRate": 0,
          "amount": 0,
          "hotelCurrency": "string",
          "hotelMandatory": false,
          "allotment": 0,
          "commission": 0,
          "commissionVAT": 0,
          "commissionPCT": 0,
          "cost": {
            "amount": 0,
            "currency": "string"
          },
          "rateCommentsId": "string",
          "rateComments": "string",
          "paymentType": "AT_HOTEL",
          "packaging": false,
          "boardCode": "string",
          "boardName": "string",
          "rateBreakDown": {
            "rateDiscount": [
              {
                "code": "string",
                "name": "string",
                "amount": 0
              }
            ],
            "rateSupplement": [
              {
                "code": "string",
                "name": "string",
                "from": "2017-10-21",
                "to": "2017-10-21",
                "amount": 0,
                "nights": 0,
                "paxNumber": 0
              }
            ]
          },
          "rooms": 0,
          "adults": 0,
          "children": 0,
          "childrenAges": "string",
          "rateup": 0,
          "comment": [
            {
              "type": "string",
              "text": "string"
            }
          ],
          "cancellationPolicy": [
            {
              "amount": 0,
              "hotelAmount": 0,
              "hotelCurrency": "string",
              "from": "string"
            }
          ],
          "taxes": {
            "allIncluded": false,
            "tax": [
              {
                "included": false,
                "percent": 0,
                "amount": 0,
                "currency": "string",
                "type": "TAX",
                "clientAmount": 0,
                "clientCurrency": "string"
              }
            ]
          },
          "promotion": [
            {
              "code": "string",
              "name": "string",
              "remark": "string"
            }
          ],
          "offer": [
            {
              "code": "string",
              "name": "string",
              "amount": 0
            }
          ],
          "shiftRate": [
            {
              "rateKey": "string",
              "rateClass": "string",
              "rateType": "BOOKABLE",
              "net": 0,
              "discount": 0,
              "discountPCT": 0,
              "sellingRate": 0,
              "hotelSellingRate": 0,
              "amount": 0,
              "hotelCurrency": "string",
              "hotelMandatory": false,
              "allotment": 0,
              "commission": 0,
              "commissionVAT": 0,
              "commissionPCT": 0,
              "cost": {
                "amount": 0,
                "currency": "string"
              },
              "checkIn": "2017-10-21",
              "checkOut": "2017-10-21"
            }
          ],
          "dailyRate": [
            {
              "offset": 0,
              "dailyNet": 0,
              "dailySellingRate": 0
            }
          ]
        }
      ]
    }
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
room|[[room](#schemaroom)]|false|No description
» status|string|false|No description
» id|integer(int32)|false|No description
» code|string|false|No description
» name|string|false|No description
» pax|[[ApiPax](#schemaapipax)]|false|No description
»» roomId|integer(int32)|false|No description
»» type|string|true|No description
»» age|integer(int32)|false|No description
»» name|string|false|No description
»» surname|string|false|No description
» rate|[[ApiRate](#schemaapirate)]|false|No description
»» rateKey|string|false|No description
»» rateClass|string|false|No description
»» rateType|string|false|No description
»» net|number|false|No description
»» discount|number|false|No description
»» discountPCT|number|false|No description
»» sellingRate|number|false|No description
»» hotelSellingRate|number|false|No description
»» amount|number|false|No description
»» hotelCurrency|string|false|No description
»» hotelMandatory|boolean|false|No description
»» allotment|integer(int32)|false|No description
»» commission|number|false|No description
»» commissionVAT|number|false|No description
»» commissionPCT|number|false|No description
»» cost|[ApiCost](#schemaapicost)|false|No description
»»» amount|number|false|No description
»»» currency|string|false|No description
»» rateCommentsId|string|false|No description
»» rateComments|string|false|No description
»» paymentType|string|false|No description
»» packaging|boolean|false|No description
»» boardCode|string|false|No description
»» boardName|string|false|No description
»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»» code|string|false|No description
»»»» name|string|false|No description
»»»» amount|number|false|No description
»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»» code|string|false|No description
»»»» name|string|false|No description
»»»» from|string(date)|false|No description
»»»» to|string(date)|false|No description
»»»» amount|number|false|No description
»»»» nights|integer(int32)|false|No description
»»»» paxNumber|integer(int32)|false|No description
»» rooms|integer(int32)|false|No description
»» adults|integer(int32)|false|No description
»» children|integer(int32)|false|No description
»» childrenAges|string|false|No description
»» rateup|number|false|No description
»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»» allIncluded|boolean|false|No description
»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»» included|boolean|false|No description
»»»» percent|number|false|No description
»»»» amount|number|false|No description
»»»» currency|string|false|No description
»»»» type|string|false|No description
»»»» clientAmount|number|false|No description
»»»» clientCurrency|string|false|No description
»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»» type|string|false|No description
»»» text|string|false|No description
»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»» amount|number|false|No description
»»» hotelAmount|number|false|No description
»»» hotelCurrency|string|false|No description
»»» from|string|false|No description
»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»» code|string|false|No description
»»» name|string|false|No description
»»» remark|string|false|No description
»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»» code|string|false|No description
»»» name|string|false|No description
»»» amount|number|false|No description
»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»» rateKey|string|false|No description
»»» rateClass|string|false|No description
»»» rateType|string|false|No description
»»» net|number|false|No description
»»» discount|number|false|No description
»»» discountPCT|number|false|No description
»»» sellingRate|number|false|No description
»»» hotelSellingRate|number|false|No description
»»» amount|number|false|No description
»»» hotelCurrency|string|false|No description
»»» hotelMandatory|boolean|false|No description
»»» allotment|integer(int32)|false|No description
»»» commission|number|false|No description
»»» commissionVAT|number|false|No description
»»» commissionPCT|number|false|No description
»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»» amount|number|false|No description
»»»» currency|string|false|No description
»»» checkIn|string(date)|false|No description
»»» checkOut|string(date)|false|No description
»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»» offset|integer(int32)|false|No description
»»» dailyNet|number|false|No description
»»» dailySellingRate|number|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
» status|NEW|
» status|PRECONFIRMED|
» status|CONFIRMED|
» status|TO_BE_UPDATED|
» status|CANCELLED|
» status|TO_BE_CANCELLED|
»» type|AD|
»» type|CH|
»» rateType|BOOKABLE|
»» rateType|RECHECK|
»» paymentType|AT_HOTEL|
»» paymentType|AT_WEB|
»»»» type|TAX|
»»»» type|FEE|
»»» rateType|BOOKABLE|
»»» rateType|RECHECK|


## ApiVoucher

<a name="schemaapivoucher"></a>

```json
{
  "language": "string",
  "email": {
    "to": "string",
    "from": "string",
    "title": "string",
    "body": "string"
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
language|string|false|No description
email|[ApiVoucherEmail](#schemaapivoucheremail)|false|No description
» to|string|false|No description
» from|string|false|No description
» title|string|false|No description
» body|string|false|No description



## ApiVoucherComment

<a name="schemaapivouchercomment"></a>

```json
{
  "type": "string",
  "text": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
type|string|false|No description
text|string|false|No description



## ApiVoucherEmail

<a name="schemaapivoucheremail"></a>

```json
{
  "to": "string",
  "from": "string",
  "title": "string",
  "body": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
to|string|false|No description
from|string|false|No description
title|string|false|No description
body|string|false|No description



## apiError

<a name="schemaapierror"></a>

```json
{
  "code": "string",
  "message": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
code|string|false|No description
message|string|false|No description



## availabilityRQ

<a name="schemaavailabilityrq"></a>

```json
{
  "echoToken": "string",
  "stay": {
    "checkIn": "2017-09-21",
    "checkOut": "2017-09-23",
    "shiftDays": 3,
    "allowOnlyShift": false
  },
  "geolocation": {
    "longitude": 2.62155,
    "latitude": 39.5554,
    "radius": 0,
    "unit": "mi",
    "secondaryLatitude": 0,
    "secondaryLongitude": 0
  },
  "destination": {
    "code": "PMI",
    "zone": 10
  },
  "filter": {
    "maxHotels": 1000,
    "maxRooms": 10,
    "minRate": 0,
    "maxRate": 1000,
    "maxRatesPerRoom": 1,
    "packaging": false,
    "paymentType": "AT_WEB",
    "hotelPackage": "BOTH",
    "minCategory": 1,
    "maxCategory": 5,
    "contract": "CG-VARIOS"
  },
  "boards": {
    "board": [
      "string"
    ],
    "included": false
  },
  "rooms": {
    "room": [
      "string"
    ],
    "included": false
  },
  "dailyRate": false,
  "sourceMarket": "ES",
  "source": {
    "channel": "B2B",
    "device": "WEB",
    "deviceInfo": "string"
  },
  "aifUse": false,
  "platform": 0,
  "language": "ENG",
  "occupancy": [
    {
      "rooms": 1,
      "adults": 2,
      "children": 0,
      "pax": [
        {
          "roomId": 1,
          "type": "AD",
          "age": 20,
          "name": "string",
          "surname": "string"
        }
      ]
    }
  ],
  "keywords": {
    "allIncluded": false,
    "keyword": [
      0
    ]
  },
  "hotels": {
    "included": false,
    "type": "HOTELBEDS",
    "hotel": [
      0
    ]
  },
  "review": [
    {
      "type": "TRIPADVISOR",
      "minRate": 0,
      "maxRate": 1,
      "minReviewCount": 1
    }
  ],
  "accommodation": [
    "HOTEL"
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
echoToken|string|false|No description
stay|[ApiStay](#schemaapistay)|true|No description
» checkIn|string(date)|true|Check-in date
» checkOut|string(date)|true|Check-out date
» shiftDays|integer(int32)|false|No description
» allowOnlyShift|boolean|false|No description
geolocation|[ApiGeoLocation](#schemaapigeolocation)|false|No description
» longitude|number|true|No description
» latitude|number|true|No description
» radius|number|false|No description
» unit|string|false|No description
» secondaryLatitude|number|false|No description
» secondaryLongitude|number|false|No description
destination|[ApiDestination](#schemaapidestination)|false|No description
» code|string|true|No description
» zone|integer(int32)|false|No description
filter|[ApiFilter](#schemaapifilter)|false|No description
» maxHotels|integer(int32)|false|No description
» maxRooms|integer(int32)|false|No description
» minRate|number|false|No description
» maxRate|number|false|No description
» maxRatesPerRoom|integer(int32)|false|No description
» packaging|boolean|false|No description
» paymentType|string|false|No description
» hotelPackage|string|false|No description
» minCategory|integer(int32)|false|No description
» maxCategory|integer(int32)|false|No description
» contract|string|false|No description
boards|[ApiBoards](#schemaapiboards)|false|No description
» included|boolean|true|No description
» board|[string]|false|No description
rooms|[ApiRooms](#schemaapirooms)|false|No description
» included|boolean|true|No description
» room|[string]|false|No description
dailyRate|boolean|false|Display the rate day-by-day
sourceMarket|string|false|No description
source|[ApiSource](#schemaapisource)|false|No description
» channel|string|true|No description
» device|string|true|No description
» deviceInfo|string|false|No description
aifUse|boolean|false|No description
platform|integer(int32)|false|No description
language|string|false|No description
keywords|[ApiKeywordsFilter](#schemaapikeywordsfilter)|false|No description
» allIncluded|boolean|false|No description
» keyword|[integer(int32)]|false|No description
hotels|[ApiHotelsFilter](#schemaapihotelsfilter)|false|No description
» included|boolean|false|No description
» type|string|false|No description
» hotel|[integer(int32)]|false|No description
occupancy|[[ApiOccupancy](#schemaapioccupancy)]|false|No description
» rooms|integer(int32)|true|No description
» adults|integer(int32)|true|No description
» children|integer(int32)|true|No description
» pax|[[ApiPax](#schemaapipax)]|false|No description
»» roomId|integer(int32)|false|No description
»» type|string|true|No description
»» age|integer(int32)|false|No description
»» name|string|false|No description
»» surname|string|false|No description
review|[[ApiReviewFilter](#schemaapireviewfilter)]|false|No description
» type|string|true|No description
» minRate|number|false|No description
» maxRate|number|false|No description
» minReviewCount|integer(int32)|false|No description
accommodation|[string]|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
» unit|mi|
» unit|km|
» paymentType|AT_HOTEL|
» paymentType|AT_WEB|
» paymentType|BOTH|
» hotelPackage|YES|
» hotelPackage|NO|
» hotelPackage|BOTH|
» channel|B2B|
» channel|B2C|
» channel|META|
» channel|NEWSLETTER|
» device|MOBILE|
» device|WEB|
» device|TABLET|
» type|HOTELBEDS|
» type|GIATA|
»» type|AD|
»» type|CH|
» type|TRIPADVISOR|
» type|HOTELBEDS|
accommodation|HOTEL|
accommodation|APARTMENT|
accommodation|RURAL|
accommodation|HOSTEL|
accommodation|APTHOTEL|
accommodation|CAMPING|
accommodation|HISTORIC|
accommodation|PENDING|
accommodation|RESORT|
accommodation|HOMES|


## availabilityRS

<a name="schemaavailabilityrs"></a>

```json
{
  "echoToken": "string",
  "auditData": {
    "processTime": "string",
    "timestamp": "string",
    "requestHost": "string",
    "serverId": "string",
    "environment": "string",
    "release": "string",
    "token": "string"
  },
  "error": {
    "code": "string",
    "message": "string"
  },
  "hotels": {
    "checkIn": "2017-10-21",
    "checkOut": "2017-10-21",
    "hotel": [
      {
        "checkOut": "2017-10-21",
        "checkIn": "2017-10-21",
        "code": 0,
        "name": "string",
        "description": "string",
        "image": "string",
        "categoryCode": "string",
        "categoryName": "string",
        "destinationCode": "string",
        "destinationName": "string",
        "zoneCode": 0,
        "zoneName": "string",
        "latitude": "string",
        "longitude": "string",
        "giata": "string",
        "minRate": 0,
        "maxRate": 0,
        "totalSellingRate": 0,
        "totalNet": 0,
        "pendingAmount": 0,
        "currency": "string",
        "supplier": {
          "name": "string",
          "vatNumber": "string"
        },
        "clientComments": "string",
        "cancellationAmount": 0,
        "upselling": {
          "room": [
            {
              "status": "NEW",
              "id": 0,
              "code": "string",
              "name": "string",
              "pax": [
                {
                  "roomId": 1,
                  "type": "AD",
                  "age": 20,
                  "name": "string",
                  "surname": "string"
                }
              ],
              "rate": [
                {
                  "rateKey": "string",
                  "rateClass": "string",
                  "rateType": "BOOKABLE",
                  "net": 0,
                  "discount": 0,
                  "discountPCT": 0,
                  "sellingRate": 0,
                  "hotelSellingRate": 0,
                  "amount": 0,
                  "hotelCurrency": "string",
                  "hotelMandatory": false,
                  "allotment": 0,
                  "commission": 0,
                  "commissionVAT": 0,
                  "commissionPCT": 0,
                  "cost": {
                    "amount": 0,
                    "currency": "string"
                  },
                  "rateCommentsId": "string",
                  "rateComments": "string",
                  "paymentType": "AT_HOTEL",
                  "packaging": false,
                  "boardCode": "string",
                  "boardName": "string",
                  "rateBreakDown": {
                    "rateDiscount": [
                      {
                        "code": "string",
                        "name": "string",
                        "amount": 0
                      }
                    ],
                    "rateSupplement": [
                      {
                        "code": "string",
                        "name": "string",
                        "from": "2017-10-21",
                        "to": "2017-10-21",
                        "amount": 0,
                        "nights": 0,
                        "paxNumber": 0
                      }
                    ]
                  },
                  "rooms": 0,
                  "adults": 0,
                  "children": 0,
                  "childrenAges": "string",
                  "rateup": 0,
                  "comment": [
                    {
                      "type": "string",
                      "text": "string"
                    }
                  ],
                  "cancellationPolicy": [
                    {
                      "amount": 0,
                      "hotelAmount": 0,
                      "hotelCurrency": "string",
                      "from": "string"
                    }
                  ],
                  "taxes": {
                    "allIncluded": false,
                    "tax": [
                      {
                        "included": false,
                        "percent": 0,
                        "amount": 0,
                        "currency": "string",
                        "type": "TAX",
                        "clientAmount": 0,
                        "clientCurrency": "string"
                      }
                    ]
                  },
                  "promotion": [
                    {
                      "code": "string",
                      "name": "string",
                      "remark": "string"
                    }
                  ],
                  "offer": [
                    {
                      "code": "string",
                      "name": "string",
                      "amount": 0
                    }
                  ],
                  "shiftRate": [
                    {
                      "rateKey": "string",
                      "rateClass": "string",
                      "rateType": "BOOKABLE",
                      "net": 0,
                      "discount": 0,
                      "discountPCT": 0,
                      "sellingRate": 0,
                      "hotelSellingRate": 0,
                      "amount": 0,
                      "hotelCurrency": "string",
                      "hotelMandatory": false,
                      "allotment": 0,
                      "commission": 0,
                      "commissionVAT": 0,
                      "commissionPCT": 0,
                      "cost": {
                        "amount": 0,
                        "currency": "string"
                      },
                      "checkIn": "2017-10-21",
                      "checkOut": "2017-10-21"
                    }
                  ],
                  "dailyRate": [
                    {
                      "offset": 0,
                      "dailyNet": 0,
                      "dailySellingRate": 0
                    }
                  ]
                }
              ]
            }
          ]
        },
        "keyword": [
          {
            "code": 0,
            "rating": 0
          }
        ],
        "review": [
          {
            "rate": 0,
            "reviewCount": 0,
            "type": "string"
          }
        ],
        "room": [
          {
            "status": "NEW",
            "id": 0,
            "code": "string",
            "name": "string",
            "pax": [
              {
                "roomId": 1,
                "type": "AD",
                "age": 20,
                "name": "string",
                "surname": "string"
              }
            ],
            "rate": [
              {
                "rateKey": "string",
                "rateClass": "string",
                "rateType": "BOOKABLE",
                "net": 0,
                "discount": 0,
                "discountPCT": 0,
                "sellingRate": 0,
                "hotelSellingRate": 0,
                "amount": 0,
                "hotelCurrency": "string",
                "hotelMandatory": false,
                "allotment": 0,
                "commission": 0,
                "commissionVAT": 0,
                "commissionPCT": 0,
                "cost": {
                  "amount": 0,
                  "currency": "string"
                },
                "rateCommentsId": "string",
                "rateComments": "string",
                "paymentType": "AT_HOTEL",
                "packaging": false,
                "boardCode": "string",
                "boardName": "string",
                "rateBreakDown": {
                  "rateDiscount": [
                    {
                      "code": "string",
                      "name": "string",
                      "amount": 0
                    }
                  ],
                  "rateSupplement": [
                    {
                      "code": "string",
                      "name": "string",
                      "from": "2017-10-21",
                      "to": "2017-10-21",
                      "amount": 0,
                      "nights": 0,
                      "paxNumber": 0
                    }
                  ]
                },
                "rooms": 0,
                "adults": 0,
                "children": 0,
                "childrenAges": "string",
                "rateup": 0,
                "comment": [
                  {
                    "type": "string",
                    "text": "string"
                  }
                ],
                "cancellationPolicy": [
                  {
                    "amount": 0,
                    "hotelAmount": 0,
                    "hotelCurrency": "string",
                    "from": "string"
                  }
                ],
                "taxes": {
                  "allIncluded": false,
                  "tax": [
                    {
                      "included": false,
                      "percent": 0,
                      "amount": 0,
                      "currency": "string",
                      "type": "TAX",
                      "clientAmount": 0,
                      "clientCurrency": "string"
                    }
                  ]
                },
                "promotion": [
                  {
                    "code": "string",
                    "name": "string",
                    "remark": "string"
                  }
                ],
                "offer": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "shiftRate": [
                  {
                    "rateKey": "string",
                    "rateClass": "string",
                    "rateType": "BOOKABLE",
                    "net": 0,
                    "discount": 0,
                    "discountPCT": 0,
                    "sellingRate": 0,
                    "hotelSellingRate": 0,
                    "amount": 0,
                    "hotelCurrency": "string",
                    "hotelMandatory": false,
                    "allotment": 0,
                    "commission": 0,
                    "commissionVAT": 0,
                    "commissionPCT": 0,
                    "cost": {
                      "amount": 0,
                      "currency": "string"
                    },
                    "checkIn": "2017-10-21",
                    "checkOut": "2017-10-21"
                  }
                ],
                "dailyRate": [
                  {
                    "offset": 0,
                    "dailyNet": 0,
                    "dailySellingRate": 0
                  }
                ]
              }
            ]
          }
        ],
        "creditCard": [
          {
            "code": "string",
            "name": "string",
            "paymentType": "AT_HOTEL"
          }
        ]
      }
    ],
    "total": 0
  },
  "source": {
    "channel": "B2B",
    "device": "WEB",
    "deviceInfo": "string"
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
echoToken|string|false|No description
auditData|[ApiAuditData](#schemaapiauditdata)|true|No description
» processTime|string|false|No description
» timestamp|string|false|No description
» requestHost|string|false|No description
» serverId|string|false|No description
» environment|string|false|No description
» release|string|false|No description
» token|string|false|No description
error|[apiError](#schemaapierror)|false|No description
» code|string|false|No description
» message|string|false|No description
hotels|[ApiHotels](#schemaapihotels)|false|No description
» checkIn|string(date)|false|No description
» checkOut|string(date)|false|No description
» total|integer(int32)|false|No description
» hotel|[[ApiHotel](#schemaapihotel)]|false|No description
»» checkOut|string(date)|false|No description
»» checkIn|string(date)|false|No description
»» code|integer(int32)|false|No description
»» name|string|false|No description
»» description|string|false|No description
»» image|string|false|No description
»» categoryCode|string|false|No description
»» categoryName|string|false|No description
»» destinationCode|string|false|No description
»» destinationName|string|false|No description
»» zoneCode|integer(int32)|false|No description
»» zoneName|string|false|No description
»» latitude|string|false|No description
»» longitude|string|false|No description
»» giata|string|false|No description
»» minRate|number|false|No description
»» maxRate|number|false|No description
»» totalSellingRate|number|false|No description
»» totalNet|number|false|No description
»» pendingAmount|number|false|No description
»» currency|string|false|No description
»» supplier|[ApiSupplier](#schemaapisupplier)|false|No description
»»» name|string|false|No description
»»» vatNumber|string|false|No description
»» clientComments|string|false|No description
»» cancellationAmount|number|false|No description
»» upselling|[ApiUpselling](#schemaapiupselling)|false|No description
»»» room|[[room](#schemaroom)]|false|No description
»»»» status|string|false|No description
»»»» id|integer(int32)|false|No description
»»»» code|string|false|No description
»»»» name|string|false|No description
»»»» pax|[[ApiPax](#schemaapipax)]|false|No description
»»»»» roomId|integer(int32)|false|No description
»»»»» type|string|true|No description
»»»»» age|integer(int32)|false|No description
»»»»» name|string|false|No description
»»»»» surname|string|false|No description
»»»» rate|[[ApiRate](#schemaapirate)]|false|No description
»»»»» rateKey|string|false|No description
»»»»» rateClass|string|false|No description
»»»»» rateType|string|false|No description
»»»»» net|number|false|No description
»»»»» discount|number|false|No description
»»»»» discountPCT|number|false|No description
»»»»» sellingRate|number|false|No description
»»»»» hotelSellingRate|number|false|No description
»»»»» amount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» hotelMandatory|boolean|false|No description
»»»»» allotment|integer(int32)|false|No description
»»»»» commission|number|false|No description
»»»»» commissionVAT|number|false|No description
»»»»» commissionPCT|number|false|No description
»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»» rateCommentsId|string|false|No description
»»»»» rateComments|string|false|No description
»»»»» paymentType|string|false|No description
»»»»» packaging|boolean|false|No description
»»»»» boardCode|string|false|No description
»»»»» boardName|string|false|No description
»»»»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»»»» code|string|false|No description
»»»»»»» name|string|false|No description
»»»»»»» amount|number|false|No description
»»»»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»»»» code|string|false|No description
»»»»»»» name|string|false|No description
»»»»»»» from|string(date)|false|No description
»»»»»»» to|string(date)|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» nights|integer(int32)|false|No description
»»»»»»» paxNumber|integer(int32)|false|No description
»»»»» rooms|integer(int32)|false|No description
»»»»» adults|integer(int32)|false|No description
»»»»» children|integer(int32)|false|No description
»»»»» childrenAges|string|false|No description
»»»»» rateup|number|false|No description
»»»»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»»»»» allIncluded|boolean|false|No description
»»»»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»»»»» included|boolean|false|No description
»»»»»»» percent|number|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» currency|string|false|No description
»»»»»»» type|string|false|No description
»»»»»»» clientAmount|number|false|No description
»»»»»»» clientCurrency|string|false|No description
»»»»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»»»» type|string|false|No description
»»»»»» text|string|false|No description
»»»»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»»»» amount|number|false|No description
»»»»»» hotelAmount|number|false|No description
»»»»»» hotelCurrency|string|false|No description
»»»»»» from|string|false|No description
»»»»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» remark|string|false|No description
»»»»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» amount|number|false|No description
»»»»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»»»» rateKey|string|false|No description
»»»»»» rateClass|string|false|No description
»»»»»» rateType|string|false|No description
»»»»»» net|number|false|No description
»»»»»» discount|number|false|No description
»»»»»» discountPCT|number|false|No description
»»»»»» sellingRate|number|false|No description
»»»»»» hotelSellingRate|number|false|No description
»»»»»» amount|number|false|No description
»»»»»» hotelCurrency|string|false|No description
»»»»»» hotelMandatory|boolean|false|No description
»»»»»» allotment|integer(int32)|false|No description
»»»»»» commission|number|false|No description
»»»»»» commissionVAT|number|false|No description
»»»»»» commissionPCT|number|false|No description
»»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» currency|string|false|No description
»»»»»» checkIn|string(date)|false|No description
»»»»»» checkOut|string(date)|false|No description
»»»»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»»»» offset|integer(int32)|false|No description
»»»»»» dailyNet|number|false|No description
»»»»»» dailySellingRate|number|false|No description
»» keyword|[[ApiKeyword](#schemaapikeyword)]|false|No description
»»» code|integer(int32)|true|No description
»»» rating|integer(int32)|false|No description
»» review|[[ApiReview](#schemaapireview)]|false|No description
»»» rate|number|false|No description
»»» reviewCount|integer(int32)|false|No description
»»» type|string|false|No description
»» room|[[room](#schemaroom)]|false|No description
»»» status|string|false|No description
»»» id|integer(int32)|false|No description
»»» code|string|false|No description
»»» name|string|false|No description
»»» pax|[[ApiPax](#schemaapipax)]|false|No description
»»»» roomId|integer(int32)|false|No description
»»»» type|string|true|No description
»»»» age|integer(int32)|false|No description
»»»» name|string|false|No description
»»»» surname|string|false|No description
»»» rate|[[ApiRate](#schemaapirate)]|false|No description
»»»» rateKey|string|false|No description
»»»» rateClass|string|false|No description
»»»» rateType|string|false|No description
»»»» net|number|false|No description
»»»» discount|number|false|No description
»»»» discountPCT|number|false|No description
»»»» sellingRate|number|false|No description
»»»» hotelSellingRate|number|false|No description
»»»» amount|number|false|No description
»»»» hotelCurrency|string|false|No description
»»»» hotelMandatory|boolean|false|No description
»»»» allotment|integer(int32)|false|No description
»»»» commission|number|false|No description
»»»» commissionVAT|number|false|No description
»»»» commissionPCT|number|false|No description
»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»» amount|number|false|No description
»»»»» currency|string|false|No description
»»»» rateCommentsId|string|false|No description
»»»» rateComments|string|false|No description
»»»» paymentType|string|false|No description
»»»» packaging|boolean|false|No description
»»»» boardCode|string|false|No description
»»»» boardName|string|false|No description
»»»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» amount|number|false|No description
»»»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» from|string(date)|false|No description
»»»»»» to|string(date)|false|No description
»»»»»» amount|number|false|No description
»»»»»» nights|integer(int32)|false|No description
»»»»»» paxNumber|integer(int32)|false|No description
»»»» rooms|integer(int32)|false|No description
»»»» adults|integer(int32)|false|No description
»»»» children|integer(int32)|false|No description
»»»» childrenAges|string|false|No description
»»»» rateup|number|false|No description
»»»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»»»» allIncluded|boolean|false|No description
»»»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»»»» included|boolean|false|No description
»»»»»» percent|number|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»»» type|string|false|No description
»»»»»» clientAmount|number|false|No description
»»»»»» clientCurrency|string|false|No description
»»»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»»» type|string|false|No description
»»»»» text|string|false|No description
»»»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»»» amount|number|false|No description
»»»»» hotelAmount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» from|string|false|No description
»»»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» remark|string|false|No description
»»»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» amount|number|false|No description
»»»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»»» rateKey|string|false|No description
»»»»» rateClass|string|false|No description
»»»»» rateType|string|false|No description
»»»»» net|number|false|No description
»»»»» discount|number|false|No description
»»»»» discountPCT|number|false|No description
»»»»» sellingRate|number|false|No description
»»»»» hotelSellingRate|number|false|No description
»»»»» amount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» hotelMandatory|boolean|false|No description
»»»»» allotment|integer(int32)|false|No description
»»»»» commission|number|false|No description
»»»»» commissionVAT|number|false|No description
»»»»» commissionPCT|number|false|No description
»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»» checkIn|string(date)|false|No description
»»»»» checkOut|string(date)|false|No description
»»»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»»» offset|integer(int32)|false|No description
»»»»» dailyNet|number|false|No description
»»»»» dailySellingRate|number|false|No description
»» creditCard|[[ApiCreditCard](#schemaapicreditcard)]|false|No description
»»» code|string|false|No description
»»» name|string|false|No description
»»» paymentType|string|false|No description
source|[ApiSource](#schemaapisource)|false|No description
» channel|string|true|No description
» device|string|true|No description
» deviceInfo|string|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
»»»» status|NEW|
»»»» status|PRECONFIRMED|
»»»» status|CONFIRMED|
»»»» status|TO_BE_UPDATED|
»»»» status|CANCELLED|
»»»» status|TO_BE_CANCELLED|
»»»»» type|AD|
»»»»» type|CH|
»»»»» rateType|BOOKABLE|
»»»»» rateType|RECHECK|
»»»»» paymentType|AT_HOTEL|
»»»»» paymentType|AT_WEB|
»»»»»»» type|TAX|
»»»»»»» type|FEE|
»»»»»» rateType|BOOKABLE|
»»»»»» rateType|RECHECK|
»»» status|NEW|
»»» status|PRECONFIRMED|
»»» status|CONFIRMED|
»»» status|TO_BE_UPDATED|
»»» status|CANCELLED|
»»» status|TO_BE_CANCELLED|
»»»» type|AD|
»»»» type|CH|
»»»» rateType|BOOKABLE|
»»»» rateType|RECHECK|
»»»» paymentType|AT_HOTEL|
»»»» paymentType|AT_WEB|
»»»»»» type|TAX|
»»»»»» type|FEE|
»»»»» rateType|BOOKABLE|
»»»»» rateType|RECHECK|
»»» paymentType|AT_HOTEL|
»»» paymentType|AT_WEB|
» channel|B2B|
» channel|B2C|
» channel|META|
» channel|NEWSLETTER|
» device|MOBILE|
» device|WEB|
» device|TABLET|


## bookingCancellationRS

<a name="schemabookingcancellationrs"></a>

```json
{
  "echoToken": "string",
  "auditData": {
    "processTime": "string",
    "timestamp": "string",
    "requestHost": "string",
    "serverId": "string",
    "environment": "string",
    "release": "string",
    "token": "string"
  },
  "error": {
    "code": "string",
    "message": "string"
  },
  "booking": {
    "reference": "string",
    "cancellationReference": "string",
    "clientReference": "string",
    "creationDate": "2017-10-21",
    "status": "NEW",
    "modificationPolicies": {
      "cancellation": false,
      "modification": false
    },
    "agCommision": 0,
    "commisionVAT": 0,
    "creationUser": "string",
    "holder": {
      "name": "string",
      "surname": "string"
    },
    "remark": "string",
    "totalSellingRate": 0,
    "totalNet": 0,
    "pendingAmount": 0,
    "currency": "string",
    "hotel": {
      "checkOut": "2017-10-21",
      "checkIn": "2017-10-21",
      "code": 0,
      "name": "string",
      "description": "string",
      "image": "string",
      "categoryCode": "string",
      "categoryName": "string",
      "destinationCode": "string",
      "destinationName": "string",
      "zoneCode": 0,
      "zoneName": "string",
      "latitude": "string",
      "longitude": "string",
      "giata": "string",
      "minRate": 0,
      "maxRate": 0,
      "totalSellingRate": 0,
      "totalNet": 0,
      "pendingAmount": 0,
      "currency": "string",
      "supplier": {
        "name": "string",
        "vatNumber": "string"
      },
      "clientComments": "string",
      "cancellationAmount": 0,
      "upselling": {
        "room": [
          {
            "status": "NEW",
            "id": 0,
            "code": "string",
            "name": "string",
            "pax": [
              {
                "roomId": 1,
                "type": "AD",
                "age": 20,
                "name": "string",
                "surname": "string"
              }
            ],
            "rate": [
              {
                "rateKey": "string",
                "rateClass": "string",
                "rateType": "BOOKABLE",
                "net": 0,
                "discount": 0,
                "discountPCT": 0,
                "sellingRate": 0,
                "hotelSellingRate": 0,
                "amount": 0,
                "hotelCurrency": "string",
                "hotelMandatory": false,
                "allotment": 0,
                "commission": 0,
                "commissionVAT": 0,
                "commissionPCT": 0,
                "cost": {
                  "amount": 0,
                  "currency": "string"
                },
                "rateCommentsId": "string",
                "rateComments": "string",
                "paymentType": "AT_HOTEL",
                "packaging": false,
                "boardCode": "string",
                "boardName": "string",
                "rateBreakDown": {
                  "rateDiscount": [
                    {
                      "code": "string",
                      "name": "string",
                      "amount": 0
                    }
                  ],
                  "rateSupplement": [
                    {
                      "code": "string",
                      "name": "string",
                      "from": "2017-10-21",
                      "to": "2017-10-21",
                      "amount": 0,
                      "nights": 0,
                      "paxNumber": 0
                    }
                  ]
                },
                "rooms": 0,
                "adults": 0,
                "children": 0,
                "childrenAges": "string",
                "rateup": 0,
                "comment": [
                  {
                    "type": "string",
                    "text": "string"
                  }
                ],
                "cancellationPolicy": [
                  {
                    "amount": 0,
                    "hotelAmount": 0,
                    "hotelCurrency": "string",
                    "from": "string"
                  }
                ],
                "taxes": {
                  "allIncluded": false,
                  "tax": [
                    {
                      "included": false,
                      "percent": 0,
                      "amount": 0,
                      "currency": "string",
                      "type": "TAX",
                      "clientAmount": 0,
                      "clientCurrency": "string"
                    }
                  ]
                },
                "promotion": [
                  {
                    "code": "string",
                    "name": "string",
                    "remark": "string"
                  }
                ],
                "offer": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "shiftRate": [
                  {
                    "rateKey": "string",
                    "rateClass": "string",
                    "rateType": "BOOKABLE",
                    "net": 0,
                    "discount": 0,
                    "discountPCT": 0,
                    "sellingRate": 0,
                    "hotelSellingRate": 0,
                    "amount": 0,
                    "hotelCurrency": "string",
                    "hotelMandatory": false,
                    "allotment": 0,
                    "commission": 0,
                    "commissionVAT": 0,
                    "commissionPCT": 0,
                    "cost": {
                      "amount": 0,
                      "currency": "string"
                    },
                    "checkIn": "2017-10-21",
                    "checkOut": "2017-10-21"
                  }
                ],
                "dailyRate": [
                  {
                    "offset": 0,
                    "dailyNet": 0,
                    "dailySellingRate": 0
                  }
                ]
              }
            ]
          }
        ]
      },
      "keyword": [
        {
          "code": 0,
          "rating": 0
        }
      ],
      "review": [
        {
          "rate": 0,
          "reviewCount": 0,
          "type": "string"
        }
      ],
      "room": [
        {
          "status": "NEW",
          "id": 0,
          "code": "string",
          "name": "string",
          "pax": [
            {
              "roomId": 1,
              "type": "AD",
              "age": 20,
              "name": "string",
              "surname": "string"
            }
          ],
          "rate": [
            {
              "rateKey": "string",
              "rateClass": "string",
              "rateType": "BOOKABLE",
              "net": 0,
              "discount": 0,
              "discountPCT": 0,
              "sellingRate": 0,
              "hotelSellingRate": 0,
              "amount": 0,
              "hotelCurrency": "string",
              "hotelMandatory": false,
              "allotment": 0,
              "commission": 0,
              "commissionVAT": 0,
              "commissionPCT": 0,
              "cost": {
                "amount": 0,
                "currency": "string"
              },
              "rateCommentsId": "string",
              "rateComments": "string",
              "paymentType": "AT_HOTEL",
              "packaging": false,
              "boardCode": "string",
              "boardName": "string",
              "rateBreakDown": {
                "rateDiscount": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "rateSupplement": [
                  {
                    "code": "string",
                    "name": "string",
                    "from": "2017-10-21",
                    "to": "2017-10-21",
                    "amount": 0,
                    "nights": 0,
                    "paxNumber": 0
                  }
                ]
              },
              "rooms": 0,
              "adults": 0,
              "children": 0,
              "childrenAges": "string",
              "rateup": 0,
              "comment": [
                {
                  "type": "string",
                  "text": "string"
                }
              ],
              "cancellationPolicy": [
                {
                  "amount": 0,
                  "hotelAmount": 0,
                  "hotelCurrency": "string",
                  "from": "string"
                }
              ],
              "taxes": {
                "allIncluded": false,
                "tax": [
                  {
                    "included": false,
                    "percent": 0,
                    "amount": 0,
                    "currency": "string",
                    "type": "TAX",
                    "clientAmount": 0,
                    "clientCurrency": "string"
                  }
                ]
              },
              "promotion": [
                {
                  "code": "string",
                  "name": "string",
                  "remark": "string"
                }
              ],
              "offer": [
                {
                  "code": "string",
                  "name": "string",
                  "amount": 0
                }
              ],
              "shiftRate": [
                {
                  "rateKey": "string",
                  "rateClass": "string",
                  "rateType": "BOOKABLE",
                  "net": 0,
                  "discount": 0,
                  "discountPCT": 0,
                  "sellingRate": 0,
                  "hotelSellingRate": 0,
                  "amount": 0,
                  "hotelCurrency": "string",
                  "hotelMandatory": false,
                  "allotment": 0,
                  "commission": 0,
                  "commissionVAT": 0,
                  "commissionPCT": 0,
                  "cost": {
                    "amount": 0,
                    "currency": "string"
                  },
                  "checkIn": "2017-10-21",
                  "checkOut": "2017-10-21"
                }
              ],
              "dailyRate": [
                {
                  "offset": 0,
                  "dailyNet": 0,
                  "dailySellingRate": 0
                }
              ]
            }
          ]
        }
      ],
      "creditCard": [
        {
          "code": "string",
          "name": "string",
          "paymentType": "AT_HOTEL"
        }
      ]
    }
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
echoToken|string|false|No description
auditData|[ApiAuditData](#schemaapiauditdata)|true|No description
» processTime|string|false|No description
» timestamp|string|false|No description
» requestHost|string|false|No description
» serverId|string|false|No description
» environment|string|false|No description
» release|string|false|No description
» token|string|false|No description
error|[apiError](#schemaapierror)|false|No description
» code|string|false|No description
» message|string|false|No description
booking|[ApiBooking](#schemaapibooking)|false|No description
» reference|string|false|No description
» cancellationReference|string|false|No description
» clientReference|string|false|No description
» creationDate|string(date)|false|No description
» status|string|false|No description
» modificationPolicies|[ApiModificationPolicies](#schemaapimodificationpolicies)|false|No description
»» cancellation|boolean|true|No description
»» modification|boolean|true|No description
» agCommision|number|false|No description
» commisionVAT|number|false|No description
» creationUser|string|false|No description
» holder|[ApiHolder](#schemaapiholder)|false|No description
»» name|string|true|No description
»» surname|string|true|No description
» remark|string|false|No description
» totalSellingRate|number|false|No description
» totalNet|number|false|No description
» pendingAmount|number|false|No description
» currency|string|false|No description
» hotel|[ApiHotel](#schemaapihotel)|false|No description
»» checkOut|string(date)|false|No description
»» checkIn|string(date)|false|No description
»» code|integer(int32)|false|No description
»» name|string|false|No description
»» description|string|false|No description
»» image|string|false|No description
»» categoryCode|string|false|No description
»» categoryName|string|false|No description
»» destinationCode|string|false|No description
»» destinationName|string|false|No description
»» zoneCode|integer(int32)|false|No description
»» zoneName|string|false|No description
»» latitude|string|false|No description
»» longitude|string|false|No description
»» giata|string|false|No description
»» minRate|number|false|No description
»» maxRate|number|false|No description
»» totalSellingRate|number|false|No description
»» totalNet|number|false|No description
»» pendingAmount|number|false|No description
»» currency|string|false|No description
»» supplier|[ApiSupplier](#schemaapisupplier)|false|No description
»»» name|string|false|No description
»»» vatNumber|string|false|No description
»» clientComments|string|false|No description
»» cancellationAmount|number|false|No description
»» upselling|[ApiUpselling](#schemaapiupselling)|false|No description
»»» room|[[room](#schemaroom)]|false|No description
»»»» status|string|false|No description
»»»» id|integer(int32)|false|No description
»»»» code|string|false|No description
»»»» name|string|false|No description
»»»» pax|[[ApiPax](#schemaapipax)]|false|No description
»»»»» roomId|integer(int32)|false|No description
»»»»» type|string|true|No description
»»»»» age|integer(int32)|false|No description
»»»»» name|string|false|No description
»»»»» surname|string|false|No description
»»»» rate|[[ApiRate](#schemaapirate)]|false|No description
»»»»» rateKey|string|false|No description
»»»»» rateClass|string|false|No description
»»»»» rateType|string|false|No description
»»»»» net|number|false|No description
»»»»» discount|number|false|No description
»»»»» discountPCT|number|false|No description
»»»»» sellingRate|number|false|No description
»»»»» hotelSellingRate|number|false|No description
»»»»» amount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» hotelMandatory|boolean|false|No description
»»»»» allotment|integer(int32)|false|No description
»»»»» commission|number|false|No description
»»»»» commissionVAT|number|false|No description
»»»»» commissionPCT|number|false|No description
»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»» rateCommentsId|string|false|No description
»»»»» rateComments|string|false|No description
»»»»» paymentType|string|false|No description
»»»»» packaging|boolean|false|No description
»»»»» boardCode|string|false|No description
»»»»» boardName|string|false|No description
»»»»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»»»» code|string|false|No description
»»»»»»» name|string|false|No description
»»»»»»» amount|number|false|No description
»»»»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»»»» code|string|false|No description
»»»»»»» name|string|false|No description
»»»»»»» from|string(date)|false|No description
»»»»»»» to|string(date)|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» nights|integer(int32)|false|No description
»»»»»»» paxNumber|integer(int32)|false|No description
»»»»» rooms|integer(int32)|false|No description
»»»»» adults|integer(int32)|false|No description
»»»»» children|integer(int32)|false|No description
»»»»» childrenAges|string|false|No description
»»»»» rateup|number|false|No description
»»»»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»»»»» allIncluded|boolean|false|No description
»»»»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»»»»» included|boolean|false|No description
»»»»»»» percent|number|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» currency|string|false|No description
»»»»»»» type|string|false|No description
»»»»»»» clientAmount|number|false|No description
»»»»»»» clientCurrency|string|false|No description
»»»»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»»»» type|string|false|No description
»»»»»» text|string|false|No description
»»»»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»»»» amount|number|false|No description
»»»»»» hotelAmount|number|false|No description
»»»»»» hotelCurrency|string|false|No description
»»»»»» from|string|false|No description
»»»»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» remark|string|false|No description
»»»»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» amount|number|false|No description
»»»»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»»»» rateKey|string|false|No description
»»»»»» rateClass|string|false|No description
»»»»»» rateType|string|false|No description
»»»»»» net|number|false|No description
»»»»»» discount|number|false|No description
»»»»»» discountPCT|number|false|No description
»»»»»» sellingRate|number|false|No description
»»»»»» hotelSellingRate|number|false|No description
»»»»»» amount|number|false|No description
»»»»»» hotelCurrency|string|false|No description
»»»»»» hotelMandatory|boolean|false|No description
»»»»»» allotment|integer(int32)|false|No description
»»»»»» commission|number|false|No description
»»»»»» commissionVAT|number|false|No description
»»»»»» commissionPCT|number|false|No description
»»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» currency|string|false|No description
»»»»»» checkIn|string(date)|false|No description
»»»»»» checkOut|string(date)|false|No description
»»»»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»»»» offset|integer(int32)|false|No description
»»»»»» dailyNet|number|false|No description
»»»»»» dailySellingRate|number|false|No description
»» keyword|[[ApiKeyword](#schemaapikeyword)]|false|No description
»»» code|integer(int32)|true|No description
»»» rating|integer(int32)|false|No description
»» review|[[ApiReview](#schemaapireview)]|false|No description
»»» rate|number|false|No description
»»» reviewCount|integer(int32)|false|No description
»»» type|string|false|No description
»» room|[[room](#schemaroom)]|false|No description
»»» status|string|false|No description
»»» id|integer(int32)|false|No description
»»» code|string|false|No description
»»» name|string|false|No description
»»» pax|[[ApiPax](#schemaapipax)]|false|No description
»»»» roomId|integer(int32)|false|No description
»»»» type|string|true|No description
»»»» age|integer(int32)|false|No description
»»»» name|string|false|No description
»»»» surname|string|false|No description
»»» rate|[[ApiRate](#schemaapirate)]|false|No description
»»»» rateKey|string|false|No description
»»»» rateClass|string|false|No description
»»»» rateType|string|false|No description
»»»» net|number|false|No description
»»»» discount|number|false|No description
»»»» discountPCT|number|false|No description
»»»» sellingRate|number|false|No description
»»»» hotelSellingRate|number|false|No description
»»»» amount|number|false|No description
»»»» hotelCurrency|string|false|No description
»»»» hotelMandatory|boolean|false|No description
»»»» allotment|integer(int32)|false|No description
»»»» commission|number|false|No description
»»»» commissionVAT|number|false|No description
»»»» commissionPCT|number|false|No description
»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»» amount|number|false|No description
»»»»» currency|string|false|No description
»»»» rateCommentsId|string|false|No description
»»»» rateComments|string|false|No description
»»»» paymentType|string|false|No description
»»»» packaging|boolean|false|No description
»»»» boardCode|string|false|No description
»»»» boardName|string|false|No description
»»»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» amount|number|false|No description
»»»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» from|string(date)|false|No description
»»»»»» to|string(date)|false|No description
»»»»»» amount|number|false|No description
»»»»»» nights|integer(int32)|false|No description
»»»»»» paxNumber|integer(int32)|false|No description
»»»» rooms|integer(int32)|false|No description
»»»» adults|integer(int32)|false|No description
»»»» children|integer(int32)|false|No description
»»»» childrenAges|string|false|No description
»»»» rateup|number|false|No description
»»»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»»»» allIncluded|boolean|false|No description
»»»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»»»» included|boolean|false|No description
»»»»»» percent|number|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»»» type|string|false|No description
»»»»»» clientAmount|number|false|No description
»»»»»» clientCurrency|string|false|No description
»»»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»»» type|string|false|No description
»»»»» text|string|false|No description
»»»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»»» amount|number|false|No description
»»»»» hotelAmount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» from|string|false|No description
»»»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» remark|string|false|No description
»»»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» amount|number|false|No description
»»»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»»» rateKey|string|false|No description
»»»»» rateClass|string|false|No description
»»»»» rateType|string|false|No description
»»»»» net|number|false|No description
»»»»» discount|number|false|No description
»»»»» discountPCT|number|false|No description
»»»»» sellingRate|number|false|No description
»»»»» hotelSellingRate|number|false|No description
»»»»» amount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» hotelMandatory|boolean|false|No description
»»»»» allotment|integer(int32)|false|No description
»»»»» commission|number|false|No description
»»»»» commissionVAT|number|false|No description
»»»»» commissionPCT|number|false|No description
»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»» checkIn|string(date)|false|No description
»»»»» checkOut|string(date)|false|No description
»»»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»»» offset|integer(int32)|false|No description
»»»»» dailyNet|number|false|No description
»»»»» dailySellingRate|number|false|No description
»» creditCard|[[ApiCreditCard](#schemaapicreditcard)]|false|No description
»»» code|string|false|No description
»»» name|string|false|No description
»»» paymentType|string|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
» status|NEW|
» status|PRECONFIRMED|
» status|CONFIRMED|
» status|TO_BE_UPDATED|
» status|CANCELLED|
» status|TO_BE_CANCELLED|
»»»» status|NEW|
»»»» status|PRECONFIRMED|
»»»» status|CONFIRMED|
»»»» status|TO_BE_UPDATED|
»»»» status|CANCELLED|
»»»» status|TO_BE_CANCELLED|
»»»»» type|AD|
»»»»» type|CH|
»»»»» rateType|BOOKABLE|
»»»»» rateType|RECHECK|
»»»»» paymentType|AT_HOTEL|
»»»»» paymentType|AT_WEB|
»»»»»»» type|TAX|
»»»»»»» type|FEE|
»»»»»» rateType|BOOKABLE|
»»»»»» rateType|RECHECK|
»»» status|NEW|
»»» status|PRECONFIRMED|
»»» status|CONFIRMED|
»»» status|TO_BE_UPDATED|
»»» status|CANCELLED|
»»» status|TO_BE_CANCELLED|
»»»» type|AD|
»»»» type|CH|
»»»» rateType|BOOKABLE|
»»»» rateType|RECHECK|
»»»» paymentType|AT_HOTEL|
»»»» paymentType|AT_WEB|
»»»»»» type|TAX|
»»»»»» type|FEE|
»»»»» rateType|BOOKABLE|
»»»»» rateType|RECHECK|
»»» paymentType|AT_HOTEL|
»»» paymentType|AT_WEB|


## bookingChangeRQ

<a name="schemabookingchangerq"></a>

```json
{
  "echoToken": "string",
  "bookingId": "string",
  "mode": "SIMULATION",
  "language": "ENG",
  "booking": {
    "reference": "string",
    "cancellationReference": "string",
    "clientReference": "string",
    "creationDate": "2017-10-21",
    "status": "NEW",
    "modificationPolicies": {
      "cancellation": false,
      "modification": false
    },
    "agCommision": 0,
    "commisionVAT": 0,
    "creationUser": "string",
    "holder": {
      "name": "string",
      "surname": "string"
    },
    "remark": "string",
    "totalSellingRate": 0,
    "totalNet": 0,
    "pendingAmount": 0,
    "currency": "string",
    "hotel": {
      "checkOut": "2017-10-21",
      "checkIn": "2017-10-21",
      "code": 0,
      "name": "string",
      "description": "string",
      "image": "string",
      "categoryCode": "string",
      "categoryName": "string",
      "destinationCode": "string",
      "destinationName": "string",
      "zoneCode": 0,
      "zoneName": "string",
      "latitude": "string",
      "longitude": "string",
      "giata": "string",
      "minRate": 0,
      "maxRate": 0,
      "totalSellingRate": 0,
      "totalNet": 0,
      "pendingAmount": 0,
      "currency": "string",
      "supplier": {
        "name": "string",
        "vatNumber": "string"
      },
      "clientComments": "string",
      "cancellationAmount": 0,
      "upselling": {
        "room": [
          {
            "status": "NEW",
            "id": 0,
            "code": "string",
            "name": "string",
            "pax": [
              {
                "roomId": 1,
                "type": "AD",
                "age": 20,
                "name": "string",
                "surname": "string"
              }
            ],
            "rate": [
              {
                "rateKey": "string",
                "rateClass": "string",
                "rateType": "BOOKABLE",
                "net": 0,
                "discount": 0,
                "discountPCT": 0,
                "sellingRate": 0,
                "hotelSellingRate": 0,
                "amount": 0,
                "hotelCurrency": "string",
                "hotelMandatory": false,
                "allotment": 0,
                "commission": 0,
                "commissionVAT": 0,
                "commissionPCT": 0,
                "cost": {
                  "amount": 0,
                  "currency": "string"
                },
                "rateCommentsId": "string",
                "rateComments": "string",
                "paymentType": "AT_HOTEL",
                "packaging": false,
                "boardCode": "string",
                "boardName": "string",
                "rateBreakDown": {
                  "rateDiscount": [
                    {
                      "code": "string",
                      "name": "string",
                      "amount": 0
                    }
                  ],
                  "rateSupplement": [
                    {
                      "code": "string",
                      "name": "string",
                      "from": "2017-10-21",
                      "to": "2017-10-21",
                      "amount": 0,
                      "nights": 0,
                      "paxNumber": 0
                    }
                  ]
                },
                "rooms": 0,
                "adults": 0,
                "children": 0,
                "childrenAges": "string",
                "rateup": 0,
                "comment": [
                  {
                    "type": "string",
                    "text": "string"
                  }
                ],
                "cancellationPolicy": [
                  {
                    "amount": 0,
                    "hotelAmount": 0,
                    "hotelCurrency": "string",
                    "from": "string"
                  }
                ],
                "taxes": {
                  "allIncluded": false,
                  "tax": [
                    {
                      "included": false,
                      "percent": 0,
                      "amount": 0,
                      "currency": "string",
                      "type": "TAX",
                      "clientAmount": 0,
                      "clientCurrency": "string"
                    }
                  ]
                },
                "promotion": [
                  {
                    "code": "string",
                    "name": "string",
                    "remark": "string"
                  }
                ],
                "offer": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "shiftRate": [
                  {
                    "rateKey": "string",
                    "rateClass": "string",
                    "rateType": "BOOKABLE",
                    "net": 0,
                    "discount": 0,
                    "discountPCT": 0,
                    "sellingRate": 0,
                    "hotelSellingRate": 0,
                    "amount": 0,
                    "hotelCurrency": "string",
                    "hotelMandatory": false,
                    "allotment": 0,
                    "commission": 0,
                    "commissionVAT": 0,
                    "commissionPCT": 0,
                    "cost": {
                      "amount": 0,
                      "currency": "string"
                    },
                    "checkIn": "2017-10-21",
                    "checkOut": "2017-10-21"
                  }
                ],
                "dailyRate": [
                  {
                    "offset": 0,
                    "dailyNet": 0,
                    "dailySellingRate": 0
                  }
                ]
              }
            ]
          }
        ]
      },
      "keyword": [
        {
          "code": 0,
          "rating": 0
        }
      ],
      "review": [
        {
          "rate": 0,
          "reviewCount": 0,
          "type": "string"
        }
      ],
      "room": [
        {
          "status": "NEW",
          "id": 0,
          "code": "string",
          "name": "string",
          "pax": [
            {
              "roomId": 1,
              "type": "AD",
              "age": 20,
              "name": "string",
              "surname": "string"
            }
          ],
          "rate": [
            {
              "rateKey": "string",
              "rateClass": "string",
              "rateType": "BOOKABLE",
              "net": 0,
              "discount": 0,
              "discountPCT": 0,
              "sellingRate": 0,
              "hotelSellingRate": 0,
              "amount": 0,
              "hotelCurrency": "string",
              "hotelMandatory": false,
              "allotment": 0,
              "commission": 0,
              "commissionVAT": 0,
              "commissionPCT": 0,
              "cost": {
                "amount": 0,
                "currency": "string"
              },
              "rateCommentsId": "string",
              "rateComments": "string",
              "paymentType": "AT_HOTEL",
              "packaging": false,
              "boardCode": "string",
              "boardName": "string",
              "rateBreakDown": {
                "rateDiscount": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "rateSupplement": [
                  {
                    "code": "string",
                    "name": "string",
                    "from": "2017-10-21",
                    "to": "2017-10-21",
                    "amount": 0,
                    "nights": 0,
                    "paxNumber": 0
                  }
                ]
              },
              "rooms": 0,
              "adults": 0,
              "children": 0,
              "childrenAges": "string",
              "rateup": 0,
              "comment": [
                {
                  "type": "string",
                  "text": "string"
                }
              ],
              "cancellationPolicy": [
                {
                  "amount": 0,
                  "hotelAmount": 0,
                  "hotelCurrency": "string",
                  "from": "string"
                }
              ],
              "taxes": {
                "allIncluded": false,
                "tax": [
                  {
                    "included": false,
                    "percent": 0,
                    "amount": 0,
                    "currency": "string",
                    "type": "TAX",
                    "clientAmount": 0,
                    "clientCurrency": "string"
                  }
                ]
              },
              "promotion": [
                {
                  "code": "string",
                  "name": "string",
                  "remark": "string"
                }
              ],
              "offer": [
                {
                  "code": "string",
                  "name": "string",
                  "amount": 0
                }
              ],
              "shiftRate": [
                {
                  "rateKey": "string",
                  "rateClass": "string",
                  "rateType": "BOOKABLE",
                  "net": 0,
                  "discount": 0,
                  "discountPCT": 0,
                  "sellingRate": 0,
                  "hotelSellingRate": 0,
                  "amount": 0,
                  "hotelCurrency": "string",
                  "hotelMandatory": false,
                  "allotment": 0,
                  "commission": 0,
                  "commissionVAT": 0,
                  "commissionPCT": 0,
                  "cost": {
                    "amount": 0,
                    "currency": "string"
                  },
                  "checkIn": "2017-10-21",
                  "checkOut": "2017-10-21"
                }
              ],
              "dailyRate": [
                {
                  "offset": 0,
                  "dailyNet": 0,
                  "dailySellingRate": 0
                }
              ]
            }
          ]
        }
      ],
      "creditCard": [
        {
          "code": "string",
          "name": "string",
          "paymentType": "AT_HOTEL"
        }
      ]
    }
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
echoToken|string|false|No description
bookingId|string|true|No description
mode|string|true|No description
language|string|false|No description
booking|[ApiBooking](#schemaapibooking)|true|No description
» reference|string|false|No description
» cancellationReference|string|false|No description
» clientReference|string|false|No description
» creationDate|string(date)|false|No description
» status|string|false|No description
» modificationPolicies|[ApiModificationPolicies](#schemaapimodificationpolicies)|false|No description
»» cancellation|boolean|true|No description
»» modification|boolean|true|No description
» agCommision|number|false|No description
» commisionVAT|number|false|No description
» creationUser|string|false|No description
» holder|[ApiHolder](#schemaapiholder)|false|No description
»» name|string|true|No description
»» surname|string|true|No description
» remark|string|false|No description
» totalSellingRate|number|false|No description
» totalNet|number|false|No description
» pendingAmount|number|false|No description
» currency|string|false|No description
» hotel|[ApiHotel](#schemaapihotel)|false|No description
»» checkOut|string(date)|false|No description
»» checkIn|string(date)|false|No description
»» code|integer(int32)|false|No description
»» name|string|false|No description
»» description|string|false|No description
»» image|string|false|No description
»» categoryCode|string|false|No description
»» categoryName|string|false|No description
»» destinationCode|string|false|No description
»» destinationName|string|false|No description
»» zoneCode|integer(int32)|false|No description
»» zoneName|string|false|No description
»» latitude|string|false|No description
»» longitude|string|false|No description
»» giata|string|false|No description
»» minRate|number|false|No description
»» maxRate|number|false|No description
»» totalSellingRate|number|false|No description
»» totalNet|number|false|No description
»» pendingAmount|number|false|No description
»» currency|string|false|No description
»» supplier|[ApiSupplier](#schemaapisupplier)|false|No description
»»» name|string|false|No description
»»» vatNumber|string|false|No description
»» clientComments|string|false|No description
»» cancellationAmount|number|false|No description
»» upselling|[ApiUpselling](#schemaapiupselling)|false|No description
»»» room|[[room](#schemaroom)]|false|No description
»»»» status|string|false|No description
»»»» id|integer(int32)|false|No description
»»»» code|string|false|No description
»»»» name|string|false|No description
»»»» pax|[[ApiPax](#schemaapipax)]|false|No description
»»»»» roomId|integer(int32)|false|No description
»»»»» type|string|true|No description
»»»»» age|integer(int32)|false|No description
»»»»» name|string|false|No description
»»»»» surname|string|false|No description
»»»» rate|[[ApiRate](#schemaapirate)]|false|No description
»»»»» rateKey|string|false|No description
»»»»» rateClass|string|false|No description
»»»»» rateType|string|false|No description
»»»»» net|number|false|No description
»»»»» discount|number|false|No description
»»»»» discountPCT|number|false|No description
»»»»» sellingRate|number|false|No description
»»»»» hotelSellingRate|number|false|No description
»»»»» amount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» hotelMandatory|boolean|false|No description
»»»»» allotment|integer(int32)|false|No description
»»»»» commission|number|false|No description
»»»»» commissionVAT|number|false|No description
»»»»» commissionPCT|number|false|No description
»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»» rateCommentsId|string|false|No description
»»»»» rateComments|string|false|No description
»»»»» paymentType|string|false|No description
»»»»» packaging|boolean|false|No description
»»»»» boardCode|string|false|No description
»»»»» boardName|string|false|No description
»»»»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»»»» code|string|false|No description
»»»»»»» name|string|false|No description
»»»»»»» amount|number|false|No description
»»»»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»»»» code|string|false|No description
»»»»»»» name|string|false|No description
»»»»»»» from|string(date)|false|No description
»»»»»»» to|string(date)|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» nights|integer(int32)|false|No description
»»»»»»» paxNumber|integer(int32)|false|No description
»»»»» rooms|integer(int32)|false|No description
»»»»» adults|integer(int32)|false|No description
»»»»» children|integer(int32)|false|No description
»»»»» childrenAges|string|false|No description
»»»»» rateup|number|false|No description
»»»»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»»»»» allIncluded|boolean|false|No description
»»»»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»»»»» included|boolean|false|No description
»»»»»»» percent|number|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» currency|string|false|No description
»»»»»»» type|string|false|No description
»»»»»»» clientAmount|number|false|No description
»»»»»»» clientCurrency|string|false|No description
»»»»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»»»» type|string|false|No description
»»»»»» text|string|false|No description
»»»»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»»»» amount|number|false|No description
»»»»»» hotelAmount|number|false|No description
»»»»»» hotelCurrency|string|false|No description
»»»»»» from|string|false|No description
»»»»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» remark|string|false|No description
»»»»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» amount|number|false|No description
»»»»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»»»» rateKey|string|false|No description
»»»»»» rateClass|string|false|No description
»»»»»» rateType|string|false|No description
»»»»»» net|number|false|No description
»»»»»» discount|number|false|No description
»»»»»» discountPCT|number|false|No description
»»»»»» sellingRate|number|false|No description
»»»»»» hotelSellingRate|number|false|No description
»»»»»» amount|number|false|No description
»»»»»» hotelCurrency|string|false|No description
»»»»»» hotelMandatory|boolean|false|No description
»»»»»» allotment|integer(int32)|false|No description
»»»»»» commission|number|false|No description
»»»»»» commissionVAT|number|false|No description
»»»»»» commissionPCT|number|false|No description
»»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» currency|string|false|No description
»»»»»» checkIn|string(date)|false|No description
»»»»»» checkOut|string(date)|false|No description
»»»»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»»»» offset|integer(int32)|false|No description
»»»»»» dailyNet|number|false|No description
»»»»»» dailySellingRate|number|false|No description
»» keyword|[[ApiKeyword](#schemaapikeyword)]|false|No description
»»» code|integer(int32)|true|No description
»»» rating|integer(int32)|false|No description
»» review|[[ApiReview](#schemaapireview)]|false|No description
»»» rate|number|false|No description
»»» reviewCount|integer(int32)|false|No description
»»» type|string|false|No description
»» room|[[room](#schemaroom)]|false|No description
»»» status|string|false|No description
»»» id|integer(int32)|false|No description
»»» code|string|false|No description
»»» name|string|false|No description
»»» pax|[[ApiPax](#schemaapipax)]|false|No description
»»»» roomId|integer(int32)|false|No description
»»»» type|string|true|No description
»»»» age|integer(int32)|false|No description
»»»» name|string|false|No description
»»»» surname|string|false|No description
»»» rate|[[ApiRate](#schemaapirate)]|false|No description
»»»» rateKey|string|false|No description
»»»» rateClass|string|false|No description
»»»» rateType|string|false|No description
»»»» net|number|false|No description
»»»» discount|number|false|No description
»»»» discountPCT|number|false|No description
»»»» sellingRate|number|false|No description
»»»» hotelSellingRate|number|false|No description
»»»» amount|number|false|No description
»»»» hotelCurrency|string|false|No description
»»»» hotelMandatory|boolean|false|No description
»»»» allotment|integer(int32)|false|No description
»»»» commission|number|false|No description
»»»» commissionVAT|number|false|No description
»»»» commissionPCT|number|false|No description
»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»» amount|number|false|No description
»»»»» currency|string|false|No description
»»»» rateCommentsId|string|false|No description
»»»» rateComments|string|false|No description
»»»» paymentType|string|false|No description
»»»» packaging|boolean|false|No description
»»»» boardCode|string|false|No description
»»»» boardName|string|false|No description
»»»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» amount|number|false|No description
»»»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» from|string(date)|false|No description
»»»»»» to|string(date)|false|No description
»»»»»» amount|number|false|No description
»»»»»» nights|integer(int32)|false|No description
»»»»»» paxNumber|integer(int32)|false|No description
»»»» rooms|integer(int32)|false|No description
»»»» adults|integer(int32)|false|No description
»»»» children|integer(int32)|false|No description
»»»» childrenAges|string|false|No description
»»»» rateup|number|false|No description
»»»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»»»» allIncluded|boolean|false|No description
»»»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»»»» included|boolean|false|No description
»»»»»» percent|number|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»»» type|string|false|No description
»»»»»» clientAmount|number|false|No description
»»»»»» clientCurrency|string|false|No description
»»»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»»» type|string|false|No description
»»»»» text|string|false|No description
»»»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»»» amount|number|false|No description
»»»»» hotelAmount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» from|string|false|No description
»»»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» remark|string|false|No description
»»»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» amount|number|false|No description
»»»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»»» rateKey|string|false|No description
»»»»» rateClass|string|false|No description
»»»»» rateType|string|false|No description
»»»»» net|number|false|No description
»»»»» discount|number|false|No description
»»»»» discountPCT|number|false|No description
»»»»» sellingRate|number|false|No description
»»»»» hotelSellingRate|number|false|No description
»»»»» amount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» hotelMandatory|boolean|false|No description
»»»»» allotment|integer(int32)|false|No description
»»»»» commission|number|false|No description
»»»»» commissionVAT|number|false|No description
»»»»» commissionPCT|number|false|No description
»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»» checkIn|string(date)|false|No description
»»»»» checkOut|string(date)|false|No description
»»»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»»» offset|integer(int32)|false|No description
»»»»» dailyNet|number|false|No description
»»»»» dailySellingRate|number|false|No description
»» creditCard|[[ApiCreditCard](#schemaapicreditcard)]|false|No description
»»» code|string|false|No description
»»» name|string|false|No description
»»» paymentType|string|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
mode|SIMULATION|
mode|UPDATE|
» status|NEW|
» status|PRECONFIRMED|
» status|CONFIRMED|
» status|TO_BE_UPDATED|
» status|CANCELLED|
» status|TO_BE_CANCELLED|
»»»» status|NEW|
»»»» status|PRECONFIRMED|
»»»» status|CONFIRMED|
»»»» status|TO_BE_UPDATED|
»»»» status|CANCELLED|
»»»» status|TO_BE_CANCELLED|
»»»»» type|AD|
»»»»» type|CH|
»»»»» rateType|BOOKABLE|
»»»»» rateType|RECHECK|
»»»»» paymentType|AT_HOTEL|
»»»»» paymentType|AT_WEB|
»»»»»»» type|TAX|
»»»»»»» type|FEE|
»»»»»» rateType|BOOKABLE|
»»»»»» rateType|RECHECK|
»»» status|NEW|
»»» status|PRECONFIRMED|
»»» status|CONFIRMED|
»»» status|TO_BE_UPDATED|
»»» status|CANCELLED|
»»» status|TO_BE_CANCELLED|
»»»» type|AD|
»»»» type|CH|
»»»» rateType|BOOKABLE|
»»»» rateType|RECHECK|
»»»» paymentType|AT_HOTEL|
»»»» paymentType|AT_WEB|
»»»»»» type|TAX|
»»»»»» type|FEE|
»»»»» rateType|BOOKABLE|
»»»»» rateType|RECHECK|
»»» paymentType|AT_HOTEL|
»»» paymentType|AT_WEB|


## bookingChangeRS

<a name="schemabookingchangers"></a>

```json
{
  "echoToken": "string",
  "auditData": {
    "processTime": "string",
    "timestamp": "string",
    "requestHost": "string",
    "serverId": "string",
    "environment": "string",
    "release": "string",
    "token": "string"
  },
  "error": {
    "code": "string",
    "message": "string"
  },
  "booking": {
    "reference": "string",
    "cancellationReference": "string",
    "clientReference": "string",
    "creationDate": "2017-10-21",
    "status": "NEW",
    "modificationPolicies": {
      "cancellation": false,
      "modification": false
    },
    "agCommision": 0,
    "commisionVAT": 0,
    "creationUser": "string",
    "holder": {
      "name": "string",
      "surname": "string"
    },
    "remark": "string",
    "totalSellingRate": 0,
    "totalNet": 0,
    "pendingAmount": 0,
    "currency": "string",
    "hotel": {
      "checkOut": "2017-10-21",
      "checkIn": "2017-10-21",
      "code": 0,
      "name": "string",
      "description": "string",
      "image": "string",
      "categoryCode": "string",
      "categoryName": "string",
      "destinationCode": "string",
      "destinationName": "string",
      "zoneCode": 0,
      "zoneName": "string",
      "latitude": "string",
      "longitude": "string",
      "giata": "string",
      "minRate": 0,
      "maxRate": 0,
      "totalSellingRate": 0,
      "totalNet": 0,
      "pendingAmount": 0,
      "currency": "string",
      "supplier": {
        "name": "string",
        "vatNumber": "string"
      },
      "clientComments": "string",
      "cancellationAmount": 0,
      "upselling": {
        "room": [
          {
            "status": "NEW",
            "id": 0,
            "code": "string",
            "name": "string",
            "pax": [
              {
                "roomId": 1,
                "type": "AD",
                "age": 20,
                "name": "string",
                "surname": "string"
              }
            ],
            "rate": [
              {
                "rateKey": "string",
                "rateClass": "string",
                "rateType": "BOOKABLE",
                "net": 0,
                "discount": 0,
                "discountPCT": 0,
                "sellingRate": 0,
                "hotelSellingRate": 0,
                "amount": 0,
                "hotelCurrency": "string",
                "hotelMandatory": false,
                "allotment": 0,
                "commission": 0,
                "commissionVAT": 0,
                "commissionPCT": 0,
                "cost": {
                  "amount": 0,
                  "currency": "string"
                },
                "rateCommentsId": "string",
                "rateComments": "string",
                "paymentType": "AT_HOTEL",
                "packaging": false,
                "boardCode": "string",
                "boardName": "string",
                "rateBreakDown": {
                  "rateDiscount": [
                    {
                      "code": "string",
                      "name": "string",
                      "amount": 0
                    }
                  ],
                  "rateSupplement": [
                    {
                      "code": "string",
                      "name": "string",
                      "from": "2017-10-21",
                      "to": "2017-10-21",
                      "amount": 0,
                      "nights": 0,
                      "paxNumber": 0
                    }
                  ]
                },
                "rooms": 0,
                "adults": 0,
                "children": 0,
                "childrenAges": "string",
                "rateup": 0,
                "comment": [
                  {
                    "type": "string",
                    "text": "string"
                  }
                ],
                "cancellationPolicy": [
                  {
                    "amount": 0,
                    "hotelAmount": 0,
                    "hotelCurrency": "string",
                    "from": "string"
                  }
                ],
                "taxes": {
                  "allIncluded": false,
                  "tax": [
                    {
                      "included": false,
                      "percent": 0,
                      "amount": 0,
                      "currency": "string",
                      "type": "TAX",
                      "clientAmount": 0,
                      "clientCurrency": "string"
                    }
                  ]
                },
                "promotion": [
                  {
                    "code": "string",
                    "name": "string",
                    "remark": "string"
                  }
                ],
                "offer": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "shiftRate": [
                  {
                    "rateKey": "string",
                    "rateClass": "string",
                    "rateType": "BOOKABLE",
                    "net": 0,
                    "discount": 0,
                    "discountPCT": 0,
                    "sellingRate": 0,
                    "hotelSellingRate": 0,
                    "amount": 0,
                    "hotelCurrency": "string",
                    "hotelMandatory": false,
                    "allotment": 0,
                    "commission": 0,
                    "commissionVAT": 0,
                    "commissionPCT": 0,
                    "cost": {
                      "amount": 0,
                      "currency": "string"
                    },
                    "checkIn": "2017-10-21",
                    "checkOut": "2017-10-21"
                  }
                ],
                "dailyRate": [
                  {
                    "offset": 0,
                    "dailyNet": 0,
                    "dailySellingRate": 0
                  }
                ]
              }
            ]
          }
        ]
      },
      "keyword": [
        {
          "code": 0,
          "rating": 0
        }
      ],
      "review": [
        {
          "rate": 0,
          "reviewCount": 0,
          "type": "string"
        }
      ],
      "room": [
        {
          "status": "NEW",
          "id": 0,
          "code": "string",
          "name": "string",
          "pax": [
            {
              "roomId": 1,
              "type": "AD",
              "age": 20,
              "name": "string",
              "surname": "string"
            }
          ],
          "rate": [
            {
              "rateKey": "string",
              "rateClass": "string",
              "rateType": "BOOKABLE",
              "net": 0,
              "discount": 0,
              "discountPCT": 0,
              "sellingRate": 0,
              "hotelSellingRate": 0,
              "amount": 0,
              "hotelCurrency": "string",
              "hotelMandatory": false,
              "allotment": 0,
              "commission": 0,
              "commissionVAT": 0,
              "commissionPCT": 0,
              "cost": {
                "amount": 0,
                "currency": "string"
              },
              "rateCommentsId": "string",
              "rateComments": "string",
              "paymentType": "AT_HOTEL",
              "packaging": false,
              "boardCode": "string",
              "boardName": "string",
              "rateBreakDown": {
                "rateDiscount": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "rateSupplement": [
                  {
                    "code": "string",
                    "name": "string",
                    "from": "2017-10-21",
                    "to": "2017-10-21",
                    "amount": 0,
                    "nights": 0,
                    "paxNumber": 0
                  }
                ]
              },
              "rooms": 0,
              "adults": 0,
              "children": 0,
              "childrenAges": "string",
              "rateup": 0,
              "comment": [
                {
                  "type": "string",
                  "text": "string"
                }
              ],
              "cancellationPolicy": [
                {
                  "amount": 0,
                  "hotelAmount": 0,
                  "hotelCurrency": "string",
                  "from": "string"
                }
              ],
              "taxes": {
                "allIncluded": false,
                "tax": [
                  {
                    "included": false,
                    "percent": 0,
                    "amount": 0,
                    "currency": "string",
                    "type": "TAX",
                    "clientAmount": 0,
                    "clientCurrency": "string"
                  }
                ]
              },
              "promotion": [
                {
                  "code": "string",
                  "name": "string",
                  "remark": "string"
                }
              ],
              "offer": [
                {
                  "code": "string",
                  "name": "string",
                  "amount": 0
                }
              ],
              "shiftRate": [
                {
                  "rateKey": "string",
                  "rateClass": "string",
                  "rateType": "BOOKABLE",
                  "net": 0,
                  "discount": 0,
                  "discountPCT": 0,
                  "sellingRate": 0,
                  "hotelSellingRate": 0,
                  "amount": 0,
                  "hotelCurrency": "string",
                  "hotelMandatory": false,
                  "allotment": 0,
                  "commission": 0,
                  "commissionVAT": 0,
                  "commissionPCT": 0,
                  "cost": {
                    "amount": 0,
                    "currency": "string"
                  },
                  "checkIn": "2017-10-21",
                  "checkOut": "2017-10-21"
                }
              ],
              "dailyRate": [
                {
                  "offset": 0,
                  "dailyNet": 0,
                  "dailySellingRate": 0
                }
              ]
            }
          ]
        }
      ],
      "creditCard": [
        {
          "code": "string",
          "name": "string",
          "paymentType": "AT_HOTEL"
        }
      ]
    }
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
echoToken|string|false|No description
auditData|[ApiAuditData](#schemaapiauditdata)|true|No description
» processTime|string|false|No description
» timestamp|string|false|No description
» requestHost|string|false|No description
» serverId|string|false|No description
» environment|string|false|No description
» release|string|false|No description
» token|string|false|No description
error|[apiError](#schemaapierror)|false|No description
» code|string|false|No description
» message|string|false|No description
booking|[ApiBooking](#schemaapibooking)|false|No description
» reference|string|false|No description
» cancellationReference|string|false|No description
» clientReference|string|false|No description
» creationDate|string(date)|false|No description
» status|string|false|No description
» modificationPolicies|[ApiModificationPolicies](#schemaapimodificationpolicies)|false|No description
»» cancellation|boolean|true|No description
»» modification|boolean|true|No description
» agCommision|number|false|No description
» commisionVAT|number|false|No description
» creationUser|string|false|No description
» holder|[ApiHolder](#schemaapiholder)|false|No description
»» name|string|true|No description
»» surname|string|true|No description
» remark|string|false|No description
» totalSellingRate|number|false|No description
» totalNet|number|false|No description
» pendingAmount|number|false|No description
» currency|string|false|No description
» hotel|[ApiHotel](#schemaapihotel)|false|No description
»» checkOut|string(date)|false|No description
»» checkIn|string(date)|false|No description
»» code|integer(int32)|false|No description
»» name|string|false|No description
»» description|string|false|No description
»» image|string|false|No description
»» categoryCode|string|false|No description
»» categoryName|string|false|No description
»» destinationCode|string|false|No description
»» destinationName|string|false|No description
»» zoneCode|integer(int32)|false|No description
»» zoneName|string|false|No description
»» latitude|string|false|No description
»» longitude|string|false|No description
»» giata|string|false|No description
»» minRate|number|false|No description
»» maxRate|number|false|No description
»» totalSellingRate|number|false|No description
»» totalNet|number|false|No description
»» pendingAmount|number|false|No description
»» currency|string|false|No description
»» supplier|[ApiSupplier](#schemaapisupplier)|false|No description
»»» name|string|false|No description
»»» vatNumber|string|false|No description
»» clientComments|string|false|No description
»» cancellationAmount|number|false|No description
»» upselling|[ApiUpselling](#schemaapiupselling)|false|No description
»»» room|[[room](#schemaroom)]|false|No description
»»»» status|string|false|No description
»»»» id|integer(int32)|false|No description
»»»» code|string|false|No description
»»»» name|string|false|No description
»»»» pax|[[ApiPax](#schemaapipax)]|false|No description
»»»»» roomId|integer(int32)|false|No description
»»»»» type|string|true|No description
»»»»» age|integer(int32)|false|No description
»»»»» name|string|false|No description
»»»»» surname|string|false|No description
»»»» rate|[[ApiRate](#schemaapirate)]|false|No description
»»»»» rateKey|string|false|No description
»»»»» rateClass|string|false|No description
»»»»» rateType|string|false|No description
»»»»» net|number|false|No description
»»»»» discount|number|false|No description
»»»»» discountPCT|number|false|No description
»»»»» sellingRate|number|false|No description
»»»»» hotelSellingRate|number|false|No description
»»»»» amount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» hotelMandatory|boolean|false|No description
»»»»» allotment|integer(int32)|false|No description
»»»»» commission|number|false|No description
»»»»» commissionVAT|number|false|No description
»»»»» commissionPCT|number|false|No description
»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»» rateCommentsId|string|false|No description
»»»»» rateComments|string|false|No description
»»»»» paymentType|string|false|No description
»»»»» packaging|boolean|false|No description
»»»»» boardCode|string|false|No description
»»»»» boardName|string|false|No description
»»»»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»»»» code|string|false|No description
»»»»»»» name|string|false|No description
»»»»»»» amount|number|false|No description
»»»»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»»»» code|string|false|No description
»»»»»»» name|string|false|No description
»»»»»»» from|string(date)|false|No description
»»»»»»» to|string(date)|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» nights|integer(int32)|false|No description
»»»»»»» paxNumber|integer(int32)|false|No description
»»»»» rooms|integer(int32)|false|No description
»»»»» adults|integer(int32)|false|No description
»»»»» children|integer(int32)|false|No description
»»»»» childrenAges|string|false|No description
»»»»» rateup|number|false|No description
»»»»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»»»»» allIncluded|boolean|false|No description
»»»»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»»»»» included|boolean|false|No description
»»»»»»» percent|number|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» currency|string|false|No description
»»»»»»» type|string|false|No description
»»»»»»» clientAmount|number|false|No description
»»»»»»» clientCurrency|string|false|No description
»»»»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»»»» type|string|false|No description
»»»»»» text|string|false|No description
»»»»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»»»» amount|number|false|No description
»»»»»» hotelAmount|number|false|No description
»»»»»» hotelCurrency|string|false|No description
»»»»»» from|string|false|No description
»»»»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» remark|string|false|No description
»»»»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» amount|number|false|No description
»»»»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»»»» rateKey|string|false|No description
»»»»»» rateClass|string|false|No description
»»»»»» rateType|string|false|No description
»»»»»» net|number|false|No description
»»»»»» discount|number|false|No description
»»»»»» discountPCT|number|false|No description
»»»»»» sellingRate|number|false|No description
»»»»»» hotelSellingRate|number|false|No description
»»»»»» amount|number|false|No description
»»»»»» hotelCurrency|string|false|No description
»»»»»» hotelMandatory|boolean|false|No description
»»»»»» allotment|integer(int32)|false|No description
»»»»»» commission|number|false|No description
»»»»»» commissionVAT|number|false|No description
»»»»»» commissionPCT|number|false|No description
»»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» currency|string|false|No description
»»»»»» checkIn|string(date)|false|No description
»»»»»» checkOut|string(date)|false|No description
»»»»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»»»» offset|integer(int32)|false|No description
»»»»»» dailyNet|number|false|No description
»»»»»» dailySellingRate|number|false|No description
»» keyword|[[ApiKeyword](#schemaapikeyword)]|false|No description
»»» code|integer(int32)|true|No description
»»» rating|integer(int32)|false|No description
»» review|[[ApiReview](#schemaapireview)]|false|No description
»»» rate|number|false|No description
»»» reviewCount|integer(int32)|false|No description
»»» type|string|false|No description
»» room|[[room](#schemaroom)]|false|No description
»»» status|string|false|No description
»»» id|integer(int32)|false|No description
»»» code|string|false|No description
»»» name|string|false|No description
»»» pax|[[ApiPax](#schemaapipax)]|false|No description
»»»» roomId|integer(int32)|false|No description
»»»» type|string|true|No description
»»»» age|integer(int32)|false|No description
»»»» name|string|false|No description
»»»» surname|string|false|No description
»»» rate|[[ApiRate](#schemaapirate)]|false|No description
»»»» rateKey|string|false|No description
»»»» rateClass|string|false|No description
»»»» rateType|string|false|No description
»»»» net|number|false|No description
»»»» discount|number|false|No description
»»»» discountPCT|number|false|No description
»»»» sellingRate|number|false|No description
»»»» hotelSellingRate|number|false|No description
»»»» amount|number|false|No description
»»»» hotelCurrency|string|false|No description
»»»» hotelMandatory|boolean|false|No description
»»»» allotment|integer(int32)|false|No description
»»»» commission|number|false|No description
»»»» commissionVAT|number|false|No description
»»»» commissionPCT|number|false|No description
»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»» amount|number|false|No description
»»»»» currency|string|false|No description
»»»» rateCommentsId|string|false|No description
»»»» rateComments|string|false|No description
»»»» paymentType|string|false|No description
»»»» packaging|boolean|false|No description
»»»» boardCode|string|false|No description
»»»» boardName|string|false|No description
»»»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» amount|number|false|No description
»»»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» from|string(date)|false|No description
»»»»»» to|string(date)|false|No description
»»»»»» amount|number|false|No description
»»»»»» nights|integer(int32)|false|No description
»»»»»» paxNumber|integer(int32)|false|No description
»»»» rooms|integer(int32)|false|No description
»»»» adults|integer(int32)|false|No description
»»»» children|integer(int32)|false|No description
»»»» childrenAges|string|false|No description
»»»» rateup|number|false|No description
»»»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»»»» allIncluded|boolean|false|No description
»»»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»»»» included|boolean|false|No description
»»»»»» percent|number|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»»» type|string|false|No description
»»»»»» clientAmount|number|false|No description
»»»»»» clientCurrency|string|false|No description
»»»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»»» type|string|false|No description
»»»»» text|string|false|No description
»»»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»»» amount|number|false|No description
»»»»» hotelAmount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» from|string|false|No description
»»»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» remark|string|false|No description
»»»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» amount|number|false|No description
»»»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»»» rateKey|string|false|No description
»»»»» rateClass|string|false|No description
»»»»» rateType|string|false|No description
»»»»» net|number|false|No description
»»»»» discount|number|false|No description
»»»»» discountPCT|number|false|No description
»»»»» sellingRate|number|false|No description
»»»»» hotelSellingRate|number|false|No description
»»»»» amount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» hotelMandatory|boolean|false|No description
»»»»» allotment|integer(int32)|false|No description
»»»»» commission|number|false|No description
»»»»» commissionVAT|number|false|No description
»»»»» commissionPCT|number|false|No description
»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»» checkIn|string(date)|false|No description
»»»»» checkOut|string(date)|false|No description
»»»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»»» offset|integer(int32)|false|No description
»»»»» dailyNet|number|false|No description
»»»»» dailySellingRate|number|false|No description
»» creditCard|[[ApiCreditCard](#schemaapicreditcard)]|false|No description
»»» code|string|false|No description
»»» name|string|false|No description
»»» paymentType|string|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
» status|NEW|
» status|PRECONFIRMED|
» status|CONFIRMED|
» status|TO_BE_UPDATED|
» status|CANCELLED|
» status|TO_BE_CANCELLED|
»»»» status|NEW|
»»»» status|PRECONFIRMED|
»»»» status|CONFIRMED|
»»»» status|TO_BE_UPDATED|
»»»» status|CANCELLED|
»»»» status|TO_BE_CANCELLED|
»»»»» type|AD|
»»»»» type|CH|
»»»»» rateType|BOOKABLE|
»»»»» rateType|RECHECK|
»»»»» paymentType|AT_HOTEL|
»»»»» paymentType|AT_WEB|
»»»»»»» type|TAX|
»»»»»»» type|FEE|
»»»»»» rateType|BOOKABLE|
»»»»»» rateType|RECHECK|
»»» status|NEW|
»»» status|PRECONFIRMED|
»»» status|CONFIRMED|
»»» status|TO_BE_UPDATED|
»»» status|CANCELLED|
»»» status|TO_BE_CANCELLED|
»»»» type|AD|
»»»» type|CH|
»»»» rateType|BOOKABLE|
»»»» rateType|RECHECK|
»»»» paymentType|AT_HOTEL|
»»»» paymentType|AT_WEB|
»»»»»» type|TAX|
»»»»»» type|FEE|
»»»»» rateType|BOOKABLE|
»»»»» rateType|RECHECK|
»»» paymentType|AT_HOTEL|
»»» paymentType|AT_WEB|


## bookingDetailRS

<a name="schemabookingdetailrs"></a>

```json
{
  "echoToken": "string",
  "auditData": {
    "processTime": "string",
    "timestamp": "string",
    "requestHost": "string",
    "serverId": "string",
    "environment": "string",
    "release": "string",
    "token": "string"
  },
  "error": {
    "code": "string",
    "message": "string"
  },
  "booking": {
    "reference": "string",
    "cancellationReference": "string",
    "clientReference": "string",
    "creationDate": "2017-10-21",
    "status": "NEW",
    "modificationPolicies": {
      "cancellation": false,
      "modification": false
    },
    "agCommision": 0,
    "commisionVAT": 0,
    "creationUser": "string",
    "holder": {
      "name": "string",
      "surname": "string"
    },
    "remark": "string",
    "totalSellingRate": 0,
    "totalNet": 0,
    "pendingAmount": 0,
    "currency": "string",
    "hotel": {
      "checkOut": "2017-10-21",
      "checkIn": "2017-10-21",
      "code": 0,
      "name": "string",
      "description": "string",
      "image": "string",
      "categoryCode": "string",
      "categoryName": "string",
      "destinationCode": "string",
      "destinationName": "string",
      "zoneCode": 0,
      "zoneName": "string",
      "latitude": "string",
      "longitude": "string",
      "giata": "string",
      "minRate": 0,
      "maxRate": 0,
      "totalSellingRate": 0,
      "totalNet": 0,
      "pendingAmount": 0,
      "currency": "string",
      "supplier": {
        "name": "string",
        "vatNumber": "string"
      },
      "clientComments": "string",
      "cancellationAmount": 0,
      "upselling": {
        "room": [
          {
            "status": "NEW",
            "id": 0,
            "code": "string",
            "name": "string",
            "pax": [
              {
                "roomId": 1,
                "type": "AD",
                "age": 20,
                "name": "string",
                "surname": "string"
              }
            ],
            "rate": [
              {
                "rateKey": "string",
                "rateClass": "string",
                "rateType": "BOOKABLE",
                "net": 0,
                "discount": 0,
                "discountPCT": 0,
                "sellingRate": 0,
                "hotelSellingRate": 0,
                "amount": 0,
                "hotelCurrency": "string",
                "hotelMandatory": false,
                "allotment": 0,
                "commission": 0,
                "commissionVAT": 0,
                "commissionPCT": 0,
                "cost": {
                  "amount": 0,
                  "currency": "string"
                },
                "rateCommentsId": "string",
                "rateComments": "string",
                "paymentType": "AT_HOTEL",
                "packaging": false,
                "boardCode": "string",
                "boardName": "string",
                "rateBreakDown": {
                  "rateDiscount": [
                    {
                      "code": "string",
                      "name": "string",
                      "amount": 0
                    }
                  ],
                  "rateSupplement": [
                    {
                      "code": "string",
                      "name": "string",
                      "from": "2017-10-21",
                      "to": "2017-10-21",
                      "amount": 0,
                      "nights": 0,
                      "paxNumber": 0
                    }
                  ]
                },
                "rooms": 0,
                "adults": 0,
                "children": 0,
                "childrenAges": "string",
                "rateup": 0,
                "comment": [
                  {
                    "type": "string",
                    "text": "string"
                  }
                ],
                "cancellationPolicy": [
                  {
                    "amount": 0,
                    "hotelAmount": 0,
                    "hotelCurrency": "string",
                    "from": "string"
                  }
                ],
                "taxes": {
                  "allIncluded": false,
                  "tax": [
                    {
                      "included": false,
                      "percent": 0,
                      "amount": 0,
                      "currency": "string",
                      "type": "TAX",
                      "clientAmount": 0,
                      "clientCurrency": "string"
                    }
                  ]
                },
                "promotion": [
                  {
                    "code": "string",
                    "name": "string",
                    "remark": "string"
                  }
                ],
                "offer": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "shiftRate": [
                  {
                    "rateKey": "string",
                    "rateClass": "string",
                    "rateType": "BOOKABLE",
                    "net": 0,
                    "discount": 0,
                    "discountPCT": 0,
                    "sellingRate": 0,
                    "hotelSellingRate": 0,
                    "amount": 0,
                    "hotelCurrency": "string",
                    "hotelMandatory": false,
                    "allotment": 0,
                    "commission": 0,
                    "commissionVAT": 0,
                    "commissionPCT": 0,
                    "cost": {
                      "amount": 0,
                      "currency": "string"
                    },
                    "checkIn": "2017-10-21",
                    "checkOut": "2017-10-21"
                  }
                ],
                "dailyRate": [
                  {
                    "offset": 0,
                    "dailyNet": 0,
                    "dailySellingRate": 0
                  }
                ]
              }
            ]
          }
        ]
      },
      "keyword": [
        {
          "code": 0,
          "rating": 0
        }
      ],
      "review": [
        {
          "rate": 0,
          "reviewCount": 0,
          "type": "string"
        }
      ],
      "room": [
        {
          "status": "NEW",
          "id": 0,
          "code": "string",
          "name": "string",
          "pax": [
            {
              "roomId": 1,
              "type": "AD",
              "age": 20,
              "name": "string",
              "surname": "string"
            }
          ],
          "rate": [
            {
              "rateKey": "string",
              "rateClass": "string",
              "rateType": "BOOKABLE",
              "net": 0,
              "discount": 0,
              "discountPCT": 0,
              "sellingRate": 0,
              "hotelSellingRate": 0,
              "amount": 0,
              "hotelCurrency": "string",
              "hotelMandatory": false,
              "allotment": 0,
              "commission": 0,
              "commissionVAT": 0,
              "commissionPCT": 0,
              "cost": {
                "amount": 0,
                "currency": "string"
              },
              "rateCommentsId": "string",
              "rateComments": "string",
              "paymentType": "AT_HOTEL",
              "packaging": false,
              "boardCode": "string",
              "boardName": "string",
              "rateBreakDown": {
                "rateDiscount": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "rateSupplement": [
                  {
                    "code": "string",
                    "name": "string",
                    "from": "2017-10-21",
                    "to": "2017-10-21",
                    "amount": 0,
                    "nights": 0,
                    "paxNumber": 0
                  }
                ]
              },
              "rooms": 0,
              "adults": 0,
              "children": 0,
              "childrenAges": "string",
              "rateup": 0,
              "comment": [
                {
                  "type": "string",
                  "text": "string"
                }
              ],
              "cancellationPolicy": [
                {
                  "amount": 0,
                  "hotelAmount": 0,
                  "hotelCurrency": "string",
                  "from": "string"
                }
              ],
              "taxes": {
                "allIncluded": false,
                "tax": [
                  {
                    "included": false,
                    "percent": 0,
                    "amount": 0,
                    "currency": "string",
                    "type": "TAX",
                    "clientAmount": 0,
                    "clientCurrency": "string"
                  }
                ]
              },
              "promotion": [
                {
                  "code": "string",
                  "name": "string",
                  "remark": "string"
                }
              ],
              "offer": [
                {
                  "code": "string",
                  "name": "string",
                  "amount": 0
                }
              ],
              "shiftRate": [
                {
                  "rateKey": "string",
                  "rateClass": "string",
                  "rateType": "BOOKABLE",
                  "net": 0,
                  "discount": 0,
                  "discountPCT": 0,
                  "sellingRate": 0,
                  "hotelSellingRate": 0,
                  "amount": 0,
                  "hotelCurrency": "string",
                  "hotelMandatory": false,
                  "allotment": 0,
                  "commission": 0,
                  "commissionVAT": 0,
                  "commissionPCT": 0,
                  "cost": {
                    "amount": 0,
                    "currency": "string"
                  },
                  "checkIn": "2017-10-21",
                  "checkOut": "2017-10-21"
                }
              ],
              "dailyRate": [
                {
                  "offset": 0,
                  "dailyNet": 0,
                  "dailySellingRate": 0
                }
              ]
            }
          ]
        }
      ],
      "creditCard": [
        {
          "code": "string",
          "name": "string",
          "paymentType": "AT_HOTEL"
        }
      ]
    }
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
echoToken|string|false|No description
auditData|[ApiAuditData](#schemaapiauditdata)|true|No description
» processTime|string|false|No description
» timestamp|string|false|No description
» requestHost|string|false|No description
» serverId|string|false|No description
» environment|string|false|No description
» release|string|false|No description
» token|string|false|No description
error|[apiError](#schemaapierror)|false|No description
» code|string|false|No description
» message|string|false|No description
booking|[ApiBooking](#schemaapibooking)|false|No description
» reference|string|false|No description
» cancellationReference|string|false|No description
» clientReference|string|false|No description
» creationDate|string(date)|false|No description
» status|string|false|No description
» modificationPolicies|[ApiModificationPolicies](#schemaapimodificationpolicies)|false|No description
»» cancellation|boolean|true|No description
»» modification|boolean|true|No description
» agCommision|number|false|No description
» commisionVAT|number|false|No description
» creationUser|string|false|No description
» holder|[ApiHolder](#schemaapiholder)|false|No description
»» name|string|true|No description
»» surname|string|true|No description
» remark|string|false|No description
» totalSellingRate|number|false|No description
» totalNet|number|false|No description
» pendingAmount|number|false|No description
» currency|string|false|No description
» hotel|[ApiHotel](#schemaapihotel)|false|No description
»» checkOut|string(date)|false|No description
»» checkIn|string(date)|false|No description
»» code|integer(int32)|false|No description
»» name|string|false|No description
»» description|string|false|No description
»» image|string|false|No description
»» categoryCode|string|false|No description
»» categoryName|string|false|No description
»» destinationCode|string|false|No description
»» destinationName|string|false|No description
»» zoneCode|integer(int32)|false|No description
»» zoneName|string|false|No description
»» latitude|string|false|No description
»» longitude|string|false|No description
»» giata|string|false|No description
»» minRate|number|false|No description
»» maxRate|number|false|No description
»» totalSellingRate|number|false|No description
»» totalNet|number|false|No description
»» pendingAmount|number|false|No description
»» currency|string|false|No description
»» supplier|[ApiSupplier](#schemaapisupplier)|false|No description
»»» name|string|false|No description
»»» vatNumber|string|false|No description
»» clientComments|string|false|No description
»» cancellationAmount|number|false|No description
»» upselling|[ApiUpselling](#schemaapiupselling)|false|No description
»»» room|[[room](#schemaroom)]|false|No description
»»»» status|string|false|No description
»»»» id|integer(int32)|false|No description
»»»» code|string|false|No description
»»»» name|string|false|No description
»»»» pax|[[ApiPax](#schemaapipax)]|false|No description
»»»»» roomId|integer(int32)|false|No description
»»»»» type|string|true|No description
»»»»» age|integer(int32)|false|No description
»»»»» name|string|false|No description
»»»»» surname|string|false|No description
»»»» rate|[[ApiRate](#schemaapirate)]|false|No description
»»»»» rateKey|string|false|No description
»»»»» rateClass|string|false|No description
»»»»» rateType|string|false|No description
»»»»» net|number|false|No description
»»»»» discount|number|false|No description
»»»»» discountPCT|number|false|No description
»»»»» sellingRate|number|false|No description
»»»»» hotelSellingRate|number|false|No description
»»»»» amount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» hotelMandatory|boolean|false|No description
»»»»» allotment|integer(int32)|false|No description
»»»»» commission|number|false|No description
»»»»» commissionVAT|number|false|No description
»»»»» commissionPCT|number|false|No description
»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»» rateCommentsId|string|false|No description
»»»»» rateComments|string|false|No description
»»»»» paymentType|string|false|No description
»»»»» packaging|boolean|false|No description
»»»»» boardCode|string|false|No description
»»»»» boardName|string|false|No description
»»»»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»»»» code|string|false|No description
»»»»»»» name|string|false|No description
»»»»»»» amount|number|false|No description
»»»»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»»»» code|string|false|No description
»»»»»»» name|string|false|No description
»»»»»»» from|string(date)|false|No description
»»»»»»» to|string(date)|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» nights|integer(int32)|false|No description
»»»»»»» paxNumber|integer(int32)|false|No description
»»»»» rooms|integer(int32)|false|No description
»»»»» adults|integer(int32)|false|No description
»»»»» children|integer(int32)|false|No description
»»»»» childrenAges|string|false|No description
»»»»» rateup|number|false|No description
»»»»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»»»»» allIncluded|boolean|false|No description
»»»»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»»»»» included|boolean|false|No description
»»»»»»» percent|number|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» currency|string|false|No description
»»»»»»» type|string|false|No description
»»»»»»» clientAmount|number|false|No description
»»»»»»» clientCurrency|string|false|No description
»»»»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»»»» type|string|false|No description
»»»»»» text|string|false|No description
»»»»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»»»» amount|number|false|No description
»»»»»» hotelAmount|number|false|No description
»»»»»» hotelCurrency|string|false|No description
»»»»»» from|string|false|No description
»»»»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» remark|string|false|No description
»»»»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» amount|number|false|No description
»»»»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»»»» rateKey|string|false|No description
»»»»»» rateClass|string|false|No description
»»»»»» rateType|string|false|No description
»»»»»» net|number|false|No description
»»»»»» discount|number|false|No description
»»»»»» discountPCT|number|false|No description
»»»»»» sellingRate|number|false|No description
»»»»»» hotelSellingRate|number|false|No description
»»»»»» amount|number|false|No description
»»»»»» hotelCurrency|string|false|No description
»»»»»» hotelMandatory|boolean|false|No description
»»»»»» allotment|integer(int32)|false|No description
»»»»»» commission|number|false|No description
»»»»»» commissionVAT|number|false|No description
»»»»»» commissionPCT|number|false|No description
»»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» currency|string|false|No description
»»»»»» checkIn|string(date)|false|No description
»»»»»» checkOut|string(date)|false|No description
»»»»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»»»» offset|integer(int32)|false|No description
»»»»»» dailyNet|number|false|No description
»»»»»» dailySellingRate|number|false|No description
»» keyword|[[ApiKeyword](#schemaapikeyword)]|false|No description
»»» code|integer(int32)|true|No description
»»» rating|integer(int32)|false|No description
»» review|[[ApiReview](#schemaapireview)]|false|No description
»»» rate|number|false|No description
»»» reviewCount|integer(int32)|false|No description
»»» type|string|false|No description
»» room|[[room](#schemaroom)]|false|No description
»»» status|string|false|No description
»»» id|integer(int32)|false|No description
»»» code|string|false|No description
»»» name|string|false|No description
»»» pax|[[ApiPax](#schemaapipax)]|false|No description
»»»» roomId|integer(int32)|false|No description
»»»» type|string|true|No description
»»»» age|integer(int32)|false|No description
»»»» name|string|false|No description
»»»» surname|string|false|No description
»»» rate|[[ApiRate](#schemaapirate)]|false|No description
»»»» rateKey|string|false|No description
»»»» rateClass|string|false|No description
»»»» rateType|string|false|No description
»»»» net|number|false|No description
»»»» discount|number|false|No description
»»»» discountPCT|number|false|No description
»»»» sellingRate|number|false|No description
»»»» hotelSellingRate|number|false|No description
»»»» amount|number|false|No description
»»»» hotelCurrency|string|false|No description
»»»» hotelMandatory|boolean|false|No description
»»»» allotment|integer(int32)|false|No description
»»»» commission|number|false|No description
»»»» commissionVAT|number|false|No description
»»»» commissionPCT|number|false|No description
»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»» amount|number|false|No description
»»»»» currency|string|false|No description
»»»» rateCommentsId|string|false|No description
»»»» rateComments|string|false|No description
»»»» paymentType|string|false|No description
»»»» packaging|boolean|false|No description
»»»» boardCode|string|false|No description
»»»» boardName|string|false|No description
»»»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» amount|number|false|No description
»»»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» from|string(date)|false|No description
»»»»»» to|string(date)|false|No description
»»»»»» amount|number|false|No description
»»»»»» nights|integer(int32)|false|No description
»»»»»» paxNumber|integer(int32)|false|No description
»»»» rooms|integer(int32)|false|No description
»»»» adults|integer(int32)|false|No description
»»»» children|integer(int32)|false|No description
»»»» childrenAges|string|false|No description
»»»» rateup|number|false|No description
»»»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»»»» allIncluded|boolean|false|No description
»»»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»»»» included|boolean|false|No description
»»»»»» percent|number|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»»» type|string|false|No description
»»»»»» clientAmount|number|false|No description
»»»»»» clientCurrency|string|false|No description
»»»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»»» type|string|false|No description
»»»»» text|string|false|No description
»»»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»»» amount|number|false|No description
»»»»» hotelAmount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» from|string|false|No description
»»»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» remark|string|false|No description
»»»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» amount|number|false|No description
»»»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»»» rateKey|string|false|No description
»»»»» rateClass|string|false|No description
»»»»» rateType|string|false|No description
»»»»» net|number|false|No description
»»»»» discount|number|false|No description
»»»»» discountPCT|number|false|No description
»»»»» sellingRate|number|false|No description
»»»»» hotelSellingRate|number|false|No description
»»»»» amount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» hotelMandatory|boolean|false|No description
»»»»» allotment|integer(int32)|false|No description
»»»»» commission|number|false|No description
»»»»» commissionVAT|number|false|No description
»»»»» commissionPCT|number|false|No description
»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»» checkIn|string(date)|false|No description
»»»»» checkOut|string(date)|false|No description
»»»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»»» offset|integer(int32)|false|No description
»»»»» dailyNet|number|false|No description
»»»»» dailySellingRate|number|false|No description
»» creditCard|[[ApiCreditCard](#schemaapicreditcard)]|false|No description
»»» code|string|false|No description
»»» name|string|false|No description
»»» paymentType|string|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
» status|NEW|
» status|PRECONFIRMED|
» status|CONFIRMED|
» status|TO_BE_UPDATED|
» status|CANCELLED|
» status|TO_BE_CANCELLED|
»»»» status|NEW|
»»»» status|PRECONFIRMED|
»»»» status|CONFIRMED|
»»»» status|TO_BE_UPDATED|
»»»» status|CANCELLED|
»»»» status|TO_BE_CANCELLED|
»»»»» type|AD|
»»»»» type|CH|
»»»»» rateType|BOOKABLE|
»»»»» rateType|RECHECK|
»»»»» paymentType|AT_HOTEL|
»»»»» paymentType|AT_WEB|
»»»»»»» type|TAX|
»»»»»»» type|FEE|
»»»»»» rateType|BOOKABLE|
»»»»»» rateType|RECHECK|
»»» status|NEW|
»»» status|PRECONFIRMED|
»»» status|CONFIRMED|
»»» status|TO_BE_UPDATED|
»»» status|CANCELLED|
»»» status|TO_BE_CANCELLED|
»»»» type|AD|
»»»» type|CH|
»»»» rateType|BOOKABLE|
»»»» rateType|RECHECK|
»»»» paymentType|AT_HOTEL|
»»»» paymentType|AT_WEB|
»»»»»» type|TAX|
»»»»»» type|FEE|
»»»»» rateType|BOOKABLE|
»»»»» rateType|RECHECK|
»»» paymentType|AT_HOTEL|
»»» paymentType|AT_WEB|


## bookingListRS

<a name="schemabookinglistrs"></a>

```json
{
  "echoToken": "string",
  "auditData": {
    "processTime": "string",
    "timestamp": "string",
    "requestHost": "string",
    "serverId": "string",
    "environment": "string",
    "release": "string",
    "token": "string"
  },
  "error": {
    "code": "string",
    "message": "string"
  },
  "bookings": {
    "from": 0,
    "to": 0,
    "total": 0,
    "booking": [
      {
        "reference": "string",
        "cancellationReference": "string",
        "clientReference": "string",
        "creationDate": "2017-10-21",
        "status": "NEW",
        "modificationPolicies": {
          "cancellation": false,
          "modification": false
        },
        "agCommision": 0,
        "commisionVAT": 0,
        "creationUser": "string",
        "holder": {
          "name": "string",
          "surname": "string"
        },
        "remark": "string",
        "totalSellingRate": 0,
        "totalNet": 0,
        "pendingAmount": 0,
        "currency": "string",
        "hotel": {
          "checkOut": "2017-10-21",
          "checkIn": "2017-10-21",
          "code": 0,
          "name": "string",
          "description": "string",
          "image": "string",
          "categoryCode": "string",
          "categoryName": "string",
          "destinationCode": "string",
          "destinationName": "string",
          "zoneCode": 0,
          "zoneName": "string",
          "latitude": "string",
          "longitude": "string",
          "giata": "string",
          "minRate": 0,
          "maxRate": 0,
          "totalSellingRate": 0,
          "totalNet": 0,
          "pendingAmount": 0,
          "currency": "string",
          "supplier": {
            "name": "string",
            "vatNumber": "string"
          },
          "clientComments": "string",
          "cancellationAmount": 0,
          "upselling": {
            "room": [
              {
                "status": "NEW",
                "id": 0,
                "code": "string",
                "name": "string",
                "pax": [
                  {
                    "roomId": 1,
                    "type": "AD",
                    "age": 20,
                    "name": "string",
                    "surname": "string"
                  }
                ],
                "rate": [
                  {
                    "rateKey": "string",
                    "rateClass": "string",
                    "rateType": "BOOKABLE",
                    "net": 0,
                    "discount": 0,
                    "discountPCT": 0,
                    "sellingRate": 0,
                    "hotelSellingRate": 0,
                    "amount": 0,
                    "hotelCurrency": "string",
                    "hotelMandatory": false,
                    "allotment": 0,
                    "commission": 0,
                    "commissionVAT": 0,
                    "commissionPCT": 0,
                    "cost": {
                      "amount": 0,
                      "currency": "string"
                    },
                    "rateCommentsId": "string",
                    "rateComments": "string",
                    "paymentType": "AT_HOTEL",
                    "packaging": false,
                    "boardCode": "string",
                    "boardName": "string",
                    "rateBreakDown": {
                      "rateDiscount": [
                        {
                          "code": "string",
                          "name": "string",
                          "amount": 0
                        }
                      ],
                      "rateSupplement": [
                        {
                          "code": "string",
                          "name": "string",
                          "from": "2017-10-21",
                          "to": "2017-10-21",
                          "amount": 0,
                          "nights": 0,
                          "paxNumber": 0
                        }
                      ]
                    },
                    "rooms": 0,
                    "adults": 0,
                    "children": 0,
                    "childrenAges": "string",
                    "rateup": 0,
                    "comment": [
                      {
                        "type": "string",
                        "text": "string"
                      }
                    ],
                    "cancellationPolicy": [
                      {
                        "amount": 0,
                        "hotelAmount": 0,
                        "hotelCurrency": "string",
                        "from": "string"
                      }
                    ],
                    "taxes": {
                      "allIncluded": false,
                      "tax": [
                        {
                          "included": false,
                          "percent": 0,
                          "amount": 0,
                          "currency": "string",
                          "type": "TAX",
                          "clientAmount": 0,
                          "clientCurrency": "string"
                        }
                      ]
                    },
                    "promotion": [
                      {
                        "code": "string",
                        "name": "string",
                        "remark": "string"
                      }
                    ],
                    "offer": [
                      {
                        "code": "string",
                        "name": "string",
                        "amount": 0
                      }
                    ],
                    "shiftRate": [
                      {
                        "rateKey": "string",
                        "rateClass": "string",
                        "rateType": "BOOKABLE",
                        "net": 0,
                        "discount": 0,
                        "discountPCT": 0,
                        "sellingRate": 0,
                        "hotelSellingRate": 0,
                        "amount": 0,
                        "hotelCurrency": "string",
                        "hotelMandatory": false,
                        "allotment": 0,
                        "commission": 0,
                        "commissionVAT": 0,
                        "commissionPCT": 0,
                        "cost": {
                          "amount": 0,
                          "currency": "string"
                        },
                        "checkIn": "2017-10-21",
                        "checkOut": "2017-10-21"
                      }
                    ],
                    "dailyRate": [
                      {
                        "offset": 0,
                        "dailyNet": 0,
                        "dailySellingRate": 0
                      }
                    ]
                  }
                ]
              }
            ]
          },
          "keyword": [
            {
              "code": 0,
              "rating": 0
            }
          ],
          "review": [
            {
              "rate": 0,
              "reviewCount": 0,
              "type": "string"
            }
          ],
          "room": [
            {
              "status": "NEW",
              "id": 0,
              "code": "string",
              "name": "string",
              "pax": [
                {
                  "roomId": 1,
                  "type": "AD",
                  "age": 20,
                  "name": "string",
                  "surname": "string"
                }
              ],
              "rate": [
                {
                  "rateKey": "string",
                  "rateClass": "string",
                  "rateType": "BOOKABLE",
                  "net": 0,
                  "discount": 0,
                  "discountPCT": 0,
                  "sellingRate": 0,
                  "hotelSellingRate": 0,
                  "amount": 0,
                  "hotelCurrency": "string",
                  "hotelMandatory": false,
                  "allotment": 0,
                  "commission": 0,
                  "commissionVAT": 0,
                  "commissionPCT": 0,
                  "cost": {
                    "amount": 0,
                    "currency": "string"
                  },
                  "rateCommentsId": "string",
                  "rateComments": "string",
                  "paymentType": "AT_HOTEL",
                  "packaging": false,
                  "boardCode": "string",
                  "boardName": "string",
                  "rateBreakDown": {
                    "rateDiscount": [
                      {
                        "code": "string",
                        "name": "string",
                        "amount": 0
                      }
                    ],
                    "rateSupplement": [
                      {
                        "code": "string",
                        "name": "string",
                        "from": "2017-10-21",
                        "to": "2017-10-21",
                        "amount": 0,
                        "nights": 0,
                        "paxNumber": 0
                      }
                    ]
                  },
                  "rooms": 0,
                  "adults": 0,
                  "children": 0,
                  "childrenAges": "string",
                  "rateup": 0,
                  "comment": [
                    {
                      "type": "string",
                      "text": "string"
                    }
                  ],
                  "cancellationPolicy": [
                    {
                      "amount": 0,
                      "hotelAmount": 0,
                      "hotelCurrency": "string",
                      "from": "string"
                    }
                  ],
                  "taxes": {
                    "allIncluded": false,
                    "tax": [
                      {
                        "included": false,
                        "percent": 0,
                        "amount": 0,
                        "currency": "string",
                        "type": "TAX",
                        "clientAmount": 0,
                        "clientCurrency": "string"
                      }
                    ]
                  },
                  "promotion": [
                    {
                      "code": "string",
                      "name": "string",
                      "remark": "string"
                    }
                  ],
                  "offer": [
                    {
                      "code": "string",
                      "name": "string",
                      "amount": 0
                    }
                  ],
                  "shiftRate": [
                    {
                      "rateKey": "string",
                      "rateClass": "string",
                      "rateType": "BOOKABLE",
                      "net": 0,
                      "discount": 0,
                      "discountPCT": 0,
                      "sellingRate": 0,
                      "hotelSellingRate": 0,
                      "amount": 0,
                      "hotelCurrency": "string",
                      "hotelMandatory": false,
                      "allotment": 0,
                      "commission": 0,
                      "commissionVAT": 0,
                      "commissionPCT": 0,
                      "cost": {
                        "amount": 0,
                        "currency": "string"
                      },
                      "checkIn": "2017-10-21",
                      "checkOut": "2017-10-21"
                    }
                  ],
                  "dailyRate": [
                    {
                      "offset": 0,
                      "dailyNet": 0,
                      "dailySellingRate": 0
                    }
                  ]
                }
              ]
            }
          ],
          "creditCard": [
            {
              "code": "string",
              "name": "string",
              "paymentType": "AT_HOTEL"
            }
          ]
        }
      }
    ]
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
echoToken|string|false|No description
auditData|[ApiAuditData](#schemaapiauditdata)|true|No description
» processTime|string|false|No description
» timestamp|string|false|No description
» requestHost|string|false|No description
» serverId|string|false|No description
» environment|string|false|No description
» release|string|false|No description
» token|string|false|No description
error|[apiError](#schemaapierror)|false|No description
» code|string|false|No description
» message|string|false|No description
bookings|[ApiBookings](#schemaapibookings)|false|No description
» from|integer(int32)|false|No description
» to|integer(int32)|false|No description
» total|number|false|No description
» booking|[[ApiBooking](#schemaapibooking)]|false|No description
»» reference|string|false|No description
»» cancellationReference|string|false|No description
»» clientReference|string|false|No description
»» creationDate|string(date)|false|No description
»» status|string|false|No description
»» modificationPolicies|[ApiModificationPolicies](#schemaapimodificationpolicies)|false|No description
»»» cancellation|boolean|true|No description
»»» modification|boolean|true|No description
»» agCommision|number|false|No description
»» commisionVAT|number|false|No description
»» creationUser|string|false|No description
»» holder|[ApiHolder](#schemaapiholder)|false|No description
»»» name|string|true|No description
»»» surname|string|true|No description
»» remark|string|false|No description
»» totalSellingRate|number|false|No description
»» totalNet|number|false|No description
»» pendingAmount|number|false|No description
»» currency|string|false|No description
»» hotel|[ApiHotel](#schemaapihotel)|false|No description
»»» checkOut|string(date)|false|No description
»»» checkIn|string(date)|false|No description
»»» code|integer(int32)|false|No description
»»» name|string|false|No description
»»» description|string|false|No description
»»» image|string|false|No description
»»» categoryCode|string|false|No description
»»» categoryName|string|false|No description
»»» destinationCode|string|false|No description
»»» destinationName|string|false|No description
»»» zoneCode|integer(int32)|false|No description
»»» zoneName|string|false|No description
»»» latitude|string|false|No description
»»» longitude|string|false|No description
»»» giata|string|false|No description
»»» minRate|number|false|No description
»»» maxRate|number|false|No description
»»» totalSellingRate|number|false|No description
»»» totalNet|number|false|No description
»»» pendingAmount|number|false|No description
»»» currency|string|false|No description
»»» supplier|[ApiSupplier](#schemaapisupplier)|false|No description
»»»» name|string|false|No description
»»»» vatNumber|string|false|No description
»»» clientComments|string|false|No description
»»» cancellationAmount|number|false|No description
»»» upselling|[ApiUpselling](#schemaapiupselling)|false|No description
»»»» room|[[room](#schemaroom)]|false|No description
»»»»» status|string|false|No description
»»»»» id|integer(int32)|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» pax|[[ApiPax](#schemaapipax)]|false|No description
»»»»»» roomId|integer(int32)|false|No description
»»»»»» type|string|true|No description
»»»»»» age|integer(int32)|false|No description
»»»»»» name|string|false|No description
»»»»»» surname|string|false|No description
»»»»» rate|[[ApiRate](#schemaapirate)]|false|No description
»»»»»» rateKey|string|false|No description
»»»»»» rateClass|string|false|No description
»»»»»» rateType|string|false|No description
»»»»»» net|number|false|No description
»»»»»» discount|number|false|No description
»»»»»» discountPCT|number|false|No description
»»»»»» sellingRate|number|false|No description
»»»»»» hotelSellingRate|number|false|No description
»»»»»» amount|number|false|No description
»»»»»» hotelCurrency|string|false|No description
»»»»»» hotelMandatory|boolean|false|No description
»»»»»» allotment|integer(int32)|false|No description
»»»»»» commission|number|false|No description
»»»»»» commissionVAT|number|false|No description
»»»»»» commissionPCT|number|false|No description
»»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» currency|string|false|No description
»»»»»» rateCommentsId|string|false|No description
»»»»»» rateComments|string|false|No description
»»»»»» paymentType|string|false|No description
»»»»»» packaging|boolean|false|No description
»»»»»» boardCode|string|false|No description
»»»»»» boardName|string|false|No description
»»»»»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»»»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»»»»» code|string|false|No description
»»»»»»»» name|string|false|No description
»»»»»»»» amount|number|false|No description
»»»»»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»»»»» code|string|false|No description
»»»»»»»» name|string|false|No description
»»»»»»»» from|string(date)|false|No description
»»»»»»»» to|string(date)|false|No description
»»»»»»»» amount|number|false|No description
»»»»»»»» nights|integer(int32)|false|No description
»»»»»»»» paxNumber|integer(int32)|false|No description
»»»»»» rooms|integer(int32)|false|No description
»»»»»» adults|integer(int32)|false|No description
»»»»»» children|integer(int32)|false|No description
»»»»»» childrenAges|string|false|No description
»»»»»» rateup|number|false|No description
»»»»»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»»»»»» allIncluded|boolean|false|No description
»»»»»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»»»»»» included|boolean|false|No description
»»»»»»»» percent|number|false|No description
»»»»»»»» amount|number|false|No description
»»»»»»»» currency|string|false|No description
»»»»»»»» type|string|false|No description
»»»»»»»» clientAmount|number|false|No description
»»»»»»»» clientCurrency|string|false|No description
»»»»»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»»»»» type|string|false|No description
»»»»»»» text|string|false|No description
»»»»»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» hotelAmount|number|false|No description
»»»»»»» hotelCurrency|string|false|No description
»»»»»»» from|string|false|No description
»»»»»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»»»»» code|string|false|No description
»»»»»»» name|string|false|No description
»»»»»»» remark|string|false|No description
»»»»»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»»»»»» code|string|false|No description
»»»»»»» name|string|false|No description
»»»»»»» amount|number|false|No description
»»»»»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»»»»» rateKey|string|false|No description
»»»»»»» rateClass|string|false|No description
»»»»»»» rateType|string|false|No description
»»»»»»» net|number|false|No description
»»»»»»» discount|number|false|No description
»»»»»»» discountPCT|number|false|No description
»»»»»»» sellingRate|number|false|No description
»»»»»»» hotelSellingRate|number|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» hotelCurrency|string|false|No description
»»»»»»» hotelMandatory|boolean|false|No description
»»»»»»» allotment|integer(int32)|false|No description
»»»»»»» commission|number|false|No description
»»»»»»» commissionVAT|number|false|No description
»»»»»»» commissionPCT|number|false|No description
»»»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»»»» amount|number|false|No description
»»»»»»»» currency|string|false|No description
»»»»»»» checkIn|string(date)|false|No description
»»»»»»» checkOut|string(date)|false|No description
»»»»»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»»»»» offset|integer(int32)|false|No description
»»»»»»» dailyNet|number|false|No description
»»»»»»» dailySellingRate|number|false|No description
»»» keyword|[[ApiKeyword](#schemaapikeyword)]|false|No description
»»»» code|integer(int32)|true|No description
»»»» rating|integer(int32)|false|No description
»»» review|[[ApiReview](#schemaapireview)]|false|No description
»»»» rate|number|false|No description
»»»» reviewCount|integer(int32)|false|No description
»»»» type|string|false|No description
»»» room|[[room](#schemaroom)]|false|No description
»»»» status|string|false|No description
»»»» id|integer(int32)|false|No description
»»»» code|string|false|No description
»»»» name|string|false|No description
»»»» pax|[[ApiPax](#schemaapipax)]|false|No description
»»»»» roomId|integer(int32)|false|No description
»»»»» type|string|true|No description
»»»»» age|integer(int32)|false|No description
»»»»» name|string|false|No description
»»»»» surname|string|false|No description
»»»» rate|[[ApiRate](#schemaapirate)]|false|No description
»»»»» rateKey|string|false|No description
»»»»» rateClass|string|false|No description
»»»»» rateType|string|false|No description
»»»»» net|number|false|No description
»»»»» discount|number|false|No description
»»»»» discountPCT|number|false|No description
»»»»» sellingRate|number|false|No description
»»»»» hotelSellingRate|number|false|No description
»»»»» amount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» hotelMandatory|boolean|false|No description
»»»»» allotment|integer(int32)|false|No description
»»»»» commission|number|false|No description
»»»»» commissionVAT|number|false|No description
»»»»» commissionPCT|number|false|No description
»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»» rateCommentsId|string|false|No description
»»»»» rateComments|string|false|No description
»»»»» paymentType|string|false|No description
»»»»» packaging|boolean|false|No description
»»»»» boardCode|string|false|No description
»»»»» boardName|string|false|No description
»»»»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»»»» code|string|false|No description
»»»»»»» name|string|false|No description
»»»»»»» amount|number|false|No description
»»»»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»»»» code|string|false|No description
»»»»»»» name|string|false|No description
»»»»»»» from|string(date)|false|No description
»»»»»»» to|string(date)|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» nights|integer(int32)|false|No description
»»»»»»» paxNumber|integer(int32)|false|No description
»»»»» rooms|integer(int32)|false|No description
»»»»» adults|integer(int32)|false|No description
»»»»» children|integer(int32)|false|No description
»»»»» childrenAges|string|false|No description
»»»»» rateup|number|false|No description
»»»»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»»»»» allIncluded|boolean|false|No description
»»»»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»»»»» included|boolean|false|No description
»»»»»»» percent|number|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» currency|string|false|No description
»»»»»»» type|string|false|No description
»»»»»»» clientAmount|number|false|No description
»»»»»»» clientCurrency|string|false|No description
»»»»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»»»» type|string|false|No description
»»»»»» text|string|false|No description
»»»»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»»»» amount|number|false|No description
»»»»»» hotelAmount|number|false|No description
»»»»»» hotelCurrency|string|false|No description
»»»»»» from|string|false|No description
»»»»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» remark|string|false|No description
»»»»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» amount|number|false|No description
»»»»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»»»» rateKey|string|false|No description
»»»»»» rateClass|string|false|No description
»»»»»» rateType|string|false|No description
»»»»»» net|number|false|No description
»»»»»» discount|number|false|No description
»»»»»» discountPCT|number|false|No description
»»»»»» sellingRate|number|false|No description
»»»»»» hotelSellingRate|number|false|No description
»»»»»» amount|number|false|No description
»»»»»» hotelCurrency|string|false|No description
»»»»»» hotelMandatory|boolean|false|No description
»»»»»» allotment|integer(int32)|false|No description
»»»»»» commission|number|false|No description
»»»»»» commissionVAT|number|false|No description
»»»»»» commissionPCT|number|false|No description
»»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» currency|string|false|No description
»»»»»» checkIn|string(date)|false|No description
»»»»»» checkOut|string(date)|false|No description
»»»»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»»»» offset|integer(int32)|false|No description
»»»»»» dailyNet|number|false|No description
»»»»»» dailySellingRate|number|false|No description
»»» creditCard|[[ApiCreditCard](#schemaapicreditcard)]|false|No description
»»»» code|string|false|No description
»»»» name|string|false|No description
»»»» paymentType|string|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
»» status|NEW|
»» status|PRECONFIRMED|
»» status|CONFIRMED|
»» status|TO_BE_UPDATED|
»» status|CANCELLED|
»» status|TO_BE_CANCELLED|
»»»»» status|NEW|
»»»»» status|PRECONFIRMED|
»»»»» status|CONFIRMED|
»»»»» status|TO_BE_UPDATED|
»»»»» status|CANCELLED|
»»»»» status|TO_BE_CANCELLED|
»»»»»» type|AD|
»»»»»» type|CH|
»»»»»» rateType|BOOKABLE|
»»»»»» rateType|RECHECK|
»»»»»» paymentType|AT_HOTEL|
»»»»»» paymentType|AT_WEB|
»»»»»»»» type|TAX|
»»»»»»»» type|FEE|
»»»»»»» rateType|BOOKABLE|
»»»»»»» rateType|RECHECK|
»»»» status|NEW|
»»»» status|PRECONFIRMED|
»»»» status|CONFIRMED|
»»»» status|TO_BE_UPDATED|
»»»» status|CANCELLED|
»»»» status|TO_BE_CANCELLED|
»»»»» type|AD|
»»»»» type|CH|
»»»»» rateType|BOOKABLE|
»»»»» rateType|RECHECK|
»»»»» paymentType|AT_HOTEL|
»»»»» paymentType|AT_WEB|
»»»»»»» type|TAX|
»»»»»»» type|FEE|
»»»»»» rateType|BOOKABLE|
»»»»»» rateType|RECHECK|
»»»» paymentType|AT_HOTEL|
»»»» paymentType|AT_WEB|


## bookingRQ

<a name="schemabookingrq"></a>

```json
{
  "echoToken": "string",
  "holder": {
    "name": "string",
    "surname": "string"
  },
  "paymentData": {
    "paymentCard": {
      "cardType": "string",
      "cardNumber": "string",
      "cardHolderName": "string",
      "expiryDate": "string",
      "cardCVC": "string"
    },
    "contactData": {
      "email": "string",
      "phoneNumber": "string"
    },
    "billingAddress": {
      "address1": "string",
      "address2": "string",
      "city": "string",
      "state": "string",
      "postalCode": "string",
      "countryCode": "string"
    },
    "webPartner": 0,
    "device": {
      "id": "string",
      "ip": "string"
    }
  },
  "clientReference": "string",
  "remark": "string",
  "voucher": {
    "language": "string",
    "email": {
      "to": "string",
      "from": "string",
      "title": "string",
      "body": "string"
    }
  },
  "language": "ENG",
  "room": [
    {
      "rateKey": "string",
      "pax": [
        {
          "roomId": 1,
          "type": "AD",
          "age": 20,
          "name": "string",
          "surname": "string"
        }
      ]
    }
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
echoToken|string|false|No description
holder|[ApiHolder](#schemaapiholder)|true|No description
» name|string|true|No description
» surname|string|true|No description
paymentData|[ApiPaymentData](#schemaapipaymentdata)|false|No description
» paymentCard|[ApiPaymentCard](#schemaapipaymentcard)|true|No description
»» cardType|string|false|No description
»» cardNumber|string|false|No description
»» cardHolderName|string|false|No description
»» expiryDate|string|false|No description
»» cardCVC|string|false|No description
» contactData|[ApiPaymentContactData](#schemaapipaymentcontactdata)|true|No description
»» email|string|false|No description
»» phoneNumber|string|false|No description
» billingAddress|[ApiBillingAddress](#schemaapibillingaddress)|false|No description
»» address1|string|false|No description
»» address2|string|false|No description
»» city|string|false|No description
»» state|string|false|No description
»» postalCode|string|false|No description
»» countryCode|string|false|No description
» webPartner|integer(int32)|false|No description
» device|[ApiBookingDevice](#schemaapibookingdevice)|false|No description
»» id|string|false|No description
»» ip|string|false|No description
clientReference|string|true|No description
remark|string|false|No description
voucher|[ApiVoucher](#schemaapivoucher)|false|No description
» language|string|false|No description
» email|[ApiVoucherEmail](#schemaapivoucheremail)|false|No description
»» to|string|false|No description
»» from|string|false|No description
»» title|string|false|No description
»» body|string|false|No description
language|string|false|No description
room|[[ApiBookingRoom](#schemaapibookingroom)]|false|No description
» rateKey|string|true|No description
» pax|[[ApiPax](#schemaapipax)]|false|No description
»» roomId|integer(int32)|false|No description
»» type|string|true|No description
»» age|integer(int32)|false|No description
»» name|string|false|No description
»» surname|string|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
»» type|AD|
»» type|CH|


## bookingRS

<a name="schemabookingrs"></a>

```json
{
  "echoToken": "string",
  "auditData": {
    "processTime": "string",
    "timestamp": "string",
    "requestHost": "string",
    "serverId": "string",
    "environment": "string",
    "release": "string",
    "token": "string"
  },
  "error": {
    "code": "string",
    "message": "string"
  },
  "source": {
    "channel": "B2B",
    "device": "WEB",
    "deviceInfo": "string"
  },
  "booking": {
    "reference": "string",
    "cancellationReference": "string",
    "clientReference": "string",
    "creationDate": "2017-10-21",
    "status": "NEW",
    "modificationPolicies": {
      "cancellation": false,
      "modification": false
    },
    "agCommision": 0,
    "commisionVAT": 0,
    "creationUser": "string",
    "holder": {
      "name": "string",
      "surname": "string"
    },
    "remark": "string",
    "totalSellingRate": 0,
    "totalNet": 0,
    "pendingAmount": 0,
    "currency": "string",
    "hotel": {
      "checkOut": "2017-10-21",
      "checkIn": "2017-10-21",
      "code": 0,
      "name": "string",
      "description": "string",
      "image": "string",
      "categoryCode": "string",
      "categoryName": "string",
      "destinationCode": "string",
      "destinationName": "string",
      "zoneCode": 0,
      "zoneName": "string",
      "latitude": "string",
      "longitude": "string",
      "giata": "string",
      "minRate": 0,
      "maxRate": 0,
      "totalSellingRate": 0,
      "totalNet": 0,
      "pendingAmount": 0,
      "currency": "string",
      "supplier": {
        "name": "string",
        "vatNumber": "string"
      },
      "clientComments": "string",
      "cancellationAmount": 0,
      "upselling": {
        "room": [
          {
            "status": "NEW",
            "id": 0,
            "code": "string",
            "name": "string",
            "pax": [
              {
                "roomId": 1,
                "type": "AD",
                "age": 20,
                "name": "string",
                "surname": "string"
              }
            ],
            "rate": [
              {
                "rateKey": "string",
                "rateClass": "string",
                "rateType": "BOOKABLE",
                "net": 0,
                "discount": 0,
                "discountPCT": 0,
                "sellingRate": 0,
                "hotelSellingRate": 0,
                "amount": 0,
                "hotelCurrency": "string",
                "hotelMandatory": false,
                "allotment": 0,
                "commission": 0,
                "commissionVAT": 0,
                "commissionPCT": 0,
                "cost": {
                  "amount": 0,
                  "currency": "string"
                },
                "rateCommentsId": "string",
                "rateComments": "string",
                "paymentType": "AT_HOTEL",
                "packaging": false,
                "boardCode": "string",
                "boardName": "string",
                "rateBreakDown": {
                  "rateDiscount": [
                    {
                      "code": "string",
                      "name": "string",
                      "amount": 0
                    }
                  ],
                  "rateSupplement": [
                    {
                      "code": "string",
                      "name": "string",
                      "from": "2017-10-21",
                      "to": "2017-10-21",
                      "amount": 0,
                      "nights": 0,
                      "paxNumber": 0
                    }
                  ]
                },
                "rooms": 0,
                "adults": 0,
                "children": 0,
                "childrenAges": "string",
                "rateup": 0,
                "comment": [
                  {
                    "type": "string",
                    "text": "string"
                  }
                ],
                "cancellationPolicy": [
                  {
                    "amount": 0,
                    "hotelAmount": 0,
                    "hotelCurrency": "string",
                    "from": "string"
                  }
                ],
                "taxes": {
                  "allIncluded": false,
                  "tax": [
                    {
                      "included": false,
                      "percent": 0,
                      "amount": 0,
                      "currency": "string",
                      "type": "TAX",
                      "clientAmount": 0,
                      "clientCurrency": "string"
                    }
                  ]
                },
                "promotion": [
                  {
                    "code": "string",
                    "name": "string",
                    "remark": "string"
                  }
                ],
                "offer": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "shiftRate": [
                  {
                    "rateKey": "string",
                    "rateClass": "string",
                    "rateType": "BOOKABLE",
                    "net": 0,
                    "discount": 0,
                    "discountPCT": 0,
                    "sellingRate": 0,
                    "hotelSellingRate": 0,
                    "amount": 0,
                    "hotelCurrency": "string",
                    "hotelMandatory": false,
                    "allotment": 0,
                    "commission": 0,
                    "commissionVAT": 0,
                    "commissionPCT": 0,
                    "cost": {
                      "amount": 0,
                      "currency": "string"
                    },
                    "checkIn": "2017-10-21",
                    "checkOut": "2017-10-21"
                  }
                ],
                "dailyRate": [
                  {
                    "offset": 0,
                    "dailyNet": 0,
                    "dailySellingRate": 0
                  }
                ]
              }
            ]
          }
        ]
      },
      "keyword": [
        {
          "code": 0,
          "rating": 0
        }
      ],
      "review": [
        {
          "rate": 0,
          "reviewCount": 0,
          "type": "string"
        }
      ],
      "room": [
        {
          "status": "NEW",
          "id": 0,
          "code": "string",
          "name": "string",
          "pax": [
            {
              "roomId": 1,
              "type": "AD",
              "age": 20,
              "name": "string",
              "surname": "string"
            }
          ],
          "rate": [
            {
              "rateKey": "string",
              "rateClass": "string",
              "rateType": "BOOKABLE",
              "net": 0,
              "discount": 0,
              "discountPCT": 0,
              "sellingRate": 0,
              "hotelSellingRate": 0,
              "amount": 0,
              "hotelCurrency": "string",
              "hotelMandatory": false,
              "allotment": 0,
              "commission": 0,
              "commissionVAT": 0,
              "commissionPCT": 0,
              "cost": {
                "amount": 0,
                "currency": "string"
              },
              "rateCommentsId": "string",
              "rateComments": "string",
              "paymentType": "AT_HOTEL",
              "packaging": false,
              "boardCode": "string",
              "boardName": "string",
              "rateBreakDown": {
                "rateDiscount": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "rateSupplement": [
                  {
                    "code": "string",
                    "name": "string",
                    "from": "2017-10-21",
                    "to": "2017-10-21",
                    "amount": 0,
                    "nights": 0,
                    "paxNumber": 0
                  }
                ]
              },
              "rooms": 0,
              "adults": 0,
              "children": 0,
              "childrenAges": "string",
              "rateup": 0,
              "comment": [
                {
                  "type": "string",
                  "text": "string"
                }
              ],
              "cancellationPolicy": [
                {
                  "amount": 0,
                  "hotelAmount": 0,
                  "hotelCurrency": "string",
                  "from": "string"
                }
              ],
              "taxes": {
                "allIncluded": false,
                "tax": [
                  {
                    "included": false,
                    "percent": 0,
                    "amount": 0,
                    "currency": "string",
                    "type": "TAX",
                    "clientAmount": 0,
                    "clientCurrency": "string"
                  }
                ]
              },
              "promotion": [
                {
                  "code": "string",
                  "name": "string",
                  "remark": "string"
                }
              ],
              "offer": [
                {
                  "code": "string",
                  "name": "string",
                  "amount": 0
                }
              ],
              "shiftRate": [
                {
                  "rateKey": "string",
                  "rateClass": "string",
                  "rateType": "BOOKABLE",
                  "net": 0,
                  "discount": 0,
                  "discountPCT": 0,
                  "sellingRate": 0,
                  "hotelSellingRate": 0,
                  "amount": 0,
                  "hotelCurrency": "string",
                  "hotelMandatory": false,
                  "allotment": 0,
                  "commission": 0,
                  "commissionVAT": 0,
                  "commissionPCT": 0,
                  "cost": {
                    "amount": 0,
                    "currency": "string"
                  },
                  "checkIn": "2017-10-21",
                  "checkOut": "2017-10-21"
                }
              ],
              "dailyRate": [
                {
                  "offset": 0,
                  "dailyNet": 0,
                  "dailySellingRate": 0
                }
              ]
            }
          ]
        }
      ],
      "creditCard": [
        {
          "code": "string",
          "name": "string",
          "paymentType": "AT_HOTEL"
        }
      ]
    }
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
echoToken|string|false|No description
auditData|[ApiAuditData](#schemaapiauditdata)|true|No description
» processTime|string|false|No description
» timestamp|string|false|No description
» requestHost|string|false|No description
» serverId|string|false|No description
» environment|string|false|No description
» release|string|false|No description
» token|string|false|No description
error|[apiError](#schemaapierror)|false|No description
» code|string|false|No description
» message|string|false|No description
source|[ApiSource](#schemaapisource)|false|No description
» channel|string|true|No description
» device|string|true|No description
» deviceInfo|string|false|No description
booking|[ApiBooking](#schemaapibooking)|false|No description
» reference|string|false|No description
» cancellationReference|string|false|No description
» clientReference|string|false|No description
» creationDate|string(date)|false|No description
» status|string|false|No description
» modificationPolicies|[ApiModificationPolicies](#schemaapimodificationpolicies)|false|No description
»» cancellation|boolean|true|No description
»» modification|boolean|true|No description
» agCommision|number|false|No description
» commisionVAT|number|false|No description
» creationUser|string|false|No description
» holder|[ApiHolder](#schemaapiholder)|false|No description
»» name|string|true|No description
»» surname|string|true|No description
» remark|string|false|No description
» totalSellingRate|number|false|No description
» totalNet|number|false|No description
» pendingAmount|number|false|No description
» currency|string|false|No description
» hotel|[ApiHotel](#schemaapihotel)|false|No description
»» checkOut|string(date)|false|No description
»» checkIn|string(date)|false|No description
»» code|integer(int32)|false|No description
»» name|string|false|No description
»» description|string|false|No description
»» image|string|false|No description
»» categoryCode|string|false|No description
»» categoryName|string|false|No description
»» destinationCode|string|false|No description
»» destinationName|string|false|No description
»» zoneCode|integer(int32)|false|No description
»» zoneName|string|false|No description
»» latitude|string|false|No description
»» longitude|string|false|No description
»» giata|string|false|No description
»» minRate|number|false|No description
»» maxRate|number|false|No description
»» totalSellingRate|number|false|No description
»» totalNet|number|false|No description
»» pendingAmount|number|false|No description
»» currency|string|false|No description
»» supplier|[ApiSupplier](#schemaapisupplier)|false|No description
»»» name|string|false|No description
»»» vatNumber|string|false|No description
»» clientComments|string|false|No description
»» cancellationAmount|number|false|No description
»» upselling|[ApiUpselling](#schemaapiupselling)|false|No description
»»» room|[[room](#schemaroom)]|false|No description
»»»» status|string|false|No description
»»»» id|integer(int32)|false|No description
»»»» code|string|false|No description
»»»» name|string|false|No description
»»»» pax|[[ApiPax](#schemaapipax)]|false|No description
»»»»» roomId|integer(int32)|false|No description
»»»»» type|string|true|No description
»»»»» age|integer(int32)|false|No description
»»»»» name|string|false|No description
»»»»» surname|string|false|No description
»»»» rate|[[ApiRate](#schemaapirate)]|false|No description
»»»»» rateKey|string|false|No description
»»»»» rateClass|string|false|No description
»»»»» rateType|string|false|No description
»»»»» net|number|false|No description
»»»»» discount|number|false|No description
»»»»» discountPCT|number|false|No description
»»»»» sellingRate|number|false|No description
»»»»» hotelSellingRate|number|false|No description
»»»»» amount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» hotelMandatory|boolean|false|No description
»»»»» allotment|integer(int32)|false|No description
»»»»» commission|number|false|No description
»»»»» commissionVAT|number|false|No description
»»»»» commissionPCT|number|false|No description
»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»» rateCommentsId|string|false|No description
»»»»» rateComments|string|false|No description
»»»»» paymentType|string|false|No description
»»»»» packaging|boolean|false|No description
»»»»» boardCode|string|false|No description
»»»»» boardName|string|false|No description
»»»»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»»»» code|string|false|No description
»»»»»»» name|string|false|No description
»»»»»»» amount|number|false|No description
»»»»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»»»» code|string|false|No description
»»»»»»» name|string|false|No description
»»»»»»» from|string(date)|false|No description
»»»»»»» to|string(date)|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» nights|integer(int32)|false|No description
»»»»»»» paxNumber|integer(int32)|false|No description
»»»»» rooms|integer(int32)|false|No description
»»»»» adults|integer(int32)|false|No description
»»»»» children|integer(int32)|false|No description
»»»»» childrenAges|string|false|No description
»»»»» rateup|number|false|No description
»»»»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»»»»» allIncluded|boolean|false|No description
»»»»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»»»»» included|boolean|false|No description
»»»»»»» percent|number|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» currency|string|false|No description
»»»»»»» type|string|false|No description
»»»»»»» clientAmount|number|false|No description
»»»»»»» clientCurrency|string|false|No description
»»»»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»»»» type|string|false|No description
»»»»»» text|string|false|No description
»»»»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»»»» amount|number|false|No description
»»»»»» hotelAmount|number|false|No description
»»»»»» hotelCurrency|string|false|No description
»»»»»» from|string|false|No description
»»»»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» remark|string|false|No description
»»»»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» amount|number|false|No description
»»»»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»»»» rateKey|string|false|No description
»»»»»» rateClass|string|false|No description
»»»»»» rateType|string|false|No description
»»»»»» net|number|false|No description
»»»»»» discount|number|false|No description
»»»»»» discountPCT|number|false|No description
»»»»»» sellingRate|number|false|No description
»»»»»» hotelSellingRate|number|false|No description
»»»»»» amount|number|false|No description
»»»»»» hotelCurrency|string|false|No description
»»»»»» hotelMandatory|boolean|false|No description
»»»»»» allotment|integer(int32)|false|No description
»»»»»» commission|number|false|No description
»»»»»» commissionVAT|number|false|No description
»»»»»» commissionPCT|number|false|No description
»»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»»» amount|number|false|No description
»»»»»»» currency|string|false|No description
»»»»»» checkIn|string(date)|false|No description
»»»»»» checkOut|string(date)|false|No description
»»»»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»»»» offset|integer(int32)|false|No description
»»»»»» dailyNet|number|false|No description
»»»»»» dailySellingRate|number|false|No description
»» keyword|[[ApiKeyword](#schemaapikeyword)]|false|No description
»»» code|integer(int32)|true|No description
»»» rating|integer(int32)|false|No description
»» review|[[ApiReview](#schemaapireview)]|false|No description
»»» rate|number|false|No description
»»» reviewCount|integer(int32)|false|No description
»»» type|string|false|No description
»» room|[[room](#schemaroom)]|false|No description
»»» status|string|false|No description
»»» id|integer(int32)|false|No description
»»» code|string|false|No description
»»» name|string|false|No description
»»» pax|[[ApiPax](#schemaapipax)]|false|No description
»»»» roomId|integer(int32)|false|No description
»»»» type|string|true|No description
»»»» age|integer(int32)|false|No description
»»»» name|string|false|No description
»»»» surname|string|false|No description
»»» rate|[[ApiRate](#schemaapirate)]|false|No description
»»»» rateKey|string|false|No description
»»»» rateClass|string|false|No description
»»»» rateType|string|false|No description
»»»» net|number|false|No description
»»»» discount|number|false|No description
»»»» discountPCT|number|false|No description
»»»» sellingRate|number|false|No description
»»»» hotelSellingRate|number|false|No description
»»»» amount|number|false|No description
»»»» hotelCurrency|string|false|No description
»»»» hotelMandatory|boolean|false|No description
»»»» allotment|integer(int32)|false|No description
»»»» commission|number|false|No description
»»»» commissionVAT|number|false|No description
»»»» commissionPCT|number|false|No description
»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»» amount|number|false|No description
»»»»» currency|string|false|No description
»»»» rateCommentsId|string|false|No description
»»»» rateComments|string|false|No description
»»»» paymentType|string|false|No description
»»»» packaging|boolean|false|No description
»»»» boardCode|string|false|No description
»»»» boardName|string|false|No description
»»»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» amount|number|false|No description
»»»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» from|string(date)|false|No description
»»»»»» to|string(date)|false|No description
»»»»»» amount|number|false|No description
»»»»»» nights|integer(int32)|false|No description
»»»»»» paxNumber|integer(int32)|false|No description
»»»» rooms|integer(int32)|false|No description
»»»» adults|integer(int32)|false|No description
»»»» children|integer(int32)|false|No description
»»»» childrenAges|string|false|No description
»»»» rateup|number|false|No description
»»»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»»»» allIncluded|boolean|false|No description
»»»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»»»» included|boolean|false|No description
»»»»»» percent|number|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»»» type|string|false|No description
»»»»»» clientAmount|number|false|No description
»»»»»» clientCurrency|string|false|No description
»»»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»»» type|string|false|No description
»»»»» text|string|false|No description
»»»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»»» amount|number|false|No description
»»»»» hotelAmount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» from|string|false|No description
»»»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» remark|string|false|No description
»»»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» amount|number|false|No description
»»»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»»» rateKey|string|false|No description
»»»»» rateClass|string|false|No description
»»»»» rateType|string|false|No description
»»»»» net|number|false|No description
»»»»» discount|number|false|No description
»»»»» discountPCT|number|false|No description
»»»»» sellingRate|number|false|No description
»»»»» hotelSellingRate|number|false|No description
»»»»» amount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» hotelMandatory|boolean|false|No description
»»»»» allotment|integer(int32)|false|No description
»»»»» commission|number|false|No description
»»»»» commissionVAT|number|false|No description
»»»»» commissionPCT|number|false|No description
»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»» checkIn|string(date)|false|No description
»»»»» checkOut|string(date)|false|No description
»»»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»»» offset|integer(int32)|false|No description
»»»»» dailyNet|number|false|No description
»»»»» dailySellingRate|number|false|No description
»» creditCard|[[ApiCreditCard](#schemaapicreditcard)]|false|No description
»»» code|string|false|No description
»»» name|string|false|No description
»»» paymentType|string|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
» channel|B2B|
» channel|B2C|
» channel|META|
» channel|NEWSLETTER|
» device|MOBILE|
» device|WEB|
» device|TABLET|
» status|NEW|
» status|PRECONFIRMED|
» status|CONFIRMED|
» status|TO_BE_UPDATED|
» status|CANCELLED|
» status|TO_BE_CANCELLED|
»»»» status|NEW|
»»»» status|PRECONFIRMED|
»»»» status|CONFIRMED|
»»»» status|TO_BE_UPDATED|
»»»» status|CANCELLED|
»»»» status|TO_BE_CANCELLED|
»»»»» type|AD|
»»»»» type|CH|
»»»»» rateType|BOOKABLE|
»»»»» rateType|RECHECK|
»»»»» paymentType|AT_HOTEL|
»»»»» paymentType|AT_WEB|
»»»»»»» type|TAX|
»»»»»»» type|FEE|
»»»»»» rateType|BOOKABLE|
»»»»»» rateType|RECHECK|
»»» status|NEW|
»»» status|PRECONFIRMED|
»»» status|CONFIRMED|
»»» status|TO_BE_UPDATED|
»»» status|CANCELLED|
»»» status|TO_BE_CANCELLED|
»»»» type|AD|
»»»» type|CH|
»»»» rateType|BOOKABLE|
»»»» rateType|RECHECK|
»»»» paymentType|AT_HOTEL|
»»»» paymentType|AT_WEB|
»»»»»» type|TAX|
»»»»»» type|FEE|
»»»»» rateType|BOOKABLE|
»»»»» rateType|RECHECK|
»»» paymentType|AT_HOTEL|
»»» paymentType|AT_WEB|


## checkRateRQ

<a name="schemacheckraterq"></a>

```json
{
  "echoToken": "string",
  "upselling": false,
  "language": "ENG",
  "room": [
    {
      "rateKey": "string",
      "pax": [
        {
          "roomId": 1,
          "type": "AD",
          "age": 20,
          "name": "string",
          "surname": "string"
        }
      ]
    }
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
echoToken|string|false|No description
upselling|boolean|false|No description
language|string|false|No description
room|[[ApiBookingRoom](#schemaapibookingroom)]|false|No description
» rateKey|string|true|No description
» pax|[[ApiPax](#schemaapipax)]|false|No description
»» roomId|integer(int32)|false|No description
»» type|string|true|No description
»» age|integer(int32)|false|No description
»» name|string|false|No description
»» surname|string|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
»» type|AD|
»» type|CH|


## checkRateRS

<a name="schemacheckraters"></a>

```json
{
  "echoToken": "string",
  "auditData": {
    "processTime": "string",
    "timestamp": "string",
    "requestHost": "string",
    "serverId": "string",
    "environment": "string",
    "release": "string",
    "token": "string"
  },
  "error": {
    "code": "string",
    "message": "string"
  },
  "hotel": {
    "checkOut": "2017-10-21",
    "checkIn": "2017-10-21",
    "code": 0,
    "name": "string",
    "description": "string",
    "image": "string",
    "categoryCode": "string",
    "categoryName": "string",
    "destinationCode": "string",
    "destinationName": "string",
    "zoneCode": 0,
    "zoneName": "string",
    "latitude": "string",
    "longitude": "string",
    "giata": "string",
    "minRate": 0,
    "maxRate": 0,
    "totalSellingRate": 0,
    "totalNet": 0,
    "pendingAmount": 0,
    "currency": "string",
    "supplier": {
      "name": "string",
      "vatNumber": "string"
    },
    "clientComments": "string",
    "cancellationAmount": 0,
    "upselling": {
      "room": [
        {
          "status": "NEW",
          "id": 0,
          "code": "string",
          "name": "string",
          "pax": [
            {
              "roomId": 1,
              "type": "AD",
              "age": 20,
              "name": "string",
              "surname": "string"
            }
          ],
          "rate": [
            {
              "rateKey": "string",
              "rateClass": "string",
              "rateType": "BOOKABLE",
              "net": 0,
              "discount": 0,
              "discountPCT": 0,
              "sellingRate": 0,
              "hotelSellingRate": 0,
              "amount": 0,
              "hotelCurrency": "string",
              "hotelMandatory": false,
              "allotment": 0,
              "commission": 0,
              "commissionVAT": 0,
              "commissionPCT": 0,
              "cost": {
                "amount": 0,
                "currency": "string"
              },
              "rateCommentsId": "string",
              "rateComments": "string",
              "paymentType": "AT_HOTEL",
              "packaging": false,
              "boardCode": "string",
              "boardName": "string",
              "rateBreakDown": {
                "rateDiscount": [
                  {
                    "code": "string",
                    "name": "string",
                    "amount": 0
                  }
                ],
                "rateSupplement": [
                  {
                    "code": "string",
                    "name": "string",
                    "from": "2017-10-21",
                    "to": "2017-10-21",
                    "amount": 0,
                    "nights": 0,
                    "paxNumber": 0
                  }
                ]
              },
              "rooms": 0,
              "adults": 0,
              "children": 0,
              "childrenAges": "string",
              "rateup": 0,
              "comment": [
                {
                  "type": "string",
                  "text": "string"
                }
              ],
              "cancellationPolicy": [
                {
                  "amount": 0,
                  "hotelAmount": 0,
                  "hotelCurrency": "string",
                  "from": "string"
                }
              ],
              "taxes": {
                "allIncluded": false,
                "tax": [
                  {
                    "included": false,
                    "percent": 0,
                    "amount": 0,
                    "currency": "string",
                    "type": "TAX",
                    "clientAmount": 0,
                    "clientCurrency": "string"
                  }
                ]
              },
              "promotion": [
                {
                  "code": "string",
                  "name": "string",
                  "remark": "string"
                }
              ],
              "offer": [
                {
                  "code": "string",
                  "name": "string",
                  "amount": 0
                }
              ],
              "shiftRate": [
                {
                  "rateKey": "string",
                  "rateClass": "string",
                  "rateType": "BOOKABLE",
                  "net": 0,
                  "discount": 0,
                  "discountPCT": 0,
                  "sellingRate": 0,
                  "hotelSellingRate": 0,
                  "amount": 0,
                  "hotelCurrency": "string",
                  "hotelMandatory": false,
                  "allotment": 0,
                  "commission": 0,
                  "commissionVAT": 0,
                  "commissionPCT": 0,
                  "cost": {
                    "amount": 0,
                    "currency": "string"
                  },
                  "checkIn": "2017-10-21",
                  "checkOut": "2017-10-21"
                }
              ],
              "dailyRate": [
                {
                  "offset": 0,
                  "dailyNet": 0,
                  "dailySellingRate": 0
                }
              ]
            }
          ]
        }
      ]
    },
    "keyword": [
      {
        "code": 0,
        "rating": 0
      }
    ],
    "review": [
      {
        "rate": 0,
        "reviewCount": 0,
        "type": "string"
      }
    ],
    "room": [
      {
        "status": "NEW",
        "id": 0,
        "code": "string",
        "name": "string",
        "pax": [
          {
            "roomId": 1,
            "type": "AD",
            "age": 20,
            "name": "string",
            "surname": "string"
          }
        ],
        "rate": [
          {
            "rateKey": "string",
            "rateClass": "string",
            "rateType": "BOOKABLE",
            "net": 0,
            "discount": 0,
            "discountPCT": 0,
            "sellingRate": 0,
            "hotelSellingRate": 0,
            "amount": 0,
            "hotelCurrency": "string",
            "hotelMandatory": false,
            "allotment": 0,
            "commission": 0,
            "commissionVAT": 0,
            "commissionPCT": 0,
            "cost": {
              "amount": 0,
              "currency": "string"
            },
            "rateCommentsId": "string",
            "rateComments": "string",
            "paymentType": "AT_HOTEL",
            "packaging": false,
            "boardCode": "string",
            "boardName": "string",
            "rateBreakDown": {
              "rateDiscount": [
                {
                  "code": "string",
                  "name": "string",
                  "amount": 0
                }
              ],
              "rateSupplement": [
                {
                  "code": "string",
                  "name": "string",
                  "from": "2017-10-21",
                  "to": "2017-10-21",
                  "amount": 0,
                  "nights": 0,
                  "paxNumber": 0
                }
              ]
            },
            "rooms": 0,
            "adults": 0,
            "children": 0,
            "childrenAges": "string",
            "rateup": 0,
            "comment": [
              {
                "type": "string",
                "text": "string"
              }
            ],
            "cancellationPolicy": [
              {
                "amount": 0,
                "hotelAmount": 0,
                "hotelCurrency": "string",
                "from": "string"
              }
            ],
            "taxes": {
              "allIncluded": false,
              "tax": [
                {
                  "included": false,
                  "percent": 0,
                  "amount": 0,
                  "currency": "string",
                  "type": "TAX",
                  "clientAmount": 0,
                  "clientCurrency": "string"
                }
              ]
            },
            "promotion": [
              {
                "code": "string",
                "name": "string",
                "remark": "string"
              }
            ],
            "offer": [
              {
                "code": "string",
                "name": "string",
                "amount": 0
              }
            ],
            "shiftRate": [
              {
                "rateKey": "string",
                "rateClass": "string",
                "rateType": "BOOKABLE",
                "net": 0,
                "discount": 0,
                "discountPCT": 0,
                "sellingRate": 0,
                "hotelSellingRate": 0,
                "amount": 0,
                "hotelCurrency": "string",
                "hotelMandatory": false,
                "allotment": 0,
                "commission": 0,
                "commissionVAT": 0,
                "commissionPCT": 0,
                "cost": {
                  "amount": 0,
                  "currency": "string"
                },
                "checkIn": "2017-10-21",
                "checkOut": "2017-10-21"
              }
            ],
            "dailyRate": [
              {
                "offset": 0,
                "dailyNet": 0,
                "dailySellingRate": 0
              }
            ]
          }
        ]
      }
    ],
    "creditCard": [
      {
        "code": "string",
        "name": "string",
        "paymentType": "AT_HOTEL"
      }
    ]
  },
  "source": {
    "channel": "B2B",
    "device": "WEB",
    "deviceInfo": "string"
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
echoToken|string|false|No description
auditData|[ApiAuditData](#schemaapiauditdata)|true|No description
» processTime|string|false|No description
» timestamp|string|false|No description
» requestHost|string|false|No description
» serverId|string|false|No description
» environment|string|false|No description
» release|string|false|No description
» token|string|false|No description
error|[apiError](#schemaapierror)|false|No description
» code|string|false|No description
» message|string|false|No description
hotel|[ApiHotel](#schemaapihotel)|false|No description
» checkOut|string(date)|false|No description
» checkIn|string(date)|false|No description
» code|integer(int32)|false|No description
» name|string|false|No description
» description|string|false|No description
» image|string|false|No description
» categoryCode|string|false|No description
» categoryName|string|false|No description
» destinationCode|string|false|No description
» destinationName|string|false|No description
» zoneCode|integer(int32)|false|No description
» zoneName|string|false|No description
» latitude|string|false|No description
» longitude|string|false|No description
» giata|string|false|No description
» minRate|number|false|No description
» maxRate|number|false|No description
» totalSellingRate|number|false|No description
» totalNet|number|false|No description
» pendingAmount|number|false|No description
» currency|string|false|No description
» supplier|[ApiSupplier](#schemaapisupplier)|false|No description
»» name|string|false|No description
»» vatNumber|string|false|No description
» clientComments|string|false|No description
» cancellationAmount|number|false|No description
» upselling|[ApiUpselling](#schemaapiupselling)|false|No description
»» room|[[room](#schemaroom)]|false|No description
»»» status|string|false|No description
»»» id|integer(int32)|false|No description
»»» code|string|false|No description
»»» name|string|false|No description
»»» pax|[[ApiPax](#schemaapipax)]|false|No description
»»»» roomId|integer(int32)|false|No description
»»»» type|string|true|No description
»»»» age|integer(int32)|false|No description
»»»» name|string|false|No description
»»»» surname|string|false|No description
»»» rate|[[ApiRate](#schemaapirate)]|false|No description
»»»» rateKey|string|false|No description
»»»» rateClass|string|false|No description
»»»» rateType|string|false|No description
»»»» net|number|false|No description
»»»» discount|number|false|No description
»»»» discountPCT|number|false|No description
»»»» sellingRate|number|false|No description
»»»» hotelSellingRate|number|false|No description
»»»» amount|number|false|No description
»»»» hotelCurrency|string|false|No description
»»»» hotelMandatory|boolean|false|No description
»»»» allotment|integer(int32)|false|No description
»»»» commission|number|false|No description
»»»» commissionVAT|number|false|No description
»»»» commissionPCT|number|false|No description
»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»» amount|number|false|No description
»»»»» currency|string|false|No description
»»»» rateCommentsId|string|false|No description
»»»» rateComments|string|false|No description
»»»» paymentType|string|false|No description
»»»» packaging|boolean|false|No description
»»»» boardCode|string|false|No description
»»»» boardName|string|false|No description
»»»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» amount|number|false|No description
»»»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»»» code|string|false|No description
»»»»»» name|string|false|No description
»»»»»» from|string(date)|false|No description
»»»»»» to|string(date)|false|No description
»»»»»» amount|number|false|No description
»»»»»» nights|integer(int32)|false|No description
»»»»»» paxNumber|integer(int32)|false|No description
»»»» rooms|integer(int32)|false|No description
»»»» adults|integer(int32)|false|No description
»»»» children|integer(int32)|false|No description
»»»» childrenAges|string|false|No description
»»»» rateup|number|false|No description
»»»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»»»» allIncluded|boolean|false|No description
»»»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»»»» included|boolean|false|No description
»»»»»» percent|number|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»»» type|string|false|No description
»»»»»» clientAmount|number|false|No description
»»»»»» clientCurrency|string|false|No description
»»»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»»» type|string|false|No description
»»»»» text|string|false|No description
»»»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»»» amount|number|false|No description
»»»»» hotelAmount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» from|string|false|No description
»»»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» remark|string|false|No description
»»»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» amount|number|false|No description
»»»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»»» rateKey|string|false|No description
»»»»» rateClass|string|false|No description
»»»»» rateType|string|false|No description
»»»»» net|number|false|No description
»»»»» discount|number|false|No description
»»»»» discountPCT|number|false|No description
»»»»» sellingRate|number|false|No description
»»»»» hotelSellingRate|number|false|No description
»»»»» amount|number|false|No description
»»»»» hotelCurrency|string|false|No description
»»»»» hotelMandatory|boolean|false|No description
»»»»» allotment|integer(int32)|false|No description
»»»»» commission|number|false|No description
»»»»» commissionVAT|number|false|No description
»»»»» commissionPCT|number|false|No description
»»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»»» amount|number|false|No description
»»»»»» currency|string|false|No description
»»»»» checkIn|string(date)|false|No description
»»»»» checkOut|string(date)|false|No description
»»»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»»» offset|integer(int32)|false|No description
»»»»» dailyNet|number|false|No description
»»»»» dailySellingRate|number|false|No description
» keyword|[[ApiKeyword](#schemaapikeyword)]|false|No description
»» code|integer(int32)|true|No description
»» rating|integer(int32)|false|No description
» review|[[ApiReview](#schemaapireview)]|false|No description
»» rate|number|false|No description
»» reviewCount|integer(int32)|false|No description
»» type|string|false|No description
» room|[[room](#schemaroom)]|false|No description
»» status|string|false|No description
»» id|integer(int32)|false|No description
»» code|string|false|No description
»» name|string|false|No description
»» pax|[[ApiPax](#schemaapipax)]|false|No description
»»» roomId|integer(int32)|false|No description
»»» type|string|true|No description
»»» age|integer(int32)|false|No description
»»» name|string|false|No description
»»» surname|string|false|No description
»» rate|[[ApiRate](#schemaapirate)]|false|No description
»»» rateKey|string|false|No description
»»» rateClass|string|false|No description
»»» rateType|string|false|No description
»»» net|number|false|No description
»»» discount|number|false|No description
»»» discountPCT|number|false|No description
»»» sellingRate|number|false|No description
»»» hotelSellingRate|number|false|No description
»»» amount|number|false|No description
»»» hotelCurrency|string|false|No description
»»» hotelMandatory|boolean|false|No description
»»» allotment|integer(int32)|false|No description
»»» commission|number|false|No description
»»» commissionVAT|number|false|No description
»»» commissionPCT|number|false|No description
»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»» amount|number|false|No description
»»»» currency|string|false|No description
»»» rateCommentsId|string|false|No description
»»» rateComments|string|false|No description
»»» paymentType|string|false|No description
»»» packaging|boolean|false|No description
»»» boardCode|string|false|No description
»»» boardName|string|false|No description
»»» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»»»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» amount|number|false|No description
»»»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»»»» code|string|false|No description
»»»»» name|string|false|No description
»»»»» from|string(date)|false|No description
»»»»» to|string(date)|false|No description
»»»»» amount|number|false|No description
»»»»» nights|integer(int32)|false|No description
»»»»» paxNumber|integer(int32)|false|No description
»»» rooms|integer(int32)|false|No description
»»» adults|integer(int32)|false|No description
»»» children|integer(int32)|false|No description
»»» childrenAges|string|false|No description
»»» rateup|number|false|No description
»»» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»»»» allIncluded|boolean|false|No description
»»»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»»»» included|boolean|false|No description
»»»»» percent|number|false|No description
»»»»» amount|number|false|No description
»»»»» currency|string|false|No description
»»»»» type|string|false|No description
»»»»» clientAmount|number|false|No description
»»»»» clientCurrency|string|false|No description
»»» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»»»» type|string|false|No description
»»»» text|string|false|No description
»»» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»»»» amount|number|false|No description
»»»» hotelAmount|number|false|No description
»»»» hotelCurrency|string|false|No description
»»»» from|string|false|No description
»»» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»»»» code|string|false|No description
»»»» name|string|false|No description
»»»» remark|string|false|No description
»»» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»»»» code|string|false|No description
»»»» name|string|false|No description
»»»» amount|number|false|No description
»»» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»»»» rateKey|string|false|No description
»»»» rateClass|string|false|No description
»»»» rateType|string|false|No description
»»»» net|number|false|No description
»»»» discount|number|false|No description
»»»» discountPCT|number|false|No description
»»»» sellingRate|number|false|No description
»»»» hotelSellingRate|number|false|No description
»»»» amount|number|false|No description
»»»» hotelCurrency|string|false|No description
»»»» hotelMandatory|boolean|false|No description
»»»» allotment|integer(int32)|false|No description
»»»» commission|number|false|No description
»»»» commissionVAT|number|false|No description
»»»» commissionPCT|number|false|No description
»»»» cost|[ApiCost](#schemaapicost)|false|No description
»»»»» amount|number|false|No description
»»»»» currency|string|false|No description
»»»» checkIn|string(date)|false|No description
»»»» checkOut|string(date)|false|No description
»»» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»»»» offset|integer(int32)|false|No description
»»»» dailyNet|number|false|No description
»»»» dailySellingRate|number|false|No description
» creditCard|[[ApiCreditCard](#schemaapicreditcard)]|false|No description
»» code|string|false|No description
»» name|string|false|No description
»» paymentType|string|false|No description
source|[ApiSource](#schemaapisource)|false|No description
» channel|string|true|No description
» device|string|true|No description
» deviceInfo|string|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
»»» status|NEW|
»»» status|PRECONFIRMED|
»»» status|CONFIRMED|
»»» status|TO_BE_UPDATED|
»»» status|CANCELLED|
»»» status|TO_BE_CANCELLED|
»»»» type|AD|
»»»» type|CH|
»»»» rateType|BOOKABLE|
»»»» rateType|RECHECK|
»»»» paymentType|AT_HOTEL|
»»»» paymentType|AT_WEB|
»»»»»» type|TAX|
»»»»»» type|FEE|
»»»»» rateType|BOOKABLE|
»»»»» rateType|RECHECK|
»» status|NEW|
»» status|PRECONFIRMED|
»» status|CONFIRMED|
»» status|TO_BE_UPDATED|
»» status|CANCELLED|
»» status|TO_BE_CANCELLED|
»»» type|AD|
»»» type|CH|
»»» rateType|BOOKABLE|
»»» rateType|RECHECK|
»»» paymentType|AT_HOTEL|
»»» paymentType|AT_WEB|
»»»»» type|TAX|
»»»»» type|FEE|
»»»» rateType|BOOKABLE|
»»»» rateType|RECHECK|
»» paymentType|AT_HOTEL|
»» paymentType|AT_WEB|
» channel|B2B|
» channel|B2C|
» channel|META|
» channel|NEWSLETTER|
» device|MOBILE|
» device|WEB|
» device|TABLET|


## room

<a name="schemaroom"></a>

```json
{
  "status": "NEW",
  "id": 0,
  "code": "string",
  "name": "string",
  "pax": [
    {
      "roomId": 1,
      "type": "AD",
      "age": 20,
      "name": "string",
      "surname": "string"
    }
  ],
  "rate": [
    {
      "rateKey": "string",
      "rateClass": "string",
      "rateType": "BOOKABLE",
      "net": 0,
      "discount": 0,
      "discountPCT": 0,
      "sellingRate": 0,
      "hotelSellingRate": 0,
      "amount": 0,
      "hotelCurrency": "string",
      "hotelMandatory": false,
      "allotment": 0,
      "commission": 0,
      "commissionVAT": 0,
      "commissionPCT": 0,
      "cost": {
        "amount": 0,
        "currency": "string"
      },
      "rateCommentsId": "string",
      "rateComments": "string",
      "paymentType": "AT_HOTEL",
      "packaging": false,
      "boardCode": "string",
      "boardName": "string",
      "rateBreakDown": {
        "rateDiscount": [
          {
            "code": "string",
            "name": "string",
            "amount": 0
          }
        ],
        "rateSupplement": [
          {
            "code": "string",
            "name": "string",
            "from": "2017-10-21",
            "to": "2017-10-21",
            "amount": 0,
            "nights": 0,
            "paxNumber": 0
          }
        ]
      },
      "rooms": 0,
      "adults": 0,
      "children": 0,
      "childrenAges": "string",
      "rateup": 0,
      "comment": [
        {
          "type": "string",
          "text": "string"
        }
      ],
      "cancellationPolicy": [
        {
          "amount": 0,
          "hotelAmount": 0,
          "hotelCurrency": "string",
          "from": "string"
        }
      ],
      "taxes": {
        "allIncluded": false,
        "tax": [
          {
            "included": false,
            "percent": 0,
            "amount": 0,
            "currency": "string",
            "type": "TAX",
            "clientAmount": 0,
            "clientCurrency": "string"
          }
        ]
      },
      "promotion": [
        {
          "code": "string",
          "name": "string",
          "remark": "string"
        }
      ],
      "offer": [
        {
          "code": "string",
          "name": "string",
          "amount": 0
        }
      ],
      "shiftRate": [
        {
          "rateKey": "string",
          "rateClass": "string",
          "rateType": "BOOKABLE",
          "net": 0,
          "discount": 0,
          "discountPCT": 0,
          "sellingRate": 0,
          "hotelSellingRate": 0,
          "amount": 0,
          "hotelCurrency": "string",
          "hotelMandatory": false,
          "allotment": 0,
          "commission": 0,
          "commissionVAT": 0,
          "commissionPCT": 0,
          "cost": {
            "amount": 0,
            "currency": "string"
          },
          "checkIn": "2017-10-21",
          "checkOut": "2017-10-21"
        }
      ],
      "dailyRate": [
        {
          "offset": 0,
          "dailyNet": 0,
          "dailySellingRate": 0
        }
      ]
    }
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
status|string|false|No description
id|integer(int32)|false|No description
code|string|false|No description
name|string|false|No description
pax|[[ApiPax](#schemaapipax)]|false|No description
» roomId|integer(int32)|false|No description
» type|string|true|No description
» age|integer(int32)|false|No description
» name|string|false|No description
» surname|string|false|No description
rate|[[ApiRate](#schemaapirate)]|false|No description
» rateKey|string|false|No description
» rateClass|string|false|No description
» rateType|string|false|No description
» net|number|false|No description
» discount|number|false|No description
» discountPCT|number|false|No description
» sellingRate|number|false|No description
» hotelSellingRate|number|false|No description
» amount|number|false|No description
» hotelCurrency|string|false|No description
» hotelMandatory|boolean|false|No description
» allotment|integer(int32)|false|No description
» commission|number|false|No description
» commissionVAT|number|false|No description
» commissionPCT|number|false|No description
» cost|[ApiCost](#schemaapicost)|false|No description
»» amount|number|false|No description
»» currency|string|false|No description
» rateCommentsId|string|false|No description
» rateComments|string|false|No description
» paymentType|string|false|No description
» packaging|boolean|false|No description
» boardCode|string|false|No description
» boardName|string|false|No description
» rateBreakDown|[ApiRateBreakDown](#schemaapiratebreakdown)|false|No description
»» rateDiscount|[[ApiRateDiscount](#schemaapiratediscount)]|false|No description
»»» code|string|false|No description
»»» name|string|false|No description
»»» amount|number|false|No description
»» rateSupplement|[[ApiRateSupplement](#schemaapiratesupplement)]|false|No description
»»» code|string|false|No description
»»» name|string|false|No description
»»» from|string(date)|false|No description
»»» to|string(date)|false|No description
»»» amount|number|false|No description
»»» nights|integer(int32)|false|No description
»»» paxNumber|integer(int32)|false|No description
» rooms|integer(int32)|false|No description
» adults|integer(int32)|false|No description
» children|integer(int32)|false|No description
» childrenAges|string|false|No description
» rateup|number|false|No description
» taxes|[ApiTaxes](#schemaapitaxes)|false|No description
»» allIncluded|boolean|false|No description
»» tax|[[ApiTax](#schemaapitax)]|false|No description
»»» included|boolean|false|No description
»»» percent|number|false|No description
»»» amount|number|false|No description
»»» currency|string|false|No description
»»» type|string|false|No description
»»» clientAmount|number|false|No description
»»» clientCurrency|string|false|No description
» comment|[[ApiVoucherComment](#schemaapivouchercomment)]|false|No description
»» type|string|false|No description
»» text|string|false|No description
» cancellationPolicy|[[ApiCancellationPolicy](#schemaapicancellationpolicy)]|false|No description
»» amount|number|false|No description
»» hotelAmount|number|false|No description
»» hotelCurrency|string|false|No description
»» from|string|false|No description
» promotion|[[ApiPromotion](#schemaapipromotion)]|false|No description
»» code|string|false|No description
»» name|string|false|No description
»» remark|string|false|No description
» offer|[[ApiOffer](#schemaapioffer)]|false|No description
»» code|string|false|No description
»» name|string|false|No description
»» amount|number|false|No description
» shiftRate|[[ApiShiftRate](#schemaapishiftrate)]|false|No description
»» rateKey|string|false|No description
»» rateClass|string|false|No description
»» rateType|string|false|No description
»» net|number|false|No description
»» discount|number|false|No description
»» discountPCT|number|false|No description
»» sellingRate|number|false|No description
»» hotelSellingRate|number|false|No description
»» amount|number|false|No description
»» hotelCurrency|string|false|No description
»» hotelMandatory|boolean|false|No description
»» allotment|integer(int32)|false|No description
»» commission|number|false|No description
»» commissionVAT|number|false|No description
»» commissionPCT|number|false|No description
»» cost|[ApiCost](#schemaapicost)|false|No description
»»» amount|number|false|No description
»»» currency|string|false|No description
»» checkIn|string(date)|false|No description
»» checkOut|string(date)|false|No description
» dailyRate|[[ApiDailyRate](#schemaapidailyrate)]|false|No description
»» offset|integer(int32)|false|No description
»» dailyNet|number|false|No description
»» dailySellingRate|number|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
status|NEW|
status|PRECONFIRMED|
status|CONFIRMED|
status|TO_BE_UPDATED|
status|CANCELLED|
status|TO_BE_CANCELLED|
» type|AD|
» type|CH|
» rateType|BOOKABLE|
» rateType|RECHECK|
» paymentType|AT_HOTEL|
» paymentType|AT_WEB|
»»» type|TAX|
»»» type|FEE|
»» rateType|BOOKABLE|
»» rateType|RECHECK|





