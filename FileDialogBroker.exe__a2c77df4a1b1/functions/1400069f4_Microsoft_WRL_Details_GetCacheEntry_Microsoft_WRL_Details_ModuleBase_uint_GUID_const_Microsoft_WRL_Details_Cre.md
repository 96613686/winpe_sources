# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x1400069f4`
- end: `0x140006b7b`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140006038`

## callees

- `0x1400069f4`
- `0x140006c68`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140006a46`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140006a46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006b2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006b2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140006a88`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140006a9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140006a88`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140006a9d`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x140006afe`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x140006afe`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x140006a58`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x140006b0d`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x140006a58`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x140006b0d`

## pseudocode

```c

```
