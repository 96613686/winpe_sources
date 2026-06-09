# __raise_securityfailure

- ea: `0x1800015ec`
- end: `0x180001620`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001630`
- `0x1800017d8`

## import_xrefs

- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800015f7`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800015f7`
- `KERNEL32!TerminateProcess` at `0x180001619`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001600`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001600`
- `KERNEL32!GetCurrentProcess` at `0x180001606`
- `KERNEL32!GetCurrentProcess` at `0x180001606`

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
0x1800015ec  push    rbx
0x1800015ee  sub     rsp, 20h
0x1800015f2  mov     rbx, rcx
0x1800015f5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800015f7  call    cs:__imp_SetUnhandledExceptionFilter
0x1800015fd  mov     rcx, rbx; ExceptionInfo
0x180001600  call    cs:__imp_UnhandledExceptionFilter
0x180001606  call    cs:__imp_GetCurrentProcess
0x18000160c  mov     rcx, rax
0x18000160f  mov     edx, 0C0000409h
0x180001614  add     rsp, 20h
0x180001618  pop     rbx
0x180001619  jmp     cs:__imp_TerminateProcess
```
