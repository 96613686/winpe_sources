# __report_securityfailure

- ea: `0x180079038`
- end: `0x1800790d5`
- name: `__report_securityfailure`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180079024`

## callees

- `0x180078f10`
- `0x180079038`
- `0x1800790d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x180079045`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x180079045`

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
  qword_1810B1300 = retaddr;
  dword_1810B12F0 = -1073740791;
  dword_1810B12F4 = 1;
  dword_1810B1308 = 1;
  qword_1810B1310[0] = v2;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180079038  mov     [rsp+arg_0], ecx
0x18007903c  sub     rsp, 28h
0x180079040  mov     ecx, 17h; ProcessorFeature
0x180079045  call    cs:IsProcessorFeaturePresent
0x18007904b  test    eax, eax
0x18007904d  jz      short loc_180079057
0x18007904f  mov     eax, [rsp+28h+arg_0]
0x180079053  mov     ecx, eax
0x180079055  int     29h; Win8: RtlFailFast(ecx)
0x180079057  lea     rcx, ContextRecord; ContextRecord
0x18007905e  call    capture_current_context
0x180079063  mov     rax, [rsp+28h]
0x180079068  mov     cs:ContextRecord.Rip, rax
0x18007906f  lea     rax, [rsp+28h]
0x180079074  add     rax, 8
0x180079078  mov     cs:ContextRecord.Rsp, rax
0x18007907f  mov     rax, cs:ContextRecord.Rip
0x180079086  mov     cs:qword_1810B1300, rax
0x18007908d  mov     cs:dword_1810B12F0, 0C0000409h
0x180079097  mov     cs:dword_1810B12F4, 1
0x1800790a1  mov     cs:dword_1810B1308, 1
0x1800790ab  mov     eax, 8
0x1800790b0  imul    rax, 0
0x1800790b4  lea     rcx, qword_1810B1310
0x1800790bb  mov     edx, [rsp+28h+arg_0]
0x1800790bf  mov     [rcx+rax], rdx
0x1800790c3  lea     rcx, ExceptionInfo; ExceptionInfo
0x1800790ca  call    __raise_securityfailure
0x1800790cf  nop
0x1800790d0  add     rsp, 28h
0x1800790d4  retn
```
