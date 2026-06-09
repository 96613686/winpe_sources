# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000ea60`
- end: `0x18000ebc9`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000e310`

## callees

- `0x18000daec`
- `0x18000ea60`
- `0x18000fbd4`
- `0x180010424`
- `0x180013010`

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
  __int64 v13; // rcx
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
      v17 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
                         v13,
                         &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_18001A898,
      0x2AF34FDu,
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
0x18000ea60  mov     [rsp+arg_10], rbx
0x18000ea65  mov     [rsp+arg_0], rcx
0x18000ea6a  push    rbp
0x18000ea6b  push    rsi
0x18000ea6c  push    rdi
0x18000ea6d  sub     rsp, 40h
0x18000ea71  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000ea78  mov     rbx, rdx
0x18000ea7b  test    rax, rax
0x18000ea7e  jz      short loc_18000EA93
0x18000ea80  mov     edx, 3
0x18000ea85  mov     ecx, 3667CADh
0x18000ea8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea8f  mov     edx, eax
0x18000ea91  jmp     short loc_18000EAA1
0x18000ea93  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000ea9a  test    rax, rax
0x18000ea9d  jnz     short loc_18000EA80
0x18000ea9f  xor     edx, edx
0x18000eaa1  mov     r8d, edx
0x18000eaa4  mov     qword ptr [rbx], 0
0x18000eaab  and     r8d, 0FFFFFF3Fh
0x18000eab2  mov     eax, edx
0x18000eab4  and     edx, 80h
0x18000eaba  mov     ecx, r8d
0x18000eabd  and     ecx, 3
0x18000eac0  mov     ebp, 40h ; '@'
0x18000eac5  shl     ecx, 2
0x18000eac8  and     eax, ebp
0x18000eaca  or      ecx, eax
0x18000eacc  shl     ecx, 2
0x18000eacf  or      ecx, edx
0x18000ead1  shl     ecx, 3
0x18000ead4  test    r8d, r8d
0x18000ead7  jnz     short loc_18000EAE0
0x18000ead9  mov     edx, ebp
0x18000eadb  mov     r8d, ebp
0x18000eade  jmp     short loc_18000EAEC
0x18000eae0  xor     edx, edx
0x18000eae2  cmp     r8d, 2
0x18000eae6  cmovz   edx, ebp
0x18000eae9  mov     r8d, edx
0x18000eaec  mov     eax, ecx
0x18000eaee  mov     edi, 1
0x18000eaf3  or      eax, r8d
0x18000eaf6  or      ecx, edx
0x18000eaf8  mov     [rbx], eax
0x18000eafa  bt      ecx, 0Ah
0x18000eafe  jnb     short loc_18000EB0D
0x18000eb00  cmp     ecx, 800h
0x18000eb06  jb      short loc_18000EB0D
0x18000eb08  mov     sil, dil
0x18000eb0b  jmp     short loc_18000EB1B
0x18000eb0d  xor     sil, sil
0x18000eb10  xor     dl, dl
0x18000eb12  test    bpl, cl
0x18000eb15  jz      loc_18000EBA5
0x18000eb1b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x18000eb22  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x18000eb27  test    al, al
0x18000eb29  jz      short loc_18000EB96
0x18000eb2b  mov     rax, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18000eb32  mov     r8d, [rax]
0x18000eb35  test    r8b, 4
0x18000eb39  jnz     short loc_18000EB50
0x18000eb3b  lea     rdx, [rsp+58h+arg_8]
0x18000eb40  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)
0x18000eb45  mov     rcx, [rax]
0x18000eb48  mov     [rsp+58h+arg_8], rcx
0x18000eb4d  mov     r8d, ecx
0x18000eb50  xor     eax, eax
0x18000eb52  mov     word ptr [rsp+58h+arg_0+4], 3
0x18000eb59  mov     r9d, r8d
0x18000eb5c  mov     [rsp+58h+var_28], eax
0x18000eb60  mov     dword ptr [rsp+58h+arg_0], eax
0x18000eb64  lea     rcx, qword_18001A898
0x18000eb6b  shr     r9d, 0Bh
0x18000eb6f  lea     rax, [rsp+58h+arg_0]
0x18000eb74  shr     r8d, 0Ah
0x18000eb78  and     r9d, edi
0x18000eb7b  and     r8d, edi
0x18000eb7e  mov     [rsp+58h+var_30], edi
0x18000eb82  mov     edx, 2AF34FDh
0x18000eb87  mov     [rsp+58h+var_38], rax
0x18000eb8c  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000eb91  mov     dl, dil
0x18000eb94  jmp     short loc_18000EB98
0x18000eb96  xor     dl, dl
0x18000eb98  test    sil, sil
0x18000eb9b  jz      short loc_18000EBA5
0x18000eb9d  test    dl, dl
0x18000eb9f  jnz     short loc_18000EBA5
0x18000eba1  btr     dword ptr [rbx], 0Ah
0x18000eba5  mov     eax, [rbx]
0x18000eba7  test    bpl, al
0x18000ebaa  jz      short loc_18000EBB0
0x18000ebac  test    dl, dl
0x18000ebae  jnz     short loc_18000EBB2
0x18000ebb0  xor     edi, edi
0x18000ebb2  and     eax, 0FFFFFFFEh
0x18000ebb5  or      eax, edi
0x18000ebb7  mov     [rbx], eax
0x18000ebb9  mov     rax, rbx
0x18000ebbc  mov     rbx, [rsp+58h+arg_10]
0x18000ebc1  add     rsp, 40h
0x18000ebc5  pop     rdi
0x18000ebc6  pop     rsi
0x18000ebc7  pop     rbp
0x18000ebc8  retn
```
