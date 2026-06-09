# __raise_securityfailure

- ea: `0x180001fa4`
- end: `0x180001fd8`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001fe0`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180001fd1`
- `KERNEL32!GetCurrentProcess` at `0x180001fbe`
- `KERNEL32!GetCurrentProcess` at `0x180001fbe`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001faf`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001faf`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001fb8`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001fb8`

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
0x180001fa4  push    rbx
0x180001fa6  sub     rsp, 20h
0x180001faa  mov     rbx, rcx
0x180001fad  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001faf  call    cs:__imp_SetUnhandledExceptionFilter
0x180001fb5  mov     rcx, rbx; ExceptionInfo
0x180001fb8  call    cs:__imp_UnhandledExceptionFilter
0x180001fbe  call    cs:__imp_GetCurrentProcess
0x180001fc4  mov     rcx, rax
0x180001fc7  mov     edx, 0C0000409h
0x180001fcc  add     rsp, 20h
0x180001fd0  pop     rbx
0x180001fd1  jmp     cs:__imp_TerminateProcess
```
