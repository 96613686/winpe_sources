# __raise_securityfailure

- ea: `0x180001730`
- end: `0x180001764`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001770`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000174a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000174a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000175d`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001744`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001744`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000173b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000173b`

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
0x180001730  push    rbx
0x180001732  sub     rsp, 20h
0x180001736  mov     rbx, rcx
0x180001739  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000173b  call    cs:__imp_SetUnhandledExceptionFilter
0x180001741  mov     rcx, rbx; ExceptionInfo
0x180001744  call    cs:__imp_UnhandledExceptionFilter
0x18000174a  call    cs:__imp_GetCurrentProcess
0x180001750  mov     rcx, rax
0x180001753  mov     edx, 0C0000409h
0x180001758  add     rsp, 20h
0x18000175c  pop     rbx
0x18000175d  jmp     cs:__imp_TerminateProcess
```
