# __raise_securityfailure

- ea: `0x18007af1c`
- end: `0x18007af50`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18007af60`
- `0x18007b050`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x18007af30`
- `KERNEL32!UnhandledExceptionFilter` at `0x18007af30`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18007af27`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18007af27`
- `KERNEL32!TerminateProcess` at `0x18007af49`
- `KERNEL32!GetCurrentProcess` at `0x18007af36`
- `KERNEL32!GetCurrentProcess` at `0x18007af36`

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
0x18007af1c  push    rbx
0x18007af1e  sub     rsp, 20h
0x18007af22  mov     rbx, rcx
0x18007af25  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18007af27  call    cs:SetUnhandledExceptionFilter
0x18007af2d  mov     rcx, rbx; ExceptionInfo
0x18007af30  call    cs:UnhandledExceptionFilter
0x18007af36  call    cs:GetCurrentProcess
0x18007af3c  mov     rcx, rax
0x18007af3f  mov     edx, 0C0000409h
0x18007af44  add     rsp, 20h
0x18007af48  pop     rbx
0x18007af49  jmp     cs:TerminateProcess
```
