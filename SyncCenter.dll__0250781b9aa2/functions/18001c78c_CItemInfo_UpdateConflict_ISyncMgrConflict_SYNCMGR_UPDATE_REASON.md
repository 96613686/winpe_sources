# CItemInfo::UpdateConflict(ISyncMgrConflict *,SYNCMGR_UPDATE_REASON)

- ea: `0x18001c78c`
- end: `0x18001c844`
- name: `?UpdateConflict@CItemInfo@@QEAAJPEAUISyncMgrConflict@@W4SYNCMGR_UPDATE_REASON@@@Z`
- size: `184`
- prototype: `__int64 __fastcall(CItemInfo *__hidden this, struct ISyncMgrConflict *, enum SYNCMGR_UPDATE_REASON)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001522c`

## callees

- `0x18001bb48`
- `0x18001c090`
- `0x18001c78c`
- `0x180033790`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x18001c828`
- `SHELL32!SHChangeNotify` at `0x18001c828`
- `SHELL32!__imp_ILFree` at `0x18001c833`
- `SHELL32!__imp_ILFree` at `0x18001c833`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c7f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c7f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c7a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c7a4`

## pseudocode

```c

```
