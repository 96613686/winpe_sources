# __raise_securityfailure

- ea: `0x14000ad30`
- end: `0x14000ad64`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000ad70`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x14000ad5d`
- `KERNEL32!GetCurrentProcess` at `0x14000ad4a`
- `KERNEL32!GetCurrentProcess` at `0x14000ad4a`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14000ad3b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14000ad3b`
- `KERNEL32!UnhandledExceptionFilter` at `0x14000ad44`
- `KERNEL32!UnhandledExceptionFilter` at `0x14000ad44`

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
0x14000ad30  push    rbx
0x14000ad32  sub     rsp, 20h
0x14000ad36  mov     rbx, rcx
0x14000ad39  xor     ecx, ecx; lpTopLevelExceptionFilter
0x14000ad3b  call    cs:SetUnhandledExceptionFilter
0x14000ad41  mov     rcx, rbx; ExceptionInfo
0x14000ad44  call    cs:UnhandledExceptionFilter
0x14000ad4a  call    cs:GetCurrentProcess
0x14000ad50  mov     rcx, rax
0x14000ad53  mov     edx, 0C0000409h
0x14000ad58  add     rsp, 20h
0x14000ad5c  pop     rbx
0x14000ad5d  jmp     cs:TerminateProcess
```
