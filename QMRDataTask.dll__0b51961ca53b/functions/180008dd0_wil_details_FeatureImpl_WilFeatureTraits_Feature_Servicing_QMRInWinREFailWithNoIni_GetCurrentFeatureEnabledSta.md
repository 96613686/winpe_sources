# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180008dd0`
- end: `0x180008f12`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180007fb0`

## callees

- `0x180008584`
- `0x180008dd0`
- `0x18000dc68`
- `0x180015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni>::GetCurrentFeatureEnabledState(
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
  wil::details *v11; // rcx
  char v12; // dl
  unsigned int v13; // r8d
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF
  __int64 v16; // [rsp+58h] [rbp+10h] BYREF

  v15 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(59205909, 3);
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
    v13 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor & 4) == 0 )
    {
      v16 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
               v11,
               &v16);
      v13 = v16;
    }
    WORD2(v15) = 3;
    LODWORD(v15) = 0;
    wil::details::ReportUsageToService(&qword_180024040, 58599532, (v13 >> 10) & 1, (v13 >> 11) & 1, &v15, 1, 0);
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
0x180008dd0  mov     [rsp+arg_10], rbx
0x180008dd5  mov     [rsp+arg_18], rsi
0x180008dda  mov     [rsp+arg_0], rcx
0x180008ddf  push    rdi
0x180008de0  sub     rsp, 40h
0x180008de4  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180008deb  mov     rbx, rdx
0x180008dee  test    rax, rax
0x180008df1  jz      short loc_180008E06
0x180008df3  mov     edx, 3
0x180008df8  mov     ecx, 3876915h
0x180008dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e02  mov     edx, eax
0x180008e04  jmp     short loc_180008E14
0x180008e06  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180008e0d  test    rax, rax
0x180008e10  jnz     short loc_180008DF3
0x180008e12  xor     edx, edx
0x180008e14  mov     r8d, edx
0x180008e17  mov     qword ptr [rbx], 0
0x180008e1e  and     r8d, 0FFFFFF3Fh
0x180008e25  mov     eax, edx
0x180008e27  and     edx, 80h
0x180008e2d  mov     ecx, r8d
0x180008e30  and     ecx, 3
0x180008e33  mov     esi, 40h ; '@'
0x180008e38  shl     ecx, 2
0x180008e3b  and     eax, esi
0x180008e3d  or      ecx, eax
0x180008e3f  shl     ecx, 2
0x180008e42  or      ecx, edx
0x180008e44  shl     ecx, 3
0x180008e47  test    r8d, r8d
0x180008e4a  jnz     short loc_180008E53
0x180008e4c  mov     edx, esi
0x180008e4e  mov     r8d, esi
0x180008e51  jmp     short loc_180008E5F
0x180008e53  xor     edx, edx
0x180008e55  cmp     r8d, 2
0x180008e59  cmovz   edx, esi
0x180008e5c  mov     r8d, edx
0x180008e5f  mov     eax, ecx
0x180008e61  mov     edi, 1
0x180008e66  or      eax, r8d
0x180008e69  or      ecx, edx
0x180008e6b  mov     [rbx], eax
0x180008e6d  bt      ecx, 0Ah
0x180008e71  jnb     short loc_180008E7B
0x180008e73  cmp     ecx, 800h
0x180008e79  jnb     short loc_180008E82
0x180008e7b  xor     dl, dl
0x180008e7d  test    sil, cl
0x180008e80  jz      short loc_180008EEB
0x180008e82  mov     rax, cs:Feature_Standalone_26_01_NonSec__descriptor
0x180008e89  mov     r8d, [rax]
0x180008e8c  test    r8b, 4
0x180008e90  jnz     short loc_180008EA7
0x180008e92  lea     rdx, [rsp+48h+arg_8]
0x180008e97  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)
0x180008e9c  mov     rcx, [rax]
0x180008e9f  mov     [rsp+48h+arg_8], rcx
0x180008ea4  mov     r8d, ecx
0x180008ea7  xor     eax, eax
0x180008ea9  mov     word ptr [rsp+48h+arg_0+4], 3
0x180008eb0  mov     r9d, r8d
0x180008eb3  mov     [rsp+48h+var_18], eax
0x180008eb7  mov     dword ptr [rsp+48h+arg_0], eax
0x180008ebb  lea     rcx, qword_180024040
0x180008ec2  shr     r9d, 0Bh
0x180008ec6  lea     rax, [rsp+48h+arg_0]
0x180008ecb  shr     r8d, 0Ah
0x180008ecf  and     r9d, edi
0x180008ed2  and     r8d, edi
0x180008ed5  mov     [rsp+48h+var_20], edi
0x180008ed9  mov     edx, 37E286Ch
0x180008ede  mov     [rsp+48h+var_28], rax
0x180008ee3  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180008ee8  mov     dl, dil
0x180008eeb  mov     eax, [rbx]
0x180008eed  test    sil, al
0x180008ef0  jz      short loc_180008EF6
0x180008ef2  test    dl, dl
0x180008ef4  jnz     short loc_180008EF8
0x180008ef6  xor     edi, edi
0x180008ef8  mov     rsi, [rsp+48h+arg_18]
0x180008efd  and     eax, 0FFFFFFFEh
0x180008f00  or      eax, edi
0x180008f02  mov     [rbx], eax
0x180008f04  mov     rax, rbx
0x180008f07  mov     rbx, [rsp+48h+arg_10]
0x180008f0c  add     rsp, 40h
0x180008f10  pop     rdi
0x180008f11  retn
```
