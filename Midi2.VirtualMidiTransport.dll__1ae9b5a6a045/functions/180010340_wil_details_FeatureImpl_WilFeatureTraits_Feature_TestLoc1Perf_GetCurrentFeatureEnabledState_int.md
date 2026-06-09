# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180010340`
- end: `0x1800104a9`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000fb60`

## callees

- `0x18000f3d0`
- `0x180010340`
- `0x180011204`
- `0x180011bb8`
- `0x180021010`

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
      (__int64)&qword_18002DD78,
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
0x180010340  mov     [rsp+arg_10], rbx
0x180010345  mov     [rsp+arg_0], rcx
0x18001034a  push    rbp
0x18001034b  push    rsi
0x18001034c  push    rdi
0x18001034d  sub     rsp, 40h
0x180010351  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180010358  mov     rbx, rdx
0x18001035b  test    rax, rax
0x18001035e  jz      short loc_180010373
0x180010360  mov     edx, 3
0x180010365  mov     ecx, 38419ACh
0x18001036a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001036f  mov     edx, eax
0x180010371  jmp     short loc_180010381
0x180010373  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001037a  test    rax, rax
0x18001037d  jnz     short loc_180010360
0x18001037f  xor     edx, edx
0x180010381  mov     r8d, edx
0x180010384  mov     qword ptr [rbx], 0
0x18001038b  and     r8d, 0FFFFFF3Fh
0x180010392  mov     eax, edx
0x180010394  and     edx, 80h
0x18001039a  mov     ecx, r8d
0x18001039d  and     ecx, 3
0x1800103a0  mov     ebp, 40h ; '@'
0x1800103a5  shl     ecx, 2
0x1800103a8  and     eax, ebp
0x1800103aa  or      ecx, eax
0x1800103ac  shl     ecx, 2
0x1800103af  or      ecx, edx
0x1800103b1  shl     ecx, 3
0x1800103b4  test    r8d, r8d
0x1800103b7  jnz     short loc_1800103C0
0x1800103b9  mov     edx, ebp
0x1800103bb  mov     r8d, ebp
0x1800103be  jmp     short loc_1800103CC
0x1800103c0  xor     edx, edx
0x1800103c2  cmp     r8d, 2
0x1800103c6  cmovz   edx, ebp
0x1800103c9  mov     r8d, edx
0x1800103cc  mov     eax, ecx
0x1800103ce  mov     edi, 1
0x1800103d3  or      eax, r8d
0x1800103d6  or      ecx, edx
0x1800103d8  mov     [rbx], eax
0x1800103da  bt      ecx, 0Ah
0x1800103de  jnb     short loc_1800103ED
0x1800103e0  cmp     ecx, 800h
0x1800103e6  jb      short loc_1800103ED
0x1800103e8  mov     sil, dil
0x1800103eb  jmp     short loc_1800103FB
0x1800103ed  xor     sil, sil
0x1800103f0  xor     dl, dl
0x1800103f2  test    bpl, cl
0x1800103f5  jz      loc_180010485
0x1800103fb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x180010402  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x180010407  test    al, al
0x180010409  jz      short loc_180010476
0x18001040b  mov     rax, cs:Feature_Standalone_26_01_NonSec__descriptor
0x180010412  mov     r8d, [rax]
0x180010415  test    r8b, 4
0x180010419  jnz     short loc_180010430
0x18001041b  lea     rdx, [rsp+58h+arg_8]
0x180010420  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)
0x180010425  mov     rcx, [rax]
0x180010428  mov     [rsp+58h+arg_8], rcx
0x18001042d  mov     r8d, ecx
0x180010430  xor     eax, eax
0x180010432  mov     word ptr [rsp+58h+arg_0+4], 3
0x180010439  mov     r9d, r8d
0x18001043c  mov     [rsp+58h+var_28], eax
0x180010440  mov     dword ptr [rsp+58h+arg_0], eax
0x180010444  lea     rcx, qword_18002DD78
0x18001044b  shr     r9d, 0Bh
0x18001044f  lea     rax, [rsp+58h+arg_0]
0x180010454  shr     r8d, 0Ah
0x180010458  and     r9d, edi
0x18001045b  and     r8d, edi
0x18001045e  mov     [rsp+58h+var_30], edi
0x180010462  mov     edx, 37E286Ch
0x180010467  mov     [rsp+58h+var_38], rax
0x18001046c  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180010471  mov     dl, dil
0x180010474  jmp     short loc_180010478
0x180010476  xor     dl, dl
0x180010478  test    sil, sil
0x18001047b  jz      short loc_180010485
0x18001047d  test    dl, dl
0x18001047f  jnz     short loc_180010485
0x180010481  btr     dword ptr [rbx], 0Ah
0x180010485  mov     eax, [rbx]
0x180010487  test    bpl, al
0x18001048a  jz      short loc_180010490
0x18001048c  test    dl, dl
0x18001048e  jnz     short loc_180010492
0x180010490  xor     edi, edi
0x180010492  and     eax, 0FFFFFFFEh
0x180010495  or      eax, edi
0x180010497  mov     [rbx], eax
0x180010499  mov     rax, rbx
0x18001049c  mov     rbx, [rsp+58h+arg_10]
0x1800104a1  add     rsp, 40h
0x1800104a5  pop     rdi
0x1800104a6  pop     rsi
0x1800104a7  pop     rbp
0x1800104a8  retn
```
