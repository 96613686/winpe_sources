# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x18003f764`
- end: `0x18003f8ea`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PVOID Ptr, struct IUnknown **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003f670`

## callees

- `0x18003f764`
- `0x18009d010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockShared` at `0x18003f7f5`
- `KERNEL32!ReleaseSRWLockShared` at `0x18003f80a`
- `KERNEL32!ReleaseSRWLockShared` at `0x18003f7f5`
- `KERNEL32!ReleaseSRWLockShared` at `0x18003f80a`
- `KERNEL32!EncodePointer` at `0x18003f86c`
- `KERNEL32!EncodePointer` at `0x18003f86c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18003f89b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18003f89b`
- `KERNEL32!DecodePointer` at `0x18003f7c6`
- `KERNEL32!DecodePointer` at `0x18003f87b`
- `KERNEL32!DecodePointer` at `0x18003f7c6`
- `KERNEL32!DecodePointer` at `0x18003f87b`
- `KERNEL32!AcquireSRWLockShared` at `0x18003f7b4`
- `KERNEL32!AcquireSRWLockShared` at `0x18003f7b4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18003f850`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18003f850`

## pseudocode

```c

```
