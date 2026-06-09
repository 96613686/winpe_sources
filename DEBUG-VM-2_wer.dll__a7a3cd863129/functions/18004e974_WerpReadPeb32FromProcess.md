# WerpReadPeb32FromProcess

- ea: `0x18004e974`
- end: `0x18004eaca`
- name: `WerpReadPeb32FromProcess`
- size: `342`
- prototype: `__int64 __fastcall(HANDLE hProcess, LPVOID lpBuffer)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18004d224`

## callees

- `0x18004e974`
- `0x180051b7c`
- `0x180052d61`
- `0x180052da9`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x18004e9ba`
- `ntdll!NtQueryInformationProcess` at `0x18004e9ba`
- `ntdll!DbgPrintEx` at `0x18004e9e8`
- `ntdll!DbgPrintEx` at `0x18004ea21`
- `ntdll!DbgPrintEx` at `0x18004ea74`
- `ntdll!DbgPrintEx` at `0x18004eaaf`
- `ntdll!DbgPrintEx` at `0x18004e9e8`
- `ntdll!DbgPrintEx` at `0x18004ea21`
- `ntdll!DbgPrintEx` at `0x18004ea74`
- `ntdll!DbgPrintEx` at `0x18004eaaf`

## string_xrefs

- `0x18004ea66`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read Peb32BaseAddress\n`

## pseudocode

```c

```
