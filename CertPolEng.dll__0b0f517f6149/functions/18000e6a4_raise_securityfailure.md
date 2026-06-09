# __raise_securityfailure

- ea: `0x18000e6a4`
- end: `0x18000e6d8`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000e6e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000e6af`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000e6af`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000e6b8`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000e6b8`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000e6d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e6be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e6be`

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
0x18000e6a4  push    rbx
0x18000e6a6  sub     rsp, 20h
0x18000e6aa  mov     rbx, rcx
0x18000e6ad  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000e6af  call    cs:__imp_SetUnhandledExceptionFilter
0x18000e6b5  mov     rcx, rbx; ExceptionInfo
0x18000e6b8  call    cs:__imp_UnhandledExceptionFilter
0x18000e6be  call    cs:__imp_GetCurrentProcess
0x18000e6c4  mov     rcx, rax
0x18000e6c7  mov     edx, 0C0000409h
0x18000e6cc  add     rsp, 20h
0x18000e6d0  pop     rbx
0x18000e6d1  jmp     cs:__imp_TerminateProcess
```
