# __raise_securityfailure

- ea: `0x140006150`
- end: `0x140006184`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140006190`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x14000617d`
- `KERNEL32!UnhandledExceptionFilter` at `0x140006164`
- `KERNEL32!UnhandledExceptionFilter` at `0x140006164`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14000615b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14000615b`
- `KERNEL32!GetCurrentProcess` at `0x14000616a`
- `KERNEL32!GetCurrentProcess` at `0x14000616a`

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
0x140006150  push    rbx
0x140006152  sub     rsp, 20h
0x140006156  mov     rbx, rcx
0x140006159  xor     ecx, ecx; lpTopLevelExceptionFilter
0x14000615b  call    cs:__imp_SetUnhandledExceptionFilter
0x140006161  mov     rcx, rbx; ExceptionInfo
0x140006164  call    cs:__imp_UnhandledExceptionFilter
0x14000616a  call    cs:__imp_GetCurrentProcess
0x140006170  mov     rcx, rax
0x140006173  mov     edx, 0C0000409h
0x140006178  add     rsp, 20h
0x14000617c  pop     rbx
0x14000617d  jmp     cs:__imp_TerminateProcess
```
