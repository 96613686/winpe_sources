# __report_securityfailure

- ea: `0x180007be8`
- end: `0x180007c85`
- name: `__report_securityfailure`
- size: `157`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007bd4`

## callees

- `0x180007acc`
- `0x180007be8`
- `0x180007c88`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x180007bf5`
- `KERNEL32!IsProcessorFeaturePresent` at `0x180007bf5`

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
  qword_18003DC10 = retaddr;
  dword_18003DC00 = -1073740791;
  dword_18003DC04 = 1;
  dword_18003DC18 = 1;
  qword_18003DC20[0] = v2;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180007be8  mov     [rsp+arg_0], ecx
0x180007bec  sub     rsp, 28h
0x180007bf0  mov     ecx, 17h; ProcessorFeature
0x180007bf5  call    cs:__imp_IsProcessorFeaturePresent
0x180007bfb  test    eax, eax
0x180007bfd  jz      short loc_180007C07
0x180007bff  mov     eax, [rsp+28h+arg_0]
0x180007c03  mov     ecx, eax
0x180007c05  int     29h; Win8: RtlFailFast(ecx)
0x180007c07  lea     rcx, ContextRecord; ContextRecord
0x180007c0e  call    capture_current_context
0x180007c13  mov     rax, [rsp+28h]
0x180007c18  mov     cs:ContextRecord.Rip, rax
0x180007c1f  lea     rax, [rsp+28h]
0x180007c24  add     rax, 8
0x180007c28  mov     cs:ContextRecord.Rsp, rax
0x180007c2f  mov     rax, cs:ContextRecord.Rip
0x180007c36  mov     cs:qword_18003DC10, rax
0x180007c3d  mov     cs:dword_18003DC00, 0C0000409h
0x180007c47  mov     cs:dword_18003DC04, 1
0x180007c51  mov     cs:dword_18003DC18, 1
0x180007c5b  mov     eax, 8
0x180007c60  imul    rax, 0
0x180007c64  lea     rcx, qword_18003DC20
0x180007c6b  mov     edx, [rsp+28h+arg_0]
0x180007c6f  mov     [rcx+rax], rdx
0x180007c73  lea     rcx, ExceptionInfo; ExceptionInfo
0x180007c7a  call    __raise_securityfailure
0x180007c7f  nop
0x180007c80  add     rsp, 28h
0x180007c84  retn
```
