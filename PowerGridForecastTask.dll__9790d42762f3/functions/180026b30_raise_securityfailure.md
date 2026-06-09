# __raise_securityfailure

- ea: `0x180026b30`
- end: `0x180026b64`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180026b70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180026b44`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180026b44`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180026b3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180026b3b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180026b5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180026b4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180026b4a`

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
0x180026b30  push    rbx
0x180026b32  sub     rsp, 20h
0x180026b36  mov     rbx, rcx
0x180026b39  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180026b3b  call    cs:__imp_SetUnhandledExceptionFilter
0x180026b41  mov     rcx, rbx; ExceptionInfo
0x180026b44  call    cs:__imp_UnhandledExceptionFilter
0x180026b4a  call    cs:__imp_GetCurrentProcess
0x180026b50  mov     rcx, rax
0x180026b53  mov     edx, 0C0000409h
0x180026b58  add     rsp, 20h
0x180026b5c  pop     rbx
0x180026b5d  jmp     cs:__imp_TerminateProcess
```
