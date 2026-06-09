# WerpReadPeb32FromProcess

- ea: `0x140030b3c`
- end: `0x140030cb1`
- name: `WerpReadPeb32FromProcess`
- size: `373`
- prototype: `__int64 __fastcall(HANDLE hProcess, LPVOID lpBuffer)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400308b8`

## callees

- `0x14000333f`
- `0x140003357`
- `0x140003387`
- `0x140030b3c`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x140030b82`
- `ntdll!NtQueryInformationProcess` at `0x140030b82`
- `ntdll!DbgPrintEx` at `0x140030bb6`
- `ntdll!DbgPrintEx` at `0x140030bf5`
- `ntdll!DbgPrintEx` at `0x140030c4e`
- `ntdll!DbgPrintEx` at `0x140030c8f`
- `ntdll!DbgPrintEx` at `0x140030bb6`
- `ntdll!DbgPrintEx` at `0x140030bf5`
- `ntdll!DbgPrintEx` at `0x140030c4e`
- `ntdll!DbgPrintEx` at `0x140030c8f`

## string_xrefs

- `0x140030c40`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read Peb32BaseAddress\n`

## pseudocode

```c

```
