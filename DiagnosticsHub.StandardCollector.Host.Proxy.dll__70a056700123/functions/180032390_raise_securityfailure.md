# __raise_securityfailure

- ea: `0x180032390`
- end: `0x1800323c4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800323d0`
- `0x1800324b8`
- `0x180032558`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x1800323a4`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800323a4`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18003239b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18003239b`
- `KERNEL32!GetCurrentProcess` at `0x1800323aa`
- `KERNEL32!GetCurrentProcess` at `0x1800323aa`
- `KERNEL32!TerminateProcess` at `0x1800323bd`

## pseudocode

```c

```
