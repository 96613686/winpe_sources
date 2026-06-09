# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001bdb8`
- end: `0x18001befa`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001bcd8`

## callees

- `0x18001b984`
- `0x18001bdb8`
- `0x18001c4a0`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
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
    v4 = v2(48433719, 3);
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
    v13 = *(_DWORD *)Feature_Standalone_Future__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_Future__descriptor & 4) == 0 )
    {
      v16 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
               v11,
               &v16);
      v13 = v16;
    }
    WORD2(v15) = 3;
    LODWORD(v15) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_18003AE48,
      0x2F29A04u,
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
0x18001bdb8  mov     [rsp+arg_10], rbx
0x18001bdbd  mov     [rsp+arg_18], rsi
0x18001bdc2  mov     [rsp+arg_0], rcx
0x18001bdc7  push    rdi
0x18001bdc8  sub     rsp, 40h
0x18001bdcc  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001bdd3  mov     rbx, rdx
0x18001bdd6  test    rax, rax
0x18001bdd9  jz      short loc_18001BDEE
0x18001bddb  mov     edx, 3
0x18001bde0  mov     ecx, 2E30A37h
0x18001bde5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdea  mov     edx, eax
0x18001bdec  jmp     short loc_18001BDFC
0x18001bdee  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001bdf5  test    rax, rax
0x18001bdf8  jnz     short loc_18001BDDB
0x18001bdfa  xor     edx, edx
0x18001bdfc  mov     r8d, edx
0x18001bdff  mov     qword ptr [rbx], 0
0x18001be06  and     r8d, 0FFFFFF3Fh
0x18001be0d  mov     eax, edx
0x18001be0f  and     edx, 80h
0x18001be15  mov     ecx, r8d
0x18001be18  and     ecx, 3
0x18001be1b  mov     esi, 40h ; '@'
0x18001be20  shl     ecx, 2
0x18001be23  and     eax, esi
0x18001be25  or      ecx, eax
0x18001be27  shl     ecx, 2
0x18001be2a  or      ecx, edx
0x18001be2c  shl     ecx, 3
0x18001be2f  test    r8d, r8d
0x18001be32  jnz     short loc_18001BE3B
0x18001be34  mov     edx, esi
0x18001be36  mov     r8d, esi
0x18001be39  jmp     short loc_18001BE47
0x18001be3b  xor     edx, edx
0x18001be3d  cmp     r8d, 2
0x18001be41  cmovz   edx, esi
0x18001be44  mov     r8d, edx
0x18001be47  mov     eax, ecx
0x18001be49  mov     edi, 1
0x18001be4e  or      eax, r8d
0x18001be51  or      ecx, edx
0x18001be53  mov     [rbx], eax
0x18001be55  bt      ecx, 0Ah
0x18001be59  jnb     short loc_18001BE63
0x18001be5b  cmp     ecx, 800h
0x18001be61  jnb     short loc_18001BE6A
0x18001be63  xor     dl, dl
0x18001be65  test    sil, cl
0x18001be68  jz      short loc_18001BED3
0x18001be6a  mov     rax, cs:Feature_Standalone_Future__descriptor
0x18001be71  mov     r8d, [rax]
0x18001be74  test    r8b, 4
0x18001be78  jnz     short loc_18001BE8F
0x18001be7a  lea     rdx, [rsp+48h+arg_8]
0x18001be7f  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)
0x18001be84  mov     rcx, [rax]
0x18001be87  mov     [rsp+48h+arg_8], rcx
0x18001be8c  mov     r8d, ecx
0x18001be8f  xor     eax, eax
0x18001be91  mov     word ptr [rsp+48h+arg_0+4], 3
0x18001be98  mov     r9d, r8d
0x18001be9b  mov     [rsp+48h+var_18], eax
0x18001be9f  mov     dword ptr [rsp+48h+arg_0], eax
0x18001bea3  lea     rcx, qword_18003AE48
0x18001beaa  shr     r9d, 0Bh
0x18001beae  lea     rax, [rsp+48h+arg_0]
0x18001beb3  shr     r8d, 0Ah
0x18001beb7  and     r9d, edi
0x18001beba  and     r8d, edi
0x18001bebd  mov     [rsp+48h+var_20], edi
0x18001bec1  mov     edx, 2F29A04h
0x18001bec6  mov     [rsp+48h+var_28], rax
0x18001becb  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18001bed0  mov     dl, dil
0x18001bed3  mov     eax, [rbx]
0x18001bed5  test    sil, al
0x18001bed8  jz      short loc_18001BEDE
0x18001beda  test    dl, dl
0x18001bedc  jnz     short loc_18001BEE0
0x18001bede  xor     edi, edi
0x18001bee0  mov     rsi, [rsp+48h+arg_18]
0x18001bee5  and     eax, 0FFFFFFFEh
0x18001bee8  or      eax, edi
0x18001beea  mov     [rbx], eax
0x18001beec  mov     rax, rbx
0x18001beef  mov     rbx, [rsp+48h+arg_10]
0x18001bef4  add     rsp, 40h
0x18001bef8  pop     rdi
0x18001bef9  retn
```
