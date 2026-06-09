# __raise_securityfailure

- ea: `0x180001900`
- end: `0x180001934`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001940`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x18000192d`
- `KERNEL32!GetCurrentProcess` at `0x18000191a`
- `KERNEL32!GetCurrentProcess` at `0x18000191a`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000190b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000190b`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001914`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001914`

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
0x180001900  push    rbx
0x180001902  sub     rsp, 20h
0x180001906  mov     rbx, rcx
0x180001909  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000190b  call    cs:__imp_SetUnhandledExceptionFilter
0x180001911  mov     rcx, rbx; ExceptionInfo
0x180001914  call    cs:__imp_UnhandledExceptionFilter
0x18000191a  call    cs:__imp_GetCurrentProcess
0x180001920  mov     rcx, rax
0x180001923  mov     edx, 0C0000409h
0x180001928  add     rsp, 20h
0x18000192c  pop     rbx
0x18000192d  jmp     cs:__imp_TerminateProcess
```
