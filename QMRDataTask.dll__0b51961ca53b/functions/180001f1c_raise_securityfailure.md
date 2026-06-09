# __raise_securityfailure

- ea: `0x180001f1c`
- end: `0x180001f50`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001f60`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180001f30`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001f30`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001f27`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001f27`
- `KERNEL32!GetCurrentProcess` at `0x180001f36`
- `KERNEL32!GetCurrentProcess` at `0x180001f36`
- `KERNEL32!TerminateProcess` at `0x180001f49`

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
0x180001f1c  push    rbx
0x180001f1e  sub     rsp, 20h
0x180001f22  mov     rbx, rcx
0x180001f25  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001f27  call    cs:__imp_SetUnhandledExceptionFilter
0x180001f2d  mov     rcx, rbx; ExceptionInfo
0x180001f30  call    cs:__imp_UnhandledExceptionFilter
0x180001f36  call    cs:__imp_GetCurrentProcess
0x180001f3c  mov     rcx, rax
0x180001f3f  mov     edx, 0C0000409h
0x180001f44  add     rsp, 20h
0x180001f48  pop     rbx
0x180001f49  jmp     cs:__imp_TerminateProcess
```
