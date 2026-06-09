# __raise_securityfailure

- ea: `0x1800020f0`
- end: `0x180002124`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002130`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800020fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800020fb`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002104`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002104`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000210a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000210a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000211d`

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
0x1800020f0  push    rbx
0x1800020f2  sub     rsp, 20h
0x1800020f6  mov     rbx, rcx
0x1800020f9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800020fb  call    cs:__imp_SetUnhandledExceptionFilter
0x180002101  mov     rcx, rbx; ExceptionInfo
0x180002104  call    cs:__imp_UnhandledExceptionFilter
0x18000210a  call    cs:__imp_GetCurrentProcess
0x180002110  mov     rcx, rax
0x180002113  mov     edx, 0C0000409h
0x180002118  add     rsp, 20h
0x18000211c  pop     rbx
0x18000211d  jmp     cs:__imp_TerminateProcess
```
