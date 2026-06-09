# AslRegistryBuildMachinePath

- ea: `0x1800297bc`
- end: `0x18002989b`
- name: `AslRegistryBuildMachinePath`
- size: `223`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800298a4`

## callees

- `0x1800295dc`
- `0x1800297bc`

## import_xrefs

- `ntdll!RtlAppendUnicodeStringToString` at `0x180029861`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180029861`
- `ntdll!RtlAppendUnicodeToString` at `0x18002987c`
- `ntdll!RtlAppendUnicodeToString` at `0x180029888`
- `ntdll!RtlAppendUnicodeToString` at `0x18002987c`
- `ntdll!RtlAppendUnicodeToString` at `0x180029888`
- `ntdll!RtlAllocateHeap` at `0x180029820`
- `ntdll!RtlAllocateHeap` at `0x180029820`
- `ntdll!RtlInitUnicodeString` at `0x1800297df`
- `ntdll!RtlInitUnicodeString` at `0x1800297df`

## string_xrefs

- `0x1800297ce`: `\Registry\Machine`
- `0x180029844`: `AslRegistryBuildMachinePath`

## pseudocode

```c

```
