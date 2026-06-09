# __raise_securityfailure

- ea: `0x180001a5c`
- end: `0x180001a90`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001aa0`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180001a89`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001a67`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001a67`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001a70`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001a70`
- `KERNEL32!GetCurrentProcess` at `0x180001a76`
- `KERNEL32!GetCurrentProcess` at `0x180001a76`

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
0x180001a5c  push    rbx
0x180001a5e  sub     rsp, 20h
0x180001a62  mov     rbx, rcx
0x180001a65  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001a67  call    cs:__imp_SetUnhandledExceptionFilter
0x180001a6d  mov     rcx, rbx; ExceptionInfo
0x180001a70  call    cs:__imp_UnhandledExceptionFilter
0x180001a76  call    cs:__imp_GetCurrentProcess
0x180001a7c  mov     rcx, rax
0x180001a7f  mov     edx, 0C0000409h
0x180001a84  add     rsp, 20h
0x180001a88  pop     rbx
0x180001a89  jmp     cs:__imp_TerminateProcess
```
