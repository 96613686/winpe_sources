# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180007a84`
- end: `0x180007c0b`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007620`

## callees

- `0x180007a84`
- `0x180007c88`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180007b8e`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180007b8e`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180007ae8`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180007b9d`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180007ae8`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180007b9d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007ad6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007ad6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007bbf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007bbf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007b18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007b2d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007b18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007b2d`

## pseudocode

```c

```
