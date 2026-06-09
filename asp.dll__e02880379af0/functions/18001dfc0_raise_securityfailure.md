# __raise_securityfailure

- ea: `0x18001dfc0`
- end: `0x18001dff4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001e000`
- `0x18001e1a8`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x18001dfd4`
- `KERNEL32!UnhandledExceptionFilter` at `0x18001dfd4`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18001dfcb`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18001dfcb`
- `KERNEL32!TerminateProcess` at `0x18001dfed`
- `KERNEL32!GetCurrentProcess` at `0x18001dfda`
- `KERNEL32!GetCurrentProcess` at `0x18001dfda`

## pseudocode

```c

```
