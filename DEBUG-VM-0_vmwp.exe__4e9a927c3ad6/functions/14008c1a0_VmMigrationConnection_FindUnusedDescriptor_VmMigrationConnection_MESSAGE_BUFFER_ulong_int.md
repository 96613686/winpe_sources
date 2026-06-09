# VmMigrationConnection::FindUnusedDescriptor(VmMigrationConnection::_MESSAGE_BUFFER * *,ulong,int)

- ea: `0x14008c1a0`
- end: `0x14008c364`
- name: `?FindUnusedDescriptor@VmMigrationConnection@@IEAAJPEAPEAU_MESSAGE_BUFFER@1@KH@Z`
- size: `452`
- prototype: `int(VmMigrationConnection *__hidden this, struct VmMigrationConnection::_MESSAGE_BUFFER **, unsigned int, int)`
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140088f38`
- `0x14008b7b0`
- `0x14008bb10`
- `0x14008c630`
- `0x1400fd4e0`

## callees

- `0x140042240`
- `0x1400549dc`
- `0x14006af38`
- `0x14008c1a0`
- `0x14009d7ac`
- `0x140132940`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14008c1ee`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14008c1ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008c233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008c233`

## string_xrefs

- `0x14008c222`: `onecore\vm\common\migration\vmmigrationconnection.cpp`
- `0x14008c247`: `onecore\vm\common\migration\vmmigrationconnection.cpp`
- `0x14008c263`: `onecore\vm\common\migration\vmmigrationconnection.cpp`
- `0x14008c27f`: `onecore\vm\common\migration\vmmigrationconnection.cpp`
- `0x14008c327`: `onecore\vm\common\migration\vmmigrationconnection.cpp`

## pseudocode

```c

```
