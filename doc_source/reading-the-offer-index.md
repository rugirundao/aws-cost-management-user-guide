# Reading the Offer Index File<a name="reading-the-offer-index"></a>

After you have the offer index file, you can use it to find an offer file\.

**Topics**
+ [Offer Index File](#offer-index-example)
+ [Offer Index Definitions](#offer-index-termdef)

## Offer Index File<a name="offer-index-example"></a>

The offer index file is available as a JSON file\. You can read the file multiple ways, such as using a text program to read the JSON file or a program that parses the JSON\.

The offer index file consists of two main sections: the metadata about the offer index file itself, and either a list of the services that AWS offers \(for the offer index file\) or a list of Regions where a service is offered \(for the regional offer index file\)\. The information about an offer file includes the URL where you can download the prices and a URL for a regional offer index file for that service\.

The offer index file looks like this:

```
{
   "[formatVersion](#offer-index-format-version)":"The version number for the offer index format",
   "[disclaimer](#offer-index-disclaimer)":"The disclaimers for this offer index",
   "[publicationDate](#offer-index-publication-date)":"The publication date of this offer index",
   "[offers](#offer-index-offers)":{
      "[offerCode](#offer-index-offer-code)":{
         "[offerCode](#offer-index-offer-code)":"The service that this price list is for",
         "[currentVersionUrl](#offer-index-offer-current-version-url)":"The URL for this offer file",
         "[currentRegionIndexUrl](#offer-index-regional-index-url)":"The URL for the regional offer index file"
      },
   },
}
```

## Offer Index Definitions<a name="offer-index-termdef"></a>

The following list defines the terms that are used in the offer index file:

**FormatVersion**  
An attribute that tracks which format version the offer index file is in\. The `formatVersion` of the file is updated when the structure is changed\. For example, the version will change from `v1` to `v2`\. 

**Disclaimer**  
Any disclaimers that apply to the offer index file\.

**PublicationDate**  
The date and time \(UTC\) when an offer index file was published\. For example, `2015-04-09T02:22:05Z`, `2015-09-10T18:21:05Z`\.

**Offers**  
A list of available offer files\.

**Offers:OfferCode**  
A unique code for the product of an AWS service\. For example, `AmazonEC2` or `AmazonS3`\. The `OfferCode` is used as the lookup key for the index\.

**Offers:CurrentVersionUrl**  
The URL where you can download the most up\-to\-date offer file\.

**Offers:currentRegionIndexUrl**  
A list of available regional offer files\.