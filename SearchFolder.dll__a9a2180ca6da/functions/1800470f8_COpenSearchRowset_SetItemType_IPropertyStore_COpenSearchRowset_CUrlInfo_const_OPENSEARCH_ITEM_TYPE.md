# COpenSearchRowset::_SetItemType(IPropertyStore *,COpenSearchRowset::CUrlInfo const &,OPENSEARCH_ITEM_TYPE *)

- ea: `0x1800470f8`
- end: `0x1800474a0`
- name: `?_SetItemType@COpenSearchRowset@@AEAAJPEAUIPropertyStore@@AEBUCUrlInfo@1@PEAW4OPENSEARCH_ITEM_TYPE@@@Z`
- size: `936`
- prototype: `int(COpenSearchRowset *__hidden this, struct IPropertyStore *, const struct COpenSearchRowset::CUrlInfo *, enum OPENSEARCH_ITEM_TYPE *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180043b28`
- `0x180043dd4`

## callees

- `0x180005460`
- `0x1800064d4`
- `0x180006900`
- `0x180041520`
- `0x180041618`
- `0x1800433b0`
- `0x180044c54`
- `0x1800470f8`
- `0x18004783c`
- `0x180051010`

## import_xrefs

- `SHLWAPI!__imp_MIME_GetExtensionW` at `0x18004724f`
- `SHLWAPI!__imp_MIME_GetExtensionW` at `0x18004724f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180047347`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180047447`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180047347`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180047447`
- `PROPSYS!PSFormatForDisplayAlloc` at `0x180047416`
- `PROPSYS!PSFormatForDisplayAlloc` at `0x180047416`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x18004731b`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x18004731b`
- `PROPSYS!__imp_GetDefaultKindsForExtension` at `0x1800472f8`
- `PROPSYS!__imp_GetDefaultKindsForExtension` at `0x1800472f8`

## string_xrefs

- `0x180047359`: `opensearchresult`
- `0x180047395`: `opensearchresult`
- `0x1800473ad`: `opensearchresult`
- `0x180047191`: `opensearchfilefolderresult`

## pseudocode

```c
__int64 __fastcall COpenSearchRowset::_SetItemType(
        COpenSearchRowset *this,
        struct IPropertyStore *a2,
        const wchar_t **a3,
        enum OPENSEARCH_ITEM_TYPE *a4)
{
  COpenSearchRowset *v8; // rcx
  const wchar_t *v9; // rsi
  struct IPropertyStore *v10; // rcx
  HRESULT v11; // ebx
  const PROPERTYKEY *v12; // rbx
  unsigned __int16 *v13; // r14
  COpenSearchRowset *v14; // rcx
  COpenSearchRowset *v15; // rcx
  HRESULT v16; // eax
  struct IPropertyStoreVtbl *v17; // rax
  struct IPropertyStoreVtbl *lpVtbl; // rax
  PCWSTR psz; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 *v21; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v22; // [rsp+30h] [rbp-D0h]
  __int64 v23; // [rsp+38h] [rbp-C8h]
  PROPVARIANT ppropvar[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v26[264]; // [rsp+60h] [rbp-A0h] BYREF

  COpenSearchRowset::_CheckUrlSecurity(this, a3, a4);
  v9 = &::psz;
  if ( a3[1] )
    v9 = a3[1];
  if ( *(_DWORD *)a4 != 2 )
  {
    v11 = 0;
    if ( *(_DWORD *)a4 != 1 )
      goto LABEL_33;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v21);
    v22 = -1;
    v23 = -1;
    if ( (int)IPropertyStore_GetString(a2, &PKEY_FileExtension, &v21) >= 0 )
    {
      v13 = v21;
      if ( *v21 == 46 )
      {
LABEL_23:
        if ( v13 )
        {
          *(_DWORD *)a4 = 1;
          v11 = IPropertyStore_SetString(a2, &PKEY_ItemType, v13);
          if ( v11 >= 0 )
          {
            psz = 0;
            if ( (int)GetDefaultKindsForExtension(v13, &psz) >= 0 )
            {
              *(_OWORD *)ppropvar = 0;
              v25 = 0;
              if ( InitPropVariantFromStringAsVector(psz, ppropvar) >= 0 )
                v11 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a2->lpVtbl->SetValue)(
                        a2,
                        &PKEY_Kind,
                        ppropvar);
              PropVariantClear(ppropvar);
            }
            CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&psz);
          }
          goto LABEL_31;
        }
        goto LABEL_30;
      }
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v21);
    v22 = -1;
    v23 = -1;
    if ( (int)IPropertyStore_GetString(a2, &PKEY_MIMEType, &v21) >= 0 && (v14 = (COpenSearchRowset *)v21, *v21) )
    {
      if ( (unsigned int)MIME_GetExtensionW(v21, v26, 260) && !COpenSearchRowset::_IsExtensionExcluded(v15, v26) )
      {
        v13 = v26;
        goto LABEL_22;
      }
    }
    else if ( *((_DWORD *)this + 19) && v9 && *v9 && !COpenSearchRowset::_IsExtensionExcluded(v14, v9) )
    {
      v13 = (unsigned __int16 *)v9;
LABEL_22:
      v11 = IPropertyStore_SetString(a2, &PKEY_FileExtension, v13);
      if ( v11 < 0 )
      {
LABEL_31:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v21);
        goto LABEL_32;
      }
      goto LABEL_23;
    }
