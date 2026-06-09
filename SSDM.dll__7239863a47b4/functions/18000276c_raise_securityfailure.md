# __raise_securityfailure

- ea: `0x18000276c`
- end: `0x1800027a0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800027b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002786`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002786`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180002799`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002780`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002780`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180002777`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180002777`

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
0x18000276c  push    rbx
0x18000276e  sub     rsp, 20h
0x180002772  mov     rbx, rcx
0x180002775  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180002777  call    cs:__imp_SetUnhandledExceptionFilter
0x18000277d  mov     rcx, rbx; ExceptionInfo
0x180002780  call    cs:__imp_UnhandledExceptionFilter
0x180002786  call    cs:__imp_GetCurrentProcess
0x18000278c  mov     rcx, rax
0x18000278f  mov     edx, 0C0000409h
0x180002794  add     rsp, 20h
0x180002798  pop     rbx
0x180002799  jmp     cs:__imp_TerminateProcess
```
