# __raise_securityfailure

- ea: `0x18001bef0`
- end: `0x18001bf24`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001bf30`
- `0x18001c018`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18001befb`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18001befb`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18001bf04`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18001bf04`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18001bf1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001bf0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001bf0a`

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
0x18001bef0  push    rbx
0x18001bef2  sub     rsp, 20h
0x18001bef6  mov     rbx, rcx
0x18001bef9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18001befb  call    cs:SetUnhandledExceptionFilter
0x18001bf01  mov     rcx, rbx; ExceptionInfo
0x18001bf04  call    cs:UnhandledExceptionFilter
0x18001bf0a  call    cs:GetCurrentProcess
0x18001bf10  mov     rcx, rax
0x18001bf13  mov     edx, 0C0000409h
0x18001bf18  add     rsp, 20h
0x18001bf1c  pop     rbx
0x18001bf1d  jmp     cs:TerminateProcess
```
