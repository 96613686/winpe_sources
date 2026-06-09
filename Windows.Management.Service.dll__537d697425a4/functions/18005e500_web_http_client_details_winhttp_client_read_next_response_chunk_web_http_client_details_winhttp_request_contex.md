# web::http::client::details::winhttp_client::read_next_response_chunk(web::http::client::details::winhttp_request_context *,ulong,bool)

- ea: `0x18005e500`
- end: `0x18005e849`
- name: `?read_next_response_chunk@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@2345@K_N@Z`
- size: `841`
- prototype: `void __fastcall(struct web::http::client::details::winhttp_request_context *this, unsigned int, bool)`
- caller_count: `3`
- callee_count: `15`
- tags: ``

## callers

- `0x1800555a0`
- `0x180055fe0`
- `0x180059480`

## callees

- `0x18000b8f0`
- `0x18000bd9c`
- `0x18000bddc`
- `0x18000c510`
- `0x18003da10`
- `0x18003dff0`
- `0x18003e140`
- `0x18003f210`
- `0x180058f40`
- `0x18005e500`
- `0x180065aec`
- `0x180139510`
- `0x1801543d4`
- `0x18016609c`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e553`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e716`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e553`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e716`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18005e545`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18005e545`
- `WINHTTP!WinHttpReadData` at `0x18005e708`
- `WINHTTP!WinHttpReadData` at `0x18005e708`

## string_xrefs

- `0x18005e732`: `WinHttpReadData`

## pseudocode

```c

```
