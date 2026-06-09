# __raise_securityfailure

- ea: `0x180018d30`
- end: `0x180018d64`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180018d70`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180018d4a`
- `KERNEL32!GetCurrentProcess` at `0x180018d4a`
- `KERNEL32!TerminateProcess` at `0x180018d5d`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180018d3b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180018d3b`
- `KERNEL32!UnhandledExceptionFilter` at `0x180018d44`
- `KERNEL32!UnhandledExceptionFilter` at `0x180018d44`

## pseudocode

```c

```
