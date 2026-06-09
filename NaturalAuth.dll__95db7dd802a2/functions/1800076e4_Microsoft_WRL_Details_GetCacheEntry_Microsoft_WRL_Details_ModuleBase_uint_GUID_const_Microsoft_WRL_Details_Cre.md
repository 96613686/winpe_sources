# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x1800076e4`
- end: `0x18000786b`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005e18`

## callees

- `0x1800076e4`
- `0x18000843c`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007736`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007736`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007778`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000778d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007778`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000778d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000781f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000781f`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800077ee`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800077ee`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180007748`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800077fd`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180007748`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800077fd`

## pseudocode

```c

```
