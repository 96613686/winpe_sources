# __raise_securityfailure

- ea: `0x180002170`
- end: `0x1800021a4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800021b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000217b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000217b`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002184`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002184`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000218a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000218a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000219d`

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
0x180002170  push    rbx
0x180002172  sub     rsp, 20h
0x180002176  mov     rbx, rcx
0x180002179  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000217b  call    cs:__imp_SetUnhandledExceptionFilter
0x180002181  mov     rcx, rbx; ExceptionInfo
0x180002184  call    cs:__imp_UnhandledExceptionFilter
0x18000218a  call    cs:__imp_GetCurrentProcess
0x180002190  mov     rcx, rax
0x180002193  mov     edx, 0C0000409h
0x180002198  add     rsp, 20h
0x18000219c  pop     rbx
0x18000219d  jmp     cs:__imp_TerminateProcess
```
