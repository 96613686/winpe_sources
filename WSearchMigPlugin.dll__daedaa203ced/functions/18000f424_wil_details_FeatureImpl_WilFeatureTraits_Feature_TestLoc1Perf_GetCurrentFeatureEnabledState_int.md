# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000f424`
- end: `0x18000f58d`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000eca4`

## callees

- `0x18000e688`
- `0x18000f424`
- `0x1800120a8`
- `0x180013e10`
- `0x180018010`

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
  wil::details *v13; // rcx
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
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_180026040, 58599532, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
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
0x18000f424  mov     [rsp+arg_10], rbx
0x18000f429  mov     [rsp+arg_0], rcx
0x18000f42e  push    rbp
0x18000f42f  push    rsi
0x18000f430  push    rdi
0x18000f431  sub     rsp, 40h
0x18000f435  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000f43c  mov     rbx, rdx
0x18000f43f  test    rax, rax
0x18000f442  jz      short loc_18000F457
0x18000f444  mov     edx, 3
0x18000f449  mov     ecx, 38419ACh
0x18000f44e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f453  mov     edx, eax
0x18000f455  jmp     short loc_18000F465
0x18000f457  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000f45e  test    rax, rax
0x18000f461  jnz     short loc_18000F444
0x18000f463  xor     edx, edx
0x18000f465  mov     r8d, edx
0x18000f468  mov     qword ptr [rbx], 0
0x18000f46f  and     r8d, 0FFFFFF3Fh
0x18000f476  mov     eax, edx
0x18000f478  and     edx, 80h
0x18000f47e  mov     ecx, r8d
0x18000f481  and     ecx, 3
0x18000f484  mov     ebp, 40h ; '@'
0x18000f489  shl     ecx, 2
0x18000f48c  and     eax, ebp
0x18000f48e  or      ecx, eax
0x18000f490  shl     ecx, 2
0x18000f493  or      ecx, edx
0x18000f495  shl     ecx, 3
0x18000f498  test    r8d, r8d
0x18000f49b  jnz     short loc_18000F4A4
0x18000f49d  mov     edx, ebp
0x18000f49f  mov     r8d, ebp
0x18000f4a2  jmp     short loc_18000F4B0
0x18000f4a4  xor     edx, edx
0x18000f4a6  cmp     r8d, 2
0x18000f4aa  cmovz   edx, ebp
0x18000f4ad  mov     r8d, edx
0x18000f4b0  mov     eax, ecx
0x18000f4b2  mov     edi, 1
0x18000f4b7  or      eax, r8d
0x18000f4ba  or      ecx, edx
0x18000f4bc  mov     [rbx], eax
0x18000f4be  bt      ecx, 0Ah
0x18000f4c2  jnb     short loc_18000F4D1
0x18000f4c4  cmp     ecx, 800h
0x18000f4ca  jb      short loc_18000F4D1
0x18000f4cc  mov     sil, dil
0x18000f4cf  jmp     short loc_18000F4DF
0x18000f4d1  xor     sil, sil
0x18000f4d4  xor     dl, dl
0x18000f4d6  test    bpl, cl
0x18000f4d9  jz      loc_18000F569
0x18000f4df  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x18000f4e6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x18000f4eb  test    al, al
0x18000f4ed  jz      short loc_18000F55A
0x18000f4ef  mov     rax, cs:Feature_Standalone_26_01_NonSec__descriptor
0x18000f4f6  mov     r8d, [rax]
0x18000f4f9  test    r8b, 4
0x18000f4fd  jnz     short loc_18000F514
0x18000f4ff  lea     rdx, [rsp+58h+arg_8]
0x18000f504  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)
0x18000f509  mov     rcx, [rax]
0x18000f50c  mov     [rsp+58h+arg_8], rcx
0x18000f511  mov     r8d, ecx
0x18000f514  xor     eax, eax
0x18000f516  mov     word ptr [rsp+58h+arg_0+4], 3
0x18000f51d  mov     r9d, r8d
0x18000f520  mov     [rsp+58h+var_28], eax
0x18000f524  mov     dword ptr [rsp+58h+arg_0], eax
0x18000f528  lea     rcx, qword_180026040
0x18000f52f  shr     r9d, 0Bh
0x18000f533  lea     rax, [rsp+58h+arg_0]
0x18000f538  shr     r8d, 0Ah
0x18000f53c  and     r9d, edi
0x18000f53f  and     r8d, edi
0x18000f542  mov     [rsp+58h+var_30], edi
0x18000f546  mov     edx, 37E286Ch
0x18000f54b  mov     [rsp+58h+var_38], rax
0x18000f550  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000f555  mov     dl, dil
0x18000f558  jmp     short loc_18000F55C
0x18000f55a  xor     dl, dl
0x18000f55c  test    sil, sil
0x18000f55f  jz      short loc_18000F569
0x18000f561  test    dl, dl
0x18000f563  jnz     short loc_18000F569
0x18000f565  btr     dword ptr [rbx], 0Ah
0x18000f569  mov     eax, [rbx]
0x18000f56b  test    bpl, al
0x18000f56e  jz      short loc_18000F574
0x18000f570  test    dl, dl
0x18000f572  jnz     short loc_18000F576
0x18000f574  xor     edi, edi
0x18000f576  and     eax, 0FFFFFFFEh
0x18000f579  or      eax, edi
0x18000f57b  mov     [rbx], eax
0x18000f57d  mov     rax, rbx
0x18000f580  mov     rbx, [rsp+58h+arg_10]
0x18000f585  add     rsp, 40h
0x18000f589  pop     rdi
0x18000f58a  pop     rsi
0x18000f58b  pop     rbp
0x18000f58c  retn
```
