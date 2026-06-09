# __raise_securityfailure

- ea: `0x140036cdc`
- end: `0x140036d10`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140036d10`
- `0x140036df8`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x140036cf6`
- `KERNEL32!GetCurrentProcess` at `0x140036cf6`
- `KERNEL32!TerminateProcess` at `0x140036d09`
- `KERNEL32!UnhandledExceptionFilter` at `0x140036cf0`
- `KERNEL32!UnhandledExceptionFilter` at `0x140036cf0`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140036ce7`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140036ce7`

## pseudocode

```c

```
