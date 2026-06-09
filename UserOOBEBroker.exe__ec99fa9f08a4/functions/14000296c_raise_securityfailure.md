# __raise_securityfailure

- ea: `0x14000296c`
- end: `0x1400029a0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400029b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140002999`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140002986`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140002986`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140002977`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140002977`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140002980`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140002980`

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
0x14000296c  push    rbx
0x14000296e  sub     rsp, 20h
0x140002972  mov     rbx, rcx
0x140002975  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140002977  call    cs:__imp_SetUnhandledExceptionFilter
0x14000297d  mov     rcx, rbx; ExceptionInfo
0x140002980  call    cs:__imp_UnhandledExceptionFilter
0x140002986  call    cs:__imp_GetCurrentProcess
0x14000298c  mov     rcx, rax
0x14000298f  mov     edx, 0C0000409h
0x140002994  add     rsp, 20h
0x140002998  pop     rbx
0x140002999  jmp     cs:__imp_TerminateProcess
```
