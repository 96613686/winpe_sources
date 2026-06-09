# __raise_securityfailure

- ea: `0x18000214c`
- end: `0x180002180`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002190`
- `0x180002338`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180002179`
- `KERNEL32!GetCurrentProcess` at `0x180002166`
- `KERNEL32!GetCurrentProcess` at `0x180002166`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180002157`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180002157`
- `KERNEL32!UnhandledExceptionFilter` at `0x180002160`
- `KERNEL32!UnhandledExceptionFilter` at `0x180002160`

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
0x18000214c  push    rbx
0x18000214e  sub     rsp, 20h
0x180002152  mov     rbx, rcx
0x180002155  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180002157  call    cs:__imp_SetUnhandledExceptionFilter
0x18000215d  mov     rcx, rbx; ExceptionInfo
0x180002160  call    cs:__imp_UnhandledExceptionFilter
0x180002166  call    cs:__imp_GetCurrentProcess
0x18000216c  mov     rcx, rax
0x18000216f  mov     edx, 0C0000409h
0x180002174  add     rsp, 20h
0x180002178  pop     rbx
0x180002179  jmp     cs:__imp_TerminateProcess
```
