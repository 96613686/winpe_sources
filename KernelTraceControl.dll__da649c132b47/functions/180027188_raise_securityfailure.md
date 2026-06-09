# __raise_securityfailure

- ea: `0x180027188`
- end: `0x1800271bc`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800271c0`
- `0x180027334`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x18002719c`
- `KERNEL32!UnhandledExceptionFilter` at `0x18002719c`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180027193`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180027193`
- `KERNEL32!GetCurrentProcess` at `0x1800271a2`
- `KERNEL32!GetCurrentProcess` at `0x1800271a2`
- `KERNEL32!TerminateProcess` at `0x1800271b5`

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
0x180027188  push    rbx
0x18002718a  sub     rsp, 20h
0x18002718e  mov     rbx, rcx
0x180027191  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180027193  call    cs:__imp_SetUnhandledExceptionFilter
0x180027199  mov     rcx, rbx; ExceptionInfo
0x18002719c  call    cs:__imp_UnhandledExceptionFilter
0x1800271a2  call    cs:__imp_GetCurrentProcess
0x1800271a8  mov     rcx, rax
0x1800271ab  mov     edx, 0C0000409h
0x1800271b0  add     rsp, 20h
0x1800271b4  pop     rbx
0x1800271b5  jmp     cs:__imp_TerminateProcess
```
