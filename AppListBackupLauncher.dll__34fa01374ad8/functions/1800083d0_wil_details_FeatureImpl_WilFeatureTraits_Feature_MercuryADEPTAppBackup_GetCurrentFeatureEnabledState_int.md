# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MercuryADEPTAppBackup>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800083d0`
- end: `0x180008512`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MercuryADEPTAppBackup@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180007d94`

## callees

- `0x180007e74`
- `0x1800083d0`
- `0x18000bad8`
- `0x180012010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MercuryADEPTAppBackup>::GetCurrentFeatureEnabledState(
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
    v4 = v2(41984359, 3);
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
    v13 = *(_DWORD *)Feature_Mercury_App_Backup_Shared__descriptor;
    if ( (*(_DWORD *)Feature_Mercury_App_Backup_Shared__descriptor & 4) == 0 )
    {
      v16 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Mercury_App_Backup_Shared>::GetCachedFeatureEnabledState(
               v11,
               &v16);
      v13 = v16;
    }
    WORD2(v15) = 3;
    LODWORD(v15) = 0;
    wil::details::ReportUsageToService(&qword_180019A98, 42529603, (v13 >> 10) & 1, (v13 >> 11) & 1, &v15, 1, 0);
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
0x1800083d0  mov     [rsp+arg_10], rbx
0x1800083d5  mov     [rsp+arg_18], rsi
0x1800083da  mov     [rsp+arg_0], rcx
0x1800083df  push    rdi
0x1800083e0  sub     rsp, 40h
0x1800083e4  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800083eb  mov     rbx, rdx
0x1800083ee  test    rax, rax
0x1800083f1  jz      short loc_180008406
0x1800083f3  mov     edx, 3
0x1800083f8  mov     ecx, 280A167h
0x1800083fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008402  mov     edx, eax
0x180008404  jmp     short loc_180008414
0x180008406  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000840d  test    rax, rax
0x180008410  jnz     short loc_1800083F3
0x180008412  xor     edx, edx
0x180008414  mov     r8d, edx
0x180008417  mov     qword ptr [rbx], 0
0x18000841e  and     r8d, 0FFFFFF3Fh
0x180008425  mov     eax, edx
0x180008427  and     edx, 80h
0x18000842d  mov     ecx, r8d
0x180008430  and     ecx, 3
0x180008433  mov     esi, 40h ; '@'
0x180008438  shl     ecx, 2
0x18000843b  and     eax, esi
0x18000843d  or      ecx, eax
0x18000843f  shl     ecx, 2
0x180008442  or      ecx, edx
0x180008444  shl     ecx, 3
0x180008447  test    r8d, r8d
0x18000844a  jnz     short loc_180008453
0x18000844c  mov     edx, esi
0x18000844e  mov     r8d, esi
0x180008451  jmp     short loc_18000845F
0x180008453  xor     edx, edx
0x180008455  cmp     r8d, 2
0x180008459  cmovz   edx, esi
0x18000845c  mov     r8d, edx
0x18000845f  mov     eax, ecx
0x180008461  mov     edi, 1
0x180008466  or      eax, r8d
0x180008469  or      ecx, edx
0x18000846b  mov     [rbx], eax
0x18000846d  bt      ecx, 0Ah
0x180008471  jnb     short loc_18000847B
0x180008473  cmp     ecx, 800h
0x180008479  jnb     short loc_180008482
0x18000847b  xor     dl, dl
0x18000847d  test    sil, cl
0x180008480  jz      short loc_1800084EB
0x180008482  mov     rax, cs:Feature_Mercury_App_Backup_Shared__descriptor
0x180008489  mov     r8d, [rax]
0x18000848c  test    r8b, 4
0x180008490  jnz     short loc_1800084A7
0x180008492  lea     rdx, [rsp+48h+arg_8]
0x180008497  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Mercury_App_Backup_Shared@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Mercury_App_Backup_Shared>::GetCachedFeatureEnabledState(void)
0x18000849c  mov     rcx, [rax]
0x18000849f  mov     [rsp+48h+arg_8], rcx
0x1800084a4  mov     r8d, ecx
0x1800084a7  xor     eax, eax
0x1800084a9  mov     word ptr [rsp+48h+arg_0+4], 3
0x1800084b0  mov     r9d, r8d
0x1800084b3  mov     [rsp+48h+var_18], eax
0x1800084b7  mov     dword ptr [rsp+48h+arg_0], eax
0x1800084bb  lea     rcx, qword_180019A98
0x1800084c2  shr     r9d, 0Bh
0x1800084c6  lea     rax, [rsp+48h+arg_0]
0x1800084cb  shr     r8d, 0Ah
0x1800084cf  and     r9d, edi
0x1800084d2  and     r8d, edi
0x1800084d5  mov     [rsp+48h+var_20], edi
0x1800084d9  mov     edx, 288F343h
0x1800084de  mov     [rsp+48h+var_28], rax
0x1800084e3  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800084e8  mov     dl, dil
0x1800084eb  mov     eax, [rbx]
0x1800084ed  test    sil, al
0x1800084f0  jz      short loc_1800084F6
0x1800084f2  test    dl, dl
0x1800084f4  jnz     short loc_1800084F8
0x1800084f6  xor     edi, edi
0x1800084f8  mov     rsi, [rsp+48h+arg_18]
0x1800084fd  and     eax, 0FFFFFFFEh
0x180008500  or      eax, edi
0x180008502  mov     [rbx], eax
0x180008504  mov     rax, rbx
0x180008507  mov     rbx, [rsp+48h+arg_10]
0x18000850c  add     rsp, 40h
0x180008510  pop     rdi
0x180008511  retn
```
