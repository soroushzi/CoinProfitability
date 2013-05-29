Is that altcoin you're considering more profitable than what you're currently mining? http://dustcoin.com/mining and http://www.coinchoose.com/ have some altcoins listed, but not all of them.  (For instance, neither of them have Yacoin listed.)  This little app I knocked together will tell you how much to expect.

It needs these to do its calculation:

 * interval over which to calculate (in seconds...86400 to calculate for a day)
 * your expected hashrate
 * the chain's current block reward
 * the current difficulty
 * (optional) exchange rate to get BTC for your altcoin

You most likely know your hashrate for SHA-256 and scrypt coins.  Difficulty is available from most block explorers.  Pools usually have the block reward available. Get the exchange rate from your favorite exchange.

I built this in Visual Studio 2012 Express against .NET Framework 4.0 (needed that version because it's the first that includes BigInteger support).  I've also tested it under Mono; its implementation of Decimal.ToString() is a bit different and needed some adjustment.  

In this release, I've added the ability to store configuration information for the coins of your choice in the registry, and to select a coin from a drop-down list.  A sample registry file (with configurations for three coins) is included.  Most items are self-explanatory.  Valid choices for ExplorerType are BlockEx (for blockexplorer.com and blockchain.info) and Abe (for block explorers running Abe).  DefaultHashRate is optional; you can set it to whatever's appropriate for your hardware.  I've only tested exchange-rate lookup against bter.com; other exchanges that offer a JSON API may also work.  For Bitcoin, the exchange rate is automatically set to 1.
