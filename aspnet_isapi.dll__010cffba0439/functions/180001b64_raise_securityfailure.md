# __raise_securityfailure

- ea: `0x180001b64`
- end: `0x180001b98`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001ba0`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180001b91`
- `KERNEL32!GetCurrentProcess` at `0x180001b7e`
- `KERNEL32!GetCurrentProcess` at `0x180001b7e`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001b6f`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001b6f`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001b78`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001b78`

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
0x180001b64  push    rbx
0x180001b66  sub     rsp, 20h
0x180001b6a  mov     rbx, rcx
0x180001b6d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001b6f  call    cs:__imp_SetUnhandledExceptionFilter
0x180001b75  mov     rcx, rbx; ExceptionInfo
0x180001b78  call    cs:__imp_UnhandledExceptionFilter
0x180001b7e  call    cs:__imp_GetCurrentProcess
0x180001b84  mov     rcx, rax
0x180001b87  mov     edx, 0C0000409h
0x180001b8c  add     rsp, 20h
0x180001b90  pop     rbx
0x180001b91  jmp     cs:__imp_TerminateProcess
```
