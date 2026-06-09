# CRecentDocumentsFolder::DeleteSelectedMRU(void *)

- ea: `0x18052fe7c`
- end: `0x18053013a`
- name: `?DeleteSelectedMRU@CRecentDocumentsFolder@@QEAAJPEAX@Z`
- size: `702`
- prototype: `__int64 __fastcall(CRecentDocumentsFolder *__hidden this, HGLOBAL hMem)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x180530cf0`

## callees

- `0x18000d6cc`
- `0x1800aa710`
- `0x1800ab960`
- `0x18018ee78`
- `0x1801904ac`
- `0x1801905a4`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x18052fe7c`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1805300ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1805300ef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1805300ce`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1805300ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18052ffd8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18052ffd8`
- `ntdll!RtlGetLastNtStatus` at `0x18052ff77`
- `ntdll!RtlGetLastNtStatus` at `0x18052ffc0`
- `ntdll!RtlGetLastNtStatus` at `0x18052ff77`
- `ntdll!RtlGetLastNtStatus` at `0x18052ffc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1805300db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1805300db`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18052ffa9`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18052ffa9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18052ff90`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18052ff90`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18052ff6d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18052ffb8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18052ff6d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18052ffb8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18053003a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18053003a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18052fed3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18052fed3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1805300f8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1805300f8`
- `SHCORE!__imp_IsNotifySuspended` at `0x18052ffe2`
- `SHCORE!__imp_IsNotifySuspended` at `0x18052ffe2`

## pseudocode

```c

```
