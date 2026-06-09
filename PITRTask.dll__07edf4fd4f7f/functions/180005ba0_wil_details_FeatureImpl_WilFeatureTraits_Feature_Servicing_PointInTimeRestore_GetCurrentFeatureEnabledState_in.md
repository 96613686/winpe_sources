# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180005ba0`
- end: `0x180005cfb`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `347`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x1800055d4`

## callees

- `0x1800058b0`
- `0x180005ba0`
- `0x1800088a8`
- `0x1800107c0`
- `0x180012010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetCurrentFeatureEnabledState(
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
  __int64 v15; // [rsp+40h] [rbp-28h] BYREF
  int v16; // [rsp+48h] [rbp-20h] BYREF
  __int16 v17; // [rsp+4Ch] [rbp-1Ch]

  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(55324166, 3);
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
      v15 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
               v11,
               &v15);
      v13 = v15;
    }
    v17 = 3;
    v16 = 0;
    wil::details::ReportUsageToService(&qword_18001BE08, 49453572, (v13 >> 10) & 1, (v13 >> 11) & 1, &v16, 1, 0);
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
0x180005ba0  mov     [rsp+arg_0], rbx
0x180005ba5  mov     [rsp+arg_18], rsi
0x180005baa  push    rdi
0x180005bab  sub     rsp, 60h
0x180005baf  mov     rax, cs:__security_cookie
0x180005bb6  xor     rax, rsp
0x180005bb9  mov     [rsp+68h+var_18], rax
0x180005bbe  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180005bc5  mov     rbx, rdx
0x180005bc8  test    rax, rax
0x180005bcb  jz      short loc_180005BE0
0x180005bcd  mov     edx, 3
0x180005bd2  mov     ecx, 34C2E06h
0x180005bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bdc  mov     edx, eax
0x180005bde  jmp     short loc_180005BEE
0x180005be0  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180005be7  test    rax, rax
0x180005bea  jnz     short loc_180005BCD
0x180005bec  xor     edx, edx
0x180005bee  mov     r8d, edx
0x180005bf1  mov     qword ptr [rbx], 0
0x180005bf8  and     r8d, 0FFFFFF3Fh
0x180005bff  mov     eax, edx
0x180005c01  and     edx, 80h
0x180005c07  mov     ecx, r8d
0x180005c0a  and     ecx, 3
0x180005c0d  mov     esi, 40h ; '@'
0x180005c12  shl     ecx, 2
0x180005c15  and     eax, esi
0x180005c17  or      ecx, eax
0x180005c19  shl     ecx, 2
0x180005c1c  or      ecx, edx
0x180005c1e  shl     ecx, 3
0x180005c21  test    r8d, r8d
0x180005c24  jnz     short loc_180005C2D
0x180005c26  mov     edx, esi
0x180005c28  mov     r8d, esi
0x180005c2b  jmp     short loc_180005C39
0x180005c2d  xor     edx, edx
0x180005c2f  cmp     r8d, 2
0x180005c33  cmovz   edx, esi
0x180005c36  mov     r8d, edx
0x180005c39  mov     eax, ecx
0x180005c3b  mov     edi, 1
0x180005c40  or      eax, r8d
0x180005c43  or      ecx, edx
0x180005c45  mov     [rbx], eax
0x180005c47  bt      ecx, 0Ah
0x180005c4b  jnb     short loc_180005C55
0x180005c4d  cmp     ecx, 800h
0x180005c53  jnb     short loc_180005C5C
0x180005c55  xor     dl, dl
0x180005c57  test    sil, cl
0x180005c5a  jz      short loc_180005CC5
0x180005c5c  mov     rax, cs:Feature_Standalone_Future__descriptor
0x180005c63  mov     r8d, [rax]
0x180005c66  test    r8b, 4
0x180005c6a  jnz     short loc_180005C81
0x180005c6c  lea     rdx, [rsp+68h+var_28]
0x180005c71  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)
0x180005c76  mov     rcx, [rax]
0x180005c79  mov     [rsp+68h+var_28], rcx
0x180005c7e  mov     r8d, ecx
0x180005c81  xor     eax, eax
0x180005c83  mov     [rsp+68h+var_1C], 3
0x180005c8a  mov     r9d, r8d
0x180005c8d  mov     [rsp+68h+var_38], eax
0x180005c91  mov     [rsp+68h+var_20], eax
0x180005c95  lea     rcx, qword_18001BE08
0x180005c9c  shr     r9d, 0Bh
0x180005ca0  lea     rax, [rsp+68h+var_20]
0x180005ca5  shr     r8d, 0Ah
0x180005ca9  and     r9d, edi
0x180005cac  and     r8d, edi
0x180005caf  mov     [rsp+68h+var_40], edi
0x180005cb3  mov     edx, 2F29A04h
0x180005cb8  mov     [rsp+68h+var_48], rax
0x180005cbd  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180005cc2  mov     dl, dil
0x180005cc5  mov     eax, [rbx]
0x180005cc7  test    sil, al
0x180005cca  jz      short loc_180005CD0
0x180005ccc  test    dl, dl
0x180005cce  jnz     short loc_180005CD2
0x180005cd0  xor     edi, edi
0x180005cd2  and     eax, 0FFFFFFFEh
0x180005cd5  or      eax, edi
0x180005cd7  mov     [rbx], eax
0x180005cd9  mov     rax, rbx
0x180005cdc  mov     rcx, [rsp+68h+var_18]
0x180005ce1  xor     rcx, rsp; StackCookie
0x180005ce4  call    __security_check_cookie
0x180005ce9  lea     r11, [rsp+68h+var_8]
0x180005cee  mov     rbx, [r11+10h]
0x180005cf2  mov     rsi, [r11+28h]
0x180005cf6  mov     rsp, r11
0x180005cf9  pop     rdi
0x180005cfa  retn
```
