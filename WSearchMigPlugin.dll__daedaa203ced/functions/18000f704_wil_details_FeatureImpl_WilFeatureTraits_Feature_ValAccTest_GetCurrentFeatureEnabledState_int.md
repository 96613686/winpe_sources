# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000f704`
- end: `0x18000f8a8`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `420`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000ee64`

## callees

- `0x18000e3a0`
- `0x18000ef44`
- `0x18000f704`
- `0x1800120a8`
- `0x180018010`

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
  wil::details *v11; // rcx
  char v12; // dl
  unsigned int v13; // r8d
  wil::details *v14; // rcx
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
  v11 = (wil::details *)(v7 | (unsigned int)v6);
  *(_DWORD *)a2 = v10;
  if ( ((unsigned __int16)v11 & 0x400) != 0 && (unsigned int)v11 >= 0x800
    || (v12 = 0, ((unsigned __int8)v11 & 0x40) != 0) )
  {
    v13 = *(_DWORD *)Feature_ValLabTest__descriptor;
    if ( (*(_DWORD *)Feature_ValLabTest__descriptor & 4) == 0 )
    {
      v18 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(v11, &v18);
      v13 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(&qword_180025FD0, 57048226, (v13 >> 10) & 1, (v13 >> 11) & 1, &v17, 1, 0);
    v15 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor & 4) == 0 )
    {
      v18 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
               v14,
               &v18);
      v15 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(&qword_180026020, 45036792, (v15 >> 10) & 1, (v15 >> 11) & 1, &v17, 1, 0);
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
0x18000f704  mov     [rsp-18h+arg_10], rbx
0x18000f709  mov     [rsp-18h+arg_0], rcx
0x18000f70e  push    rbp
0x18000f70f  push    rdi
0x18000f710  push    r14
0x18000f712  mov     rbp, rsp
0x18000f715  sub     rsp, 40h
0x18000f719  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000f720  mov     rdi, rdx
0x18000f723  test    rax, rax
0x18000f726  jz      short loc_18000F73B
0x18000f728  mov     edx, 3
0x18000f72d  mov     ecx, 3667CA7h
0x18000f732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f737  mov     edx, eax
0x18000f739  jmp     short loc_18000F749
0x18000f73b  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000f742  test    rax, rax
0x18000f745  jnz     short loc_18000F728
0x18000f747  xor     edx, edx
0x18000f749  mov     r8d, edx
0x18000f74c  mov     qword ptr [rdi], 0
0x18000f753  and     r8d, 0FFFFFF3Fh
0x18000f75a  mov     eax, edx
0x18000f75c  and     edx, 80h
0x18000f762  mov     ecx, r8d
0x18000f765  and     ecx, 3
0x18000f768  mov     r14d, 40h ; '@'
0x18000f76e  shl     ecx, 2
0x18000f771  and     eax, r14d
0x18000f774  or      ecx, eax
0x18000f776  shl     ecx, 2
0x18000f779  or      ecx, edx
0x18000f77b  shl     ecx, 3
0x18000f77e  test    r8d, r8d
0x18000f781  jnz     short loc_18000F78B
0x18000f783  mov     edx, r14d
0x18000f786  mov     r8d, r14d
0x18000f789  jmp     short loc_18000F798
0x18000f78b  xor     edx, edx
0x18000f78d  cmp     r8d, 2
0x18000f791  cmovz   edx, r14d
0x18000f795  mov     r8d, edx
0x18000f798  mov     eax, ecx
0x18000f79a  mov     ebx, 1
0x18000f79f  or      eax, r8d
0x18000f7a2  or      ecx, edx
0x18000f7a4  mov     [rdi], eax
0x18000f7a6  bt      ecx, 0Ah
0x18000f7aa  jnb     short loc_18000F7B4
0x18000f7ac  cmp     ecx, 800h
0x18000f7b2  jnb     short loc_18000F7BF
0x18000f7b4  xor     dl, dl
0x18000f7b6  test    r14b, cl
0x18000f7b9  jz      loc_18000F883
0x18000f7bf  mov     rax, cs:Feature_ValLabTest__descriptor
0x18000f7c6  mov     r8d, [rax]
0x18000f7c9  test    r8b, 4
0x18000f7cd  jnz     short loc_18000F7E2
0x18000f7cf  lea     rdx, [rbp+arg_8]
0x18000f7d3  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)
0x18000f7d8  mov     rcx, [rax]
0x18000f7db  mov     [rbp+arg_8], rcx
0x18000f7df  mov     r8d, ecx
0x18000f7e2  xor     eax, eax
0x18000f7e4  mov     word ptr [rbp+arg_0+4], 3
0x18000f7ea  mov     r9d, r8d
0x18000f7ed  mov     [rsp+40h+var_10], eax
0x18000f7f1  mov     dword ptr [rbp+arg_0], eax
0x18000f7f4  lea     rcx, qword_180025FD0
0x18000f7fb  shr     r9d, 0Bh
0x18000f7ff  lea     rax, [rbp+arg_0]
0x18000f803  shr     r8d, 0Ah
0x18000f807  and     r9d, ebx
0x18000f80a  and     r8d, ebx
0x18000f80d  mov     [rsp+40h+var_18], ebx
0x18000f811  mov     edx, 3667CA2h
0x18000f816  mov     [rsp+40h+var_20], rax
0x18000f81b  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000f820  mov     rax, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18000f827  mov     r8d, [rax]
0x18000f82a  test    r8b, 4
0x18000f82e  jnz     short loc_18000F843
0x18000f830  lea     rdx, [rbp+arg_8]
0x18000f834  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)
0x18000f839  mov     rcx, [rax]
0x18000f83c  mov     [rbp+arg_8], rcx
0x18000f840  mov     r8d, ecx
0x18000f843  xor     eax, eax
0x18000f845  mov     word ptr [rbp+arg_0+4], 3
0x18000f84b  mov     r9d, r8d
0x18000f84e  mov     [rsp+40h+var_10], eax
0x18000f852  mov     dword ptr [rbp+arg_0], eax
0x18000f855  lea     rcx, qword_180026020
0x18000f85c  shr     r9d, 0Bh
0x18000f860  lea     rax, [rbp+arg_0]
0x18000f864  shr     r8d, 0Ah
0x18000f868  and     r9d, ebx
0x18000f86b  and     r8d, ebx
0x18000f86e  mov     [rsp+40h+var_18], ebx
0x18000f872  mov     edx, 2AF34F8h
0x18000f877  mov     [rsp+40h+var_20], rax
0x18000f87c  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000f881  mov     dl, bl
0x18000f883  mov     eax, [rdi]
0x18000f885  test    r14b, al
0x18000f888  jz      short loc_18000F88E
0x18000f88a  test    dl, dl
0x18000f88c  jnz     short loc_18000F890
0x18000f88e  xor     ebx, ebx
0x18000f890  and     eax, 0FFFFFFFEh
0x18000f893  or      eax, ebx
0x18000f895  mov     rbx, [rsp+40h+arg_10]
0x18000f89a  mov     [rdi], eax
0x18000f89c  mov     rax, rdi
0x18000f89f  add     rsp, 40h
0x18000f8a3  pop     r14
0x18000f8a5  pop     rdi
0x18000f8a6  pop     rbp
0x18000f8a7  retn
```
