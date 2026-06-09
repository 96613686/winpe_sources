# __raise_securityfailure

- ea: `0x14000188c`
- end: `0x1400018c0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400018d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400018b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400018a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400018a6`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1400018a0`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1400018a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001897`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001897`

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
0x14000188c  push    rbx
0x14000188e  sub     rsp, 20h
0x140001892  mov     rbx, rcx
0x140001895  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140001897  call    cs:__imp_SetUnhandledExceptionFilter
0x14000189d  mov     rcx, rbx; ExceptionInfo
0x1400018a0  call    cs:__imp_UnhandledExceptionFilter
0x1400018a6  call    cs:__imp_GetCurrentProcess
0x1400018ac  mov     rcx, rax
0x1400018af  mov     edx, 0C0000409h
0x1400018b4  add     rsp, 20h
0x1400018b8  pop     rbx
0x1400018b9  jmp     cs:__imp_TerminateProcess
```
