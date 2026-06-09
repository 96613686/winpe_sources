# CIVIAudioFilter::GetDefaultValue(_GUID const *,tagVARIANT *)

- ea: `0x18000e8d0`
- end: `0x18000eb54`
- name: `?GetDefaultValue@CIVIAudioFilter@@UEAAJPEBU_GUID@@PEAUtagVARIANT@@@Z`
- size: `644`
- prototype: `int(CIVIAudioFilter *__hidden this, const struct _GUID *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000e8d0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000e934`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e934`
- `OLEAUT32!__imp_VariantClear` at `0x18000eb22`
- `OLEAUT32!__imp_VariantClear` at `0x18000eb22`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000e923`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000e923`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e949`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e949`

## pseudocode

```c
__int64 __fastcall CIVIAudioFilter::GetDefaultValue(
        CIVIAudioFilter *this,
        const struct _GUID *a2,
        struct tagVARIANT *a3)
{
  BSTR v4; // rax
  LPOLESTR v5; // rcx
  __int64 result; // rax
  LPOLESTR lpsz; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_3c790028_c0ce_4256_b1a2_1b0fc8b1dcdc.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_3c790028_c0ce_4256_b1a2_1b0fc8b1dcdc.Data4 )
  {
    lpsz = 0;
    a3->vt = 8;
    StringFromCLSID(&GUID_696e1d31_548f_4036_825f_7026c60011bd, &lpsz);
    v4 = SysAllocString(lpsz);
    v5 = lpsz;
    a3->llVal = (LONGLONG)v4;
    CoTaskMemFree(v5);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_d6d6c6d1_064e_4fdd_a40e_3ecbfcb7ebd0.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_d6d6c6d1_064e_4fdd_a40e_3ecbfcb7ebd0.Data4 )
  {
    goto LABEL_8;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_a5106186_cc94_4bc9_8cd9_aa2f61f6807e.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_a5106186_cc94_4bc9_8cd9_aa2f61f6807e.Data4 )
  {
    goto LABEL_11;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_50196c21_1f33_4af5_b296_11426d6c8789.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_50196c21_1f33_4af5_b296_11426d6c8789.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_044e62e4_11a5_42d5_a3b2_3bb2c7c2d7cf.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_044e62e4_11a5_42d5_a3b2_3bb2c7c2d7cf.Data4 )
  {
    a3->vt = 19;
    result = 0;
    a3->lVal = 100;
    return result;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_287c8abe_69a4_4d39_8080_d3d9712178a0.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_287c8abe_69a4_4d39_8080_d3d9712178a0.Data4 )
  {
    goto LABEL_11;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_8afd1a15_1812_4cbf_9319_433a5b2a3b27.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_8afd1a15_1812_4cbf_9319_433a5b2a3b27.Data4 )
  {
    a3->vt = 19;
    result = 0;
    a3->lVal = 2;
    return result;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_5612bca1_56da_4582_8da1_ca8090f92768.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_5612bca1_56da_4582_8da1_ca8090f92768.Data4 )
  {
    goto LABEL_11;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_01274475_f6bb_4017_b084_81a763c942d4.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_01274475_f6bb_4017_b084_81a763c942d4.Data4 )
  {
LABEL_8:
    a3->vt = 19;
    result = 0;
    a3->lVal = 1;
    return result;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_4c437134_f9c2_4713_b2c2_6f3f456158e3.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_4c437134_f9c2_4713_b2c2_6f3f456158e3.Data4 )
  {
    a3->vt = 3;
    result = 0;
    a3->lVal = 0;
    return result;
  }
  if ( *(_QWORD *)&a2->Data1 == 0x4DC5CFC22B50583DLL && *(_QWORD *)a2->Data4 == 0x693FDCA3C027B2B7LL )
  {
LABEL_11:
    a3->vt = 19;
    result = 0;
    a3->lVal = 0;
    return result;
  }
  if ( (*(_QWORD *)&a2->Data1 != 0x416E4FBFFFFFFFFFLL || *(_QWORD *)a2->Data4 != 0x16661DE94415FF93LL)
    && (*(_QWORD *)&a2->Data1 != 0x316B3EBAFFFFFFFFLL || *(_QWORD *)a2->Data4 != 0xD5742DC85426EF23uLL) )
  {
    return 2147942487LL;
  }
  VariantClear(a3);
  return 1;
}

