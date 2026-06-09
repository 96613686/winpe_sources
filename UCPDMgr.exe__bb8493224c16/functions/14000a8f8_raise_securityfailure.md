# __raise_securityfailure

- ea: `0x14000a8f8`
- end: `0x14000a92c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000a940`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x14000a925`
- `KERNEL32!GetCurrentProcess` at `0x14000a912`
- `KERNEL32!GetCurrentProcess` at `0x14000a912`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14000a903`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14000a903`
- `KERNEL32!UnhandledExceptionFilter` at `0x14000a90c`
- `KERNEL32!UnhandledExceptionFilter` at `0x14000a90c`

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
0x14000a8f8  push    rbx
0x14000a8fa  sub     rsp, 20h
0x14000a8fe  mov     rbx, rcx
0x14000a901  xor     ecx, ecx; lpTopLevelExceptionFilter
0x14000a903  call    cs:__imp_SetUnhandledExceptionFilter
0x14000a909  mov     rcx, rbx; ExceptionInfo
0x14000a90c  call    cs:__imp_UnhandledExceptionFilter
0x14000a912  call    cs:__imp_GetCurrentProcess
0x14000a918  mov     rcx, rax
0x14000a91b  mov     edx, 0C0000409h
0x14000a920  add     rsp, 20h
0x14000a924  pop     rbx
0x14000a925  jmp     cs:__imp_TerminateProcess
```
