# __raise_securityfailure

- ea: `0x140001ecc`
- end: `0x140001f00`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001f10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140001ee0`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140001ee0`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001ed7`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001ed7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001ee6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001ee6`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140001ef9`

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
0x140001ecc  push    rbx
0x140001ece  sub     rsp, 20h
0x140001ed2  mov     rbx, rcx
0x140001ed5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140001ed7  call    cs:__imp_SetUnhandledExceptionFilter
0x140001edd  mov     rcx, rbx; ExceptionInfo
0x140001ee0  call    cs:__imp_UnhandledExceptionFilter
0x140001ee6  call    cs:__imp_GetCurrentProcess
0x140001eec  mov     rcx, rax
0x140001eef  mov     edx, 0C0000409h
0x140001ef4  add     rsp, 20h
0x140001ef8  pop     rbx
0x140001ef9  jmp     cs:__imp_TerminateProcess
```
