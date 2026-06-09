# __raise_securityfailure

- ea: `0x180002bb0`
- end: `0x180002be4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002bf0`
- `0x180002cd8`
- `0x180002d78`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180002bc4`
- `KERNEL32!UnhandledExceptionFilter` at `0x180002bc4`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180002bbb`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180002bbb`
- `KERNEL32!GetCurrentProcess` at `0x180002bca`
- `KERNEL32!GetCurrentProcess` at `0x180002bca`
- `KERNEL32!TerminateProcess` at `0x180002bdd`

## pseudocode

```c

```
