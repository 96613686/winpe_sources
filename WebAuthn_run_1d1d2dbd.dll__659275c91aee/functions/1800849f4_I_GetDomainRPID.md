# I_GetDomainRPID

- ea: `0x1800849f4`
- end: `0x180084b7a`
- name: `I_GetDomainRPID`
- size: `390`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180083e50`
- `0x180084b80`
- `0x18008631c`

## callees

- `0x18002bbf4`
- `0x180031708`
- `0x18005378c`
- `0x1800537a4`
- `0x18007969c`
- `0x1800849f4`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180084af3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180084af3`
- `WINHTTP!WinHttpCrackUrl` at `0x180084aab`
- `WINHTTP!WinHttpCrackUrl` at `0x180084aab`
- `dsreg!DsrGetJoinInfoEx` at `0x180084a43`
- `dsreg!DsrGetJoinInfoEx` at `0x180084a43`
- `dsreg!DsrFreeJoinInfoEx` at `0x180084b59`
- `dsreg!DsrFreeJoinInfoEx` at `0x180084b59`

## string_xrefs

- `0x180084ad2`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x180084b31`: `DsrGetJoinInfoNoAccessTokenUrl`

## pseudocode

```c

```
