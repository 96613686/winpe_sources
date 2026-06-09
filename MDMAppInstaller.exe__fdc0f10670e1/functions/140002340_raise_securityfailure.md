# __raise_securityfailure

- ea: `0x140002340`
- end: `0x140002374`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140002380`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x14000236d`
- `KERNEL32!GetCurrentProcess` at `0x14000235a`
- `KERNEL32!GetCurrentProcess` at `0x14000235a`
- `KERNEL32!UnhandledExceptionFilter` at `0x140002354`
- `KERNEL32!UnhandledExceptionFilter` at `0x140002354`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14000234b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14000234b`

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
0x140002340  push    rbx
0x140002342  sub     rsp, 20h
0x140002346  mov     rbx, rcx
0x140002349  xor     ecx, ecx; lpTopLevelExceptionFilter
0x14000234b  call    cs:__imp_SetUnhandledExceptionFilter
0x140002351  mov     rcx, rbx; ExceptionInfo
0x140002354  call    cs:__imp_UnhandledExceptionFilter
0x14000235a  call    cs:__imp_GetCurrentProcess
0x140002360  mov     rcx, rax
0x140002363  mov     edx, 0C0000409h
0x140002368  add     rsp, 20h
0x14000236c  pop     rbx
0x14000236d  jmp     cs:__imp_TerminateProcess
```
