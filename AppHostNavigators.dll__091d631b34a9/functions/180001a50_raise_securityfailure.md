# __raise_securityfailure

- ea: `0x180001a50`
- end: `0x180001a84`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001a90`
- `0x180001c38`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180001a7d`
- `KERNEL32!GetCurrentProcess` at `0x180001a6a`
- `KERNEL32!GetCurrentProcess` at `0x180001a6a`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001a5b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001a5b`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001a64`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001a64`

## pseudocode

```c

```
