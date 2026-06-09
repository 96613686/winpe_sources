# AslRegistryBuildMachinePath

- ea: `0x18004c31c`
- end: `0x18004c3fb`
- name: `AslRegistryBuildMachinePath`
- size: `223`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18004c404`

## callees

- `0x18004c020`
- `0x18004c31c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18004c380`
- `ntdll!RtlAllocateHeap` at `0x18004c380`
- `ntdll!RtlAppendUnicodeToString` at `0x18004c3dc`
- `ntdll!RtlAppendUnicodeToString` at `0x18004c3e8`
- `ntdll!RtlAppendUnicodeToString` at `0x18004c3dc`
- `ntdll!RtlAppendUnicodeToString` at `0x18004c3e8`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18004c3c1`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18004c3c1`
- `ntdll!RtlInitUnicodeString` at `0x18004c33f`
- `ntdll!RtlInitUnicodeString` at `0x18004c33f`

## string_xrefs

- `0x18004c32e`: `\Registry\Machine`
- `0x18004c3a4`: `AslRegistryBuildMachinePath`

## pseudocode

```c

```
