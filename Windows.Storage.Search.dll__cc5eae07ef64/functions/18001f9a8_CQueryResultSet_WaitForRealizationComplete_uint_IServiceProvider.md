# CQueryResultSet::_WaitForRealizationComplete(uint,IServiceProvider *)

- ea: `0x18001f9a8`
- end: `0x18001fc13`
- name: `?_WaitForRealizationComplete@CQueryResultSet@@AEAAJIPEAUIServiceProvider@@@Z`
- size: `619`
- prototype: `int(CQueryResultSet *__hidden this, unsigned int, struct IServiceProvider *)`
- caller_count: `4`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ec80`
- `0x18001f67c`
- `0x180020748`
- `0x1800b3738`

## callees

- `0x18001db40`
- `0x18001f9a8`
- `0x180042a50`
- `0x180042b90`
- `0x180044ae0`
- `0x18004d0f0`
- `0x1800563e0`
- `0x180060b70`
- `0x180063a68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fa06`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fab6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fbdd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fa06`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fab6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fbdd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fa50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fb07`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fbf2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fa50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fb07`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fbf2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f9ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f9ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fb10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fbc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fb10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fbc8`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001fa93`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001fa93`

## pseudocode

```c

```
