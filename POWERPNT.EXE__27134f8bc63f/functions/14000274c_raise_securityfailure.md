# __raise_securityfailure

- ea: `0x14000274c`
- end: `0x140002780`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140002790`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x140002760`
- `KERNEL32!UnhandledExceptionFilter` at `0x140002760`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140002757`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140002757`
- `KERNEL32!GetCurrentProcess` at `0x140002766`
- `KERNEL32!GetCurrentProcess` at `0x140002766`
- `KERNEL32!TerminateProcess` at `0x140002779`

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
0x14000274c  push    rbx
0x14000274e  sub     rsp, 20h
0x140002752  mov     rbx, rcx
0x140002755  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140002757  call    cs:__imp_SetUnhandledExceptionFilter
0x14000275d  mov     rcx, rbx; ExceptionInfo
0x140002760  call    cs:__imp_UnhandledExceptionFilter
0x140002766  call    cs:__imp_GetCurrentProcess
0x14000276c  mov     rcx, rax
0x14000276f  mov     edx, 0C0000409h
0x140002774  add     rsp, 20h
0x140002778  pop     rbx
0x140002779  jmp     cs:__imp_TerminateProcess
```
