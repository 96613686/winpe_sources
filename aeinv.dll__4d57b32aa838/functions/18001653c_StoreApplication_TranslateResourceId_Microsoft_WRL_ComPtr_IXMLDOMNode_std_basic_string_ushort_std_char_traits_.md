# StoreApplication::TranslateResourceId(Microsoft::WRL::ComPtr<IXMLDOMNode> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001653c`
- end: `0x180017166`
- name: `?TranslateResourceId@StoreApplication@@SAXAEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11@Z`
- size: `3114`
- prototype: `void __fastcall(_bstr_t::Data_t **, __int64, const OLECHAR *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001632c`

## callees

- `0x18000a39c`
- `0x180016510`
- `0x18001653c`
- `0x18001716c`
- `0x180017250`
- `0x1800172bc`
- `0x1800175b0`
- `0x180017614`
- `0x180018450`
- `0x180018a60`
- `0x180026e74`
- `0x180029328`
- `0x1800300c0`
- `0x18003ffec`
- `0x1800402b4`
- `0x180040498`
- `0x180040500`
- `0x180044c88`
- `0x180045468`
- `0x180046d58`
- `0x18004eab4`
- `0x180051708`
- `0x180059920`
- `0x180059cf0`
- `0x18005a0ac`
- `0x1800679f8`
- `0x180067fc8`
- `0x180068f60`
- `0x1801003f4`
- `0x180130010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800166d0`
- `OLEAUT32!__imp_SysAllocString` at `0x180016ad0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800166d0`
- `OLEAUT32!__imp_SysAllocString` at `0x180016ad0`
- `OLEAUT32!__imp_VariantInit` at `0x180016619`
- `OLEAUT32!__imp_VariantInit` at `0x18001681e`
- `OLEAUT32!__imp_VariantInit` at `0x180016619`
- `OLEAUT32!__imp_VariantInit` at `0x18001681e`
- `OLEAUT32!__imp_VariantClear` at `0x180016855`
- `OLEAUT32!__imp_VariantClear` at `0x1800168ac`
- `OLEAUT32!__imp_VariantClear` at `0x180016b11`
- `OLEAUT32!__imp_VariantClear` at `0x180016855`
- `OLEAUT32!__imp_VariantClear` at `0x1800168ac`
- `OLEAUT32!__imp_VariantClear` at `0x180016b11`
- `OLEAUT32!__imp_VariantCopy` at `0x180016629`
- `OLEAUT32!__imp_VariantCopy` at `0x180016629`
- `OLEAUT32!__imp_VariantChangeType` at `0x180016834`
- `OLEAUT32!__imp_VariantChangeType` at `0x180016834`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x180016a66`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x180016d0b`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x180016dc9`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x180016e59`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x180016a66`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x180016d0b`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x180016dc9`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x180016e59`

## string_xrefs

