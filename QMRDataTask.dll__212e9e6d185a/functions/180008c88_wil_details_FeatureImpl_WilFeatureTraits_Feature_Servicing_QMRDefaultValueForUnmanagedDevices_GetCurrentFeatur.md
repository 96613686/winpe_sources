# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180008c88`
- end: `0x180008dca`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180007ed0`

## callees

- `0x1800086f8`
- `0x180008c88`
- `0x18000dc68`
- `0x180015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::GetCurrentFeatureEnabledState(
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
    v4 = v2(56157648, 3);
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
    v13 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor & 4) == 0 )
    {
      v16 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
               v11,
               &v16);
      v13 = v16;
    }
    WORD2(v15) = 3;
    LODWORD(v15) = 0;
    wil::details::ReportUsageToService(
      (__int64)&unk_180024010,
      0x37E287Eu,
      (v13 >> 10) & 1,
      (v13 >> 11) & 1,
      (__int64)&v15,
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
0x180008c88  mov     [rsp+arg_10], rbx
0x180008c8d  mov     [rsp+arg_18], rsi
0x180008c92  mov     [rsp+arg_0], rcx
0x180008c97  push    rdi
0x180008c98  sub     rsp, 40h
0x180008c9c  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180008ca3  mov     rbx, rdx
0x180008ca6  test    rax, rax
0x180008ca9  jz      short loc_180008CBE
0x180008cab  mov     edx, 3
0x180008cb0  mov     ecx, 358E5D0h
0x180008cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cba  mov     edx, eax
0x180008cbc  jmp     short loc_180008CCC
0x180008cbe  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180008cc5  test    rax, rax
0x180008cc8  jnz     short loc_180008CAB
0x180008cca  xor     edx, edx
0x180008ccc  mov     r8d, edx
0x180008ccf  mov     qword ptr [rbx], 0
0x180008cd6  and     r8d, 0FFFFFF3Fh
0x180008cdd  mov     eax, edx
0x180008cdf  and     edx, 80h
0x180008ce5  mov     ecx, r8d
0x180008ce8  and     ecx, 3
0x180008ceb  mov     esi, 40h ; '@'
0x180008cf0  shl     ecx, 2
0x180008cf3  and     eax, esi
0x180008cf5  or      ecx, eax
0x180008cf7  shl     ecx, 2
0x180008cfa  or      ecx, edx
0x180008cfc  shl     ecx, 3
0x180008cff  test    r8d, r8d
0x180008d02  jnz     short loc_180008D0B
0x180008d04  mov     edx, esi
0x180008d06  mov     r8d, esi
0x180008d09  jmp     short loc_180008D17
0x180008d0b  xor     edx, edx
0x180008d0d  cmp     r8d, 2
0x180008d11  cmovz   edx, esi
0x180008d14  mov     r8d, edx
0x180008d17  mov     eax, ecx
0x180008d19  mov     edi, 1
0x180008d1e  or      eax, r8d
0x180008d21  or      ecx, edx
0x180008d23  mov     [rbx], eax
0x180008d25  bt      ecx, 0Ah
0x180008d29  jnb     short loc_180008D33
0x180008d2b  cmp     ecx, 800h
0x180008d31  jnb     short loc_180008D3A
0x180008d33  xor     dl, dl
0x180008d35  test    sil, cl
0x180008d38  jz      short loc_180008DA3
0x180008d3a  mov     rax, cs:Feature_Standalone_26_02_NonSec__descriptor
0x180008d41  mov     r8d, [rax]
0x180008d44  test    r8b, 4
0x180008d48  jnz     short loc_180008D5F
0x180008d4a  lea     rdx, [rsp+48h+arg_8]
0x180008d4f  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)
0x180008d54  mov     rcx, [rax]
0x180008d57  mov     [rsp+48h+arg_8], rcx
0x180008d5c  mov     r8d, ecx
0x180008d5f  xor     eax, eax
0x180008d61  mov     word ptr [rsp+48h+arg_0+4], 3
0x180008d68  mov     r9d, r8d
0x180008d6b  mov     [rsp+48h+var_18], eax
0x180008d6f  mov     dword ptr [rsp+48h+arg_0], eax
0x180008d73  lea     rcx, unk_180024010
0x180008d7a  shr     r9d, 0Bh
0x180008d7e  lea     rax, [rsp+48h+arg_0]
0x180008d83  shr     r8d, 0Ah
0x180008d87  and     r9d, edi
0x180008d8a  and     r8d, edi
0x180008d8d  mov     [rsp+48h+var_20], edi
0x180008d91  mov     edx, 37E287Eh
0x180008d96  mov     [rsp+48h+var_28], rax
0x180008d9b  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180008da0  mov     dl, dil
0x180008da3  mov     eax, [rbx]
0x180008da5  test    sil, al
0x180008da8  jz      short loc_180008DAE
0x180008daa  test    dl, dl
0x180008dac  jnz     short loc_180008DB0
0x180008dae  xor     edi, edi
0x180008db0  mov     rsi, [rsp+48h+arg_18]
0x180008db5  and     eax, 0FFFFFFFEh
0x180008db8  or      eax, edi
0x180008dba  mov     [rbx], eax
0x180008dbc  mov     rax, rbx
0x180008dbf  mov     rbx, [rsp+48h+arg_10]
0x180008dc4  add     rsp, 40h
0x180008dc8  pop     rdi
0x180008dc9  retn
```
