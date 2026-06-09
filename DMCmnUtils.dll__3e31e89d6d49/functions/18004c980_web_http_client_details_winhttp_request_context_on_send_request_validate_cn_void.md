# web::http::client::details::winhttp_request_context::on_send_request_validate_cn(void)

- ea: `0x18004c980`
- end: `0x18004cf79`
- name: `?on_send_request_validate_cn@winhttp_request_context@details@client@http@web@@QEAAXXZ`
- size: `1529`
- prototype: `void __fastcall(web::http::client::details::winhttp_request_context *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800492f0`

## callees

- `0x180007270`
- `0x180007640`
- `0x18002b430`
- `0x180048db0`
- `0x180049250`
- `0x18004c980`
- `0x180051d48`
- `0x1800522c6`
- `0x180097e08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c9ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cc19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cd4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c9ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cc19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cd4e`
- `CRYPT32!CertFreeCertificateContext` at `0x18004cf4b`
- `CRYPT32!CertFreeCertificateContext` at `0x18004cf4b`
- `CRYPT32!CertGetCertificateChain` at `0x18004cc0b`
- `CRYPT32!CertGetCertificateChain` at `0x18004cc0b`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18004cd40`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18004cd40`
- `CRYPT32!CertFreeCertificateChain` at `0x18004cf38`
- `CRYPT32!CertFreeCertificateChain` at `0x18004cf38`
- `WINHTTP!WinHttpQueryOption` at `0x18004c9e0`
- `WINHTTP!WinHttpQueryOption` at `0x18004c9e0`

## string_xrefs

- `0x18004ce37`: `Incorrect common name`

## pseudocode

```c

```
