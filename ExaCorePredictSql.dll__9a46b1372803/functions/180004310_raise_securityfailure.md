# __raise_securityfailure

- ea: `0x180004310`
- end: `0x180004344`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180004350`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180004324`
- `KERNEL32!UnhandledExceptionFilter` at `0x180004324`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000431b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000431b`
- `KERNEL32!GetCurrentProcess` at `0x18000432a`
- `KERNEL32!GetCurrentProcess` at `0x18000432a`
- `KERNEL32!TerminateProcess` at `0x18000433d`

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
0x180004310  push    rbx
0x180004312  sub     rsp, 20h
0x180004316  mov     rbx, rcx
0x180004319  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000431b  call    cs:__imp_SetUnhandledExceptionFilter
0x180004321  mov     rcx, rbx; ExceptionInfo
0x180004324  call    cs:__imp_UnhandledExceptionFilter
0x18000432a  call    cs:__imp_GetCurrentProcess
0x180004330  mov     rcx, rax
0x180004333  mov     edx, 0C0000409h
0x180004338  add     rsp, 20h
0x18000433c  pop     rbx
0x18000433d  jmp     cs:__imp_TerminateProcess
```
