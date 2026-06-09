# __raise_securityfailure

- ea: `0x18000185c`
- end: `0x180001890`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800018a0`
- `0x180001a48`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180001870`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001870`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001867`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001867`
- `KERNEL32!GetCurrentProcess` at `0x180001876`
- `KERNEL32!GetCurrentProcess` at `0x180001876`
- `KERNEL32!TerminateProcess` at `0x180001889`

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
0x18000185c  push    rbx
0x18000185e  sub     rsp, 20h
0x180001862  mov     rbx, rcx
0x180001865  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001867  call    cs:__imp_SetUnhandledExceptionFilter
0x18000186d  mov     rcx, rbx; ExceptionInfo
0x180001870  call    cs:__imp_UnhandledExceptionFilter
0x180001876  call    cs:__imp_GetCurrentProcess
0x18000187c  mov     rcx, rax
0x18000187f  mov     edx, 0C0000409h
0x180001884  add     rsp, 20h
0x180001888  pop     rbx
0x180001889  jmp     cs:__imp_TerminateProcess
```
