# ___raise_securityfailure

- ea: `0x40cbab`
- end: `0x40cbd5`
- name: `___raise_securityfailure`
- size: `42`
- prototype: `BOOL __cdecl(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x40cbdb`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x40cbcd`
- `KERNEL32!TerminateProcess` at `0x40cbcd`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x40cbb2`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x40cbb2`
- `KERNEL32!UnhandledExceptionFilter` at `0x40cbbb`
- `KERNEL32!UnhandledExceptionFilter` at `0x40cbbb`
- `KERNEL32!GetCurrentProcess` at `0x40cbc6`
- `KERNEL32!GetCurrentProcess` at `0x40cbc6`

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
0x40cbab  mov     edi, edi
0x40cbad  push    ebp
0x40cbae  mov     ebp, esp
0x40cbb0  push    0; lpTopLevelExceptionFilter
0x40cbb2  call    ds:__imp__SetUnhandledExceptionFilter@4; SetUnhandledExceptionFilter(x)
0x40cbb8  push    [ebp+ExceptionInfo]; ExceptionInfo
0x40cbbb  call    ds:__imp__UnhandledExceptionFilter@4; UnhandledExceptionFilter(x)
0x40cbc1  push    0C0000409h; uExitCode
0x40cbc6  call    ds:__imp__GetCurrentProcess@0; GetCurrentProcess()
0x40cbcc  push    eax; hProcess
0x40cbcd  call    ds:__imp__TerminateProcess@8; TerminateProcess(x,x)
0x40cbd3  pop     ebp
0x40cbd4  retn
```
