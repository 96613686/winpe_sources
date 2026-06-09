# __raise_securityfailure

- ea: `0x1800015e8`
- end: `0x18000161c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001630`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x1800015fc`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800015fc`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800015f3`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800015f3`
- `KERNEL32!GetCurrentProcess` at `0x180001602`
- `KERNEL32!GetCurrentProcess` at `0x180001602`
- `KERNEL32!TerminateProcess` at `0x180001615`

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
0x1800015e8  push    rbx
0x1800015ea  sub     rsp, 20h
0x1800015ee  mov     rbx, rcx
0x1800015f1  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800015f3  call    cs:__imp_SetUnhandledExceptionFilter
0x1800015f9  mov     rcx, rbx; ExceptionInfo
0x1800015fc  call    cs:__imp_UnhandledExceptionFilter
0x180001602  call    cs:__imp_GetCurrentProcess
0x180001608  mov     rcx, rax
0x18000160b  mov     edx, 0C0000409h
0x180001610  add     rsp, 20h
0x180001614  pop     rbx
0x180001615  jmp     cs:__imp_TerminateProcess
```
