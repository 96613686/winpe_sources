# __raise_securityfailure

- ea: `0x140002158`
- end: `0x14000218c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400021a0`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x140002185`
- `KERNEL32!GetCurrentProcess` at `0x140002172`
- `KERNEL32!GetCurrentProcess` at `0x140002172`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140002163`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140002163`
- `KERNEL32!UnhandledExceptionFilter` at `0x14000216c`
- `KERNEL32!UnhandledExceptionFilter` at `0x14000216c`

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
0x140002158  push    rbx
0x14000215a  sub     rsp, 20h
0x14000215e  mov     rbx, rcx
0x140002161  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140002163  call    cs:__imp_SetUnhandledExceptionFilter
0x140002169  mov     rcx, rbx; ExceptionInfo
0x14000216c  call    cs:__imp_UnhandledExceptionFilter
0x140002172  call    cs:__imp_GetCurrentProcess
0x140002178  mov     rcx, rax
0x14000217b  mov     edx, 0C0000409h
0x140002180  add     rsp, 20h
0x140002184  pop     rbx
0x140002185  jmp     cs:__imp_TerminateProcess
```
