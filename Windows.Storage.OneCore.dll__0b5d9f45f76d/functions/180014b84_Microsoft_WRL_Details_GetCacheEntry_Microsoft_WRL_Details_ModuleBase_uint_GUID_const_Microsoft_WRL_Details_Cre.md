# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180014b84`
- end: `0x180014d0b`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014830`

## callees

- `0x180014b84`
- `0x180014d88`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014c18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014c2d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014c18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014c2d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180014bd6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180014bd6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014cbf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014cbf`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180014be8`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180014c9d`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180014be8`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180014c9d`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180014c8e`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180014c8e`

## pseudocode

```c

```
