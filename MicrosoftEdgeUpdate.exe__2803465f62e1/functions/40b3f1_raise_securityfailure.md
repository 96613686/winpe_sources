# ___raise_securityfailure

- ea: `0x40b3f1`
- end: `0x40b419`
- name: `___raise_securityfailure`
- size: `40`
- prototype: `BOOL __cdecl(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x40b419`
- `0x40b51f`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x40b3ff`
- `KERNEL32!UnhandledExceptionFilter` at `0x40b3ff`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x40b3f6`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x40b3f6`
- `KERNEL32!GetCurrentProcess` at `0x40b40a`
- `KERNEL32!GetCurrentProcess` at `0x40b40a`
- `KERNEL32!TerminateProcess` at `0x40b411`
- `KERNEL32!TerminateProcess` at `0x40b411`

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
0x40b3f1  push    ebp
0x40b3f2  mov     ebp, esp
0x40b3f4  push    0; lpTopLevelExceptionFilter
0x40b3f6  call    ds:SetUnhandledExceptionFilter
0x40b3fc  push    [ebp+ExceptionInfo]; ExceptionInfo
0x40b3ff  call    ds:UnhandledExceptionFilter
0x40b405  push    0C0000409h; uExitCode
0x40b40a  call    ds:GetCurrentProcess
0x40b410  push    eax; hProcess
0x40b411  call    ds:TerminateProcess
0x40b417  pop     ebp
0x40b418  retn
```
