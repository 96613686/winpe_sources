# __report_securityfailure

- ea: `0x180007a1c`
- end: `0x180007aa2`
- name: `__report_securityfailure`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007a00`

## callees

- `0x180007858`
- `0x180007b70`

## pseudocode

```c
void __fastcall __noreturn _report_securityfailure(unsigned int a1)
{
  DWORD64 retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v2; // [rsp+30h] [rbp+8h] BYREF

  v2 = a1;
  RtlCaptureContext_0(&ContextRecord);
  ContextRecord.Rip = retaddr;
  ContextRecord.Rsp = (DWORD64)&v2;
  qword_1800130D0 = retaddr;
  dword_1800130C0 = -1073740791;
  dword_1800130C4 = 1;
  dword_1800130D8 = 1;
  qword_1800130E0[0] = v2;
  _raise_securityfailure(&ExceptionInfo);
}

```

## disassembly

```asm
0x180007a1c  mov     [rsp+arg_0], ecx
0x180007a20  sub     rsp, 28h
0x180007a24  lea     rcx, ContextRecord; ContextRecord
0x180007a2b  call    RtlCaptureContext_0
0x180007a30  mov     rax, [rsp+28h]
0x180007a35  mov     cs:ContextRecord.Rip, rax
0x180007a3c  lea     rax, [rsp+28h]
0x180007a41  add     rax, 8
0x180007a45  mov     cs:ContextRecord.Rsp, rax
0x180007a4c  mov     rax, cs:ContextRecord.Rip
0x180007a53  mov     cs:qword_1800130D0, rax
0x180007a5a  mov     cs:dword_1800130C0, 0C0000409h
0x180007a64  mov     cs:dword_1800130C4, 1
0x180007a6e  mov     cs:dword_1800130D8, 1
0x180007a78  mov     eax, 8
0x180007a7d  imul    rax, 0
0x180007a81  lea     rcx, qword_1800130E0
0x180007a88  mov     edx, [rsp+28h+arg_0]
0x180007a8c  mov     [rcx+rax], rdx
0x180007a90  lea     rcx, ExceptionInfo
0x180007a97  call    __raise_securityfailure
0x180007a9c  nop
0x180007a9d  add     rsp, 28h
0x180007aa1  retn
```
