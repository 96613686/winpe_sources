# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x1800ef130`
- end: `0x1800ef2b7`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800ed4b8`

## callees

- `0x1800ef130`
- `0x1800f0904`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800ef1c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800ef1d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800ef1c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800ef1d9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800ef182`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800ef182`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ef26b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ef26b`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800ef194`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800ef249`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800ef194`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800ef249`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800ef23a`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800ef23a`

## pseudocode

```c

```
