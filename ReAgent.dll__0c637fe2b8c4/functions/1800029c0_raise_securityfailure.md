# __raise_securityfailure

- ea: `0x1800029c0`
- end: `0x1800029f4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002a00`
- `0x180002ba8`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x1800029d4`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800029d4`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800029cb`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800029cb`
- `KERNEL32!GetCurrentProcess` at `0x1800029da`
- `KERNEL32!GetCurrentProcess` at `0x1800029da`
- `KERNEL32!TerminateProcess` at `0x1800029ed`

## pseudocode

```c

```
