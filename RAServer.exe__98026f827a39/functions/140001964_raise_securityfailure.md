# __raise_securityfailure

- ea: `0x140001964`
- end: `0x140001998`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400019a0`
- `0x140001b48`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x140001991`
- `KERNEL32!GetCurrentProcess` at `0x14000197e`
- `KERNEL32!GetCurrentProcess` at `0x14000197e`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14000196f`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14000196f`
- `KERNEL32!UnhandledExceptionFilter` at `0x140001978`
- `KERNEL32!UnhandledExceptionFilter` at `0x140001978`

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
0x140001964  push    rbx
0x140001966  sub     rsp, 20h
0x14000196a  mov     rbx, rcx
0x14000196d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x14000196f  call    cs:__imp_SetUnhandledExceptionFilter
0x140001975  mov     rcx, rbx; ExceptionInfo
0x140001978  call    cs:__imp_UnhandledExceptionFilter
0x14000197e  call    cs:__imp_GetCurrentProcess
0x140001984  mov     rcx, rax
0x140001987  mov     edx, 0C0000409h
0x14000198c  add     rsp, 20h
0x140001990  pop     rbx
0x140001991  jmp     cs:__imp_TerminateProcess
```
