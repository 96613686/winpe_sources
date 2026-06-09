# __raise_securityfailure

- ea: `0x100469344`
- end: `0x100469378`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x100469380`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x100469358`
- `KERNEL32!UnhandledExceptionFilter` at `0x100469358`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x10046934f`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x10046934f`
- `KERNEL32!GetCurrentProcess` at `0x10046935e`
- `KERNEL32!GetCurrentProcess` at `0x10046935e`
- `KERNEL32!TerminateProcess` at `0x100469371`

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
0x100469344  push    rbx
0x100469346  sub     rsp, 20h
0x10046934a  mov     rbx, rcx
0x10046934d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x10046934f  call    cs:__imp_SetUnhandledExceptionFilter
0x100469355  mov     rcx, rbx; ExceptionInfo
0x100469358  call    cs:__imp_UnhandledExceptionFilter
0x10046935e  call    cs:__imp_GetCurrentProcess
0x100469364  mov     rcx, rax
0x100469367  mov     edx, 0C0000409h
0x10046936c  add     rsp, 20h
0x100469370  pop     rbx
0x100469371  jmp     cs:__imp_TerminateProcess
```
