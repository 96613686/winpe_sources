# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180296d50`
- end: `0x180296ed7`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180296be0`

## callees

- `0x180296d50`
- `0x180296f00`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180296de4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180296df9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180296de4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180296df9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180296e8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180296e8b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180296da2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180296da2`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180296db4`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180296e69`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180296db4`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180296e69`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180296e5a`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180296e5a`

## pseudocode

```c

```
