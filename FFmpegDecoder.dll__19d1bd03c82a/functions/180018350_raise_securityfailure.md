# __raise_securityfailure

- ea: `0x180018350`
- end: `0x180018384`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180018390`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18001837d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001836a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001836a`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18001835b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18001835b`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180018364`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180018364`

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
0x180018350  push    rbx
0x180018352  sub     rsp, 20h
0x180018356  mov     rbx, rcx
0x180018359  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18001835b  call    cs:SetUnhandledExceptionFilter
0x180018361  mov     rcx, rbx; ExceptionInfo
0x180018364  call    cs:UnhandledExceptionFilter
0x18001836a  call    cs:GetCurrentProcess
0x180018370  mov     rcx, rax
0x180018373  mov     edx, 0C0000409h
0x180018378  add     rsp, 20h
0x18001837c  pop     rbx
0x18001837d  jmp     cs:TerminateProcess
```
