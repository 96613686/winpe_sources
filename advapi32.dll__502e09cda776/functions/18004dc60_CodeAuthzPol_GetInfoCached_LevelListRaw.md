# CodeAuthzPol_GetInfoCached_LevelListRaw

- ea: `0x18004dc60`
- end: `0x18004ddae`
- name: `CodeAuthzPol_GetInfoCached_LevelListRaw`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180014c6c`

## callees

- `0x180012300`
- `0x18004dc60`

## import_xrefs

- `ntdll!RtlIsGenericTableEmpty` at `0x18004dce7`
- `ntdll!RtlIsGenericTableEmpty` at `0x18004dce7`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x18004dd1e`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x18004dd63`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x18004dd1e`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x18004dd63`
- `ntdll!RtlLeaveCriticalSection` at `0x18004dd94`
- `ntdll!RtlLeaveCriticalSection` at `0x18004dd94`
- `ntdll!RtlEnterCriticalSection` at `0x18004dc98`
- `ntdll!RtlEnterCriticalSection` at `0x18004dc98`

## pseudocode

```c

```
