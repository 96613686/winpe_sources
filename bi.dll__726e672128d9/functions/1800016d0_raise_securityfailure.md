# __raise_securityfailure

- ea: `0x1800016d0`
- end: `0x180001704`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001710`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800016db`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800016db`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800016e4`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800016e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800016ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800016ea`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800016fd`

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
0x1800016d0  push    rbx
0x1800016d2  sub     rsp, 20h
0x1800016d6  mov     rbx, rcx
0x1800016d9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800016db  call    cs:__imp_SetUnhandledExceptionFilter
0x1800016e1  mov     rcx, rbx; ExceptionInfo
0x1800016e4  call    cs:__imp_UnhandledExceptionFilter
0x1800016ea  call    cs:__imp_GetCurrentProcess
0x1800016f0  mov     rcx, rax
0x1800016f3  mov     edx, 0C0000409h
0x1800016f8  add     rsp, 20h
0x1800016fc  pop     rbx
0x1800016fd  jmp     cs:__imp_TerminateProcess
```
