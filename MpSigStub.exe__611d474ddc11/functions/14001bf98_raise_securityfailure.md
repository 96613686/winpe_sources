# __raise_securityfailure

- ea: `0x14001bf98`
- end: `0x14001bfcc`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14001bfd0`
- `0x14001c0b8`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x14001bfb2`
- `KERNEL32!GetCurrentProcess` at `0x14001bfb2`
- `KERNEL32!UnhandledExceptionFilter` at `0x14001bfac`
- `KERNEL32!UnhandledExceptionFilter` at `0x14001bfac`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14001bfa3`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14001bfa3`
- `KERNEL32!TerminateProcess` at `0x14001bfc5`

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
0x14001bf98  push    rbx
0x14001bf9a  sub     rsp, 20h
0x14001bf9e  mov     rbx, rcx
0x14001bfa1  xor     ecx, ecx; lpTopLevelExceptionFilter
0x14001bfa3  call    cs:SetUnhandledExceptionFilter
0x14001bfa9  mov     rcx, rbx; ExceptionInfo
0x14001bfac  call    cs:UnhandledExceptionFilter
0x14001bfb2  call    cs:GetCurrentProcess
0x14001bfb8  mov     rcx, rax
0x14001bfbb  mov     edx, 0C0000409h
0x14001bfc0  add     rsp, 20h
0x14001bfc4  pop     rbx
0x14001bfc5  jmp     cs:TerminateProcess
```
