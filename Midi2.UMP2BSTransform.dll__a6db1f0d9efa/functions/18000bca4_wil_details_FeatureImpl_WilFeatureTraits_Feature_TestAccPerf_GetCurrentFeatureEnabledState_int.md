# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000bca4`
- end: `0x18000be0d`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000b634`

## callees

- `0x18000af84`
- `0x18000bca4`
- `0x18000c804`
- `0x18000e088`
- `0x18000f010`

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
      (__int64)&qword_180015838,
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
0x18000bca4  mov     [rsp+arg_10], rbx
0x18000bca9  mov     [rsp+arg_0], rcx
0x18000bcae  push    rbp
0x18000bcaf  push    rsi
0x18000bcb0  push    rdi
0x18000bcb1  sub     rsp, 40h
0x18000bcb5  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000bcbc  mov     rbx, rdx
0x18000bcbf  test    rax, rax
0x18000bcc2  jz      short loc_18000BCD7
0x18000bcc4  mov     edx, 3
0x18000bcc9  mov     ecx, 3667CADh
0x18000bcce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcd3  mov     edx, eax
0x18000bcd5  jmp     short loc_18000BCE5
0x18000bcd7  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000bcde  test    rax, rax
0x18000bce1  jnz     short loc_18000BCC4
0x18000bce3  xor     edx, edx
0x18000bce5  mov     r8d, edx
0x18000bce8  mov     qword ptr [rbx], 0
0x18000bcef  and     r8d, 0FFFFFF3Fh
0x18000bcf6  mov     eax, edx
0x18000bcf8  and     edx, 80h
0x18000bcfe  mov     ecx, r8d
0x18000bd01  and     ecx, 3
0x18000bd04  mov     ebp, 40h ; '@'
0x18000bd09  shl     ecx, 2
0x18000bd0c  and     eax, ebp
0x18000bd0e  or      ecx, eax
0x18000bd10  shl     ecx, 2
0x18000bd13  or      ecx, edx
0x18000bd15  shl     ecx, 3
0x18000bd18  test    r8d, r8d
0x18000bd1b  jnz     short loc_18000BD24
0x18000bd1d  mov     edx, ebp
0x18000bd1f  mov     r8d, ebp
0x18000bd22  jmp     short loc_18000BD30
0x18000bd24  xor     edx, edx
0x18000bd26  cmp     r8d, 2
0x18000bd2a  cmovz   edx, ebp
0x18000bd2d  mov     r8d, edx
0x18000bd30  mov     eax, ecx
0x18000bd32  mov     edi, 1
0x18000bd37  or      eax, r8d
0x18000bd3a  or      ecx, edx
0x18000bd3c  mov     [rbx], eax
0x18000bd3e  bt      ecx, 0Ah
0x18000bd42  jnb     short loc_18000BD51
0x18000bd44  cmp     ecx, 800h
0x18000bd4a  jb      short loc_18000BD51
0x18000bd4c  mov     sil, dil
0x18000bd4f  jmp     short loc_18000BD5F
0x18000bd51  xor     sil, sil
0x18000bd54  xor     dl, dl
0x18000bd56  test    bpl, cl
0x18000bd59  jz      loc_18000BDE9
0x18000bd5f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x18000bd66  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x18000bd6b  test    al, al
0x18000bd6d  jz      short loc_18000BDDA
0x18000bd6f  mov     rax, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18000bd76  mov     r8d, [rax]
0x18000bd79  test    r8b, 4
0x18000bd7d  jnz     short loc_18000BD94
0x18000bd7f  lea     rdx, [rsp+58h+arg_8]
0x18000bd84  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)
0x18000bd89  mov     rcx, [rax]
0x18000bd8c  mov     [rsp+58h+arg_8], rcx
0x18000bd91  mov     r8d, ecx
0x18000bd94  xor     eax, eax
0x18000bd96  mov     word ptr [rsp+58h+arg_0+4], 3
0x18000bd9d  mov     r9d, r8d
0x18000bda0  mov     [rsp+58h+var_28], eax
0x18000bda4  mov     dword ptr [rsp+58h+arg_0], eax
0x18000bda8  lea     rcx, qword_180015838
0x18000bdaf  shr     r9d, 0Bh
0x18000bdb3  lea     rax, [rsp+58h+arg_0]
0x18000bdb8  shr     r8d, 0Ah
0x18000bdbc  and     r9d, edi
0x18000bdbf  and     r8d, edi
0x18000bdc2  mov     [rsp+58h+var_30], edi
0x18000bdc6  mov     edx, 2AF34FDh
0x18000bdcb  mov     [rsp+58h+var_38], rax
0x18000bdd0  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000bdd5  mov     dl, dil
0x18000bdd8  jmp     short loc_18000BDDC
0x18000bdda  xor     dl, dl
0x18000bddc  test    sil, sil
0x18000bddf  jz      short loc_18000BDE9
0x18000bde1  test    dl, dl
0x18000bde3  jnz     short loc_18000BDE9
0x18000bde5  btr     dword ptr [rbx], 0Ah
0x18000bde9  mov     eax, [rbx]
0x18000bdeb  test    bpl, al
0x18000bdee  jz      short loc_18000BDF4
0x18000bdf0  test    dl, dl
0x18000bdf2  jnz     short loc_18000BDF6
0x18000bdf4  xor     edi, edi
0x18000bdf6  and     eax, 0FFFFFFFEh
0x18000bdf9  or      eax, edi
0x18000bdfb  mov     [rbx], eax
0x18000bdfd  mov     rax, rbx
0x18000be00  mov     rbx, [rsp+58h+arg_10]
0x18000be05  add     rsp, 40h
0x18000be09  pop     rdi
0x18000be0a  pop     rsi
0x18000be0b  pop     rbp
0x18000be0c  retn
```