```

## disassembly

```asm
0x18000e8d0  mov     [rsp+arg_0], rbx
0x18000e8d5  push    rdi
0x18000e8d6  sub     rsp, 20h
0x18000e8da  mov     rbx, r8
0x18000e8dd  test    rdx, rdx
0x18000e8e0  jz      loc_18000EB41
0x18000e8e6  test    rbx, rbx
0x18000e8e9  jz      loc_18000EB41
0x18000e8ef  mov     rax, [rdx]
0x18000e8f2  xor     ecx, ecx
0x18000e8f4  cmp     rax, qword ptr cs:_GUID_3c790028_c0ce_4256_b1a2_1b0fc8b1dcdc.Data1
0x18000e8fb  mov     edi, ecx
0x18000e8fd  jnz     short loc_18000E963
0x18000e8ff  mov     rax, [rdx+8]
0x18000e903  cmp     rax, qword ptr cs:_GUID_3c790028_c0ce_4256_b1a2_1b0fc8b1dcdc.Data4
0x18000e90a  jnz     short loc_18000E963
0x18000e90c  mov     [rsp+28h+lpsz], rcx
0x18000e911  lea     rdx, [rsp+28h+lpsz]; lplpsz
0x18000e916  lea     rcx, _GUID_696e1d31_548f_4036_825f_7026c60011bd; rclsid
0x18000e91d  mov     word ptr [r8], 8
0x18000e923  call    cs:__imp_StringFromCLSID
0x18000e92a  nop     dword ptr [rax+rax+00h]
0x18000e92f  mov     rcx, [rsp+28h+lpsz]; psz
0x18000e934  call    cs:__imp_SysAllocString
0x18000e93b  nop     dword ptr [rax+rax+00h]
0x18000e940  mov     rcx, [rsp+28h+lpsz]; pv
0x18000e945  mov     [rbx+8], rax
0x18000e949  call    cs:__imp_CoTaskMemFree
0x18000e950  nop     dword ptr [rax+rax+00h]
0x18000e955  mov     eax, edi
0x18000e957  mov     rbx, [rsp+28h+arg_0]
0x18000e95c  add     rsp, 20h
0x18000e960  pop     rdi
0x18000e961  retn
0x18000e963  mov     rax, [rdx]
0x18000e966  cmp     rax, qword ptr cs:_GUID_d6d6c6d1_064e_4fdd_a40e_3ecbfcb7ebd0.Data1
0x18000e96d  jnz     short loc_18000E998
0x18000e96f  mov     rax, [rdx+8]
0x18000e973  cmp     rax, qword ptr cs:_GUID_d6d6c6d1_064e_4fdd_a40e_3ecbfcb7ebd0.Data4
0x18000e97a  jnz     short loc_18000E998
0x18000e97c  mov     word ptr [r8], 13h
0x18000e982  mov     eax, edi
0x18000e984  mov     dword ptr [r8+8], 1
0x18000e98c  mov     rbx, [rsp+28h+arg_0]
0x18000e991  add     rsp, 20h
0x18000e995  pop     rdi
0x18000e996  retn
0x18000e998  mov     rax, [rdx]
0x18000e99b  cmp     rax, qword ptr cs:_GUID_a5106186_cc94_4bc9_8cd9_aa2f61f6807e.Data1
0x18000e9a2  jnz     short loc_18000E9C9
0x18000e9a4  mov     rax, [rdx+8]
0x18000e9a8  cmp     rax, qword ptr cs:_GUID_a5106186_cc94_4bc9_8cd9_aa2f61f6807e.Data4
0x18000e9af  jnz     short loc_18000E9C9
0x18000e9b1  mov     word ptr [r8], 13h
0x18000e9b7  mov     eax, edi
0x18000e9b9  mov     [r8+8], ecx
0x18000e9bd  mov     rbx, [rsp+28h+arg_0]
0x18000e9c2  add     rsp, 20h
0x18000e9c6  pop     rdi
0x18000e9c7  retn
0x18000e9c9  mov     rax, [rdx]
0x18000e9cc  cmp     rax, qword ptr cs:_GUID_50196c21_1f33_4af5_b296_11426d6c8789.Data1
0x18000e9d3  jnz     short loc_18000E9FE
0x18000e9d5  mov     rax, [rdx+8]
0x18000e9d9  cmp     rax, qword ptr cs:_GUID_50196c21_1f33_4af5_b296_11426d6c8789.Data4
0x18000e9e0  jnz     short loc_18000E9FE
0x18000e9e2  mov     word ptr [r8], 13h
0x18000e9e8  mov     eax, edi
0x18000e9ea  mov     dword ptr [r8+8], 64h ; 'd'
0x18000e9f2  mov     rbx, [rsp+28h+arg_0]
0x18000e9f7  add     rsp, 20h
0x18000e9fb  pop     rdi
0x18000e9fc  retn
0x18000e9fe  mov     rax, [rdx]
0x18000ea01  cmp     rax, qword ptr cs:_GUID_044e62e4_11a5_42d5_a3b2_3bb2c7c2d7cf.Data1
0x18000ea08  jnz     short loc_18000EA17
0x18000ea0a  mov     rax, [rdx+8]
0x18000ea0e  cmp     rax, qword ptr cs:_GUID_044e62e4_11a5_42d5_a3b2_3bb2c7c2d7cf.Data4
0x18000ea15  jz      short loc_18000E9E2
0x18000ea17  mov     rax, [rdx]
0x18000ea1a  cmp     rax, qword ptr cs:_GUID_287c8abe_69a4_4d39_8080_d3d9712178a0.Data1
0x18000ea21  jnz     short loc_18000EA30
0x18000ea23  mov     rax, [rdx+8]
0x18000ea27  cmp     rax, qword ptr cs:_GUID_287c8abe_69a4_4d39_8080_d3d9712178a0.Data4
0x18000ea2e  jz      short loc_18000E9B1
0x18000ea30  mov     rax, [rdx]
0x18000ea33  cmp     rax, qword ptr cs:_GUID_8afd1a15_1812_4cbf_9319_433a5b2a3b27.Data1
0x18000ea3a  jnz     short loc_18000EA65
0x18000ea3c  mov     rax, [rdx+8]
0x18000ea40  cmp     rax, qword ptr cs:_GUID_8afd1a15_1812_4cbf_9319_433a5b2a3b27.Data4
0x18000ea47  jnz     short loc_18000EA65
0x18000ea49  mov     word ptr [r8], 13h
0x18000ea4f  mov     eax, edi
0x18000ea51  mov     dword ptr [r8+8], 2
0x18000ea59  mov     rbx, [rsp+28h+arg_0]
0x18000ea5e  add     rsp, 20h
0x18000ea62  pop     rdi
0x18000ea63  retn
0x18000ea65  mov     rax, [rdx]
0x18000ea68  cmp     rax, qword ptr cs:_GUID_5612bca1_56da_4582_8da1_ca8090f92768.Data1
0x18000ea6f  jnz     short loc_18000EA82
0x18000ea71  mov     rax, [rdx+8]
0x18000ea75  cmp     rax, qword ptr cs:_GUID_5612bca1_56da_4582_8da1_ca8090f92768.Data4
0x18000ea7c  jz      loc_18000E9B1
0x18000ea82  mov     rax, [rdx]
0x18000ea85  cmp     rax, qword ptr cs:_GUID_01274475_f6bb_4017_b084_81a763c942d4.Data1
0x18000ea8c  jnz     short loc_18000EA9F
0x18000ea8e  mov     rax, [rdx+8]
0x18000ea92  cmp     rax, qword ptr cs:_GUID_01274475_f6bb_4017_b084_81a763c942d4.Data4
0x18000ea99  jz      loc_18000E97C
0x18000ea9f  mov     rax, [rdx]
0x18000eaa2  cmp     rax, qword ptr cs:_GUID_4c437134_f9c2_4713_b2c2_6f3f456158e3.Data1
0x18000eaa9  jnz     short loc_18000EAD0
0x18000eaab  mov     rax, [rdx+8]
0x18000eaaf  cmp     rax, qword ptr cs:_GUID_4c437134_f9c2_4713_b2c2_6f3f456158e3.Data4
0x18000eab6  jnz     short loc_18000EAD0
0x18000eab8  mov     word ptr [r8], 3
0x18000eabe  mov     eax, edi
0x18000eac0  mov     [r8+8], ecx
0x18000eac4  mov     rbx, [rsp+28h+arg_0]
0x18000eac9  add     rsp, 20h
0x18000eacd  pop     rdi
0x18000eace  retn
0x18000ead0  mov     rax, [rdx]
0x18000ead3  cmp     rax, qword ptr cs:stru_18008DAC8.Data1
0x18000eada  jnz     short loc_18000EAED
0x18000eadc  mov     rax, [rdx+8]
0x18000eae0  cmp     rax, qword ptr cs:stru_18008DAC8.Data4
0x18000eae7  jz      loc_18000E9B1
0x18000eaed  mov     rax, [rdx]
0x18000eaf0  cmp     rax, cs:qword_18008DC90
0x18000eaf7  jnz     short loc_18000EB06
0x18000eaf9  mov     rax, [rdx+8]
0x18000eafd  cmp     rax, cs:qword_18008DC98
0x18000eb04  jz      short loc_18000EB1F
0x18000eb06  mov     rax, [rdx]
0x18000eb09  cmp     rax, cs:qword_18008DBE0
0x18000eb10  jnz     short loc_18000EB41
0x18000eb12  mov     rax, [rdx+8]
0x18000eb16  cmp     rax, cs:qword_18008DBE8
0x18000eb1d  jnz     short loc_18000EB41
0x18000eb1f  mov     rcx, rbx; pvarg
0x18000eb22  call    cs:__imp_VariantClear
0x18000eb29  nop     dword ptr [rax+rax+00h]
0x18000eb2e  mov     edi, 1
0x18000eb33  mov     eax, edi
0x18000eb35  mov     rbx, [rsp+28h+arg_0]
0x18000eb3a  add     rsp, 20h
0x18000eb3e  pop     rdi
0x18000eb3f  retn
0x18000eb41  mov     rbx, [rsp+28h+arg_0]
0x18000eb46  mov     edi, 80070057h
0x18000eb4b  mov     eax, edi
0x18000eb4d  add     rsp, 20h
0x18000eb51  pop     rdi
0x18000eb52  retn
```
