# __raise_securityfailure

- ea: `0x140001b98`
- end: `0x140001bcc`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001be0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001ba3`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001ba3`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140001bac`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140001bac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001bb2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001bb2`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140001bc5`

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
0x140001b98  push    rbx
0x140001b9a  sub     rsp, 20h
0x140001b9e  mov     rbx, rcx
0x140001ba1  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140001ba3  call    cs:__imp_SetUnhandledExceptionFilter
0x140001ba9  mov     rcx, rbx; ExceptionInfo
0x140001bac  call    cs:__imp_UnhandledExceptionFilter
0x140001bb2  call    cs:__imp_GetCurrentProcess
0x140001bb8  mov     rcx, rax
0x140001bbb  mov     edx, 0C0000409h
0x140001bc0  add     rsp, 20h
0x140001bc4  pop     rbx
0x140001bc5  jmp     cs:__imp_TerminateProcess
```
