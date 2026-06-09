# DownloadTaskManager::ProcessJobSuccess(WPN_DOWNLOAD_TASK *,_GUID *,IBackgroundCopyJob *)

- ea: `0x1800c1d34`
- end: `0x1800c20f5`
- name: `?ProcessJobSuccess@DownloadTaskManager@@AEAAHPEAUWPN_DOWNLOAD_TASK@@PEAU_GUID@@PEAUIBackgroundCopyJob@@@Z`
- size: `961`
- prototype: `int(DownloadTaskManager *__hidden this, struct WPN_DOWNLOAD_TASK *, struct _GUID *, struct IBackgroundCopyJob *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x180087410`

## callees

- `0x18002ee38`
- `0x1800778b4`
- `0x1800a0b2c`
- `0x1800af0a4`
- `0x1800b99f0`
- `0x1800ba574`
- `0x1800bc541`
- `0x1800c17f8`
- `0x1800c1d34`
- `0x1800c2f40`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c1eb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c20c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c1eb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c20c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c1e22`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c1e22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c2004`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c204a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c2004`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c204a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c2012`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c2058`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c2012`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c2058`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c202b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c202b`

## string_xrefs

- `0x1800c1da1`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c1fa8`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c2072`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`

## pseudocode

```c

```
