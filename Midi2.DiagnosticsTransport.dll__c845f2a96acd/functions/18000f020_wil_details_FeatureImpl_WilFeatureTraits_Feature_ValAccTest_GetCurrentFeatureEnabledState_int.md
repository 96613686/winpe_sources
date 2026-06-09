# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000f020`
- end: `0x18000f1c4`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000e690`

## callees

- `0x18000d978`
- `0x18000e770`
- `0x18000f020`
- `0x18000fbd4`
- `0x180013010`

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
      (__int64)&qword_18001A848,
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
      (__int64)&qword_18001A8A8,
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
0x18000f020  mov     [rsp-18h+arg_10], rbx
0x18000f025  mov     [rsp-18h+arg_0], rcx
0x18000f02a  push    rbp
0x18000f02b  push    rdi
0x18000f02c  push    r14
0x18000f02e  mov     rbp, rsp
0x18000f031  sub     rsp, 40h
0x18000f035  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000f03c  mov     rdi, rdx
0x18000f03f  test    rax, rax
0x18000f042  jz      short loc_18000F057
0x18000f044  mov     edx, 3
0x18000f049  mov     ecx, 3667CA7h
0x18000f04e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f053  mov     edx, eax
0x18000f055  jmp     short loc_18000F065
0x18000f057  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000f05e  test    rax, rax
0x18000f061  jnz     short loc_18000F044
0x18000f063  xor     edx, edx
0x18000f065  mov     r8d, edx
0x18000f068  mov     qword ptr [rdi], 0
0x18000f06f  and     r8d, 0FFFFFF3Fh
0x18000f076  mov     eax, edx
0x18000f078  and     edx, 80h
0x18000f07e  mov     ecx, r8d
0x18000f081  and     ecx, 3
0x18000f084  mov     r14d, 40h ; '@'
0x18000f08a  shl     ecx, 2
0x18000f08d  and     eax, r14d
0x18000f090  or      ecx, eax
0x18000f092  shl     ecx, 2
0x18000f095  or      ecx, edx
0x18000f097  shl     ecx, 3
0x18000f09a  test    r8d, r8d
0x18000f09d  jnz     short loc_18000F0A7
0x18000f09f  mov     edx, r14d
0x18000f0a2  mov     r8d, r14d
0x18000f0a5  jmp     short loc_18000F0B4
0x18000f0a7  xor     edx, edx
0x18000f0a9  cmp     r8d, 2
0x18000f0ad  cmovz   edx, r14d
0x18000f0b1  mov     r8d, edx
0x18000f0b4  mov     eax, ecx
0x18000f0b6  mov     ebx, 1
0x18000f0bb  or      eax, r8d
0x18000f0be  or      ecx, edx
0x18000f0c0  mov     [rdi], eax
0x18000f0c2  bt      ecx, 0Ah
0x18000f0c6  jnb     short loc_18000F0D0
0x18000f0c8  cmp     ecx, 800h
0x18000f0ce  jnb     short loc_18000F0DB
0x18000f0d0  xor     dl, dl
0x18000f0d2  test    r14b, cl
0x18000f0d5  jz      loc_18000F19F
0x18000f0db  mov     rax, cs:Feature_ValLabTest__descriptor
0x18000f0e2  mov     r8d, [rax]
0x18000f0e5  test    r8b, 4
0x18000f0e9  jnz     short loc_18000F0FE
0x18000f0eb  lea     rdx, [rbp+arg_8]
0x18000f0ef  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)
0x18000f0f4  mov     rcx, [rax]
0x18000f0f7  mov     [rbp+arg_8], rcx
0x18000f0fb  mov     r8d, ecx
0x18000f0fe  xor     eax, eax
0x18000f100  mov     word ptr [rbp+arg_0+4], 3
0x18000f106  mov     r9d, r8d
0x18000f109  mov     [rsp+40h+var_10], eax
0x18000f10d  mov     dword ptr [rbp+arg_0], eax
0x18000f110  lea     rcx, qword_18001A848
0x18000f117  shr     r9d, 0Bh
0x18000f11b  lea     rax, [rbp+arg_0]
0x18000f11f  shr     r8d, 0Ah
0x18000f123  and     r9d, ebx
0x18000f126  and     r8d, ebx
0x18000f129  mov     [rsp+40h+var_18], ebx
0x18000f12d  mov     edx, 3667CA2h
0x18000f132  mov     [rsp+40h+var_20], rax
0x18000f137  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000f13c  mov     rax, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18000f143  mov     r8d, [rax]
0x18000f146  test    r8b, 4
0x18000f14a  jnz     short loc_18000F15F
0x18000f14c  lea     rdx, [rbp+arg_8]
0x18000f150  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)
0x18000f155  mov     rcx, [rax]
0x18000f158  mov     [rbp+arg_8], rcx
0x18000f15c  mov     r8d, ecx
0x18000f15f  xor     eax, eax
0x18000f161  mov     word ptr [rbp+arg_0+4], 3
0x18000f167  mov     r9d, r8d
0x18000f16a  mov     [rsp+40h+var_10], eax
0x18000f16e  mov     dword ptr [rbp+arg_0], eax
0x18000f171  lea     rcx, qword_18001A8A8
0x18000f178  shr     r9d, 0Bh
0x18000f17c  lea     rax, [rbp+arg_0]
0x18000f180  shr     r8d, 0Ah
0x18000f184  and     r9d, ebx
0x18000f187  and     r8d, ebx
0x18000f18a  mov     [rsp+40h+var_18], ebx
0x18000f18e  mov     edx, 2AF34F8h
0x18000f193  mov     [rsp+40h+var_20], rax
0x18000f198  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000f19d  mov     dl, bl
0x18000f19f  mov     eax, [rdi]
0x18000f1a1  test    r14b, al
0x18000f1a4  jz      short loc_18000F1AA
0x18000f1a6  test    dl, dl
0x18000f1a8  jnz     short loc_18000F1AC
0x18000f1aa  xor     ebx, ebx
0x18000f1ac  and     eax, 0FFFFFFFEh
0x18000f1af  or      eax, ebx
0x18000f1b1  mov     rbx, [rsp+40h+arg_10]
0x18000f1b6  mov     [rdi], eax
0x18000f1b8  mov     rax, rdi
0x18000f1bb  add     rsp, 40h
0x18000f1bf  pop     r14
0x18000f1c1  pop     rdi
0x18000f1c2  pop     rbp
0x18000f1c3  retn
```
