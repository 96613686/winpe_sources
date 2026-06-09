# __raise_securityfailure

- ea: `0x180001ff0`
- end: `0x180002024`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002030`
- `0x1800021d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001ffb`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001ffb`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002004`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002004`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000200a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000200a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000201d`

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
0x180001ff0  push    rbx
0x180001ff2  sub     rsp, 20h
0x180001ff6  mov     rbx, rcx
0x180001ff9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001ffb  call    cs:__imp_SetUnhandledExceptionFilter
0x180002001  mov     rcx, rbx; ExceptionInfo
0x180002004  call    cs:__imp_UnhandledExceptionFilter
0x18000200a  call    cs:__imp_GetCurrentProcess
0x180002010  mov     rcx, rax
0x180002013  mov     edx, 0C0000409h
0x180002018  add     rsp, 20h
0x18000201c  pop     rbx
0x18000201d  jmp     cs:__imp_TerminateProcess
```
