# __raise_securityfailure

- ea: `0x180004fe0`
- end: `0x180005014`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180005020`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180004ff4`
- `KERNEL32!UnhandledExceptionFilter` at `0x180004ff4`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180004feb`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180004feb`
- `KERNEL32!GetCurrentProcess` at `0x180004ffa`
- `KERNEL32!GetCurrentProcess` at `0x180004ffa`
- `KERNEL32!TerminateProcess` at `0x18000500d`

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
0x180004fe0  push    rbx
0x180004fe2  sub     rsp, 20h
0x180004fe6  mov     rbx, rcx
0x180004fe9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180004feb  call    cs:__imp_SetUnhandledExceptionFilter
0x180004ff1  mov     rcx, rbx; ExceptionInfo
0x180004ff4  call    cs:__imp_UnhandledExceptionFilter
0x180004ffa  call    cs:__imp_GetCurrentProcess
0x180005000  mov     rcx, rax
0x180005003  mov     edx, 0C0000409h
0x180005008  add     rsp, 20h
0x18000500c  pop     rbx
0x18000500d  jmp     cs:__imp_TerminateProcess
```
