# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000c0f4`
- end: `0x18000c298`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000b8d4`

## callees

- `0x18000ae10`
- `0x18000b9b4`
- `0x18000c0f4`
- `0x18000c804`
- `0x18000f010`

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
      (__int64)&qword_1800157F8,
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
      (__int64)&qword_180015848,
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
0x18000c0f4  mov     [rsp-18h+arg_10], rbx
0x18000c0f9  mov     [rsp-18h+arg_0], rcx
0x18000c0fe  push    rbp
0x18000c0ff  push    rdi
0x18000c100  push    r14
0x18000c102  mov     rbp, rsp
0x18000c105  sub     rsp, 40h
0x18000c109  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000c110  mov     rdi, rdx
0x18000c113  test    rax, rax
0x18000c116  jz      short loc_18000C12B
0x18000c118  mov     edx, 3
0x18000c11d  mov     ecx, 3667CA7h
0x18000c122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c127  mov     edx, eax
0x18000c129  jmp     short loc_18000C139
0x18000c12b  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000c132  test    rax, rax
0x18000c135  jnz     short loc_18000C118
0x18000c137  xor     edx, edx
0x18000c139  mov     r8d, edx
0x18000c13c  mov     qword ptr [rdi], 0
0x18000c143  and     r8d, 0FFFFFF3Fh
0x18000c14a  mov     eax, edx
0x18000c14c  and     edx, 80h
0x18000c152  mov     ecx, r8d
0x18000c155  and     ecx, 3
0x18000c158  mov     r14d, 40h ; '@'
0x18000c15e  shl     ecx, 2
0x18000c161  and     eax, r14d
0x18000c164  or      ecx, eax
0x18000c166  shl     ecx, 2
0x18000c169  or      ecx, edx
0x18000c16b  shl     ecx, 3
0x18000c16e  test    r8d, r8d
0x18000c171  jnz     short loc_18000C17B
0x18000c173  mov     edx, r14d
0x18000c176  mov     r8d, r14d
0x18000c179  jmp     short loc_18000C188
0x18000c17b  xor     edx, edx
0x18000c17d  cmp     r8d, 2
0x18000c181  cmovz   edx, r14d
0x18000c185  mov     r8d, edx
0x18000c188  mov     eax, ecx
0x18000c18a  mov     ebx, 1
0x18000c18f  or      eax, r8d
0x18000c192  or      ecx, edx
0x18000c194  mov     [rdi], eax
0x18000c196  bt      ecx, 0Ah
0x18000c19a  jnb     short loc_18000C1A4
0x18000c19c  cmp     ecx, 800h
0x18000c1a2  jnb     short loc_18000C1AF
0x18000c1a4  xor     dl, dl
0x18000c1a6  test    r14b, cl
0x18000c1a9  jz      loc_18000C273
0x18000c1af  mov     rax, cs:Feature_ValLabTest__descriptor
0x18000c1b6  mov     r8d, [rax]
0x18000c1b9  test    r8b, 4
0x18000c1bd  jnz     short loc_18000C1D2
0x18000c1bf  lea     rdx, [rbp+arg_8]
0x18000c1c3  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)
0x18000c1c8  mov     rcx, [rax]
0x18000c1cb  mov     [rbp+arg_8], rcx
0x18000c1cf  mov     r8d, ecx
0x18000c1d2  xor     eax, eax
0x18000c1d4  mov     word ptr [rbp+arg_0+4], 3
0x18000c1da  mov     r9d, r8d
0x18000c1dd  mov     [rsp+40h+var_10], eax
0x18000c1e1  mov     dword ptr [rbp+arg_0], eax
0x18000c1e4  lea     rcx, qword_1800157F8
0x18000c1eb  shr     r9d, 0Bh
0x18000c1ef  lea     rax, [rbp+arg_0]
0x18000c1f3  shr     r8d, 0Ah
0x18000c1f7  and     r9d, ebx
0x18000c1fa  and     r8d, ebx
0x18000c1fd  mov     [rsp+40h+var_18], ebx
0x18000c201  mov     edx, 3667CA2h
0x18000c206  mov     [rsp+40h+var_20], rax
0x18000c20b  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000c210  mov     rax, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18000c217  mov     r8d, [rax]
0x18000c21a  test    r8b, 4
0x18000c21e  jnz     short loc_18000C233
0x18000c220  lea     rdx, [rbp+arg_8]
0x18000c224  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)
0x18000c229  mov     rcx, [rax]
0x18000c22c  mov     [rbp+arg_8], rcx
0x18000c230  mov     r8d, ecx
0x18000c233  xor     eax, eax
0x18000c235  mov     word ptr [rbp+arg_0+4], 3
0x18000c23b  mov     r9d, r8d
0x18000c23e  mov     [rsp+40h+var_10], eax
0x18000c242  mov     dword ptr [rbp+arg_0], eax
0x18000c245  lea     rcx, qword_180015848
0x18000c24c  shr     r9d, 0Bh
0x18000c250  lea     rax, [rbp+arg_0]
0x18000c254  shr     r8d, 0Ah
0x18000c258  and     r9d, ebx
0x18000c25b  and     r8d, ebx
0x18000c25e  mov     [rsp+40h+var_18], ebx
0x18000c262  mov     edx, 2AF34F8h
0x18000c267  mov     [rsp+40h+var_20], rax
0x18000c26c  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000c271  mov     dl, bl
0x18000c273  mov     eax, [rdi]
0x18000c275  test    r14b, al
0x18000c278  jz      short loc_18000C27E
0x18000c27a  test    dl, dl
0x18000c27c  jnz     short loc_18000C280
0x18000c27e  xor     ebx, ebx
0x18000c280  and     eax, 0FFFFFFFEh
0x18000c283  or      eax, ebx
0x18000c285  mov     rbx, [rsp+40h+arg_10]
0x18000c28a  mov     [rdi], eax
0x18000c28c  mov     rax, rdi
0x18000c28f  add     rsp, 40h
0x18000c293  pop     r14
0x18000c295  pop     rdi
0x18000c296  pop     rbp
0x18000c297  retn
```
