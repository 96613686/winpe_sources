# LoadLibraryA

- ea: `0x1800e7d50`
- end: `0x1800e7e10`
- name: `LoadLibraryA`
- size: `192`
- prototype: `HMODULE __stdcall(LPCSTR lpLibFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800e7d50`

## callees

- `0x1800134a0`
- `0x1800145c0`
- `0x1800e7d50`
- `0x180101e90`
- `0x180197010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800e7dd2`
- `ntdll!RtlFreeUnicodeString` at `0x1800e7dd2`
- `ntdll!RtlSetLastWin32Error` at `0x1800e7e04`
- `ntdll!RtlSetLastWin32Error` at `0x1800e7e04`
- `ntdll!RtlInitAnsiStringEx` at `0x1800e7d94`
- `ntdll!RtlInitAnsiStringEx` at `0x1800e7d94`
- `ntdll!RtlFreeHeap` at `0x18019468d`
- `ntdll!RtlFreeHeap` at `0x1801946ad`
- `ntdll!RtlFreeHeap` at `0x18019468d`
- `ntdll!RtlFreeHeap` at `0x1801946ad`
- `ntdll!_stricmp` at `0x1800e7d6e`
- `ntdll!_stricmp` at `0x1800e7d6e`
- `ntdll!strncat_s` at `0x180194665`
- `ntdll!strncat_s` at `0x180194665`
- `ntdll!RtlAllocateHeap` at `0x18019462d`
- `ntdll!RtlAllocateHeap` at `0x18019462d`

## string_xrefs

- `0x1800e7d67`: `twain_32.dll`
- `0x180194659`: `\twain_32.dll`

## pseudocode

```c

```
