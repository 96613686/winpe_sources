# WerpReadPeb32FromProcess

- ea: `0x14002ece8`
- end: `0x14002ee3e`
- name: `WerpReadPeb32FromProcess`
- size: `342`
- prototype: `__int64 __fastcall(HANDLE hProcess, LPVOID lpBuffer)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14002ea98`

## callees

- `0x1400032ef`
- `0x140003307`
- `0x140003337`
- `0x14002ece8`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x14002ed2e`
- `ntdll!NtQueryInformationProcess` at `0x14002ed2e`
- `ntdll!DbgPrintEx` at `0x14002ed5c`
- `ntdll!DbgPrintEx` at `0x14002ed95`
- `ntdll!DbgPrintEx` at `0x14002ede8`
- `ntdll!DbgPrintEx` at `0x14002ee23`
- `ntdll!DbgPrintEx` at `0x14002ed5c`
- `ntdll!DbgPrintEx` at `0x14002ed95`
- `ntdll!DbgPrintEx` at `0x14002ede8`
- `ntdll!DbgPrintEx` at `0x14002ee23`

## string_xrefs

- `0x14002edda`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read Peb32BaseAddress\n`

## pseudocode

```c

```
