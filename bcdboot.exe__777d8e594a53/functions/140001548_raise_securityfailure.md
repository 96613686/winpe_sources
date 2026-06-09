# __raise_securityfailure

- ea: `0x140001548`
- end: `0x14000157c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001590`
- `0x140001738`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x14000155c`
- `KERNEL32!UnhandledExceptionFilter` at `0x14000155c`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140001553`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140001553`
- `KERNEL32!TerminateProcess` at `0x140001575`
- `KERNEL32!GetCurrentProcess` at `0x140001562`
- `KERNEL32!GetCurrentProcess` at `0x140001562`

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
0x140001548  push    rbx
0x14000154a  sub     rsp, 20h
0x14000154e  mov     rbx, rcx
0x140001551  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140001553  call    cs:__imp_SetUnhandledExceptionFilter
0x140001559  mov     rcx, rbx; ExceptionInfo
0x14000155c  call    cs:__imp_UnhandledExceptionFilter
0x140001562  call    cs:__imp_GetCurrentProcess
0x140001568  mov     rcx, rax
0x14000156b  mov     edx, 0C0000409h
0x140001570  add     rsp, 20h
0x140001574  pop     rbx
0x140001575  jmp     cs:__imp_TerminateProcess
```
