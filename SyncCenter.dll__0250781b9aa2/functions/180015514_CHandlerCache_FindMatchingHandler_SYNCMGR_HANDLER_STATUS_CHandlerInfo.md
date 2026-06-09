# CHandlerCache::_FindMatchingHandler(SYNCMGR_HANDLER_STATUS,CHandlerInfo * *)

- ea: `0x180015514`
- end: `0x180015598`
- name: `?_FindMatchingHandler@CHandlerCache@@AEAAJW4SYNCMGR_HANDLER_STATUS@@PEAPEAVCHandlerInfo@@@Z`
- size: `132`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *, unsigned int, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180004a60`
- `0x180013fb8`
- `0x1800142c4`

## callees

- `0x180008abc`
- `0x180015514`
- `0x180016048`
- `0x1800160ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015583`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015583`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001552f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001552f`

## pseudocode

```c

```
