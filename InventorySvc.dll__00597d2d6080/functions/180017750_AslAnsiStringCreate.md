# AslAnsiStringCreate

- ea: `0x180017750`
- end: `0x1800177ef`
- name: `AslAnsiStringCreate`
- size: `159`
- prototype: `__int64 __fastcall(PANSI_STRING DestinationString)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180014320`

## callees

- `0x1800152d0`
- `0x180017750`
- `0x180017d18`

## import_xrefs

- `ntdll!RtlInitAnsiString` at `0x1800177bd`
- `ntdll!RtlInitAnsiString` at `0x1800177bd`
- `ntdll!RtlFreeHeap` at `0x1800177dc`
- `ntdll!RtlFreeHeap` at `0x1800177dc`

## string_xrefs

- `0x180017798`: `AslAnsiStringCreate`

## pseudocode

```c

```
