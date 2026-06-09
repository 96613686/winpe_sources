# __raise_securityfailure

- ea: `0x180001f48`
- end: `0x180001f7c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001f90`
- `0x180002138`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001f53`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001f53`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001f5c`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001f5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001f62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001f62`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001f75`

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
0x180001f48  push    rbx
0x180001f4a  sub     rsp, 20h
0x180001f4e  mov     rbx, rcx
0x180001f51  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001f53  call    cs:__imp_SetUnhandledExceptionFilter
0x180001f59  mov     rcx, rbx; ExceptionInfo
0x180001f5c  call    cs:__imp_UnhandledExceptionFilter
0x180001f62  call    cs:__imp_GetCurrentProcess
0x180001f68  mov     rcx, rax
0x180001f6b  mov     edx, 0C0000409h
0x180001f70  add     rsp, 20h
0x180001f74  pop     rbx
0x180001f75  jmp     cs:__imp_TerminateProcess
```
