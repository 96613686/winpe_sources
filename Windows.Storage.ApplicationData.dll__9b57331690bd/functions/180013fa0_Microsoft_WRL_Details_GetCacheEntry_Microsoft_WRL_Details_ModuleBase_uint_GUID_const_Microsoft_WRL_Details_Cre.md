# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180013fa0`
- end: `0x18001413c`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `412`
- prototype: `HRESULT __fastcall(Microsoft::WRL::Details::ModuleBase *modulePtr, unsigned int *flags, const _GUID *riid, const Microsoft::WRL::Details::CreatorMap *entry, IUnknown **ppFactory)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180026d3c`

## callees

- `0x180013fa0`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800140a4`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800140a4`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180014005`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001411f`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180014005`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001411f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180013fef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180013fef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014034`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800140e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014034`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800140e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800140b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800140b9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014083`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014083`

## pseudocode

```c

```
