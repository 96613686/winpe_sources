# __raise_securityfailure

- ea: `0x18000ce1c`
- end: `0x18000ce50`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000ce50`
- `0x18000cf38`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x18000ce36`
- `KERNEL32!GetCurrentProcess` at `0x18000ce36`
- `KERNEL32!UnhandledExceptionFilter` at `0x18000ce30`
- `KERNEL32!UnhandledExceptionFilter` at `0x18000ce30`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000ce27`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000ce27`
- `KERNEL32!TerminateProcess` at `0x18000ce49`

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
0x18000ce1c  push    rbx
0x18000ce1e  sub     rsp, 20h
0x18000ce22  mov     rbx, rcx
0x18000ce25  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000ce27  call    cs:__imp_SetUnhandledExceptionFilter
0x18000ce2d  mov     rcx, rbx; ExceptionInfo
0x18000ce30  call    cs:__imp_UnhandledExceptionFilter
0x18000ce36  call    cs:__imp_GetCurrentProcess
0x18000ce3c  mov     rcx, rax
0x18000ce3f  mov     edx, 0C0000409h
0x18000ce44  add     rsp, 20h
0x18000ce48  pop     rbx
0x18000ce49  jmp     cs:__imp_TerminateProcess
```
