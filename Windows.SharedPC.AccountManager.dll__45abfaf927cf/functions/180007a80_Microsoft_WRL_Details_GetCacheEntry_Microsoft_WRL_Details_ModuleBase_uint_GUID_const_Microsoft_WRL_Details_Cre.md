# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180007a80`
- end: `0x180007c07`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005ec8`

## callees

- `0x180007a80`
- `0x1800082f4`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007b14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007b29`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007b14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007b29`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007ad2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007ad2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007bbb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007bbb`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180007ae4`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180007b99`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180007ae4`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180007b99`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180007b8a`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180007b8a`

## pseudocode

```c

```
