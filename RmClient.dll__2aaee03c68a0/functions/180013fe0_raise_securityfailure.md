# __raise_securityfailure

- ea: `0x180013fe0`
- end: `0x180014014`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180014020`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180013ffa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180013ffa`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18001400d`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180013feb`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180013feb`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180013ff4`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180013ff4`

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
0x180013fe0  push    rbx
0x180013fe2  sub     rsp, 20h
0x180013fe6  mov     rbx, rcx
0x180013fe9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180013feb  call    cs:__imp_SetUnhandledExceptionFilter
0x180013ff1  mov     rcx, rbx; ExceptionInfo
0x180013ff4  call    cs:__imp_UnhandledExceptionFilter
0x180013ffa  call    cs:__imp_GetCurrentProcess
0x180014000  mov     rcx, rax
0x180014003  mov     edx, 0C0000409h
0x180014008  add     rsp, 20h
0x18001400c  pop     rbx
0x18001400d  jmp     cs:__imp_TerminateProcess
```
