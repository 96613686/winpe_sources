# __raise_securityfailure

- ea: `0x14005acb0`
- end: `0x14005ace4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14005acf0`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x14005acdd`
- `KERNEL32!GetCurrentProcess` at `0x14005acca`
- `KERNEL32!GetCurrentProcess` at `0x14005acca`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14005acbb`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14005acbb`
- `KERNEL32!UnhandledExceptionFilter` at `0x14005acc4`
- `KERNEL32!UnhandledExceptionFilter` at `0x14005acc4`

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
0x14005acb0  push    rbx
0x14005acb2  sub     rsp, 20h
0x14005acb6  mov     rbx, rcx
0x14005acb9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x14005acbb  call    cs:SetUnhandledExceptionFilter
0x14005acc1  mov     rcx, rbx; ExceptionInfo
0x14005acc4  call    cs:UnhandledExceptionFilter
0x14005acca  call    cs:GetCurrentProcess
0x14005acd0  mov     rcx, rax
0x14005acd3  mov     edx, 0C0000409h
0x14005acd8  add     rsp, 20h
0x14005acdc  pop     rbx
0x14005acdd  jmp     cs:TerminateProcess
```
