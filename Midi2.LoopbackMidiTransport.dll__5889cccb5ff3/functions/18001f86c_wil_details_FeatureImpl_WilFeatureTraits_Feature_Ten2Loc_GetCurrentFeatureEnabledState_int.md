# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001f86c`
- end: `0x18001f9d5`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001f1ac`

## callees

- `0x18001ed50`
- `0x18001f86c`
- `0x180020aa4`
- `0x180021500`
- `0x180032010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  __int64 v7; // rdx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  unsigned int v11; // ecx
  char v12; // si
  __int64 v13; // rcx
  unsigned int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v16 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(58989002, 3);
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
  v11 = v7 | v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    LOBYTE(v7) = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_22;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor & 4) == 0 )
    {
      v17 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
                         v13,
                         &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_18005FDB8,
      0x37E287Eu,
      (v14 >> 10) & 1,
      (v14 >> 11) & 1,
      (__int64)&v16,
      1u,
      0);
    LOBYTE(v7) = 1;
  }
  else
  {
    LOBYTE(v7) = 0;
  }
  if ( v12 && !(_BYTE)v7 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_22:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x18001f86c  mov     [rsp+arg_10], rbx
0x18001f871  mov     [rsp+arg_0], rcx
0x18001f876  push    rbp
0x18001f877  push    rsi
0x18001f878  push    rdi
0x18001f879  sub     rsp, 40h
0x18001f87d  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001f884  mov     rbx, rdx
0x18001f887  test    rax, rax
0x18001f88a  jz      short loc_18001F89F
0x18001f88c  mov     edx, 3
0x18001f891  mov     ecx, 38419CAh
0x18001f896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f89b  mov     edx, eax
0x18001f89d  jmp     short loc_18001F8AD
0x18001f89f  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001f8a6  test    rax, rax
0x18001f8a9  jnz     short loc_18001F88C
0x18001f8ab  xor     edx, edx
0x18001f8ad  mov     r8d, edx
0x18001f8b0  mov     qword ptr [rbx], 0
0x18001f8b7  and     r8d, 0FFFFFF3Fh
0x18001f8be  mov     eax, edx
0x18001f8c0  and     edx, 80h
0x18001f8c6  mov     ecx, r8d
0x18001f8c9  and     ecx, 3
0x18001f8cc  mov     ebp, 40h ; '@'
0x18001f8d1  shl     ecx, 2
0x18001f8d4  and     eax, ebp
0x18001f8d6  or      ecx, eax
0x18001f8d8  shl     ecx, 2
0x18001f8db  or      ecx, edx
0x18001f8dd  shl     ecx, 3
0x18001f8e0  test    r8d, r8d
0x18001f8e3  jnz     short loc_18001F8EC
0x18001f8e5  mov     edx, ebp
0x18001f8e7  mov     r8d, ebp
0x18001f8ea  jmp     short loc_18001F8F8
0x18001f8ec  xor     edx, edx
0x18001f8ee  cmp     r8d, 2
0x18001f8f2  cmovz   edx, ebp
0x18001f8f5  mov     r8d, edx
0x18001f8f8  mov     eax, ecx
0x18001f8fa  mov     edi, 1
0x18001f8ff  or      eax, r8d
0x18001f902  or      ecx, edx
0x18001f904  mov     [rbx], eax
0x18001f906  bt      ecx, 0Ah
0x18001f90a  jnb     short loc_18001F919
0x18001f90c  cmp     ecx, 800h
0x18001f912  jb      short loc_18001F919
0x18001f914  mov     sil, dil
0x18001f917  jmp     short loc_18001F927
0x18001f919  xor     sil, sil
0x18001f91c  xor     dl, dl
0x18001f91e  test    bpl, cl
0x18001f921  jz      loc_18001F9B1
0x18001f927  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x18001f92e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x18001f933  test    al, al
0x18001f935  jz      short loc_18001F9A2
0x18001f937  mov     rax, cs:Feature_Standalone_26_02_NonSec__descriptor
0x18001f93e  mov     r8d, [rax]
0x18001f941  test    r8b, 4
0x18001f945  jnz     short loc_18001F95C
0x18001f947  lea     rdx, [rsp+58h+arg_8]
0x18001f94c  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)
0x18001f951  mov     rcx, [rax]
0x18001f954  mov     [rsp+58h+arg_8], rcx
0x18001f959  mov     r8d, ecx
0x18001f95c  xor     eax, eax
0x18001f95e  mov     word ptr [rsp+58h+arg_0+4], 3
0x18001f965  mov     r9d, r8d
0x18001f968  mov     [rsp+58h+var_28], eax
0x18001f96c  mov     dword ptr [rsp+58h+arg_0], eax
0x18001f970  lea     rcx, qword_18005FDB8
0x18001f977  shr     r9d, 0Bh
0x18001f97b  lea     rax, [rsp+58h+arg_0]
0x18001f980  shr     r8d, 0Ah
0x18001f984  and     r9d, edi
0x18001f987  and     r8d, edi
0x18001f98a  mov     [rsp+58h+var_30], edi
0x18001f98e  mov     edx, 37E287Eh
0x18001f993  mov     [rsp+58h+var_38], rax
0x18001f998  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18001f99d  mov     dl, dil
0x18001f9a0  jmp     short loc_18001F9A4
0x18001f9a2  xor     dl, dl
0x18001f9a4  test    sil, sil
0x18001f9a7  jz      short loc_18001F9B1
0x18001f9a9  test    dl, dl
0x18001f9ab  jnz     short loc_18001F9B1
0x18001f9ad  btr     dword ptr [rbx], 0Ah
0x18001f9b1  mov     eax, [rbx]
0x18001f9b3  test    bpl, al
0x18001f9b6  jz      short loc_18001F9BC
0x18001f9b8  test    dl, dl
0x18001f9ba  jnz     short loc_18001F9BE
0x18001f9bc  xor     edi, edi
0x18001f9be  and     eax, 0FFFFFFFEh
0x18001f9c1  or      eax, edi
0x18001f9c3  mov     [rbx], eax
0x18001f9c5  mov     rax, rbx
0x18001f9c8  mov     rbx, [rsp+58h+arg_10]
0x18001f9cd  add     rsp, 40h
0x18001f9d1  pop     rdi
0x18001f9d2  pop     rsi
0x18001f9d3  pop     rbp
0x18001f9d4  retn
```
