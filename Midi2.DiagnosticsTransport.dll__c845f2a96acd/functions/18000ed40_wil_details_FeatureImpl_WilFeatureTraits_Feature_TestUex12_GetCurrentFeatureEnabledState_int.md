# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000ed40`
- end: `0x18000eea9`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000e4d0`

## callees

- `0x18000e0bc`
- `0x18000ed40`
- `0x18000fbd4`
- `0x180010388`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCurrentFeatureEnabledState(
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
    v4 = v2(58989070, 3);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_04_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_04_NonSec__descriptor & 4) == 0 )
    {
      v17 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(
                         v13,
                         &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_18001A858,
      0x37E2887u,
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
0x18000ed40  mov     [rsp+arg_10], rbx
0x18000ed45  mov     [rsp+arg_0], rcx
0x18000ed4a  push    rbp
0x18000ed4b  push    rsi
0x18000ed4c  push    rdi
0x18000ed4d  sub     rsp, 40h
0x18000ed51  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000ed58  mov     rbx, rdx
0x18000ed5b  test    rax, rax
0x18000ed5e  jz      short loc_18000ED73
0x18000ed60  mov     edx, 3
0x18000ed65  mov     ecx, 3841A0Eh
0x18000ed6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed6f  mov     edx, eax
0x18000ed71  jmp     short loc_18000ED81
0x18000ed73  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000ed7a  test    rax, rax
0x18000ed7d  jnz     short loc_18000ED60
0x18000ed7f  xor     edx, edx
0x18000ed81  mov     r8d, edx
0x18000ed84  mov     qword ptr [rbx], 0
0x18000ed8b  and     r8d, 0FFFFFF3Fh
0x18000ed92  mov     eax, edx
0x18000ed94  and     edx, 80h
0x18000ed9a  mov     ecx, r8d
0x18000ed9d  and     ecx, 3
0x18000eda0  mov     ebp, 40h ; '@'
0x18000eda5  shl     ecx, 2
0x18000eda8  and     eax, ebp
0x18000edaa  or      ecx, eax
0x18000edac  shl     ecx, 2
0x18000edaf  or      ecx, edx
0x18000edb1  shl     ecx, 3
0x18000edb4  test    r8d, r8d
0x18000edb7  jnz     short loc_18000EDC0
0x18000edb9  mov     edx, ebp
0x18000edbb  mov     r8d, ebp
0x18000edbe  jmp     short loc_18000EDCC
0x18000edc0  xor     edx, edx
0x18000edc2  cmp     r8d, 2
0x18000edc6  cmovz   edx, ebp
0x18000edc9  mov     r8d, edx
0x18000edcc  mov     eax, ecx
0x18000edce  mov     edi, 1
0x18000edd3  or      eax, r8d
0x18000edd6  or      ecx, edx
0x18000edd8  mov     [rbx], eax
0x18000edda  bt      ecx, 0Ah
0x18000edde  jnb     short loc_18000EDED
0x18000ede0  cmp     ecx, 800h
0x18000ede6  jb      short loc_18000EDED
0x18000ede8  mov     sil, dil
0x18000edeb  jmp     short loc_18000EDFB
0x18000eded  xor     sil, sil
0x18000edf0  xor     dl, dl
0x18000edf2  test    bpl, cl
0x18000edf5  jz      loc_18000EE85
0x18000edfb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UexTest7@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7> `wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl(void)'::`2'::impl
0x18000ee02  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(wil::ReportingKind)
0x18000ee07  test    al, al
0x18000ee09  jz      short loc_18000EE76
0x18000ee0b  mov     rax, cs:Feature_Standalone_26_04_NonSec__descriptor
0x18000ee12  mov     r8d, [rax]
0x18000ee15  test    r8b, 4
0x18000ee19  jnz     short loc_18000EE30
0x18000ee1b  lea     rdx, [rsp+58h+arg_8]
0x18000ee20  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_04_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(void)
0x18000ee25  mov     rcx, [rax]
0x18000ee28  mov     [rsp+58h+arg_8], rcx
0x18000ee2d  mov     r8d, ecx
0x18000ee30  xor     eax, eax
0x18000ee32  mov     word ptr [rsp+58h+arg_0+4], 3
0x18000ee39  mov     r9d, r8d
0x18000ee3c  mov     [rsp+58h+var_28], eax
0x18000ee40  mov     dword ptr [rsp+58h+arg_0], eax
0x18000ee44  lea     rcx, qword_18001A858
0x18000ee4b  shr     r9d, 0Bh
0x18000ee4f  lea     rax, [rsp+58h+arg_0]
0x18000ee54  shr     r8d, 0Ah
0x18000ee58  and     r9d, edi
0x18000ee5b  and     r8d, edi
0x18000ee5e  mov     [rsp+58h+var_30], edi
0x18000ee62  mov     edx, 37E2887h
0x18000ee67  mov     [rsp+58h+var_38], rax
0x18000ee6c  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000ee71  mov     dl, dil
0x18000ee74  jmp     short loc_18000EE78
0x18000ee76  xor     dl, dl
0x18000ee78  test    sil, sil
0x18000ee7b  jz      short loc_18000EE85
0x18000ee7d  test    dl, dl
0x18000ee7f  jnz     short loc_18000EE85
0x18000ee81  btr     dword ptr [rbx], 0Ah
0x18000ee85  mov     eax, [rbx]
0x18000ee87  test    bpl, al
0x18000ee8a  jz      short loc_18000EE90
0x18000ee8c  test    dl, dl
0x18000ee8e  jnz     short loc_18000EE92
0x18000ee90  xor     edi, edi
0x18000ee92  and     eax, 0FFFFFFFEh
0x18000ee95  or      eax, edi
0x18000ee97  mov     [rbx], eax
0x18000ee99  mov     rax, rbx
0x18000ee9c  mov     rbx, [rsp+58h+arg_10]
0x18000eea1  add     rsp, 40h
0x18000eea5  pop     rdi
0x18000eea6  pop     rsi
0x18000eea7  pop     rbp
0x18000eea8  retn
```
