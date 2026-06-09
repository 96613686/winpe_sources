# __raise_securityfailure

- ea: `0x180028560`
- end: `0x180028594`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800285a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002858d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002857a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002857a`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18002856b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18002856b`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180028574`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180028574`

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
0x180028560  push    rbx
0x180028562  sub     rsp, 20h
0x180028566  mov     rbx, rcx
0x180028569  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18002856b  call    cs:SetUnhandledExceptionFilter
0x180028571  mov     rcx, rbx; ExceptionInfo
0x180028574  call    cs:UnhandledExceptionFilter
0x18002857a  call    cs:GetCurrentProcess
0x180028580  mov     rcx, rax
0x180028583  mov     edx, 0C0000409h
0x180028588  add     rsp, 20h
0x18002858c  pop     rbx
0x18002858d  jmp     cs:TerminateProcess
```
