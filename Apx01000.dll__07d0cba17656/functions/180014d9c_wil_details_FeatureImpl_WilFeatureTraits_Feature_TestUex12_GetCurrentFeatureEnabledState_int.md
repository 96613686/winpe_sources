# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180014d9c`
- end: `0x180014f05`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180013ed8`

## callees

- `0x18000ab68`
- `0x180013ac4`
- `0x180014d9c`
- `0x180015748`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCurrentFeatureEnabledState(
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
    v4 = v2(58989070, 3);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_04_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_04_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_1800337D8, 58599559, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
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
0x180014d9c  mov     [rsp+arg_10], rbx
0x180014da1  mov     [rsp+arg_0], rcx
0x180014da6  push    rbp
0x180014da7  push    rsi
0x180014da8  push    rdi
0x180014da9  sub     rsp, 40h
0x180014dad  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180014db4  mov     rbx, rdx
0x180014db7  test    rax, rax
0x180014dba  jz      short loc_180014DCF
0x180014dbc  mov     edx, 3
0x180014dc1  mov     ecx, 3841A0Eh
0x180014dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dcb  mov     edx, eax
0x180014dcd  jmp     short loc_180014DDD
0x180014dcf  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180014dd6  test    rax, rax
0x180014dd9  jnz     short loc_180014DBC
0x180014ddb  xor     edx, edx
0x180014ddd  mov     r8d, edx
0x180014de0  mov     qword ptr [rbx], 0
0x180014de7  and     r8d, 0FFFFFF3Fh
0x180014dee  mov     eax, edx
0x180014df0  and     edx, 80h
0x180014df6  mov     ecx, r8d
0x180014df9  and     ecx, 3
0x180014dfc  mov     ebp, 40h ; '@'
0x180014e01  shl     ecx, 2
0x180014e04  and     eax, ebp
0x180014e06  or      ecx, eax
0x180014e08  shl     ecx, 2
0x180014e0b  or      ecx, edx
0x180014e0d  shl     ecx, 3
0x180014e10  test    r8d, r8d
0x180014e13  jnz     short loc_180014E1C
0x180014e15  mov     edx, ebp
0x180014e17  mov     r8d, ebp
0x180014e1a  jmp     short loc_180014E28
0x180014e1c  xor     edx, edx
0x180014e1e  cmp     r8d, 2
0x180014e22  cmovz   edx, ebp
0x180014e25  mov     r8d, edx
0x180014e28  mov     eax, ecx
0x180014e2a  mov     edi, 1
0x180014e2f  or      eax, r8d
0x180014e32  or      ecx, edx
0x180014e34  mov     [rbx], eax
0x180014e36  bt      ecx, 0Ah
0x180014e3a  jnb     short loc_180014E49
0x180014e3c  cmp     ecx, 800h
0x180014e42  jb      short loc_180014E49
0x180014e44  mov     sil, dil
0x180014e47  jmp     short loc_180014E57
0x180014e49  xor     sil, sil
0x180014e4c  xor     dl, dl
0x180014e4e  test    bpl, cl
0x180014e51  jz      loc_180014EE1
0x180014e57  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UexTest7@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7> `wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl(void)'::`2'::impl
0x180014e5e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(wil::ReportingKind)
0x180014e63  test    al, al
0x180014e65  jz      short loc_180014ED2
0x180014e67  mov     rax, cs:Feature_Standalone_26_04_NonSec__descriptor
0x180014e6e  mov     r8d, [rax]
0x180014e71  test    r8b, 4
0x180014e75  jnz     short loc_180014E8C
0x180014e77  lea     rdx, [rsp+58h+arg_8]
0x180014e7c  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_04_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(void)
0x180014e81  mov     rcx, [rax]
0x180014e84  mov     [rsp+58h+arg_8], rcx
0x180014e89  mov     r8d, ecx
0x180014e8c  xor     eax, eax
0x180014e8e  mov     word ptr [rsp+58h+arg_0+4], 3
0x180014e95  mov     r9d, r8d
0x180014e98  mov     [rsp+58h+var_28], eax
0x180014e9c  mov     dword ptr [rsp+58h+arg_0], eax
0x180014ea0  lea     rcx, qword_1800337D8
0x180014ea7  shr     r9d, 0Bh
0x180014eab  lea     rax, [rsp+58h+arg_0]
0x180014eb0  shr     r8d, 0Ah
0x180014eb4  and     r9d, edi
0x180014eb7  and     r8d, edi
0x180014eba  mov     [rsp+58h+var_30], edi
0x180014ebe  mov     edx, 37E2887h
0x180014ec3  mov     [rsp+58h+var_38], rax
0x180014ec8  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180014ecd  mov     dl, dil
0x180014ed0  jmp     short loc_180014ED4
0x180014ed2  xor     dl, dl
0x180014ed4  test    sil, sil
0x180014ed7  jz      short loc_180014EE1
0x180014ed9  test    dl, dl
0x180014edb  jnz     short loc_180014EE1
0x180014edd  btr     dword ptr [rbx], 0Ah
0x180014ee1  mov     eax, [rbx]
0x180014ee3  test    bpl, al
0x180014ee6  jz      short loc_180014EEC
0x180014ee8  test    dl, dl
0x180014eea  jnz     short loc_180014EEE
0x180014eec  xor     edi, edi
0x180014eee  and     eax, 0FFFFFFFEh
0x180014ef1  or      eax, edi
0x180014ef3  mov     [rbx], eax
0x180014ef5  mov     rax, rbx
0x180014ef8  mov     rbx, [rsp+58h+arg_10]
0x180014efd  add     rsp, 40h
0x180014f01  pop     rdi
0x180014f02  pop     rsi
0x180014f03  pop     rbp
0x180014f04  retn
```
