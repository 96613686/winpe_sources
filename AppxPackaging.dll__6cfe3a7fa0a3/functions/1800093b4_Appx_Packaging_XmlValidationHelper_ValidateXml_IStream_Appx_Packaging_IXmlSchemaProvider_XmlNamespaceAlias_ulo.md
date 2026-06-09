# Appx::Packaging::XmlValidationHelper::ValidateXml(IStream *,Appx::Packaging::IXmlSchemaProvider *,XmlNamespaceAlias *,ulong,long,ushort const *,IXMLDOMDocument * *,IXMLDOMDocument * *)

- ea: `0x1800093b4`
- end: `0x180009eb0`
- name: `?ValidateXml@XmlValidationHelper@Packaging@Appx@@SAJPEAUIStream@@PEAUIXmlSchemaProvider@23@PEAUXmlNamespaceAlias@@KJPEBGPEAPEAUIXMLDOMDocument@@4@Z`
- size: `2812`
- prototype: `__int64 __fastcall(struct IStream *, struct Appx::Packaging::IXmlSchemaProvider *, struct XmlNamespaceAlias *, unsigned int, unsigned int, const unsigned __int16 *, struct IXMLDOMDocument **, struct IXMLDOMDocument **)`
- caller_count: `5`
- callee_count: `20`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180009f04`
- `0x1800f6880`
- `0x1800f733c`
- `0x1800f8120`
- `0x1800fc8c4`

## callees

- `0x180005eb8`
- `0x180009224`
- `0x1800093b4`
- `0x180009eb8`
- `0x18000b254`
- `0x1800133fc`
- `0x180024c74`
- `0x18003986c`
- `0x18003a344`
- `0x18003a4a0`
- `0x180046da4`
- `0x18006bf44`
- `0x180071f50`
- `0x180096a00`
- `0x1800992c4`
- `0x18009d3d0`
- `0x1800c9aac`
- `0x1800e0c4c`
- `0x1800e56cc`
- `0x180106010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800097bb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800097fb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800097bb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800097fb`
- `OpcServices!__imp_AppxPreprocessXml` at `0x180009532`
- `OpcServices!__imp_AppxPreprocessXml` at `0x180009532`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000988f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800099a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009a1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009a9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009c3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000988f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800099a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009a1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009a9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009c3a`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180009440`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180009440`
- `OLEAUT32!__imp_SysFreeString` at `0x180009972`
- `OLEAUT32!__imp_SysFreeString` at `0x180009e9c`
- `OLEAUT32!__imp_SysFreeString` at `0x180009972`
- `OLEAUT32!__imp_SysFreeString` at `0x180009e9c`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18000983f`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18000983f`

## string_xrefs

