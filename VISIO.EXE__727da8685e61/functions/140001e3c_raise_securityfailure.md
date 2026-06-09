# __raise_securityfailure

- ea: `0x140001e3c`
- end: `0x140001e70`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001e80`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x140001e56`
- `KERNEL32!GetCurrentProcess` at `0x140001e56`
- `KERNEL32!UnhandledExceptionFilter` at `0x140001e50`
- `KERNEL32!UnhandledExceptionFilter` at `0x140001e50`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140001e47`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140001e47`
- `KERNEL32!TerminateProcess` at `0x140001e69`

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
0x140001e3c  push    rbx
0x140001e3e  sub     rsp, 20h
0x140001e42  mov     rbx, rcx
0x140001e45  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140001e47  call    cs:SetUnhandledExceptionFilter
0x140001e4d  mov     rcx, rbx; ExceptionInfo
0x140001e50  call    cs:UnhandledExceptionFilter
0x140001e56  call    cs:GetCurrentProcess
0x140001e5c  mov     rcx, rax
0x140001e5f  mov     edx, 0C0000409h
0x140001e64  add     rsp, 20h
0x140001e68  pop     rbx
0x140001e69  jmp     cs:TerminateProcess
```
