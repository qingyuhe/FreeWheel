# FreeWheel Assignment - Cynthia He

## Question 1
### FreeWheel provides several publications on programmatic advertising. Read the following programmatic case study, then provide a general, clear definition of “programmatic advertising” and highlight two items from the case study that stand out to you, and why.

    Programmatic advertising is the automated use of algorithmic software to buy and sell ad inventory.


1.  The *Programmatic Module: Value in Action* graph stood out to me, not only because it's one of the few visuals of the case study, but also because it's clear there was a significant increase in the percentage of impressions and revenue in Q2 and Q3 from the year prior. It's clear that the graph is meant to illustrate the benefit of adapting the Programmatic Module. 

    However, I'm drawn to that fact that the streaming service went live on the Programmatic Module in March 2020&mdash;the beginning of the pandemic. I would like to see how much of the percentage increase of impressions and revenue can be attributed to the adaptation of the Programmatic Module and how much of it can be contributed to the fact that potentially more people were at home watching television (with this streaming service) due to quarantine.

    The report is seemingly published in 2021, so it makes sense to use data from the year prior. But even so, it would be interesting to see a *Value in Action* graph of a more recent use case to see the effectiveness of FreeWheel's Programmatic Module solution without the influence of unique external factors like the pandemic. 

2. There isn't much clarity in the text blocks describing the benefits of implementing the Programmatic Module. They all summarize these benefits with different wording or only highlight certain benefits, even if they apply to the same use case: 
        
    > [T]he client increased competition for its inventory, resulting in higher average CPMs and greater programmatic revenue, while preserving the high-quality user experience its
    customers have come to expect. (pg. 1)

    > [O]ur client increased inventory competition, win rate, and average CPM, and drove explosive revenue growth. (pg. 2)

    It's essentially the same thing but re-worded. On first glance, decyphering whether these are different outcomes or the same takes unnecessary re-reading and energy.

    This becomes especially muddled when you read the other paragraphs describing the benefits of the Programmatic Module outside of the use case: 

    > Programmatic Module facilitates unified competition across direct and programmatic demand channels, while maximizing yield and maintaining seller control. (pg. 3)
    
    > [H]olistic management across programmatic & direct with complementary demand sourcing&mdash;all without compromising your control or the user experience. (pg. 4)

    What's ironic is that there's already a valuable and eye-catching diagram (pg. 3) that summarizes and offers specific **vocabulary** to describe the benefits. It would be better utilized if the same words and the same definitions were applied in rest of the report to drive home how exactly the Programmatic Module can help the client: 

    > Programmatic module is **unified**&mdash;unifies demand across all possible sales channels by bringing all demand sources to one table. It is also **actionable** and **integrated** in that it combines direct and programmatic data into a single reporting suite and introduces programmatic demand holistically into your demand portfolio. 

## Question 2
### A digital advertising marketplace is much like Amazon or other ecommerce platforms, with sellers on one side of a transaction, and buyers on the other. Using this transaction model, answer the following:
1.  Where does the typical Agency sit (Seller or Buyer)? 
2.  Where does the typical Publisher sit (Seller or Buyer)?
3.  And why? (Describe a typical ad transaction between the two.)

![Agency and Publisher diagram](/images/FreeWheel.png "Agency and Publisher diagram")

As demonstrated in the above diagram: 
1. The Agency is typically the **Buyer**. 
2. The Publisher is typically the **Seller**. 
3. Typically, the Publisher (website, mobile app, streaming service, etc.) has ad inventory that it wants to sell to Agencies to generate revenue. The Publisher can use a Supply-Side Platform (SSP) to manage the selling of this ad inventory.

    The Agency creates advertisements to sell products or services and requires ad inventory to project those advertisements to a certain public. The Agency can use a Demand-Side Platform (DSP) to manage the buying of ad inventory. 

    At the intersection of the Buyer and Seller sides is where the Ad Exchange occurs. The SSP helps the Publisher get the best offer for its ad inventory and the DSP bids for this ad inventory. This auction occurs in real-time. 

## Question 3
### Application Programming Interfaces (APIs) are commonly used to automate large or frequent transactions. APIs also provide important structure by defining how users can interact with a product. Considering these traits, how might APIs be used in the ad industry?

