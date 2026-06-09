# __raise_securityfailure

- ea: `0x1400021dc`
- end: `0x140002210`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140002220`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1400021e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1400021e7`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1400021f0`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1400021f0`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140002209`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400021f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400021f6`

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
0x1400021dc  push    rbx
0x1400021de  sub     rsp, 20h
0x1400021e2  mov     rbx, rcx
0x1400021e5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1400021e7  call    cs:__imp_SetUnhandledExceptionFilter
0x1400021ed  mov     rcx, rbx; ExceptionInfo
0x1400021f0  call    cs:__imp_UnhandledExceptionFilter
0x1400021f6  call    cs:__imp_GetCurrentProcess
0x1400021fc  mov     rcx, rax
0x1400021ff  mov     edx, 0C0000409h
0x140002204  add     rsp, 20h
0x140002208  pop     rbx
0x140002209  jmp     cs:__imp_TerminateProcess
```
