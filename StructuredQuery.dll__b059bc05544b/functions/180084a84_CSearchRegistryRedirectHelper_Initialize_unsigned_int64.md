# CSearchRegistryRedirectHelper::Initialize(unsigned __int64)

- ea: `0x180084a84`
- end: `0x180084b09`
- name: `?Initialize@CSearchRegistryRedirectHelper@@QEAAJ_K@Z`
- size: `133`
- prototype: `__int64 __fastcall(CSearchRegistryRedirectHelper *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180084990`

## callees

- `0x18002a220`
- `0x180084a84`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x180084ac3`
- `ntdll!RtlGetPersistedStateLocation` at `0x180084ac3`
- `ntdll!RtlNtStatusToDosError` at `0x180084acb`
- `ntdll!RtlNtStatusToDosError` at `0x180084acb`

## string_xrefs

- `0x180084ae9`: `onecoreuap\base\appmodel\search\common\utils\regredirect.cxx`

## pseudocode

```c

```
