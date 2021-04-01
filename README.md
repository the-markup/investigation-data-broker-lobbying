# Data Broker Lobbying

This repository contains code and data to reproduce the findings featured in our story "[The Little-Known Data Broker Industry Is Spending Big Bucks Lobbying Congress](https://themarkup.org/privacy/2021/04/01/the-little-known-data-broker-industry-is-spending-big-bucks-lobbying-congress)."

## Methodology

We used [California](https://oag.ca.gov/data-brokers) and [Vermont](https://bizfilings.vermont.gov/online/DatabrokerInquire/DataBrokerSearch)'s data broker databases to identify company names. 

We compared the data broker company names to client names listed in the Senate's [Lobbying Disclosure Act Database](https://www.senate.gov/legislative/Public_Disclosure/database_download.htm). We looked at 2020 filings received from Q1 2020 through Q1 2021.

A copy of both the California and Vermont tables are included in this repository in the `data/brokers` folder.

We used [The Center for Responsive Politics' approach](https://www.opensecrets.org/federal-lobbying/methodology#totals) to calculate total spending amounts.

To identify bills, we used regular expression to pull bill numbers from filings' issue descriptions and searched for the titles in the [U.S. Congress legislation database](https://www.congress.gov/search?q={%22source%22:%22legislation%22,%22congress%22:116,%22type%22:%22bills%22,%22chamber%22:%22House%22}&searchResultViewType=expanded). 

## Data

### `data/findings/data-broker-filings.csv`

| Column | Description |
| -------|-------------|
| `filing_id` | The filing ID  |
| `url` | A link to the filing on the U.S. Senate's website|
| `parent_company` | The parent company, if a company is a subsidiary of a larger company|
| `company` | The company name |
| `client_name` | The company name as it appears in the filing |
| `lobbying_firm` | The lobbying firm as it appears in the filing |
| `is_self_filer` | `TRUE` or `FALSE` depending on whether the "Self" box is checked in the "Client" section of the filing |
| `type` | What kind of report the filing is, according the filing itself 
| `period` | The reporting period, according to the filing itself |
| `spending` | The estimated dollar amount spent, according to the filing|

## Licensing

Copyright 2021, The Markup News Inc.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.

3. Neither the name of the copyright holder nor the names of its contributors may be used to endorse or promote products derived from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
