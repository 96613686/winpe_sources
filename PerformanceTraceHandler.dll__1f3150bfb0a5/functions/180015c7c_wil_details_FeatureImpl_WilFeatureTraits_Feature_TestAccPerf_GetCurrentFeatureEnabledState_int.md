# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180015c7c`
- end: `0x180015dc4`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `328`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800153f8`

## callees

- `0x18000cc60`
- `0x18000cfc0`
- `0x180014da8`
- `0x180015c7c`
- `0x180017e10`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // r8d
  int v7; // ecx
  int v8; // edx
  int v9; // edi
  int v10; // eax
  unsigned int v11; // r8d
  char v12; // si
  char v13; // cl
  wil::details *v14; // rcx
  unsigned int v15; // r8d
  __int64 v17; // [rsp+60h] [rbp+8h] BYREF
  __int64 v18; // [rsp+68h] [rbp+10h] BYREF

  v17 = a1;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3667CAD, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( (FeatureEnabledState & 0xFFFFFF3F) == 2 )
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
  v11 = v7 | v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    v13 = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_18;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl'::`2'::impl) )
  {
    v15 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor & 4) == 0 )
    {
      v18 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
               v14,
               &v18);
      v15 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(&qword_180027D48, 45036797, (v15 >> 10) & 1, (v15 >> 11) & 1, &v17, 1, 0);
    v13 = 1;
  }
  else
  {
    v13 = 0;
  }
  if ( v12 && !v13 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_18:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v13 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180015c7c  mov     [rsp+arg_10], rbx
0x180015c81  mov     [rsp+arg_0], rcx
0x180015c86  push    rbp
0x180015c87  push    rsi
0x180015c88  push    rdi
0x180015c89  sub     rsp, 40h
0x180015c8d  mov     ecx, 3667CADh; this
0x180015c92  mov     rbx, rdx
0x180015c95  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180015c9a  mov     edx, eax
0x180015c9c  mov     qword ptr [rbx], 0
0x180015ca3  and     edx, 0FFFFFF3Fh
0x180015ca9  mov     ecx, eax
0x180015cab  and     eax, 80h
0x180015cb0  mov     r8d, edx
0x180015cb3  and     r8d, 3
0x180015cb7  mov     ebp, 40h ; '@'
0x180015cbc  shl     r8d, 2
0x180015cc0  and     ecx, ebp
0x180015cc2  or      r8d, ecx
0x180015cc5  shl     r8d, 2
0x180015cc9  or      r8d, eax
0x180015ccc  shl     r8d, 3
0x180015cd0  test    edx, edx
0x180015cd2  jnz     short loc_180015CDA
0x180015cd4  mov     ecx, ebp
0x180015cd6  mov     edx, ebp
0x180015cd8  jmp     short loc_180015CE4
0x180015cda  xor     ecx, ecx
0x180015cdc  cmp     edx, 2
0x180015cdf  cmovz   ecx, ebp
0x180015ce2  mov     edx, ecx
0x180015ce4  mov     eax, r8d
0x180015ce7  mov     edi, 1
0x180015cec  or      eax, edx
0x180015cee  or      r8d, ecx
0x180015cf1  mov     [rbx], eax
0x180015cf3  bt      r8d, 0Ah
0x180015cf8  jnb     short loc_180015D08
0x180015cfa  cmp     r8d, 800h
0x180015d01  jb      short loc_180015D08
0x180015d03  mov     sil, dil
0x180015d06  jmp     short loc_180015D16
0x180015d08  xor     sil, sil
0x180015d0b  xor     cl, cl
0x180015d0d  test    bpl, r8b
0x180015d10  jz      loc_180015DA0
0x180015d16  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x180015d1d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x180015d22  test    al, al
0x180015d24  jz      short loc_180015D91
0x180015d26  mov     rax, cs:Feature_Standalone_25_11_NonSec__descriptor
0x180015d2d  mov     r8d, [rax]
0x180015d30  test    r8b, 4
0x180015d34  jnz     short loc_180015D4B
0x180015d36  lea     rdx, [rsp+58h+arg_8]
0x180015d3b  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)
0x180015d40  mov     rcx, [rax]
0x180015d43  mov     [rsp+58h+arg_8], rcx
0x180015d48  mov     r8d, ecx
0x180015d4b  xor     eax, eax
0x180015d4d  mov     word ptr [rsp+58h+arg_0+4], 3
0x180015d54  mov     r9d, r8d
0x180015d57  mov     [rsp+58h+var_28], eax
0x180015d5b  mov     dword ptr [rsp+58h+arg_0], eax
0x180015d5f  lea     rcx, qword_180027D48
0x180015d66  shr     r9d, 0Bh
0x180015d6a  lea     rax, [rsp+58h+arg_0]
0x180015d6f  shr     r8d, 0Ah
0x180015d73  and     r9d, edi
0x180015d76  and     r8d, edi
0x180015d79  mov     [rsp+58h+var_30], edi
0x180015d7d  mov     edx, 2AF34FDh
0x180015d82  mov     [rsp+58h+var_38], rax
0x180015d87  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180015d8c  mov     cl, dil
0x180015d8f  jmp     short loc_180015D93
0x180015d91  xor     cl, cl
0x180015d93  test    sil, sil
0x180015d96  jz      short loc_180015DA0
0x180015d98  test    cl, cl
0x180015d9a  jnz     short loc_180015DA0
0x180015d9c  btr     dword ptr [rbx], 0Ah
0x180015da0  mov     eax, [rbx]
0x180015da2  test    bpl, al
0x180015da5  jz      short loc_180015DAB
0x180015da7  test    cl, cl
0x180015da9  jnz     short loc_180015DAD
0x180015dab  xor     edi, edi
0x180015dad  and     eax, 0FFFFFFFEh
0x180015db0  or      eax, edi
0x180015db2  mov     [rbx], eax
0x180015db4  mov     rax, rbx
0x180015db7  mov     rbx, [rsp+58h+arg_10]
0x180015dbc  add     rsp, 40h
0x180015dc0  pop     rdi
0x180015dc1  pop     rsi
0x180015dc2  pop     rbp
0x180015dc3  retn
```
