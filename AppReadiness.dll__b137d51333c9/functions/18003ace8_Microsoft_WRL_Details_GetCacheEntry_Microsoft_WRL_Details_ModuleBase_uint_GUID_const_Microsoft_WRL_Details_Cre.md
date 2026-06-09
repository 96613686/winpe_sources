# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x18003ace8`
- end: `0x18003ae6b`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `387`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock, struct IUnknown **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800407b8`

## callees

- `0x1800148b0`
- `0x18001a8c0`
- `0x18003ace8`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ae22`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ae22`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003ad7e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003ad94`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003ad7e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003ad94`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18003adf2`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18003adf2`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18003ad4e`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18003ae01`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18003ad4e`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18003ae01`

## pseudocode

```c

```
