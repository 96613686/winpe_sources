# __raise_securityfailure

- ea: `0x180011c88`
- end: `0x180011cbc`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180011cc0`
- `0x180011da8`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180011cb5`
- `KERNEL32!UnhandledExceptionFilter` at `0x180011c9c`
- `KERNEL32!UnhandledExceptionFilter` at `0x180011c9c`
- `KERNEL32!GetCurrentProcess` at `0x180011ca2`
- `KERNEL32!GetCurrentProcess` at `0x180011ca2`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180011c93`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180011c93`

## pseudocode

```c

```
