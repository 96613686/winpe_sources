# __raise_securityfailure

- ea: `0x14000198c`
- end: `0x1400019c0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400019c0`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x1400019a0`
- `KERNEL32!UnhandledExceptionFilter` at `0x1400019a0`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140001997`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140001997`
- `KERNEL32!GetCurrentProcess` at `0x1400019a6`
- `KERNEL32!GetCurrentProcess` at `0x1400019a6`
- `KERNEL32!TerminateProcess` at `0x1400019b9`

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
0x14000198c  push    rbx
0x14000198e  sub     rsp, 20h
0x140001992  mov     rbx, rcx
0x140001995  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140001997  call    cs:SetUnhandledExceptionFilter
0x14000199d  mov     rcx, rbx; ExceptionInfo
0x1400019a0  call    cs:UnhandledExceptionFilter
0x1400019a6  call    cs:GetCurrentProcess
0x1400019ac  mov     rcx, rax
0x1400019af  mov     edx, 0C0000409h
0x1400019b4  add     rsp, 20h
0x1400019b8  pop     rbx
0x1400019b9  jmp     cs:TerminateProcess
```
