# __raise_securityfailure

- ea: `0x18000226c`
- end: `0x1800022a0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800022b0`
- `0x180002458`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002280`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002280`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180002277`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180002277`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180002299`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002286`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002286`

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
0x18000226c  push    rbx
0x18000226e  sub     rsp, 20h
0x180002272  mov     rbx, rcx
0x180002275  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180002277  call    cs:__imp_SetUnhandledExceptionFilter
0x18000227d  mov     rcx, rbx; ExceptionInfo
0x180002280  call    cs:__imp_UnhandledExceptionFilter
0x180002286  call    cs:__imp_GetCurrentProcess
0x18000228c  mov     rcx, rax
0x18000228f  mov     edx, 0C0000409h
0x180002294  add     rsp, 20h
0x180002298  pop     rbx
0x180002299  jmp     cs:__imp_TerminateProcess
```
