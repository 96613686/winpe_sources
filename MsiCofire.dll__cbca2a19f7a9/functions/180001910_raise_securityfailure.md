# __raise_securityfailure

- ea: `0x180001910`
- end: `0x180001944`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001950`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180001924`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001924`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000191b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000191b`
- `KERNEL32!GetCurrentProcess` at `0x18000192a`
- `KERNEL32!GetCurrentProcess` at `0x18000192a`
- `KERNEL32!TerminateProcess` at `0x18000193d`

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
0x180001910  push    rbx
0x180001912  sub     rsp, 20h
0x180001916  mov     rbx, rcx
0x180001919  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000191b  call    cs:__imp_SetUnhandledExceptionFilter
0x180001921  mov     rcx, rbx; ExceptionInfo
0x180001924  call    cs:__imp_UnhandledExceptionFilter
0x18000192a  call    cs:__imp_GetCurrentProcess
0x180001930  mov     rcx, rax
0x180001933  mov     edx, 0C0000409h
0x180001938  add     rsp, 20h
0x18000193c  pop     rbx
0x18000193d  jmp     cs:__imp_TerminateProcess
```
