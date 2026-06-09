# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001507c`
- end: `0x180015220`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `420`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180014218`

## callees

- `0x18000ab68`
- `0x180013380`
- `0x1800142f8`
- `0x18001507c`
- `0x18002a010`

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
    wil::details::ReportUsageToService(&qword_180033728, 57048226, (v13 >> 10) & 1, (v13 >> 11) & 1, &v17, 1, 0);
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
    wil::details::ReportUsageToService(&qword_180033788, 45036792, (v15 >> 10) & 1, (v15 >> 11) & 1, &v17, 1, 0);
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
0x18001507c  mov     [rsp-18h+arg_10], rbx
0x180015081  mov     [rsp-18h+arg_0], rcx
0x180015086  push    rbp
0x180015087  push    rdi
0x180015088  push    r14
0x18001508a  mov     rbp, rsp
0x18001508d  sub     rsp, 40h
0x180015091  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180015098  mov     rdi, rdx
0x18001509b  test    rax, rax
0x18001509e  jz      short loc_1800150B3
0x1800150a0  mov     edx, 3
0x1800150a5  mov     ecx, 3667CA7h
0x1800150aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150af  mov     edx, eax
0x1800150b1  jmp     short loc_1800150C1
0x1800150b3  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800150ba  test    rax, rax
0x1800150bd  jnz     short loc_1800150A0
0x1800150bf  xor     edx, edx
0x1800150c1  mov     r8d, edx
0x1800150c4  mov     qword ptr [rdi], 0
0x1800150cb  and     r8d, 0FFFFFF3Fh
0x1800150d2  mov     eax, edx
0x1800150d4  and     edx, 80h
0x1800150da  mov     ecx, r8d
0x1800150dd  and     ecx, 3
0x1800150e0  mov     r14d, 40h ; '@'
0x1800150e6  shl     ecx, 2
0x1800150e9  and     eax, r14d
0x1800150ec  or      ecx, eax
0x1800150ee  shl     ecx, 2
0x1800150f1  or      ecx, edx
0x1800150f3  shl     ecx, 3
0x1800150f6  test    r8d, r8d
0x1800150f9  jnz     short loc_180015103
0x1800150fb  mov     edx, r14d
0x1800150fe  mov     r8d, r14d
0x180015101  jmp     short loc_180015110
0x180015103  xor     edx, edx
0x180015105  cmp     r8d, 2
0x180015109  cmovz   edx, r14d
0x18001510d  mov     r8d, edx
0x180015110  mov     eax, ecx
0x180015112  mov     ebx, 1
0x180015117  or      eax, r8d
0x18001511a  or      ecx, edx
0x18001511c  mov     [rdi], eax
0x18001511e  bt      ecx, 0Ah
0x180015122  jnb     short loc_18001512C
0x180015124  cmp     ecx, 800h
0x18001512a  jnb     short loc_180015137
0x18001512c  xor     dl, dl
0x18001512e  test    r14b, cl
0x180015131  jz      loc_1800151FB
0x180015137  mov     rax, cs:Feature_ValLabTest__descriptor
0x18001513e  mov     r8d, [rax]
0x180015141  test    r8b, 4
0x180015145  jnz     short loc_18001515A
0x180015147  lea     rdx, [rbp+arg_8]
0x18001514b  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)
0x180015150  mov     rcx, [rax]
0x180015153  mov     [rbp+arg_8], rcx
0x180015157  mov     r8d, ecx
0x18001515a  xor     eax, eax
0x18001515c  mov     word ptr [rbp+arg_0+4], 3
0x180015162  mov     r9d, r8d
0x180015165  mov     [rsp+40h+var_10], eax
0x180015169  mov     dword ptr [rbp+arg_0], eax
0x18001516c  lea     rcx, qword_180033728
0x180015173  shr     r9d, 0Bh
0x180015177  lea     rax, [rbp+arg_0]
0x18001517b  shr     r8d, 0Ah
0x18001517f  and     r9d, ebx
0x180015182  and     r8d, ebx
0x180015185  mov     [rsp+40h+var_18], ebx
0x180015189  mov     edx, 3667CA2h
0x18001518e  mov     [rsp+40h+var_20], rax
0x180015193  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180015198  mov     rax, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18001519f  mov     r8d, [rax]
0x1800151a2  test    r8b, 4
0x1800151a6  jnz     short loc_1800151BB
0x1800151a8  lea     rdx, [rbp+arg_8]
0x1800151ac  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)
0x1800151b1  mov     rcx, [rax]
0x1800151b4  mov     [rbp+arg_8], rcx
0x1800151b8  mov     r8d, ecx
0x1800151bb  xor     eax, eax
0x1800151bd  mov     word ptr [rbp+arg_0+4], 3
0x1800151c3  mov     r9d, r8d
0x1800151c6  mov     [rsp+40h+var_10], eax
0x1800151ca  mov     dword ptr [rbp+arg_0], eax
0x1800151cd  lea     rcx, qword_180033788
0x1800151d4  shr     r9d, 0Bh
0x1800151d8  lea     rax, [rbp+arg_0]
0x1800151dc  shr     r8d, 0Ah
0x1800151e0  and     r9d, ebx
0x1800151e3  and     r8d, ebx
0x1800151e6  mov     [rsp+40h+var_18], ebx
0x1800151ea  mov     edx, 2AF34F8h
0x1800151ef  mov     [rsp+40h+var_20], rax
0x1800151f4  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800151f9  mov     dl, bl
0x1800151fb  mov     eax, [rdi]
0x1800151fd  test    r14b, al
0x180015200  jz      short loc_180015206
0x180015202  test    dl, dl
0x180015204  jnz     short loc_180015208
0x180015206  xor     ebx, ebx
0x180015208  and     eax, 0FFFFFFFEh
0x18001520b  or      eax, ebx
0x18001520d  mov     rbx, [rsp+40h+arg_10]
0x180015212  mov     [rdi], eax
0x180015214  mov     rax, rdi
0x180015217  add     rsp, 40h
0x18001521b  pop     r14
0x18001521d  pop     rdi
0x18001521e  pop     rbp
0x18001521f  retn
```
