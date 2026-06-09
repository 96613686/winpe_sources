# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x14000b3c4`
- end: `0x14000b54b`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140005c28`

## callees

- `0x14000b3c4`
- `0x14000c8d0`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000b458`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000b46d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000b458`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000b46d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000b416`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000b416`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b4ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b4ff`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x14000b428`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x14000b4dd`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x14000b428`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x14000b4dd`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000b4ce`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x14000b4ce`

## pseudocode

```c

```
