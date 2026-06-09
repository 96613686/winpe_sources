# __raise_securityfailure

- ea: `0x180002240`
- end: `0x180002274`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002280`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002254`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002254`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000224b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000224b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000225a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000225a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000226d`

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
0x180002240  push    rbx
0x180002242  sub     rsp, 20h
0x180002246  mov     rbx, rcx
0x180002249  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000224b  call    cs:__imp_SetUnhandledExceptionFilter
0x180002251  mov     rcx, rbx; ExceptionInfo
0x180002254  call    cs:__imp_UnhandledExceptionFilter
0x18000225a  call    cs:__imp_GetCurrentProcess
0x180002260  mov     rcx, rax
0x180002263  mov     edx, 0C0000409h
0x180002268  add     rsp, 20h
0x18000226c  pop     rbx
0x18000226d  jmp     cs:__imp_TerminateProcess
```
