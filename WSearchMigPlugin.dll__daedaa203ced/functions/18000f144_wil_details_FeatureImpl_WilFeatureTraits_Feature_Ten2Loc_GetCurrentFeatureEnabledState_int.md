# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000f144`
- end: `0x18000f2ad`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000eae4`

## callees

- `0x18000e7fc`
- `0x18000f144`
- `0x1800120a8`
- `0x180013eac`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  __int64 v7; // rdx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  unsigned int v11; // ecx
  char v12; // si
  wil::details *v13; // rcx
  unsigned int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v16 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(58989002, 3);
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
  v11 = v7 | v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    LOBYTE(v7) = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_22;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(
                          &`wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_180026050, 58599550, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
    LOBYTE(v7) = 1;
  }
  else
  {
    LOBYTE(v7) = 0;
  }
  if ( v12 && !(_BYTE)v7 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_22:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x18000f144  mov     [rsp+arg_10], rbx
0x18000f149  mov     [rsp+arg_0], rcx
0x18000f14e  push    rbp
0x18000f14f  push    rsi
0x18000f150  push    rdi
0x18000f151  sub     rsp, 40h
0x18000f155  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000f15c  mov     rbx, rdx
0x18000f15f  test    rax, rax
0x18000f162  jz      short loc_18000F177
0x18000f164  mov     edx, 3
0x18000f169  mov     ecx, 38419CAh
0x18000f16e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f173  mov     edx, eax
0x18000f175  jmp     short loc_18000F185
0x18000f177  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000f17e  test    rax, rax
0x18000f181  jnz     short loc_18000F164
0x18000f183  xor     edx, edx
0x18000f185  mov     r8d, edx
0x18000f188  mov     qword ptr [rbx], 0
0x18000f18f  and     r8d, 0FFFFFF3Fh
0x18000f196  mov     eax, edx
0x18000f198  and     edx, 80h
0x18000f19e  mov     ecx, r8d
0x18000f1a1  and     ecx, 3
0x18000f1a4  mov     ebp, 40h ; '@'
0x18000f1a9  shl     ecx, 2
0x18000f1ac  and     eax, ebp
0x18000f1ae  or      ecx, eax
0x18000f1b0  shl     ecx, 2
0x18000f1b3  or      ecx, edx
0x18000f1b5  shl     ecx, 3
0x18000f1b8  test    r8d, r8d
0x18000f1bb  jnz     short loc_18000F1C4
0x18000f1bd  mov     edx, ebp
0x18000f1bf  mov     r8d, ebp
0x18000f1c2  jmp     short loc_18000F1D0
0x18000f1c4  xor     edx, edx
0x18000f1c6  cmp     r8d, 2
0x18000f1ca  cmovz   edx, ebp
0x18000f1cd  mov     r8d, edx
0x18000f1d0  mov     eax, ecx
0x18000f1d2  mov     edi, 1
0x18000f1d7  or      eax, r8d
0x18000f1da  or      ecx, edx
0x18000f1dc  mov     [rbx], eax
0x18000f1de  bt      ecx, 0Ah
0x18000f1e2  jnb     short loc_18000F1F1
0x18000f1e4  cmp     ecx, 800h
0x18000f1ea  jb      short loc_18000F1F1
0x18000f1ec  mov     sil, dil
0x18000f1ef  jmp     short loc_18000F1FF
0x18000f1f1  xor     sil, sil
0x18000f1f4  xor     dl, dl
0x18000f1f6  test    bpl, cl
0x18000f1f9  jz      loc_18000F289
0x18000f1ff  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x18000f206  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x18000f20b  test    al, al
0x18000f20d  jz      short loc_18000F27A
0x18000f20f  mov     rax, cs:Feature_Standalone_26_02_NonSec__descriptor
0x18000f216  mov     r8d, [rax]
0x18000f219  test    r8b, 4
0x18000f21d  jnz     short loc_18000F234
0x18000f21f  lea     rdx, [rsp+58h+arg_8]
0x18000f224  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)
0x18000f229  mov     rcx, [rax]
0x18000f22c  mov     [rsp+58h+arg_8], rcx
0x18000f231  mov     r8d, ecx
0x18000f234  xor     eax, eax
0x18000f236  mov     word ptr [rsp+58h+arg_0+4], 3
0x18000f23d  mov     r9d, r8d
0x18000f240  mov     [rsp+58h+var_28], eax
0x18000f244  mov     dword ptr [rsp+58h+arg_0], eax
0x18000f248  lea     rcx, qword_180026050
0x18000f24f  shr     r9d, 0Bh
0x18000f253  lea     rax, [rsp+58h+arg_0]
0x18000f258  shr     r8d, 0Ah
0x18000f25c  and     r9d, edi
0x18000f25f  and     r8d, edi
0x18000f262  mov     [rsp+58h+var_30], edi
0x18000f266  mov     edx, 37E287Eh
0x18000f26b  mov     [rsp+58h+var_38], rax
0x18000f270  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000f275  mov     dl, dil
0x18000f278  jmp     short loc_18000F27C
0x18000f27a  xor     dl, dl
0x18000f27c  test    sil, sil
0x18000f27f  jz      short loc_18000F289
0x18000f281  test    dl, dl
0x18000f283  jnz     short loc_18000F289
0x18000f285  btr     dword ptr [rbx], 0Ah
0x18000f289  mov     eax, [rbx]
0x18000f28b  test    bpl, al
0x18000f28e  jz      short loc_18000F294
0x18000f290  test    dl, dl
0x18000f292  jnz     short loc_18000F296
0x18000f294  xor     edi, edi
0x18000f296  and     eax, 0FFFFFFFEh
0x18000f299  or      eax, edi
0x18000f29b  mov     [rbx], eax
0x18000f29d  mov     rax, rbx
0x18000f2a0  mov     rbx, [rsp+58h+arg_10]
0x18000f2a5  add     rsp, 40h
0x18000f2a9  pop     rdi
0x18000f2aa  pop     rsi
0x18000f2ab  pop     rbp
0x18000f2ac  retn
```
