# CClassContainer::BuildDNFromPackageGuid(_GUID,ushort * *)

- ea: `0x18001ed14`
- end: `0x18001eeb9`
- name: `?BuildDNFromPackageGuid@CClassContainer@@QEAAJU_GUID@@PEAPEAG@Z`
- size: `421`
- prototype: `__int64 __fastcall(CClassContainer *this, struct _GUID *, HLOCAL *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001f800`
- `0x1800226f0`
- `0x180022870`

## callees

- `0x1800016d0`
- `0x180008f58`
- `0x18001e754`
- `0x18001ed14`
- `0x1800234b0`

## import_xrefs

- `adsldpc!ADsEncodeBinaryData` at `0x18001ed84`
- `adsldpc!ADsEncodeBinaryData` at `0x18001ed84`
- `adsldpc!ADSIExecuteSearch` at `0x18001ede3`
- `adsldpc!ADSIExecuteSearch` at `0x18001ede3`
- `adsldpc!ADSICloseSearchHandle` at `0x18001ee8f`
- `adsldpc!ADSICloseSearchHandle` at `0x18001ee8f`
- `adsldpc!ADSIGetFirstRow` at `0x18001edfd`
- `adsldpc!ADSIGetFirstRow` at `0x18001edfd`
- `adsldpc!FreeADsMem` at `0x18001edbd`
- `adsldpc!FreeADsMem` at `0x18001edbd`
- `adsldpc!ADSIFreeColumn` at `0x18001ee71`
- `adsldpc!ADSIFreeColumn` at `0x18001ee71`

## string_xrefs

- `0x18001ed3f`: `ADsPath`

## pseudocode

