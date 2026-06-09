# __raise_securityfailure

- ea: `0x14000aa80`
- end: `0x14000aab4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000aac0`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x14000aa9a`
- `KERNEL32!GetCurrentProcess` at `0x14000aa9a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14000aaad`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x14000aa8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x14000aa8b`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x14000aa94`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x14000aa94`

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
0x14000aa80  push    rbx
0x14000aa82  sub     rsp, 20h
0x14000aa86  mov     rbx, rcx
0x14000aa89  xor     ecx, ecx; lpTopLevelExceptionFilter
0x14000aa8b  call    cs:SetUnhandledExceptionFilter
0x14000aa91  mov     rcx, rbx; ExceptionInfo
0x14000aa94  call    cs:UnhandledExceptionFilter
0x14000aa9a  call    cs:GetCurrentProcess
0x14000aaa0  mov     rcx, rax
0x14000aaa3  mov     edx, 0C0000409h
0x14000aaa8  add     rsp, 20h
0x14000aaac  pop     rbx
0x14000aaad  jmp     cs:TerminateProcess
```
