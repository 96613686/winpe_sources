# __raise_securityfailure

- ea: `0x140001cec`
- end: `0x140001d20`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001d30`
- `0x140001e20`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x140001d00`
- `KERNEL32!UnhandledExceptionFilter` at `0x140001d00`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140001cf7`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140001cf7`
- `KERNEL32!GetCurrentProcess` at `0x140001d06`
- `KERNEL32!GetCurrentProcess` at `0x140001d06`
- `KERNEL32!TerminateProcess` at `0x140001d19`

## pseudocode

```c
BOOL __fastcall _raise_securityfailure(struct _EXCEPTION_POINTERS *ExceptionInfo)
{
  HANDLE CurrentProcess; // rax

  SetUnhandledExceptionFilter(0);
  UnhandledExceptionFilter(ExceptionInfo);
  CurrentProcess = GetCurrentProcess();
  return TerminateProcess(CurrentProcess, 0xC0000409);
}

```

## disassembly

```asm
0x140001cec  push    rbx
0x140001cee  sub     rsp, 20h
0x140001cf2  mov     rbx, rcx
0x140001cf5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140001cf7  call    cs:__imp_SetUnhandledExceptionFilter
0x140001cfd  mov     rcx, rbx; ExceptionInfo
0x140001d00  call    cs:__imp_UnhandledExceptionFilter
0x140001d06  call    cs:__imp_GetCurrentProcess
0x140001d0c  mov     rcx, rax
0x140001d0f  mov     edx, 0C0000409h
0x140001d14  add     rsp, 20h
0x140001d18  pop     rbx
0x140001d19  jmp     cs:__imp_TerminateProcess
```