- `0x18000995a`: `onecore\printscan\appxpackaging\lib\core\src\xmlvalidationhelper.cpp`
- `0x1800099fe`: `onecore\printscan\appxpackaging\lib\core\src\xmlvalidationhelper.cpp`
- `0x180009a83`: `onecore\printscan\appxpackaging\lib\core\src\xmlvalidationhelper.cpp`
- `0x180009af3`: `onecore\printscan\appxpackaging\lib\core\src\xmlvalidationhelper.cpp`
- `0x180009b15`: `onecore\printscan\appxpackaging\lib\core\src\xmlvalidationhelper.cpp`
- `0x180009c02`: `onecore\printscan\appxpackaging\lib\core\src\xmlvalidationhelper.cpp`
- `0x180009ca6`: `onecore\printscan\appxpackaging\lib\core\src\xmlvalidationhelper.cpp`
- `0x180009cb8`: `onecore\printscan\appxpackaging\lib\core\src\xmlvalidationhelper.cpp`
- `0x180009d27`: `onecore\printscan\appxpackaging\lib\core\src\xmlvalidationhelper.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::XmlValidationHelper::ValidateXml(
        struct IStream *a1,
        struct Appx::Packaging::IXmlSchemaProvider *a2,
        struct XmlNamespaceAlias *a3,
        unsigned int a4,
        unsigned int a5,
        const unsigned __int16 *a6,
        struct IXMLDOMDocument **a7,
        struct IXMLDOMDocument **a8)
{
  struct IXMLDOMDocument2 *v10; // rsi
  HRESULT v11; // eax
  unsigned int v12; // ebx
  __int64 (__fastcall **v13)(struct Appx::Packaging::IXmlSchemaProvider *, struct IStream *); // rax
  unsigned __int64 v14; // r12
  unsigned __int64 v15; // rax
  char *v16; // rbx
  unsigned int i; // ecx
  __int64 v18; // rdx
  _QWORD *v19; // rax
  int v20; // eax
  int v21; // edx
  __int64 v22; // rcx
  int XmlDocument; // edi
  int v24; // eax
  int v25; // eax
  struct IXMLDOMDocument **v26; // r13
  __int64 v27; // rdx
  int v28; // edi
  struct IXMLDOMDocument2 *v29; // r14
  int v30; // eax
  unsigned __int64 v31; // r8
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  unsigned __int64 v33; // r8
  int v34; // eax
  unsigned int v35; // r15d
  HRESULT (__stdcall *get_namespaces)(IXMLDOMDocument2 *, IXMLDOMSchemaCollection **); // rdi
  int v37; // eax
  __int64 v38; // rcx
  unsigned int j; // edi
  _QWORD *v40; // rcx
  int k; // edi
  __int64 v42; // rcx
  unsigned __int64 v43; // rdx
  IErrorInfo *v44; // rcx
  struct IXMLDOMDocument *v45; // rax
  __int64 v46; // rcx
  LPSTREAM v47; // rcx
  int v49; // eax
  __int64 v50; // rdx
  __int64 v51; // rdx
  unsigned __int64 v52; // rdx
  __int64 v53; // rcx
  LPSTREAM v54; // rcx
  unsigned __int64 v55; // rdx
  unsigned __int64 v56; // rdx
  struct IXMLDOMDocument2 v57; // rax
  BSTR v58; // rcx
  __int64 v59; // rdx
  unsigned __int64 v60; // rdx
  unsigned __int64 v61; // rdx
  LPSTREAM v62; // rcx
  __int64 v63; // rdx
  unsigned __int64 v64; // rdx
  __int64 v65; // rdx
  __int64 v66; // r9
  unsigned __int64 v67; // rdx
  unsigned __int64 v68; // rdx
  __int64 v69; // rdx
  int v70; // ecx
  int v71; // [rsp+28h] [rbp-99h]
  LPVOID *p_pv; // [rsp+28h] [rbp-99h]
  LPSTREAM ppstm; // [rsp+48h] [rbp-79h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-71h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-69h] BYREF
  __int64 v76; // [rsp+60h] [rbp-61h] BYREF
  unsigned int v77; // [rsp+68h] [rbp-59h]
  unsigned int v78; // [rsp+6Ch] [rbp-55h]
  __int16 v79; // [rsp+70h] [rbp-51h] BYREF
  _QWORD *v80; // [rsp+78h] [rbp-49h] BYREF
  int v81; // [rsp+80h] [rbp-41h] BYREF
  struct IXMLDOMDocument2 *v82; // [rsp+88h] [rbp-39h] BYREF
  IErrorInfo *pperrinfo; // [rsp+90h] [rbp-31h] BYREF
  __int64 v84; // [rsp+98h] [rbp-29h] BYREF
  LPSTREAM v85; // [rsp+A0h] [rbp-21h]
  __int64 v86; // [rsp+A8h] [rbp-19h]
  _QWORD v87[8]; // [rsp+B8h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+3Fh]
  char v89; // [rsp+108h] [rbp+47h] BYREF
  struct XmlNamespaceAlias *v90; // [rsp+118h] [rbp+57h]
  unsigned int v91; // [rsp+120h] [rbp+5Fh]

  v91 = a4;
  v90 = a3;
  if ( !a1 )
  {
    v63 = 274;
LABEL_112:
    v12 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v63,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xmlvalidationhelper.cpp",
      (const char *)0x80070057LL,
      v71);
    return v12;
  }
  if ( !a2 )
  {
    v63 = 275;
    goto LABEL_112;
  }
  if ( !a3 )
  {
    v63 = 276;
    goto LABEL_112;
  }
  if ( !a4 )
  {
    v63 = 277;
    goto LABEL_112;
  }
  if ( !a7 )
  {
    v63 = 278;
    goto LABEL_112;
  }
  ppstm = 0;
  bstrString = 0;
  v10 = 0;
  v82 = 0;
  pv = 0;
  v78 = 0;
  v77 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppstm);
  v11 = CreateStreamOnHGlobal(0, 1, &ppstm);
  v12 = v11;
  if ( v11 < 0 )
  {
    v65 = 286;
LABEL_122:
    v66 = (unsigned int)v11;
LABEL_124:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v65,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xmlvalidationhelper.cpp",
      (const char *)v66,
      v71);
    goto LABEL_114;
  }
  v13 = *(__int64 (__fastcall ***)(struct Appx::Packaging::IXmlSchemaProvider *, struct IStream *))a2;
  v80 = 0;
  v11 = (*v13)(a2, a1);
  v12 = v11;
  if ( v11 < 0 )
  {
    v65 = 289;
    goto LABEL_122;
  }
  v11 = (*(__int64 (__fastcall **)(struct Appx::Packaging::IXmlSchemaProvider *, _QWORD **))(*(_QWORD *)a2 + 8LL))(
          a2,
          &v80);
  v12 = v11;
  if ( v11 < 0 )
  {
    v65 = 290;
    goto LABEL_122;
  }
  v14 = v80[2];
  if ( v14 >= 0xFFFFFFFF )
  {
    v12 = -2146958848;
    v65 = 292;
    v66 = 2148008448LL;
    goto LABEL_124;
  }
  v15 = 8LL * (unsigned int)v14;
  if ( !is_mul_ok((unsigned int)v14, 8u) )
    v15 = -1;
  v16 = (char *)operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v16 )
  {
    v12 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12A,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xmlvalidationhelper.cpp",
      (const char *)0x8007000ELL,
      v71);
    operator delete(0, v67);
    goto LABEL_114;
  }
  for ( i = 0; i < (unsigned int)v14; *(_QWORD *)&v16[v18] = *v19 )
  {
    v18 = 8LL * i;
    if ( (unsigned __int64)i >= v80[2] )
      v19 = 0;
    else
      v19 = *(_QWORD **)(v18 + *v80);
    ++i;
  }
  p_pv = &pv;
  v20 = AppxPreprocessXml(a1, ppstm, v16, (unsigned int)v14);
  XmlDocument = v20;
  if ( v20 < 0 )
  {
    if ( v20 == -2142175166 )
    {
      XmlDocument = a5;
      if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
        McTemplateU0q_EventWriteTransfer(v22, &EVENT_MANIFEST_INVALID_XML_ENCODING, a5);
      AppxPackagingLog(&EVENT_MANIFEST_INVALID_XML_ENCODING, 0xB0000084, XmlDocument);
      goto LABEL_133;
    }
    if ( v20 == -2142175169 )
    {
      XmlDocument = a5;
      if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
        McTemplateU0dqq_EventWriteTransfer(
          v22,
          (unsigned int)&EVENT_MANIFEST_IGNORABLENAMESPACES_PREFIX_NOT_FOUND,
          a5,
          v78,
          v77);
      AppxPackagingLog(&EVENT_MANIFEST_IGNORABLENAMESPACES_PREFIX_NOT_FOUND, 0xB0000124, XmlDocument, v78, v77);
      goto LABEL_133;
    }
    if ( Appx::Packaging::Xml::IsIXmlParseError((Appx::Packaging::Xml *)(unsigned int)v20, v21)
      || (XmlDocument & 0x1FFF0000) == 0x510000
      || XmlDocument == -2147467259 )
    {
      XmlDocument = a5;
      if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
        McTemplateU0dqqz_EventWriteTransfer(
          v70,
          (unsigned int)&EVENT_MANIFEST_XML_PARSING_ERROR,
          a5,
          v78,
          v77,
          (__int64)pv);
      AppxPackagingLog(
        &EVENT_MANIFEST_XML_PARSING_ERROR,
        0xB000007B,
        XmlDocument,
        v78,
        v77,
        (const unsigned __int16 *)pv);
      goto LABEL_133;
    }
    v69 = 339;
LABEL_132:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v69,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xmlvalidationhelper.cpp",
      (const char *)(unsigned int)XmlDocument,
      (int)p_pv);
LABEL_133:
    operator delete(v16, v68);
    v12 = XmlDocument;
    goto LABEL_114;
  }
  v24 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, 0, 0, 0);
  XmlDocument = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecore\\printscan\\AppxPackaging\\lib\\Core\\src\\StreamHelper.hpp",
      (const char *)(unsigned int)v24,
      (int)&pv);
    v69 = 343;
    goto LABEL_132;
  }
  v25 = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
  XmlDocument = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecore\\printscan\\AppxPackaging\\lib\\Core\\src\\StreamHelper.hpp",
      (const char *)(unsigned int)v25,
      (int)&pv);
    v69 = 344;
    goto LABEL_132;
  }
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&bstrString);
  XmlDocument = Appx::Packaging::XmlValidationHelper::CreateXmlDocument((struct IXMLDOMDocument2 **)&bstrString);
  if ( XmlDocument < 0 )
  {
    v69 = 347;
    goto LABEL_132;
  }
  v26 = a8;
  if ( a8 )
  {
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v82);
    v49 = Appx::Packaging::XmlValidationHelper::CreateXmlDocument(&v82);
    v28 = v49;
    if ( v49 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15E,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xmlvalidationhelper.cpp",
        (const char *)(unsigned int)v49,
        (int)&pv);
      operator delete(v16, v55);
      CoTaskMemFree(pv);
      if ( v82 )
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v82->lpVtbl->Release)(v82);
      if ( bstrString )
        (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
      v54 = ppstm;
      if ( !ppstm )
        return (unsigned int)v28;
      ppstm = 0;
      goto LABEL_78;
    }
    v10 = v82;
  }
  v89 = 0;
  v87[0] = 0;
  v28 = (*(__int64 (__fastcall **)(struct Appx::Packaging::IXmlSchemaProvider *, char *))(*(_QWORD *)a2 + 24LL))(
          a2,
          &v89);
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x163,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xmlvalidationhelper.cpp",
      (const char *)(unsigned int)v28,
      (int)&pv);
    operator delete(v16, v60);
    CoTaskMemFree(pv);
    if ( v10 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v10->lpVtbl->Release)(v10);
    v58 = bstrString;
    if ( !bstrString )
      goto LABEL_92;
    v57.lpVtbl = *(struct IXMLDOMDocument2Vtbl **)bstrString;
    goto LABEL_91;
  }
  if ( !v89 )
  {
    v29 = (struct IXMLDOMDocument2 *)bstrString;
    v28 = Appx::Packaging::XmlValidationHelper::SetSchemas(v80, v27, bstrString);
    if ( v28 < 0 )
    {
      v51 = 365;
      goto LABEL_87;
    }
    goto LABEL_25;
  }
  XmlDocument = (*(__int64 (__fastcall **)(struct Appx::Packaging::IXmlSchemaProvider *, _QWORD *))(*(_QWORD *)a2 + 16LL))(
                  a2,
                  v87);
  if ( XmlDocument < 0 )
  {
    v69 = 360;
    goto LABEL_132;
  }
  v29 = (struct IXMLDOMDocument2 *)bstrString;
  v28 = Appx::Packaging::XmlValidationHelper::SetSchemas(v87[0], v50, bstrString);
  if ( v28 < 0 )
  {
    v51 = 361;
LABEL_87:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v51,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xmlvalidationhelper.cpp",
      (const char *)(unsigned int)v28,
      (int)&pv);
    operator delete(v16, v56);
    CoTaskMemFree(pv);
    if ( v10 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v10->lpVtbl->Release)(v10);
    if ( !v29 )
      goto LABEL_92;
    v57.lpVtbl = v29->lpVtbl;
    v58 = (BSTR)v29;
LABEL_91:
    ((void (__fastcall *)(BSTR))v57.lpVtbl->Release)(v58);
LABEL_92:
    v54 = ppstm;
    if ( !ppstm )
      return (unsigned int)v28;
    ppstm = 0;
LABEL_78:
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v54 + 16LL))(v54);
    return (unsigned int)v28;
  }
LABEL_25:
  v28 = Appx::Packaging::XmlValidationHelper::SetSelectionNamespaces(v29, v90, v91);
  if ( v28 < 0 )
  {
    v51 = 367;
    goto LABEL_87;
  }
  LOWORD(a6) = 0;
  v86 = 0;
  v84 = 13;
  v85 = ppstm;
  v30 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int64 *, const unsigned __int16 **))v29->lpVtbl->load)(
          v29,
          &v84,
          &a6);
  v28 = v30;
  if ( v30 < 0 )
  {
    v51 = 377;
    goto LABEL_87;
  }
  if ( v30 == 1 || !(_WORD)a6 )
  {
    Appx::Packaging::XmlValidationHelper::LogParseError(a1, (unsigned int)&pv);
    operator delete(v16, v61);
    CoTaskMemFree(pv);
    if ( v10 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v10->lpVtbl->Release)(v10);
    v62 = ppstm;
    if ( ppstm )
    {
      ppstm = 0;
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v62 + 16LL))(v62);
    }
    return a5;
  }
  if ( v26 )
  {
    v28 = Appx::Packaging::SetStreamPosition(a1, 0, v31);
    if ( v28 < 0 )
    {
      v51 = 391;
    }
    else
    {
      v79 = 0;
      v86 = 0;
      lpVtbl = v10->lpVtbl;
      v84 = 13;
      v85 = a1;
      v28 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int64 *, __int16 *))lpVtbl->load)(v10, &v84, &v79);
      if ( v28 >= 0 )
      {
        if ( v28 != 1 && (_WORD)a6 )
        {
          v34 = Appx::Packaging::SetStreamPosition(a1, 0, v33);
          v35 = 0;
          XmlDocument = v34;
          if ( v34 >= 0 )
            goto LABEL_35;
          v69 = 410;
          goto LABEL_132;
        }
        bstrString = 0;
        Appx::Packaging::XmlValidationHelper::LogParseError(a1, (unsigned int)&pv);
        operator delete(v16, v64);
        v12 = a5;
LABEL_114:
        CoTaskMemFree(pv);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v82);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&bstrString);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppstm);
        return v12;
      }
      v51 = 399;
    }
    goto LABEL_87;
  }
  v35 = 0;
LABEL_35:
  v76 = 0;
  v81 = 0;
  get_namespaces = v29->lpVtbl->get_namespaces;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
  v28 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int64 *))get_namespaces)(v29, &v76);
  if ( v28 < 0 )
  {
    v59 = 418;
LABEL_95:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v59,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xmlvalidationhelper.cpp",
      (const char *)(unsigned int)v28,
      (int)&pv);
LABEL_70:
    v53 = v76;
    if ( v76 )
    {
      v76 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    }
    operator delete(v16, v52);
    CoTaskMemFree(pv);
    if ( v10 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v10->lpVtbl->Release)(v10);
    if ( v29 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v29->lpVtbl->Release)(v29);
    v54 = ppstm;
    if ( !ppstm )
      return (unsigned int)v28;
    ppstm = 0;
    goto LABEL_78;
  }
  v28 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v76 + 80LL))(v76, &v81);
  if ( v28 < 0 )
  {
    v59 = 419;
    goto LABEL_95;
  }
  while ( (int)v35 < v81 )
  {
    bstrString = 0;
    v37 = (*(__int64 (__fastcall **)(__int64, _QWORD, BSTR *))(*(_QWORD *)v76 + 88LL))(v76, v35, &bstrString);
    v28 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A7,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\xmlvalidationhelper.cpp",
        (const char *)(unsigned int)v37,
        (int)&pv);
      SysFreeString(bstrString);
      goto LABEL_70;
    }
    for ( j = 0; j < (unsigned int)v14; ++j )
    {
      if ( (unsigned __int64)j >= v80[2] )
        v40 = 0;
      else
        v40 = *(_QWORD **)(*v80 + 8LL * j);
      if ( !(unsigned int)_o__wcsicmp(*v40, bstrString) )
        goto LABEL_47;
    }
    if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 4) != 0 )
      McTemplateU0z_EventWriteTransfer(v38, EVENT_MANIFEST_INAPPLICABLE_NAMESPACE_DECLARED, bstrString);
LABEL_47:
    for ( k = 0; k < 6; ++k )
    {
      if ( !(unsigned int)_o__wcsicmp(off_180107210[k], bstrString) )
      {
        if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(v42, EVENT_MANIFEST_PREVIEW_NAMESPACE_DECLARED, bstrString);
        break;
      }
    }
    SysFreeString(bstrString);
    ++v35;
  }
  pperrinfo = 0;
  while ( 1 )
  {
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&pperrinfo);
    GetErrorInfo(0, &pperrinfo);
    v44 = pperrinfo;
    if ( !pperrinfo )
      break;
    pperrinfo = 0;
    ((void (__fastcall *)(IErrorInfo *))v44->lpVtbl->Release)(v44);
  }
  *a7 = (struct IXMLDOMDocument *)v29;
  if ( v26 )
  {
    v45 = (struct IXMLDOMDocument *)v10;
    v10 = 0;
    *v26 = v45;
  }
  v46 = v76;
  if ( v76 )
  {
    v76 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  operator delete(v16, v43);
  CoTaskMemFree(pv);
  if ( v10 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v10->lpVtbl->Release)(v10);
  v47 = ppstm;
  if ( ppstm )
  {
    ppstm = 0;
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v47 + 16LL))(v47);
  }
  return 0;
}

```

