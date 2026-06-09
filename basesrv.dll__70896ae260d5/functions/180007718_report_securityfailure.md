# __report_securityfailure

- ea: `0x180007718`
- end: `0x18000779d`
- name: `__report_securityfailure`
- size: `133`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800076fc`

## callees

- `0x180007558`
- `0x18000786c`

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
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180007718  mov     [rsp+arg_0], ecx
0x18000771c  sub     rsp, 28h
0x180007720  lea     rcx, ContextRecord; ContextRecord
0x180007727  call    RtlCaptureContext_0
0x18000772c  mov     rax, [rsp+28h]
0x180007731  mov     cs:ContextRecord.Rip, rax
0x180007738  lea     rax, [rsp+28h]
0x18000773d  add     rax, 8
0x180007741  mov     cs:ContextRecord.Rsp, rax
0x180007748  mov     rax, cs:ContextRecord.Rip
0x18000774f  mov     cs:qword_1800130D0, rax
0x180007756  mov     cs:dword_1800130C0, 0C0000409h
0x180007760  mov     cs:dword_1800130C4, 1
0x18000776a  mov     cs:dword_1800130D8, 1
0x180007774  mov     eax, 8
0x180007779  imul    rax, 0
0x18000777d  lea     rcx, qword_1800130E0
0x180007784  mov     edx, [rsp+28h+arg_0]
0x180007788  mov     [rcx+rax], rdx
0x18000778c  lea     rcx, ExceptionInfo
0x180007793  call    __raise_securityfailure
0x180007798  add     rsp, 28h
0x18000779c  retn
```
