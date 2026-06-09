# COpenSearchRowset::_ParseProperty(IPropertyStore *,_tagpropertykey const &,ushort const *,int)

- ea: `0x180045fa0`
- end: `0x1800463da`
- name: `?_ParseProperty@COpenSearchRowset@@AEAAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEBGH@Z`
- size: `1082`
- prototype: `int(COpenSearchRowset *__hidden this, struct IPropertyStore *, const struct _tagpropertykey *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180045e30`

## callees

- `0x1800054b0`
- `0x180005c88`
- `0x1800064d4`
- `0x180006900`
- `0x1800129c0`
- `0x1800129f8`
- `0x18001f128`
- `0x180024d10`
- `0x18003d428`
- `0x180041520`
- `0x180044cec`
- `0x180045fa0`
- `0x1800479a0`
- `0x18004dcc8`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-unicodeansi-l1-1-0!SHUnicodeToAnsi` at `0x180046279`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHUnicodeToAnsi` at `0x180046279`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180046201`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180046399`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180046201`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180046399`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800461b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800461b8`
- `PROPSYS!PSGetPropertyDescription` at `0x180046028`
- `PROPSYS!PSGetPropertyDescription` at `0x180046028`
- `PROPSYS!InitPropVariantFromFileTime` at `0x1800462a2`
- `PROPSYS!InitPropVariantFromFileTime` at `0x1800462a2`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x1800461d7`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x1800461d7`

## pseudocode

```c
__int64 __fastcall COpenSearchRowset::_ParseProperty(
        COpenSearchRowset *this,
        struct IPropertyStore *a2,
        const struct _tagpropertykey *a3,
        const unsigned __int16 *a4,
        int a5)
{
  __int64 v8; // rax
  __int64 (__fastcall **v9)(struct IPropertyStore *, GUID *, __int64); // rdx
  int v10; // ebx
  void **v11; // rax
  unsigned __int64 v12; // r14
  COpenSearchRowset *v13; // rcx
  unsigned __int64 v14; // rsi
  unsigned __int64 v15; // r8
  int inited; // eax
  COpenSearchRowset *v17; // rcx
  unsigned __int64 v18; // rsi
  _WORD v20[2]; // [rsp+30h] [rbp-61h] BYREF
  int v21; // [rsp+34h] [rbp-5Dh] BYREF
  LPVOID pv; // [rsp+38h] [rbp-59h] BYREF
  __int64 v23; // [rsp+40h] [rbp-51h] BYREF
  __int64 v24; // [rsp+48h] [rbp-49h] BYREF
  PROPVARIANT ppropvar[2]; // [rsp+50h] [rbp-41h] BYREF
  __int64 v26; // [rsp+60h] [rbp-31h]
  FILETIME pftIn; // [rsp+68h] [rbp-29h] BYREF
  PCWSTR psz; // [rsp+70h] [rbp-21h] BYREF
  unsigned __int64 v29; // [rsp+78h] [rbp-19h]
  __int64 v30; // [rsp+80h] [rbp-11h]

  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v24);
  v8 = ATL::CComPtrBase<IXMLDOMDocument>::operator&((__int64)&v24);
  v10 = (*v9)(a2, &GUID_388cec0d_4ef6_4015_a135_d96527fd84e2, v8);
  if ( v10 >= 0 )
  {
    ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v23);
    v11 = (void **)ATL::CComPtrBase<IXMLDOMDocument>::operator&((__int64)&v23);
    v10 = PSGetPropertyDescription(a3, &GUID_6f79d558_3e96_4549_a1d1_7d75d2288814, v11);
    if ( v10 < 0 )
      goto LABEL_64;
    v12 = 1;
    v21 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v23 + 64LL))(v23, 1, &v21);
    if ( v10 < 0 )
      goto LABEL_64;
    if ( !(unsigned int)operator==(a3, &PKEY_ImageParsingName) && (v21 & 1) != 0 )
    {
      psz = 0;
      v29 = 0;
      v30 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&psz);
      v14 = -1;
      if ( v29 >= 0x824 )
      {
        v10 = 0;
        if ( v29 > 0x824 )
        {
          v29 = 2084;
          *((_WORD *)psz + 2084) = 0;
          goto LABEL_13;
        }
      }
      else
      {
        v15 = -1;
        do
          ++v15;
        while ( a4[v15] );
        if ( 2084 - v29 < v15 )
          v15 = 2084 - v29;
        v10 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                &psz,
                a4,
                v15);
      }
      if ( v10 < 0 )
      {
LABEL_35:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&psz);
LABEL_64:
        ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v23);
        goto LABEL_65;
      }
