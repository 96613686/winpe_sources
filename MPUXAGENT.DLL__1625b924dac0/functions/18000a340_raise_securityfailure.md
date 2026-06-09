# __raise_securityfailure

- ea: `0x18000a340`
- end: `0x18000a374`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a380`
- `0x18000a468`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x18000a36d`
- `KERNEL32!GetCurrentProcess` at `0x18000a35a`
- `KERNEL32!GetCurrentProcess` at `0x18000a35a`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000a34b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000a34b`
- `KERNEL32!UnhandledExceptionFilter` at `0x18000a354`
- `KERNEL32!UnhandledExceptionFilter` at `0x18000a354`

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
0x18000a340  push    rbx
0x18000a342  sub     rsp, 20h
0x18000a346  mov     rbx, rcx
0x18000a349  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000a34b  call    cs:SetUnhandledExceptionFilter
0x18000a351  mov     rcx, rbx; ExceptionInfo
0x18000a354  call    cs:UnhandledExceptionFilter
0x18000a35a  call    cs:GetCurrentProcess
0x18000a360  mov     rcx, rax
0x18000a363  mov     edx, 0C0000409h
0x18000a368  add     rsp, 20h
0x18000a36c  pop     rbx
0x18000a36d  jmp     cs:TerminateProcess
```
