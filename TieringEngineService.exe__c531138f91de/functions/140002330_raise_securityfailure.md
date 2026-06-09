# __raise_securityfailure

- ea: `0x140002330`
- end: `0x140002364`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140002370`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140002344`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140002344`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x14000233b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x14000233b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14000235d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000234a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000234a`

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
0x140002330  push    rbx
0x140002332  sub     rsp, 20h
0x140002336  mov     rbx, rcx
0x140002339  xor     ecx, ecx; lpTopLevelExceptionFilter
0x14000233b  call    cs:__imp_SetUnhandledExceptionFilter
0x140002341  mov     rcx, rbx; ExceptionInfo
0x140002344  call    cs:__imp_UnhandledExceptionFilter
0x14000234a  call    cs:__imp_GetCurrentProcess
0x140002350  mov     rcx, rax
0x140002353  mov     edx, 0C0000409h
0x140002358  add     rsp, 20h
0x14000235c  pop     rbx
0x14000235d  jmp     cs:__imp_TerminateProcess
```
