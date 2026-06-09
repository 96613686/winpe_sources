# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000eca4`
- end: `0x18000ee0d`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000e604`

## callees

- `0x18000e0c8`
- `0x18000eca4`
- `0x18000fdb4`
- `0x180011590`
- `0x180015010`

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
      (__int64)&qword_18001E818,
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
0x18000eca4  mov     [rsp+arg_10], rbx
0x18000eca9  mov     [rsp+arg_0], rcx
0x18000ecae  push    rbp
0x18000ecaf  push    rsi
0x18000ecb0  push    rdi
0x18000ecb1  sub     rsp, 40h
0x18000ecb5  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000ecbc  mov     rbx, rdx
0x18000ecbf  test    rax, rax
0x18000ecc2  jz      short loc_18000ECD7
0x18000ecc4  mov     edx, 3
0x18000ecc9  mov     ecx, 3667CADh
0x18000ecce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecd3  mov     edx, eax
0x18000ecd5  jmp     short loc_18000ECE5
0x18000ecd7  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000ecde  test    rax, rax
0x18000ece1  jnz     short loc_18000ECC4
0x18000ece3  xor     edx, edx
0x18000ece5  mov     r8d, edx
0x18000ece8  mov     qword ptr [rbx], 0
0x18000ecef  and     r8d, 0FFFFFF3Fh
0x18000ecf6  mov     eax, edx
0x18000ecf8  and     edx, 80h
0x18000ecfe  mov     ecx, r8d
0x18000ed01  and     ecx, 3
0x18000ed04  mov     ebp, 40h ; '@'
0x18000ed09  shl     ecx, 2
0x18000ed0c  and     eax, ebp
0x18000ed0e  or      ecx, eax
0x18000ed10  shl     ecx, 2
0x18000ed13  or      ecx, edx
0x18000ed15  shl     ecx, 3
0x18000ed18  test    r8d, r8d
0x18000ed1b  jnz     short loc_18000ED24
0x18000ed1d  mov     edx, ebp
0x18000ed1f  mov     r8d, ebp
0x18000ed22  jmp     short loc_18000ED30
0x18000ed24  xor     edx, edx
0x18000ed26  cmp     r8d, 2
0x18000ed2a  cmovz   edx, ebp
0x18000ed2d  mov     r8d, edx
0x18000ed30  mov     eax, ecx
0x18000ed32  mov     edi, 1
0x18000ed37  or      eax, r8d
0x18000ed3a  or      ecx, edx
0x18000ed3c  mov     [rbx], eax
0x18000ed3e  bt      ecx, 0Ah
0x18000ed42  jnb     short loc_18000ED51
0x18000ed44  cmp     ecx, 800h
0x18000ed4a  jb      short loc_18000ED51
0x18000ed4c  mov     sil, dil
0x18000ed4f  jmp     short loc_18000ED5F
0x18000ed51  xor     sil, sil
0x18000ed54  xor     dl, dl
0x18000ed56  test    bpl, cl
0x18000ed59  jz      loc_18000EDE9
0x18000ed5f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x18000ed66  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x18000ed6b  test    al, al
0x18000ed6d  jz      short loc_18000EDDA
0x18000ed6f  mov     rax, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18000ed76  mov     r8d, [rax]
0x18000ed79  test    r8b, 4
0x18000ed7d  jnz     short loc_18000ED94
0x18000ed7f  lea     rdx, [rsp+58h+arg_8]
0x18000ed84  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)
0x18000ed89  mov     rcx, [rax]
0x18000ed8c  mov     [rsp+58h+arg_8], rcx
0x18000ed91  mov     r8d, ecx
0x18000ed94  xor     eax, eax
0x18000ed96  mov     word ptr [rsp+58h+arg_0+4], 3
0x18000ed9d  mov     r9d, r8d
0x18000eda0  mov     [rsp+58h+var_28], eax
0x18000eda4  mov     dword ptr [rsp+58h+arg_0], eax
0x18000eda8  lea     rcx, qword_18001E818
0x18000edaf  shr     r9d, 0Bh
0x18000edb3  lea     rax, [rsp+58h+arg_0]
0x18000edb8  shr     r8d, 0Ah
0x18000edbc  and     r9d, edi
0x18000edbf  and     r8d, edi
0x18000edc2  mov     [rsp+58h+var_30], edi
0x18000edc6  mov     edx, 2AF34FDh
0x18000edcb  mov     [rsp+58h+var_38], rax
0x18000edd0  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000edd5  mov     dl, dil
0x18000edd8  jmp     short loc_18000EDDC
0x18000edda  xor     dl, dl
0x18000eddc  test    sil, sil
0x18000eddf  jz      short loc_18000EDE9
0x18000ede1  test    dl, dl
0x18000ede3  jnz     short loc_18000EDE9
0x18000ede5  btr     dword ptr [rbx], 0Ah
0x18000ede9  mov     eax, [rbx]
0x18000edeb  test    bpl, al
0x18000edee  jz      short loc_18000EDF4
0x18000edf0  test    dl, dl
0x18000edf2  jnz     short loc_18000EDF6
0x18000edf4  xor     edi, edi
0x18000edf6  and     eax, 0FFFFFFFEh
0x18000edf9  or      eax, edi
0x18000edfb  mov     [rbx], eax
0x18000edfd  mov     rax, rbx
0x18000ee00  mov     rbx, [rsp+58h+arg_10]
0x18000ee05  add     rsp, 40h
0x18000ee09  pop     rdi
0x18000ee0a  pop     rsi
0x18000ee0b  pop     rbp
0x18000ee0c  retn
```
