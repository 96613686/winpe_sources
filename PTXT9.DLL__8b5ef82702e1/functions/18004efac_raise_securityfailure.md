# __raise_securityfailure

- ea: `0x18004efac`
- end: `0x18004efe0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18004eff0`
- `0x18004f0e0`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x18004efd9`
- `KERNEL32!GetCurrentProcess` at `0x18004efc6`
- `KERNEL32!GetCurrentProcess` at `0x18004efc6`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18004efb7`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18004efb7`
- `KERNEL32!UnhandledExceptionFilter` at `0x18004efc0`
- `KERNEL32!UnhandledExceptionFilter` at `0x18004efc0`

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
0x18004efac  push    rbx
0x18004efae  sub     rsp, 20h
0x18004efb2  mov     rbx, rcx
0x18004efb5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18004efb7  call    cs:SetUnhandledExceptionFilter
0x18004efbd  mov     rcx, rbx; ExceptionInfo
0x18004efc0  call    cs:UnhandledExceptionFilter
0x18004efc6  call    cs:GetCurrentProcess
0x18004efcc  mov     rcx, rax
0x18004efcf  mov     edx, 0C0000409h
0x18004efd4  add     rsp, 20h
0x18004efd8  pop     rbx
0x18004efd9  jmp     cs:TerminateProcess
```
