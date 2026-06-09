# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000ebd0`
- end: `0x18000ed39`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000e3f0`

## callees

- `0x18000dc60`
- `0x18000ebd0`
- `0x18000fbd4`
- `0x1800101b4`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(
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
    v4 = v2(58988972, 3);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor & 4) == 0 )
    {
      v17 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
                         v13,
                         &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_18001A888,
      0x37E286Cu,
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
0x18000ebd0  mov     [rsp+arg_10], rbx
0x18000ebd5  mov     [rsp+arg_0], rcx
0x18000ebda  push    rbp
0x18000ebdb  push    rsi
0x18000ebdc  push    rdi
0x18000ebdd  sub     rsp, 40h
0x18000ebe1  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000ebe8  mov     rbx, rdx
0x18000ebeb  test    rax, rax
0x18000ebee  jz      short loc_18000EC03
0x18000ebf0  mov     edx, 3
0x18000ebf5  mov     ecx, 38419ACh
0x18000ebfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebff  mov     edx, eax
0x18000ec01  jmp     short loc_18000EC11
0x18000ec03  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000ec0a  test    rax, rax
0x18000ec0d  jnz     short loc_18000EBF0
0x18000ec0f  xor     edx, edx
0x18000ec11  mov     r8d, edx
0x18000ec14  mov     qword ptr [rbx], 0
0x18000ec1b  and     r8d, 0FFFFFF3Fh
0x18000ec22  mov     eax, edx
0x18000ec24  and     edx, 80h
0x18000ec2a  mov     ecx, r8d
0x18000ec2d  and     ecx, 3
0x18000ec30  mov     ebp, 40h ; '@'
0x18000ec35  shl     ecx, 2
0x18000ec38  and     eax, ebp
0x18000ec3a  or      ecx, eax
0x18000ec3c  shl     ecx, 2
0x18000ec3f  or      ecx, edx
0x18000ec41  shl     ecx, 3
0x18000ec44  test    r8d, r8d
0x18000ec47  jnz     short loc_18000EC50
0x18000ec49  mov     edx, ebp
0x18000ec4b  mov     r8d, ebp
0x18000ec4e  jmp     short loc_18000EC5C
0x18000ec50  xor     edx, edx
0x18000ec52  cmp     r8d, 2
0x18000ec56  cmovz   edx, ebp
0x18000ec59  mov     r8d, edx
0x18000ec5c  mov     eax, ecx
0x18000ec5e  mov     edi, 1
0x18000ec63  or      eax, r8d
0x18000ec66  or      ecx, edx
0x18000ec68  mov     [rbx], eax
0x18000ec6a  bt      ecx, 0Ah
0x18000ec6e  jnb     short loc_18000EC7D
0x18000ec70  cmp     ecx, 800h
0x18000ec76  jb      short loc_18000EC7D
0x18000ec78  mov     sil, dil
0x18000ec7b  jmp     short loc_18000EC8B
0x18000ec7d  xor     sil, sil
0x18000ec80  xor     dl, dl
0x18000ec82  test    bpl, cl
0x18000ec85  jz      loc_18000ED15
0x18000ec8b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x18000ec92  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x18000ec97  test    al, al
0x18000ec99  jz      short loc_18000ED06
0x18000ec9b  mov     rax, cs:Feature_Standalone_26_01_NonSec__descriptor
0x18000eca2  mov     r8d, [rax]
0x18000eca5  test    r8b, 4
0x18000eca9  jnz     short loc_18000ECC0
0x18000ecab  lea     rdx, [rsp+58h+arg_8]
0x18000ecb0  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)
0x18000ecb5  mov     rcx, [rax]
0x18000ecb8  mov     [rsp+58h+arg_8], rcx
0x18000ecbd  mov     r8d, ecx
0x18000ecc0  xor     eax, eax
0x18000ecc2  mov     word ptr [rsp+58h+arg_0+4], 3
0x18000ecc9  mov     r9d, r8d
0x18000eccc  mov     [rsp+58h+var_28], eax
0x18000ecd0  mov     dword ptr [rsp+58h+arg_0], eax
0x18000ecd4  lea     rcx, qword_18001A888
0x18000ecdb  shr     r9d, 0Bh
0x18000ecdf  lea     rax, [rsp+58h+arg_0]
0x18000ece4  shr     r8d, 0Ah
0x18000ece8  and     r9d, edi
0x18000eceb  and     r8d, edi
0x18000ecee  mov     [rsp+58h+var_30], edi
0x18000ecf2  mov     edx, 37E286Ch
0x18000ecf7  mov     [rsp+58h+var_38], rax
0x18000ecfc  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000ed01  mov     dl, dil
0x18000ed04  jmp     short loc_18000ED08
0x18000ed06  xor     dl, dl
0x18000ed08  test    sil, sil
0x18000ed0b  jz      short loc_18000ED15
0x18000ed0d  test    dl, dl
0x18000ed0f  jnz     short loc_18000ED15
0x18000ed11  btr     dword ptr [rbx], 0Ah
0x18000ed15  mov     eax, [rbx]
0x18000ed17  test    bpl, al
0x18000ed1a  jz      short loc_18000ED20
0x18000ed1c  test    dl, dl
0x18000ed1e  jnz     short loc_18000ED22
0x18000ed20  xor     edi, edi
0x18000ed22  and     eax, 0FFFFFFFEh
0x18000ed25  or      eax, edi
0x18000ed27  mov     [rbx], eax
0x18000ed29  mov     rax, rbx
0x18000ed2c  mov     rbx, [rsp+58h+arg_10]
0x18000ed31  add     rsp, 40h
0x18000ed35  pop     rdi
0x18000ed36  pop     rsi
0x18000ed37  pop     rbp
0x18000ed38  retn
```
