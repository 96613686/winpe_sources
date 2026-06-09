# AslRegistryBuildMachinePath

- ea: `0x14003c388`
- end: `0x14003c467`
- name: `AslRegistryBuildMachinePath`
- size: `223`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14003c618`

## callees

- `0x14003bf18`
- `0x14003c388`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14003c3ab`
- `ntdll!RtlInitUnicodeString` at `0x14003c3ab`
- `ntdll!RtlAllocateHeap` at `0x14003c3ec`
- `ntdll!RtlAllocateHeap` at `0x14003c3ec`
- `ntdll!RtlAppendUnicodeToString` at `0x14003c448`
- `ntdll!RtlAppendUnicodeToString` at `0x14003c454`
- `ntdll!RtlAppendUnicodeToString` at `0x14003c448`
- `ntdll!RtlAppendUnicodeToString` at `0x14003c454`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14003c42d`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14003c42d`

## string_xrefs

- `0x14003c39a`: `\Registry\Machine`
- `0x14003c410`: `AslRegistryBuildMachinePath`

## pseudocode

```c

```
