# __report_securityfailureEx

- ea: `0x180002d78`
- end: `0x180002e88`
- name: `__report_securityfailureEx`
- size: `272`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002bb0`
- `0x180002d78`
- `0x180002e88`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x180002d8e`
- `KERNEL32!IsProcessorFeaturePresent` at `0x180002d8e`

## pseudocode

```c
void __fastcall __noreturn _report_securityfailureEx(unsigned int a1, unsigned int a2, __int64 a3)
{
  unsigned int i; // [rsp+20h] [rbp-18h]
  DWORD64 retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v5; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v6; // [rsp+48h] [rbp+10h]
  __int64 v7; // [rsp+50h] [rbp+18h]

  v7 = a3;
  v6 = a2;
  v5 = a1;
  if ( IsProcessorFeaturePresent(0x17u) )
    __fastfail(v5);
  capture_current_context(&ContextRecord);
  ContextRecord.Rip = retaddr;
  ContextRecord.Rsp = (DWORD64)&v5;
  qword_18007B2E0 = retaddr;
  dword_18007B2D0 = -1073740791;
  dword_18007B2D4 = 1;
  if ( v6 && !v7 )
    v6 = 0;
  if ( v6 > 0xE )
    --v6;
  dword_18007B2E8 = v6 + 1;
  qword_18007B2F0[0] = v5;
  for ( i = 0; i < v6; ++i )
    qword_18007B2F0[i + 1] = *(_QWORD *)(v7 + 8LL * i);
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180002d78  mov     [rsp+arg_10], r8
0x180002d7d  mov     [rsp+arg_8], edx
0x180002d81  mov     [rsp+arg_0], ecx
0x180002d85  sub     rsp, 38h
0x180002d89  mov     ecx, 17h; ProcessorFeature
0x180002d8e  call    cs:__imp_IsProcessorFeaturePresent
0x180002d94  test    eax, eax
0x180002d96  jz      short loc_180002DA0
0x180002d98  mov     eax, [rsp+38h+arg_0]
0x180002d9c  mov     ecx, eax
0x180002d9e  int     29h; Win8: RtlFailFast(ecx)
0x180002da0  lea     rcx, ContextRecord; ContextRecord
0x180002da7  call    capture_current_context
0x180002dac  mov     rax, [rsp+38h]
0x180002db1  mov     cs:ContextRecord.Rip, rax
0x180002db8  lea     rax, [rsp+38h]
0x180002dbd  add     rax, 8
0x180002dc1  mov     cs:ContextRecord.Rsp, rax
0x180002dc8  mov     rax, cs:ContextRecord.Rip
0x180002dcf  mov     cs:qword_18007B2E0, rax
0x180002dd6  mov     cs:dword_18007B2D0, 0C0000409h
0x180002de0  mov     cs:dword_18007B2D4, 1
0x180002dea  cmp     [rsp+38h+arg_8], 0
0x180002def  jbe     short loc_180002E01
0x180002df1  cmp     [rsp+38h+arg_10], 0
0x180002df7  jnz     short loc_180002E01
0x180002df9  mov     [rsp+38h+arg_8], 0
0x180002e01  cmp     [rsp+38h+arg_8], 0Eh
0x180002e06  jbe     short loc_180002E12
0x180002e08  mov     eax, [rsp+38h+arg_8]
0x180002e0c  dec     eax
0x180002e0e  mov     [rsp+38h+arg_8], eax
0x180002e12  mov     eax, [rsp+38h+arg_8]
0x180002e16  inc     eax
0x180002e18  mov     cs:dword_18007B2E8, eax
0x180002e1e  mov     eax, 8
0x180002e23  imul    rax, 0
0x180002e27  lea     rcx, qword_18007B2F0
0x180002e2e  mov     edx, [rsp+38h+arg_0]
0x180002e32  mov     [rcx+rax], rdx
0x180002e36  mov     [rsp+38h+var_18], 0
0x180002e3e  jmp     short loc_180002E4A
0x180002e40  mov     eax, [rsp+38h+var_18]
0x180002e44  inc     eax
0x180002e46  mov     [rsp+38h+var_18], eax
0x180002e4a  mov     eax, [rsp+38h+arg_8]
0x180002e4e  cmp     [rsp+38h+var_18], eax
0x180002e52  jnb     short loc_180002E76
0x180002e54  mov     eax, [rsp+38h+var_18]
0x180002e58  mov     ecx, [rsp+38h+var_18]
0x180002e5c  inc     ecx
0x180002e5e  mov     ecx, ecx
0x180002e60  lea     rdx, qword_18007B2F0
0x180002e67  mov     r8, [rsp+38h+arg_10]
0x180002e6c  mov     rax, [r8+rax*8]
0x180002e70  mov     [rdx+rcx*8], rax
0x180002e74  jmp     short loc_180002E40
0x180002e76  lea     rcx, ExceptionInfo; ExceptionInfo
0x180002e7d  call    __raise_securityfailure
0x180002e82  nop
0x180002e83  add     rsp, 38h
0x180002e87  retn
```
