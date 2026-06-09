# TileQueueManager::CreateHashEntry<char const *>(WPN_APPDB_HASH_BUCKET *,char const *,uint,APPENTRY_LOCK_FLAGS,WPN_APPDB_APP_ENTRY *)

- ea: `0x1800f8b80`
- end: `0x1800f8d2e`
- name: `??$CreateHashEntry@PEBD@TileQueueManager@@AEAAJPEAUWPN_APPDB_HASH_BUCKET@@PEBDIW4APPENTRY_LOCK_FLAGS@@PEAUWPN_APPDB_APP_ENTRY@@@Z`
- size: `430`
- prototype: `__int64 __fastcall(__int64, RTL_SRWLOCK *, const char *, int, char, RTL_SRWLOCK *SRWLock)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800fa2b0`

## callees

- `0x18002ee38`
- `0x1800af0a4`
- `0x1800f8b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f8cac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f8d1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f8cac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f8d1d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800f8d02`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800f8d02`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f8c12`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f8d14`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f8c12`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f8d14`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f8ba4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f8ba4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f8b92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f8cb2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f8b92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f8cb2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f8cc0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f8cc0`

## pseudocode

```c

```
