# CSearchRegistryRedirectHelper::Initialize(unsigned __int64)

- ea: `0x14004edf8`
- end: `0x14004ee7d`
- name: `?Initialize@CSearchRegistryRedirectHelper@@QEAAJ_K@Z`
- size: `133`
- prototype: `__int64 __fastcall(CSearchRegistryRedirectHelper *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14004ed20`

## callees

- `0x140028044`
- `0x14004edf8`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x14004ee37`
- `ntdll!RtlGetPersistedStateLocation` at `0x14004ee37`
- `ntdll!RtlNtStatusToDosError` at `0x14004ee3f`
- `ntdll!RtlNtStatusToDosError` at `0x14004ee3f`

## string_xrefs

- `0x14004ee5d`: `onecoreuap\base\appmodel\search\common\utils\regredirect.cxx`

## pseudocode

```c

```
