# __raise_securityfailure

- ea: `0x140001624`
- end: `0x140001658`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001660`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x14000163e`
- `KERNEL32!GetCurrentProcess` at `0x14000163e`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14000162f`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14000162f`
- `KERNEL32!UnhandledExceptionFilter` at `0x140001638`
- `KERNEL32!UnhandledExceptionFilter` at `0x140001638`
- `KERNEL32!TerminateProcess` at `0x140001651`

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
0x140001624  push    rbx
0x140001626  sub     rsp, 20h
0x14000162a  mov     rbx, rcx
0x14000162d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x14000162f  call    cs:__imp_SetUnhandledExceptionFilter
0x140001635  mov     rcx, rbx; ExceptionInfo
0x140001638  call    cs:__imp_UnhandledExceptionFilter
0x14000163e  call    cs:__imp_GetCurrentProcess
0x140001644  mov     rcx, rax
0x140001647  mov     edx, 0C0000409h
0x14000164c  add     rsp, 20h
0x140001650  pop     rbx
0x140001651  jmp     cs:__imp_TerminateProcess
```
