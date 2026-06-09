# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x18000c4ec`
- end: `0x18000c66f`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `387`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock, struct IUnknown **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005ce0`
- `0x180005e60`

## callees

- `0x18000b360`
- `0x18000b390`
- `0x18000c4ec`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c626`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c626`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c582`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c598`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c582`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c598`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000c5f6`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000c5f6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000c552`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000c605`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000c552`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000c605`

## pseudocode

```c

```
