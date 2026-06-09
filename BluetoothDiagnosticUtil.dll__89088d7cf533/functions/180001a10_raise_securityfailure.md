# __raise_securityfailure

- ea: `0x180001a10`
- end: `0x180001a44`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001a50`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180001a3d`
- `KERNEL32!GetCurrentProcess` at `0x180001a2a`
- `KERNEL32!GetCurrentProcess` at `0x180001a2a`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001a1b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180001a1b`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001a24`
- `KERNEL32!UnhandledExceptionFilter` at `0x180001a24`

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
0x180001a10  push    rbx
0x180001a12  sub     rsp, 20h
0x180001a16  mov     rbx, rcx
0x180001a19  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001a1b  call    cs:__imp_SetUnhandledExceptionFilter
0x180001a21  mov     rcx, rbx; ExceptionInfo
0x180001a24  call    cs:__imp_UnhandledExceptionFilter
0x180001a2a  call    cs:__imp_GetCurrentProcess
0x180001a30  mov     rcx, rax
0x180001a33  mov     edx, 0C0000409h
0x180001a38  add     rsp, 20h
0x180001a3c  pop     rbx
0x180001a3d  jmp     cs:__imp_TerminateProcess
```
