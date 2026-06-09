# web::http::client::details::winhttp_request_context::on_send_request_validate_cn(void)

- ea: `0x18005cb10`
- end: `0x18005d109`
- name: `?on_send_request_validate_cn@winhttp_request_context@details@client@http@web@@QEAAXXZ`
- size: `1529`
- prototype: `void __fastcall(web::http::client::details::winhttp_request_context *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180059480`

## callees

- `0x18000b8f0`
- `0x18000bd9c`
- `0x18000bddc`
- `0x18003f210`
- `0x180058f40`
- `0x1800593e0`
- `0x18005cb10`
- `0x180063fa3`
- `0x18013241c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cb7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cda9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cb7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cda9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cede`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18005ced0`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18005ced0`
- `CRYPT32!CertFreeCertificateChain` at `0x18005d0c8`
- `CRYPT32!CertFreeCertificateChain` at `0x18005d0c8`
- `CRYPT32!CertGetCertificateChain` at `0x18005cd9b`
- `CRYPT32!CertGetCertificateChain` at `0x18005cd9b`
- `CRYPT32!CertFreeCertificateContext` at `0x18005d0db`
- `CRYPT32!CertFreeCertificateContext` at `0x18005d0db`
- `WINHTTP!WinHttpQueryOption` at `0x18005cb70`
- `WINHTTP!WinHttpQueryOption` at `0x18005cb70`

## string_xrefs

- `0x18005cfc7`: `Incorrect common name`

## pseudocode

```c

```
