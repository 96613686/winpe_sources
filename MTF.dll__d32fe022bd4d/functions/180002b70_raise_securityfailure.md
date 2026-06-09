# __raise_securityfailure

- ea: `0x180002b70`
- end: `0x180002ba4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002bb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002b84`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002b84`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180002b7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180002b7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002b8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002b8a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180002b9d`

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
0x180002b70  push    rbx
0x180002b72  sub     rsp, 20h
0x180002b76  mov     rbx, rcx
0x180002b79  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180002b7b  call    cs:__imp_SetUnhandledExceptionFilter
0x180002b81  mov     rcx, rbx; ExceptionInfo
0x180002b84  call    cs:__imp_UnhandledExceptionFilter
0x180002b8a  call    cs:__imp_GetCurrentProcess
0x180002b90  mov     rcx, rax
0x180002b93  mov     edx, 0C0000409h
0x180002b98  add     rsp, 20h
0x180002b9c  pop     rbx
0x180002b9d  jmp     cs:__imp_TerminateProcess
```
