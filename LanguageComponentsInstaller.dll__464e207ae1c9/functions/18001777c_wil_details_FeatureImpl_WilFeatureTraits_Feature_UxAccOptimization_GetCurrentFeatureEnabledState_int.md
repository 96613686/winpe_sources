# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001777c`
- end: `0x1800178d7`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `347`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180017234`

## callees

- `0x180003520`
- `0x18001709c`
- `0x18001777c`
- `0x18001b0f0`
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
  __int64 v15; // [rsp+40h] [rbp-28h] BYREF
  int v16; // [rsp+48h] [rbp-20h] BYREF
  __int16 v17; // [rsp+4Ch] [rbp-1Ch]

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
      v15 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
               v11,
               &v15);
      v13 = v15;
    }
    v17 = 3;
    v16 = 0;
    wil::details::ReportUsageToService(&qword_1800377B0, 49453572, (v13 >> 10) & 1, (v13 >> 11) & 1, &v16, 1, 0);
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
0x18001777c  mov     [rsp+arg_0], rbx
0x180017781  mov     [rsp+arg_18], rsi
0x180017786  push    rdi
0x180017787  sub     rsp, 60h
0x18001778b  mov     rax, cs:__security_cookie
0x180017792  xor     rax, rsp
0x180017795  mov     [rsp+68h+var_18], rax
0x18001779a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800177a1  mov     rbx, rdx
0x1800177a4  test    rax, rax
0x1800177a7  jz      short loc_1800177BC
0x1800177a9  mov     edx, 3
0x1800177ae  mov     ecx, 2E30A37h
0x1800177b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177b8  mov     edx, eax
0x1800177ba  jmp     short loc_1800177CA
0x1800177bc  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800177c3  test    rax, rax
0x1800177c6  jnz     short loc_1800177A9
0x1800177c8  xor     edx, edx
0x1800177ca  mov     r8d, edx
0x1800177cd  mov     qword ptr [rbx], 0
0x1800177d4  and     r8d, 0FFFFFF3Fh
0x1800177db  mov     eax, edx
0x1800177dd  and     edx, 80h
0x1800177e3  mov     ecx, r8d
0x1800177e6  and     ecx, 3
0x1800177e9  mov     esi, 40h ; '@'
0x1800177ee  shl     ecx, 2
0x1800177f1  and     eax, esi
0x1800177f3  or      ecx, eax
0x1800177f5  shl     ecx, 2
0x1800177f8  or      ecx, edx
0x1800177fa  shl     ecx, 3
0x1800177fd  test    r8d, r8d
0x180017800  jnz     short loc_180017809
0x180017802  mov     edx, esi
0x180017804  mov     r8d, esi
0x180017807  jmp     short loc_180017815
0x180017809  xor     edx, edx
0x18001780b  cmp     r8d, 2
0x18001780f  cmovz   edx, esi
0x180017812  mov     r8d, edx
0x180017815  mov     eax, ecx
0x180017817  mov     edi, 1
0x18001781c  or      eax, r8d
0x18001781f  or      ecx, edx
0x180017821  mov     [rbx], eax
0x180017823  bt      ecx, 0Ah
0x180017827  jnb     short loc_180017831
0x180017829  cmp     ecx, 800h
0x18001782f  jnb     short loc_180017838
0x180017831  xor     dl, dl
0x180017833  test    sil, cl
0x180017836  jz      short loc_1800178A1
0x180017838  mov     rax, cs:Feature_Standalone_Future__descriptor
0x18001783f  mov     r8d, [rax]
0x180017842  test    r8b, 4
0x180017846  jnz     short loc_18001785D
0x180017848  lea     rdx, [rsp+68h+var_28]
0x18001784d  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)
0x180017852  mov     rcx, [rax]
0x180017855  mov     [rsp+68h+var_28], rcx
0x18001785a  mov     r8d, ecx
0x18001785d  xor     eax, eax
0x18001785f  mov     [rsp+68h+var_1C], 3
0x180017866  mov     r9d, r8d
0x180017869  mov     [rsp+68h+var_38], eax
0x18001786d  mov     [rsp+68h+var_20], eax
0x180017871  lea     rcx, qword_1800377B0
0x180017878  shr     r9d, 0Bh
0x18001787c  lea     rax, [rsp+68h+var_20]
0x180017881  shr     r8d, 0Ah
0x180017885  and     r9d, edi
0x180017888  and     r8d, edi
0x18001788b  mov     [rsp+68h+var_40], edi
0x18001788f  mov     edx, 2F29A04h
0x180017894  mov     [rsp+68h+var_48], rax
0x180017899  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18001789e  mov     dl, dil
0x1800178a1  mov     eax, [rbx]
0x1800178a3  test    sil, al
0x1800178a6  jz      short loc_1800178AC
0x1800178a8  test    dl, dl
0x1800178aa  jnz     short loc_1800178AE
0x1800178ac  xor     edi, edi
0x1800178ae  and     eax, 0FFFFFFFEh
0x1800178b1  or      eax, edi
0x1800178b3  mov     [rbx], eax
0x1800178b5  mov     rax, rbx
0x1800178b8  mov     rcx, [rsp+68h+var_18]
0x1800178bd  xor     rcx, rsp; StackCookie
0x1800178c0  call    __security_check_cookie
0x1800178c5  lea     r11, [rsp+68h+var_8]
0x1800178ca  mov     rbx, [r11+10h]
0x1800178ce  mov     rsi, [r11+28h]
0x1800178d2  mov     rsp, r11
0x1800178d5  pop     rdi
0x1800178d6  retn
```
