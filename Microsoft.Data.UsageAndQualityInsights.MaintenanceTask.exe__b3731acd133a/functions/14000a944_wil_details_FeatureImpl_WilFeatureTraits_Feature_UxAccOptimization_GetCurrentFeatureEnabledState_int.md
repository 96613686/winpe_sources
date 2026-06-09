# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)

- ea: `0x14000a944`
- end: `0x14000aa86`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000a864`

## callees

- `0x14000a514`
- `0x14000a944`
- `0x14000ac4c`
- `0x14000c010`

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
    wil::details::ReportUsageToService(&qword_140011A18, 49453572, (v13 >> 10) & 1, (v13 >> 11) & 1, &v15, 1, 0);
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
0x14000a944  mov     [rsp+arg_10], rbx
0x14000a949  mov     [rsp+arg_18], rsi
0x14000a94e  mov     [rsp+arg_0], rcx
0x14000a953  push    rdi
0x14000a954  sub     rsp, 40h
0x14000a958  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x14000a95f  mov     rbx, rdx
0x14000a962  test    rax, rax
0x14000a965  jz      short loc_14000A97A
0x14000a967  mov     edx, 3
0x14000a96c  mov     ecx, 2E30A37h
0x14000a971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a976  mov     edx, eax
0x14000a978  jmp     short loc_14000A988
0x14000a97a  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x14000a981  test    rax, rax
0x14000a984  jnz     short loc_14000A967
0x14000a986  xor     edx, edx
0x14000a988  mov     r8d, edx
0x14000a98b  mov     qword ptr [rbx], 0
0x14000a992  and     r8d, 0FFFFFF3Fh
0x14000a999  mov     eax, edx
0x14000a99b  and     edx, 80h
0x14000a9a1  mov     ecx, r8d
0x14000a9a4  and     ecx, 3
0x14000a9a7  mov     esi, 40h ; '@'
0x14000a9ac  shl     ecx, 2
0x14000a9af  and     eax, esi
0x14000a9b1  or      ecx, eax
0x14000a9b3  shl     ecx, 2
0x14000a9b6  or      ecx, edx
0x14000a9b8  shl     ecx, 3
0x14000a9bb  test    r8d, r8d
0x14000a9be  jnz     short loc_14000A9C7
0x14000a9c0  mov     edx, esi
0x14000a9c2  mov     r8d, esi
0x14000a9c5  jmp     short loc_14000A9D3
0x14000a9c7  xor     edx, edx
0x14000a9c9  cmp     r8d, 2
0x14000a9cd  cmovz   edx, esi
0x14000a9d0  mov     r8d, edx
0x14000a9d3  mov     eax, ecx
0x14000a9d5  mov     edi, 1
0x14000a9da  or      eax, r8d
0x14000a9dd  or      ecx, edx
0x14000a9df  mov     [rbx], eax
0x14000a9e1  bt      ecx, 0Ah
0x14000a9e5  jnb     short loc_14000A9EF
0x14000a9e7  cmp     ecx, 800h
0x14000a9ed  jnb     short loc_14000A9F6
0x14000a9ef  xor     dl, dl
0x14000a9f1  test    sil, cl
0x14000a9f4  jz      short loc_14000AA5F
0x14000a9f6  mov     rax, cs:Feature_Standalone_Future__descriptor
0x14000a9fd  mov     r8d, [rax]
0x14000aa00  test    r8b, 4
0x14000aa04  jnz     short loc_14000AA1B
0x14000aa06  lea     rdx, [rsp+48h+arg_8]
0x14000aa0b  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)
0x14000aa10  mov     rcx, [rax]
0x14000aa13  mov     [rsp+48h+arg_8], rcx
0x14000aa18  mov     r8d, ecx
0x14000aa1b  xor     eax, eax
0x14000aa1d  mov     word ptr [rsp+48h+arg_0+4], 3
0x14000aa24  mov     r9d, r8d
0x14000aa27  mov     [rsp+48h+var_18], eax
0x14000aa2b  mov     dword ptr [rsp+48h+arg_0], eax
0x14000aa2f  lea     rcx, qword_140011A18
0x14000aa36  shr     r9d, 0Bh
0x14000aa3a  lea     rax, [rsp+48h+arg_0]
0x14000aa3f  shr     r8d, 0Ah
0x14000aa43  and     r9d, edi
0x14000aa46  and     r8d, edi
0x14000aa49  mov     [rsp+48h+var_20], edi
0x14000aa4d  mov     edx, 2F29A04h
0x14000aa52  mov     [rsp+48h+var_28], rax
0x14000aa57  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x14000aa5c  mov     dl, dil
0x14000aa5f  mov     eax, [rbx]
0x14000aa61  test    sil, al
0x14000aa64  jz      short loc_14000AA6A
0x14000aa66  test    dl, dl
0x14000aa68  jnz     short loc_14000AA6C
0x14000aa6a  xor     edi, edi
0x14000aa6c  mov     rsi, [rsp+48h+arg_18]
0x14000aa71  and     eax, 0FFFFFFFEh
0x14000aa74  or      eax, edi
0x14000aa76  mov     [rbx], eax
0x14000aa78  mov     rax, rbx
0x14000aa7b  mov     rbx, [rsp+48h+arg_10]
0x14000aa80  add     rsp, 40h
0x14000aa84  pop     rdi
0x14000aa85  retn
```
