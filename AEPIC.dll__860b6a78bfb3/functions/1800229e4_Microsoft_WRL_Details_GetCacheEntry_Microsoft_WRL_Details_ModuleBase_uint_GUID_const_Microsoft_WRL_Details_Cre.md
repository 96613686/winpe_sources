# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x1800229e4`
- end: `0x180022b6b`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800226e0`

## callees

- `0x1800229e4`
- `0x180022f08`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022b1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022b1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180022a78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180022a8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180022a78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180022a8d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180022a36`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180022a36`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180022a48`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180022afd`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180022a48`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180022afd`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180022aee`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180022aee`

## pseudocode

```c

```
