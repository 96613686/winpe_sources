# __raise_securityfailure

- ea: `0x180001980`
- end: `0x1800019b4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800019c0`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x1800019ad`
- `KERNEL32!GetCurrentProcess` at `0x18000199a`
- `KERNEL32!GetCurrentProcess` at `0x18000199a`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000198b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000198b`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001994`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001994`

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
0x180001980  push    rbx
0x180001982  sub     rsp, 20h
0x180001986  mov     rbx, rcx
0x180001989  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000198b  call    cs:__imp_SetUnhandledExceptionFilter
0x180001991  mov     rcx, rbx; ExceptionInfo
0x180001994  call    cs:__imp_UnhandledExceptionFilter
0x18000199a  call    cs:__imp_GetCurrentProcess
0x1800019a0  mov     rcx, rax
0x1800019a3  mov     edx, 0C0000409h
0x1800019a8  add     rsp, 20h
0x1800019ac  pop     rbx
0x1800019ad  jmp     cs:__imp_TerminateProcess
```
