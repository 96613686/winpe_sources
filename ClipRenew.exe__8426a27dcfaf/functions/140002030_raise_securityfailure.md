# __raise_securityfailure

- ea: `0x140002030`
- end: `0x140002064`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140002070`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140002044`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140002044`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x14000203b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x14000203b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14000205d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000204a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000204a`

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
0x140002030  push    rbx
0x140002032  sub     rsp, 20h
0x140002036  mov     rbx, rcx
0x140002039  xor     ecx, ecx; lpTopLevelExceptionFilter
0x14000203b  call    cs:__imp_SetUnhandledExceptionFilter
0x140002041  mov     rcx, rbx; ExceptionInfo
0x140002044  call    cs:__imp_UnhandledExceptionFilter
0x14000204a  call    cs:__imp_GetCurrentProcess
0x140002050  mov     rcx, rax
0x140002053  mov     edx, 0C0000409h
0x140002058  add     rsp, 20h
0x14000205c  pop     rbx
0x14000205d  jmp     cs:__imp_TerminateProcess
```
