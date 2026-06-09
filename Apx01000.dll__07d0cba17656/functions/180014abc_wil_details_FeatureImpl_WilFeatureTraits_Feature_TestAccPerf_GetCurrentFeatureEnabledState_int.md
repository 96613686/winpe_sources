# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180014abc`
- end: `0x180014c25`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180013d18`

## callees

- `0x18000ab68`
- `0x1800134f4`
- `0x180014abc`
- `0x1800157e4`
- `0x18002a010`

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
    wil::details::ReportUsageToService(&qword_180033798, 45036797, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
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
0x180014abc  mov     [rsp+arg_10], rbx
0x180014ac1  mov     [rsp+arg_0], rcx
0x180014ac6  push    rbp
0x180014ac7  push    rsi
0x180014ac8  push    rdi
0x180014ac9  sub     rsp, 40h
0x180014acd  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180014ad4  mov     rbx, rdx
0x180014ad7  test    rax, rax
0x180014ada  jz      short loc_180014AEF
0x180014adc  mov     edx, 3
0x180014ae1  mov     ecx, 3667CADh
0x180014ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014aeb  mov     edx, eax
0x180014aed  jmp     short loc_180014AFD
0x180014aef  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180014af6  test    rax, rax
0x180014af9  jnz     short loc_180014ADC
0x180014afb  xor     edx, edx
0x180014afd  mov     r8d, edx
0x180014b00  mov     qword ptr [rbx], 0
0x180014b07  and     r8d, 0FFFFFF3Fh
0x180014b0e  mov     eax, edx
0x180014b10  and     edx, 80h
0x180014b16  mov     ecx, r8d
0x180014b19  and     ecx, 3
0x180014b1c  mov     ebp, 40h ; '@'
0x180014b21  shl     ecx, 2
0x180014b24  and     eax, ebp
0x180014b26  or      ecx, eax
0x180014b28  shl     ecx, 2
0x180014b2b  or      ecx, edx
0x180014b2d  shl     ecx, 3
0x180014b30  test    r8d, r8d
0x180014b33  jnz     short loc_180014B3C
0x180014b35  mov     edx, ebp
0x180014b37  mov     r8d, ebp
0x180014b3a  jmp     short loc_180014B48
0x180014b3c  xor     edx, edx
0x180014b3e  cmp     r8d, 2
0x180014b42  cmovz   edx, ebp
0x180014b45  mov     r8d, edx
0x180014b48  mov     eax, ecx
0x180014b4a  mov     edi, 1
0x180014b4f  or      eax, r8d
0x180014b52  or      ecx, edx
0x180014b54  mov     [rbx], eax
0x180014b56  bt      ecx, 0Ah
0x180014b5a  jnb     short loc_180014B69
0x180014b5c  cmp     ecx, 800h
0x180014b62  jb      short loc_180014B69
0x180014b64  mov     sil, dil
0x180014b67  jmp     short loc_180014B77
0x180014b69  xor     sil, sil
0x180014b6c  xor     dl, dl
0x180014b6e  test    bpl, cl
0x180014b71  jz      loc_180014C01
0x180014b77  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x180014b7e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x180014b83  test    al, al
0x180014b85  jz      short loc_180014BF2
0x180014b87  mov     rax, cs:Feature_Standalone_25_11_NonSec__descriptor
0x180014b8e  mov     r8d, [rax]
0x180014b91  test    r8b, 4
0x180014b95  jnz     short loc_180014BAC
0x180014b97  lea     rdx, [rsp+58h+arg_8]
0x180014b9c  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)
0x180014ba1  mov     rcx, [rax]
0x180014ba4  mov     [rsp+58h+arg_8], rcx
0x180014ba9  mov     r8d, ecx
0x180014bac  xor     eax, eax
0x180014bae  mov     word ptr [rsp+58h+arg_0+4], 3
0x180014bb5  mov     r9d, r8d
0x180014bb8  mov     [rsp+58h+var_28], eax
0x180014bbc  mov     dword ptr [rsp+58h+arg_0], eax
0x180014bc0  lea     rcx, qword_180033798
0x180014bc7  shr     r9d, 0Bh
0x180014bcb  lea     rax, [rsp+58h+arg_0]
0x180014bd0  shr     r8d, 0Ah
0x180014bd4  and     r9d, edi
0x180014bd7  and     r8d, edi
0x180014bda  mov     [rsp+58h+var_30], edi
0x180014bde  mov     edx, 2AF34FDh
0x180014be3  mov     [rsp+58h+var_38], rax
0x180014be8  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180014bed  mov     dl, dil
0x180014bf0  jmp     short loc_180014BF4
0x180014bf2  xor     dl, dl
0x180014bf4  test    sil, sil
0x180014bf7  jz      short loc_180014C01
0x180014bf9  test    dl, dl
0x180014bfb  jnz     short loc_180014C01
0x180014bfd  btr     dword ptr [rbx], 0Ah
0x180014c01  mov     eax, [rbx]
0x180014c03  test    bpl, al
0x180014c06  jz      short loc_180014C0C
0x180014c08  test    dl, dl
0x180014c0a  jnz     short loc_180014C0E
0x180014c0c  xor     edi, edi
0x180014c0e  and     eax, 0FFFFFFFEh
0x180014c11  or      eax, edi
0x180014c13  mov     [rbx], eax
0x180014c15  mov     rax, rbx
0x180014c18  mov     rbx, [rsp+58h+arg_10]
0x180014c1d  add     rsp, 40h
0x180014c21  pop     rdi
0x180014c22  pop     rsi
0x180014c23  pop     rbp
0x180014c24  retn
```
