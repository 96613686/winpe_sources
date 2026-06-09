# __raise_securityfailure

- ea: `0x180008b74`
- end: `0x180008ba8`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180008bb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180008b7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180008b7f`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180008b88`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180008b88`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180008ba1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008b8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008b8e`

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
0x180008b74  push    rbx
0x180008b76  sub     rsp, 20h
0x180008b7a  mov     rbx, rcx
0x180008b7d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180008b7f  call    cs:__imp_SetUnhandledExceptionFilter
0x180008b85  mov     rcx, rbx; ExceptionInfo
0x180008b88  call    cs:__imp_UnhandledExceptionFilter
0x180008b8e  call    cs:__imp_GetCurrentProcess
0x180008b94  mov     rcx, rax
0x180008b97  mov     edx, 0C0000409h
0x180008b9c  add     rsp, 20h
0x180008ba0  pop     rbx
0x180008ba1  jmp     cs:__imp_TerminateProcess
```
