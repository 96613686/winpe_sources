# __raise_securityfailure

- ea: `0x1801825e8`
- end: `0x18018261c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180182620`
- `0x180182710`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180182615`
- `KERNEL32!UnhandledExceptionFilter` at `0x1801825fc`
- `KERNEL32!UnhandledExceptionFilter` at `0x1801825fc`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1801825f3`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1801825f3`
- `KERNEL32!GetCurrentProcess` at `0x180182602`
- `KERNEL32!GetCurrentProcess` at `0x180182602`

## pseudocode

```c

```
