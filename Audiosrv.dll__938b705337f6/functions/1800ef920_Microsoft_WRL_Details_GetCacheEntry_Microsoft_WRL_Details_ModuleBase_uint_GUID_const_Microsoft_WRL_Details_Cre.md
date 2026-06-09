# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x1800ef920`
- end: `0x1800efaa7`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800edcbc`

## callees

- `0x1800ef920`
- `0x1800f10f4`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800ef9b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800ef9c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800ef9b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800ef9c9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800ef972`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800ef972`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800efa5b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800efa5b`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800ef984`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800efa39`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800ef984`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800efa39`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800efa2a`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800efa2a`

## pseudocode

```c

```
