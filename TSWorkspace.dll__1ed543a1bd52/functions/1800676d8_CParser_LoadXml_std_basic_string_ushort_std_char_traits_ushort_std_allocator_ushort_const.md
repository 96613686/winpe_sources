# CParser::LoadXml(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800676d8`
- end: `0x1800681af`
- name: `?LoadXml@CParser@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `2775`
- prototype: `__int64 __fastcall(LPVOID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `22`
- tags: `reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004adfc`

## callees

- `0x1800054c4`
- `0x18000b1d8`
- `0x18000d948`
- `0x18000dbdc`
- `0x18000ec94`
- `0x18000ece0`
- `0x18000ef54`
- `0x18000efc4`
- `0x18000ff00`
- `0x180020964`
- `0x180020bf0`
- `0x180027e9c`
- `0x180027ef8`
- `0x1800289a8`
- `0x1800461b0`
- `0x180063e8c`
- `0x1800644bc`
- `0x1800676d8`
- `0x18006c158`
- `0x18009a520`
- `0x18009a5e0`
- `0x1800a3010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180067794`
- `ole32!CoCreateInstance` at `0x18006781e`
- `ole32!CoCreateInstance` at `0x180067794`
- `ole32!CoCreateInstance` at `0x18006781e`
- `ole32!CoTaskMemFree` at `0x180068145`
- `ole32!CoTaskMemFree` at `0x180068145`
- `OLEAUT32!__imp_SysFreeString` at `0x180067d53`
- `OLEAUT32!__imp_SysFreeString` at `0x180068033`
- `OLEAUT32!__imp_SysFreeString` at `0x180067d53`
- `OLEAUT32!__imp_SysFreeString` at `0x180068033`
- `OLEAUT32!__imp_VariantInit` at `0x18006773d`
- `OLEAUT32!__imp_VariantInit` at `0x18006773d`
- `OLEAUT32!__imp_VariantClear` at `0x180068173`
- `OLEAUT32!__imp_VariantClear` at `0x180068173`
- `SHELL32!SHGetKnownFolderPath` at `0x180067d79`
- `SHELL32!SHGetKnownFolderPath` at `0x180067d79`

## string_xrefs

- `0x18006785f`: `CoCreateInstance XMLSchemaCache60 failed`
- `0x1800678ba`: `IXmlDOMDocument::put_async failed`
- `0x180067915`: `IXmlDOMDocument::put_validateOnParse failed`
- `0x180067b22`: `MaxXMLSize`
- `0x180067b70`: `IXmlDOMDocument::setProperty  MaxXMLSize failed`
- `0x180067dba`: `SHGetKnownFolderPath failed`
- `0x180067bdf`: `TSWFileURLFromPath failed`
- `0x180067f0c`: `IXMLDOMSchemaCollection::add failed`
- `0x180067f9c`: `IXmlDOMDocument::putref_schemas failed`
- `0x1800677d3`: `CoCreateInstance DomDocument60 failed`
- `0x180067970`: `IXmlDOMDocument::put_resolveExternals failed`
- `0x180067a32`: `IXmlDOMDocument::setProperty  UseInlineSchema failed`
- `0x180067aee`: `IXmlDOMDocument::setProperty NormalizeAttributeValues failed`
- `0x180067c8d`: `IXmlDOMDocument::LoadXML failed`
- `0x180067e74`: `http://schemas.microsoft.com/ts/2007/05/tswf`

## pseudocode

```c
__int64 __fastcall CParser::LoadXml(LPVOID *a1, const unsigned __int16 *a2)
{
  _QWORD *v4; // rsi
  HRESULT Instance; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v7; // edx
  const char *v8; // rcx
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, __int64, VARIANTARG *); // rdi
  __int128 v11; // xmm6
  IRecordInfo *v12; // xmm7_8
  _bstr_t *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rbx
  __int64 (__fastcall *v16)(__int64, __int64, VARIANTARG *); // rdi
  __int128 v17; // xmm6
  IRecordInfo *v18; // xmm7_8
  _bstr_t *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  const unsigned __int16 *v22; // rcx
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, VARIANTARG *, _WORD *); // rbx
  const struct _bstr_t *v25; // rax
  BSTR v26; // rbx
  char v27; // di
  unsigned int v28; // eax
  int v29; // r8d
  const unsigned __int16 *v30; // rcx
  struct IDispatch *v31; // rbx
  HRESULT (__stdcall *QueryInterface)(IDispatch *, const IID *const, void **); // rdi
  const struct _bstr_t *v33; // rax
  _variant_t *v34; // rax
  __int128 v35; // xmm6
  IRecordInfo *v36; // xmm7_8
  _bstr_t *v37; // rax
  __int64 v38; // rdx
  bool v39; // r8
  __int64 v40; // rdi
  __int64 (__fastcall *v41)(__int64, VARIANTARG *); // rbx
  BSTR v42; // rbx
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  __int64 v46; // rdx
  BSTR bstrString; // [rsp+30h] [rbp-D0h] BYREF
  _WORD v49[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v50; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int v51; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v52; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG v53; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v54; // [rsp+70h] [rbp-90h] BYREF
  IRecordInfo *v55; // [rsp+80h] [rbp-80h]
  struct IDispatch *ppv; // [rsp+88h] [rbp-78h] BYREF
  PWSTR ppszPath; // [rsp+90h] [rbp-70h] BYREF
  __int64 v58; // [rsp+98h] [rbp-68h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v60; // [rsp+B8h] [rbp-48h]
  unsigned __int16 *v61[3]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v62; // [rsp+D8h] [rbp-28h]
  unsigned __int16 v63[2088]; // [rsp+E0h] [rbp-20h] BYREF

  v60 = -2;
  v49[0] = 0;
  VariantInit(&pvarg);
  v51 = 0;
  ppszPath = 0;
  v62 = 7;
  v61[2] = 0;
  LOWORD(v61[0]) = 0;
  ppv = 0;
  v58 = 0;
  v50 = 0;
  v4 = a1 + 6;
  Instance = CoCreateInstance(
               &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
               0,
               3u,
               &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
               a1 + 6);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_112;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 94;
    v8 = "CoCreateInstance DomDocument60 failed";
LABEL_6:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v8,
      Instance);
LABEL_112:
    CParser::CloseXML((CParser *)a1);
    goto LABEL_120;
  }
  Instance = CoCreateInstance(
               &GUID_88d96a07_f192_11d4_a65f_0040963251e5,
               0,
               3u,
               &GUID_373984c8_b845_449b_91e7_45ac83036ade,
               (LPVOID *)&ppv);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_112;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 95;
    v8 = "CoCreateInstance XMLSchemaCache60 failed";
    goto LABEL_6;
  }
  Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v4 + 504LL))(*v4, 0);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_112;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 96;
    v8 = "IXmlDOMDocument::put_async failed";
    goto LABEL_6;
  }
  Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v4 + 544LL))(*v4, 0);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_112;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 97;
    v8 = "IXmlDOMDocument::put_validateOnParse failed";
    goto LABEL_6;
  }
  Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v4 + 560LL))(*v4, 0);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_112;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 98;
    v8 = "IXmlDOMDocument::put_resolveExternals failed";
    goto LABEL_6;
  }
  v9 = *v4;
  v10 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)*v4 + 640LL);
  LOWORD(v54) = 11;
  WORD4(v54) = 0;
  v11 = v54;
  v12 = v55;
  v13 = _bstr_t::_bstr_t((_bstr_t *)&bstrString, L"UseInlineSchema");
  if ( *(_QWORD *)v13 )
    v14 = **(_QWORD **)v13;
  else
    v14 = 0;
  *(_OWORD *)&v53.vt = v11;
  v53.pRecInfo = v12;
  Instance = v10(v9, v14, &v53);
  _bstr_t::_Free((_bstr_t *)&bstrString);
  _variant_t::~_variant_t((_variant_t *)&v54);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_112;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 99;
    v8 = "IXmlDOMDocument::setProperty  UseInlineSchema failed";
    goto LABEL_6;
  }
  v15 = *v4;
  v16 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)*v4 + 640LL);
  LOWORD(v54) = 11;
  WORD4(v54) = 0;
  v17 = v54;
  v18 = v55;
  v19 = _bstr_t::_bstr_t((_bstr_t *)&bstrString, L"NormalizeAttributeValues");
  if ( *(_QWORD *)v19 )
    v20 = **(_QWORD **)v19;
  else
    v20 = 0;
  *(_OWORD *)&v53.vt = v17;
  v53.pRecInfo = v18;
  Instance = v16(v15, v20, &v53);
  _bstr_t::_Free((_bstr_t *)&bstrString);
  _variant_t::~_variant_t((_variant_t *)&v54);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_112;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 100;
    v8 = "IXmlDOMDocument::setProperty NormalizeAttributeValues failed";
    goto LABEL_6;
  }
  ATL::CComVariant::operator=(&pvarg);
  v21 = *v4;
  v53 = pvarg;
  Instance = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v21 + 640LL))(
               v21,
               L"MaxXMLSize",
               &v53);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_112;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 101;
    v8 = "IXmlDOMDocument::setProperty  MaxXMLSize failed";
    goto LABEL_6;
  }
  v51 = 2084;
  if ( *((_QWORD *)a2 + 3) < 8u )
    v22 = a2;
  else
    v22 = *(const unsigned __int16 **)a2;
  Instance = TSWFileURLFromPath(v22, v63, &v51);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_112;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 102;
    goto LABEL_56;
  }
  v23 = *v4;
  v24 = *(__int64 (__fastcall **)(__int64, VARIANTARG *, _WORD *))(*(_QWORD *)*v4 + 464LL);
  v25 = _bstr_t::_bstr_t((_bstr_t *)&bstrString, v63);
  v53 = *(VARIANTARG *)_variant_t::_variant_t((_variant_t *)&v54, v25);
  Instance = v24(v23, &v53, v49);
  _variant_t::~_variant_t((_variant_t *)&v54);
  _bstr_t::_Free((_bstr_t *)&bstrString);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_112;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 103;
    v8 = "IXmlDOMDocument::LoadXML failed";
    goto LABEL_6;
  }
  if ( !v49[0] )
  {
    v52 = 0;
    v50 = 0;
    bstrString = 0;
    if ( (*(int (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v4 + 480LL))(*v4, &v52) >= 0 )
    {
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v52 + 88LL))(v52, &v50);
      (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v52 + 72LL))(v52, &bstrString);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v26 = bstrString;
      v27 = v50;
      v28 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DdS(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, v29, v28, v27, (__int64)v26);
    }
    Instance = -2147220988;
    SysFreeString(bstrString);
    ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v52);
    goto LABEL_112;
  }
  Instance = SHGetKnownFolderPath(&FOLDERID_Windows, 0, 0, &ppszPath);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_112;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 105;
    v8 = "SHGetKnownFolderPath failed";
    goto LABEL_6;
  }
  std::wstring::assign(v61, ppszPath);
  std::wstring::append(v61, L"\\schemas\\tsworkspace\\tswf.xsd");
  v51 = 2084;
  v30 = (const unsigned __int16 *)v61;
  if ( v62 >= 8 )
    v30 = v61[0];
  Instance = TSWFileURLFromPath(v30, v63, &v51);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_112;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 106;
LABEL_56:
    v8 = "TSWFileURLFromPath failed";
    goto LABEL_6;
  }
  v31 = ppv;
  QueryInterface = ppv->lpVtbl[1].QueryInterface;
  v33 = _bstr_t::_bstr_t((_bstr_t *)&v52, v63);
  v34 = _variant_t::_variant_t((_variant_t *)&v54, v33);
  v35 = *(_OWORD *)v34;
  v36 = (IRecordInfo *)*((_QWORD *)v34 + 2);
  v37 = _bstr_t::_bstr_t((_bstr_t *)&bstrString, L"http://schemas.microsoft.com/ts/2007/05/tswf");
  if ( *(_QWORD *)v37 )
    v38 = **(_QWORD **)v37;
  else
    v38 = 0;
  *(_OWORD *)&v53.vt = v35;
  v53.pRecInfo = v36;
  Instance = ((__int64 (__fastcall *)(struct IDispatch *, __int64, VARIANTARG *))QueryInterface)(v31, v38, &v53);
  _bstr_t::_Free((_bstr_t *)&bstrString);
  _variant_t::~_variant_t((_variant_t *)&v54);
  _bstr_t::_Free((_bstr_t *)&v52);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_112;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 107;
    v8 = "IXMLDOMSchemaCollection::add failed";
    goto LABEL_6;
  }
  v40 = *v4;
  v41 = *(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)*v4 + 624LL);
  v53 = *(VARIANTARG *)_variant_t::_variant_t((_variant_t *)&v54, ppv, v39);
  Instance = v41(v40, &v53);
  _variant_t::~_variant_t((_variant_t *)&v54);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_112;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 108;
    v8 = "IXmlDOMDocument::putref_schemas failed";
    goto LABEL_6;
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v4 + 632LL))(*v4, &v58) )
  {
    bstrString = 0;
    (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v58 + 72LL))(v58, &bstrString);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v42 = bstrString;
      v43 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        109,
        (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        v43,
        (__int64)v42);
    }
    Instance = -2147220988;
    SysFreeString(bstrString);
    goto LABEL_112;
  }
  Instance = CParser::GetFolderNameExists((CParser *)a1, &v50);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_112;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 110;
    v8 = "GetFolderNameExists failed";
    goto LABEL_6;
  }
  if ( v50 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v44 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        111,
        &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        v44,
        -2147220973);
    }
    Instance = -2147220973;
    goto LABEL_112;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    if ( *((_QWORD *)a2 + 3) >= 8u )
      a2 = *(const unsigned __int16 **)a2;
    v45 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      112,
      (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
      v45,
      (__int64)a2);
  }
  Instance = 0;
LABEL_120:
  if ( ppszPath )
    CoTaskMemFree(ppszPath);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v58);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&ppv);
  LOBYTE(v46) = 1;
  std::wstring::_Tidy(v61, v46, 0);
  VariantClear(&pvarg);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800676d8  push    rbp
0x1800676da  push    rsi
0x1800676db  push    rdi
0x1800676dc  push    r12
0x1800676de  push    r13
0x1800676e0  push    r14
0x1800676e2  push    r15
0x1800676e4  lea     rbp, [rsp-1060h]
0x1800676ec  mov     eax, 1160h
0x1800676f1  call    _alloca_probe
0x1800676f6  sub     rsp, rax
0x1800676f9  mov     [rbp+1090h+var_10D8], 0FFFFFFFFFFFFFFFEh
0x180067701  mov     [rsp+1190h+arg_10], rbx
0x180067709  movaps  [rsp+1190h+var_40], xmm6
0x180067711  movaps  [rsp+1190h+var_50], xmm7
0x180067719  mov     rax, cs:__security_cookie
0x180067720  xor     rax, rsp
0x180067723  mov     [rbp+1090h+var_60], rax
0x18006772a  mov     r14, rdx
0x18006772d  mov     r15, rcx
0x180067730  xor     r12d, r12d
0x180067733  mov     [rsp+1190h+var_1158], r12w
0x180067739  lea     rcx, [rbp+1090h+pvarg]; pvarg
0x18006773d  call    cs:__imp_VariantInit
0x180067743  nop
0x180067744  mov     [rsp+1190h+var_1150], r12d
0x180067749  mov     [rbp+1090h+ppszPath], r12
0x18006774d  mov     [rbp+1090h+var_10C0], r12
0x180067751  mov     [rbp+1090h+var_10B8], r12
0x180067755  mov     [rbp+1090h+var_10B8], 7
0x18006775d  mov     [rbp+1090h+var_10C0], r12
0x180067761  mov     word ptr [rbp+1090h+var_10D0], r12w
0x180067766  mov     [rbp+1090h+var_1108], r12
0x18006776a  mov     [rbp+1090h+var_10F8], r12
0x18006776e  mov     [rsp+1190h+var_1154], r12d
0x180067773  lea     rsi, [r15+30h]
0x180067777  mov     [rsp+1190h+ppv], rsi; ppv
0x18006777c  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x180067783  lea     edi, [r12+3]
0x180067788  mov     r8d, edi; dwClsContext
0x18006778b  xor     edx, edx; pUnkOuter
0x18006778d  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x180067794  call    cs:__imp_CoCreateInstance
0x18006779a  mov     ebx, eax
0x18006779c  test    eax, eax
0x18006779e  jns     short loc_180067802
0x1800677a0  lea     rcx, WPP_GLOBAL_Control
0x1800677a7  mov     rax, cs:WPP_GLOBAL_Control
0x1800677ae  cmp     rax, rcx
0x1800677b1  jz      loc_1800680DD
0x1800677b7  test    byte ptr [rax+1Ch], 8
0x1800677bb  jz      loc_1800680DD
0x1800677c1  cmp     byte ptr [rax+19h], 2
0x1800677c5  jb      loc_1800680DD
0x1800677cb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800677d0  lea     edx, [rdi+5Bh]
0x1800677d3  lea     rcx, aCocreateinstan_7; "CoCreateInstance DomDocument60 failed"
0x1800677da  mov     dword ptr [rsp+1190h+var_1168], ebx
0x1800677de  mov     [rsp+1190h+ppv], rcx
0x1800677e3  mov     r9d, eax
0x1800677e6  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x1800677ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800677f4  mov     rcx, [rcx+10h]
0x1800677f8  call    WPP_SF_DsD
0x1800677fd  jmp     loc_1800680DD
0x180067802  lea     rax, [rbp+1090h+var_1108]
0x180067806  mov     [rsp+1190h+ppv], rax; ppv
0x18006780b  lea     r9, _GUID_373984c8_b845_449b_91e7_45ac83036ade; riid
0x180067812  mov     r8d, edi; dwClsContext
0x180067815  xor     edx, edx; pUnkOuter
0x180067817  lea     rcx, _GUID_88d96a07_f192_11d4_a65f_0040963251e5; rclsid
0x18006781e  call    cs:__imp_CoCreateInstance
0x180067824  mov     ebx, eax
0x180067826  test    eax, eax
0x180067828  jns     short loc_18006786B
0x18006782a  lea     rcx, WPP_GLOBAL_Control
0x180067831  mov     rax, cs:WPP_GLOBAL_Control
0x180067838  cmp     rax, rcx
0x18006783b  jz      loc_1800680DD
0x180067841  test    byte ptr [rax+1Ch], 8
0x180067845  jz      loc_1800680DD
0x18006784b  cmp     byte ptr [rax+19h], 2
0x18006784f  jb      loc_1800680DD
0x180067855  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18006785a  mov     edx, 5Fh ; '_'
0x18006785f  lea     rcx, aCocreateinstan; "CoCreateInstance XMLSchemaCache60 faile"...
0x180067866  jmp     loc_1800677DA
0x18006786b  mov     rcx, [rsi]
0x18006786e  mov     rax, [rcx]
0x180067871  xor     edx, edx
0x180067873  mov     rax, [rax+1F8h]
0x18006787a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006787f  mov     ebx, eax
0x180067881  test    eax, eax
0x180067883  jns     short loc_1800678C6
0x180067885  lea     rcx, WPP_GLOBAL_Control
0x18006788c  mov     rax, cs:WPP_GLOBAL_Control
0x180067893  cmp     rax, rcx
0x180067896  jz      loc_1800680DD
0x18006789c  test    byte ptr [rax+1Ch], 8
0x1800678a0  jz      loc_1800680DD
0x1800678a6  cmp     byte ptr [rax+19h], 2
0x1800678aa  jb      loc_1800680DD
0x1800678b0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800678b5  mov     edx, 60h ; '`'
0x1800678ba  lea     rcx, aIxmldomdocumen_4; "IXmlDOMDocument::put_async failed"
0x1800678c1  jmp     loc_1800677DA
0x1800678c6  mov     rcx, [rsi]
0x1800678c9  mov     rax, [rcx]
0x1800678cc  xor     edx, edx
0x1800678ce  mov     rax, [rax+220h]
0x1800678d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800678da  mov     ebx, eax
0x1800678dc  test    eax, eax
0x1800678de  jns     short loc_180067921
0x1800678e0  lea     rcx, WPP_GLOBAL_Control
0x1800678e7  mov     rax, cs:WPP_GLOBAL_Control
0x1800678ee  cmp     rax, rcx
0x1800678f1  jz      loc_1800680DD
0x1800678f7  test    byte ptr [rax+1Ch], 8
0x1800678fb  jz      loc_1800680DD
0x180067901  cmp     byte ptr [rax+19h], 2
0x180067905  jb      loc_1800680DD
0x18006790b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180067910  mov     edx, 61h ; 'a'
0x180067915  lea     rcx, aIxmldomdocumen_6; "IXmlDOMDocument::put_validateOnParse fa"...
0x18006791c  jmp     loc_1800677DA
0x180067921  mov     rcx, [rsi]
0x180067924  mov     rax, [rcx]
0x180067927  xor     edx, edx
0x180067929  mov     rax, [rax+230h]
0x180067930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067935  mov     ebx, eax
0x180067937  test    eax, eax
0x180067939  jns     short loc_18006797C
0x18006793b  lea     rcx, WPP_GLOBAL_Control
0x180067942  mov     rax, cs:WPP_GLOBAL_Control
0x180067949  cmp     rax, rcx
0x18006794c  jz      loc_1800680DD
0x180067952  test    byte ptr [rax+1Ch], 8
0x180067956  jz      loc_1800680DD
0x18006795c  cmp     byte ptr [rax+19h], 2
0x180067960  jb      loc_1800680DD
0x180067966  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18006796b  mov     edx, 62h ; 'b'
0x180067970  lea     rcx, aIxmldomdocumen_3; "IXmlDOMDocument::put_resolveExternals f"...
0x180067977  jmp     loc_1800677DA
0x18006797c  mov     rbx, [rsi]
0x18006797f  mov     rax, [rbx]
0x180067982  mov     rdi, [rax+280h]
0x180067989  mov     r13d, 0Bh
0x18006798f  mov     word ptr [rsp+1190h+var_1120], r13w
0x180067995  mov     word ptr [rsp+1190h+var_1120+8], r12w
0x18006799b  movups  xmm6, [rsp+1190h+var_1120]
0x1800679a0  movsd   xmm7, [rbp+1090h+var_1110]
0x1800679a5  lea     rdx, aUseinlineschem; "UseInlineSchema"
0x1800679ac  lea     rcx, [rsp+1190h+bstrString]; this
0x1800679b1  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800679b6  nop
0x1800679b7  mov     rdx, [rax]
0x1800679ba  test    rdx, rdx
0x1800679bd  jz      short loc_1800679C4
0x1800679bf  mov     rdx, [rdx]
0x1800679c2  jmp     short loc_1800679C7
0x1800679c4  mov     rdx, r12
0x1800679c7  movaps  [rsp+1190h+var_1140], xmm6
0x1800679cc  movsd   [rsp+1190h+var_1130], xmm7
0x1800679d2  lea     r8, [rsp+1190h+var_1140]
0x1800679d7  mov     rcx, rbx
0x1800679da  mov     rax, rdi
0x1800679dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800679e2  mov     ebx, eax
0x1800679e4  lea     rcx, [rsp+1190h+bstrString]; this
0x1800679e9  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800679ee  nop
0x1800679ef  lea     rcx, [rsp+1190h+var_1120]; this
0x1800679f4  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800679f9  test    ebx, ebx
0x1800679fb  jns     short loc_180067A3E
0x1800679fd  lea     rcx, WPP_GLOBAL_Control
0x180067a04  mov     rax, cs:WPP_GLOBAL_Control
0x180067a0b  cmp     rax, rcx
0x180067a0e  jz      loc_1800680DD
0x180067a14  test    byte ptr [rax+1Ch], 8
0x180067a18  jz      loc_1800680DD
0x180067a1e  cmp     byte ptr [rax+19h], 2
0x180067a22  jb      loc_1800680DD
0x180067a28  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180067a2d  mov     edx, 63h ; 'c'
0x180067a32  lea     rcx, aIxmldomdocumen_5; "IXmlDOMDocument::setProperty  UseInline"...
0x180067a39  jmp     loc_1800677DA
0x180067a3e  mov     rbx, [rsi]
0x180067a41  mov     rax, [rbx]
0x180067a44  mov     rdi, [rax+280h]
0x180067a4b  mov     word ptr [rsp+1190h+var_1120], r13w
0x180067a51  mov     word ptr [rsp+1190h+var_1120+8], r12w
0x180067a57  movups  xmm6, [rsp+1190h+var_1120]
0x180067a5c  movsd   xmm7, [rbp+1090h+var_1110]
0x180067a61  lea     rdx, aNormalizeattri; "NormalizeAttributeValues"
0x180067a68  lea     rcx, [rsp+1190h+bstrString]; this
0x180067a6d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180067a72  nop
0x180067a73  mov     rdx, [rax]
0x180067a76  test    rdx, rdx
0x180067a79  jz      short loc_180067A80
0x180067a7b  mov     rdx, [rdx]
0x180067a7e  jmp     short loc_180067A83
0x180067a80  mov     rdx, r12
0x180067a83  movaps  [rsp+1190h+var_1140], xmm6
0x180067a88  movsd   [rsp+1190h+var_1130], xmm7
0x180067a8e  lea     r8, [rsp+1190h+var_1140]
0x180067a93  mov     rcx, rbx
0x180067a96  mov     rax, rdi
0x180067a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067a9e  mov     ebx, eax
0x180067aa0  lea     rcx, [rsp+1190h+bstrString]; this
0x180067aa5  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180067aaa  nop
0x180067aab  lea     rcx, [rsp+1190h+var_1120]; this
0x180067ab0  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180067ab5  test    ebx, ebx
0x180067ab7  jns     short loc_180067AFA
0x180067ab9  lea     rcx, WPP_GLOBAL_Control
0x180067ac0  mov     rax, cs:WPP_GLOBAL_Control
0x180067ac7  cmp     rax, rcx
0x180067aca  jz      loc_1800680DD
0x180067ad0  test    byte ptr [rax+1Ch], 8
0x180067ad4  jz      loc_1800680DD
0x180067ada  cmp     byte ptr [rax+19h], 2
0x180067ade  jb      loc_1800680DD
0x180067ae4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180067ae9  mov     edx, 64h ; 'd'
0x180067aee  lea     rcx, aIxmldomdocumen_0; "IXmlDOMDocument::setProperty NormalizeA"...
0x180067af5  jmp     loc_1800677DA
0x180067afa  lea     rcx, [rbp+1090h+pvarg]
0x180067afe  call    ??4CComVariant@ATL@@QEAAAEAV01@H@Z; ATL::CComVariant::operator=(int)
0x180067b03  mov     rcx, [rsi]
0x180067b06  movups  xmm0, xmmword ptr [rbp+1090h+pvarg]
0x180067b0a  movaps  [rsp+1190h+var_1140], xmm0
0x180067b0f  movsd   xmm1, qword ptr [rbp+1090h+pvarg+10h]
0x180067b14  movsd   [rsp+1190h+var_1130], xmm1
0x180067b1a  mov     rax, [rcx]
0x180067b1d  lea     r8, [rsp+1190h+var_1140]
0x180067b22  lea     rdx, aMaxxmlsize; "MaxXMLSize"
0x180067b29  mov     rax, [rax+280h]
0x180067b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067b35  mov     ebx, eax
0x180067b37  test    eax, eax
0x180067b39  jns     short loc_180067B7C
0x180067b3b  lea     rcx, WPP_GLOBAL_Control
0x180067b42  mov     rax, cs:WPP_GLOBAL_Control
0x180067b49  cmp     rax, rcx
0x180067b4c  jz      loc_1800680DD
0x180067b52  test    byte ptr [rax+1Ch], 8
0x180067b56  jz      loc_1800680DD
0x180067b5c  cmp     byte ptr [rax+19h], 2
0x180067b60  jb      loc_1800680DD
0x180067b66  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180067b6b  mov     edx, 65h ; 'e'
0x180067b70  lea     rcx, aIxmldomdocumen_1; "IXmlDOMDocument::setProperty  MaxXMLSiz"...
0x180067b77  jmp     loc_1800677DA
0x180067b7c  mov     r13d, 824h
0x180067b82  mov     [rsp+1190h+var_1150], r13d
0x180067b87  cmp     qword ptr [r14+18h], 8
0x180067b8c  jb      short loc_180067B93
0x180067b8e  mov     rcx, [r14]
0x180067b91  jmp     short loc_180067B96
0x180067b93  mov     rcx, r14; unsigned __int16 *
0x180067b96  lea     r8, [rsp+1190h+var_1150]; unsigned int *
0x180067b9b  lea     rdx, [rbp+1090h+var_10B0]; unsigned __int16 *
0x180067b9f  call    ?TSWFileURLFromPath@@YAJPEBGPEAGPEAK@Z; TSWFileURLFromPath(ushort const *,ushort *,ulong *)
0x180067ba4  mov     ebx, eax
0x180067ba6  test    eax, eax
0x180067ba8  jns     short loc_180067BEB
0x180067baa  lea     rcx, WPP_GLOBAL_Control
0x180067bb1  mov     rax, cs:WPP_GLOBAL_Control
0x180067bb8  cmp     rax, rcx
0x180067bbb  jz      loc_1800680DD
0x180067bc1  test    byte ptr [rax+1Ch], 8
0x180067bc5  jz      loc_1800680DD
0x180067bcb  cmp     byte ptr [rax+19h], 2
0x180067bcf  jb      loc_1800680DD
0x180067bd5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180067bda  mov     edx, 66h ; 'f'
0x180067bdf  lea     rcx, aTswfileurlfrom; "TSWFileURLFromPath failed"
0x180067be6  jmp     loc_1800677DA
0x180067beb  mov     rdi, [rsi]
0x180067bee  mov     rax, [rdi]
0x180067bf1  mov     rbx, [rax+1D0h]
0x180067bf8  lea     rdx, [rbp+1090h+var_10B0]; unsigned __int16 *
0x180067bfc  lea     rcx, [rsp+1190h+bstrString]; this
0x180067c01  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180067c06  nop
0x180067c07  mov     rdx, rax; struct _bstr_t *
0x180067c0a  lea     rcx, [rsp+1190h+var_1120]; this
0x180067c0f  call    ??0_variant_t@@QEAA@AEBV_bstr_t@@@Z; _variant_t::_variant_t(_bstr_t const &)
0x180067c14  nop
0x180067c15  movups  xmm0, xmmword ptr [rax]
0x180067c18  movaps  [rsp+1190h+var_1140], xmm0
0x180067c1d  movsd   xmm1, qword ptr [rax+10h]
  ... truncated ...
```
