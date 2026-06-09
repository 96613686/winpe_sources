# __raise_securityfailure

- ea: `0x180001ee4`
- end: `0x180001f18`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001f20`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180001ef8`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001ef8`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001eef`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001eef`
- `KERNEL32!GetCurrentProcess` at `0x180001efe`
- `KERNEL32!GetCurrentProcess` at `0x180001efe`
- `KERNEL32!TerminateProcess` at `0x180001f11`

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
0x180001ee4  push    rbx
0x180001ee6  sub     rsp, 20h
0x180001eea  mov     rbx, rcx
0x180001eed  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001eef  call    cs:__imp_SetUnhandledExceptionFilter
0x180001ef5  mov     rcx, rbx; ExceptionInfo
0x180001ef8  call    cs:__imp_UnhandledExceptionFilter
0x180001efe  call    cs:__imp_GetCurrentProcess
0x180001f04  mov     rcx, rax
0x180001f07  mov     edx, 0C0000409h
0x180001f0c  add     rsp, 20h
0x180001f10  pop     rbx
0x180001f11  jmp     cs:__imp_TerminateProcess
```
