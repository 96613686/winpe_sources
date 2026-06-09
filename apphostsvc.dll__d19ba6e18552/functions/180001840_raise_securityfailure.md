# __raise_securityfailure

- ea: `0x180001840`
- end: `0x180001874`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001880`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001854`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001854`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000184b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000184b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000185a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000185a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000186d`

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
0x180001840  push    rbx
0x180001842  sub     rsp, 20h
0x180001846  mov     rbx, rcx
0x180001849  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000184b  call    cs:__imp_SetUnhandledExceptionFilter
0x180001851  mov     rcx, rbx; ExceptionInfo
0x180001854  call    cs:__imp_UnhandledExceptionFilter
0x18000185a  call    cs:__imp_GetCurrentProcess
0x180001860  mov     rcx, rax
0x180001863  mov     edx, 0C0000409h
0x180001868  add     rsp, 20h
0x18000186c  pop     rbx
0x18000186d  jmp     cs:__imp_TerminateProcess
```
