# __raise_securityfailure

- ea: `0x18000220c`
- end: `0x180002240`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002250`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002220`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002220`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180002217`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180002217`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180002239`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002226`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002226`

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
0x18000220c  push    rbx
0x18000220e  sub     rsp, 20h
0x180002212  mov     rbx, rcx
0x180002215  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180002217  call    cs:__imp_SetUnhandledExceptionFilter
0x18000221d  mov     rcx, rbx; ExceptionInfo
0x180002220  call    cs:__imp_UnhandledExceptionFilter
0x180002226  call    cs:__imp_GetCurrentProcess
0x18000222c  mov     rcx, rax
0x18000222f  mov     edx, 0C0000409h
0x180002234  add     rsp, 20h
0x180002238  pop     rbx
0x180002239  jmp     cs:__imp_TerminateProcess
```
