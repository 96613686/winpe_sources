# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001494c`
- end: `0x180014ab5`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180013c38`

## callees

- `0x18000ab68`
- `0x1800137dc`
- `0x18001494c`
- `0x180015610`
- `0x18002a010`

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
                          `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl'::`2'::impl,
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
    wil::details::ReportUsageToService(&qword_1800337B8, 58599550, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
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
0x18001494c  mov     [rsp+arg_10], rbx
0x180014951  mov     [rsp+arg_0], rcx
0x180014956  push    rbp
0x180014957  push    rsi
0x180014958  push    rdi
0x180014959  sub     rsp, 40h
0x18001495d  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180014964  mov     rbx, rdx
0x180014967  test    rax, rax
0x18001496a  jz      short loc_18001497F
0x18001496c  mov     edx, 3
0x180014971  mov     ecx, 38419CAh
0x180014976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001497b  mov     edx, eax
0x18001497d  jmp     short loc_18001498D
0x18001497f  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180014986  test    rax, rax
0x180014989  jnz     short loc_18001496C
0x18001498b  xor     edx, edx
0x18001498d  mov     r8d, edx
0x180014990  mov     qword ptr [rbx], 0
0x180014997  and     r8d, 0FFFFFF3Fh
0x18001499e  mov     eax, edx
0x1800149a0  and     edx, 80h
0x1800149a6  mov     ecx, r8d
0x1800149a9  and     ecx, 3
0x1800149ac  mov     ebp, 40h ; '@'
0x1800149b1  shl     ecx, 2
0x1800149b4  and     eax, ebp
0x1800149b6  or      ecx, eax
0x1800149b8  shl     ecx, 2
0x1800149bb  or      ecx, edx
0x1800149bd  shl     ecx, 3
0x1800149c0  test    r8d, r8d
0x1800149c3  jnz     short loc_1800149CC
0x1800149c5  mov     edx, ebp
0x1800149c7  mov     r8d, ebp
0x1800149ca  jmp     short loc_1800149D8
0x1800149cc  xor     edx, edx
0x1800149ce  cmp     r8d, 2
0x1800149d2  cmovz   edx, ebp
0x1800149d5  mov     r8d, edx
0x1800149d8  mov     eax, ecx
0x1800149da  mov     edi, 1
0x1800149df  or      eax, r8d
0x1800149e2  or      ecx, edx
0x1800149e4  mov     [rbx], eax
0x1800149e6  bt      ecx, 0Ah
0x1800149ea  jnb     short loc_1800149F9
0x1800149ec  cmp     ecx, 800h
0x1800149f2  jb      short loc_1800149F9
0x1800149f4  mov     sil, dil
0x1800149f7  jmp     short loc_180014A07
0x1800149f9  xor     sil, sil
0x1800149fc  xor     dl, dl
0x1800149fe  test    bpl, cl
0x180014a01  jz      loc_180014A91
0x180014a07  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x180014a0e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x180014a13  test    al, al
0x180014a15  jz      short loc_180014A82
0x180014a17  mov     rax, cs:Feature_Standalone_26_02_NonSec__descriptor
0x180014a1e  mov     r8d, [rax]
0x180014a21  test    r8b, 4
0x180014a25  jnz     short loc_180014A3C
0x180014a27  lea     rdx, [rsp+58h+arg_8]
0x180014a2c  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)
0x180014a31  mov     rcx, [rax]
0x180014a34  mov     [rsp+58h+arg_8], rcx
0x180014a39  mov     r8d, ecx
0x180014a3c  xor     eax, eax
0x180014a3e  mov     word ptr [rsp+58h+arg_0+4], 3
0x180014a45  mov     r9d, r8d
0x180014a48  mov     [rsp+58h+var_28], eax
0x180014a4c  mov     dword ptr [rsp+58h+arg_0], eax
0x180014a50  lea     rcx, qword_1800337B8
0x180014a57  shr     r9d, 0Bh
0x180014a5b  lea     rax, [rsp+58h+arg_0]
0x180014a60  shr     r8d, 0Ah
0x180014a64  and     r9d, edi
0x180014a67  and     r8d, edi
0x180014a6a  mov     [rsp+58h+var_30], edi
0x180014a6e  mov     edx, 37E287Eh
0x180014a73  mov     [rsp+58h+var_38], rax
0x180014a78  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180014a7d  mov     dl, dil
0x180014a80  jmp     short loc_180014A84
0x180014a82  xor     dl, dl
0x180014a84  test    sil, sil
0x180014a87  jz      short loc_180014A91
0x180014a89  test    dl, dl
0x180014a8b  jnz     short loc_180014A91
0x180014a8d  btr     dword ptr [rbx], 0Ah
0x180014a91  mov     eax, [rbx]
0x180014a93  test    bpl, al
0x180014a96  jz      short loc_180014A9C
0x180014a98  test    dl, dl
0x180014a9a  jnz     short loc_180014A9E
0x180014a9c  xor     edi, edi
0x180014a9e  and     eax, 0FFFFFFFEh
0x180014aa1  or      eax, edi
0x180014aa3  mov     [rbx], eax
0x180014aa5  mov     rax, rbx
0x180014aa8  mov     rbx, [rsp+58h+arg_10]
0x180014aad  add     rsp, 40h
0x180014ab1  pop     rdi
0x180014ab2  pop     rsi
0x180014ab3  pop     rbp
0x180014ab4  retn
```