- `0x180016f81`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x180016f93`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x180016fc7`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x180016fdc`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall StoreApplication::TranslateResourceId(
        _bstr_t::Data_t **a1,
        __int64 a2,
        const OLECHAR *a3,
        const unsigned __int16 *a4)
{
  _bstr_t::Data_t *v8; // rdi
  __int64 (__fastcall *v9)(_bstr_t::Data_t *, _QWORD **); // rbx
  int v10; // eax
  const char *v11; // r9
  _QWORD *v12; // rbx
  int v13; // eax
  HRESULT v14; // eax
  const unsigned __int16 *bstrVal; // rbx
  void *v16; // rax
  _bstr_t::Data_t *v17; // rbx
  __int64 v18; // r14
  BSTR *v19; // rax
  BSTR *v20; // rdi
  BSTR v21; // rax
  int v22; // eax
  _bstr_t::Data_t *v23; // rcx
  _bstr_t::Data_t *v24; // rbx
  _bstr_t::Data_t *v25; // rdx
  void *v26; // rdx
  _bstr_t::Data_t *v27; // rcx
  _QWORD *v28; // rcx
  HRESULT v29; // eax
  __int64 v30; // rdx
  _bstr_t::Data_t *v31; // rsi
  __int64 v32; // rdi
  __int64 v33; // r8
  void **v34; // rdx
  unsigned __int64 v35; // r8
  void **v36; // rsi
  __int64 v37; // rcx
  __int64 v38; // rbx
  _bstr_t::Data_t *v39; // rdx
  void *v40; // rcx
  void **v41; // rax
  void **v42; // r8
  __int64 v43; // rcx
  PWSTR *v44; // rcx
  WCHAR *v45; // rdx
  const WCHAR *v46; // rcx
  PWSTR *v47; // rdx
  _bstr_t::Data_t *v48; // rcx
  __int64 v49; // rax
  PWSTR *v50; // rax
  _bstr_t::Data_t *v51; // rdi
  __int64 v52; // rsi
  PWSTR *v53; // rbx
  void *v54; // rdx
  void *v55; // rdx
  _bstr_t::Data_t *v56; // rcx
  __m128i si128; // xmm0
  void *v58; // rdx
  _bstr_t::Data_t *v59; // rcx
  void *v60; // rdx
  _bstr_t::Data_t *v61; // rcx
  void *v62; // rdx
  _bstr_t::Data_t *v63; // rcx
  size_t v64; // r8
  __int64 v65; // rax
  void **v66; // rax
  void **v67; // r8
  wchar_t *v68; // rbx
  WCHAR *v69; // rdx
  const WCHAR *v70; // rcx
  PWSTR *v71; // rdx
  __int64 v72; // rax
  void **v73; // rcx
  __int64 v74; // rax
  void **v75; // rax
  void **v76; // r8
  wchar_t *v77; // rbx
  WCHAR *v78; // rdx
  const WCHAR *v79; // rcx
  PWSTR *v80; // rdx
  __int64 v81; // rax
  void **v82; // r9
  void **v83; // r8
  wchar_t *v84; // rbx
  WCHAR *v85; // rdx
  const WCHAR *v86; // rcx
  _bstr_t::Data_t *v87; // rbx
  void (__fastcall *v88)(_bstr_t::Data_t *, VARIANTARG *); // rdi
  char *v89; // rbx
  __int64 seq_traits_avx_2_void_unsigned_short; // rax
  PWSTR *v91; // r10
  __int64 v92; // r10
  __int64 v93; // rax
  int v94; // [rsp+20h] [rbp-E0h]
  _bstr_t::Data_t *v95; // [rsp+30h] [rbp-D0h] BYREF
  void *v96; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v97; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG pvargSrc; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v100; // [rsp+78h] [rbp-88h]
  PWSTR pszOutBuf[2]; // [rsp+80h] [rbp-80h] BYREF
  UINT cchOutBuf[2]; // [rsp+90h] [rbp-70h]
  unsigned __int64 v103; // [rsp+98h] [rbp-68h]
  void *v104[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v105; // [rsp+B0h] [rbp-50h]
  PCWSTR pszSource[2]; // [rsp+C0h] [rbp-40h] BYREF
  __m128i v107; // [rsp+D0h] [rbp-30h]
  VARIANTARG pvargDest; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v109; // [rsp+F8h] [rbp-8h]
  void *Src[3]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v111; // [rsp+118h] [rbp+18h]
  void *v112[2]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int64 v113; // [rsp+130h] [rbp+30h]
  unsigned __int64 v114; // [rsp+138h] [rbp+38h]
  void *v115[2]; // [rsp+140h] [rbp+40h] BYREF
  __m128i v116; // [rsp+150h] [rbp+50h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v100 = -2;
  v97 = 0;
  v8 = *a1;
  v9 = *(__int64 (__fastcall **)(_bstr_t::Data_t *, _QWORD **))(*(_QWORD *)*a1 + 136LL);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v97);
  v10 = v9(v8, &v97);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x7DB,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v10,
      v94);
  v12 = v97;
  if ( !v97 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x7DC,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      v11);
  if ( !*((_QWORD *)a3 + 2) )
  {
LABEL_4:
    memset(&pvargSrc, 0, sizeof(pvargSrc));
    pvargSrc.vt = 13;
    v13 = (*(__int64 (__fastcall **)(_bstr_t::Data_t *, VARIANTARG *))(*(_QWORD *)*a1 + 240LL))(*a1, &pvargSrc);
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x7F1,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
        (const char *)(unsigned int)v13,
        v94);
    VariantInit(&pvarg);
    v14 = VariantCopy(&pvarg, &pvargSrc);
    if ( v14 < 0 )
      _com_issue_error(v14);
    v95 = 0;
    if ( pvarg.vt == 8 )
    {
      bstrVal = pvarg.bstrVal;
      _bstr_t::~_bstr_t((_bstr_t *)&v95);
      v16 = operator new(0x18u);
      v96 = v16;
      if ( v16 )
        v17 = (_bstr_t::Data_t *)_bstr_t::Data_t::Data_t((_bstr_t::Data_t *)v16, bstrVal);
      else
        v17 = 0;
      v95 = v17;
      if ( !v17 )
        _com_issue_error(-2147024882);
    }
    else
    {
      VariantInit(&pvargDest);
      v29 = VariantChangeType(&pvargDest, &pvarg, 0, 8u);
      if ( v29 < 0 )
        _com_issue_error(v29);
      _bstr_t::operator=(&v95, pvargDest.llVal);
      VariantClear(&pvargDest);
      v17 = v95;
    }
    if ( v17 )
    {
      v30 = *(_QWORD *)v17;
      v31 = v17;
    }
    else
    {
      v30 = 0;
      v31 = 0;
    }
    *(_OWORD *)v104 = 0;
    v105 = 0u;
    v32 = -1;
    v33 = -1;
    do
      ++v33;
    while ( *(_WORD *)(v30 + 2 * v33) );
    std::wstring::_Construct<1,unsigned short const *>(v104);
    if ( v31 )
      _bstr_t::Data_t::Release(v17);
    VariantClear(&pvarg);
    *(_OWORD *)v115 = 0;
    v116 = 0;
    v34 = v104;
    if ( *((_QWORD *)&v105 + 1) > 7u )
      v34 = (void **)v104[0];
    std::wstring::_Construct<2,unsigned short const *>(v115, v34, v105);
    if ( !(_QWORD)v105 )
      goto LABEL_95;
    *(_OWORD *)v112 = 0;
    v113 = 0;
    v114 = 0;
    std::wstring::_Construct<1,unsigned short const *>(v112);
    v35 = v113;
    v36 = v104;
    if ( *((_QWORD *)&v105 + 1) > 7u )
      v36 = (void **)v104[0];
    if ( v113 > (unsigned __int64)v105 )
    {
      v65 = -1;
    }
    else
    {
      if ( !v113 )
        goto LABEL_46;
      v89 = (char *)v36 + 2 * v105;
      seq_traits_avx_2_void_unsigned_short = anonymous_namespace_::_Find_seq::_Search_impl__anonymous_namespace_::_Finding::_Find_traits_2_A0x8fcf2c39::_Find_seq::_Find_seq_traits_avx_2_void_unsigned_short_(
                                               v36,
                                               v89);
      if ( (char *)seq_traits_avx_2_void_unsigned_short == v89 )
        goto LABEL_90;
      v65 = (seq_traits_avx_2_void_unsigned_short - (__int64)v36) >> 1;
      v35 = v113;
    }
    if ( v65 )
      goto LABEL_90;
LABEL_46:
    v38 = std::wstring::substr(v104, &pvargDest, v35, -1);
    if ( v104 != (void **)v38 )
    {
      std::wstring::_Tidy_deallocate(v104);
      *(_OWORD *)v104 = *(_OWORD *)v38;
      v105 = *(_OWORD *)(v38 + 16);
      *(_QWORD *)(v38 + 16) = 0;
      *(_QWORD *)(v38 + 24) = 7;
      *(_WORD *)v38 = 0;
    }
    if ( v109 > 7 )
    {
      v39 = (_bstr_t::Data_t *)(2 * v109 + 2);
      v95 = v39;
      v40 = *(void **)&pvargDest.vt;
      v96 = *(void **)&pvargDest.vt;
      if ( (unsigned __int64)v39 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v96, (unsigned __int64 *)&v95);
        v39 = v95;
        v40 = v96;
      }
      operator delete(v40, v39);
    }
    Utility::TrimChar(v37, v104);
    Utility::GetDirectoryFromPath(Src, a2);
    std::wstring::_Append<unsigned short>(Src);
    v41 = v104;
    if ( *((_QWORD *)&v105 + 1) > 7u )
      v41 = (void **)v104[0];
    v42 = Src;
    if ( v111 > 7 )
      v42 = (void **)Src[0];
    Utility::FormatWstring((wchar_t *)pszSource, L"@{%ws? ms-resource://%ws/resources/%ws}", v42, &byte_1801389F0, v41);
    *(_OWORD *)pszOutBuf = 0;
    *(_QWORD *)cchOutBuf = 0;
    v103 = 0;
    std::wstring::_Construct_empty(pszOutBuf);
    v43 = *(_QWORD *)cchOutBuf;
    if ( *(_QWORD *)cchOutBuf < 0x104u )
    {
      v64 = 260LL - *(_QWORD *)cchOutBuf;
      if ( 260LL - *(_QWORD *)cchOutBuf <= v103 - *(_QWORD *)cchOutBuf )
      {
        *(_QWORD *)cchOutBuf = 260;
        v91 = pszOutBuf;
        if ( v103 > 7 )
          v91 = (PWSTR *)pszOutBuf[0];
        wmemset((wchar_t *)v91 + v43, 0, v64);
        *(_WORD *)(v92 + 520) = 0;
      }
      else
      {
        std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(
          (unsigned int)pszOutBuf,
          260 - cchOutBuf[0],
          v64,
          260 - cchOutBuf[0],
          0);
      }
    }
    else
    {
      *(_QWORD *)cchOutBuf = 260;
      v44 = pszOutBuf;
      if ( v103 > 7 )
        v44 = (PWSTR *)pszOutBuf[0];
      *((_WORD *)v44 + 260) = 0;
    }
    v45 = (WCHAR *)pszOutBuf;
    if ( v103 > 7 )
      v45 = pszOutBuf[0];
    v46 = (const WCHAR *)pszSource;
    if ( v107.m128i_i64[1] > 7uLL )
      v46 = pszSource[0];
    SHLoadIndirectString(v46, v45, cchOutBuf[0], 0);
    v47 = pszOutBuf;
    v48 = (_bstr_t::Data_t *)pszOutBuf[0];
    if ( v103 > 7 )
      v47 = (PWSTR *)pszOutBuf[0];
    v49 = -1;
    do
      ++v49;
    while ( *((_WORD *)v47 + v49) );
    if ( !v49 )
    {
      v66 = v104;
      if ( *((_QWORD *)&v105 + 1) > 7u )
        v66 = (void **)v104[0];
      v67 = Src;
      if ( v111 > 7 )
        v67 = (void **)Src[0];
      v68 = Utility::FormatWstring(&pvargDest.vt, L"@{%ws? ms-resource://%ws/%ws}", v67, &byte_1801389F0, v66);
      if ( pszSource != (PCWSTR *)v68 )
      {
        std::wstring::_Tidy_deallocate(pszSource);
        *(_OWORD *)pszSource = *(_OWORD *)v68;
        v107 = *((__m128i *)v68 + 1);
        *((_QWORD *)v68 + 2) = 0;
        *((_QWORD *)v68 + 3) = 7;
        *v68 = 0;
      }
      std::wstring::~wstring(&pvargDest);
      v69 = (WCHAR *)pszOutBuf;
      if ( v103 > 7 )
        v69 = pszOutBuf[0];
      v70 = (const WCHAR *)pszSource;
      if ( v107.m128i_i64[1] > 7uLL )
        v70 = pszSource[0];
      SHLoadIndirectString(v70, v69, cchOutBuf[0], 0);
      v71 = pszOutBuf;
      v48 = (_bstr_t::Data_t *)pszOutBuf[0];
      if ( v103 > 7 )
        v71 = (PWSTR *)pszOutBuf[0];
      v72 = -1;
      do
        ++v72;
      while ( *((_WORD *)v71 + v72) );
      if ( !v72 )
      {
        v73 = v104;
        if ( *((_QWORD *)&v105 + 1) > 7u )
          v73 = (void **)v104[0];
        v74 = std::_Traits_rfind_ch<std::char_traits<unsigned short>>(v73, v105, -1, 47);
        if ( v74 != -1 )
        {
          v93 = std::wstring::substr(v104, &pvargDest, v74 + 1, v105);
          std::wstring::operator=(v104, v93);
          std::wstring::~wstring(&pvargDest);
        }
        v75 = v104;
        if ( *((_QWORD *)&v105 + 1) > 7u )
          v75 = (void **)v104[0];
        v76 = Src;
        if ( v111 > 7 )
          v76 = (void **)Src[0];
        v77 = Utility::FormatWstring(&pvargDest.vt, L"@{%ws? ms-resource://%ws/%ws}", v76, &byte_1801389F0, v75);
        if ( pszSource != (PCWSTR *)v77 )
        {
          std::wstring::_Tidy_deallocate(pszSource);
          *(_OWORD *)pszSource = *(_OWORD *)v77;
          v107 = *((__m128i *)v77 + 1);
          *((_QWORD *)v77 + 2) = 0;
          *((_QWORD *)v77 + 3) = 7;
          *v77 = 0;
        }
        std::wstring::~wstring(&pvargDest);
        v78 = (WCHAR *)pszOutBuf;
        if ( v103 > 7 )
          v78 = pszOutBuf[0];
        v79 = (const WCHAR *)pszSource;
        if ( v107.m128i_i64[1] > 7uLL )
          v79 = pszSource[0];
        SHLoadIndirectString(v79, v78, cchOutBuf[0], 0);
        v80 = pszOutBuf;
        v48 = (_bstr_t::Data_t *)pszOutBuf[0];
        if ( v103 > 7 )
          v80 = (PWSTR *)pszOutBuf[0];
        v81 = -1;
        do
          ++v81;
        while ( *((_WORD *)v80 + v81) );
        if ( !v81 )
        {
          v82 = v115;
          if ( v116.m128i_i64[1] > 7uLL )
            v82 = (void **)v115[0];
          v83 = Src;
          if ( v111 > 7 )
            v83 = (void **)Src[0];
          v84 = Utility::FormatWstring(&pvargDest.vt, L"@{%ws? %ws}", v83, v82);
          if ( pszSource != (PCWSTR *)v84 )
          {
            std::wstring::_Tidy_deallocate(pszSource);
            *(_OWORD *)pszSource = *(_OWORD *)v84;
            v107 = *((__m128i *)v84 + 1);
            *((_QWORD *)v84 + 2) = 0;
            *((_QWORD *)v84 + 3) = 7;
            *v84 = 0;
          }
          std::wstring::~wstring(&pvargDest);
          v85 = (WCHAR *)pszOutBuf;
          if ( v103 > 7 )
            v85 = pszOutBuf[0];
          v86 = (const WCHAR *)pszSource;
          if ( v107.m128i_i64[1] > 7uLL )
            v86 = pszSource[0];
          SHLoadIndirectString(v86, v85, cchOutBuf[0], 0);
          v48 = (_bstr_t::Data_t *)pszOutBuf[0];
        }
      }
    }
    v50 = pszOutBuf;
    if ( v103 > 7 )
      v50 = (PWSTR *)v48;
    do
      ++v32;
    while ( *((_WORD *)v50 + v32) );
    if ( v32 )
    {
      v51 = *a1;
      v52 = *(_QWORD *)*a1;
      v53 = pszOutBuf;
      if ( v103 > 7 )
        v53 = (PWSTR *)v48;
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)SysAllocString((const OLECHAR *)v53);
      if ( !pvarg.llVal && v53 )
        _com_issue_error(-2147024882);
      pvargDest = pvarg;
      (*(void (__fastcall **)(_bstr_t::Data_t *, VARIANTARG *))(v52 + 248))(v51, &pvargDest);
    }
    else
    {
      if ( !*((_QWORD *)a4 + 2) )
        goto LABEL_78;
      v87 = *a1;
      v88 = *(void (__fastcall **)(_bstr_t::Data_t *, VARIANTARG *))(*(_QWORD *)*a1 + 248LL);
      if ( *((_QWORD *)a4 + 3) > 7u )
        a4 = *(const unsigned __int16 **)a4;
      pvargDest = *(VARIANTARG *)_variant_t::_variant_t((_variant_t *)&pvarg, a4);
      v88(v87, &pvargDest);
    }
    VariantClear(&pvarg);
    v48 = (_bstr_t::Data_t *)pszOutBuf[0];
LABEL_78:
    if ( v103 > 7 )
    {
      v54 = (void *)(2 * v103 + 2);
      v96 = v54;
      v95 = v48;
      if ( (unsigned __int64)v54 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned((void **)&v95, (unsigned __int64 *)&v96);
        v54 = v96;
        v48 = v95;
      }
      operator delete(v48, (const struct std::nothrow_t *)v54);
    }
    *(_QWORD *)cchOutBuf = 0;
    v103 = 7;
    LOWORD(pszOutBuf[0]) = 0;
    if ( v107.m128i_i64[1] > 7uLL )
    {
      v55 = (void *)(2 * v107.m128i_i64[1] + 2);
      v96 = v55;
      v56 = (_bstr_t::Data_t *)pszSource[0];
      v95 = (_bstr_t::Data_t *)pszSource[0];
      if ( (unsigned __int64)v55 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned((void **)&v95, (unsigned __int64 *)&v96);
        v55 = v96;
        v56 = v95;
      }
      operator delete(v56, (const struct std::nothrow_t *)v55);
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v107 = si128;
    LOWORD(pszSource[0]) = 0;
    if ( v111 <= 7 )
      goto LABEL_91;
    v58 = (void *)(2 * v111 + 2);
    v96 = v58;
    v59 = (_bstr_t::Data_t *)Src[0];
    v95 = (_bstr_t::Data_t *)Src[0];
    if ( (unsigned __int64)v58 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned((void **)&v95, (unsigned __int64 *)&v96);
      v58 = v96;
      v59 = v95;
    }
    operator delete(v59, (const struct std::nothrow_t *)v58);
LABEL_90:
    si128 = _mm_load_si128((const __m128i *)&_xmm);
LABEL_91:
    if ( v114 <= 7 )
    {
LABEL_96:
      if ( v116.m128i_i64[1] > 7uLL )
      {
        v62 = (void *)(2 * v116.m128i_i64[1] + 2);
        v96 = v62;
        v63 = (_bstr_t::Data_t *)v115[0];
        v95 = (_bstr_t::Data_t *)v115[0];
        if ( (unsigned __int64)v62 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned((void **)&v95, (unsigned __int64 *)&v96);
          v62 = v96;
          v63 = v95;
        }
        operator delete(v63, (const struct std::nothrow_t *)v62);
        si128 = _mm_load_si128((const __m128i *)&_xmm);
      }
      v116 = si128;
      LOWORD(v115[0]) = 0;
      if ( *((_QWORD *)&v105 + 1) > 7u )
      {
        v26 = (void *)(2LL * *((_QWORD *)&v105 + 1) + 2);
        v96 = v26;
        v27 = (_bstr_t::Data_t *)v104[0];
        v95 = (_bstr_t::Data_t *)v104[0];
        if ( (unsigned __int64)v26 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned((void **)&v95, (unsigned __int64 *)&v96);
          v26 = v96;
          v27 = v95;
        }
        operator delete(v27, (const struct std::nothrow_t *)v26);
      }
      *(_QWORD *)&v105 = 0;
      *((_QWORD *)&v105 + 1) = 7;
      LOWORD(v104[0]) = 0;
      goto LABEL_27;
    }
    v60 = (void *)(2 * v114 + 2);
    v96 = v60;
    v61 = (_bstr_t::Data_t *)v112[0];
    v95 = (_bstr_t::Data_t *)v112[0];
    if ( (unsigned __int64)v60 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned((void **)&v95, (unsigned __int64 *)&v96);
      v60 = v96;
      v61 = v95;
    }
    operator delete(v61, (const struct std::nothrow_t *)v60);
LABEL_95:
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    goto LABEL_96;
  }
  v95 = 0;
  v18 = *v97;
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v95);
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(const OLECHAR **)a3;
  v19 = (BSTR *)operator new(0x18u);
  v20 = v19;
  v96 = v19;
  if ( v19 )
  {
    v19[1] = 0;
    *((_DWORD *)v19 + 4) = 1;
    v21 = SysAllocString(a3);
    *v20 = v21;
    if ( !v21 && a3 )
      _com_issue_error(-2147024882);
  }
  else
  {
    v20 = 0;
  }
  v96 = v20;
  if ( !v20 )
    _com_issue_error(-2147024882);
  v22 = (*(__int64 (__fastcall **)(_QWORD *, BSTR, _bstr_t::Data_t **))(v18 + 56))(v12, *v20, &v95);
  if ( v22 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x7E2,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v22,
      v94);
  _bstr_t::Data_t::Release((_bstr_t::Data_t *)v20);
  v23 = v95;
  if ( v95 )
  {
    if ( *a1 != v95 )
    {
      v24 = v95;
      (*(void (**)(void))(*(_QWORD *)v95 + 8LL))();
      v23 = v95;
      v25 = *a1;
      *a1 = v24;
      if ( v25 )
      {
        (*(void (__fastcall **)(_bstr_t::Data_t *))(*(_QWORD *)v25 + 16LL))(v25);
        v23 = v95;
      }
    }
    if ( v23 )
    {
      v95 = 0;
      (*(void (__fastcall **)(_bstr_t::Data_t *))(*(_QWORD *)v23 + 16LL))(v23);
    }
    goto LABEL_4;
  }
LABEL_27:
  v28 = v97;
  if ( v97 )
  {
    v97 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
  }
}

```

