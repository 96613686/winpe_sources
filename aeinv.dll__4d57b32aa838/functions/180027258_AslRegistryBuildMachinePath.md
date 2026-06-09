# AslRegistryBuildMachinePath

- ea: `0x180027258`
- end: `0x180027337`
- name: `AslRegistryBuildMachinePath`
- size: `223`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180027118`

## callees

- `0x1800197d4`
- `0x180027258`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x180027318`
- `ntdll!RtlAppendUnicodeToString` at `0x180027324`
- `ntdll!RtlAppendUnicodeToString` at `0x180027318`
- `ntdll!RtlAppendUnicodeToString` at `0x180027324`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800272fd`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800272fd`
- `ntdll!RtlAllocateHeap` at `0x1800272bc`
- `ntdll!RtlAllocateHeap` at `0x1800272bc`
- `ntdll!RtlInitUnicodeString` at `0x18002727b`
- `ntdll!RtlInitUnicodeString` at `0x18002727b`

## string_xrefs

- `0x18002726a`: `\Registry\Machine`
- `0x1800272e0`: `AslRegistryBuildMachinePath`

## pseudocode

```c

```
