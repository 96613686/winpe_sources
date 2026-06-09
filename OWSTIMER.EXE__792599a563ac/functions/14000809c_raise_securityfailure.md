# __raise_securityfailure

- ea: `0x14000809c`
- end: `0x1400080d0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400080d0`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x1400080b6`
- `KERNEL32!GetCurrentProcess` at `0x1400080b6`
- `KERNEL32!TerminateProcess` at `0x1400080c9`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1400080a7`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1400080a7`
- `KERNEL32!UnhandledExceptionFilter` at `0x1400080b0`
- `KERNEL32!UnhandledExceptionFilter` at `0x1400080b0`

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
0x14000809c  push    rbx
0x14000809e  sub     rsp, 20h
0x1400080a2  mov     rbx, rcx
0x1400080a5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1400080a7  call    cs:SetUnhandledExceptionFilter
0x1400080ad  mov     rcx, rbx; ExceptionInfo
0x1400080b0  call    cs:UnhandledExceptionFilter
0x1400080b6  call    cs:GetCurrentProcess
0x1400080bc  mov     rcx, rax
0x1400080bf  mov     edx, 0C0000409h
0x1400080c4  add     rsp, 20h
0x1400080c8  pop     rbx
0x1400080c9  jmp     cs:TerminateProcess
```
