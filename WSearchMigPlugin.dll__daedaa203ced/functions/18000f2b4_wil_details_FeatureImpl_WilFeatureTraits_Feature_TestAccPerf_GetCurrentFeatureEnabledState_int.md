# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000f2b4`
- end: `0x18000f41d`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000ebc4`

## callees

- `0x18000e514`
- `0x18000f2b4`
- `0x1800120a8`
- `0x180013fe4`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(
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
  wil::details *v13; // rcx
  unsigned int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v16 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(57048237, 3);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_180026030, 45036797, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
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
0x18000f2b4  mov     [rsp+arg_10], rbx
0x18000f2b9  mov     [rsp+arg_0], rcx
0x18000f2be  push    rbp
0x18000f2bf  push    rsi
0x18000f2c0  push    rdi
0x18000f2c1  sub     rsp, 40h
0x18000f2c5  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000f2cc  mov     rbx, rdx
0x18000f2cf  test    rax, rax
0x18000f2d2  jz      short loc_18000F2E7
0x18000f2d4  mov     edx, 3
0x18000f2d9  mov     ecx, 3667CADh
0x18000f2de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2e3  mov     edx, eax
0x18000f2e5  jmp     short loc_18000F2F5
0x18000f2e7  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000f2ee  test    rax, rax
0x18000f2f1  jnz     short loc_18000F2D4
0x18000f2f3  xor     edx, edx
0x18000f2f5  mov     r8d, edx
0x18000f2f8  mov     qword ptr [rbx], 0
0x18000f2ff  and     r8d, 0FFFFFF3Fh
0x18000f306  mov     eax, edx
0x18000f308  and     edx, 80h
0x18000f30e  mov     ecx, r8d
0x18000f311  and     ecx, 3
0x18000f314  mov     ebp, 40h ; '@'
0x18000f319  shl     ecx, 2
0x18000f31c  and     eax, ebp
0x18000f31e  or      ecx, eax
0x18000f320  shl     ecx, 2
0x18000f323  or      ecx, edx
0x18000f325  shl     ecx, 3
0x18000f328  test    r8d, r8d
0x18000f32b  jnz     short loc_18000F334
0x18000f32d  mov     edx, ebp
0x18000f32f  mov     r8d, ebp
0x18000f332  jmp     short loc_18000F340
0x18000f334  xor     edx, edx
0x18000f336  cmp     r8d, 2
0x18000f33a  cmovz   edx, ebp
0x18000f33d  mov     r8d, edx
0x18000f340  mov     eax, ecx
0x18000f342  mov     edi, 1
0x18000f347  or      eax, r8d
0x18000f34a  or      ecx, edx
0x18000f34c  mov     [rbx], eax
0x18000f34e  bt      ecx, 0Ah
0x18000f352  jnb     short loc_18000F361
0x18000f354  cmp     ecx, 800h
0x18000f35a  jb      short loc_18000F361
0x18000f35c  mov     sil, dil
0x18000f35f  jmp     short loc_18000F36F
0x18000f361  xor     sil, sil
0x18000f364  xor     dl, dl
0x18000f366  test    bpl, cl
0x18000f369  jz      loc_18000F3F9
0x18000f36f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x18000f376  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x18000f37b  test    al, al
0x18000f37d  jz      short loc_18000F3EA
0x18000f37f  mov     rax, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18000f386  mov     r8d, [rax]
0x18000f389  test    r8b, 4
0x18000f38d  jnz     short loc_18000F3A4
0x18000f38f  lea     rdx, [rsp+58h+arg_8]
0x18000f394  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)
0x18000f399  mov     rcx, [rax]
0x18000f39c  mov     [rsp+58h+arg_8], rcx
0x18000f3a1  mov     r8d, ecx
0x18000f3a4  xor     eax, eax
0x18000f3a6  mov     word ptr [rsp+58h+arg_0+4], 3
0x18000f3ad  mov     r9d, r8d
0x18000f3b0  mov     [rsp+58h+var_28], eax
0x18000f3b4  mov     dword ptr [rsp+58h+arg_0], eax
0x18000f3b8  lea     rcx, qword_180026030
0x18000f3bf  shr     r9d, 0Bh
0x18000f3c3  lea     rax, [rsp+58h+arg_0]
0x18000f3c8  shr     r8d, 0Ah
0x18000f3cc  and     r9d, edi
0x18000f3cf  and     r8d, edi
0x18000f3d2  mov     [rsp+58h+var_30], edi
0x18000f3d6  mov     edx, 2AF34FDh
0x18000f3db  mov     [rsp+58h+var_38], rax
0x18000f3e0  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000f3e5  mov     dl, dil
0x18000f3e8  jmp     short loc_18000F3EC
0x18000f3ea  xor     dl, dl
0x18000f3ec  test    sil, sil
0x18000f3ef  jz      short loc_18000F3F9
0x18000f3f1  test    dl, dl
0x18000f3f3  jnz     short loc_18000F3F9
0x18000f3f5  btr     dword ptr [rbx], 0Ah
0x18000f3f9  mov     eax, [rbx]
0x18000f3fb  test    bpl, al
0x18000f3fe  jz      short loc_18000F404
0x18000f400  test    dl, dl
0x18000f402  jnz     short loc_18000F406
0x18000f404  xor     edi, edi
0x18000f406  and     eax, 0FFFFFFFEh
0x18000f409  or      eax, edi
0x18000f40b  mov     [rbx], eax
0x18000f40d  mov     rax, rbx
0x18000f410  mov     rbx, [rsp+58h+arg_10]
0x18000f415  add     rsp, 40h
0x18000f419  pop     rdi
0x18000f41a  pop     rsi
0x18000f41b  pop     rbp
0x18000f41c  retn
```
