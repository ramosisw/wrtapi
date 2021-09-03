# WrtApi
OpenWRT administration HTTP api written in go  (Golang MIPS/ARM/x86 cross compilation)
----

This project was created to be used for a mobile APP to display system info and network status. OpenWRT configuartion changes and other features could also be implemented with little effort.

* Golang net/http and [httprouter](https://github.com/julienschmidt/httprouter) is used for HTTP API
* HTTP API uses JSON data to comunicate with ubus [(OpenWrt micro bus architecture)](https://openwrt.org/docs/techref/ubus)


Implemented API endpoints:
| Method | Endpoint | Description  |
|------- | -------- | ------------ |
|`GET`   | / | <em>Test method</em> |
|`GET`   | /system | <em>Get System info</em> |
|`GET`   | /system/board | <em>add description</em> |
|`GET`   | /system/services | <em>add description</em> |
|`GET`   | /network | <em>add description</em> |
|`GET`   | /network/interfaces | <em>add description</em> |
|`GET`   | /network/interfaces/wan | <em>add description</em> |
|`GET`   | /network/interfaces/lan | <em>add description</em> |
|`GET`   | /wlan | <em>add description</em> |
|`GET`   | /wlan/clients | <em>add description</em> |


## Build

### mips
```powershell
$env:GOOS = "linux"; $env:GOARCH = "mipsle"; $env:GOMIPS = "softfloat"; go build -ldflags "-w" .
```

### amd64
```powershell
$env:GOOS = "linux"; $env:GOARCH = "amd64"; go build -ldflags "-w" .
```

### amd64 windows
```powershell
$env:GOOS = "windows"; $env:GOARCH = "amd64"; go build -ldflags "-w" .
```