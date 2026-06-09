# ___raise_securityfailure

- ea: `0x40d74a`
- end: `0x40d772`
- name: `___raise_securityfailure`
- size: `40`
- prototype: `BOOL __cdecl(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x40d772`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x40d758`
- `KERNEL32!UnhandledExceptionFilter` at `0x40d758`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x40d74f`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x40d74f`
- `KERNEL32!GetCurrentProcess` at `0x40d763`
- `KERNEL32!GetCurrentProcess` at `0x40d763`
- `KERNEL32!TerminateProcess` at `0x40d76a`
- `KERNEL32!TerminateProcess` at `0x40d76a`

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
0x40d74a  push    ebp
0x40d74b  mov     ebp, esp
0x40d74d  push    0; lpTopLevelExceptionFilter
0x40d74f  call    ds:SetUnhandledExceptionFilter
0x40d755  push    [ebp+ExceptionInfo]; ExceptionInfo
0x40d758  call    ds:UnhandledExceptionFilter
0x40d75e  push    0C0000409h; uExitCode
0x40d763  call    ds:GetCurrentProcess
0x40d769  push    eax; hProcess
0x40d76a  call    ds:TerminateProcess
0x40d770  pop     ebp
0x40d771  retn
```
