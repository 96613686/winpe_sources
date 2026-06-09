# __raise_securityfailure

- ea: `0x1800026e8`
- end: `0x18000271c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002730`
- `0x1800028d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800026f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800026f3`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800026fc`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800026fc`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180002715`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002702`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002702`

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
0x1800026e8  push    rbx
0x1800026ea  sub     rsp, 20h
0x1800026ee  mov     rbx, rcx
0x1800026f1  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800026f3  call    cs:__imp_SetUnhandledExceptionFilter
0x1800026f9  mov     rcx, rbx; ExceptionInfo
0x1800026fc  call    cs:__imp_UnhandledExceptionFilter
0x180002702  call    cs:__imp_GetCurrentProcess
0x180002708  mov     rcx, rax
0x18000270b  mov     edx, 0C0000409h
0x180002710  add     rsp, 20h
0x180002714  pop     rbx
0x180002715  jmp     cs:__imp_TerminateProcess
```
