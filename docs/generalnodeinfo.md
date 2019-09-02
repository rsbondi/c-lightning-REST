## General node info API Documentation [Back to Readme](../README.md)

### getinfo
Type: `GET`
Sample request URL: `https://localhost:3001/v1/getinfo/`
Required Params: None
Optional Params: None
Response:
"id", "alias", "color", "num_peers", "num_pending_channels", "num_active_channels", "num_inactive_channels", "address" [ {"type", "address", "port"}], "binding" [{"type", "ipv4", "address", "port"}], "version", "blockheight", "network", "msatoshi_fees_collected", "fees_collected_msat"

### listfunds
Type: `GET`
Sample request URL: `https://localhost:3001/v1/listFunds/`
Required Params: None
Optional Params: None
Response:
"outputs" : [{"txid", "output", "value", "amount_msat", "address", "status"}], "channels": [{"peer_id", "short_channel_id", "channel_sat", "our_amount_msat", "channel_total_sat", "amount_msat", "funding_txid"}]

### getbalance
Type: `GET`
Description: Invoke the 'listfunds' command to fetch the confirmed, unconfirmed and total on-chain balance
Sample request URL: `https://localhost:3001/v1/getBalance/`
Required Params: None
Optional Params: None
Response:
"totalBalance", "confBalance", "unconfBalance"

### getfees
Type: `GET`
Description: Invoke the 'getinfo' command to query the routing fee earned
Sample request URL: `https://localhost:3001/v1/getFees/`
Required Params: None
Optional Params: None
Response:
"feeCollected"

### localremotebal
Type: `GET`
Description: nvoke the 'listfunds' command to calculate and return local-remote channel balances
Sample request URL: `https://localhost:3001/v1/channel/localRemoteBal`
Required Params: None
Optional Params: None
Response:
"localBalance", "remoteBalance"