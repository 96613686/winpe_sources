# VmMigrationTcpTransport::FindUnusedBuffer(VmMigrationTcpTransport::_TRANSPORT_BUFFER * *,ulong)

- ea: `0x14012dc3c`
- end: `0x14012dd6e`
- name: `?FindUnusedBuffer@VmMigrationTcpTransport@@IEAAJPEAPEAU_TRANSPORT_BUFFER@1@K@Z`
- size: `306`
- prototype: `__int64 __fastcall(VmMigrationTcpTransport *__hidden this, struct VmMigrationTcpTransport::_TRANSPORT_BUFFER **, DWORD dwMilliseconds)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14012d718`
- `0x14012d820`
- `0x1401decf0`

## callees

- `0x14006af38`
- `0x140095d6c`
- `0x14009d7ac`
- `0x14009f9ec`
- `0x14012dc3c`
- `0x140132940`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14012dc88`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14012dc88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14012dcc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14012dcc9`

## string_xrefs

- `0x14012dcb8`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14012dcdd`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14012dcf9`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14012dd1e`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14012dd42`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`

## pseudocode

```c

```
