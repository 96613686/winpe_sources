# DownloadTaskManager::ProcessJobError(WPN_DOWNLOAD_TASK *,_GUID *,IBackgroundCopyError *)

- ea: `0x1800c1a20`
- end: `0x1800c1d2d`
- name: `?ProcessJobError@DownloadTaskManager@@AEAAXPEAUWPN_DOWNLOAD_TASK@@PEAU_GUID@@PEAUIBackgroundCopyError@@@Z`
- size: `781`
- prototype: `void(DownloadTaskManager *__hidden this, struct WPN_DOWNLOAD_TASK *, struct _GUID *, struct IBackgroundCopyError *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x1800c0b20`

## callees

- `0x18002ee38`
- `0x1800778b4`
- `0x1800a0b2c`
- `0x1800af0a4`
- `0x1800b99f0`
- `0x1800ba574`
- `0x1800bc541`
- `0x1800c11b4`
- `0x1800c1a20`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c1b9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c1cfd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c1b9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c1cfd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c1b0f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c1b0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c1c46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c1c87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c1c46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c1c87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c1c54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c1c95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c1c54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c1c95`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c1c6c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c1c6c`

## string_xrefs

- `0x1800c1a8b`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c1caf`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`

## pseudocode

```c

```
