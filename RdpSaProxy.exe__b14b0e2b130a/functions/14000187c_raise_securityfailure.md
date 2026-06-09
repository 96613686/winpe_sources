# __raise_securityfailure

- ea: `0x14000187c`
- end: `0x1400018b0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400018c0`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x140001896`
- `KERNEL32!GetCurrentProcess` at `0x140001896`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400018a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001887`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001887`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140001890`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140001890`

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
0x14000187c  push    rbx
0x14000187e  sub     rsp, 20h
0x140001882  mov     rbx, rcx
0x140001885  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140001887  call    cs:__imp_SetUnhandledExceptionFilter
0x14000188d  mov     rcx, rbx; ExceptionInfo
0x140001890  call    cs:__imp_UnhandledExceptionFilter
0x140001896  call    cs:__imp_GetCurrentProcess
0x14000189c  mov     rcx, rax
0x14000189f  mov     edx, 0C0000409h
0x1400018a4  add     rsp, 20h
0x1400018a8  pop     rbx
0x1400018a9  jmp     cs:__imp_TerminateProcess
```
