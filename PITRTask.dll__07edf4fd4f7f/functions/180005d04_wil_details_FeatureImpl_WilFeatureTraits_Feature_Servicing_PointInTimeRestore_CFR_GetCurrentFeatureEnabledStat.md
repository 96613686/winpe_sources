# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_CFR>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180005d04`
- end: `0x180005e81`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_CFR@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `381`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x1800056c8`

## callees

- `0x1800058b0`
- `0x180005d04`
- `0x1800088a8`
- `0x18000bb90`
- `0x1800107c0`
- `0x180012010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_CFR>::GetCurrentFeatureEnabledState(
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
  char v12; // si
  bool v13; // dl
  unsigned int v14; // r8d
  char IsEnabled; // al
  __int64 v17; // [rsp+40h] [rbp-38h] BYREF
  int v18; // [rsp+48h] [rbp-30h] BYREF
  __int16 v19; // [rsp+4Ch] [rbp-2Ch]

  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(59673297, 3);
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
  if ( ((unsigned __int16)v11 & 0x400) != 0 && (unsigned int)v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    v13 = 0;
    if ( ((unsigned __int8)v11 & 0x40) == 0 )
      goto LABEL_19;
  }
  v14 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (*(_DWORD *)Feature_Standalone_Future__descriptor & 4) == 0 )
  {
    v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
             v11,
             &v17);
    v14 = v17;
  }
  v19 = 3;
  v18 = 0;
  wil::details::ReportUsageToService(&qword_18001BE08, 49453572, (v14 >> 10) & 1, (v14 >> 11) & 1, &v18, 1, 0);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl);
  v13 = IsEnabled != 0;
  if ( v12 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_19:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v13 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180005d04  mov     [rsp+arg_0], rbx
0x180005d09  push    rbp
0x180005d0a  push    rsi
0x180005d0b  push    rdi
0x180005d0c  sub     rsp, 60h
0x180005d10  mov     rax, cs:__security_cookie
0x180005d17  xor     rax, rsp
0x180005d1a  mov     [rsp+78h+var_28], rax
0x180005d1f  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180005d26  mov     rbx, rdx
0x180005d29  test    rax, rax
0x180005d2c  jz      short loc_180005D41
0x180005d2e  mov     edx, 3
0x180005d33  mov     ecx, 38E8AD1h
0x180005d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d3d  mov     edx, eax
0x180005d3f  jmp     short loc_180005D4F
0x180005d41  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180005d48  test    rax, rax
0x180005d4b  jnz     short loc_180005D2E
0x180005d4d  xor     edx, edx
0x180005d4f  mov     r8d, edx
0x180005d52  mov     qword ptr [rbx], 0
0x180005d59  and     r8d, 0FFFFFF3Fh
0x180005d60  mov     eax, edx
0x180005d62  and     edx, 80h
0x180005d68  mov     ecx, r8d
0x180005d6b  and     ecx, 3
0x180005d6e  mov     ebp, 40h ; '@'
0x180005d73  shl     ecx, 2
0x180005d76  and     eax, ebp
0x180005d78  or      ecx, eax
0x180005d7a  shl     ecx, 2
0x180005d7d  or      ecx, edx
0x180005d7f  shl     ecx, 3
0x180005d82  test    r8d, r8d
0x180005d85  jnz     short loc_180005D8E
0x180005d87  mov     edx, ebp
0x180005d89  mov     r8d, ebp
0x180005d8c  jmp     short loc_180005D9A
0x180005d8e  xor     edx, edx
0x180005d90  cmp     r8d, 2
0x180005d94  cmovz   edx, ebp
0x180005d97  mov     r8d, edx
0x180005d9a  mov     eax, ecx
0x180005d9c  mov     edi, 1
0x180005da1  or      eax, r8d
0x180005da4  or      ecx, edx
0x180005da6  mov     [rbx], eax
0x180005da8  bt      ecx, 0Ah
0x180005dac  jnb     short loc_180005DBB
0x180005dae  cmp     ecx, 800h
0x180005db4  jb      short loc_180005DBB
0x180005db6  mov     sil, dil
0x180005db9  jmp     short loc_180005DC9
0x180005dbb  xor     sil, sil
0x180005dbe  xor     dl, dl
0x180005dc0  test    bpl, cl
0x180005dc3  jz      loc_180005E4D
0x180005dc9  mov     rax, cs:Feature_Standalone_Future__descriptor
0x180005dd0  mov     r8d, [rax]
0x180005dd3  test    r8b, 4
0x180005dd7  jnz     short loc_180005DEE
0x180005dd9  lea     rdx, [rsp+78h+var_38]
0x180005dde  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)
0x180005de3  mov     rcx, [rax]
0x180005de6  mov     [rsp+78h+var_38], rcx
0x180005deb  mov     r8d, ecx
0x180005dee  xor     eax, eax
0x180005df0  mov     [rsp+78h+var_2C], 3
0x180005df7  mov     r9d, r8d
0x180005dfa  mov     [rsp+78h+var_48], eax
0x180005dfe  mov     [rsp+78h+var_30], eax
0x180005e02  lea     rcx, qword_18001BE08
0x180005e09  shr     r9d, 0Bh
0x180005e0d  lea     rax, [rsp+78h+var_30]
0x180005e12  shr     r8d, 0Ah
0x180005e16  and     r9d, edi
0x180005e19  and     r8d, edi
0x180005e1c  mov     [rsp+78h+var_50], edi
0x180005e20  mov     edx, 2F29A04h
0x180005e25  mov     [rsp+78h+var_58], rax
0x180005e2a  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180005e2f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x180005e36  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(wil::ReportingKind)
0x180005e3b  test    al, al
0x180005e3d  setnz   dl
0x180005e40  test    sil, sil
0x180005e43  jz      short loc_180005E4D
0x180005e45  test    dl, dl
0x180005e47  jnz     short loc_180005E4D
0x180005e49  btr     dword ptr [rbx], 0Ah
0x180005e4d  mov     eax, [rbx]
0x180005e4f  test    bpl, al
0x180005e52  jz      short loc_180005E58
0x180005e54  test    dl, dl
0x180005e56  jnz     short loc_180005E5A
0x180005e58  xor     edi, edi
0x180005e5a  and     eax, 0FFFFFFFEh
0x180005e5d  or      eax, edi
0x180005e5f  mov     [rbx], eax
0x180005e61  mov     rax, rbx
0x180005e64  mov     rcx, [rsp+78h+var_28]
0x180005e69  xor     rcx, rsp; StackCookie
0x180005e6c  call    __security_check_cookie
0x180005e71  mov     rbx, [rsp+78h+arg_0]
0x180005e79  add     rsp, 60h
0x180005e7d  pop     rdi
0x180005e7e  pop     rsi
0x180005e7f  pop     rbp
0x180005e80  retn
```
