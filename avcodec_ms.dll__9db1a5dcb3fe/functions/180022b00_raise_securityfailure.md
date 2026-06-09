# __raise_securityfailure

- ea: `0x180022b00`
- end: `0x180022b34`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180022b40`
- `0x180022c28`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180022b2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022b1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022b1a`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180022b14`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180022b14`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180022b0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180022b0b`

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
0x180022b00  push    rbx
0x180022b02  sub     rsp, 20h
0x180022b06  mov     rbx, rcx
0x180022b09  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180022b0b  call    cs:SetUnhandledExceptionFilter
0x180022b11  mov     rcx, rbx; ExceptionInfo
0x180022b14  call    cs:UnhandledExceptionFilter
0x180022b1a  call    cs:GetCurrentProcess
0x180022b20  mov     rcx, rax
0x180022b23  mov     edx, 0C0000409h
0x180022b28  add     rsp, 20h
0x180022b2c  pop     rbx
0x180022b2d  jmp     cs:TerminateProcess
```
