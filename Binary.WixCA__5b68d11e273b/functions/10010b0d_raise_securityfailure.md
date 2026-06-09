# ___raise_securityfailure

- ea: `0x10010b0d`
- end: `0x10010b35`
- name: `___raise_securityfailure`
- size: `40`
- prototype: `int __cdecl(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x10010b35`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x10010b2d`
- `KERNEL32!TerminateProcess` at `0x10010b2d`
- `KERNEL32!GetCurrentProcess` at `0x10010b26`
- `KERNEL32!GetCurrentProcess` at `0x10010b26`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x10010b12`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x10010b12`
- `KERNEL32!UnhandledExceptionFilter` at `0x10010b1b`
- `KERNEL32!UnhandledExceptionFilter` at `0x10010b1b`

## pseudocode

```c
BOOL __cdecl __raise_securityfailure(struct _EXCEPTION_POINTERS *ExceptionInfo)
{
  HANDLE CurrentProcess; // eax

  SetUnhandledExceptionFilter(0);
  UnhandledExceptionFilter(ExceptionInfo);
  CurrentProcess = GetCurrentProcess();
  return TerminateProcess(CurrentProcess, 0xC0000409);
}

```

## disassembly

```asm
0x10010b0d  push    ebp
0x10010b0e  mov     ebp, esp
0x10010b10  push    0; lpTopLevelExceptionFilter
0x10010b12  call    ds:SetUnhandledExceptionFilter
0x10010b18  push    [ebp+ExceptionInfo]; ExceptionInfo
0x10010b1b  call    ds:UnhandledExceptionFilter
0x10010b21  push    0C0000409h; uExitCode
0x10010b26  call    ds:GetCurrentProcess
0x10010b2c  push    eax; hProcess
0x10010b2d  call    ds:TerminateProcess
0x10010b33  pop     ebp
0x10010b34  retn
```
