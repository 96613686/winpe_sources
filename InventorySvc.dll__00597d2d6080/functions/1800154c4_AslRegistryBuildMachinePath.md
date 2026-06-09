# AslRegistryBuildMachinePath

- ea: `0x1800154c4`
- end: `0x1800155a3`
- name: `AslRegistryBuildMachinePath`
- size: `223`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800155ac`

## callees

- `0x1800152d0`
- `0x1800154c4`

## import_xrefs

- `ntdll!RtlAppendUnicodeStringToString` at `0x180015569`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180015569`
- `ntdll!RtlAppendUnicodeToString` at `0x180015584`
- `ntdll!RtlAppendUnicodeToString` at `0x180015590`
- `ntdll!RtlAppendUnicodeToString` at `0x180015584`
- `ntdll!RtlAppendUnicodeToString` at `0x180015590`
- `ntdll!RtlAllocateHeap` at `0x180015528`
- `ntdll!RtlAllocateHeap` at `0x180015528`
- `ntdll!RtlInitUnicodeString` at `0x1800154e7`
- `ntdll!RtlInitUnicodeString` at `0x1800154e7`

## string_xrefs

- `0x1800154d6`: `\Registry\Machine`
- `0x18001554c`: `AslRegistryBuildMachinePath`

## pseudocode

```c

```
