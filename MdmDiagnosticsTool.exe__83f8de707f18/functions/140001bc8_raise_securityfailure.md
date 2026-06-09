# __raise_securityfailure

- ea: `0x140001bc8`
- end: `0x140001bfc`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001c10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001bd3`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001bd3`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140001bdc`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140001bdc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001be2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001be2`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140001bf5`

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
0x140001bc8  push    rbx
0x140001bca  sub     rsp, 20h
0x140001bce  mov     rbx, rcx
0x140001bd1  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140001bd3  call    cs:__imp_SetUnhandledExceptionFilter
0x140001bd9  mov     rcx, rbx; ExceptionInfo
0x140001bdc  call    cs:__imp_UnhandledExceptionFilter
0x140001be2  call    cs:__imp_GetCurrentProcess
0x140001be8  mov     rcx, rax
0x140001beb  mov     edx, 0C0000409h
0x140001bf0  add     rsp, 20h
0x140001bf4  pop     rbx
0x140001bf5  jmp     cs:__imp_TerminateProcess
```
