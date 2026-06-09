# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180009258`
- end: `0x1800093df`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800061e8`

## callees

- `0x180009258`
- `0x18000a0c8`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800092ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009301`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800092ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009301`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009393`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009393`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800092aa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800092aa`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800092bc`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009371`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800092bc`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009371`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180009362`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180009362`

## pseudocode

```c

```
