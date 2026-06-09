# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x140005b90`
- end: `0x140005cf9`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140005554`

## callees

- `0x14000526c`
- `0x140005b90`
- `0x140009590`
- `0x14000b7ac`
- `0x140012010`

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
  wil::details *v13; // rcx
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
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_140019860, 45036797, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
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
0x140005b90  mov     [rsp+arg_10], rbx
0x140005b95  mov     [rsp+arg_0], rcx
0x140005b9a  push    rbp
0x140005b9b  push    rsi
0x140005b9c  push    rdi
0x140005b9d  sub     rsp, 40h
0x140005ba1  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140005ba8  mov     rbx, rdx
0x140005bab  test    rax, rax
0x140005bae  jz      short loc_140005BC3
0x140005bb0  mov     edx, 3
0x140005bb5  mov     ecx, 3667CADh
0x140005bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005bbf  mov     edx, eax
0x140005bc1  jmp     short loc_140005BD1
0x140005bc3  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140005bca  test    rax, rax
0x140005bcd  jnz     short loc_140005BB0
0x140005bcf  xor     edx, edx
0x140005bd1  mov     r8d, edx
0x140005bd4  mov     qword ptr [rbx], 0
0x140005bdb  and     r8d, 0FFFFFF3Fh
0x140005be2  mov     eax, edx
0x140005be4  and     edx, 80h
0x140005bea  mov     ecx, r8d
0x140005bed  and     ecx, 3
0x140005bf0  mov     ebp, 40h ; '@'
0x140005bf5  shl     ecx, 2
0x140005bf8  and     eax, ebp
0x140005bfa  or      ecx, eax
0x140005bfc  shl     ecx, 2
0x140005bff  or      ecx, edx
0x140005c01  shl     ecx, 3
0x140005c04  test    r8d, r8d
0x140005c07  jnz     short loc_140005C10
0x140005c09  mov     edx, ebp
0x140005c0b  mov     r8d, ebp
0x140005c0e  jmp     short loc_140005C1C
0x140005c10  xor     edx, edx
0x140005c12  cmp     r8d, 2
0x140005c16  cmovz   edx, ebp
0x140005c19  mov     r8d, edx
0x140005c1c  mov     eax, ecx
0x140005c1e  mov     edi, 1
0x140005c23  or      eax, r8d
0x140005c26  or      ecx, edx
0x140005c28  mov     [rbx], eax
0x140005c2a  bt      ecx, 0Ah
0x140005c2e  jnb     short loc_140005C3D
0x140005c30  cmp     ecx, 800h
0x140005c36  jb      short loc_140005C3D
0x140005c38  mov     sil, dil
0x140005c3b  jmp     short loc_140005C4B
0x140005c3d  xor     sil, sil
0x140005c40  xor     dl, dl
0x140005c42  test    bpl, cl
0x140005c45  jz      loc_140005CD5
0x140005c4b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x140005c52  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x140005c57  test    al, al
0x140005c59  jz      short loc_140005CC6
0x140005c5b  mov     rax, cs:Feature_Standalone_25_11_NonSec__descriptor
0x140005c62  mov     r8d, [rax]
0x140005c65  test    r8b, 4
0x140005c69  jnz     short loc_140005C80
0x140005c6b  lea     rdx, [rsp+58h+arg_8]
0x140005c70  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)
0x140005c75  mov     rcx, [rax]
0x140005c78  mov     [rsp+58h+arg_8], rcx
0x140005c7d  mov     r8d, ecx
0x140005c80  xor     eax, eax
0x140005c82  mov     word ptr [rsp+58h+arg_0+4], 3
0x140005c89  mov     r9d, r8d
0x140005c8c  mov     [rsp+58h+var_28], eax
0x140005c90  mov     dword ptr [rsp+58h+arg_0], eax
0x140005c94  lea     rcx, qword_140019860
0x140005c9b  shr     r9d, 0Bh
0x140005c9f  lea     rax, [rsp+58h+arg_0]
0x140005ca4  shr     r8d, 0Ah
0x140005ca8  and     r9d, edi
0x140005cab  and     r8d, edi
0x140005cae  mov     [rsp+58h+var_30], edi
0x140005cb2  mov     edx, 2AF34FDh
0x140005cb7  mov     [rsp+58h+var_38], rax
0x140005cbc  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x140005cc1  mov     dl, dil
0x140005cc4  jmp     short loc_140005CC8
0x140005cc6  xor     dl, dl
0x140005cc8  test    sil, sil
0x140005ccb  jz      short loc_140005CD5
0x140005ccd  test    dl, dl
0x140005ccf  jnz     short loc_140005CD5
0x140005cd1  btr     dword ptr [rbx], 0Ah
0x140005cd5  mov     eax, [rbx]
0x140005cd7  test    bpl, al
0x140005cda  jz      short loc_140005CE0
0x140005cdc  test    dl, dl
0x140005cde  jnz     short loc_140005CE2
0x140005ce0  xor     edi, edi
0x140005ce2  and     eax, 0FFFFFFFEh
0x140005ce5  or      eax, edi
0x140005ce7  mov     [rbx], eax
0x140005ce9  mov     rax, rbx
0x140005cec  mov     rbx, [rsp+58h+arg_10]
0x140005cf1  add     rsp, 40h
0x140005cf5  pop     rdi
0x140005cf6  pop     rsi
0x140005cf7  pop     rbp
0x140005cf8  retn
```
