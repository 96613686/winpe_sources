# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800091a8`
- end: `0x1800092ea`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180008250`

## callees

- `0x18000886c`
- `0x1800091a8`
- `0x18000dc68`
- `0x180015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::GetCurrentFeatureEnabledState(
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
    v4 = v2(57665307, 3);
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
    wil::details::ReportUsageToService(&qword_180024070, 49453572, (v13 >> 10) & 1, (v13 >> 11) & 1, &v15, 1, 0);
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
0x1800091a8  mov     [rsp+arg_10], rbx
0x1800091ad  mov     [rsp+arg_18], rsi
0x1800091b2  mov     [rsp+arg_0], rcx
0x1800091b7  push    rdi
0x1800091b8  sub     rsp, 40h
0x1800091bc  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800091c3  mov     rbx, rdx
0x1800091c6  test    rax, rax
0x1800091c9  jz      short loc_1800091DE
0x1800091cb  mov     edx, 3
0x1800091d0  mov     ecx, 36FE71Bh
0x1800091d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091da  mov     edx, eax
0x1800091dc  jmp     short loc_1800091EC
0x1800091de  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800091e5  test    rax, rax
0x1800091e8  jnz     short loc_1800091CB
0x1800091ea  xor     edx, edx
0x1800091ec  mov     r8d, edx
0x1800091ef  mov     qword ptr [rbx], 0
0x1800091f6  and     r8d, 0FFFFFF3Fh
0x1800091fd  mov     eax, edx
0x1800091ff  and     edx, 80h
0x180009205  mov     ecx, r8d
0x180009208  and     ecx, 3
0x18000920b  mov     esi, 40h ; '@'
0x180009210  shl     ecx, 2
0x180009213  and     eax, esi
0x180009215  or      ecx, eax
0x180009217  shl     ecx, 2
0x18000921a  or      ecx, edx
0x18000921c  shl     ecx, 3
0x18000921f  test    r8d, r8d
0x180009222  jnz     short loc_18000922B
0x180009224  mov     edx, esi
0x180009226  mov     r8d, esi
0x180009229  jmp     short loc_180009237
0x18000922b  xor     edx, edx
0x18000922d  cmp     r8d, 2
0x180009231  cmovz   edx, esi
0x180009234  mov     r8d, edx
0x180009237  mov     eax, ecx
0x180009239  mov     edi, 1
0x18000923e  or      eax, r8d
0x180009241  or      ecx, edx
0x180009243  mov     [rbx], eax
0x180009245  bt      ecx, 0Ah
0x180009249  jnb     short loc_180009253
0x18000924b  cmp     ecx, 800h
0x180009251  jnb     short loc_18000925A
0x180009253  xor     dl, dl
0x180009255  test    sil, cl
0x180009258  jz      short loc_1800092C3
0x18000925a  mov     rax, cs:Feature_Standalone_Future__descriptor
0x180009261  mov     r8d, [rax]
0x180009264  test    r8b, 4
0x180009268  jnz     short loc_18000927F
0x18000926a  lea     rdx, [rsp+48h+arg_8]
0x18000926f  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)
0x180009274  mov     rcx, [rax]
0x180009277  mov     [rsp+48h+arg_8], rcx
0x18000927c  mov     r8d, ecx
0x18000927f  xor     eax, eax
0x180009281  mov     word ptr [rsp+48h+arg_0+4], 3
0x180009288  mov     r9d, r8d
0x18000928b  mov     [rsp+48h+var_18], eax
0x18000928f  mov     dword ptr [rsp+48h+arg_0], eax
0x180009293  lea     rcx, qword_180024070
0x18000929a  shr     r9d, 0Bh
0x18000929e  lea     rax, [rsp+48h+arg_0]
0x1800092a3  shr     r8d, 0Ah
0x1800092a7  and     r9d, edi
0x1800092aa  and     r8d, edi
0x1800092ad  mov     [rsp+48h+var_20], edi
0x1800092b1  mov     edx, 2F29A04h
0x1800092b6  mov     [rsp+48h+var_28], rax
0x1800092bb  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800092c0  mov     dl, dil
0x1800092c3  mov     eax, [rbx]
0x1800092c5  test    sil, al
0x1800092c8  jz      short loc_1800092CE
0x1800092ca  test    dl, dl
0x1800092cc  jnz     short loc_1800092D0
0x1800092ce  xor     edi, edi
0x1800092d0  mov     rsi, [rsp+48h+arg_18]
0x1800092d5  and     eax, 0FFFFFFFEh
0x1800092d8  or      eax, edi
0x1800092da  mov     [rbx], eax
0x1800092dc  mov     rax, rbx
0x1800092df  mov     rbx, [rsp+48h+arg_10]
0x1800092e4  add     rsp, 40h
0x1800092e8  pop     rdi
0x1800092e9  retn
```
