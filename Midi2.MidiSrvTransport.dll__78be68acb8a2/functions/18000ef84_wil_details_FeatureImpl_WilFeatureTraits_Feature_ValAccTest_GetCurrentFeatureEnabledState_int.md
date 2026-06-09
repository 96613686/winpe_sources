# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000ef84`
- end: `0x18000f128`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000e7c4`

## callees

- `0x18000df54`
- `0x18000e8a4`
- `0x18000ef84`
- `0x18000fdb4`
- `0x180015010`

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
      (__int64)&qword_18001E808,
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
      (__int64)&qword_18001E8B0,
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
0x18000ef84  mov     [rsp-18h+arg_10], rbx
0x18000ef89  mov     [rsp-18h+arg_0], rcx
0x18000ef8e  push    rbp
0x18000ef8f  push    rdi
0x18000ef90  push    r14
0x18000ef92  mov     rbp, rsp
0x18000ef95  sub     rsp, 40h
0x18000ef99  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000efa0  mov     rdi, rdx
0x18000efa3  test    rax, rax
0x18000efa6  jz      short loc_18000EFBB
0x18000efa8  mov     edx, 3
0x18000efad  mov     ecx, 3667CA7h
0x18000efb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efb7  mov     edx, eax
0x18000efb9  jmp     short loc_18000EFC9
0x18000efbb  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000efc2  test    rax, rax
0x18000efc5  jnz     short loc_18000EFA8
0x18000efc7  xor     edx, edx
0x18000efc9  mov     r8d, edx
0x18000efcc  mov     qword ptr [rdi], 0
0x18000efd3  and     r8d, 0FFFFFF3Fh
0x18000efda  mov     eax, edx
0x18000efdc  and     edx, 80h
0x18000efe2  mov     ecx, r8d
0x18000efe5  and     ecx, 3
0x18000efe8  mov     r14d, 40h ; '@'
0x18000efee  shl     ecx, 2
0x18000eff1  and     eax, r14d
0x18000eff4  or      ecx, eax
0x18000eff6  shl     ecx, 2
0x18000eff9  or      ecx, edx
0x18000effb  shl     ecx, 3
0x18000effe  test    r8d, r8d
0x18000f001  jnz     short loc_18000F00B
0x18000f003  mov     edx, r14d
0x18000f006  mov     r8d, r14d
0x18000f009  jmp     short loc_18000F018
0x18000f00b  xor     edx, edx
0x18000f00d  cmp     r8d, 2
0x18000f011  cmovz   edx, r14d
0x18000f015  mov     r8d, edx
0x18000f018  mov     eax, ecx
0x18000f01a  mov     ebx, 1
0x18000f01f  or      eax, r8d
0x18000f022  or      ecx, edx
0x18000f024  mov     [rdi], eax
0x18000f026  bt      ecx, 0Ah
0x18000f02a  jnb     short loc_18000F034
0x18000f02c  cmp     ecx, 800h
0x18000f032  jnb     short loc_18000F03F
0x18000f034  xor     dl, dl
0x18000f036  test    r14b, cl
0x18000f039  jz      loc_18000F103
0x18000f03f  mov     rax, cs:Feature_ValLabTest__descriptor
0x18000f046  mov     r8d, [rax]
0x18000f049  test    r8b, 4
0x18000f04d  jnz     short loc_18000F062
0x18000f04f  lea     rdx, [rbp+arg_8]
0x18000f053  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)
0x18000f058  mov     rcx, [rax]
0x18000f05b  mov     [rbp+arg_8], rcx
0x18000f05f  mov     r8d, ecx
0x18000f062  xor     eax, eax
0x18000f064  mov     word ptr [rbp+arg_0+4], 3
0x18000f06a  mov     r9d, r8d
0x18000f06d  mov     [rsp+40h+var_10], eax
0x18000f071  mov     dword ptr [rbp+arg_0], eax
0x18000f074  lea     rcx, qword_18001E808
0x18000f07b  shr     r9d, 0Bh
0x18000f07f  lea     rax, [rbp+arg_0]
0x18000f083  shr     r8d, 0Ah
0x18000f087  and     r9d, ebx
0x18000f08a  and     r8d, ebx
0x18000f08d  mov     [rsp+40h+var_18], ebx
0x18000f091  mov     edx, 3667CA2h
0x18000f096  mov     [rsp+40h+var_20], rax
0x18000f09b  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000f0a0  mov     rax, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18000f0a7  mov     r8d, [rax]
0x18000f0aa  test    r8b, 4
0x18000f0ae  jnz     short loc_18000F0C3
0x18000f0b0  lea     rdx, [rbp+arg_8]
0x18000f0b4  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)
0x18000f0b9  mov     rcx, [rax]
0x18000f0bc  mov     [rbp+arg_8], rcx
0x18000f0c0  mov     r8d, ecx
0x18000f0c3  xor     eax, eax
0x18000f0c5  mov     word ptr [rbp+arg_0+4], 3
0x18000f0cb  mov     r9d, r8d
0x18000f0ce  mov     [rsp+40h+var_10], eax
0x18000f0d2  mov     dword ptr [rbp+arg_0], eax
0x18000f0d5  lea     rcx, qword_18001E8B0
0x18000f0dc  shr     r9d, 0Bh
0x18000f0e0  lea     rax, [rbp+arg_0]
0x18000f0e4  shr     r8d, 0Ah
0x18000f0e8  and     r9d, ebx
0x18000f0eb  and     r8d, ebx
0x18000f0ee  mov     [rsp+40h+var_18], ebx
0x18000f0f2  mov     edx, 2AF34F8h
0x18000f0f7  mov     [rsp+40h+var_20], rax
0x18000f0fc  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000f101  mov     dl, bl
0x18000f103  mov     eax, [rdi]
0x18000f105  test    r14b, al
0x18000f108  jz      short loc_18000F10E
0x18000f10a  test    dl, dl
0x18000f10c  jnz     short loc_18000F110
0x18000f10e  xor     ebx, ebx
0x18000f110  and     eax, 0FFFFFFFEh
0x18000f113  or      eax, ebx
0x18000f115  mov     rbx, [rsp+40h+arg_10]
0x18000f11a  mov     [rdi], eax
0x18000f11c  mov     rax, rdi
0x18000f11f  add     rsp, 40h
0x18000f123  pop     r14
0x18000f125  pop     rdi
0x18000f126  pop     rbp
0x18000f127  retn
```
