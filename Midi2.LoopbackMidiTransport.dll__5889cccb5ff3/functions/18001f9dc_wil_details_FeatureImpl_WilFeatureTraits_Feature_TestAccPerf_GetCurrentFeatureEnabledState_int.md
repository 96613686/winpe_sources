# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001f9dc`
- end: `0x18001fb45`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001f28c`

## callees

- `0x18001ea68`
- `0x18001f9dc`
- `0x180020aa4`
- `0x1800216d4`
- `0x180032010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(
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
  __int64 v13; // rcx
  unsigned int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v16 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(57048237, 3);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor & 4) == 0 )
    {
      v17 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
                         v13,
                         &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_18005FDD8,
      0x2AF34FDu,
      (v14 >> 10) & 1,
      (v14 >> 11) & 1,
      (__int64)&v16,
      1u,
      0);
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
0x18001f9dc  mov     [rsp+arg_10], rbx
0x18001f9e1  mov     [rsp+arg_0], rcx
0x18001f9e6  push    rbp
0x18001f9e7  push    rsi
0x18001f9e8  push    rdi
0x18001f9e9  sub     rsp, 40h
0x18001f9ed  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001f9f4  mov     rbx, rdx
0x18001f9f7  test    rax, rax
0x18001f9fa  jz      short loc_18001FA0F
0x18001f9fc  mov     edx, 3
0x18001fa01  mov     ecx, 3667CADh
0x18001fa06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa0b  mov     edx, eax
0x18001fa0d  jmp     short loc_18001FA1D
0x18001fa0f  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001fa16  test    rax, rax
0x18001fa19  jnz     short loc_18001F9FC
0x18001fa1b  xor     edx, edx
0x18001fa1d  mov     r8d, edx
0x18001fa20  mov     qword ptr [rbx], 0
0x18001fa27  and     r8d, 0FFFFFF3Fh
0x18001fa2e  mov     eax, edx
0x18001fa30  and     edx, 80h
0x18001fa36  mov     ecx, r8d
0x18001fa39  and     ecx, 3
0x18001fa3c  mov     ebp, 40h ; '@'
0x18001fa41  shl     ecx, 2
0x18001fa44  and     eax, ebp
0x18001fa46  or      ecx, eax
0x18001fa48  shl     ecx, 2
0x18001fa4b  or      ecx, edx
0x18001fa4d  shl     ecx, 3
0x18001fa50  test    r8d, r8d
0x18001fa53  jnz     short loc_18001FA5C
0x18001fa55  mov     edx, ebp
0x18001fa57  mov     r8d, ebp
0x18001fa5a  jmp     short loc_18001FA68
0x18001fa5c  xor     edx, edx
0x18001fa5e  cmp     r8d, 2
0x18001fa62  cmovz   edx, ebp
0x18001fa65  mov     r8d, edx
0x18001fa68  mov     eax, ecx
0x18001fa6a  mov     edi, 1
0x18001fa6f  or      eax, r8d
0x18001fa72  or      ecx, edx
0x18001fa74  mov     [rbx], eax
0x18001fa76  bt      ecx, 0Ah
0x18001fa7a  jnb     short loc_18001FA89
0x18001fa7c  cmp     ecx, 800h
0x18001fa82  jb      short loc_18001FA89
0x18001fa84  mov     sil, dil
0x18001fa87  jmp     short loc_18001FA97
0x18001fa89  xor     sil, sil
0x18001fa8c  xor     dl, dl
0x18001fa8e  test    bpl, cl
0x18001fa91  jz      loc_18001FB21
0x18001fa97  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x18001fa9e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x18001faa3  test    al, al
0x18001faa5  jz      short loc_18001FB12
0x18001faa7  mov     rax, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18001faae  mov     r8d, [rax]
0x18001fab1  test    r8b, 4
0x18001fab5  jnz     short loc_18001FACC
0x18001fab7  lea     rdx, [rsp+58h+arg_8]
0x18001fabc  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)
0x18001fac1  mov     rcx, [rax]
0x18001fac4  mov     [rsp+58h+arg_8], rcx
0x18001fac9  mov     r8d, ecx
0x18001facc  xor     eax, eax
0x18001face  mov     word ptr [rsp+58h+arg_0+4], 3
0x18001fad5  mov     r9d, r8d
0x18001fad8  mov     [rsp+58h+var_28], eax
0x18001fadc  mov     dword ptr [rsp+58h+arg_0], eax
0x18001fae0  lea     rcx, qword_18005FDD8
0x18001fae7  shr     r9d, 0Bh
0x18001faeb  lea     rax, [rsp+58h+arg_0]
0x18001faf0  shr     r8d, 0Ah
0x18001faf4  and     r9d, edi
0x18001faf7  and     r8d, edi
0x18001fafa  mov     [rsp+58h+var_30], edi
0x18001fafe  mov     edx, 2AF34FDh
0x18001fb03  mov     [rsp+58h+var_38], rax
0x18001fb08  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18001fb0d  mov     dl, dil
0x18001fb10  jmp     short loc_18001FB14
0x18001fb12  xor     dl, dl
0x18001fb14  test    sil, sil
0x18001fb17  jz      short loc_18001FB21
0x18001fb19  test    dl, dl
0x18001fb1b  jnz     short loc_18001FB21
0x18001fb1d  btr     dword ptr [rbx], 0Ah
0x18001fb21  mov     eax, [rbx]
0x18001fb23  test    bpl, al
0x18001fb26  jz      short loc_18001FB2C
0x18001fb28  test    dl, dl
0x18001fb2a  jnz     short loc_18001FB2E
0x18001fb2c  xor     edi, edi
0x18001fb2e  and     eax, 0FFFFFFFEh
0x18001fb31  or      eax, edi
0x18001fb33  mov     [rbx], eax
0x18001fb35  mov     rax, rbx
0x18001fb38  mov     rbx, [rsp+58h+arg_10]
0x18001fb3d  add     rsp, 40h
0x18001fb41  pop     rdi
0x18001fb42  pop     rsi
0x18001fb43  pop     rbp
0x18001fb44  retn
```
