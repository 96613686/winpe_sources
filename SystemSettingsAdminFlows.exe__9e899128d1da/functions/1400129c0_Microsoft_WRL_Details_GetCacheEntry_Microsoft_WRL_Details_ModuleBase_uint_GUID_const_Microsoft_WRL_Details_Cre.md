# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x1400129c0`
- end: `0x140012b47`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000a0f0`

## callees

- `0x1400129c0`
- `0x14001a89c`
- `0x14007d010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockShared` at `0x140012a54`
- `KERNEL32!ReleaseSRWLockShared` at `0x140012a69`
- `KERNEL32!ReleaseSRWLockShared` at `0x140012a54`
- `KERNEL32!ReleaseSRWLockShared` at `0x140012a69`
- `KERNEL32!AcquireSRWLockShared` at `0x140012a12`
- `KERNEL32!AcquireSRWLockShared` at `0x140012a12`
- `KERNEL32!DecodePointer` at `0x140012a24`
- `KERNEL32!DecodePointer` at `0x140012ad9`
- `KERNEL32!DecodePointer` at `0x140012a24`
- `KERNEL32!DecodePointer` at `0x140012ad9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140012afb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140012afb`
- `KERNEL32!EncodePointer` at `0x140012aca`
- `KERNEL32!EncodePointer` at `0x140012aca`

## pseudocode

```c

```
