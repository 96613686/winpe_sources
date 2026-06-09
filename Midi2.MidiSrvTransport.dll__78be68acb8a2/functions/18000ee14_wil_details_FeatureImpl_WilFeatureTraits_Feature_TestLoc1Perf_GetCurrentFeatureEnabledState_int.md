# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000ee14`
- end: `0x18000ef7d`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000e6e4`

## callees

- `0x18000e23c`
- `0x18000ee14`
- `0x18000fdb4`
- `0x180011458`
- `0x180015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  int v7; // edx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  unsigned int v11; // ecx
  char v12; // si
  char v13; // dl
  __int64 v14; // rcx
  unsigned int v15; // r8d
  __int64 v17; // [rsp+60h] [rbp+8h] BYREF
  __int64 v18; // [rsp+68h] [rbp+10h] BYREF

  v17 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(58988972, 3);
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
    v13 = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_22;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl'::`2'::impl) )
  {
    v15 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor & 4) == 0 )
    {
      v18 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
                         v14,
                         &v18);
      v15 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_18001E890,
      0x37E286Cu,
      (v15 >> 10) & 1,
      (v15 >> 11) & 1,
      (__int64)&v17,
      1u,
      0);
    v13 = 1;
  }
  else
  {
    v13 = 0;
  }
  if ( v12 && !v13 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_22:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v13 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x18000ee14  mov     [rsp+arg_10], rbx
0x18000ee19  mov     [rsp+arg_0], rcx
0x18000ee1e  push    rbp
0x18000ee1f  push    rsi
0x18000ee20  push    rdi
0x18000ee21  sub     rsp, 40h
0x18000ee25  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000ee2c  mov     rbx, rdx
0x18000ee2f  test    rax, rax
0x18000ee32  jz      short loc_18000EE47
0x18000ee34  mov     edx, 3
0x18000ee39  mov     ecx, 38419ACh
0x18000ee3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee43  mov     edx, eax
0x18000ee45  jmp     short loc_18000EE55
0x18000ee47  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000ee4e  test    rax, rax
0x18000ee51  jnz     short loc_18000EE34
0x18000ee53  xor     edx, edx
0x18000ee55  mov     r8d, edx
0x18000ee58  mov     qword ptr [rbx], 0
0x18000ee5f  and     r8d, 0FFFFFF3Fh
0x18000ee66  mov     eax, edx
0x18000ee68  and     edx, 80h
0x18000ee6e  mov     ecx, r8d
0x18000ee71  and     ecx, 3
0x18000ee74  mov     ebp, 40h ; '@'
0x18000ee79  shl     ecx, 2
0x18000ee7c  and     eax, ebp
0x18000ee7e  or      ecx, eax
0x18000ee80  shl     ecx, 2
0x18000ee83  or      ecx, edx
0x18000ee85  shl     ecx, 3
0x18000ee88  test    r8d, r8d
0x18000ee8b  jnz     short loc_18000EE94
0x18000ee8d  mov     edx, ebp
0x18000ee8f  mov     r8d, ebp
0x18000ee92  jmp     short loc_18000EEA0
0x18000ee94  xor     edx, edx
0x18000ee96  cmp     r8d, 2
0x18000ee9a  cmovz   edx, ebp
0x18000ee9d  mov     r8d, edx
0x18000eea0  mov     eax, ecx
0x18000eea2  mov     edi, 1
0x18000eea7  or      eax, r8d
0x18000eeaa  or      ecx, edx
0x18000eeac  mov     [rbx], eax
0x18000eeae  bt      ecx, 0Ah
0x18000eeb2  jnb     short loc_18000EEC1
0x18000eeb4  cmp     ecx, 800h
0x18000eeba  jb      short loc_18000EEC1
0x18000eebc  mov     sil, dil
0x18000eebf  jmp     short loc_18000EECF
0x18000eec1  xor     sil, sil
0x18000eec4  xor     dl, dl
0x18000eec6  test    bpl, cl
0x18000eec9  jz      loc_18000EF59
0x18000eecf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x18000eed6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x18000eedb  test    al, al
0x18000eedd  jz      short loc_18000EF4A
0x18000eedf  mov     rax, cs:Feature_Standalone_26_01_NonSec__descriptor
0x18000eee6  mov     r8d, [rax]
0x18000eee9  test    r8b, 4
0x18000eeed  jnz     short loc_18000EF04
0x18000eeef  lea     rdx, [rsp+58h+arg_8]
0x18000eef4  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)
0x18000eef9  mov     rcx, [rax]
0x18000eefc  mov     [rsp+58h+arg_8], rcx
0x18000ef01  mov     r8d, ecx
0x18000ef04  xor     eax, eax
0x18000ef06  mov     word ptr [rsp+58h+arg_0+4], 3
0x18000ef0d  mov     r9d, r8d
0x18000ef10  mov     [rsp+58h+var_28], eax
0x18000ef14  mov     dword ptr [rsp+58h+arg_0], eax
0x18000ef18  lea     rcx, qword_18001E890
0x18000ef1f  shr     r9d, 0Bh
0x18000ef23  lea     rax, [rsp+58h+arg_0]
0x18000ef28  shr     r8d, 0Ah
0x18000ef2c  and     r9d, edi
0x18000ef2f  and     r8d, edi
0x18000ef32  mov     [rsp+58h+var_30], edi
0x18000ef36  mov     edx, 37E286Ch
0x18000ef3b  mov     [rsp+58h+var_38], rax
0x18000ef40  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000ef45  mov     dl, dil
0x18000ef48  jmp     short loc_18000EF4C
0x18000ef4a  xor     dl, dl
0x18000ef4c  test    sil, sil
0x18000ef4f  jz      short loc_18000EF59
0x18000ef51  test    dl, dl
0x18000ef53  jnz     short loc_18000EF59
0x18000ef55  btr     dword ptr [rbx], 0Ah
0x18000ef59  mov     eax, [rbx]
0x18000ef5b  test    bpl, al
0x18000ef5e  jz      short loc_18000EF64
0x18000ef60  test    dl, dl
0x18000ef62  jnz     short loc_18000EF66
0x18000ef64  xor     edi, edi
0x18000ef66  and     eax, 0FFFFFFFEh
0x18000ef69  or      eax, edi
0x18000ef6b  mov     [rbx], eax
0x18000ef6d  mov     rax, rbx
0x18000ef70  mov     rbx, [rsp+58h+arg_10]
0x18000ef75  add     rsp, 40h
0x18000ef79  pop     rdi
0x18000ef7a  pop     rsi
0x18000ef7b  pop     rbp
0x18000ef7c  retn
```
