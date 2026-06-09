# WerpGetHeaderFromProcess

- ea: `0x18007a754`
- end: `0x18007a9f4`
- name: `WerpGetHeaderFromProcess`
- size: `672`
- prototype: `__int64 __fastcall(HANDLE hProcess, PVOID Buffer)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18007a4ec`
- `0x18007a5b0`
- `0x180126728`

## callees

- `0x1800134a0`
- `0x18007a754`
- `0x18007aa00`
- `0x18007aa54`
- `0x18007c8ec`
- `0x180124c00`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x18007a897`
- `ntdll!DbgPrintEx` at `0x18007a8e8`
- `ntdll!DbgPrintEx` at `0x18007a922`
- `ntdll!DbgPrintEx` at `0x18007a968`
- `ntdll!DbgPrintEx` at `0x18007a9e4`
- `ntdll!DbgPrintEx` at `0x18007a897`
- `ntdll!DbgPrintEx` at `0x18007a8e8`
- `ntdll!DbgPrintEx` at `0x18007a922`
- `ntdll!DbgPrintEx` at `0x18007a968`
- `ntdll!DbgPrintEx` at `0x18007a9e4`
- `ntdll!NtReadVirtualMemory` at `0x18007a82e`
- `ntdll!NtReadVirtualMemory` at `0x18007a82e`
- `ntdll!RtlWow64GetProcessMachines` at `0x18007a7bc`
- `ntdll!RtlWow64GetProcessMachines` at `0x18007a7bc`

## string_xrefs

- `0x18007a908`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read WerRegistrationData\n`
- `0x18007a9ca`: `WER/CrashAPI/%u:%u: ERROR WerpNtWow64ReadVirtualMemory64 failed while trying to read PebBaseAddress\n`
- `0x18007a885`: `WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n`
- `0x18007a8b2`: `WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n`

## pseudocode

```c

```
