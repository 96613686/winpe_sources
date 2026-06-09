# AslRegistryBuildMachinePath

- ea: `0x180016aa8`
- end: `0x180016b87`
- name: `AslRegistryBuildMachinePath`
- size: `223`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180016910`

## callees

- `0x18000f114`
- `0x180016aa8`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180016acb`
- `ntdll!RtlInitUnicodeString` at `0x180016acb`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180016b56`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180016b56`
- `ntdll!RtlAppendUnicodeToString` at `0x180016b71`
- `ntdll!RtlAppendUnicodeToString` at `0x180016b7d`
- `ntdll!RtlAppendUnicodeToString` at `0x180016b71`
- `ntdll!RtlAppendUnicodeToString` at `0x180016b7d`
- `ntdll!RtlAllocateHeap` at `0x180016b0c`
- `ntdll!RtlAllocateHeap` at `0x180016b0c`

## string_xrefs

- `0x180016aba`: `\Registry\Machine`
- `0x180016b30`: `AslRegistryBuildMachinePath`

## pseudocode

```c

```
