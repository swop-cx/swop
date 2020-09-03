# SWOP - Foreign Exchange Rate API

https://swop.cx

Transparent, secure, fast and easy-to-use GraphQL and REST API for foreign exchange rates and currency conversion.

# Getting started

1. Get a free API key [here](https://swop.cx/account/register/developer)
2. Have a look at the [docs](https://swop.cx/documentation)

# Support

Questions and suggestions are very welcome, just open an [issue](https://github.com/swop-cx/swop/issues).

# Usage

### GraphQL

Query:
```graphql
query LatestEuro {
  latest(baseCurrency: "EUR", quoteCurrencies: ["USD", "CHF", "HKD"]) {
    date
    baseCurrency
    quoteCurrency
    quote
  }
}
```

Response:
```json
{
  "data": {
    "latest": [
      {
        "date": "2020-04-08",
        "baseCurrency": "EUR",
        "quoteCurrency": "CHF",
        "quote": 1.0557
      },
      {
        "date": "2020-04-08",
        "baseCurrency": "EUR",
        "quoteCurrency": "HKD",
        "quote": 8.4277
      },
      {
        "date": "2020-04-08",
        "baseCurrency": "EUR",
        "quoteCurrency": "USD",
        "quote": 1.0871
      }
    ]
  }
}
```

### REST

Query:
```
curl -i -H "Authorization: ApiKey <api-key>" "https://swop.cx/rest/rates"
```

Response:
```json
[
  {
    "base_currency": "EUR",
    "quote_currency": "CHF",
    "quote": 1.054871,
    "date": "2020-04-04"
  },
  {
    "base_currency": "EUR",
    "quote_currency": "GBP",
    "quote": 0.878173,
    "date": "2020-04-04"
  },
  {
    "base_currency": "EUR",
    "quote_currency": "USD",
    "quote": 1.079301,
    "date": "2020-04-04"
  }
]
```
