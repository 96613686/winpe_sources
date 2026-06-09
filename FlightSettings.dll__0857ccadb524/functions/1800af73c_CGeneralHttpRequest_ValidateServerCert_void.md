# CGeneralHttpRequest::ValidateServerCert(void *)

- ea: `0x1800af73c`
- end: `0x1800af8da`
- name: `?ValidateServerCert@CGeneralHttpRequest@@CAJPEAX@Z`
- size: `414`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800af8e0`

## callees

- `0x18000cc8c`
- `0x180013da0`
- `0x1800177bc`
- `0x18001b2c0`
- `0x1800add54`
- `0x1800add74`
- `0x1800ae284`
- `0x1800af73c`

## import_xrefs

- `CRYPT32!CertGetCertificateChain` at `0x1800af7f1`
- `CRYPT32!CertGetCertificateChain` at `0x1800af7f1`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1800af848`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1800af848`
- `WINHTTP!WinHttpQueryOption` at `0x1800af76a`
- `WINHTTP!WinHttpQueryOption` at `0x1800af76a`

## string_xrefs

- `0x1800af787`: `onecore\base\flighting\flightsettings\broker\libs\common\generalhttprequest.cpp`
- `0x1800af8a9`: `onecore\base\flighting\flightsettings\broker\libs\common\generalhttprequest.cpp`

## pseudocode

```c

```
