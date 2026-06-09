# __raise_securityfailure

- ea: `0x14000236c`
- end: `0x1400023a0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400023b0`
- `0x140002558`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140002377`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140002377`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140002380`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140002380`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140002399`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140002386`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140002386`

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
0x14000236c  push    rbx
0x14000236e  sub     rsp, 20h
0x140002372  mov     rbx, rcx
0x140002375  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140002377  call    cs:SetUnhandledExceptionFilter
0x14000237d  mov     rcx, rbx; ExceptionInfo
0x140002380  call    cs:UnhandledExceptionFilter
0x140002386  call    cs:GetCurrentProcess
0x14000238c  mov     rcx, rax
0x14000238f  mov     edx, 0C0000409h
0x140002394  add     rsp, 20h
0x140002398  pop     rbx
0x140002399  jmp     cs:TerminateProcess
```
