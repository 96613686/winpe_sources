# __raise_securityfailure

- ea: `0x180001b50`
- end: `0x180001b84`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001b90`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180001b7d`
- `KERNEL32!GetCurrentProcess` at `0x180001b6a`
- `KERNEL32!GetCurrentProcess` at `0x180001b6a`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001b5b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001b5b`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001b64`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001b64`

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
0x180001b50  push    rbx
0x180001b52  sub     rsp, 20h
0x180001b56  mov     rbx, rcx
0x180001b59  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001b5b  call    cs:__imp_SetUnhandledExceptionFilter
0x180001b61  mov     rcx, rbx; ExceptionInfo
0x180001b64  call    cs:__imp_UnhandledExceptionFilter
0x180001b6a  call    cs:__imp_GetCurrentProcess
0x180001b70  mov     rcx, rax
0x180001b73  mov     edx, 0C0000409h
0x180001b78  add     rsp, 20h
0x180001b7c  pop     rbx
0x180001b7d  jmp     cs:__imp_TerminateProcess
```
