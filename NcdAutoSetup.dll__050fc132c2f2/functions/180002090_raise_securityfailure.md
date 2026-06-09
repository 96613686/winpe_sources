# __raise_securityfailure

- ea: `0x180002090`
- end: `0x1800020c4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800020d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800020bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800020aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800020aa`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800020a4`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800020a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000209b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000209b`

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
0x180002090  push    rbx
0x180002092  sub     rsp, 20h
0x180002096  mov     rbx, rcx
0x180002099  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000209b  call    cs:__imp_SetUnhandledExceptionFilter
0x1800020a1  mov     rcx, rbx; ExceptionInfo
0x1800020a4  call    cs:__imp_UnhandledExceptionFilter
0x1800020aa  call    cs:__imp_GetCurrentProcess
0x1800020b0  mov     rcx, rax
0x1800020b3  mov     edx, 0C0000409h
0x1800020b8  add     rsp, 20h
0x1800020bc  pop     rbx
0x1800020bd  jmp     cs:__imp_TerminateProcess
```
