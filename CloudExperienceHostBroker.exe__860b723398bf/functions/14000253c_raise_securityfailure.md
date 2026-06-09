# __raise_securityfailure

- ea: `0x14000253c`
- end: `0x140002570`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140002580`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140002547`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140002547`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140002550`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140002550`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140002556`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140002556`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140002569`

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
0x14000253c  push    rbx
0x14000253e  sub     rsp, 20h
0x140002542  mov     rbx, rcx
0x140002545  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140002547  call    cs:__imp_SetUnhandledExceptionFilter
0x14000254d  mov     rcx, rbx; ExceptionInfo
0x140002550  call    cs:__imp_UnhandledExceptionFilter
0x140002556  call    cs:__imp_GetCurrentProcess
0x14000255c  mov     rcx, rax
0x14000255f  mov     edx, 0C0000409h
0x140002564  add     rsp, 20h
0x140002568  pop     rbx
0x140002569  jmp     cs:__imp_TerminateProcess
```
