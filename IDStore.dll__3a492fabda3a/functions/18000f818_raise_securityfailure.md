# __raise_securityfailure

- ea: `0x18000f818`
- end: `0x18000f84c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000f860`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f832`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f832`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000f845`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000f82c`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000f82c`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000f823`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000f823`

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
0x18000f818  push    rbx
0x18000f81a  sub     rsp, 20h
0x18000f81e  mov     rbx, rcx
0x18000f821  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000f823  call    cs:__imp_SetUnhandledExceptionFilter
0x18000f829  mov     rcx, rbx; ExceptionInfo
0x18000f82c  call    cs:__imp_UnhandledExceptionFilter
0x18000f832  call    cs:__imp_GetCurrentProcess
0x18000f838  mov     rcx, rax
0x18000f83b  mov     edx, 0C0000409h
0x18000f840  add     rsp, 20h
0x18000f844  pop     rbx
0x18000f845  jmp     cs:__imp_TerminateProcess
```
