# __raise_securityfailure

- ea: `0x180001fc8`
- end: `0x180001ffc`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002010`
- `0x1800021b8`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180001ff5`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001fd3`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001fd3`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001fdc`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001fdc`
- `KERNEL32!GetCurrentProcess` at `0x180001fe2`
- `KERNEL32!GetCurrentProcess` at `0x180001fe2`

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
0x180001fc8  push    rbx
0x180001fca  sub     rsp, 20h
0x180001fce  mov     rbx, rcx
0x180001fd1  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001fd3  call    cs:__imp_SetUnhandledExceptionFilter
0x180001fd9  mov     rcx, rbx; ExceptionInfo
0x180001fdc  call    cs:__imp_UnhandledExceptionFilter
0x180001fe2  call    cs:__imp_GetCurrentProcess
0x180001fe8  mov     rcx, rax
0x180001feb  mov     edx, 0C0000409h
0x180001ff0  add     rsp, 20h
0x180001ff4  pop     rbx
0x180001ff5  jmp     cs:__imp_TerminateProcess
```
