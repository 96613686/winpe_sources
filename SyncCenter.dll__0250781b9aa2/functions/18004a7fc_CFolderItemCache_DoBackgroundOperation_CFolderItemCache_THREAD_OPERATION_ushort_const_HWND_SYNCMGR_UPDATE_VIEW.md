# CFolderItemCache::_DoBackgroundOperation(CFolderItemCache::THREAD_OPERATION,ushort const *,HWND__ *,SYNCMGR_UPDATE_VIEW_ID,_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x18004a7fc`
- end: `0x18004a90c`
- name: `?_DoBackgroundOperation@CFolderItemCache@@AEAAJW4THREAD_OPERATION@1@PEBGPEAUHWND__@@W4SYNCMGR_UPDATE_VIEW_ID@@PEBU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(__int64, int, const unsigned __int16 *, __int64, int, struct _ITEMIDLIST_RELATIVE *)`
- caller_count: `4`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1800499d0`
- `0x180049fa0`
- `0x18004a030`
- `0x18004a290`

## callees

- `0x180005660`
- `0x180005f90`
- `0x180009940`
- `0x18000a5e4`
- `0x18003f00c`
- `0x18004a7fc`
- `0x18004a914`
- `0x18005292a`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x18004a8e3`
- `SHELL32!__imp_ILFree` at `0x18004a8e3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004a8d3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004a8d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a8f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a8f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a8b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a8b1`

## pseudocode

```c

```
