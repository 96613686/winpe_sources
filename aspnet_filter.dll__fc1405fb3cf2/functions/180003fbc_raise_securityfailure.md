# __raise_securityfailure

- ea: `0x180003fbc`
- end: `0x180003ff0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180003ff0`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180003fe9`
- `KERNEL32!GetCurrentProcess` at `0x180003fd6`
- `KERNEL32!GetCurrentProcess` at `0x180003fd6`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180003fc7`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180003fc7`
- `KERNEL32!UnhandledExceptionFilter` at `0x180003fd0`
- `KERNEL32!UnhandledExceptionFilter` at `0x180003fd0`

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
0x180003fbc  push    rbx
0x180003fbe  sub     rsp, 20h
0x180003fc2  mov     rbx, rcx
0x180003fc5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180003fc7  call    cs:__imp_SetUnhandledExceptionFilter
0x180003fcd  mov     rcx, rbx; ExceptionInfo
0x180003fd0  call    cs:__imp_UnhandledExceptionFilter
0x180003fd6  call    cs:__imp_GetCurrentProcess
0x180003fdc  mov     rcx, rax
0x180003fdf  mov     edx, 0C0000409h
0x180003fe4  add     rsp, 20h
0x180003fe8  pop     rbx
0x180003fe9  jmp     cs:__imp_TerminateProcess
```
