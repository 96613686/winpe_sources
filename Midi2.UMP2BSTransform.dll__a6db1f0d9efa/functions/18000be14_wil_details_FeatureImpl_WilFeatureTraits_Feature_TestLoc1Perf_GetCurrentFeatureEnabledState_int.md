# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000be14`
- end: `0x18000bf7d`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000b714`

## callees

- `0x18000b0f8`
- `0x18000be14`
- `0x18000c804`
- `0x18000deb4`
- `0x18000f010`

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
      (__int64)&qword_180015828,
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
0x18000be14  mov     [rsp+arg_10], rbx
0x18000be19  mov     [rsp+arg_0], rcx
0x18000be1e  push    rbp
0x18000be1f  push    rsi
0x18000be20  push    rdi
0x18000be21  sub     rsp, 40h
0x18000be25  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000be2c  mov     rbx, rdx
0x18000be2f  test    rax, rax
0x18000be32  jz      short loc_18000BE47
0x18000be34  mov     edx, 3
0x18000be39  mov     ecx, 38419ACh
0x18000be3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be43  mov     edx, eax
0x18000be45  jmp     short loc_18000BE55
0x18000be47  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000be4e  test    rax, rax
0x18000be51  jnz     short loc_18000BE34
0x18000be53  xor     edx, edx
0x18000be55  mov     r8d, edx
0x18000be58  mov     qword ptr [rbx], 0
0x18000be5f  and     r8d, 0FFFFFF3Fh
0x18000be66  mov     eax, edx
0x18000be68  and     edx, 80h
0x18000be6e  mov     ecx, r8d
0x18000be71  and     ecx, 3
0x18000be74  mov     ebp, 40h ; '@'
0x18000be79  shl     ecx, 2
0x18000be7c  and     eax, ebp
0x18000be7e  or      ecx, eax
0x18000be80  shl     ecx, 2
0x18000be83  or      ecx, edx
0x18000be85  shl     ecx, 3
0x18000be88  test    r8d, r8d
0x18000be8b  jnz     short loc_18000BE94
0x18000be8d  mov     edx, ebp
0x18000be8f  mov     r8d, ebp
0x18000be92  jmp     short loc_18000BEA0
0x18000be94  xor     edx, edx
0x18000be96  cmp     r8d, 2
0x18000be9a  cmovz   edx, ebp
0x18000be9d  mov     r8d, edx
0x18000bea0  mov     eax, ecx
0x18000bea2  mov     edi, 1
0x18000bea7  or      eax, r8d
0x18000beaa  or      ecx, edx
0x18000beac  mov     [rbx], eax
0x18000beae  bt      ecx, 0Ah
0x18000beb2  jnb     short loc_18000BEC1
0x18000beb4  cmp     ecx, 800h
0x18000beba  jb      short loc_18000BEC1
0x18000bebc  mov     sil, dil
0x18000bebf  jmp     short loc_18000BECF
0x18000bec1  xor     sil, sil
0x18000bec4  xor     dl, dl
0x18000bec6  test    bpl, cl
0x18000bec9  jz      loc_18000BF59
0x18000becf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x18000bed6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x18000bedb  test    al, al
0x18000bedd  jz      short loc_18000BF4A
0x18000bedf  mov     rax, cs:Feature_Standalone_26_01_NonSec__descriptor
0x18000bee6  mov     r8d, [rax]
0x18000bee9  test    r8b, 4
0x18000beed  jnz     short loc_18000BF04
0x18000beef  lea     rdx, [rsp+58h+arg_8]
0x18000bef4  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)
0x18000bef9  mov     rcx, [rax]
0x18000befc  mov     [rsp+58h+arg_8], rcx
0x18000bf01  mov     r8d, ecx
0x18000bf04  xor     eax, eax
0x18000bf06  mov     word ptr [rsp+58h+arg_0+4], 3
0x18000bf0d  mov     r9d, r8d
0x18000bf10  mov     [rsp+58h+var_28], eax
0x18000bf14  mov     dword ptr [rsp+58h+arg_0], eax
0x18000bf18  lea     rcx, qword_180015828
0x18000bf1f  shr     r9d, 0Bh
0x18000bf23  lea     rax, [rsp+58h+arg_0]
0x18000bf28  shr     r8d, 0Ah
0x18000bf2c  and     r9d, edi
0x18000bf2f  and     r8d, edi
0x18000bf32  mov     [rsp+58h+var_30], edi
0x18000bf36  mov     edx, 37E286Ch
0x18000bf3b  mov     [rsp+58h+var_38], rax
0x18000bf40  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000bf45  mov     dl, dil
0x18000bf48  jmp     short loc_18000BF4C
0x18000bf4a  xor     dl, dl
0x18000bf4c  test    sil, sil
0x18000bf4f  jz      short loc_18000BF59
0x18000bf51  test    dl, dl
0x18000bf53  jnz     short loc_18000BF59
0x18000bf55  btr     dword ptr [rbx], 0Ah
0x18000bf59  mov     eax, [rbx]
0x18000bf5b  test    bpl, al
0x18000bf5e  jz      short loc_18000BF64
0x18000bf60  test    dl, dl
0x18000bf62  jnz     short loc_18000BF66
0x18000bf64  xor     edi, edi
0x18000bf66  and     eax, 0FFFFFFFEh
0x18000bf69  or      eax, edi
0x18000bf6b  mov     [rbx], eax
0x18000bf6d  mov     rax, rbx
0x18000bf70  mov     rbx, [rsp+58h+arg_10]
0x18000bf75  add     rsp, 40h
0x18000bf79  pop     rdi
0x18000bf7a  pop     rsi
0x18000bf7b  pop     rbp
0x18000bf7c  retn
```
