# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x18000916c`
- end: `0x1800092da`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `366`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PVOID Ptr, struct IUnknown **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800075d8`
- `0x180007750`

## callees

- `0x18000916c`
- `0x180009784`
- `0x180009808`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009297`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009297`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800091f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000920d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800091f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000920d`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180009267`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180009267`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800091cb`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009276`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800091cb`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009276`

## pseudocode

```c

```
