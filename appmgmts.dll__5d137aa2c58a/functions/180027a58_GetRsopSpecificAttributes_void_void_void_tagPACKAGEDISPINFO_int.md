# GetRsopSpecificAttributes(void *,void *,void *,tagPACKAGEDISPINFO *,int *)

- ea: `0x180027a58`
- end: `0x180027cbc`
- name: `?GetRsopSpecificAttributes@@YAJPEAX00PEAUtagPACKAGEDISPINFO@@PEAH@Z`
- size: `612`
- prototype: `__int64 __fastcall(void *, void *, void *, struct tagPACKAGEDISPINFO *, int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180025378`
- `0x180026040`

## callees

- `0x18001e754`
- `0x1800234b0`
- `0x180024ea0`
- `0x180024f20`
- `0x180027a58`
- `0x180027cc4`

## import_xrefs

- `adsldpc!ADSIFreeColumn` at `0x180027b1c`
- `adsldpc!ADSIFreeColumn` at `0x180027b88`
- `adsldpc!ADSIFreeColumn` at `0x180027bfa`
- `adsldpc!ADSIFreeColumn` at `0x180027c45`
- `adsldpc!ADSIFreeColumn` at `0x180027c8a`
- `adsldpc!ADSIFreeColumn` at `0x180027b1c`
- `adsldpc!ADSIFreeColumn` at `0x180027b88`
- `adsldpc!ADSIFreeColumn` at `0x180027bfa`
- `adsldpc!ADSIFreeColumn` at `0x180027c45`
- `adsldpc!ADSIFreeColumn` at `0x180027c8a`

## string_xrefs

- `0x180027b98`: `msiFileList`

## pseudocode

