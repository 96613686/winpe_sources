# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x18001f9f0`
- end: `0x18001fb77`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001eac8`

## callees

- `0x18001f9f0`
- `0x18001fd74`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fb2b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fb2b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001fa42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001fa42`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001fa84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001fa99`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001fa84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001fa99`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001fa54`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001fb09`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001fa54`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001fb09`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18001fafa`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18001fafa`

## pseudocode

```c

```
