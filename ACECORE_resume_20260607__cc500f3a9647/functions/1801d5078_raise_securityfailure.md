# __raise_securityfailure

- ea: `0x1801d5078`
- end: `0x1801d50ac`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1801d50b0`
- `0x1801d51a0`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x1801d508c`
- `KERNEL32!UnhandledExceptionFilter` at `0x1801d508c`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1801d5083`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1801d5083`
- `KERNEL32!GetCurrentProcess` at `0x1801d5092`
- `KERNEL32!GetCurrentProcess` at `0x1801d5092`
- `KERNEL32!TerminateProcess` at `0x1801d50a5`

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
0x1801d5078  push    rbx
0x1801d507a  sub     rsp, 20h
0x1801d507e  mov     rbx, rcx
0x1801d5081  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1801d5083  call    cs:SetUnhandledExceptionFilter
0x1801d5089  mov     rcx, rbx; ExceptionInfo
0x1801d508c  call    cs:UnhandledExceptionFilter
0x1801d5092  call    cs:GetCurrentProcess
0x1801d5098  mov     rcx, rax
0x1801d509b  mov     edx, 0C0000409h
0x1801d50a0  add     rsp, 20h
0x1801d50a4  pop     rbx
0x1801d50a5  jmp     cs:TerminateProcess
```
