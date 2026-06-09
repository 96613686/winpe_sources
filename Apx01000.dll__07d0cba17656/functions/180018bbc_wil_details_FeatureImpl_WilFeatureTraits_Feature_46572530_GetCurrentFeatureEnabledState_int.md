# wil::details::FeatureImpl<__WilFeatureTraits_Feature_46572530>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180018bbc`
- end: `0x180018cfe`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_46572530@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180018adc`

## callees

- `0x18000ab68`
- `0x180013200`
- `0x180018bbc`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_46572530>::GetCurrentFeatureEnabledState(
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
    v4 = v2(46572530, 3);
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
    v13 = *(_DWORD *)Feature_ImplVal__descriptor;
    if ( (*(_DWORD *)Feature_ImplVal__descriptor & 4) == 0 )
    {
      v16 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImplVal>::GetCachedFeatureEnabledState(v11, &v16);
      v13 = v16;
    }
    WORD2(v15) = 3;
    LODWORD(v15) = 0;
    wil::details::ReportUsageToService(&qword_180033808, 54237993, (v13 >> 10) & 1, (v13 >> 11) & 1, &v15, 1, 0);
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
0x180018bbc  mov     [rsp+arg_10], rbx
0x180018bc1  mov     [rsp+arg_18], rsi
0x180018bc6  mov     [rsp+arg_0], rcx
0x180018bcb  push    rdi
0x180018bcc  sub     rsp, 40h
0x180018bd0  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180018bd7  mov     rbx, rdx
0x180018bda  test    rax, rax
0x180018bdd  jz      short loc_180018BF2
0x180018bdf  mov     edx, 3
0x180018be4  mov     ecx, 2C6A3F2h
0x180018be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018bee  mov     edx, eax
0x180018bf0  jmp     short loc_180018C00
0x180018bf2  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180018bf9  test    rax, rax
0x180018bfc  jnz     short loc_180018BDF
0x180018bfe  xor     edx, edx
0x180018c00  mov     r8d, edx
0x180018c03  mov     qword ptr [rbx], 0
0x180018c0a  and     r8d, 0FFFFFF3Fh
0x180018c11  mov     eax, edx
0x180018c13  and     edx, 80h
0x180018c19  mov     ecx, r8d
0x180018c1c  and     ecx, 3
0x180018c1f  mov     esi, 40h ; '@'
0x180018c24  shl     ecx, 2
0x180018c27  and     eax, esi
0x180018c29  or      ecx, eax
0x180018c2b  shl     ecx, 2
0x180018c2e  or      ecx, edx
0x180018c30  shl     ecx, 3
0x180018c33  test    r8d, r8d
0x180018c36  jnz     short loc_180018C3F
0x180018c38  mov     edx, esi
0x180018c3a  mov     r8d, esi
0x180018c3d  jmp     short loc_180018C4B
0x180018c3f  xor     edx, edx
0x180018c41  cmp     r8d, 2
0x180018c45  cmovz   edx, esi
0x180018c48  mov     r8d, edx
0x180018c4b  mov     eax, ecx
0x180018c4d  mov     edi, 1
0x180018c52  or      eax, r8d
0x180018c55  or      ecx, edx
0x180018c57  mov     [rbx], eax
0x180018c59  bt      ecx, 0Ah
0x180018c5d  jnb     short loc_180018C67
0x180018c5f  cmp     ecx, 800h
0x180018c65  jnb     short loc_180018C6E
0x180018c67  xor     dl, dl
0x180018c69  test    sil, cl
0x180018c6c  jz      short loc_180018CD7
0x180018c6e  mov     rax, cs:Feature_ImplVal__descriptor
0x180018c75  mov     r8d, [rax]
0x180018c78  test    r8b, 4
0x180018c7c  jnz     short loc_180018C93
0x180018c7e  lea     rdx, [rsp+48h+arg_8]
0x180018c83  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ImplVal@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImplVal>::GetCachedFeatureEnabledState(void)
0x180018c88  mov     rcx, [rax]
0x180018c8b  mov     [rsp+48h+arg_8], rcx
0x180018c90  mov     r8d, ecx
0x180018c93  xor     eax, eax
0x180018c95  mov     word ptr [rsp+48h+arg_0+4], 3
0x180018c9c  mov     r9d, r8d
0x180018c9f  mov     [rsp+48h+var_18], eax
0x180018ca3  mov     dword ptr [rsp+48h+arg_0], eax
0x180018ca7  lea     rcx, qword_180033808
0x180018cae  shr     r9d, 0Bh
0x180018cb2  lea     rax, [rsp+48h+arg_0]
0x180018cb7  shr     r8d, 0Ah
0x180018cbb  and     r9d, edi
0x180018cbe  and     r8d, edi
0x180018cc1  mov     [rsp+48h+var_20], edi
0x180018cc5  mov     edx, 33B9B29h
0x180018cca  mov     [rsp+48h+var_28], rax
0x180018ccf  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180018cd4  mov     dl, dil
0x180018cd7  mov     eax, [rbx]
0x180018cd9  test    sil, al
0x180018cdc  jz      short loc_180018CE2
0x180018cde  test    dl, dl
0x180018ce0  jnz     short loc_180018CE4
0x180018ce2  xor     edi, edi
0x180018ce4  mov     rsi, [rsp+48h+arg_18]
0x180018ce9  and     eax, 0FFFFFFFEh
0x180018cec  or      eax, edi
0x180018cee  mov     [rbx], eax
0x180018cf0  mov     rax, rbx
0x180018cf3  mov     rbx, [rsp+48h+arg_10]
0x180018cf8  add     rsp, 40h
0x180018cfc  pop     rdi
0x180018cfd  retn
```
