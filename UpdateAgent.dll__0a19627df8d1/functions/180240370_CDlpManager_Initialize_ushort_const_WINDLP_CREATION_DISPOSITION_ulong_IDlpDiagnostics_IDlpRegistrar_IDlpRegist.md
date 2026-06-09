# CDlpManager::Initialize(ushort const *,WINDLP_CREATION_DISPOSITION,ulong,IDlpDiagnostics *,IDlpRegistrar *,IDlpRegistrar *)

- ea: `0x180240370`
- end: `0x180240f69`
- name: `?Initialize@CDlpManager@@UEAAJPEBGW4WINDLP_CREATION_DISPOSITION@@KPEAVIDlpDiagnostics@@PEAVIDlpRegistrar@@3@Z`
- size: `3065`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x180039f90`
- `0x18006968c`
- `0x180077664`
- `0x18022e8ec`
- `0x18022eab0`
- `0x180231644`
- `0x180233cf0`
- `0x18023af54`
- `0x180240370`
- `0x180240f70`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180240796`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180240796`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802403e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180240c89`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802403e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180240c89`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802403bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180240be5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802403bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180240be5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802408e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180240f23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802408e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180240f23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802408f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180240f37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802408f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180240f37`

## string_xrefs

- `0x180240862`: `Create`
- `0x1802408b1`: `DlpMgrInit: WorkingPath = [%s], Disposition = [%s], Flags = [0x%X], Diagnostics = [%s], StockRegistrar = [%s], UserRegistrar = [%s]`

## pseudocode

```c

```
