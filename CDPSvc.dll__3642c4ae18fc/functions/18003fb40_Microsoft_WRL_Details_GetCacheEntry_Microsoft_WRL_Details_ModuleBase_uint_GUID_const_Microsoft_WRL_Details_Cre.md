# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x18003fb40`
- end: `0x18003fcc7`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003bf28`

## callees

- `0x18003fb40`
- `0x1800406c0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003fb92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003fb92`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003fbd4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003fbe9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003fbd4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003fbe9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003fc7b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003fc7b`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18003fc4a`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18003fc4a`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18003fba4`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18003fc59`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18003fba4`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18003fc59`

## pseudocode

```c

```