## disassembly

```asm
0x1800093b4  mov     rax, rsp
0x1800093b7  mov     [rax+10h], rbx
0x1800093bb  mov     [rax+20h], r9d
0x1800093bf  mov     [rax+18h], r8
0x1800093c3  push    rbp
0x1800093c4  push    rsi
0x1800093c5  push    rdi
0x1800093c6  push    r12
0x1800093c8  push    r13
0x1800093ca  push    r14
0x1800093cc  push    r15
0x1800093ce  lea     rbp, [rax-3Fh]
0x1800093d2  sub     rsp, 0C0h
0x1800093d9  xor     r13d, r13d
0x1800093dc  mov     eax, r9d
0x1800093df  mov     r14, rdx
0x1800093e2  mov     r15, rcx
0x1800093e5  test    rcx, rcx
0x1800093e8  jz      loc_180009BF2
0x1800093ee  test    rdx, rdx
0x1800093f1  jz      loc_180009C68
0x1800093f7  test    r8, r8
0x1800093fa  jz      loc_180009C6F
0x180009400  test    eax, eax
0x180009402  jz      loc_180009C76
0x180009408  cmp     [rbp+37h+arg_30], r13
0x18000940c  jz      loc_180009BF9
0x180009412  lea     rcx, [rbp+37h+ppstm]
0x180009416  mov     [rbp+37h+ppstm], r13
0x18000941a  mov     [rbp+37h+bstrString], r13
0x18000941e  mov     esi, r13d
0x180009421  mov     [rbp+37h+var_70], r13
0x180009425  mov     [rbp+37h+pv], r13
0x180009429  mov     [rbp+37h+var_8C], r13d
0x18000942d  mov     [rbp+37h+var_90], r13d
0x180009431  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180009436  lea     r8, [rbp+37h+ppstm]; ppstm
0x18000943a  xor     ecx, ecx; hGlobal
0x18000943c  lea     edx, [r13+1]; fDeleteOnRelease
0x180009440  call    cs:__imp_CreateStreamOnHGlobal
0x180009447  nop     dword ptr [rax+rax+00h]
0x18000944c  mov     ebx, eax
0x18000944e  test    eax, eax
0x180009450  js      loc_180009C7D
0x180009456  mov     rax, [r14]
0x180009459  mov     rdx, r15
0x18000945c  mov     rcx, r14
0x18000945f  mov     [rbp+37h+var_80], r13
0x180009463  mov     rax, [rax]
0x180009466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000946b  mov     ebx, eax
0x18000946d  test    eax, eax
0x18000946f  js      loc_180009C84
0x180009475  mov     rax, [r14]
0x180009478  lea     rdx, [rbp+37h+var_80]
0x18000947c  mov     rcx, r14
0x18000947f  mov     rax, [rax+8]
0x180009483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009488  mov     ebx, eax
0x18000948a  test    eax, eax
0x18000948c  js      loc_180009C8B
0x180009492  mov     rax, [rbp+37h+var_80]
0x180009496  mov     r12, [rax+10h]
0x18000949a  mov     eax, 0FFFFFFFFh
0x18000949f  cmp     r12, rax
0x1800094a2  jnb     loc_180009C95
0x1800094a8  mov     ecx, r12d
0x1800094ab  lea     eax, [r13+8]
0x1800094af  mul     rcx
0x1800094b2  lea     rcx, [r13-1]
0x1800094b6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800094bd  cmovb   rax, rcx
0x1800094c1  mov     rcx, rax; unsigned __int64
0x1800094c4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800094c9  mov     rbx, rax
0x1800094cc  test    rax, rax
0x1800094cf  jz      loc_180009CB4
0x1800094d5  mov     ecx, r13d
0x1800094d8  test    r12d, r12d
0x1800094db  jz      short loc_18000950A
0x1800094dd  mov     r8, [rbp+37h+var_80]
0x1800094e1  mov     eax, ecx
0x1800094e3  lea     rdx, ds:0[rax*8]
0x1800094eb  cmp     rax, [r8+10h]
0x1800094ef  jnb     loc_180009CDD
0x1800094f5  mov     rax, [r8]
0x1800094f8  mov     rax, [rdx+rax]
0x1800094fc  mov     rax, [rax]
0x1800094ff  inc     ecx
0x180009501  mov     [rbx+rdx], rax
0x180009505  cmp     ecx, r12d
0x180009508  jb      short loc_1800094DD
0x18000950a  mov     rdx, [rbp+37h+ppstm]
0x18000950e  lea     rax, [rbp+37h+var_90]
0x180009512  mov     [rsp+30h], rax
0x180009517  mov     r9d, r12d
0x18000951a  lea     rax, [rbp+37h+var_8C]
0x18000951e  mov     r8, rbx
0x180009521  mov     [rsp+0F0h+var_C8], rax
0x180009526  mov     rcx, r15
0x180009529  lea     rax, [rbp+37h+pv]
0x18000952d  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x180009532  call    cs:__imp_AppxPreprocessXml
0x180009539  nop     dword ptr [rax+rax+00h]
0x18000953e  mov     edi, eax
0x180009540  test    eax, eax
0x180009542  js      loc_180009CE5
0x180009548  mov     rax, [r15]
0x18000954b  mov     rdx, r13
0x18000954e  xor     r9d, r9d
0x180009551  xor     r8d, r8d
0x180009554  mov     rcx, r15
0x180009557  mov     rax, [rax+28h]
0x18000955b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009560  mov     edi, eax
0x180009562  test    eax, eax
0x180009564  js      loc_180009E15
0x18000956a  mov     rcx, [rbp+37h+ppstm]
0x18000956e  mov     rdx, r13
0x180009571  xor     r9d, r9d
0x180009574  xor     r8d, r8d
0x180009577  mov     rax, [rcx]
0x18000957a  mov     rax, [rax+28h]
0x18000957e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009583  mov     edi, eax
0x180009585  test    eax, eax
0x180009587  js      loc_180009E37
0x18000958d  lea     rcx, [rbp+37h+bstrString]
0x180009591  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180009596  lea     rcx, [rbp+37h+bstrString]; struct IXMLDOMDocument2 **
0x18000959a  call    ?CreateXmlDocument@XmlValidationHelper@Packaging@Appx@@SAJPEAPEAUIXMLDOMDocument2@@@Z; Appx::Packaging::XmlValidationHelper::CreateXmlDocument(IXMLDOMDocument2 * *)
0x18000959f  mov     edi, eax
0x1800095a1  test    eax, eax
0x1800095a3  js      loc_180009E59
0x1800095a9  mov     r13, [rbp+37h+arg_38]
0x1800095ad  xor     eax, eax
0x1800095af  test    r13, r13
0x1800095b2  jnz     loc_1800098E6
0x1800095b8  mov     [rbp+37h+arg_0], al
0x1800095bb  lea     rdx, [rbp+37h+arg_0]
0x1800095bf  mov     [rbp+37h+var_40], rax
0x1800095c3  mov     rcx, r14
0x1800095c6  mov     rax, [r14]
0x1800095c9  mov     rax, [rax+18h]
0x1800095cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095d2  mov     edi, eax
0x1800095d4  xor     eax, eax
0x1800095d6  test    edi, edi
0x1800095d8  js      loc_180009B11
0x1800095de  cmp     [rbp+37h+arg_0], al
0x1800095e1  jnz     loc_18000990D
0x1800095e7  mov     r14, [rbp+37h+bstrString]
0x1800095eb  mov     rcx, [rbp+37h+var_80]
0x1800095ef  mov     r8, r14
0x1800095f2  call    ?SetSchemas@XmlValidationHelper@Packaging@Appx@@SAJPEAV?$Array@$$CBUXmlSchemaInfo@@V?$ContainerOperations@$$CBUXmlSchemaInfo@@$$CBU1@@Common@@VNoKey@3@V?$ContainerOperations@VNoKey@Common@@$$CBUXmlSchemaInfo@@@3@V?$ArrayOperations@$$CBUXmlSchemaInfo@@VNoKey@Common@@@3@@Common@@PEBGPEAUIXMLDOMDocument2@@@Z; Appx::Packaging::XmlValidationHelper::SetSchemas(Common::Array<XmlSchemaInfo const,Common::ContainerOperations<XmlSchemaInfo const,XmlSchemaInfo const>,Common::NoKey,Common::ContainerOperations<Common::NoKey,XmlSchemaInfo const>,Common::ArrayOperations<XmlSchemaInfo const,Common::NoKey>> *,ushort const *,IXMLDOMDocument2 *)
0x1800095f7  mov     edi, eax
0x1800095f9  test    eax, eax
0x1800095fb  js      loc_180009BE8
0x180009601  mov     r8d, [rbp+37h+arg_18]; unsigned int
0x180009605  mov     rcx, r14; struct IXMLDOMDocument2 *
0x180009608  mov     rdx, [rbp+37h+arg_10]; struct XmlNamespaceAlias *
0x18000960c  call    ?SetSelectionNamespaces@XmlValidationHelper@Packaging@Appx@@SAJPEAUIXMLDOMDocument2@@PEAUXmlNamespaceAlias@@K@Z; Appx::Packaging::XmlValidationHelper::SetSelectionNamespaces(IXMLDOMDocument2 *,XmlNamespaceAlias *,ulong)
0x180009611  mov     edi, eax
0x180009613  xor     eax, eax
0x180009615  test    edi, edi
0x180009617  js      loc_180009BDE
0x18000961d  mov     word ptr [rbp+37h+arg_28], ax
0x180009621  lea     r8, [rbp+37h+arg_28]
0x180009625  xor     ecx, ecx
0x180009627  lea     rdx, [rbp+37h+var_60]
0x18000962b  xorps   xmm0, xmm0
0x18000962e  mov     [rbp+37h+var_50], rcx
0x180009632  movups  [rbp+37h+var_60], xmm0
0x180009636  lea     eax, [rcx+0Dh]
0x180009639  mov     rcx, r14
0x18000963c  mov     word ptr [rbp+37h+var_60], ax
0x180009640  mov     rax, [rbp+37h+ppstm]
0x180009644  mov     qword ptr [rbp+37h+var_60+8], rax
0x180009648  mov     rax, [r14]
0x18000964b  movups  xmm0, [rbp+37h+var_60]
0x18000964f  mov     rax, [rax+1D0h]
0x180009656  movaps  [rbp+37h+var_60], xmm0
0x18000965a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000965f  mov     edi, eax
0x180009661  test    eax, eax
0x180009663  js      loc_180009B6C
0x180009669  cmp     eax, 1
0x18000966c  jz      loc_180009B80
0x180009672  xor     edi, edi
0x180009674  cmp     word ptr [rbp+37h+arg_28], di
0x180009678  jz      loc_180009B82
0x18000967e  test    r13, r13
0x180009681  jz      loc_18000994E
0x180009687  xor     edx, edx; struct IStream *
0x180009689  mov     rcx, r15; this
0x18000968c  call    ?SetStreamPosition@Packaging@Appx@@YAJPEAUIStream@@_K@Z; Appx::Packaging::SetStreamPosition(IStream *,unsigned __int64)
0x180009691  mov     edi, eax
0x180009693  xor     eax, eax
0x180009695  test    edi, edi
0x180009697  js      loc_180009B07
0x18000969d  lea     ecx, [rax+0Dh]
0x1800096a0  mov     [rbp+37h+var_88], ax
0x1800096a4  xorps   xmm0, xmm0
0x1800096a7  mov     [rbp+37h+var_50], rax
0x1800096ab  mov     rax, [rsi]
0x1800096ae  lea     r8, [rbp+37h+var_88]
0x1800096b2  movups  [rbp+37h+var_60], xmm0
0x1800096b6  mov     word ptr [rbp+37h+var_60], cx
0x1800096ba  lea     rdx, [rbp+37h+var_60]
0x1800096be  mov     qword ptr [rbp+37h+var_60+8], r15
0x1800096c2  mov     rcx, rsi
0x1800096c5  movups  xmm0, [rbp+37h+var_60]
0x1800096c9  mov     rax, [rax+1D0h]
0x1800096d0  movaps  [rbp+37h+var_60], xmm0
0x1800096d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096d9  mov     edi, eax
0x1800096db  xor     eax, eax
0x1800096dd  test    edi, edi
0x1800096df  js      loc_180009A7A
0x1800096e5  cmp     edi, 1
0x1800096e8  jz      loc_180009C18
0x1800096ee  cmp     word ptr [rbp+37h+arg_28], ax
0x1800096f2  jz      loc_180009C18
0x1800096f8  xor     edx, edx; struct IStream *
0x1800096fa  mov     rcx, r15; this
0x1800096fd  call    ?SetStreamPosition@Packaging@Appx@@YAJPEAUIStream@@_K@Z; Appx::Packaging::SetStreamPosition(IStream *,unsigned __int64)
0x180009702  xor     r15d, r15d
0x180009705  mov     edi, eax
0x180009707  test    eax, eax
0x180009709  js      loc_180009E6D
0x18000970f  mov     [rbp+37h+var_98], r15
0x180009713  lea     rcx, [rbp+37h+var_98]
0x180009717  mov     [rbp+37h+var_78], r15d
0x18000971b  mov     rax, [r14]
0x18000971e  mov     rdi, [rax+260h]
0x180009725  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18000972a  lea     rdx, [rbp+37h+var_98]
0x18000972e  mov     rcx, r14
0x180009731  mov     rax, rdi
0x180009734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009739  mov     edi, eax
0x18000973b  test    eax, eax
0x18000973d  js      loc_180009B76
0x180009743  mov     rcx, [rbp+37h+var_98]
0x180009747  lea     rdx, [rbp+37h+var_78]
0x18000974b  mov     rax, [rcx]
0x18000974e  mov     rax, [rax+50h]
0x180009752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009757  mov     edi, eax
0x180009759  test    eax, eax
0x18000975b  js      loc_180009AEA
0x180009761  cmp     r15d, [rbp+37h+var_78]
0x180009765  jge     loc_180009813
0x18000976b  mov     rcx, [rbp+37h+var_98]
0x18000976f  lea     r8, [rbp+37h+bstrString]
0x180009773  mov     [rbp+37h+bstrString], 0
0x18000977b  mov     edx, r15d
0x18000977e  mov     rax, [rcx]
0x180009781  mov     rax, [rax+58h]
0x180009785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000978a  xor     edx, edx
0x18000978c  mov     edi, eax
0x18000978e  test    eax, eax
0x180009790  js      loc_180009956
0x180009796  mov     edi, edx
0x180009798  cmp     edi, r12d
0x18000979b  jnb     short loc_1800097D1
0x18000979d  mov     rax, [rbp+37h+var_80]
0x1800097a1  mov     ecx, edi
0x1800097a3  cmp     rcx, [rax+10h]
0x1800097a7  jnb     loc_180009E77
0x1800097ad  mov     rax, [rax]
0x1800097b0  mov     rcx, [rax+rcx*8]
0x1800097b4  mov     rdx, [rbp+37h+bstrString]
0x1800097b8  mov     rcx, [rcx]
0x1800097bb  call    cs:__imp__o__wcsicmp
0x1800097c2  nop     dword ptr [rax+rax+00h]
0x1800097c7  xor     edx, edx
0x1800097c9  test    eax, eax
0x1800097cb  jz      short loc_1800097DE
0x1800097cd  inc     edi
0x1800097cf  jmp     short loc_180009798
0x1800097d1  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 4
0x1800097d8  jnz     loc_180009A63
0x1800097de  mov     edi, edx
0x1800097e0  cmp     edi, 6
0x1800097e3  jge     loc_180009E98
0x1800097e9  mov     rdx, [rbp+37h+bstrString]
0x1800097ed  lea     rax, off_180107210; "http://schemas.microsoft.com/appx/manif"...
0x1800097f4  movsxd  rcx, edi
0x1800097f7  mov     rcx, [rax+rcx*8]
0x1800097fb  call    cs:__imp__o__wcsicmp
0x180009802  nop     dword ptr [rax+rax+00h]
0x180009807  test    eax, eax
0x180009809  jz      loc_180009E7F
0x18000980f  inc     edi
0x180009811  jmp     short loc_1800097E0
0x180009813  xor     edi, edi
0x180009815  mov     ecx, edi
0x180009817  mov     [rbp+37h+pperrinfo], rcx
  ... truncated ...
```
