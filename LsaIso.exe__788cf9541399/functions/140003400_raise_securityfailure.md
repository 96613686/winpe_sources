# __raise_securityfailure

- ea: `0x140003400`
- end: `0x140003434`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140003440`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x14000340b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x14000340b`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140003414`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140003414`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000341a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000341a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14000342d`

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
0x140003400  push    rbx
0x140003402  sub     rsp, 20h
0x140003406  mov     rbx, rcx
0x140003409  xor     ecx, ecx; lpTopLevelExceptionFilter
0x14000340b  call    cs:__imp_SetUnhandledExceptionFilter
0x140003411  mov     rcx, rbx; ExceptionInfo
0x140003414  call    cs:__imp_UnhandledExceptionFilter
0x14000341a  call    cs:__imp_GetCurrentProcess
0x140003420  mov     rcx, rax
0x140003423  mov     edx, 0C0000409h
0x140003428  add     rsp, 20h
0x14000342c  pop     rbx
0x14000342d  jmp     cs:__imp_TerminateProcess
```
