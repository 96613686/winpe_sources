# AslAnsiStringCreate

- ea: `0x180029f70`
- end: `0x18002a00f`
- name: `AslAnsiStringCreate`
- size: `159`
- prototype: `__int64 __fastcall(PANSI_STRING DestinationString)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180050550`

## callees

- `0x1800197d4`
- `0x180029f70`
- `0x18002a018`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180029ffc`
- `ntdll!RtlFreeHeap` at `0x180029ffc`
- `ntdll!RtlInitAnsiString` at `0x180029fdd`
- `ntdll!RtlInitAnsiString` at `0x180029fdd`

## string_xrefs

- `0x180029fb8`: `AslAnsiStringCreate`

## pseudocode

```c

```
