# AslRegistryGetString

- ea: `0x18002b99c`
- end: `0x18002bb5f`
- name: `AslRegistryGetString`
- size: `451`
- prototype: `__int64 __fastcall(_QWORD *, void *, const WCHAR *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001f2dc`
- `0x180069a0c`
- `0x18006c90c`
- `0x180119ec8`

## callees

- `0x1800197d4`
- `0x18001b0b8`
- `0x18002b99c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18002bb4d`
- `ntdll!RtlFreeHeap` at `0x18002bb4d`
- `ntdll!RtlAllocateHeap` at `0x18002ba5a`
- `ntdll!RtlAllocateHeap` at `0x18002ba5a`
- `ntdll!RtlInitUnicodeString` at `0x18002b9cb`
- `ntdll!RtlInitUnicodeString` at `0x18002b9cb`
- `ntdll!ZwQueryValueKey` at `0x18002b9f2`
- `ntdll!ZwQueryValueKey` at `0x18002bab1`
- `ntdll!ZwQueryValueKey` at `0x18002b9f2`
- `ntdll!ZwQueryValueKey` at `0x18002bab1`

## string_xrefs

- `0x18002ba24`: `AslRegistryGetString`
- `0x18002ba75`: `AslRegistryGetString`
- `0x18002bae3`: `AslRegistryGetString`
- `0x18002bb26`: `AslRegistryGetString`

## pseudocode

```c

```
