# __raise_securityfailure

- ea: `0x18000180c`
- end: `0x180001840`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001820`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001820`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001817`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001817`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001826`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001826`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001839`

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
0x18000180c  push    rbx
0x18000180e  sub     rsp, 20h
0x180001812  mov     rbx, rcx
0x180001815  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001817  call    cs:__imp_SetUnhandledExceptionFilter
0x18000181d  mov     rcx, rbx; ExceptionInfo
0x180001820  call    cs:__imp_UnhandledExceptionFilter
0x180001826  call    cs:__imp_GetCurrentProcess
0x18000182c  mov     rcx, rax
0x18000182f  mov     edx, 0C0000409h
0x180001834  add     rsp, 20h
0x180001838  pop     rbx
0x180001839  jmp     cs:__imp_TerminateProcess
```