```c
__int64 __fastcall CClassContainer::BuildDNFromPackageGuid(CClassContainer *this, struct _GUID *a2, HLOCAL *a3)
{
  __int128 v3; // xmm0
  __int64 result; // rax
  int Row; // eax
  int v8; // edi
  void *v9; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR ppszDestData; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v11; // [rsp+40h] [rbp-C0h] BYREF
  ads_search_column v12; // [rsp+48h] [rbp-B8h] BYREF
  ads_search_column v13; // [rsp+70h] [rbp-90h] BYREF
  BYTE pbSrcData[16]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v15[264]; // [rsp+B0h] [rbp-50h] BYREF

  v3 = (__int128)*a2;
  v9 = 0;
  v11 = L"ADsPath";
  *(_OWORD *)pbSrcData = v3;
  ppszDestData = 0;
  memset(&v12, 0, sizeof(v12));
  ADsEncodeBinaryData(pbSrcData, 0x10u, &ppszDestData);
  result = StringCchPrintfW(v15, 0x104u, L"(%s=%s)", L"objectGUID", ppszDestData);
  if ( (int)result >= 0 )
  {
    FreeADsMem(ppszDestData);
    result = ADSIExecuteSearch(*((_QWORD *)this + 70), v15, &v11, 1, &v9);
    if ( (int)result >= 0 )
    {
      Row = ADSIGetFirstRow(*((_QWORD *)this + 70), v9);
      if ( Row < 0 || Row == 20498 )
      {
        v8 = -2147221148;
      }
      else
      {
        v8 = DSGetAndValidateColumn(*((void **)this + 70), v9, ADSTYPE_CASE_IGNORE_STRING, v11, &v12);
        if ( v8 >= 0 )
        {
          v13 = v12;
          UnpackStrAllocFrom<_ads_attr_info>((__int64)&v13, a3);
          ADSIFreeColumn(*((_QWORD *)this + 70), &v12);
        }
      }
      if ( v9 )
        ADSICloseSearchHandle(*((_QWORD *)this + 70));
      return (unsigned int)v8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001ed14  mov     [rsp-8+arg_18], rbx
0x18001ed19  push    rbp
0x18001ed1a  push    rsi
0x18001ed1b  push    rdi
0x18001ed1c  lea     rbp, [rsp-1D0h]
0x18001ed24  sub     rsp, 2D0h
0x18001ed2b  mov     rax, cs:__security_cookie
0x18001ed32  xor     rax, rsp
0x18001ed35  mov     [rbp+1E0h+var_20], rax
0x18001ed3c  movups  xmm0, xmmword ptr [rdx]
0x18001ed3f  lea     rax, aAdspath; "ADsPath"
0x18001ed46  mov     [rsp+2E0h+var_2B0], 0
0x18001ed4f  mov     [rsp+2E0h+var_2A0], rax
0x18001ed54  mov     rsi, r8
0x18001ed57  xor     eax, eax
0x18001ed59  lea     r8, [rsp+2E0h+ppszDestData]; ppszDestData
0x18001ed5e  movdqu  xmmword ptr [rbp+1E0h+pbSrcData], xmm0
0x18001ed63  mov     [rsp+2E0h+var_298.hReserved], rax
0x18001ed68  mov     rbx, rcx
0x18001ed6b  xorps   xmm0, xmm0
0x18001ed6e  mov     [rsp+2E0h+ppszDestData], rax
0x18001ed73  lea     edx, [rax+10h]; dwSrcLen
0x18001ed76  lea     rcx, [rbp+1E0h+pbSrcData]; pbSrcData
0x18001ed7a  movups  xmmword ptr [rsp+2E0h+var_298.pszAttrName], xmm0
0x18001ed7f  movups  xmmword ptr [rsp+2E0h+var_298.pADsValues], xmm0
0x18001ed84  call    cs:__imp_ADsEncodeBinaryData
0x18001ed8a  mov     rax, [rsp+2E0h+ppszDestData]
0x18001ed8f  lea     r9, aObjectguid; "objectGUID"
0x18001ed96  lea     r8, aSS; "(%s=%s)"
0x18001ed9d  mov     [rsp+2E0h+var_2C0], rax
0x18001eda2  mov     edx, 104h; unsigned __int64
0x18001eda7  lea     rcx, [rbp+1E0h+var_230]; unsigned __int16 *
0x18001edab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001edb0  test    eax, eax
0x18001edb2  js      loc_18001EE97
0x18001edb8  mov     rcx, [rsp+2E0h+ppszDestData]; pMem
0x18001edbd  call    cs:__imp_FreeADsMem
0x18001edc3  mov     rcx, [rbx+230h]
0x18001edca  lea     rax, [rsp+2E0h+var_2B0]
0x18001edcf  mov     r9d, 1
0x18001edd5  mov     [rsp+2E0h+var_2C0], rax
0x18001edda  lea     r8, [rsp+2E0h+var_2A0]
0x18001eddf  lea     rdx, [rbp+1E0h+var_230]
0x18001ede3  call    cs:__imp_ADSIExecuteSearch
0x18001ede9  test    eax, eax
0x18001edeb  js      loc_18001EE97
0x18001edf1  mov     rdx, [rsp+2E0h+var_2B0]
0x18001edf6  mov     rcx, [rbx+230h]
0x18001edfd  call    cs:__imp_ADSIGetFirstRow
0x18001ee03  test    eax, eax
0x18001ee05  js      short loc_18001EE79
0x18001ee07  cmp     eax, 5012h
0x18001ee0c  jz      short loc_18001EE79
0x18001ee0e  mov     r9, [rsp+2E0h+var_2A0]; unsigned __int16 *
0x18001ee13  lea     rax, [rsp+2E0h+var_298]
0x18001ee18  mov     rdx, [rsp+2E0h+var_2B0]; void *
0x18001ee1d  mov     r8d, 3; enum __MIDL___MIDL_itf_ads_0000_0000_0001
0x18001ee23  mov     rcx, [rbx+230h]; void *
0x18001ee2a  mov     [rsp+2E0h+var_2C0], rax; struct ads_search_column *
0x18001ee2f  call    ?DSGetAndValidateColumn@@YAJPEAX0W4__MIDL___MIDL_itf_ads_0000_0000_0001@@PEBGPEAUads_search_column@@@Z; DSGetAndValidateColumn(void *,void *,__MIDL___MIDL_itf_ads_0000_0000_0001,ushort const *,ads_search_column *)
0x18001ee34  mov     edi, eax
0x18001ee36  test    eax, eax
0x18001ee38  js      short loc_18001EE7E
0x18001ee3a  movups  xmm0, xmmword ptr [rsp+2E0h+var_298.pszAttrName]
0x18001ee3f  mov     rdx, rsi
0x18001ee42  lea     rcx, [rsp+2E0h+var_270]
0x18001ee47  movups  xmm1, xmmword ptr [rsp+2E0h+var_298.pADsValues]
0x18001ee4c  movaps  [rsp+2E0h+var_270], xmm0
0x18001ee51  movsd   xmm0, [rsp+2E0h+var_298.hReserved]
0x18001ee57  movsd   [rbp+1E0h+var_250], xmm0
0x18001ee5c  movaps  [rbp+1E0h+var_260], xmm1
0x18001ee60  call    ??$UnpackStrAllocFrom@U_ads_attr_info@@@@YAJU_ads_attr_info@@PEAPEAG@Z; UnpackStrAllocFrom<_ads_attr_info>(_ads_attr_info,ushort * *)
0x18001ee65  mov     rcx, [rbx+230h]
0x18001ee6c  lea     rdx, [rsp+2E0h+var_298]
0x18001ee71  call    cs:__imp_ADSIFreeColumn
0x18001ee77  jmp     short loc_18001EE7E
0x18001ee79  mov     edi, 80040164h
0x18001ee7e  mov     rdx, [rsp+2E0h+var_2B0]
0x18001ee83  test    rdx, rdx
0x18001ee86  jz      short loc_18001EE95
0x18001ee88  mov     rcx, [rbx+230h]
0x18001ee8f  call    cs:__imp_ADSICloseSearchHandle
0x18001ee95  mov     eax, edi
0x18001ee97  mov     rcx, [rbp+1E0h+var_20]
0x18001ee9e  xor     rcx, rsp; StackCookie
0x18001eea1  call    __security_check_cookie
0x18001eea6  mov     rbx, [rsp+2E0h+arg_18]
0x18001eeae  add     rsp, 2D0h
0x18001eeb5  pop     rdi
0x18001eeb6  pop     rsi
0x18001eeb7  pop     rbp
0x18001eeb8  retn
```
