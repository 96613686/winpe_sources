# OSDeploymentHelper::CreateAndAcquireSandboxAccessMutex(_GUID const &,void * *,ulong)

- ea: `0x180052248`
- end: `0x1800523c7`
- name: `?CreateAndAcquireSandboxAccessMutex@OSDeploymentHelper@@YAJAEBU_GUID@@PEAPEAXK@Z`
- size: `383`
- prototype: `__int64 __fastcall(GUID *rguid, const wchar_t *, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003e3e8`
- `0x1800526f4`

## callees

- `0x180003180`
- `0x18000c640`
- `0x180052248`
- `0x1800523d0`
- `0x180052b14`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18005238e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18005238e`
- `RPCRT4!UuidToStringW` at `0x1800522e5`
- `RPCRT4!UuidToStringW` at `0x1800522e5`

## pseudocode

```c

```
