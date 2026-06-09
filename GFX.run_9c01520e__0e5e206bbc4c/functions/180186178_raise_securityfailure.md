# __raise_securityfailure

- ea: `0x180186178`
- end: `0x1801861ac`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1801861b0`
- `0x1801862a0`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x1801861a5`
- `KERNEL32!UnhandledExceptionFilter` at `0x18018618c`
- `KERNEL32!UnhandledExceptionFilter` at `0x18018618c`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180186183`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180186183`
- `KERNEL32!GetCurrentProcess` at `0x180186192`
- `KERNEL32!GetCurrentProcess` at `0x180186192`

## pseudocode

```c

```
