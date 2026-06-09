# CacheGetRecordHeader(CacheBuffer *,_LARGE_INTEGER,_LOCK_BOX_RECORD_HEADER *,unsigned __int64)

- ea: `0x140058734`
- end: `0x140058808`
- name: `?CacheGetRecordHeader@@YAJPEAVCacheBuffer@@T_LARGE_INTEGER@@PEAU_LOCK_BOX_RECORD_HEADER@@_K@Z`
- size: `212`
- prototype: `__int64 __fastcall(struct CacheBuffer *this, union _LARGE_INTEGER, struct _LOCK_BOX_RECORD_HEADER *, size_t)`
- caller_count: `5`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000e9e0`
- `0x1400115c0`
- `0x140011f50`
- `0x140063840`
- `0x140063f10`

## callees

- `0x14000a420`
- `0x14001cb78`
- `0x1400584a0`
- `0x140058624`
- `0x140058734`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140058798`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400587f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140058798`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400587f0`

## string_xrefs

- `0x14005877a`: `onecore\ds\security\biometrics\service\trustlet\exe\cachestoragehelpers.cpp`

## pseudocode

```c

```