LABEL_30:
    v11 = IPropertyStore_SetString(a2, &PKEY_ItemType, L"opensearchresult");
    *(_DWORD *)a4 = 0;
    goto LABEL_31;
  }
  v10 = a2;
  if ( *v9 )
  {
    v11 = IPropertyStore_SetString(a2, &PKEY_ItemType, v9);
    if ( v11 < 0 )
    {
LABEL_44:
      v25 = 0;
      lpVtbl = a2->lpVtbl;
      *(_OWORD *)ppropvar = 0;
      ((void (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))lpVtbl->SetValue)(
        a2,
        &PKEY_ItemType,
        ppropvar);
      return (unsigned int)v11;
    }
    v10 = a2;
    v12 = &PKEY_FileExtension;
  }
  else
  {
    *(_DWORD *)a4 = 3;
    v12 = &PKEY_ItemType;
    v9 = L"opensearchfilefolderresult";
  }
  v11 = IPropertyStore_SetString(v10, v12, v9);
LABEL_32:
  if ( v11 < 0 )
    goto LABEL_44;
LABEL_33:
  if ( !*(_DWORD *)a4 )
  {
    if ( *((_QWORD *)this + 101) )
      v16 = COpenSearchRowset::_SetPropertyIfEmpty(v8, a2, &PKEY_ItemType, L"opensearchresult");
    else
      v16 = IPropertyStore_SetString(a2, &PKEY_ItemType, L"opensearchresult");
    v11 = v16;
  }
  if ( v11 < 0 )
    goto LABEL_44;
  v25 = 0;
  v17 = a2->lpVtbl;
  *(_OWORD *)ppropvar = 0;
  v11 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v17->GetValue)(
          a2,
          &PKEY_ItemType,
          ppropvar);
  if ( v11 >= 0 )
  {
    psz = 0;
    v11 = PSFormatForDisplayAlloc(&PKEY_ItemType, ppropvar, PDFF_DEFAULT, (PWSTR *)&psz);
    if ( v11 >= 0 )
      v11 = IPropertyStore_SetString(a2, &PKEY_ItemTypeText, psz);
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&psz);
  }
  PropVariantClear(ppropvar);
  if ( v11 < 0 )
    goto LABEL_44;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800470f8  push    rbp
