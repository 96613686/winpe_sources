# __report_securityfailureEx

- ea: `0x180032558`
- end: `0x180032668`
- name: `__report_securityfailureEx`
- size: `272`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180032390`
- `0x180032558`
- `0x180032668`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x18003256e`
- `KERNEL32!IsProcessorFeaturePresent` at `0x18003256e`

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
  capture_current_context_0(&ContextRecord);
  ContextRecord.Rip = retaddr;
  ContextRecord.Rsp = (DWORD64)&v5;
  qword_180079150 = retaddr;
  dword_180079140 = -1073740791;
  dword_180079144 = 1;
  if ( v6 && !v7 )
    v6 = 0;
  if ( v6 > 0xE )
    --v6;
  dword_180079158 = v6 + 1;
  qword_180079160[0] = v5;
  for ( i = 0; i < v6; ++i )
    qword_180079160[i + 1] = *(_QWORD *)(v7 + 8LL * i);
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180032558  mov     [rsp+arg_10], r8
0x18003255d  mov     [rsp+arg_8], edx
0x180032561  mov     [rsp+arg_0], ecx
0x180032565  sub     rsp, 38h
0x180032569  mov     ecx, 17h; ProcessorFeature
0x18003256e  call    cs:__imp_IsProcessorFeaturePresent
0x180032574  test    eax, eax
0x180032576  jz      short loc_180032580
0x180032578  mov     eax, [rsp+38h+arg_0]
0x18003257c  mov     ecx, eax
0x18003257e  int     29h; Win8: RtlFailFast(ecx)
0x180032580  lea     rcx, ContextRecord; ContextRecord
0x180032587  call    capture_current_context_0
0x18003258c  mov     rax, [rsp+38h]
0x180032591  mov     cs:ContextRecord.Rip, rax
0x180032598  lea     rax, [rsp+38h]
0x18003259d  add     rax, 8
0x1800325a1  mov     cs:ContextRecord.Rsp, rax
0x1800325a8  mov     rax, cs:ContextRecord.Rip
0x1800325af  mov     cs:qword_180079150, rax
0x1800325b6  mov     cs:dword_180079140, 0C0000409h
0x1800325c0  mov     cs:dword_180079144, 1
0x1800325ca  cmp     [rsp+38h+arg_8], 0
0x1800325cf  jbe     short loc_1800325E1
0x1800325d1  cmp     [rsp+38h+arg_10], 0
0x1800325d7  jnz     short loc_1800325E1
0x1800325d9  mov     [rsp+38h+arg_8], 0
0x1800325e1  cmp     [rsp+38h+arg_8], 0Eh
0x1800325e6  jbe     short loc_1800325F2
0x1800325e8  mov     eax, [rsp+38h+arg_8]
0x1800325ec  dec     eax
0x1800325ee  mov     [rsp+38h+arg_8], eax
0x1800325f2  mov     eax, [rsp+38h+arg_8]
0x1800325f6  inc     eax
0x1800325f8  mov     cs:dword_180079158, eax
0x1800325fe  mov     eax, 8
0x180032603  imul    rax, 0
0x180032607  lea     rcx, qword_180079160
0x18003260e  mov     edx, [rsp+38h+arg_0]
0x180032612  mov     [rcx+rax], rdx
0x180032616  mov     [rsp+38h+var_18], 0
0x18003261e  jmp     short loc_18003262A
0x180032620  mov     eax, [rsp+38h+var_18]
0x180032624  inc     eax
0x180032626  mov     [rsp+38h+var_18], eax
0x18003262a  mov     eax, [rsp+38h+arg_8]
0x18003262e  cmp     [rsp+38h+var_18], eax
0x180032632  jnb     short loc_180032656
0x180032634  mov     eax, [rsp+38h+var_18]
0x180032638  mov     ecx, [rsp+38h+var_18]
0x18003263c  inc     ecx
0x18003263e  mov     ecx, ecx
0x180032640  lea     rdx, qword_180079160
0x180032647  mov     r8, [rsp+38h+arg_10]
0x18003264c  mov     rax, [r8+rax*8]
0x180032650  mov     [rdx+rcx*8], rax
0x180032654  jmp     short loc_180032620
0x180032656  lea     rcx, ExceptionInfo; ExceptionInfo
0x18003265d  call    __raise_securityfailure
0x180032662  nop
0x180032663  add     rsp, 38h
0x180032667  retn
```
