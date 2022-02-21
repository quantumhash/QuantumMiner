# QuantumMiner

Nvidia and AMD GPU miner for `ETH`, `ETC`, `RVN`, `FIRO`

## Features
* Support Windows and Ubuntu
* Support DNS-Over-TLS
* Support SOCKS5 proxy
* Support SSL/TLS connection
* Support backup pool configuration
* Support watchdog
* Dev Fee of all algorithms is 0.5%

## Contact Us
EMail: quantumhash1024@gmail.com

## Usage

Example usage: QuantumMiner --algo ethash --pool eu1.ethermine.org:5555 --ssl --wallet 0xabcd1234abcd1234abcd1234abcd1234abcd1234

    --help           Show help text and exit

    --algo           One of ethash, etchash, kawpow, firopow, blake3

    --pool           Primary stratum pool URL
                     Format: hostname:port, e.g. eu1.ethermine.org:4444

    --wallet         Primary stratum pool wallet
                     e.g. 0xabcd1234abcd1234abcd1234abcd1234abcd1234

    --ssl            Enable ssl connection on primary pool

    --backup-pool    Backup stratum pool URL
                     Format: hostname:port, e.g. eu1.ethermine.org:4444

    --backup-wallet  Backup stratum pool wallet
                     e.g. 0xabcd1234abcd1234abcd1234abcd1234abcd1234

    --backup-ssl     Enable ssl connection on backup pool

    --worker-name    Custom name of current worker, default: default_worker

    --tlimit         Default is 0
                     Stop mining when GPU temperature is above

    --tresume        Default is 0
                     Resume mining when GPU temperature is below if GPU was overheated, Must be lower than --tlimit

    --devices        Default not set, e.g. --devices 0 2 3
                     If not set all available devices will be used

    --no-watchdog    Running QuantumMiner without launching watchdog process

    --list-device    Print available devices and exit

    --log            Enable writing console output to file

    --enable-dot     Enable DNS over TLS

    --proxy          SOCKS5 proxy, format: e.g. --proxy 127.0.0.1:10808

    --api            API server config, format: e.g. --api 127.0.0.1:22333
                     Default to 0.0.0.0:22333

    --no-hwstat      Disable printing hardware stat information

    --no-validation  Disable CPU validation before submitting share to pool
	
## API Reference

### Request

GET http://addr:port/api/status

### Response

``` json
{
    "connection":{
        "connected":true,
        "is_ssl":"no",
        "server":"eth-backup.f2pool.com:6688"
    },
    "miner":{
        "devices":[
            {
                "accepted":0,
                "hashrate":"0.00 h",
                "invalid":0,
                "name":"NVIDIA GeForce RTX 3060 Ti",
                "rejected":0
            },
            {
                "accepted":0,
                "hashrate":"0.00 h",
                "invalid":0,
                "name":"AMD Radeon RX 580 2048SP",
                "rejected":0
            }
        ],
        "total_accepted":0,
        "total_hashrate":"0.00 h",
        "total_invalid":0,
        "total_rejected":0
    },
    "version":"1.2"
}
```

## Change log

#### v1.3
- Added `blake3(ALPH)` algorithm, mining pools including herominers and woolypooly are tested

#### v1.2
- Added API server
- Minor bug fixes

#### v1.1
- Added Ubuntu build

#### v1.0
- Initial release