LABEL_13:
      pv = 0;
      if ( (int)IPropertyStore_GetString(a2, a3, &pv) < 0 )
        goto LABEL_31;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&psz);
      if ( v29 >= 0x824 )
      {
        if ( v29 > 0x824 )
        {
          v29 = 2084;
          *((_WORD *)psz + 2084) = 0;
        }
      }
      else
      {
        if ( 2084 == v29 )
          v12 = 0;
        v10 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                &psz,
                L";",
                v12);
        if ( v10 < 0 )
          goto LABEL_30;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&psz);
      if ( v29 >= 0x824 )
      {
        v10 = 0;
        if ( v29 > 0x824 )
        {
          v29 = 2084;
          *((_WORD *)psz + 2084) = 0;
        }
      }
      else
      {
        do
          ++v14;
        while ( *((_WORD *)pv + v14) );
        if ( 2084 - v29 < v14 )
          v14 = 2084 - v29;
        v10 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                &psz,
                (const unsigned __int16 *)pv,
                v14);
      }
LABEL_30:
      CoTaskMemFree(pv);
LABEL_31:
      if ( v10 >= 0 )
      {
        *(_OWORD *)ppropvar = 0;
        v26 = 0;
        if ( InitPropVariantFromStringAsVector(psz, ppropvar) >= 0 )
          v10 = (*(__int64 (__fastcall **)(__int64, const struct _tagpropertykey *, PROPVARIANT *, _QWORD))(*(_QWORD *)v24 + 64LL))(
                  v24,
                  a3,
                  ppropvar,
                  0);
        PropVariantClear(ppropvar);
      }
      goto LABEL_35;
    }
    if ( a5 && COpenSearchRowset::_IsPropertyPresent(v13, a2, a3) )
      goto LABEL_64;
    v20[0] = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v23 + 40LL))(v23, v20);
    if ( v10 < 0 )
      goto LABEL_64;
    *(_OWORD *)ppropvar = 0;
    v26 = 0;
    if ( v20[0] == 64 )
    {
      pftIn = 0;
      LODWORD(pv) = -1;
      inited = SHUnicodeToAnsi(a4, (PSTR)&psz, 41);
      if ( inited >= 0 )
      {
        inited = iso8601ToFileTime(&psz, &pftIn, &pv);
        if ( inited >= 0 )
          inited = InitPropVariantFromFileTime(&pftIn, ppropvar);
      }
      v10 = 0;
      if ( inited >= 0 )
        v10 = inited;
LABEL_61:
      if ( v10 >= 0 )
        goto LABEL_62;
      goto LABEL_63;
    }
    if ( (unsigned int)operator==(a3, &PKEY_Search_AutoSummary) )
    {
      v10 = COpenSearchRowset::_TrimSpaces(v17, a4, (unsigned __int16 **)&ppropvar[1]);
      if ( v10 >= 0 )
      {
        LOWORD(ppropvar[0]) = 31;
LABEL_62:
        v10 = (*(__int64 (__fastcall **)(__int64, const struct _tagpropertykey *, PROPVARIANT *, _QWORD))(*(_QWORD *)v24 + 64LL))(
                v24,
                a3,
                ppropvar,
                0);
      }
LABEL_63:
      PropVariantClear(ppropvar);
      goto LABEL_64;
    }
    psz = 0;
    v29 = 0;
    v30 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&psz);
    if ( v29 >= 0x824 )
    {
      if ( v29 > 0x824 )
      {
        v29 = 2084;
        *((_WORD *)psz + 2084) = 0;
      }
    }
    else
    {
      v18 = -1;
      do
        ++v18;
      while ( a4[v18] );
      if ( 2084 - v29 < v18 )
        v18 = 2084 - v29;
      v10 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(&psz, a4, v18);
      if ( v10 < 0 )
        goto LABEL_60;
    }
    v10 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::DetachInitializeIfEmpty(
            &psz,
            &ppropvar[1]);
    if ( v10 >= 0 )
      LOWORD(ppropvar[0]) = 31;
