# web::http::client::details::winhttp_client::read_next_response_chunk(web::http::client::details::winhttp_request_context *,ulong,bool)

- ea: `0x18005e320`
- end: `0x18005e669`
- name: `?read_next_response_chunk@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@2345@K_N@Z`
- size: `841`
- prototype: `void __fastcall(struct web::http::client::details::winhttp_request_context *this, unsigned int, bool)`
- caller_count: `3`
- callee_count: `15`
- tags: ``

## callers

- `0x1800553f0`
- `0x180055e30`
- `0x1800592a0`

## callees

- `0x18000b820`
- `0x18000bccc`
- `0x18000bd0c`
- `0x18000c420`
- `0x18003d860`
- `0x18003de40`
- `0x18003df90`
- `0x18003f060`
- `0x180058d60`
- `0x18005e320`
- `0x1800658b0`
- `0x18013560c`
- `0x180150384`
- `0x180161cc4`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e373`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e536`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e373`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e536`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18005e365`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18005e365`
- `WINHTTP!WinHttpReadData` at `0x18005e528`
- `WINHTTP!WinHttpReadData` at `0x18005e528`

## string_xrefs

- `0x18005e552`: `WinHttpReadData`

## pseudocode

```c

```
