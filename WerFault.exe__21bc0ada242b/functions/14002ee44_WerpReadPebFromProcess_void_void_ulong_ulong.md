# WerpReadPebFromProcess(void *,void *,ulong,ulong)

- ea: `0x14002ee44`
- end: `0x14002ef8f`
- name: `?WerpReadPebFromProcess@@YAJPEAX0KK@Z`
- size: `331`
- prototype: `signed int __fastcall(HANDLE hProcess, void *lpBuffer)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14002ea98`

## callees

- `0x1400032ef`
- `0x140003307`
- `0x140003337`
- `0x14002ee44`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x14002ee8b`
- `ntdll!NtQueryInformationProcess` at `0x14002ee8b`
- `ntdll!DbgPrintEx` at `0x14002eeb3`
- `ntdll!DbgPrintEx` at `0x14002eeeb`
- `ntdll!DbgPrintEx` at `0x14002ef3e`
- `ntdll!DbgPrintEx` at `0x14002ef79`
- `ntdll!DbgPrintEx` at `0x14002eeb3`
- `ntdll!DbgPrintEx` at `0x14002eeeb`
- `ntdll!DbgPrintEx` at `0x14002ef3e`
- `ntdll!DbgPrintEx` at `0x14002ef79`

## string_xrefs

- `0x14002ef30`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read PebBaseAddress\n`

## pseudocode

```c

```