```c
__int64 __fastcall GetRsopSpecificAttributes(void *a1, void *a2, void *a3, struct tagPACKAGEDISPINFO *a4, int *a5)
{
  int *v5; // r15
  char *v10; // r12
  char *v11; // rsi
  int v12; // esi
  ADS_BOOLEAN v13; // ecx
  ADS_BOOLEAN Boolean; // ecx
  struct ads_search_column v16; // [rsp+30h] [rbp-51h] BYREF
  struct ads_search_column v17[2]; // [rsp+60h] [rbp-21h] BYREF

  v5 = a5;
  memset(&v16, 0, sizeof(v16));
  if ( a5 )
    *a5 = 1;
  v10 = (char *)a4 + 184;
  *((_QWORD *)a4 + 17) = 0;
  v11 = (char *)a4 + 168;
  *((_DWORD *)a4 + 36) = 0;
  *((_DWORD *)a4 + 44) = 0;
  *((_DWORD *)a4 + 41) = 0;
  *((_QWORD *)a4 + 23) = 0;
  *((_QWORD *)a4 + 21) = 0;
  if ( (int)DSGetAndValidateColumn(a1, a2, ADSTYPE_CASE_IGNORE_STRING, L"vendor", &v16) >= 0 )
  {
    v17[0] = v16;
    UnpackStrAllocFrom<_ads_attr_info>((__int64)v17, (HLOCAL *)a4 + 3);
    ADSIFreeColumn(a1, &v16);
  }
  if ( (int)DSGetAndValidateColumn(a1, a2, ADSTYPE_INTEGER, L"machineArchitecture", &v16) >= 0 )
  {
    LODWORD(a5) = 0;
    v17[0] = v16;
    UnpackDWArrFrom<ads_search_column>(v17, v11, &a5);
    *((_DWORD *)a4 + 41) = (_DWORD)a5;
    ADSIFreeColumn(a1, &v16);
  }
  v12 = DSGetAndValidateColumn(a1, a2, ADSTYPE_CASE_IGNORE_STRING, L"msiFileList", &v16);
  if ( v12 >= 0 )
  {
    LODWORD(a5) = 0;
    v17[0] = v16;
    UnpackStrArrAllocFrom<ads_search_column>(v17, v10, &a5);
    *((_DWORD *)a4 + 44) = (_DWORD)a5;
    ADSIFreeColumn(a1, &v16);
    v12 = DSGetAndValidateColumn(a1, a2, ADSTYPE_INTEGER, L"versionNumberHi", &v16);
    if ( v12 >= 0 )
    {
      v13 = v16.dwNumValues ? v16.pADsValues->Boolean : 0;
      *((_DWORD *)a4 + 22) = v13;
      ADSIFreeColumn(a1, &v16);
      v12 = DSGetAndValidateColumn(a1, a2, ADSTYPE_INTEGER, L"versionNumberLo", &v16);
      if ( v12 >= 0 )
      {
        if ( v16.dwNumValues )
          Boolean = v16.pADsValues->Boolean;
        else
          Boolean = 0;
        *((_DWORD *)a4 + 23) = Boolean;
        ADSIFreeColumn(a1, &v16);
        GetSecurityDescriptor(a1, a2, a3, a4, v5);
      }
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180027a58  push    rbp
0x180027a5a  push    rbx
0x180027a5b  push    rsi
0x180027a5c  push    rdi
0x180027a5d  push    r12
0x180027a5f  push    r13
0x180027a61  push    r14
0x180027a63  push    r15
0x180027a65  lea     rbp, [rsp-17h]
0x180027a6a  sub     rsp, 98h
0x180027a71  mov     r15, [rbp+4Fh+arg_20]
0x180027a75  xor     eax, eax
0x180027a77  mov     [rbp+4Fh+var_A0.hReserved], rax
0x180027a7b  xorps   xmm0, xmm0
0x180027a7e  mov     rbx, r9
0x180027a81  mov     r13, r8
0x180027a84  mov     r14, rdx
0x180027a87  mov     rdi, rcx
0x180027a8a  movups  xmmword ptr [rbp+4Fh+var_A0.pszAttrName], xmm0
0x180027a8e  movups  xmmword ptr [rbp+4Fh+var_A0.pADsValues], xmm0
0x180027a92  test    r15, r15
0x180027a95  jz      short loc_180027A9E
0x180027a97  mov     dword ptr [r15], 1
0x180027a9e  lea     r12, [r9+0B8h]
0x180027aa5  mov     [r9+88h], rax
0x180027aac  lea     rsi, [r9+0A8h]
0x180027ab3  mov     [r9+90h], eax
0x180027aba  mov     [r9+0B0h], eax
0x180027ac1  mov     r8d, 3; enum __MIDL___MIDL_itf_ads_0000_0000_0001
0x180027ac7  mov     [r9+0A4h], eax
0x180027ace  lea     r9, aVendor; "vendor"
0x180027ad5  mov     [r12], rax
0x180027ad9  mov     [rsi], rax
0x180027adc  lea     rax, [rbp+4Fh+var_A0]
0x180027ae0  mov     [rsp+0D0h+var_B0], rax; struct ads_search_column *
0x180027ae5  call    ?DSGetAndValidateColumn@@YAJPEAX0W4__MIDL___MIDL_itf_ads_0000_0000_0001@@PEBGPEAUads_search_column@@@Z; DSGetAndValidateColumn(void *,void *,__MIDL___MIDL_itf_ads_0000_0000_0001,ushort const *,ads_search_column *)
0x180027aea  test    eax, eax
0x180027aec  js      short loc_180027B22
0x180027aee  movups  xmm0, xmmword ptr [rbp+4Fh+var_A0.pszAttrName]
0x180027af2  lea     rdx, [rbx+18h]
0x180027af6  movups  xmm1, xmmword ptr [rbp+4Fh+var_A0.pADsValues]
0x180027afa  lea     rcx, [rbp+4Fh+var_70]
0x180027afe  movaps  [rbp+4Fh+var_70], xmm0
0x180027b02  movsd   xmm0, [rbp+4Fh+var_A0.hReserved]
0x180027b07  movsd   [rbp+4Fh+var_50], xmm0
0x180027b0c  movaps  [rbp+4Fh+var_60], xmm1
0x180027b10  call    ??$UnpackStrAllocFrom@U_ads_attr_info@@@@YAJU_ads_attr_info@@PEAPEAG@Z; UnpackStrAllocFrom<_ads_attr_info>(_ads_attr_info,ushort * *)
0x180027b15  lea     rdx, [rbp+4Fh+var_A0]
0x180027b19  mov     rcx, rdi
0x180027b1c  call    cs:__imp_ADSIFreeColumn
0x180027b22  lea     rax, [rbp+4Fh+var_A0]
0x180027b26  mov     r8d, 7; enum __MIDL___MIDL_itf_ads_0000_0000_0001
0x180027b2c  lea     r9, aMachinearchite_0; "machineArchitecture"
0x180027b33  mov     [rsp+0D0h+var_B0], rax; struct ads_search_column *
0x180027b38  mov     rdx, r14; void *
0x180027b3b  mov     rcx, rdi; void *
0x180027b3e  call    ?DSGetAndValidateColumn@@YAJPEAX0W4__MIDL___MIDL_itf_ads_0000_0000_0001@@PEBGPEAUads_search_column@@@Z; DSGetAndValidateColumn(void *,void *,__MIDL___MIDL_itf_ads_0000_0000_0001,ushort const *,ads_search_column *)
0x180027b43  test    eax, eax
0x180027b45  js      short loc_180027B8E
0x180027b47  movups  xmm0, xmmword ptr [rbp+4Fh+var_A0.pszAttrName]
0x180027b4b  lea     r8, [rbp+4Fh+arg_20]
0x180027b4f  mov     rdx, rsi
0x180027b52  movups  xmm1, xmmword ptr [rbp+4Fh+var_A0.pADsValues]
0x180027b56  lea     rcx, [rbp+4Fh+var_70]
0x180027b5a  mov     dword ptr [rbp+4Fh+arg_20], 0
0x180027b61  movaps  [rbp+4Fh+var_70], xmm0
0x180027b65  movsd   xmm0, [rbp+4Fh+var_A0.hReserved]
0x180027b6a  movsd   [rbp+4Fh+var_50], xmm0
0x180027b6f  movaps  [rbp+4Fh+var_60], xmm1
0x180027b73  call    ??$UnpackDWArrFrom@Uads_search_column@@@@YAJUads_search_column@@PEAPEAKPEAK@Z; UnpackDWArrFrom<ads_search_column>(ads_search_column,ulong * *,ulong *)
0x180027b78  mov     eax, dword ptr [rbp+4Fh+arg_20]
0x180027b7b  lea     rdx, [rbp+4Fh+var_A0]
0x180027b7f  mov     rcx, rdi
0x180027b82  mov     [rbx+0A4h], eax
0x180027b88  call    cs:__imp_ADSIFreeColumn
0x180027b8e  lea     rax, [rbp+4Fh+var_A0]
0x180027b92  mov     r8d, 3; enum __MIDL___MIDL_itf_ads_0000_0000_0001
0x180027b98  lea     r9, aMsifilelist; "msiFileList"
0x180027b9f  mov     [rsp+0D0h+var_B0], rax; struct ads_search_column *
0x180027ba4  mov     rdx, r14; void *
0x180027ba7  mov     rcx, rdi; void *
0x180027baa  call    ?DSGetAndValidateColumn@@YAJPEAX0W4__MIDL___MIDL_itf_ads_0000_0000_0001@@PEBGPEAUads_search_column@@@Z; DSGetAndValidateColumn(void *,void *,__MIDL___MIDL_itf_ads_0000_0000_0001,ushort const *,ads_search_column *)
0x180027baf  mov     esi, eax
0x180027bb1  test    eax, eax
0x180027bb3  js      loc_180027CA6
0x180027bb9  movups  xmm0, xmmword ptr [rbp+4Fh+var_A0.pszAttrName]
0x180027bbd  lea     r8, [rbp+4Fh+arg_20]
0x180027bc1  mov     rdx, r12
0x180027bc4  movups  xmm1, xmmword ptr [rbp+4Fh+var_A0.pADsValues]
0x180027bc8  lea     rcx, [rbp+4Fh+var_70]
0x180027bcc  mov     dword ptr [rbp+4Fh+arg_20], 0
0x180027bd3  movaps  [rbp+4Fh+var_70], xmm0
0x180027bd7  movsd   xmm0, [rbp+4Fh+var_A0.hReserved]
0x180027bdc  movsd   [rbp+4Fh+var_50], xmm0
0x180027be1  movaps  [rbp+4Fh+var_60], xmm1
0x180027be5  call    ??$UnpackStrArrAllocFrom@Uads_search_column@@@@YAJUads_search_column@@PEAPEAPEAGPEAK@Z; UnpackStrArrAllocFrom<ads_search_column>(ads_search_column,ushort * * *,ulong *)
0x180027bea  mov     eax, dword ptr [rbp+4Fh+arg_20]
0x180027bed  lea     rdx, [rbp+4Fh+var_A0]
0x180027bf1  mov     rcx, rdi
0x180027bf4  mov     [rbx+0B0h], eax
0x180027bfa  call    cs:__imp_ADSIFreeColumn
0x180027c00  lea     rax, [rbp+4Fh+var_A0]
0x180027c04  mov     r12d, 7
0x180027c0a  mov     r8d, r12d; enum __MIDL___MIDL_itf_ads_0000_0000_0001
0x180027c0d  mov     [rsp+0D0h+var_B0], rax; struct ads_search_column *
0x180027c12  lea     r9, aVersionnumberh; "versionNumberHi"
0x180027c19  mov     rdx, r14; void *
0x180027c1c  mov     rcx, rdi; void *
0x180027c1f  call    ?DSGetAndValidateColumn@@YAJPEAX0W4__MIDL___MIDL_itf_ads_0000_0000_0001@@PEBGPEAUads_search_column@@@Z; DSGetAndValidateColumn(void *,void *,__MIDL___MIDL_itf_ads_0000_0000_0001,ushort const *,ads_search_column *)
0x180027c24  mov     esi, eax
0x180027c26  test    eax, eax
0x180027c28  js      short loc_180027CA6
0x180027c2a  cmp     [rbp+4Fh+var_A0.dwNumValues], 0
0x180027c2e  jz      short loc_180027C39
0x180027c30  mov     rax, [rbp+4Fh+var_A0.pADsValues]
0x180027c34  mov     ecx, [rax+8]
0x180027c37  jmp     short loc_180027C3B
0x180027c39  xor     ecx, ecx
0x180027c3b  mov     [rbx+58h], ecx
0x180027c3e  lea     rdx, [rbp+4Fh+var_A0]
0x180027c42  mov     rcx, rdi
0x180027c45  call    cs:__imp_ADSIFreeColumn
0x180027c4b  lea     rax, [rbp+4Fh+var_A0]
0x180027c4f  mov     r8d, r12d; enum __MIDL___MIDL_itf_ads_0000_0000_0001
0x180027c52  lea     r9, aVersionnumberl; "versionNumberLo"
0x180027c59  mov     [rsp+0D0h+var_B0], rax; struct ads_search_column *
0x180027c5e  mov     rdx, r14; void *
0x180027c61  mov     rcx, rdi; void *
0x180027c64  call    ?DSGetAndValidateColumn@@YAJPEAX0W4__MIDL___MIDL_itf_ads_0000_0000_0001@@PEBGPEAUads_search_column@@@Z; DSGetAndValidateColumn(void *,void *,__MIDL___MIDL_itf_ads_0000_0000_0001,ushort const *,ads_search_column *)
0x180027c69  mov     esi, eax
0x180027c6b  test    eax, eax
0x180027c6d  js      short loc_180027CA6
0x180027c6f  cmp     [rbp+4Fh+var_A0.dwNumValues], 0
0x180027c73  jz      short loc_180027C7E
0x180027c75  mov     rax, [rbp+4Fh+var_A0.pADsValues]
0x180027c79  mov     ecx, [rax+8]
0x180027c7c  jmp     short loc_180027C80
0x180027c7e  xor     ecx, ecx
0x180027c80  mov     [rbx+5Ch], ecx
0x180027c83  lea     rdx, [rbp+4Fh+var_A0]
0x180027c87  mov     rcx, rdi
0x180027c8a  call    cs:__imp_ADSIFreeColumn
0x180027c90  mov     r9, rbx; struct tagPACKAGEDISPINFO *
0x180027c93  mov     [rsp+0D0h+var_B0], r15; int *
0x180027c98  mov     r8, r13; void *
0x180027c9b  mov     rdx, r14; void *
0x180027c9e  mov     rcx, rdi; void *
0x180027ca1  call    ?GetSecurityDescriptor@@YAJPEAX00PEAUtagPACKAGEDISPINFO@@PEAH@Z; GetSecurityDescriptor(void *,void *,void *,tagPACKAGEDISPINFO *,int *)
0x180027ca6  mov     eax, esi
0x180027ca8  add     rsp, 98h
0x180027caf  pop     r15
0x180027cb1  pop     r14
0x180027cb3  pop     r13
0x180027cb5  pop     r12
0x180027cb7  pop     rdi
0x180027cb8  pop     rsi
0x180027cb9  pop     rbx
0x180027cba  pop     rbp
0x180027cbb  retn
```
