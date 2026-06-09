# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180009f84`
- end: `0x18000a10b`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock, struct IUnknown **)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004aa8`
- `0x180004c28`

## callees

- `0x180009f84`
- `0x18000b794`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009fd6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009fd6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a0bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a0bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000a018`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000a02d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000a018`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000a02d`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009fe8`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000a09d`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009fe8`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000a09d`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000a08e`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000a08e`

## pseudocode

```c

```
