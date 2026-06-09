# CreateEventExA

- ea: `0x18006d010`
- end: `0x18006d256`
- name: `CreateEventExA`
- size: `582`
- prototype: `HANDLE __stdcall(LPSECURITY_ATTRIBUTES lpEventAttributes, LPCSTR lpName, DWORD dwFlags, DWORD dwDesiredAccess)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006bcf0`
- `0x1800d061c`
- `0x1800f8e60`

## callees

- `0x1800134a0`
- `0x18006d010`
- `0x18006e3f0`
- `0x180197010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18006d1b8`
- `ntdll!RtlFreeUnicodeString` at `0x18006d1b8`
- `ntdll!RtlInitUnicodeString` at `0x18006d119`
- `ntdll!RtlInitUnicodeString` at `0x18006d119`
- `ntdll!RtlSetLastWin32Error` at `0x18006d0b8`
- `ntdll!RtlSetLastWin32Error` at `0x18006d221`
- `ntdll!RtlSetLastWin32Error` at `0x18006d23f`
- `ntdll!RtlSetLastWin32Error` at `0x18006d0b8`
- `ntdll!RtlSetLastWin32Error` at `0x18006d221`
- `ntdll!RtlSetLastWin32Error` at `0x18006d23f`
- `ntdll!NtCreateEvent` at `0x18006d09d`
- `ntdll!NtCreateEvent` at `0x18006d09d`
- `ntdll!RtlInitAnsiStringEx` at `0x18006d1d7`
- `ntdll!RtlInitAnsiStringEx` at `0x18006d1d7`

## pseudocode

```c

```
