# __raise_securityfailure

- ea: `0x180004ab4`
- end: `0x180004ae8`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180004af0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004ace`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004ace`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180004ae1`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180004ac8`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180004ac8`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180004abf`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180004abf`

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
0x180004ab4  push    rbx
0x180004ab6  sub     rsp, 20h
0x180004aba  mov     rbx, rcx
0x180004abd  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180004abf  call    cs:__imp_SetUnhandledExceptionFilter
0x180004ac5  mov     rcx, rbx; ExceptionInfo
0x180004ac8  call    cs:__imp_UnhandledExceptionFilter
0x180004ace  call    cs:__imp_GetCurrentProcess
0x180004ad4  mov     rcx, rax
0x180004ad7  mov     edx, 0C0000409h
0x180004adc  add     rsp, 20h
0x180004ae0  pop     rbx
0x180004ae1  jmp     cs:__imp_TerminateProcess
```
