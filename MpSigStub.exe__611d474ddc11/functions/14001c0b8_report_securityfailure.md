# __report_securityfailure

- ea: `0x14001c0b8`
- end: `0x14001c154`
- name: `__report_securityfailure`
- size: `156`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001c0a4`

## callees

- `0x14001bf98`
- `0x14001c0b8`
- `0x14001c154`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x14001c0c5`
- `KERNEL32!IsProcessorFeaturePresent` at `0x14001c0c5`

## pseudocode

```c
void __fastcall __noreturn _report_securityfailure(unsigned int a1)
{
  DWORD64 retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v2; // [rsp+30h] [rbp+8h] BYREF

  v2 = a1;
  if ( IsProcessorFeaturePresent(0x17u) )
    __fastfail(v2);
  sub_14001C154(&ContextRecord);
  ContextRecord.Rip = retaddr;
  ContextRecord.Rsp = (DWORD64)&v2;
  qword_1400D72A0 = retaddr;
  dword_1400D7290 = -1073740791;
  dword_1400D7294 = 1;
  dword_1400D72A8 = 1;
  qword_1400D72B0[0] = v2;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x14001c0b8  mov     [rsp+arg_0], ecx
0x14001c0bc  sub     rsp, 28h
0x14001c0c0  mov     ecx, 17h; ProcessorFeature
0x14001c0c5  call    cs:IsProcessorFeaturePresent
0x14001c0cb  test    eax, eax
0x14001c0cd  jz      short loc_14001C0D7
0x14001c0cf  mov     eax, [rsp+28h+arg_0]
0x14001c0d3  mov     ecx, eax
0x14001c0d5  int     29h; Win8: RtlFailFast(ecx)
0x14001c0d7  lea     rcx, ContextRecord; ContextRecord
0x14001c0de  call    sub_14001C154
0x14001c0e3  mov     rax, [rsp+28h]
0x14001c0e8  mov     cs:ContextRecord.Rip, rax
0x14001c0ef  lea     rax, [rsp+28h]
0x14001c0f4  add     rax, 8
0x14001c0f8  mov     cs:ContextRecord.Rsp, rax
0x14001c0ff  mov     rax, cs:ContextRecord.Rip
0x14001c106  mov     cs:qword_1400D72A0, rax
0x14001c10d  mov     cs:dword_1400D7290, 0C0000409h
0x14001c117  mov     cs:dword_1400D7294, 1
0x14001c121  mov     cs:dword_1400D72A8, 1
0x14001c12b  mov     eax, 8
0x14001c130  imul    rax, 0
0x14001c134  lea     rcx, qword_1400D72B0
0x14001c13b  mov     edx, [rsp+28h+arg_0]
0x14001c13f  mov     [rcx+rax], rdx
0x14001c143  lea     rcx, ExceptionInfo; ExceptionInfo
0x14001c14a  call    __raise_securityfailure
0x14001c14f  add     rsp, 28h
0x14001c153  retn
```
