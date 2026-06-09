# __report_securityfailure

- ea: `0x18004f0e0`
- end: `0x18004f180`
- name: `__report_securityfailure`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18004f0c8`

## callees

- `0x18004efac`
- `0x18004f0e0`
- `0x18004f180`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x18004f0ed`
- `KERNEL32!IsProcessorFeaturePresent` at `0x18004f0ed`

## pseudocode

```c
void __fastcall __noreturn _report_securityfailure(unsigned int a1)
{
  DWORD64 retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v2; // [rsp+30h] [rbp+8h] BYREF

  v2 = a1;
  if ( IsProcessorFeaturePresent(0x17u) )
    __fastfail(v2);
  capture_current_context(&ContextRecord);
  ContextRecord.Rip = retaddr;
  ContextRecord.Rsp = (DWORD64)&v2;
  qword_1800DCCD0 = retaddr;
  dword_1800DCCC0 = -1073740791;
  dword_1800DCCC4 = 1;
  dword_1800DCCD8 = 1;
  qword_1800DCCE0[0] = v2;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x18004f0e0  mov     [rsp+arg_0], ecx
0x18004f0e4  sub     rsp, 28h
0x18004f0e8  mov     ecx, 17h; ProcessorFeature
0x18004f0ed  call    cs:IsProcessorFeaturePresent
0x18004f0f3  test    eax, eax
0x18004f0f5  jz      short loc_18004F0FF
0x18004f0f7  mov     eax, [rsp+28h+arg_0]
0x18004f0fb  mov     ecx, eax
0x18004f0fd  int     29h; Win8: RtlFailFast(ecx)
0x18004f0ff  lea     rcx, ContextRecord; ContextRecord
0x18004f106  call    capture_current_context
0x18004f10b  mov     rax, [rsp+28h]
0x18004f110  mov     cs:ContextRecord.Rip, rax
0x18004f117  lea     rax, [rsp+28h]
0x18004f11c  add     rax, 8
0x18004f120  mov     cs:ContextRecord.Rsp, rax
0x18004f127  mov     rax, cs:ContextRecord.Rip
0x18004f12e  mov     cs:qword_1800DCCD0, rax
0x18004f135  mov     cs:dword_1800DCCC0, 0C0000409h
0x18004f13f  mov     cs:dword_1800DCCC4, 1
0x18004f149  mov     cs:dword_1800DCCD8, 1
0x18004f153  mov     eax, 8
0x18004f158  imul    rax, 0
0x18004f15c  lea     rcx, qword_1800DCCE0
0x18004f163  mov     edx, [rsp+28h+arg_0]
0x18004f167  mov     [rcx+rax], rdx
0x18004f16b  lea     rcx, ExceptionInfo; ExceptionInfo
0x18004f172  call    __raise_securityfailure
0x18004f177  nop
0x18004f178  jmp     short $+2
0x18004f17a  nop
0x18004f17b  add     rsp, 28h
0x18004f17f  retn
```
