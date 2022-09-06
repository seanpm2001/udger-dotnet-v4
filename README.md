# Do not use for production environments. Version 4 is for testing purposes only.

# Udger client for .NET (data ver. 4)
Local parser is very fast and accurate useragent string detection solution. Enables developers to locally install and integrate a highly-scalable product.
We provide the detection of the devices (personal computer, tablet, Smart TV, Game console etc.), operating system, client SW type (browser, e-mail client etc.)
and devices market name (example: Sony Xperia Tablet S, Nokia Lumia 820 etc.).
It also provides information about IP addresses (Public proxies, VPN services, Tor exit nodes, Fake crawlers, Web scrapers, Datacenter name .. etc.)

- Tested with more the 1.000.000 unique user agents.
- Processes Google User-Agent Client Hints
- Up to date data provided by https://udger.com/

### Requirements
- .NET Framework 4 or later.
- ADO.NET Data Provider for SQLite (included)
- datafile v4 (udgerdb_v4.dat) from https://data.udger.com/ 

### Automatic updates download
- for autoupdate data use Udger data updater (https://udger.com/support/documentation/?doc=62)

###Features
- Fast
- Written in C#
- LRU cache
- Released under the MIT


### Usage
You should review the included example (`ConsoleTest\Program.cs`)
Here's a quick example:

```csharp
UdgerParser parser = new UdgerParser();
// Set data dir (in this directory is stored data file: udgerdb_v3.dat)
// Data file can be downloaded manually from https://data.udger.com/, but we recommend use udger-updater (https://udger.com/support/documentation/?doc=62)
parser.SetDataDir(@"C:\udger");
// set user agent and/or IP address
parser.ua = "Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/48.0.2564.116 Safari/537.36";
parser.ip = "2600:3c01::f03c:91ff:fe70:9208";
// parse
parser.parse();
Udger.Parser.UserAgent a = parser.userAgent;
Udger.Parser.IPAddress i = parser.ipAddress;
```


### Documentation for programmers
- https://udger.com/pub/documentation/parser/NET/html/


### Author
The Udger.com Team (info@udger.com)

### v3 format
For the previous data format (v3), please use https://github.com/udger/udger-dotnet