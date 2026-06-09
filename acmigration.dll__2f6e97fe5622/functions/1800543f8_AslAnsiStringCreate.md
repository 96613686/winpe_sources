# AslAnsiStringCreate

- ea: `0x1800543f8`
- end: `0x180054497`
- name: `AslAnsiStringCreate`
- size: `159`
- prototype: `__int64 __fastcall(PANSI_STRING DestinationString)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800509d0`

## callees

- `0x1800543c0`
- `0x1800543f8`
- `0x180054b70`

## import_xrefs

- `ntdll!RtlInitAnsiString` at `0x180054465`
- `ntdll!RtlInitAnsiString` at `0x180054465`
- `ntdll!RtlFreeHeap` at `0x180054484`
- `ntdll!RtlFreeHeap` at `0x180054484`

## string_xrefs

- `0x180054440`: `AslAnsiStringCreate`

## pseudocode

```c

```