## disassembly

```asm
0x18001653c  push    rbp
0x18001653e  push    rbx
0x18001653f  push    rsi
0x180016540  push    rdi
0x180016541  push    r12
0x180016543  push    r13
0x180016545  push    r14
0x180016547  push    r15
0x180016549  lea     rbp, [rsp-78h]
0x18001654e  sub     rsp, 178h
0x180016555  mov     [rsp+1B0h+var_138], 0FFFFFFFFFFFFFFFEh
0x18001655e  mov     rax, cs:__security_cookie
0x180016565  xor     rax, rsp
0x180016568  mov     [rbp+0B0h+var_50], rax
0x18001656c  mov     r12, r9
0x18001656f  mov     rsi, r8
0x180016572  mov     r13, rdx
0x180016575  mov     r15, rcx
0x180016578  xor     r14d, r14d
0x18001657b  mov     [rsp+1B0h+var_170], r14
0x180016580  mov     rdi, [rcx]
0x180016583  mov     rax, [rdi]
0x180016586  mov     rbx, [rax+88h]
0x18001658d  lea     rcx, [rsp+1B0h+var_170]
0x180016592  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x180016597  lea     rdx, [rsp+1B0h+var_170]
0x18001659c  mov     rcx, rdi
0x18001659f  mov     rax, rbx
0x1800165a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165a7  mov     rcx, [rbp+0B8h]; this
0x1800165ae  test    eax, eax
0x1800165b0  js      loc_180016F7E
0x1800165b6  mov     rcx, [rbp+0B8h]; this
0x1800165bd  mov     rbx, [rsp+1B0h+var_170]
0x1800165c2  test    rbx, rbx
0x1800165c5  jz      loc_180016F93
0x1800165cb  cmp     [rsi+10h], r14
0x1800165cf  ja      loc_180016686
0x1800165d5  xorps   xmm0, xmm0
0x1800165d8  xor     eax, eax
0x1800165da  movups  xmmword ptr [rsp+1B0h+pvargSrc], xmm0
0x1800165df  mov     qword ptr [rsp+1B0h+pvargSrc+10h], rax
0x1800165e4  mov     eax, 0Dh
0x1800165e9  mov     word ptr [rsp+1B0h+pvargSrc], ax
0x1800165ee  mov     rcx, [r15]
0x1800165f1  mov     rax, [rcx]
0x1800165f4  lea     rdx, [rsp+1B0h+pvargSrc]
0x1800165f9  mov     rax, [rax+0F0h]
0x180016600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016605  mov     rcx, [rbp+0B8h]; this
0x18001660c  test    eax, eax
0x18001660e  js      loc_180016FD9
0x180016614  lea     rcx, [rsp+1B0h+pvarg]; pvarg
0x180016619  call    cs:__imp_VariantInit
0x18001661f  lea     rdx, [rsp+1B0h+pvargSrc]; pvargSrc
0x180016624  lea     rcx, [rsp+1B0h+pvarg]; pvargDest
0x180016629  call    cs:__imp_VariantCopy
0x18001662f  test    eax, eax
0x180016631  js      loc_180016FEE
0x180016637  mov     [rsp+1B0h+var_180], r14
0x18001663c  mov     ebx, 8
0x180016641  cmp     word ptr [rsp+1B0h+pvarg], bx
0x180016646  jnz     loc_18001681A
0x18001664c  mov     rbx, qword ptr [rsp+1B0h+pvarg+8]
0x180016651  lea     rcx, [rsp+1B0h+var_180]; this
0x180016656  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001665b  mov     ecx, 18h; Size
0x180016660  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016665  mov     [rsp+1B0h+var_178], rax
0x18001666a  test    rax, rax
0x18001666d  jz      loc_180016FF6
0x180016673  mov     rdx, rbx; unsigned __int16 *
0x180016676  mov     rcx, rax; this
0x180016679  call    ??0Data_t@_bstr_t@@QEAA@PEBG@Z; _bstr_t::Data_t::Data_t(ushort const *)
0x18001667e  mov     rbx, rax
0x180016681  jmp     loc_180016FF9
0x180016686  mov     [rsp+1B0h+var_180], r14
0x18001668b  mov     r14, [rbx]
0x18001668e  lea     rcx, [rsp+1B0h+var_180]
0x180016693  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x180016698  cmp     qword ptr [rsi+18h], 7
0x18001669d  ja      loc_1800167F0
0x1800166a3  mov     ecx, 18h; Size
0x1800166a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800166ad  mov     rdi, rax
0x1800166b0  mov     [rsp+1B0h+var_178], rax
0x1800166b5  test    rax, rax
0x1800166b8  jz      loc_1800167F8
0x1800166be  mov     qword ptr [rax+8], 0
0x1800166c6  mov     dword ptr [rax+10h], 1
0x1800166cd  mov     rcx, rsi; psz
0x1800166d0  call    cs:__imp_SysAllocString
0x1800166d6  mov     [rdi], rax
0x1800166d9  test    rax, rax
0x1800166dc  jz      loc_180016FA5
0x1800166e2  mov     [rsp+1B0h+var_178], rdi
0x1800166e7  test    rdi, rdi
0x1800166ea  jz      loc_180016FB9
0x1800166f0  lea     r8, [rsp+1B0h+var_180]
0x1800166f5  mov     rdx, [rdi]
0x1800166f8  mov     rcx, rbx
0x1800166fb  mov     rax, [r14+38h]
0x1800166ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016704  mov     rcx, [rbp+0B8h]; this
0x18001670b  xor     r14d, r14d
0x18001670e  test    eax, eax
0x180016710  js      loc_180016FC4
0x180016716  mov     rcx, rdi; this
0x180016719  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x18001671e  mov     rcx, [rsp+1B0h+var_180]
0x180016723  test    rcx, rcx
0x180016726  jz      short loc_180016781
0x180016728  cmp     [r15], rcx
0x18001672b  jz      short loc_180016765
0x18001672d  mov     rbx, rcx
0x180016730  test    rcx, rcx
0x180016733  jz      short loc_180016746
0x180016735  mov     rax, [rcx]
0x180016738  mov     rax, [rax+8]
0x18001673c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016741  mov     rcx, [rsp+1B0h+var_180]
0x180016746  mov     rdx, [r15]
0x180016749  mov     [r15], rbx
0x18001674c  test    rdx, rdx
0x18001674f  jz      short loc_180016765
0x180016751  mov     rax, [rdx]
0x180016754  mov     rcx, rdx
0x180016757  mov     rax, [rax+10h]
0x18001675b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016760  mov     rcx, [rsp+1B0h+var_180]
0x180016765  test    rcx, rcx
0x180016768  jz      short loc_18001677C
0x18001676a  mov     [rsp+1B0h+var_180], r14
0x18001676f  mov     rax, [rcx]
0x180016772  mov     rax, [rax+10h]
0x180016776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001677b  nop
0x18001677c  jmp     loc_1800165D5
0x180016781  jmp     short loc_1800167B4
0x180016783  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x18001678b  mov     [rsp+1B0h+var_178], rdx
0x180016790  mov     rcx, [rbp+0B0h+var_110]; void *
0x180016794  mov     [rsp+1B0h+var_180], rcx
0x180016799  cmp     rdx, 1000h
0x1800167a0  jnb     short loc_1800167FF
0x1800167a2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800167a7  mov     qword ptr [rbp+0B0h+var_100], r14
0x1800167ab  mov     qword ptr [rbp+0B0h+var_100+8], r13
0x1800167af  mov     word ptr [rbp+0B0h+var_110], r14w
0x1800167b4  mov     rcx, [rsp+1B0h+var_170]
0x1800167b9  test    rcx, rcx
0x1800167bc  jz      short loc_1800167D0
0x1800167be  mov     [rsp+1B0h+var_170], r14
0x1800167c3  mov     rax, [rcx]
0x1800167c6  mov     rax, [rax+10h]
0x1800167ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167cf  nop
0x1800167d0  mov     rcx, [rbp+0B0h+var_50]
0x1800167d4  xor     rcx, rsp; StackCookie
0x1800167d7  call    __security_check_cookie
0x1800167dc  add     rsp, 178h
0x1800167e3  pop     r15
0x1800167e5  pop     r14
0x1800167e7  pop     r13
0x1800167e9  pop     r12
0x1800167eb  pop     rdi
0x1800167ec  pop     rsi
0x1800167ed  pop     rbx
0x1800167ee  pop     rbp
0x1800167ef  retn
0x1800167f0  mov     rsi, [rsi]
0x1800167f3  jmp     loc_1800166A3
0x1800167f8  xor     edi, edi
0x1800167fa  jmp     loc_1800166E2
0x1800167ff  lea     rdx, [rsp+1B0h+var_178]; unsigned __int64 *
0x180016804  lea     rcx, [rsp+1B0h+var_180]; void **
0x180016809  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18001680e  mov     rdx, [rsp+1B0h+var_178]
0x180016813  mov     rcx, [rsp+1B0h+var_180]
0x180016818  jmp     short loc_1800167A2
0x18001681a  lea     rcx, [rbp+0B0h+pvargDest]; pvarg
0x18001681e  call    cs:__imp_VariantInit
0x180016824  nop
0x180016825  mov     r9d, ebx; vt
0x180016828  xor     r8d, r8d; wFlags
0x18001682b  lea     rdx, [rsp+1B0h+pvarg]; pvarSrc
0x180016830  lea     rcx, [rbp+0B0h+pvargDest]; pvargDest
0x180016834  call    cs:__imp_VariantChangeType
0x18001683a  test    eax, eax
0x18001683c  js      loc_180017012
0x180016842  mov     rdx, qword ptr [rbp+0B0h+pvargDest+8]
0x180016846  lea     rcx, [rsp+1B0h+var_180]
0x18001684b  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180016850  nop
0x180016851  lea     rcx, [rbp+0B0h+pvargDest]; pvarg
0x180016855  call    cs:__imp_VariantClear
0x18001685b  mov     rbx, [rsp+1B0h+var_180]
0x180016860  test    rbx, rbx
0x180016863  jz      loc_18001701A
0x180016869  mov     rdx, [rbx]
0x18001686c  mov     rsi, rbx
0x18001686f  xorps   xmm0, xmm0
0x180016872  movups  xmmword ptr [rbp+0B0h+var_110], xmm0
0x180016876  mov     qword ptr [rbp+0B0h+var_100], r14
0x18001687a  mov     qword ptr [rbp+0B0h+var_100+8], r14
0x18001687e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180016882  mov     r8, rdi
0x180016885  inc     r8
0x180016888  cmp     [rdx+r8*2], r14w
0x18001688d  jnz     short loc_180016885
0x18001688f  lea     rcx, [rbp+0B0h+var_110]
0x180016893  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180016898  nop
0x180016899  test    rsi, rsi
0x18001689c  jz      short loc_1800168A7
0x18001689e  mov     rcx, rbx; this
0x1800168a1  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x1800168a6  nop
0x1800168a7  lea     rcx, [rsp+1B0h+pvarg]; pvarg
0x1800168ac  call    cs:__imp_VariantClear
0x1800168b2  xorps   xmm0, xmm0
0x1800168b5  movups  xmmword ptr [rbp+0B0h+var_70], xmm0
0x1800168b9  xorps   xmm1, xmm1
0x1800168bc  movdqu  [rbp+0B0h+var_60], xmm1
0x1800168c1  lea     rdx, [rbp+0B0h+var_110]
0x1800168c5  cmp     qword ptr [rbp+0B0h+var_100+8], 7
0x1800168ca  cmova   rdx, [rbp+0B0h+var_110]
0x1800168cf  mov     r8, qword ptr [rbp+0B0h+var_100]
0x1800168d3  lea     rcx, [rbp+0B0h+var_70]
0x1800168d7  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1800168dc  nop
0x1800168dd  cmp     qword ptr [rbp+0B0h+var_100], r14
0x1800168e1  jz      loc_180016E68
0x1800168e7  xorps   xmm0, xmm0
0x1800168ea  movups  xmmword ptr [rbp+0B0h+var_90], xmm0
0x1800168ee  mov     [rbp+0B0h+var_80], r14
0x1800168f2  mov     [rbp+0B0h+var_78], r14
0x1800168f6  mov     r8d, 0Ch
0x1800168fc  lea     rdx, aMsResource; "ms-resource:"
0x180016903  lea     rcx, [rbp+0B0h+var_90]
0x180016907  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001690c  nop
0x18001690d  mov     r8, [rbp+0B0h+var_80]
0x180016911  lea     rax, [rbp+0B0h+var_90]
0x180016915  cmp     [rbp+0B0h+var_78], 7
0x18001691a  cmova   rax, [rbp+0B0h+var_90]
0x18001691f  mov     rcx, qword ptr [rbp+0B0h+var_100]
0x180016923  lea     rsi, [rbp+0B0h+var_110]
0x180016927  cmp     qword ptr [rbp+0B0h+var_100+8], 7
0x18001692c  cmova   rsi, [rbp+0B0h+var_110]
0x180016931  cmp     r8, rcx
0x180016934  ja      loc_180016C88
0x18001693a  test    r8, r8
0x18001693d  jnz     loc_180017025
0x180016943  mov     r9, rdi
0x180016946  lea     rdx, [rbp+0B0h+pvargDest]
0x18001694a  lea     rcx, [rbp+0B0h+var_110]
0x18001694e  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180016953  mov     rbx, rax
0x180016956  lea     rax, [rbp+0B0h+var_110]
0x18001695a  cmp     rax, rbx
0x18001695d  jnz     loc_180017052
0x180016963  mov     rdx, [rbp+0B0h+var_B8]
0x180016967  cmp     rdx, 7
0x18001696b  jbe     short loc_180016995
0x18001696d  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x180016975  mov     [rsp+1B0h+var_180], rdx
0x18001697a  mov     rcx, qword ptr [rbp+0B0h+pvargDest]; void *
0x18001697e  mov     [rsp+1B0h+var_178], rcx
0x180016983  cmp     rdx, 1000h
0x18001698a  jnb     loc_180016E73
0x180016990  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016995  lea     rdx, [rbp+0B0h+var_110]
0x180016999  call    ?TrimChar@Utility@@SAXDAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Utility::TrimChar(char,std::wstring &)
0x18001699e  mov     rdx, r13
0x1800169a1  lea     rcx, [rbp+0B0h+Src]
0x1800169a5  call    ?GetDirectoryFromPath@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::GetDirectoryFromPath(std::wstring const &)
0x1800169aa  nop
0x1800169ab  mov     r8d, 0Eh
0x1800169b1  lea     rdx, aResourcesPri; "\\resources.pri"
0x1800169b8  lea     rcx, [rbp+0B0h+Src]; Src
0x1800169bc  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800169c1  lea     rax, [rbp+0B0h+var_110]
0x1800169c5  mov     r13d, 7
0x1800169cb  cmp     qword ptr [rbp+0B0h+var_100+8], r13
0x1800169cf  cmova   rax, [rbp+0B0h+var_110]
0x1800169d4  lea     r8, [rbp+0B0h+Src]
0x1800169d8  cmp     [rbp+0B0h+var_98], r13
0x1800169dc  cmova   r8, [rbp+0B0h+Src]
0x1800169e1  mov     qword ptr [rsp+1B0h+var_190], rax
0x1800169e6  lea     rsi, byte_1801389F0
0x1800169ed  mov     r9, rsi
0x1800169f0  lea     rdx, aWsMsResourceWs; "@{%ws? ms-resource://%ws/resources/%ws}"
0x1800169f7  lea     rcx, [rbp+0B0h+pszSource]
0x1800169fb  call    ?FormatWstring@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Utility::FormatWstring(ushort const *,...)
0x180016a00  nop
0x180016a01  xorps   xmm0, xmm0
0x180016a04  movups  xmmword ptr [rbp+0B0h+pszOutBuf], xmm0
0x180016a08  mov     qword ptr [rbp+0B0h+cchOutBuf], r14
0x180016a0c  mov     [rbp+0B0h+var_118], r14
  ... truncated ...
```
