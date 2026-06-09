# __raise_securityfailure

- ea: `0x140001d4c`
- end: `0x140001d80`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001d90`
- `0x140001f38`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001d66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001d66`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140001d79`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001d57`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001d57`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140001d60`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140001d60`

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
0x140001d4c  push    rbx
0x140001d4e  sub     rsp, 20h
0x140001d52  mov     rbx, rcx
0x140001d55  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140001d57  call    cs:__imp_SetUnhandledExceptionFilter
0x140001d5d  mov     rcx, rbx; ExceptionInfo
0x140001d60  call    cs:__imp_UnhandledExceptionFilter
0x140001d66  call    cs:__imp_GetCurrentProcess
0x140001d6c  mov     rcx, rax
0x140001d6f  mov     edx, 0C0000409h
0x140001d74  add     rsp, 20h
0x140001d78  pop     rbx
0x140001d79  jmp     cs:__imp_TerminateProcess
```
