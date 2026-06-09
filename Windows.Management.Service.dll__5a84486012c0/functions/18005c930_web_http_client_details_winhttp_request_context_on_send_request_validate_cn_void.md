# web::http::client::details::winhttp_request_context::on_send_request_validate_cn(void)

- ea: `0x18005c930`
- end: `0x18005cf29`
- name: `?on_send_request_validate_cn@winhttp_request_context@details@client@http@web@@QEAAXXZ`
- size: `1529`
- prototype: `void __fastcall(HINTERNET *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800592a0`

## callees

- `0x18000b820`
- `0x18000bccc`
- `0x18000bd0c`
- `0x18003f060`
- `0x180058d60`
- `0x180059200`
- `0x18005c930`
- `0x180063dc3`
- `0x18012e6d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c99e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cbc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ccfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c99e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cbc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ccfe`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18005ccf0`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18005ccf0`
- `CRYPT32!CertFreeCertificateChain` at `0x18005cee8`
- `CRYPT32!CertFreeCertificateChain` at `0x18005cee8`
- `CRYPT32!CertGetCertificateChain` at `0x18005cbbb`
- `CRYPT32!CertGetCertificateChain` at `0x18005cbbb`
- `CRYPT32!CertFreeCertificateContext` at `0x18005cefb`
- `CRYPT32!CertFreeCertificateContext` at `0x18005cefb`
- `WINHTTP!WinHttpQueryOption` at `0x18005c990`
- `WINHTTP!WinHttpQueryOption` at `0x18005c990`

## string_xrefs

- `0x18005cde7`: `Incorrect common name`

## pseudocode

```c

```
