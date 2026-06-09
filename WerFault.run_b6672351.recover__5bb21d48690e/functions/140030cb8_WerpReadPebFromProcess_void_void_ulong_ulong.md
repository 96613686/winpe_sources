# WerpReadPebFromProcess(void *,void *,ulong,ulong)

- ea: `0x140030cb8`
- end: `0x140030e22`
- name: `?WerpReadPebFromProcess@@YAJPEAX0KK@Z`
- size: `362`
- prototype: `__int64 __fastcall(HANDLE hProcess, void *lpBuffer, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400308b8`

## callees

- `0x14000333f`
- `0x140003357`
- `0x140003387`
- `0x140030cb8`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x140030cff`
- `ntdll!NtQueryInformationProcess` at `0x140030cff`
- `ntdll!DbgPrintEx` at `0x140030d2d`
- `ntdll!DbgPrintEx` at `0x140030d6b`
- `ntdll!DbgPrintEx` at `0x140030dc4`
- `ntdll!DbgPrintEx` at `0x140030e05`
- `ntdll!DbgPrintEx` at `0x140030d2d`
- `ntdll!DbgPrintEx` at `0x140030d6b`
- `ntdll!DbgPrintEx` at `0x140030dc4`
- `ntdll!DbgPrintEx` at `0x140030e05`

## string_xrefs

- `0x140030db6`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read PebBaseAddress\n`

## pseudocode

```c

```
