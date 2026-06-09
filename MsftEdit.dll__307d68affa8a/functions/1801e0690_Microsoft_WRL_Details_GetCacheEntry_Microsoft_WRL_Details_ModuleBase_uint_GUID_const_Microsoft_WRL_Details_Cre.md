# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x1801e0690`
- end: `0x1801e0817`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1801df718`

## callees

- `0x1801e0690`
- `0x1801e193c`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1801e06e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1801e06e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801e0724`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801e0739`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801e0724`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801e0739`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801e07cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801e07cb`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1801e079a`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1801e079a`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1801e06f4`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1801e07a9`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1801e06f4`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1801e07a9`

## pseudocode

```c

```
