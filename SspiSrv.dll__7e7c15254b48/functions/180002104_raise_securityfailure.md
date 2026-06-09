# __raise_securityfailure

- ea: `0x180002104`
- end: `0x180002138`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002140`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000210f`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000210f`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002118`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002118`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000211e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000211e`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180002131`

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
0x180002104  push    rbx
0x180002106  sub     rsp, 20h
0x18000210a  mov     rbx, rcx
0x18000210d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000210f  call    cs:__imp_SetUnhandledExceptionFilter
0x180002115  mov     rcx, rbx; ExceptionInfo
0x180002118  call    cs:__imp_UnhandledExceptionFilter
0x18000211e  call    cs:__imp_GetCurrentProcess
0x180002124  mov     rcx, rax
0x180002127  mov     edx, 0C0000409h
0x18000212c  add     rsp, 20h
0x180002130  pop     rbx
0x180002131  jmp     cs:__imp_TerminateProcess
```
