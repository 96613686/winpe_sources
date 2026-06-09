# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x18000c308`
- end: `0x18000c48f`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009d28`

## callees

- `0x18000c308`
- `0x18000d124`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c443`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c443`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c39c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c3b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c39c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c3b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000c35a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000c35a`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000c412`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000c412`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000c36c`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000c421`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000c36c`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000c421`

## pseudocode

```c

```
