# __raise_securityfailure

- ea: `0x180150780`
- end: `0x1801507b4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1801507c0`
- `0x1801508a8`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x18015079a`
- `KERNEL32!GetCurrentProcess` at `0x18015079a`
- `KERNEL32!TerminateProcess` at `0x1801507ad`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18015078b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18015078b`
- `KERNEL32!UnhandledExceptionFilter` at `0x180150794`
- `KERNEL32!UnhandledExceptionFilter` at `0x180150794`

## pseudocode

```c

```
