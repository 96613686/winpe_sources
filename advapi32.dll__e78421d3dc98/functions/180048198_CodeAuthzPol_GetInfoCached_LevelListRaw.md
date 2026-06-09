# CodeAuthzPol_GetInfoCached_LevelListRaw

- ea: `0x180048198`
- end: `0x1800482c7`
- name: `CodeAuthzPol_GetInfoCached_LevelListRaw`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000f164`

## callees

- `0x18000cb10`
- `0x180048198`

## import_xrefs

- `ntdll!RtlIsGenericTableEmpty` at `0x180048219`
- `ntdll!RtlIsGenericTableEmpty` at `0x180048219`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x18004824a`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x180048289`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x18004824a`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x180048289`
- `ntdll!RtlLeaveCriticalSection` at `0x1800482b4`
- `ntdll!RtlLeaveCriticalSection` at `0x1800482b4`
- `ntdll!RtlEnterCriticalSection` at `0x1800481d0`
- `ntdll!RtlEnterCriticalSection` at `0x1800481d0`

## pseudocode

```c

```
