# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001ff9c`
- end: `0x180020140`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001f60c`

## callees

- `0x18001e8f4`
- `0x18001f6ec`
- `0x18001ff9c`
- `0x180020aa4`
- `0x180032010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  int v7; // edx
  int v8; // r8d
  int v9; // ebx
  int v10; // eax
  __int64 v11; // rcx
  char v12; // dl
  unsigned int v13; // r8d
  __int64 v14; // rcx
  unsigned int v15; // r8d
  __int64 v17; // [rsp+60h] [rbp+20h] BYREF
  __int64 v18; // [rsp+68h] [rbp+28h] BYREF

  v17 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(57048231, 3);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( (v4 & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( v5 == 2 )
      v7 = 64;
    v8 = v7;
  }
  else
  {
    v7 = 64;
    v8 = 64;
  }
  v9 = 1;
  v10 = v8 | v6;
  v11 = v7 | (unsigned int)v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && (unsigned int)v11 >= 0x800 || (v12 = 0, (v11 & 0x40) != 0) )
  {
    v13 = *(_DWORD *)Feature_ValLabTest__descriptor;
    if ( (*(_DWORD *)Feature_ValLabTest__descriptor & 4) == 0 )
    {
      v18 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
                         v11,
                         &v18);
      v13 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_18005FD88,
      0x3667CA2u,
      (v13 >> 10) & 1,
      (v13 >> 11) & 1,
      (__int64)&v17,
      1u,
      0);
    v15 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor & 4) == 0 )
    {
      v18 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
                         v14,
                         &v18);
      v15 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_18005FDE8,
      0x2AF34F8u,
      (v15 >> 10) & 1,
      (v15 >> 11) & 1,
      (__int64)&v17,
      1u,
      0);
    v12 = 1;
  }
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v12 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x18001ff9c  mov     [rsp-18h+arg_10], rbx
0x18001ffa1  mov     [rsp-18h+arg_0], rcx
0x18001ffa6  push    rbp
0x18001ffa7  push    rdi
0x18001ffa8  push    r14
0x18001ffaa  mov     rbp, rsp
0x18001ffad  sub     rsp, 40h
0x18001ffb1  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001ffb8  mov     rdi, rdx
0x18001ffbb  test    rax, rax
0x18001ffbe  jz      short loc_18001FFD3
0x18001ffc0  mov     edx, 3
0x18001ffc5  mov     ecx, 3667CA7h
0x18001ffca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffcf  mov     edx, eax
0x18001ffd1  jmp     short loc_18001FFE1
0x18001ffd3  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001ffda  test    rax, rax
0x18001ffdd  jnz     short loc_18001FFC0
0x18001ffdf  xor     edx, edx
0x18001ffe1  mov     r8d, edx
0x18001ffe4  mov     qword ptr [rdi], 0
0x18001ffeb  and     r8d, 0FFFFFF3Fh
0x18001fff2  mov     eax, edx
0x18001fff4  and     edx, 80h
0x18001fffa  mov     ecx, r8d
0x18001fffd  and     ecx, 3
0x180020000  mov     r14d, 40h ; '@'
0x180020006  shl     ecx, 2
0x180020009  and     eax, r14d
0x18002000c  or      ecx, eax
0x18002000e  shl     ecx, 2
0x180020011  or      ecx, edx
0x180020013  shl     ecx, 3
0x180020016  test    r8d, r8d
0x180020019  jnz     short loc_180020023
0x18002001b  mov     edx, r14d
0x18002001e  mov     r8d, r14d
0x180020021  jmp     short loc_180020030
0x180020023  xor     edx, edx
0x180020025  cmp     r8d, 2
0x180020029  cmovz   edx, r14d
0x18002002d  mov     r8d, edx
0x180020030  mov     eax, ecx
0x180020032  mov     ebx, 1
0x180020037  or      eax, r8d
0x18002003a  or      ecx, edx
0x18002003c  mov     [rdi], eax
0x18002003e  bt      ecx, 0Ah
0x180020042  jnb     short loc_18002004C
0x180020044  cmp     ecx, 800h
0x18002004a  jnb     short loc_180020057
0x18002004c  xor     dl, dl
0x18002004e  test    r14b, cl
0x180020051  jz      loc_18002011B
0x180020057  mov     rax, cs:Feature_ValLabTest__descriptor
0x18002005e  mov     r8d, [rax]
0x180020061  test    r8b, 4
0x180020065  jnz     short loc_18002007A
0x180020067  lea     rdx, [rbp+arg_8]
0x18002006b  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)
0x180020070  mov     rcx, [rax]
0x180020073  mov     [rbp+arg_8], rcx
0x180020077  mov     r8d, ecx
0x18002007a  xor     eax, eax
0x18002007c  mov     word ptr [rbp+arg_0+4], 3
0x180020082  mov     r9d, r8d
0x180020085  mov     [rsp+40h+var_10], eax
0x180020089  mov     dword ptr [rbp+arg_0], eax
0x18002008c  lea     rcx, qword_18005FD88
0x180020093  shr     r9d, 0Bh
0x180020097  lea     rax, [rbp+arg_0]
0x18002009b  shr     r8d, 0Ah
0x18002009f  and     r9d, ebx
0x1800200a2  and     r8d, ebx
0x1800200a5  mov     [rsp+40h+var_18], ebx
0x1800200a9  mov     edx, 3667CA2h
0x1800200ae  mov     [rsp+40h+var_20], rax
0x1800200b3  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800200b8  mov     rax, cs:Feature_Standalone_25_10_NonSec__descriptor
0x1800200bf  mov     r8d, [rax]
0x1800200c2  test    r8b, 4
0x1800200c6  jnz     short loc_1800200DB
0x1800200c8  lea     rdx, [rbp+arg_8]
0x1800200cc  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)
0x1800200d1  mov     rcx, [rax]
0x1800200d4  mov     [rbp+arg_8], rcx
0x1800200d8  mov     r8d, ecx
0x1800200db  xor     eax, eax
0x1800200dd  mov     word ptr [rbp+arg_0+4], 3
0x1800200e3  mov     r9d, r8d
0x1800200e6  mov     [rsp+40h+var_10], eax
0x1800200ea  mov     dword ptr [rbp+arg_0], eax
0x1800200ed  lea     rcx, qword_18005FDE8
0x1800200f4  shr     r9d, 0Bh
0x1800200f8  lea     rax, [rbp+arg_0]
0x1800200fc  shr     r8d, 0Ah
0x180020100  and     r9d, ebx
0x180020103  and     r8d, ebx
0x180020106  mov     [rsp+40h+var_18], ebx
0x18002010a  mov     edx, 2AF34F8h
0x18002010f  mov     [rsp+40h+var_20], rax
0x180020114  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180020119  mov     dl, bl
0x18002011b  mov     eax, [rdi]
0x18002011d  test    r14b, al
0x180020120  jz      short loc_180020126
0x180020122  test    dl, dl
0x180020124  jnz     short loc_180020128
0x180020126  xor     ebx, ebx
0x180020128  and     eax, 0FFFFFFFEh
0x18002012b  or      eax, ebx
0x18002012d  mov     rbx, [rsp+40h+arg_10]
0x180020132  mov     [rdi], eax
0x180020134  mov     rax, rdi
0x180020137  add     rsp, 40h
0x18002013b  pop     r14
0x18002013d  pop     rdi
0x18002013e  pop     rbp
0x18002013f  retn
```
