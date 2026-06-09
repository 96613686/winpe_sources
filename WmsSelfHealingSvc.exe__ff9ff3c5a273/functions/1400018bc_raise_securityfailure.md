# __raise_securityfailure

- ea: `0x1400018bc`
- end: `0x1400018f0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001900`

## import_xrefs

- `KERNEL32!SetUnhandledExceptionFilter` at `0x1400018c7`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1400018c7`
- `KERNEL32!UnhandledExceptionFilter` at `0x1400018d0`
- `KERNEL32!UnhandledExceptionFilter` at `0x1400018d0`
- `KERNEL32!GetCurrentProcess` at `0x1400018d6`
- `KERNEL32!GetCurrentProcess` at `0x1400018d6`
- `KERNEL32!TerminateProcess` at `0x1400018e9`

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
0x1400018bc  push    rbx
0x1400018be  sub     rsp, 20h
0x1400018c2  mov     rbx, rcx
0x1400018c5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1400018c7  call    cs:__imp_SetUnhandledExceptionFilter
0x1400018cd  mov     rcx, rbx; ExceptionInfo
0x1400018d0  call    cs:__imp_UnhandledExceptionFilter
0x1400018d6  call    cs:__imp_GetCurrentProcess
0x1400018dc  mov     rcx, rax
0x1400018df  mov     edx, 0C0000409h
0x1400018e4  add     rsp, 20h
0x1400018e8  pop     rbx
0x1400018e9  jmp     cs:__imp_TerminateProcess
```
