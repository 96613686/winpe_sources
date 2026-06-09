# __raise_securityfailure

- ea: `0x1800016c0`
- end: `0x1800016f4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001700`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x1800016d4`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800016d4`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800016cb`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800016cb`
- `KERNEL32!GetCurrentProcess` at `0x1800016da`
- `KERNEL32!GetCurrentProcess` at `0x1800016da`
- `KERNEL32!TerminateProcess` at `0x1800016ed`

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
0x1800016c0  push    rbx
0x1800016c2  sub     rsp, 20h
0x1800016c6  mov     rbx, rcx
0x1800016c9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800016cb  call    cs:__imp_SetUnhandledExceptionFilter
0x1800016d1  mov     rcx, rbx; ExceptionInfo
0x1800016d4  call    cs:__imp_UnhandledExceptionFilter
0x1800016da  call    cs:__imp_GetCurrentProcess
0x1800016e0  mov     rcx, rax
0x1800016e3  mov     edx, 0C0000409h
0x1800016e8  add     rsp, 20h
0x1800016ec  pop     rbx
0x1800016ed  jmp     cs:__imp_TerminateProcess
```
