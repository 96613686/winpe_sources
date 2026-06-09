# __raise_securityfailure

- ea: `0x180001ec8`
- end: `0x180001efc`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001f10`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180001ee2`
- `KERNEL32!GetCurrentProcess` at `0x180001ee2`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001edc`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001edc`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001ed3`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001ed3`
- `KERNEL32!TerminateProcess` at `0x180001ef5`

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
0x180001ec8  push    rbx
0x180001eca  sub     rsp, 20h
0x180001ece  mov     rbx, rcx
0x180001ed1  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001ed3  call    cs:__imp_SetUnhandledExceptionFilter
0x180001ed9  mov     rcx, rbx; ExceptionInfo
0x180001edc  call    cs:__imp_UnhandledExceptionFilter
0x180001ee2  call    cs:__imp_GetCurrentProcess
0x180001ee8  mov     rcx, rax
0x180001eeb  mov     edx, 0C0000409h
0x180001ef0  add     rsp, 20h
0x180001ef4  pop     rbx
0x180001ef5  jmp     cs:__imp_TerminateProcess
```
