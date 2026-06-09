# CFolderItemCache::_WorkerRegisterForUpdates(ushort const *,HWND__ *,SYNCMGR_UPDATE_VIEW_ID,_ITEMIDLIST_ABSOLUTE *)

- ea: `0x18004b32c`
- end: `0x18004b476`
- name: `?_WorkerRegisterForUpdates@CFolderItemCache@@AEAAJPEBGPEAUHWND__@@W4SYNCMGR_UPDATE_VIEW_ID@@PEAU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `330`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64, unsigned int, LPITEMIDLIST pidl)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18004b51c`

## callees

- `0x180008abc`
- `0x180049e90`
- `0x18004ae70`
- `0x18004b32c`
- `0x180051bfc`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x18004b45d`
- `SHELL32!__imp_ILFree` at `0x18004b45d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b3be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b42a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b3be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b42a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b35a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b407`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b35a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b407`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18004b38e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18004b38e`

## pseudocode

```c

```
