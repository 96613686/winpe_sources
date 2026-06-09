# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000eb34`
- end: `0x18000ec9d`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000e524`

## callees

- `0x18000e3b0`
- `0x18000eb34`
- `0x18000fdb4`
- `0x1800114f4`
- `0x180015010`

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
      (__int64)&qword_18001E860,
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
0x18000eb34  mov     [rsp+arg_10], rbx
0x18000eb39  mov     [rsp+arg_0], rcx
0x18000eb3e  push    rbp
0x18000eb3f  push    rsi
0x18000eb40  push    rdi
0x18000eb41  sub     rsp, 40h
0x18000eb45  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000eb4c  mov     rbx, rdx
0x18000eb4f  test    rax, rax
0x18000eb52  jz      short loc_18000EB67
0x18000eb54  mov     edx, 3
0x18000eb59  mov     ecx, 38419CAh
0x18000eb5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb63  mov     edx, eax
0x18000eb65  jmp     short loc_18000EB75
0x18000eb67  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000eb6e  test    rax, rax
0x18000eb71  jnz     short loc_18000EB54
0x18000eb73  xor     edx, edx
0x18000eb75  mov     r8d, edx
0x18000eb78  mov     qword ptr [rbx], 0
0x18000eb7f  and     r8d, 0FFFFFF3Fh
0x18000eb86  mov     eax, edx
0x18000eb88  and     edx, 80h
0x18000eb8e  mov     ecx, r8d
0x18000eb91  and     ecx, 3
0x18000eb94  mov     ebp, 40h ; '@'
0x18000eb99  shl     ecx, 2
0x18000eb9c  and     eax, ebp
0x18000eb9e  or      ecx, eax
0x18000eba0  shl     ecx, 2
0x18000eba3  or      ecx, edx
0x18000eba5  shl     ecx, 3
0x18000eba8  test    r8d, r8d
0x18000ebab  jnz     short loc_18000EBB4
0x18000ebad  mov     edx, ebp
0x18000ebaf  mov     r8d, ebp
0x18000ebb2  jmp     short loc_18000EBC0
0x18000ebb4  xor     edx, edx
0x18000ebb6  cmp     r8d, 2
0x18000ebba  cmovz   edx, ebp
0x18000ebbd  mov     r8d, edx
0x18000ebc0  mov     eax, ecx
0x18000ebc2  mov     edi, 1
0x18000ebc7  or      eax, r8d
0x18000ebca  or      ecx, edx
0x18000ebcc  mov     [rbx], eax
0x18000ebce  bt      ecx, 0Ah
0x18000ebd2  jnb     short loc_18000EBE1
0x18000ebd4  cmp     ecx, 800h
0x18000ebda  jb      short loc_18000EBE1
0x18000ebdc  mov     sil, dil
0x18000ebdf  jmp     short loc_18000EBEF
0x18000ebe1  xor     sil, sil
0x18000ebe4  xor     dl, dl
0x18000ebe6  test    bpl, cl
0x18000ebe9  jz      loc_18000EC79
0x18000ebef  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x18000ebf6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x18000ebfb  test    al, al
0x18000ebfd  jz      short loc_18000EC6A
0x18000ebff  mov     rax, cs:Feature_Standalone_26_02_NonSec__descriptor
0x18000ec06  mov     r8d, [rax]
0x18000ec09  test    r8b, 4
0x18000ec0d  jnz     short loc_18000EC24
0x18000ec0f  lea     rdx, [rsp+58h+arg_8]
0x18000ec14  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)
0x18000ec19  mov     rcx, [rax]
0x18000ec1c  mov     [rsp+58h+arg_8], rcx
0x18000ec21  mov     r8d, ecx
0x18000ec24  xor     eax, eax
0x18000ec26  mov     word ptr [rsp+58h+arg_0+4], 3
0x18000ec2d  mov     r9d, r8d
0x18000ec30  mov     [rsp+58h+var_28], eax
0x18000ec34  mov     dword ptr [rsp+58h+arg_0], eax
0x18000ec38  lea     rcx, qword_18001E860
0x18000ec3f  shr     r9d, 0Bh
0x18000ec43  lea     rax, [rsp+58h+arg_0]
0x18000ec48  shr     r8d, 0Ah
0x18000ec4c  and     r9d, edi
0x18000ec4f  and     r8d, edi
0x18000ec52  mov     [rsp+58h+var_30], edi
0x18000ec56  mov     edx, 37E287Eh
0x18000ec5b  mov     [rsp+58h+var_38], rax
0x18000ec60  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000ec65  mov     dl, dil
0x18000ec68  jmp     short loc_18000EC6C
0x18000ec6a  xor     dl, dl
0x18000ec6c  test    sil, sil
0x18000ec6f  jz      short loc_18000EC79
0x18000ec71  test    dl, dl
0x18000ec73  jnz     short loc_18000EC79
0x18000ec75  btr     dword ptr [rbx], 0Ah
0x18000ec79  mov     eax, [rbx]
0x18000ec7b  test    bpl, al
0x18000ec7e  jz      short loc_18000EC84
0x18000ec80  test    dl, dl
0x18000ec82  jnz     short loc_18000EC86
0x18000ec84  xor     edi, edi
0x18000ec86  and     eax, 0FFFFFFFEh
0x18000ec89  or      eax, edi
0x18000ec8b  mov     [rbx], eax
0x18000ec8d  mov     rax, rbx
0x18000ec90  mov     rbx, [rsp+58h+arg_10]
0x18000ec95  add     rsp, 40h
0x18000ec99  pop     rdi
0x18000ec9a  pop     rsi
0x18000ec9b  pop     rbp
0x18000ec9c  retn
```
