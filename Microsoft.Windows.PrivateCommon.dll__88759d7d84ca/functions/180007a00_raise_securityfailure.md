# __raise_securityfailure

- ea: `0x180007a00`
- end: `0x180007a34`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180007a40`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180007a14`
- `KERNEL32!UnhandledExceptionFilter` at `0x180007a14`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180007a0b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180007a0b`
- `KERNEL32!GetCurrentProcess` at `0x180007a1a`
- `KERNEL32!GetCurrentProcess` at `0x180007a1a`
- `KERNEL32!TerminateProcess` at `0x180007a2d`

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
0x180007a00  push    rbx
0x180007a02  sub     rsp, 20h
0x180007a06  mov     rbx, rcx
0x180007a09  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180007a0b  call    cs:__imp_SetUnhandledExceptionFilter
0x180007a11  mov     rcx, rbx; ExceptionInfo
0x180007a14  call    cs:__imp_UnhandledExceptionFilter
0x180007a1a  call    cs:__imp_GetCurrentProcess
0x180007a20  mov     rcx, rax
0x180007a23  mov     edx, 0C0000409h
0x180007a28  add     rsp, 20h
0x180007a2c  pop     rbx
0x180007a2d  jmp     cs:__imp_TerminateProcess
```
