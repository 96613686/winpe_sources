# __raise_securityfailure

- ea: `0x180007acc`
- end: `0x180007b00`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180007b00`
- `0x180007be8`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180007ae0`
- `KERNEL32!UnhandledExceptionFilter` at `0x180007ae0`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180007ad7`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180007ad7`
- `KERNEL32!GetCurrentProcess` at `0x180007ae6`
- `KERNEL32!GetCurrentProcess` at `0x180007ae6`
- `KERNEL32!TerminateProcess` at `0x180007af9`

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
0x180007acc  push    rbx
0x180007ace  sub     rsp, 20h
0x180007ad2  mov     rbx, rcx
0x180007ad5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180007ad7  call    cs:__imp_SetUnhandledExceptionFilter
0x180007add  mov     rcx, rbx; ExceptionInfo
0x180007ae0  call    cs:__imp_UnhandledExceptionFilter
0x180007ae6  call    cs:__imp_GetCurrentProcess
0x180007aec  mov     rcx, rax
0x180007aef  mov     edx, 0C0000409h
0x180007af4  add     rsp, 20h
0x180007af8  pop     rbx
0x180007af9  jmp     cs:__imp_TerminateProcess
```
