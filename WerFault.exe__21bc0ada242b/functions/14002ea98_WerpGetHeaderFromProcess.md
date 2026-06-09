# WerpGetHeaderFromProcess

- ea: `0x14002ea98`
- end: `0x14002ecdf`
- name: `WerpGetHeaderFromProcess`
- size: `583`
- prototype: `signed int __fastcall(HANDLE hProcess, _WORD *lpBuffer)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x14002f008`
- `0x14002f194`
- `0x14004bb6c`

## callees

- `0x1400032ef`
- `0x140003307`
- `0x140003313`
- `0x140003337`
- `0x14002ea98`
- `0x14002ece8`
- `0x14002ee44`
- `0x14002ef98`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x14002eb96`
- `ntdll!DbgPrintEx` at `0x14002ebd5`
- `ntdll!DbgPrintEx` at `0x14002ec50`
- `ntdll!DbgPrintEx` at `0x14002ec93`
- `ntdll!DbgPrintEx` at `0x14002ecc9`
- `ntdll!DbgPrintEx` at `0x14002eb96`
- `ntdll!DbgPrintEx` at `0x14002ebd5`
- `ntdll!DbgPrintEx` at `0x14002ec50`
- `ntdll!DbgPrintEx` at `0x14002ec93`
- `ntdll!DbgPrintEx` at `0x14002ecc9`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x14002ead8`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x14002eafe`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x14002eb18`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x14002ead8`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x14002eafe`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x14002eb18`

## string_xrefs

- `0x14002eb51`: `WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n`
- `0x14002eb88`: `WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n`
- `0x14002ebc7`: `WER/CrashAPI/%u:%u: ERROR WerpNtWow64ReadVirtualMemory64 failed while trying to read PebBaseAddress\n`
- `0x14002ec42`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read WerRegistrationData\n`

## pseudocode

```c

```
