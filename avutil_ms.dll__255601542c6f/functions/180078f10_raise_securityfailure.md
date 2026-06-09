# __raise_securityfailure

- ea: `0x180078f10`
- end: `0x180078f44`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180078f50`
- `0x180079038`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180078f3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180078f2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180078f2a`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180078f24`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180078f24`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180078f1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180078f1b`

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
0x180078f10  push    rbx
0x180078f12  sub     rsp, 20h
0x180078f16  mov     rbx, rcx
0x180078f19  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180078f1b  call    cs:SetUnhandledExceptionFilter
0x180078f21  mov     rcx, rbx; ExceptionInfo
0x180078f24  call    cs:UnhandledExceptionFilter
0x180078f2a  call    cs:GetCurrentProcess
0x180078f30  mov     rcx, rax
0x180078f33  mov     edx, 0C0000409h
0x180078f38  add     rsp, 20h
0x180078f3c  pop     rbx
0x180078f3d  jmp     cs:TerminateProcess
```
