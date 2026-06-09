# TileQueueManager::RemoveHashEntry<char const *>(WPN_APPDB_HASH_BUCKET *,char const *,uint,APPENTRY_LOCK_FLAGS,WPN_APPDB_APP_ENTRY * *)

- ea: `0x1800f8e78`
- end: `0x1800f8f89`
- name: `??$RemoveHashEntry@PEBD@TileQueueManager@@AEAAJPEAUWPN_APPDB_HASH_BUCKET@@PEBDIW4APPENTRY_LOCK_FLAGS@@PEAPEAUWPN_APPDB_APP_ENTRY@@@Z`
- size: `273`
- prototype: `__int64 __fastcall(__int64, RTL_SRWLOCK *, const char *, int, __int64, RTL_SRWLOCK **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800fe1c0`

## callees

- `0x18002ee38`
- `0x1800af0a4`
- `0x1800f8e78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f8efe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f8f78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f8efe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f8f78`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f8e8d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f8ef5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f8e8d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f8ef5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f8f04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f8f04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f8f12`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f8f12`

## pseudocode

```c

```
