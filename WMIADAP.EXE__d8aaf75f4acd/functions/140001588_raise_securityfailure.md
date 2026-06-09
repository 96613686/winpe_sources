# __raise_securityfailure

- ea: `0x140001588`
- end: `0x1400015bc`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400015d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400015b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400015a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400015a2`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x14000159c`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x14000159c`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001593`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001593`

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
0x140001588  push    rbx
0x14000158a  sub     rsp, 20h
0x14000158e  mov     rbx, rcx
0x140001591  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140001593  call    cs:__imp_SetUnhandledExceptionFilter
0x140001599  mov     rcx, rbx; ExceptionInfo
0x14000159c  call    cs:__imp_UnhandledExceptionFilter
0x1400015a2  call    cs:__imp_GetCurrentProcess
0x1400015a8  mov     rcx, rax
0x1400015ab  mov     edx, 0C0000409h
0x1400015b0  add     rsp, 20h
0x1400015b4  pop     rbx
0x1400015b5  jmp     cs:__imp_TerminateProcess
```