Given that APIs are used often in large automated transactions, it would make sense for APIs to facilitate the Ad Exchange between SSPs and DSPs when it comes to bidding for and selling ad inventory. 

For example, Google offers a Marketplace API, which Buyers can use to manage negotiations with Publishers. The Marketplace API uses resources, such as `Deal`, to provide a detailed account of inventory, creative requirements, targeting details, etc. for ads in order to negotiate with Publishers. 

Performing a `buyers.proposals.deals.get` method can retrieve all the data about a `Deal`:

    {
        "name": "buyers/12345678/proposals/MP21673270/deals/52404",
        "createTime": "2036-12-27T04:02:39.731Z",
        "updateTime": "2036-12-27T04:03:51.097Z",
        "proposalRevision": "4",
        "displayName": "test_deal_7435251",
        "buyer": "buyers/12345678",
        "publisherProfile": "buyers/12345678/publisherProfiles/PP54321",
        "flightStartTime": "2036-12-28T00:00:00Z",
        "flightEndTime": "2036-12-30T23:59:00Z",
        "targeting": {
        "inventorySizeTargeting": {
            "targetedInventorySizes": [
            {
                "width": "1024",
                "height": "768",
                "type": "PIXEL"
            }
            ]
        }
        },
        "creativeRequirements": {
        "creativePreApprovalPolicy": "SELLER_PRE_APPROVAL_NOT_REQUIRED",
        "creativeSafeFrameCompatibility": "COMPATIBLE",
        "programmaticCreativeSource": "ADVERTISER",
        "creativeFormat": "DISPLAY"
        },
        "deliveryControl": {
        "deliveryRateType": "EVENLY"
        },
        "billedBuyer": "buyers/12345678",
        "dealType": "PROGRAMMATIC_GUARANTEED",
        "programmaticGuaranteedTerms": {
        "guaranteedLooks": "100",
        "fixedPrice": {
            "type": "CPM",
            "amount": {
            "currencyCode": "CNY",
            "units": "10"
            }
        },
        "reservationType": "STANDARD"
        },
        "sellerTimeZone": {
        "id": "Asia/Shanghai"
        }
    }

    (https://developers.google.com/authorized-buyers/apis/guides/marketplace/view-deals)

It is with APIs such as Google's Marketplace API that can facilitate the quick, real-time, yet detailed exchange of money and ad space between Buyers and Sellers. 

Additionally, the way APIs can affect how a user interacts with a product has a lot to do with ad APIs and audience management (or ad targeting). A User who interacts with specific products (websites, mobile apps, etc.) will have their information stored (probably with cookies) which then Buyers can access with ad APIs to have their advertisements of their products shown to the same or similar Users, even when they visit other sites. 

## Question 4

### What are the key differences between programmatic and direct-sold ads? Feel free to be comprehensive in your answer—and, again, no generative AI. Concepts to consider include, but are not limited to: is one more dependent on human interaction than the other? What workflows and components are used for each? etc.

| Programmatic                                                                                                                                         | Direct-Sold                                                                                       |
|------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| Agencies and Publishers buy and sell ads with  algorithmic software in the form of DSPs and SSPs. Less dependent on human interaction.                                                   | No third-party or middle-men. Agencies and Publishers  buy and sell ads to each other. More dependent on human interaction.           |
| Competitive and not guaranteed. Buying and selling ads is done through automated bids in a real-time auction.                                        | Agencies have guaranteed ad placement with Publishers.                                            |
| Ad revision can be done quickly with little adjustment.  Audience targeting changes, Publisher changes, or Agency  changes can be done immediately.  | Ad revision is manual and will take longer with negotiations between the Agency and Publisher.    |
| Ad quality is generally lower: mid-tier or remnant.                                                                                                  | Ad quality is much higher. Ex. SuperBowl and Taco Bell.                                           |
| Lower CPM (cost-per-thousand impressions). Lots of views at a lower cost.                                                                            | Higher CPM but ads are generally much more impressionable given the specific audience of the ads. |
| Vulnerable to bots and fake interaction.                                                                                                             | Limited exposure to ad fraud.                                                                     |









    

