# __raise_securityfailure

- ea: `0x180001f18`
- end: `0x180001f4c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001f23`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001f23`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001f2c`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001f2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001f32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001f32`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001f45`

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
0x180001f18  push    rbx
0x180001f1a  sub     rsp, 20h
0x180001f1e  mov     rbx, rcx
0x180001f21  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001f23  call    cs:__imp_SetUnhandledExceptionFilter
0x180001f29  mov     rcx, rbx; ExceptionInfo
0x180001f2c  call    cs:__imp_UnhandledExceptionFilter
0x180001f32  call    cs:__imp_GetCurrentProcess
0x180001f38  mov     rcx, rax
0x180001f3b  mov     edx, 0C0000409h
0x180001f40  add     rsp, 20h
0x180001f44  pop     rbx
0x180001f45  jmp     cs:__imp_TerminateProcess
```
