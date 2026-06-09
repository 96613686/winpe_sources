# WerpGetHeaderFromProcess

- ea: `0x1400308b8`
- end: `0x140030b34`
- name: `WerpGetHeaderFromProcess`
- size: `636`
- prototype: `__int64 __fastcall(HANDLE hProcess, LPVOID lpBuffer)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x140030e9c`
- `0x140031044`
- `0x14004f02c`

## callees

- `0x14000333f`
- `0x140003357`
- `0x140003363`
- `0x140003387`
- `0x1400308b8`
- `0x140030b3c`
- `0x140030cb8`
- `0x140030e28`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x1400309c8`
- `ntdll!DbgPrintEx` at `0x140030a0d`
- `ntdll!DbgPrintEx` at `0x140030a8e`
- `ntdll!DbgPrintEx` at `0x140030adb`
- `ntdll!DbgPrintEx` at `0x140030b17`
- `ntdll!DbgPrintEx` at `0x1400309c8`
- `ntdll!DbgPrintEx` at `0x140030a0d`
- `ntdll!DbgPrintEx` at `0x140030a8e`
- `ntdll!DbgPrintEx` at `0x140030adb`
- `ntdll!DbgPrintEx` at `0x140030b17`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x1400308f8`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x140030924`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x140030944`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x1400308f8`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x140030924`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x140030944`

## string_xrefs

- `0x140030983`: `WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n`
- `0x1400309ba`: `WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n`
- `0x1400309ff`: `WER/CrashAPI/%u:%u: ERROR WerpNtWow64ReadVirtualMemory64 failed while trying to read PebBaseAddress\n`
- `0x140030a80`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read WerRegistrationData\n`

## pseudocode

```c

```
