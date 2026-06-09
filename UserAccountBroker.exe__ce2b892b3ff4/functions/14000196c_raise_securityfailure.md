# __raise_securityfailure

- ea: `0x14000196c`
- end: `0x1400019a0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400019b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001986`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001986`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140001999`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140001980`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140001980`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001977`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001977`

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
0x14000196c  push    rbx
0x14000196e  sub     rsp, 20h
0x140001972  mov     rbx, rcx
0x140001975  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140001977  call    cs:__imp_SetUnhandledExceptionFilter
0x14000197d  mov     rcx, rbx; ExceptionInfo
0x140001980  call    cs:__imp_UnhandledExceptionFilter
0x140001986  call    cs:__imp_GetCurrentProcess
0x14000198c  mov     rcx, rax
0x14000198f  mov     edx, 0C0000409h
0x140001994  add     rsp, 20h
0x140001998  pop     rbx
0x140001999  jmp     cs:__imp_TerminateProcess
```
