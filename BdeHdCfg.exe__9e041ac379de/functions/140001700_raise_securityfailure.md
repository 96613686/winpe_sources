# __raise_securityfailure

- ea: `0x140001700`
- end: `0x140001734`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001740`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000171a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000171a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14000172d`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x14000170b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x14000170b`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140001714`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140001714`

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
0x140001700  push    rbx
0x140001702  sub     rsp, 20h
0x140001706  mov     rbx, rcx
0x140001709  xor     ecx, ecx; lpTopLevelExceptionFilter
0x14000170b  call    cs:__imp_SetUnhandledExceptionFilter
0x140001711  mov     rcx, rbx; ExceptionInfo
0x140001714  call    cs:__imp_UnhandledExceptionFilter
0x14000171a  call    cs:__imp_GetCurrentProcess
0x140001720  mov     rcx, rax
0x140001723  mov     edx, 0C0000409h
0x140001728  add     rsp, 20h
0x14000172c  pop     rbx
0x14000172d  jmp     cs:__imp_TerminateProcess
```
