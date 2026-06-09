# ___raise_securityfailure

- ea: `0x408c13`
- end: `0x408c3b`
- name: `___raise_securityfailure`
- size: `40`
- prototype: `BOOL __cdecl(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x408c3b`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x408c33`
- `KERNEL32!TerminateProcess` at `0x408c33`
- `KERNEL32!GetCurrentProcess` at `0x408c2c`
- `KERNEL32!GetCurrentProcess` at `0x408c2c`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x408c18`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x408c18`
- `KERNEL32!UnhandledExceptionFilter` at `0x408c21`
- `KERNEL32!UnhandledExceptionFilter` at `0x408c21`

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
0x408c13  push    ebp
0x408c14  mov     ebp, esp
0x408c16  push    0; lpTopLevelExceptionFilter
0x408c18  call    ds:SetUnhandledExceptionFilter
0x408c1e  push    [ebp+ExceptionInfo]; ExceptionInfo
0x408c21  call    ds:UnhandledExceptionFilter
0x408c27  push    0C0000409h; uExitCode
0x408c2c  call    ds:GetCurrentProcess
0x408c32  push    eax; hProcess
0x408c33  call    ds:TerminateProcess
0x408c39  pop     ebp
0x408c3a  retn
```
