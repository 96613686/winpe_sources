# VmMigrationTcpTransport::FlushPendingReceives(ulong)

- ea: `0x140097c04`
- end: `0x140097d70`
- name: `?FlushPendingReceives@VmMigrationTcpTransport@@IEAAJK@Z`
- size: `364`
- prototype: `__int64 __fastcall(VmMigrationTcpTransport *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140097680`
- `0x1401df640`

## callees

- `0x14004bbcc`
- `0x140097c04`
- `0x14009d7ac`
- `0x1400d8488`
- `0x140132940`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140097cc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140097cc2`
- `WS2_32!WSAGetOverlappedResult` at `0x140097cb2`
- `WS2_32!WSAGetOverlappedResult` at `0x140097cb2`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x140097ce0`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x140097ce0`

## string_xrefs

- `0x140097d25`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`

## pseudocode

```c

```
