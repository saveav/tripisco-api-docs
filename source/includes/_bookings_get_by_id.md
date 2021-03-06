## Get booking

<table><tbody><tr><td>Base URL</td><td>/api/v1/books/by_id</td>
</tr><tr><td>Method</td><td>GET</td></tr></table>

This get booking by ID endpoint can be used to get specific booking data.

```json
{
  "version": 1,
  "response": {
    "agent": "A00052",
    "doer": "88FD5AE951",
    "ticket_email": "adam.pahlevi@gmail.com",
    "type": "HOTEL",
    "booking": {
      "id": "BF50814",
      "status": "CANCELLED",
      "checkin_instruction": "N/A",
      "cancellation_policy": "Kami memahami bahwa kadang kala rencana tidak berjalan seperti yang diharapkan. Tidak dikenakan biaya perubahan atau pembatalan. Namun demikian, properti ini (Capsule Homestay Surabaya) memberlakukan denda berikut kepada pelanggan yang perlu kami informasikan: pembatalan atau perubahan yang dibuat setelah pukul 18:00 ((GMT+07:00) Bangkok, Hanoi, Jakarta) tanggal 05 Mar 17 akan dikenakan denda sebesar harga 1 Kamar & Pajak.",
      "detail": {
        "hotel": {
          "bed_type_id": "42",
          "bed_type_description": "1 single",
          "hotel": {
            "id": "568385",
            "name": "Capsule Homestay Surabaya",
            "location": {
              "address1": "Jalan Kedungdoro 50 AB",
              "city": "Surabaya",
              "country_code": "ID"
            }
          },
          "date": {
            "arrival": "03/08/2017",
            "departure": "03/09/2017",
            "arrival_text": "Wed, 08 Mar 2017",
            "departure_text": "Thu, 09 Mar 2017"
          },
          "rate": {
            "name": "Capsule Express",
            "currency_code": "IDR",
            "nightly_rate_total": 74380,
            "nightly_rates": [
              74380
            ],
            "nightly_dates": [
              "March  8, 2017"
            ],
            "refundable": true,
            "require_deposit": true,
            "require_guarantee": false,
            "surcharge_total": 15619,
            "surcharges": [
              {
                "caption": "Tax Recovery Charges and Service Fees",
                "amount": "15619.00"
              }
            ],
            "hotel_fees": [],
            "hotel_fees_total": 0,
            "total": 89999
          },
          "guest": {
            "min_age": 0,
            "adults_count": 1,
            "children_count": 0,
            "children_ages": []
          }
        }
      }
    },
    "rate": {
      "currency": "IDR",
      "rate": "89999.0",
      "rate_cents": 8999900
    },
    "contact": {
      "first_name": "Adam Pahlevi",
      "last_name": "Baihaqi",
      "phone": {
        "hand": "08151666433",
        "home": "3953672"
      },
      "address": {
        "location": "Jalan Beton",
        "city": "Gresik",
        "country_code": "ID",
        "postcode": "61151"
      }
    }
  }
}
```

List of parameters:

Name | Type | Required | Description
---- | ---- | ---- | ---- |
id | String | Y | The ID of the booking that want to be retrieved

### Listing bookings response

Field name | Type | Description
---------- | ---- | ------------
agent | String | The agent/company/merchant ID
doer | String | The user registered at the agent that made the booking request
ticket_email | String | The email address to which the ticket will be sent to
type | String | What the booking is made for
detail | Object | The detailed object about the booking
booking | Object | An object that specify in detail about the booking, its status, and policies
rate | Object | An object containing the final pricing, and in what currency
contact | Object | Specify the person contactable for the booking

### `booking.detail` Object

`detail` object is returned only at this get-by-id specific request, meaning, the
booking listing endpoint will not have the `detail` object for each booking
data returned due to performance consideration.
