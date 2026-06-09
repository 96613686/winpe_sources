# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800101d0`
- end: `0x180010339`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000fa80`

## callees

- `0x18000f25c`
- `0x1800101d0`
- `0x180011204`
- `0x180011e28`
- `0x180021010`

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
      (__int64)&qword_18002DD88,
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
0x1800101d0  mov     [rsp+arg_10], rbx
0x1800101d5  mov     [rsp+arg_0], rcx
0x1800101da  push    rbp
0x1800101db  push    rsi
0x1800101dc  push    rdi
0x1800101dd  sub     rsp, 40h
0x1800101e1  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800101e8  mov     rbx, rdx
0x1800101eb  test    rax, rax
0x1800101ee  jz      short loc_180010203
0x1800101f0  mov     edx, 3
0x1800101f5  mov     ecx, 3667CADh
0x1800101fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101ff  mov     edx, eax
0x180010201  jmp     short loc_180010211
0x180010203  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001020a  test    rax, rax
0x18001020d  jnz     short loc_1800101F0
0x18001020f  xor     edx, edx
0x180010211  mov     r8d, edx
0x180010214  mov     qword ptr [rbx], 0
0x18001021b  and     r8d, 0FFFFFF3Fh
0x180010222  mov     eax, edx
0x180010224  and     edx, 80h
0x18001022a  mov     ecx, r8d
0x18001022d  and     ecx, 3
0x180010230  mov     ebp, 40h ; '@'
0x180010235  shl     ecx, 2
0x180010238  and     eax, ebp
0x18001023a  or      ecx, eax
0x18001023c  shl     ecx, 2
0x18001023f  or      ecx, edx
0x180010241  shl     ecx, 3
0x180010244  test    r8d, r8d
0x180010247  jnz     short loc_180010250
0x180010249  mov     edx, ebp
0x18001024b  mov     r8d, ebp
0x18001024e  jmp     short loc_18001025C
0x180010250  xor     edx, edx
0x180010252  cmp     r8d, 2
0x180010256  cmovz   edx, ebp
0x180010259  mov     r8d, edx
0x18001025c  mov     eax, ecx
0x18001025e  mov     edi, 1
0x180010263  or      eax, r8d
0x180010266  or      ecx, edx
0x180010268  mov     [rbx], eax
0x18001026a  bt      ecx, 0Ah
0x18001026e  jnb     short loc_18001027D
0x180010270  cmp     ecx, 800h
0x180010276  jb      short loc_18001027D
0x180010278  mov     sil, dil
0x18001027b  jmp     short loc_18001028B
0x18001027d  xor     sil, sil
0x180010280  xor     dl, dl
0x180010282  test    bpl, cl
0x180010285  jz      loc_180010315
0x18001028b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x180010292  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x180010297  test    al, al
0x180010299  jz      short loc_180010306
0x18001029b  mov     rax, cs:Feature_Standalone_25_11_NonSec__descriptor
0x1800102a2  mov     r8d, [rax]
0x1800102a5  test    r8b, 4
0x1800102a9  jnz     short loc_1800102C0
0x1800102ab  lea     rdx, [rsp+58h+arg_8]
0x1800102b0  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)
0x1800102b5  mov     rcx, [rax]
0x1800102b8  mov     [rsp+58h+arg_8], rcx
0x1800102bd  mov     r8d, ecx
0x1800102c0  xor     eax, eax
0x1800102c2  mov     word ptr [rsp+58h+arg_0+4], 3
0x1800102c9  mov     r9d, r8d
0x1800102cc  mov     [rsp+58h+var_28], eax
0x1800102d0  mov     dword ptr [rsp+58h+arg_0], eax
0x1800102d4  lea     rcx, qword_18002DD88
0x1800102db  shr     r9d, 0Bh
0x1800102df  lea     rax, [rsp+58h+arg_0]
0x1800102e4  shr     r8d, 0Ah
0x1800102e8  and     r9d, edi
0x1800102eb  and     r8d, edi
0x1800102ee  mov     [rsp+58h+var_30], edi
0x1800102f2  mov     edx, 2AF34FDh
0x1800102f7  mov     [rsp+58h+var_38], rax
0x1800102fc  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180010301  mov     dl, dil
0x180010304  jmp     short loc_180010308
0x180010306  xor     dl, dl
0x180010308  test    sil, sil
0x18001030b  jz      short loc_180010315
0x18001030d  test    dl, dl
0x18001030f  jnz     short loc_180010315
0x180010311  btr     dword ptr [rbx], 0Ah
0x180010315  mov     eax, [rbx]
0x180010317  test    bpl, al
0x18001031a  jz      short loc_180010320
0x18001031c  test    dl, dl
0x18001031e  jnz     short loc_180010322
0x180010320  xor     edi, edi
0x180010322  and     eax, 0FFFFFFFEh
0x180010325  or      eax, edi
0x180010327  mov     [rbx], eax
0x180010329  mov     rax, rbx
0x18001032c  mov     rbx, [rsp+58h+arg_10]
0x180010331  add     rsp, 40h
0x180010335  pop     rdi
0x180010336  pop     rsi
0x180010337  pop     rbp
0x180010338  retn
```
