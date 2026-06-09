# __raise_securityfailure

- ea: `0x180001ac4`
- end: `0x180001af8`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001b00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001acf`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001acf`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001ad8`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001ad8`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001af1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001ade`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001ade`

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
0x180001ac4  push    rbx
0x180001ac6  sub     rsp, 20h
0x180001aca  mov     rbx, rcx
0x180001acd  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001acf  call    cs:__imp_SetUnhandledExceptionFilter
0x180001ad5  mov     rcx, rbx; ExceptionInfo
0x180001ad8  call    cs:__imp_UnhandledExceptionFilter
0x180001ade  call    cs:__imp_GetCurrentProcess
0x180001ae4  mov     rcx, rax
0x180001ae7  mov     edx, 0C0000409h
0x180001aec  add     rsp, 20h
0x180001af0  pop     rbx
0x180001af1  jmp     cs:__imp_TerminateProcess
```
