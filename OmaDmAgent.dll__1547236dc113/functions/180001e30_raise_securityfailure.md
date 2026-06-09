# __raise_securityfailure

- ea: `0x180001e30`
- end: `0x180001e64`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001e70`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180001e44`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001e44`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001e3b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001e3b`
- `KERNEL32!GetCurrentProcess` at `0x180001e4a`
- `KERNEL32!GetCurrentProcess` at `0x180001e4a`
- `KERNEL32!TerminateProcess` at `0x180001e5d`

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
0x180001e30  push    rbx
0x180001e32  sub     rsp, 20h
0x180001e36  mov     rbx, rcx
0x180001e39  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001e3b  call    cs:__imp_SetUnhandledExceptionFilter
0x180001e41  mov     rcx, rbx; ExceptionInfo
0x180001e44  call    cs:__imp_UnhandledExceptionFilter
0x180001e4a  call    cs:__imp_GetCurrentProcess
0x180001e50  mov     rcx, rax
0x180001e53  mov     edx, 0C0000409h
0x180001e58  add     rsp, 20h
0x180001e5c  pop     rbx
0x180001e5d  jmp     cs:__imp_TerminateProcess
```
