# __raise_securityfailure

- ea: `0x180002970`
- end: `0x1800029a4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800029b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002984`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002984`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000297b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000297b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000299d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000298a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000298a`

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
0x180002970  push    rbx
0x180002972  sub     rsp, 20h
0x180002976  mov     rbx, rcx
0x180002979  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000297b  call    cs:__imp_SetUnhandledExceptionFilter
0x180002981  mov     rcx, rbx; ExceptionInfo
0x180002984  call    cs:__imp_UnhandledExceptionFilter
0x18000298a  call    cs:__imp_GetCurrentProcess
0x180002990  mov     rcx, rax
0x180002993  mov     edx, 0C0000409h
0x180002998  add     rsp, 20h
0x18000299c  pop     rbx
0x18000299d  jmp     cs:__imp_TerminateProcess
```
