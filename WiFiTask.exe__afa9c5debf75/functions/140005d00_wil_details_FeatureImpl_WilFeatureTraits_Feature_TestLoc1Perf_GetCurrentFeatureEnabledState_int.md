# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x140005d00`
- end: `0x140005e69`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140005634`

## callees

- `0x1400053e0`
- `0x140005d00`
- `0x140009590`
- `0x14000b674`
- `0x140012010`

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
    LOBYTE(v7) = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_22;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_140019890, 58599532, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
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
0x140005d00  mov     [rsp+arg_10], rbx
0x140005d05  mov     [rsp+arg_0], rcx
0x140005d0a  push    rbp
0x140005d0b  push    rsi
0x140005d0c  push    rdi
0x140005d0d  sub     rsp, 40h
0x140005d11  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140005d18  mov     rbx, rdx
0x140005d1b  test    rax, rax
0x140005d1e  jz      short loc_140005D33
0x140005d20  mov     edx, 3
0x140005d25  mov     ecx, 38419ACh
0x140005d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d2f  mov     edx, eax
0x140005d31  jmp     short loc_140005D41
0x140005d33  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140005d3a  test    rax, rax
0x140005d3d  jnz     short loc_140005D20
0x140005d3f  xor     edx, edx
0x140005d41  mov     r8d, edx
0x140005d44  mov     qword ptr [rbx], 0
0x140005d4b  and     r8d, 0FFFFFF3Fh
0x140005d52  mov     eax, edx
0x140005d54  and     edx, 80h
0x140005d5a  mov     ecx, r8d
0x140005d5d  and     ecx, 3
0x140005d60  mov     ebp, 40h ; '@'
0x140005d65  shl     ecx, 2
0x140005d68  and     eax, ebp
0x140005d6a  or      ecx, eax
0x140005d6c  shl     ecx, 2
0x140005d6f  or      ecx, edx
0x140005d71  shl     ecx, 3
0x140005d74  test    r8d, r8d
0x140005d77  jnz     short loc_140005D80
0x140005d79  mov     edx, ebp
0x140005d7b  mov     r8d, ebp
0x140005d7e  jmp     short loc_140005D8C
0x140005d80  xor     edx, edx
0x140005d82  cmp     r8d, 2
0x140005d86  cmovz   edx, ebp
0x140005d89  mov     r8d, edx
0x140005d8c  mov     eax, ecx
0x140005d8e  mov     edi, 1
0x140005d93  or      eax, r8d
0x140005d96  or      ecx, edx
0x140005d98  mov     [rbx], eax
0x140005d9a  bt      ecx, 0Ah
0x140005d9e  jnb     short loc_140005DAD
0x140005da0  cmp     ecx, 800h
0x140005da6  jb      short loc_140005DAD
0x140005da8  mov     sil, dil
0x140005dab  jmp     short loc_140005DBB
0x140005dad  xor     sil, sil
0x140005db0  xor     dl, dl
0x140005db2  test    bpl, cl
0x140005db5  jz      loc_140005E45
0x140005dbb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x140005dc2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x140005dc7  test    al, al
0x140005dc9  jz      short loc_140005E36
0x140005dcb  mov     rax, cs:Feature_Standalone_26_01_NonSec__descriptor
0x140005dd2  mov     r8d, [rax]
0x140005dd5  test    r8b, 4
0x140005dd9  jnz     short loc_140005DF0
0x140005ddb  lea     rdx, [rsp+58h+arg_8]
0x140005de0  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)
0x140005de5  mov     rcx, [rax]
0x140005de8  mov     [rsp+58h+arg_8], rcx
0x140005ded  mov     r8d, ecx
0x140005df0  xor     eax, eax
0x140005df2  mov     word ptr [rsp+58h+arg_0+4], 3
0x140005df9  mov     r9d, r8d
0x140005dfc  mov     [rsp+58h+var_28], eax
0x140005e00  mov     dword ptr [rsp+58h+arg_0], eax
0x140005e04  lea     rcx, qword_140019890
0x140005e0b  shr     r9d, 0Bh
0x140005e0f  lea     rax, [rsp+58h+arg_0]
0x140005e14  shr     r8d, 0Ah
0x140005e18  and     r9d, edi
0x140005e1b  and     r8d, edi
0x140005e1e  mov     [rsp+58h+var_30], edi
0x140005e22  mov     edx, 37E286Ch
0x140005e27  mov     [rsp+58h+var_38], rax
0x140005e2c  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x140005e31  mov     dl, dil
0x140005e34  jmp     short loc_140005E38
0x140005e36  xor     dl, dl
0x140005e38  test    sil, sil
0x140005e3b  jz      short loc_140005E45
0x140005e3d  test    dl, dl
0x140005e3f  jnz     short loc_140005E45
0x140005e41  btr     dword ptr [rbx], 0Ah
0x140005e45  mov     eax, [rbx]
0x140005e47  test    bpl, al
0x140005e4a  jz      short loc_140005E50
0x140005e4c  test    dl, dl
0x140005e4e  jnz     short loc_140005E52
0x140005e50  xor     edi, edi
0x140005e52  and     eax, 0FFFFFFFEh
0x140005e55  or      eax, edi
0x140005e57  mov     [rbx], eax
0x140005e59  mov     rax, rbx
0x140005e5c  mov     rbx, [rsp+58h+arg_10]
0x140005e61  add     rsp, 40h
0x140005e65  pop     rdi
0x140005e66  pop     rsi
0x140005e67  pop     rbp
0x140005e68  retn
```
