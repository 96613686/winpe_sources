# __raise_securityfailure

- ea: `0x180001ce8`
- end: `0x180001d1c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001d30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001cf3`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001cf3`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001cfc`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001cfc`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001d15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001d02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001d02`

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
0x180001ce8  push    rbx
0x180001cea  sub     rsp, 20h
0x180001cee  mov     rbx, rcx
0x180001cf1  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001cf3  call    cs:__imp_SetUnhandledExceptionFilter
0x180001cf9  mov     rcx, rbx; ExceptionInfo
0x180001cfc  call    cs:__imp_UnhandledExceptionFilter
0x180001d02  call    cs:__imp_GetCurrentProcess
0x180001d08  mov     rcx, rax
0x180001d0b  mov     edx, 0C0000409h
0x180001d10  add     rsp, 20h
0x180001d14  pop     rbx
0x180001d15  jmp     cs:__imp_TerminateProcess
```