0x1800470fa  push    rbx
0x1800470fb  push    rsi
0x1800470fc  push    rdi
0x1800470fd  push    r12
0x1800470ff  push    r13
0x180047101  push    r14
0x180047103  push    r15
0x180047105  lea     rbp, [rsp-188h]
0x18004710d  sub     rsp, 288h
0x180047114  mov     rax, cs:__security_cookie
0x18004711b  xor     rax, rsp
0x18004711e  mov     [rbp+1C0h+var_50], rax
0x180047125  mov     rbx, r8
0x180047128  mov     rdi, rdx
0x18004712b  mov     rdx, rbx; struct COpenSearchRowset::CUrlInfo *
0x18004712e  mov     r8, r9; enum OPENSEARCH_ITEM_TYPE *
0x180047131  mov     r15, r9
0x180047134  mov     r12, rcx
0x180047137  call    ?_CheckUrlSecurity@COpenSearchRowset@@AEAAJAEBUCUrlInfo@1@PEAW4OPENSEARCH_ITEM_TYPE@@@Z; COpenSearchRowset::_CheckUrlSecurity(COpenSearchRowset::CUrlInfo const &,OPENSEARCH_ITEM_TYPE *)
0x18004713c  xor     r13d, r13d
0x18004713f  lea     rsi, psz
0x180047146  cmp     [rbx+8], r13
0x18004714a  cmovnz  rsi, [rbx+8]
0x18004714f  cmp     dword ptr [r15], 2
0x180047153  jnz     short loc_1800471AA
0x180047155  mov     rcx, rdi
0x180047158  cmp     [rsi], r13w
0x18004715c  jz      short loc_180047183
0x18004715e  mov     r8, rsi
0x180047161  lea     rdx, PKEY_ItemType
0x180047168  call    IPropertyStore_SetString
0x18004716d  mov     ebx, eax
0x18004716f  test    eax, eax
0x180047171  js      loc_180047451
0x180047177  mov     rcx, rdi
0x18004717a  lea     rbx, PKEY_FileExtension
0x180047181  jmp     short loc_180047198
0x180047183  mov     dword ptr [r15], 3
0x18004718a  lea     rbx, PKEY_ItemType
0x180047191  lea     rsi, aOpensearchfile; "opensearchfilefolderresult"
0x180047198  mov     r8, rsi
0x18004719b  mov     rdx, rbx
0x18004719e  call    IPropertyStore_SetString
0x1800471a3  mov     ebx, eax
0x1800471a5  jmp     loc_18004737E
0x1800471aa  cmp     dword ptr [r15], 1
0x1800471ae  mov     ebx, r13d
0x1800471b1  jnz     loc_180047386
0x1800471b7  lea     rcx, [rsp+2C0h+var_298]
0x1800471bc  mov     [rsp+2C0h+var_298], r13
0x1800471c1  mov     [rsp+2C0h+var_290], r13
0x1800471c6  mov     [rsp+2C0h+var_288], r13
0x1800471cb  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800471d0  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800471d4  lea     rbx, PKEY_FileExtension
0x1800471db  mov     rdx, rbx
0x1800471de  mov     [rsp+2C0h+var_290], r14
0x1800471e3  lea     r8, [rsp+2C0h+var_298]
0x1800471e8  mov     [rsp+2C0h+var_288], r14
0x1800471ed  mov     rcx, rdi
0x1800471f0  call    IPropertyStore_GetString
0x1800471f5  test    eax, eax
0x1800471f7  js      short loc_18004720D
0x1800471f9  mov     r14, [rsp+2C0h+var_298]
0x1800471fe  cmp     word ptr [r14], 2Eh ; '.'
0x180047203  jz      loc_1800472BF
0x180047209  or      r14, 0FFFFFFFFFFFFFFFFh
0x18004720d  lea     rcx, [rsp+2C0h+var_298]
0x180047212  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180047217  lea     r8, [rsp+2C0h+var_298]
0x18004721c  mov     [rsp+2C0h+var_290], r14
0x180047221  lea     rdx, PKEY_MIMEType
0x180047228  mov     [rsp+2C0h+var_288], r14
0x18004722d  mov     rcx, rdi
0x180047230  call    IPropertyStore_GetString
0x180047235  test    eax, eax
0x180047237  js      short loc_180047276
0x180047239  mov     rcx, [rsp+2C0h+var_298]
0x18004723e  cmp     [rcx], r13w
0x180047242  jz      short loc_180047276
0x180047244  mov     r8d, 104h
0x18004724a  lea     rdx, [rsp+2C0h+var_260]
0x18004724f  call    cs:__imp_MIME_GetExtensionW
0x180047255  test    eax, eax
0x180047257  jz      loc_180047359
0x18004725d  lea     rdx, [rsp+2C0h+var_260]; unsigned __int16 *
0x180047262  call    ?_IsExtensionExcluded@COpenSearchRowset@@AEAAHPEBG@Z; COpenSearchRowset::_IsExtensionExcluded(ushort const *)
0x180047267  test    eax, eax
0x180047269  jnz     loc_180047359
0x18004726f  lea     r14, [rsp+2C0h+var_260]
0x180047274  jmp     short loc_1800472A7
0x180047276  cmp     [r12+4Ch], r13d
0x18004727b  jz      loc_180047359
0x180047281  test    rsi, rsi
0x180047284  jz      loc_180047359
0x18004728a  cmp     [rsi], r13w
0x18004728e  jz      loc_180047359
0x180047294  mov     rdx, rsi; unsigned __int16 *
0x180047297  call    ?_IsExtensionExcluded@COpenSearchRowset@@AEAAHPEBG@Z; COpenSearchRowset::_IsExtensionExcluded(ushort const *)
0x18004729c  test    eax, eax
0x18004729e  jnz     loc_180047359
0x1800472a4  mov     r14, rsi
0x1800472a7  mov     r8, r14
0x1800472aa  mov     rdx, rbx
0x1800472ad  mov     rcx, rdi
0x1800472b0  call    IPropertyStore_SetString
0x1800472b5  mov     ebx, eax
0x1800472b7  test    eax, eax
0x1800472b9  js      loc_180047374
0x1800472bf  test    r14, r14
0x1800472c2  jz      loc_180047359
0x1800472c8  mov     r8, r14
0x1800472cb  mov     dword ptr [r15], 1
0x1800472d2  lea     rdx, PKEY_ItemType
0x1800472d9  mov     rcx, rdi
0x1800472dc  call    IPropertyStore_SetString
0x1800472e1  mov     ebx, eax
0x1800472e3  test    eax, eax
0x1800472e5  js      loc_180047374
0x1800472eb  lea     rdx, [rsp+2C0h+psz]
0x1800472f0  mov     [rsp+2C0h+psz], r13
0x1800472f5  mov     rcx, r14
0x1800472f8  call    cs:__imp_GetDefaultKindsForExtension
0x1800472fe  test    eax, eax
0x180047300  js      short loc_18004734D
0x180047302  mov     rcx, [rsp+2C0h+psz]; psz
0x180047307  lea     rdx, [rsp+2C0h+ppropvar]; ppropvar
0x18004730c  xorps   xmm0, xmm0
0x18004730f  xor     eax, eax
0x180047311  movups  xmmword ptr [rsp+2C0h+ppropvar], xmm0
0x180047316  mov     [rsp+2C0h+var_270], rax
0x18004731b  call    cs:__imp_InitPropVariantFromStringAsVector
0x180047321  test    eax, eax
0x180047323  js      short loc_180047342
0x180047325  mov     rax, [rdi]
0x180047328  lea     r8, [rsp+2C0h+ppropvar]
0x18004732d  lea     rdx, PKEY_Kind
0x180047334  mov     rcx, rdi
0x180047337  mov     rax, [rax+30h]
0x18004733b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047340  mov     ebx, eax
0x180047342  lea     rcx, [rsp+2C0h+ppropvar]; pvar
0x180047347  call    cs:__imp_PropVariantClear
0x18004734d  lea     rcx, [rsp+2C0h+psz]; void *
0x180047352  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180047357  jmp     short loc_180047374
0x180047359  lea     r8, aOpensearchresu; "opensearchresult"
0x180047360  mov     rcx, rdi
0x180047363  lea     rdx, PKEY_ItemType
0x18004736a  call    IPropertyStore_SetString
0x18004736f  mov     ebx, eax
0x180047371  mov     [r15], r13d
0x180047374  lea     rcx, [rsp+2C0h+var_298]
0x180047379  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004737e  test    ebx, ebx
0x180047380  js      loc_180047451
0x180047386  cmp     [r15], r13d
0x180047389  jnz     short loc_1800473C5
0x18004738b  cmp     [r12+328h], r13
0x180047393  jz      short loc_1800473AD
0x180047395  lea     r9, aOpensearchresu; "opensearchresult"
0x18004739c  mov     rdx, rdi; struct IPropertyStore *
0x18004739f  lea     r8, PKEY_ItemType; struct _tagpropertykey *
0x1800473a6  call    ?_SetPropertyIfEmpty@COpenSearchRowset@@AEAAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEBG@Z; COpenSearchRowset::_SetPropertyIfEmpty(IPropertyStore *,_tagpropertykey const &,ushort const *)
0x1800473ab  jmp     short loc_1800473C3
0x1800473ad  lea     r8, aOpensearchresu; "opensearchresult"
0x1800473b4  mov     rcx, rdi
0x1800473b7  lea     rdx, PKEY_ItemType
0x1800473be  call    IPropertyStore_SetString
0x1800473c3  mov     ebx, eax
0x1800473c5  test    ebx, ebx
0x1800473c7  js      loc_180047451
0x1800473cd  xor     eax, eax
0x1800473cf  lea     r8, [rsp+2C0h+ppropvar]
0x1800473d4  mov     [rsp+2C0h+var_270], rax
0x1800473d9  lea     rdx, PKEY_ItemType
0x1800473e0  mov     rax, [rdi]
0x1800473e3  xorps   xmm0, xmm0
0x1800473e6  mov     rcx, rdi
0x1800473e9  movups  xmmword ptr [rsp+2C0h+ppropvar], xmm0
0x1800473ee  mov     rax, [rax+28h]
0x1800473f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800473f7  mov     ebx, eax
0x1800473f9  test    eax, eax
0x1800473fb  js      short loc_180047442
0x1800473fd  lea     r9, [rsp+2C0h+psz]; ppszDisplay
0x180047402  mov     [rsp+2C0h+psz], r13
0x180047407  xor     r8d, r8d; pdff
0x18004740a  lea     rdx, [rsp+2C0h+ppropvar]; propvar
0x18004740f  lea     rcx, PKEY_ItemType; key
0x180047416  call    cs:__imp_PSFormatForDisplayAlloc
0x18004741c  mov     ebx, eax
0x18004741e  test    eax, eax
0x180047420  js      short loc_180047438
0x180047422  mov     r8, [rsp+2C0h+psz]
0x180047427  lea     rdx, PKEY_ItemTypeText
0x18004742e  mov     rcx, rdi
0x180047431  call    IPropertyStore_SetString
0x180047436  mov     ebx, eax
0x180047438  lea     rcx, [rsp+2C0h+psz]; void *
0x18004743d  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180047442  lea     rcx, [rsp+2C0h+ppropvar]; pvar
0x180047447  call    cs:__imp_PropVariantClear
0x18004744d  test    ebx, ebx
0x18004744f  jns     short loc_18004747B
0x180047451  xor     eax, eax
0x180047453  lea     r8, [rsp+2C0h+ppropvar]
0x180047458  mov     [rsp+2C0h+var_270], rax
0x18004745d  lea     rdx, PKEY_ItemType
0x180047464  mov     rax, [rdi]
0x180047467  xorps   xmm0, xmm0
0x18004746a  mov     rcx, rdi
0x18004746d  movups  xmmword ptr [rsp+2C0h+ppropvar], xmm0
0x180047472  mov     rax, [rax+30h]
0x180047476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004747b  mov     eax, ebx
0x18004747d  mov     rcx, [rbp+1C0h+var_50]
0x180047484  xor     rcx, rsp; StackCookie
0x180047487  call    __security_check_cookie
0x18004748c  add     rsp, 288h
0x180047493  pop     r15
0x180047495  pop     r14
0x180047497  pop     r13
0x180047499  pop     r12
0x18004749b  pop     rdi
0x18004749c  pop     rsi
0x18004749d  pop     rbx
0x18004749e  pop     rbp
0x18004749f  retn
```