LABEL_60:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&psz);
    goto LABEL_61;
  }
LABEL_65:
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v24);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180045fa0  mov     [rsp-8+arg_0], rbx
0x180045fa5  push    rbp
0x180045fa6  push    rsi
0x180045fa7  push    rdi
0x180045fa8  push    r12
0x180045faa  push    r13
0x180045fac  push    r14
0x180045fae  push    r15
0x180045fb0  lea     rbp, [rsp-1Fh]
0x180045fb5  sub     rsp, 0B0h
0x180045fbc  mov     rax, cs:__security_cookie
0x180045fc3  xor     rax, rsp
0x180045fc6  mov     [rbp+4Fh+var_40], rax
0x180045fca  lea     rcx, [rbp+4Fh+var_98]; void *
0x180045fce  mov     r15, r9
0x180045fd1  mov     r12, r8
0x180045fd4  mov     r13, rdx
0x180045fd7  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180045fdc  mov     rdx, [rdx]
0x180045fdf  lea     rcx, [rbp+4Fh+var_98]
0x180045fe3  call    ??I?$CComPtrBase@UIXMLDOMDocument@@@ATL@@QEAAPEAPEAUIXMLDOMDocument@@XZ; ATL::CComPtrBase<IXMLDOMDocument>::operator&(void)
0x180045fe8  mov     r8, rax
0x180045feb  mov     rcx, r13
0x180045fee  mov     rax, [rdx]
0x180045ff1  lea     rdx, _GUID_388cec0d_4ef6_4015_a135_d96527fd84e2
0x180045ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045ffd  xor     esi, esi
0x180045fff  mov     ebx, eax
0x180046001  test    eax, eax
0x180046003  js      loc_1800463A8
0x180046009  lea     rcx, [rbp+4Fh+var_A0]; void *
0x18004600d  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180046012  lea     rcx, [rbp+4Fh+var_A0]
0x180046016  call    ??I?$CComPtrBase@UIXMLDOMDocument@@@ATL@@QEAAPEAPEAUIXMLDOMDocument@@XZ; ATL::CComPtrBase<IXMLDOMDocument>::operator&(void)
0x18004601b  mov     r8, rax; ppv
0x18004601e  lea     rdx, _GUID_6f79d558_3e96_4549_a1d1_7d75d2288814; riid
0x180046025  mov     rcx, r12; propkey
0x180046028  call    cs:__imp_PSGetPropertyDescription
0x18004602e  mov     ebx, eax
0x180046030  test    eax, eax
0x180046032  js      loc_18004639F
0x180046038  mov     rcx, [rbp+4Fh+var_A0]
0x18004603c  lea     r14d, [rsi+1]
0x180046040  mov     [rbp+4Fh+var_AC], esi
0x180046043  lea     r8, [rbp+4Fh+var_AC]
0x180046047  mov     edx, r14d
0x18004604a  mov     rax, [rcx]
0x18004604d  mov     rax, [rax+40h]
0x180046051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046056  mov     ebx, eax
0x180046058  test    eax, eax
0x18004605a  js      loc_18004639F
0x180046060  lea     rdx, PKEY_ImageParsingName
0x180046067  mov     rcx, r12
0x18004606a  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18004606f  test    eax, eax
0x180046071  jnz     loc_180046215
0x180046077  test    byte ptr [rbp+4Fh+var_AC], r14b
0x18004607b  jz      loc_180046215
0x180046081  lea     rcx, [rbp+4Fh+psz]
0x180046085  mov     [rbp+4Fh+psz], rsi
0x180046089  mov     [rbp+4Fh+var_68], rsi
0x18004608d  mov     [rbp+4Fh+var_60], rsi
0x180046091  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x180046096  mov     rcx, [rbp+4Fh+var_68]
0x18004609a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004609e  mov     edi, 824h
0x1800460a3  cmp     rcx, rdi
0x1800460a6  jnb     loc_180046136
0x1800460ac  mov     r8, rsi
0x1800460af  xor     eax, eax
0x1800460b1  inc     r8
0x1800460b4  cmp     [r15+r8*2], ax
0x1800460b9  jnz     short loc_1800460B1
0x1800460bb  mov     rax, rdi
0x1800460be  mov     rdx, r15
0x1800460c1  sub     rax, rcx
0x1800460c4  lea     rcx, [rbp+4Fh+psz]
0x1800460c8  cmp     rax, r8
0x1800460cb  cmovb   r8, rax
0x1800460cf  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x1800460d4  mov     ebx, eax
0x1800460d6  xor     r15d, r15d
0x1800460d9  test    ebx, ebx
0x1800460db  js      loc_180046207
0x1800460e1  lea     r8, [rbp+4Fh+pv]
0x1800460e5  mov     [rbp+4Fh+pv], r15
0x1800460e9  mov     rdx, r12
0x1800460ec  mov     rcx, r13
0x1800460ef  call    IPropertyStore_GetString
0x1800460f4  test    eax, eax
0x1800460f6  js      loc_1800461BE
0x1800460fc  lea     rcx, [rbp+4Fh+psz]
0x180046100  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x180046105  mov     rcx, [rbp+4Fh+var_68]
0x180046109  cmp     rcx, rdi
0x18004610c  jnb     short loc_180046153
0x18004610e  mov     rax, rdi
0x180046111  lea     rdx, asc_18005CB90; ";"
0x180046118  sub     rax, rcx
0x18004611b  lea     rcx, [rbp+4Fh+psz]
0x18004611f  cmp     rax, r14
0x180046122  cmovb   r14, rax
0x180046126  mov     r8, r14
0x180046129  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18004612e  mov     ebx, eax
0x180046130  test    eax, eax
0x180046132  jns     short loc_180046165
0x180046134  jmp     short loc_1800461B4
0x180046136  xor     r15d, r15d
0x180046139  mov     ebx, r15d
0x18004613c  cmp     rcx, rdi
0x18004613f  jbe     short loc_1800460D9
0x180046141  mov     rax, [rbp+4Fh+psz]
0x180046145  mov     [rbp+4Fh+var_68], rdi
0x180046149  mov     [rax+1048h], r15w
0x180046151  jmp     short loc_1800460E1
0x180046153  jbe     short loc_180046165
0x180046155  mov     rax, [rbp+4Fh+psz]
0x180046159  mov     [rbp+4Fh+var_68], rdi
0x18004615d  mov     [rax+1048h], r15w
0x180046165  lea     rcx, [rbp+4Fh+psz]
0x180046169  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18004616e  mov     rcx, [rbp+4Fh+var_68]
0x180046172  cmp     rcx, rdi
0x180046175  jnb     short loc_18004619F
0x180046177  mov     rdx, [rbp+4Fh+pv]
0x18004617b  inc     rsi
0x18004617e  cmp     [rdx+rsi*2], r15w
0x180046183  jnz     short loc_18004617B
0x180046185  sub     rdi, rcx
0x180046188  lea     rcx, [rbp+4Fh+psz]
0x18004618c  cmp     rdi, rsi
0x18004618f  cmovb   rsi, rdi
0x180046193  mov     r8, rsi
0x180046196  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18004619b  mov     ebx, eax
0x18004619d  jmp     short loc_1800461B4
0x18004619f  mov     ebx, r15d
0x1800461a2  jbe     short loc_1800461B4
0x1800461a4  mov     rax, [rbp+4Fh+psz]
0x1800461a8  mov     [rbp+4Fh+var_68], rdi
0x1800461ac  mov     [rax+1048h], r15w
0x1800461b4  mov     rcx, [rbp+4Fh+pv]; pv
0x1800461b8  call    cs:__imp_CoTaskMemFree
0x1800461be  test    ebx, ebx
0x1800461c0  js      short loc_180046207
0x1800461c2  mov     rcx, [rbp+4Fh+psz]; psz
0x1800461c6  lea     rdx, [rbp+4Fh+ppropvar]; ppropvar
0x1800461ca  xorps   xmm0, xmm0
0x1800461cd  xor     eax, eax
0x1800461cf  movups  xmmword ptr [rbp+4Fh+ppropvar], xmm0
0x1800461d3  mov     [rbp+4Fh+var_80], rax
0x1800461d7  call    cs:__imp_InitPropVariantFromStringAsVector
0x1800461dd  test    eax, eax
0x1800461df  js      short loc_1800461FD
0x1800461e1  mov     rcx, [rbp+4Fh+var_98]
0x1800461e5  lea     r8, [rbp+4Fh+ppropvar]
0x1800461e9  xor     r9d, r9d
0x1800461ec  mov     rdx, r12
0x1800461ef  mov     rax, [rcx]
0x1800461f2  mov     rax, [rax+40h]
0x1800461f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800461fb  mov     ebx, eax
0x1800461fd  lea     rcx, [rbp+4Fh+ppropvar]; pvar
0x180046201  call    cs:__imp_PropVariantClear
0x180046207  lea     rcx, [rbp+4Fh+psz]
0x18004620b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180046210  jmp     loc_18004639F
0x180046215  cmp     [rbp+4Fh+arg_20], esi
0x180046218  jz      short loc_18004622D
0x18004621a  mov     r8, r12; struct _tagpropertykey *
0x18004621d  mov     rdx, r13; struct IPropertyStore *
0x180046220  call    ?_IsPropertyPresent@COpenSearchRowset@@AEAAHPEAUIPropertyStore@@AEBU_tagpropertykey@@@Z; COpenSearchRowset::_IsPropertyPresent(IPropertyStore *,_tagpropertykey const &)
0x180046225  test    eax, eax
0x180046227  jnz     loc_18004639F
0x18004622d  mov     rcx, [rbp+4Fh+var_A0]
0x180046231  lea     rdx, [rbp+4Fh+var_B0]
0x180046235  mov     [rbp+4Fh+var_B0], si
0x180046239  mov     rax, [rcx]
0x18004623c  mov     rax, [rax+28h]
0x180046240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046245  mov     ebx, eax
0x180046247  test    eax, eax
0x180046249  js      loc_18004639F
0x18004624f  xor     eax, eax
0x180046251  xorps   xmm0, xmm0
0x180046254  cmp     [rbp+4Fh+var_B0], 40h ; '@'
0x180046259  movups  xmmword ptr [rbp+4Fh+ppropvar], xmm0
0x18004625d  mov     [rbp+4Fh+var_80], rax
0x180046261  jnz     short loc_1800462B4
0x180046263  mov     qword ptr [rbp+4Fh+pftIn.dwLowDateTime], rsi
0x180046267  lea     r8d, [rax+29h]; cchBuf
0x18004626b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004626f  lea     rdx, [rbp+4Fh+psz]; pszDst
0x180046273  mov     rcx, r15; pwszSrc
0x180046276  mov     dword ptr [rbp+4Fh+pv], esi
0x180046279  call    cs:__imp_SHUnicodeToAnsi
0x18004627f  xor     esi, esi
0x180046281  test    eax, eax
0x180046283  js      short loc_1800462A8
0x180046285  lea     r8, [rbp+4Fh+pv]
0x180046289  lea     rdx, [rbp+4Fh+pftIn]
0x18004628d  lea     rcx, [rbp+4Fh+psz]
0x180046291  call    _iso8601ToFileTime
0x180046296  test    eax, eax
0x180046298  js      short loc_1800462A8
0x18004629a  lea     rdx, [rbp+4Fh+ppropvar]; ppropvar
0x18004629e  lea     rcx, [rbp+4Fh+pftIn]; pftIn
0x1800462a2  call    cs:__imp_InitPropVariantFromFileTime
0x1800462a8  test    eax, eax
0x1800462aa  mov     ebx, esi
0x1800462ac  cmovns  ebx, eax
0x1800462af  jmp     loc_180046375
0x1800462b4  lea     rdx, PKEY_Search_AutoSummary
0x1800462bb  mov     rcx, r12
0x1800462be  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x1800462c3  test    eax, eax
0x1800462c5  jz      short loc_1800462EB
0x1800462c7  lea     r8, [rbp+4Fh+ppropvar+8]; unsigned __int16 **
0x1800462cb  mov     rdx, r15; unsigned __int16 *
0x1800462ce  call    ?_TrimSpaces@COpenSearchRowset@@AEAAJPEBGPEAPEAG@Z; COpenSearchRowset::_TrimSpaces(ushort const *,ushort * *)
0x1800462d3  mov     ebx, eax
0x1800462d5  test    eax, eax
0x1800462d7  js      loc_180046395
0x1800462dd  mov     eax, 1Fh
0x1800462e2  mov     word ptr [rbp+4Fh+ppropvar], ax
0x1800462e6  jmp     loc_180046379
0x1800462eb  lea     rcx, [rbp+4Fh+psz]
0x1800462ef  mov     [rbp+4Fh+psz], rsi
0x1800462f3  mov     [rbp+4Fh+var_68], rsi
0x1800462f7  mov     [rbp+4Fh+var_60], rsi
0x1800462fb  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x180046300  mov     rcx, [rbp+4Fh+var_68]
0x180046304  mov     edi, 824h
0x180046309  cmp     rcx, rdi
0x18004630c  jnb     short loc_18004633F
0x18004630e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180046312  xor     eax, eax
0x180046314  inc     rsi
0x180046317  cmp     [r15+rsi*2], ax
0x18004631c  jnz     short loc_180046314
0x18004631e  sub     rdi, rcx
0x180046321  mov     rdx, r15
0x180046324  cmp     rdi, rsi
0x180046327  lea     rcx, [rbp+4Fh+psz]
0x18004632b  cmovb   rsi, rdi
0x18004632f  mov     r8, rsi
0x180046332  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x180046337  mov     ebx, eax
0x180046339  test    eax, eax
0x18004633b  jns     short loc_180046350
0x18004633d  jmp     short loc_18004636C
0x18004633f  jbe     short loc_180046350
0x180046341  mov     rax, [rbp+4Fh+psz]
0x180046345  mov     [rbp+4Fh+var_68], rdi
0x180046349  mov     [rax+1048h], si
0x180046350  lea     rdx, [rbp+4Fh+ppropvar+8]
0x180046354  lea     rcx, [rbp+4Fh+psz]
0x180046358  call    ?DetachInitializeIfEmpty@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAPEAG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::DetachInitializeIfEmpty(ushort * *)
0x18004635d  mov     ebx, eax
0x18004635f  test    eax, eax
0x180046361  js      short loc_18004636C
0x180046363  mov     eax, 1Fh
0x180046368  mov     word ptr [rbp+4Fh+ppropvar], ax
0x18004636c  lea     rcx, [rbp+4Fh+psz]
0x180046370  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180046375  test    ebx, ebx
0x180046377  js      short loc_180046395
0x180046379  mov     rcx, [rbp+4Fh+var_98]
0x18004637d  lea     r8, [rbp+4Fh+ppropvar]
0x180046381  xor     r9d, r9d
0x180046384  mov     rdx, r12
0x180046387  mov     rax, [rcx]
0x18004638a  mov     rax, [rax+40h]
0x18004638e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046393  mov     ebx, eax
0x180046395  lea     rcx, [rbp+4Fh+ppropvar]; pvar
0x180046399  call    cs:__imp_PropVariantClear
0x18004639f  lea     rcx, [rbp+4Fh+var_A0]
0x1800463a3  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800463a8  lea     rcx, [rbp+4Fh+var_98]
0x1800463ac  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800463b1  mov     eax, ebx
0x1800463b3  mov     rcx, [rbp+4Fh+var_40]
0x1800463b7  xor     rcx, rsp; StackCookie
0x1800463ba  call    __security_check_cookie
0x1800463bf  mov     rbx, [rsp+0E0h+arg_0]
0x1800463c7  add     rsp, 0B0h
0x1800463ce  pop     r15
0x1800463d0  pop     r14
0x1800463d2  pop     r13
0x1800463d4  pop     r12
0x1800463d6  pop     rdi
0x1800463d7  pop     rsi
0x1800463d8  pop     rbp
0x1800463d9  retn
```
