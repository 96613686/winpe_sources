# __raise_securityfailure

- ea: `0x1800060b0`
- end: `0x1800060e4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800060f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800060bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800060bb`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800060c4`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800060c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800060ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800060ca`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800060dd`

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
0x1800060b0  push    rbx
0x1800060b2  sub     rsp, 20h
0x1800060b6  mov     rbx, rcx
0x1800060b9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800060bb  call    cs:__imp_SetUnhandledExceptionFilter
0x1800060c1  mov     rcx, rbx; ExceptionInfo
0x1800060c4  call    cs:__imp_UnhandledExceptionFilter
0x1800060ca  call    cs:__imp_GetCurrentProcess
0x1800060d0  mov     rcx, rax
0x1800060d3  mov     edx, 0C0000409h
0x1800060d8  add     rsp, 20h
0x1800060dc  pop     rbx
0x1800060dd  jmp     cs:__imp_TerminateProcess
```
