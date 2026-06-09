# __raise_securityfailure

- ea: `0x180001f04`
- end: `0x180001f38`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001f40`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180001f18`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001f18`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001f0f`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001f0f`
- `KERNEL32!GetCurrentProcess` at `0x180001f1e`
- `KERNEL32!GetCurrentProcess` at `0x180001f1e`
- `KERNEL32!TerminateProcess` at `0x180001f31`

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
0x180001f04  push    rbx
0x180001f06  sub     rsp, 20h
0x180001f0a  mov     rbx, rcx
0x180001f0d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001f0f  call    cs:__imp_SetUnhandledExceptionFilter
0x180001f15  mov     rcx, rbx; ExceptionInfo
0x180001f18  call    cs:__imp_UnhandledExceptionFilter
0x180001f1e  call    cs:__imp_GetCurrentProcess
0x180001f24  mov     rcx, rax
0x180001f27  mov     edx, 0C0000409h
0x180001f2c  add     rsp, 20h
0x180001f30  pop     rbx
0x180001f31  jmp     cs:__imp_TerminateProcess
```
