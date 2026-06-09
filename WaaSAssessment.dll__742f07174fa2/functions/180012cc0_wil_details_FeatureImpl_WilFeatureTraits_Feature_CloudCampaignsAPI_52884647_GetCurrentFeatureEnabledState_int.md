# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudCampaignsAPI_52884647>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180012cc0`
- end: `0x180012e02`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudCampaignsAPI_52884647@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180012a60`

## callees

- `0x180012b40`
- `0x180012cc0`
- `0x18001553c`
- `0x18001b010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudCampaignsAPI_52884647>::GetCurrentFeatureEnabledState(
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
    v4 = v2(52884647, 3);
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
    v13 = *(_DWORD *)Feature_GatePerf__descriptor;
    if ( (*(_DWORD *)Feature_GatePerf__descriptor & 4) == 0 )
    {
      v16 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_GatePerf>::GetCachedFeatureEnabledState(v11, &v16);
      v13 = v16;
    }
    WORD2(v15) = 3;
    LODWORD(v15) = 0;
    wil::details::ReportUsageToService(&qword_180027D88, 54238000, (v13 >> 10) & 1, (v13 >> 11) & 1, &v15, 1, 0);
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
0x180012cc0  mov     [rsp+arg_10], rbx
0x180012cc5  mov     [rsp+arg_18], rsi
0x180012cca  mov     [rsp+arg_0], rcx
0x180012ccf  push    rdi
0x180012cd0  sub     rsp, 40h
0x180012cd4  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180012cdb  mov     rbx, rdx
0x180012cde  test    rax, rax
0x180012ce1  jz      short loc_180012CF6
0x180012ce3  mov     edx, 3
0x180012ce8  mov     ecx, 326F4A7h
0x180012ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cf2  mov     edx, eax
0x180012cf4  jmp     short loc_180012D04
0x180012cf6  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180012cfd  test    rax, rax
0x180012d00  jnz     short loc_180012CE3
0x180012d02  xor     edx, edx
0x180012d04  mov     r8d, edx
0x180012d07  mov     qword ptr [rbx], 0
0x180012d0e  and     r8d, 0FFFFFF3Fh
0x180012d15  mov     eax, edx
0x180012d17  and     edx, 80h
0x180012d1d  mov     ecx, r8d
0x180012d20  and     ecx, 3
0x180012d23  mov     esi, 40h ; '@'
0x180012d28  shl     ecx, 2
0x180012d2b  and     eax, esi
0x180012d2d  or      ecx, eax
0x180012d2f  shl     ecx, 2
0x180012d32  or      ecx, edx
0x180012d34  shl     ecx, 3
0x180012d37  test    r8d, r8d
0x180012d3a  jnz     short loc_180012D43
0x180012d3c  mov     edx, esi
0x180012d3e  mov     r8d, esi
0x180012d41  jmp     short loc_180012D4F
0x180012d43  xor     edx, edx
0x180012d45  cmp     r8d, 2
0x180012d49  cmovz   edx, esi
0x180012d4c  mov     r8d, edx
0x180012d4f  mov     eax, ecx
0x180012d51  mov     edi, 1
0x180012d56  or      eax, r8d
0x180012d59  or      ecx, edx
0x180012d5b  mov     [rbx], eax
0x180012d5d  bt      ecx, 0Ah
0x180012d61  jnb     short loc_180012D6B
0x180012d63  cmp     ecx, 800h
0x180012d69  jnb     short loc_180012D72
0x180012d6b  xor     dl, dl
0x180012d6d  test    sil, cl
0x180012d70  jz      short loc_180012DDB
0x180012d72  mov     rax, cs:Feature_GatePerf__descriptor
0x180012d79  mov     r8d, [rax]
0x180012d7c  test    r8b, 4
0x180012d80  jnz     short loc_180012D97
0x180012d82  lea     rdx, [rsp+48h+arg_8]
0x180012d87  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GatePerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GatePerf>::GetCachedFeatureEnabledState(void)
0x180012d8c  mov     rcx, [rax]
0x180012d8f  mov     [rsp+48h+arg_8], rcx
0x180012d94  mov     r8d, ecx
0x180012d97  xor     eax, eax
0x180012d99  mov     word ptr [rsp+48h+arg_0+4], 3
0x180012da0  mov     r9d, r8d
0x180012da3  mov     [rsp+48h+var_18], eax
0x180012da7  mov     dword ptr [rsp+48h+arg_0], eax
0x180012dab  lea     rcx, qword_180027D88
0x180012db2  shr     r9d, 0Bh
0x180012db6  lea     rax, [rsp+48h+arg_0]
0x180012dbb  shr     r8d, 0Ah
0x180012dbf  and     r9d, edi
0x180012dc2  and     r8d, edi
0x180012dc5  mov     [rsp+48h+var_20], edi
0x180012dc9  mov     edx, 33B9B30h
0x180012dce  mov     [rsp+48h+var_28], rax
0x180012dd3  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180012dd8  mov     dl, dil
0x180012ddb  mov     eax, [rbx]
0x180012ddd  test    sil, al
0x180012de0  jz      short loc_180012DE6
0x180012de2  test    dl, dl
0x180012de4  jnz     short loc_180012DE8
0x180012de6  xor     edi, edi
0x180012de8  mov     rsi, [rsp+48h+arg_18]
0x180012ded  and     eax, 0FFFFFFFEh
0x180012df0  or      eax, edi
0x180012df2  mov     [rbx], eax
0x180012df4  mov     rax, rbx
0x180012df7  mov     rbx, [rsp+48h+arg_10]
0x180012dfc  add     rsp, 40h
0x180012e00  pop     rdi
0x180012e01  retn
```
