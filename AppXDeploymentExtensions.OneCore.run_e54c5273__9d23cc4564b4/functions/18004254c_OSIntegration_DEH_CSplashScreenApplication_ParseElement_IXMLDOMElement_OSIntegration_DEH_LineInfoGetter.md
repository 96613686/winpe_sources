# OSIntegration::DEH::CSplashScreenApplication::_ParseElement(IXMLDOMElement *,OSIntegration::DEH::LineInfoGetter *)

- ea: `0x18004254c`
- end: `0x18004318c`
- name: `?_ParseElement@CSplashScreenApplication@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEAVLineInfoGetter@23@@Z`
- size: `3136`
- prototype: `__int64 __fastcall(OSIntegration::DEH::CSplashScreenApplication *__hidden this, struct IXMLDOMElement *, struct OSIntegration::DEH::LineInfoGetter *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007fd1c`

## callees

- `0x18000afcc`
- `0x18000b3bc`
- `0x18000bd80`
- `0x18000e6e0`
- `0x18000fed0`
- `0x1800138e0`
- `0x18003aec8`
- `0x18004120c`
- `0x18004254c`
- `0x18007dbc0`
- `0x180098bf4`
- `0x1800a219c`
- `0x1800f0260`
- `0x1800f0700`
- `0x180211010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180042646`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180042646`
- `OLEAUT32!__imp_SysFreeString` at `0x1800425dd`
- `OLEAUT32!__imp_SysFreeString` at `0x180042718`
- `OLEAUT32!__imp_SysFreeString` at `0x1800425dd`
- `OLEAUT32!__imp_SysFreeString` at `0x180042718`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180042820`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180042820`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180042baf`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180042baf`

## string_xrefs

- `0x1800425ca`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180042836`: `onecore\admin\appmodel\osim\src\deh\visualelements\splashscreeninstall.cpp`
- `0x18004287b`: `onecore\admin\appmodel\osim\src\deh\visualelements\splashscreeninstall.cpp`
- `0x1800428bb`: `onecore\admin\appmodel\osim\src\deh\visualelements\splashscreeninstall.cpp`
- `0x1800428f3`: `onecore\admin\appmodel\osim\src\deh\visualelements\splashscreeninstall.cpp`
- `0x180042a4c`: `onecore\admin\appmodel\osim\src\deh\visualelements\splashscreeninstall.cpp`
- `0x180042bde`: `onecore\admin\appmodel\osim\src\deh\visualelements\splashscreeninstall.cpp`
- `0x180042d52`: `onecore\admin\appmodel\osim\src\deh\visualelements\splashscreeninstall.cpp`
- `0x180042ec6`: `onecore\admin\appmodel\osim\src\deh\visualelements\splashscreeninstall.cpp`
- `0x180042faa`: `onecore\admin\appmodel\osim\src\deh\visualelements\splashscreeninstall.cpp`
- `0x180042fe9`: `onecore\admin\appmodel\osim\src\deh\visualelements\splashscreeninstall.cpp`
- `0x180043069`: `onecore\admin\appmodel\osim\src\deh\visualelements\splashscreeninstall.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall OSIntegration::DEH::CSplashScreenApplication::_ParseElement(
        OSIntegration::DEH::CSplashScreenApplication *this,
        struct IXMLDOMElement *a2,
        struct OSIntegration::DEH::LineInfoGetter *a3)
{
  OLECHAR *v6; // rbx
  unsigned int v7; // esi
  wil::details::in1diag3 *v8; // rcx
  __int64 v9; // rdx
  unsigned __int64 v10; // r9
  __int64 v11; // rcx
  const OLECHAR *v12; // rax
  __int64 v13; // r8
  HRESULT (__stdcall *selectSingleNode)(IXMLDOMElement *, BSTR, IXMLDOMNode **); // rdi
  int v15; // eax
  __int64 (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v17)(_QWORD, GUID *, LPVOID *); // rsi
  int v18; // eax
  LPVOID v19; // rax
  LPVOID v20; // rcx
  __int64 (__fastcall ***v21)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v22; // rbx
  struct IResourceMap *v23; // rbx
  __int64 v24; // rax
  struct IResourceMap *v25; // rdi
  HRESULT v26; // eax
  unsigned int AttributeValueStringFromQuery; // ebx
  LPVOID v28; // rcx
  int v29; // eax
  LPVOID v30; // rcx
  LPVOID v31; // rcx
  struct IResourceValidator *v32; // rcx
  struct IResourceMap *v33; // rcx
  struct IResourceMap *v34; // rdx
  char v36; // si
  __int64 v37; // rdi
  __int64 v38; // rcx
  unsigned __int64 v39; // rdx
  LPVOID v40; // rcx
  struct IResourceValidator *v41; // rcx
  struct IResourceMap *v42; // rcx
  struct IResourceMap *v43; // rcx
  __int64 v44; // rbx
  __int64 v45; // rcx
  __int64 v46; // r9
  __int64 v47; // rdx
  _BYTE *v48; // rbx
  struct IResourceMap *v49; // rdx
  HRESULT v50; // eax
  __int64 v51; // rdx
  int v52; // esi
  char v53; // di
  __int64 v54; // rbx
  __int64 v55; // rcx
  __int64 v56; // rsi
  __int64 v57; // rcx
  unsigned __int64 v58; // rdx
  LPVOID v59; // rcx
  struct IResourceValidator *v60; // rcx
  struct IResourceMap *v61; // rcx
  struct IResourceMap *v62; // rcx
  int v63; // eax
  char v64; // di
  __int64 v65; // rsi
  __int64 v66; // rcx
  unsigned __int64 v67; // rdx
  LPVOID v68; // rcx
  struct IResourceValidator *v69; // rcx
  struct IResourceMap *v70; // rcx
  struct IResourceMap *v71; // rcx
  int v72; // eax
  WCHAR *v73; // rbx
  unsigned __int64 v74; // rdx
  int v75; // eax
  LPVOID v76; // rcx
  struct IResourceValidator *v77; // rcx
  struct IResourceMap *v78; // rcx
  struct IResourceMap *v79; // rcx
  LPVOID v80; // rcx
  struct IResourceValidator *v81; // rcx
  struct IResourceMap *v82; // rcx
  struct IResourceMap *v83; // rcx
  int *ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  int ppvb; // [rsp+20h] [rbp-E0h]
  LPVOID v87; // [rsp+30h] [rbp-D0h] BYREF
  struct IResourceValidator *v88; // [rsp+38h] [rbp-C8h] BYREF
  struct IResourceMap *v89; // [rsp+40h] [rbp-C0h] BYREF
  struct IResourceMap *v90; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v91; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR pszMore[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v93; // [rsp+68h] [rbp-98h]
  bool v94; // [rsp+70h] [rbp-90h] BYREF
  struct IXMLDOMElement *v95; // [rsp+78h] [rbp-88h] BYREF
  int v96; // [rsp+80h] [rbp-80h]
  __int64 v97; // [rsp+88h] [rbp-78h]
  __int64 (__fastcall ***v98)(_QWORD, GUID *, LPVOID *); // [rsp+90h] [rbp-70h] BYREF
  OLECHAR *v99; // [rsp+98h] [rbp-68h]
  WCHAR pszPathOut[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  v90 = 0;
  v89 = 0;
  v88 = 0;
  v91 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
  v98 = 0;
  v87 = 0;
  v6 = 0;
  if ( !a2 )
  {
    v7 = -2147024809;
    v8 = retaddr;
    v9 = 124;
LABEL_3:
    v10 = v7;
LABEL_4:
    wil::details::in1diag3::_Log_Hr(
      v8,
      (void *)v9,
      (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
      (const char *)v10,
      (int)ppv);
    goto LABEL_21;
  }
  SysFreeString(0);
  v6 = 0;
  v99 = 0;
  v11 = 0x7FFFFFFF;
  v12 = L"./*[local-name()='SplashScreen']";
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v7 = -2147024809;
  v13 = (0x7FFFFFFF - v11) & -(__int64)(v11 != 0);
  if ( v11 )
  {
    if ( (unsigned int)v13 <= 0x3FFFFFFF )
    {
      v6 = SysAllocStringLen(L"./*[local-name()='SplashScreen']", v13);
      v99 = v6;
      v7 = v6 == 0 ? 0x8007000E : 0;
    }
  }
  else
  {
    v7 = -2147024809;
  }
  v8 = retaddr;
  if ( (v7 & 0x80000000) != 0 )
  {
    v9 = 127;
    goto LABEL_3;
  }
  selectSingleNode = a2->lpVtbl->selectSingleNode;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v98);
  v15 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, OLECHAR *, _QWORD))selectSingleNode)(a2, v6, &v98);
  v7 = v15;
  v8 = retaddr;
  if ( v15 < 0 )
  {
    v10 = (unsigned int)v15;
    v9 = 131;
    goto LABEL_4;
  }
  v16 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v98;
  if ( v98 )
  {
    v17 = **v98;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
    v18 = v17(v16, &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60, &v87);
    v7 = v18;
    v8 = retaddr;
    if ( v18 < 0 )
    {
      v10 = (unsigned int)v18;
      v9 = 137;
      goto LABEL_4;
    }
    v19 = v87;
    v87 = 0;
    v91 = v19;
  }
  else
  {
    v91 = 0;
  }
LABEL_21:
  SysFreeString(v6);
  v20 = v87;
  if ( v87 )
  {
    v87 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
  }
  v21 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v98;
  if ( v98 )
  {
    v98 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v21)[2])(v21);
  }
  if ( v7 == 1 )
  {
    *(_BYTE *)this = 0;
  }
  else if ( (v7 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12C,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\visualelements\\splashscreeninstall.cpp",
      (const char *)v7,
      (int)ppv);
LABEL_149:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90);
    return v7;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90);
  v89 = 0;
  v90 = 0;
  v88 = 0;
  v22 = *((_QWORD *)this + 25);
  if ( v22 )
  {
    v23 = *(struct IResourceMap **)(v22 + 16);
    if ( v23 )
      (*(void (__fastcall **)(struct IResourceMap *))(*(_QWORD *)v23 + 8LL))(v23);
    v89 = v23;
    v24 = *((_QWORD *)this + 25);
    v25 = *(struct IResourceMap **)(v24 + 24);
    if ( v25 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v25 + 8LL))(*(_QWORD *)(v24 + 24));
      v23 = v89;
    }
    v90 = v25;
    if ( v23 || v25 )
    {
      v87 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v87);
      v26 = CoCreateInstance(&CLSID_ResourceValidator, 0, 1u, &GUID_7bb324ba_6dfe_4551_945f_935e101ecb96, &v87);
      AttributeValueStringFromQuery = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBE,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\visualelements\\splashscreeninstall.cpp",
          (const char *)(unsigned int)v26,
          (int)ppv);
        v28 = v87;
        if ( v87 )
        {
          v87 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
        }
LABEL_43:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12F,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\visualelements\\splashscreeninstall.cpp",
          (const char *)AttributeValueStringFromQuery,
          ppva);
        v31 = v91;
        if ( v91 )
        {
          v91 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v31 + 16LL))(v31);
        }
        v32 = v88;
        if ( v88 )
        {
          v88 = 0;
          (*(void (__fastcall **)(struct IResourceValidator *))(*(_QWORD *)v32 + 16LL))(v32);
        }
        v33 = v89;
        if ( v89 )
        {
          v89 = 0;
          (*(void (__fastcall **)(struct IResourceMap *))(*(_QWORD *)v33 + 16LL))(v33);
        }
        v34 = v90;
        if ( v90 )
        {
          v90 = 0;
          (*(void (__fastcall **)(struct IResourceMap *))(*(_QWORD *)v34 + 16LL))(v34);
        }
        return AttributeValueStringFromQuery;
      }
      v29 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v87 + 24LL))(v87, 1);
      AttributeValueStringFromQuery = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC0,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\visualelements\\splashscreeninstall.cpp",
          (const char *)(unsigned int)v29,
          (int)ppv);
        v30 = v87;
        if ( v87 )
        {
          v87 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v30 + 16LL))(v30);
        }
        goto LABEL_43;
      }
      v88 = (struct IResourceValidator *)v87;
    }
  }
  if ( *(_BYTE *)this )
  {
    *(_OWORD *)pszMore = 0;
    v93 = 0;
    LODWORD(v87) = 0;
    AttributeValueStringFromQuery = Common::Xml::GetAttributeValueStringFromQuery(
                                      (OLECHAR *)L"./*[local-name()='SplashScreen']",
                                      (const unsigned __int16 *)a2,
                                      L"Image",
                                      (unsigned __int16 *)pszMore,
                                      (struct Common::StringBuffer *)&v87);
    if ( AttributeValueStringFromQuery || (v36 = 1, !(_DWORD)v87) )
      v36 = 0;
    if ( a3 )
    {
      v37 = *((_QWORD *)this + 25);
      v95 = a2;
      Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(&v95);
      v96 = 0;
      v97 = v37;
      v95 = 0;
      v38 = *(_QWORD *)a3;
      *(_QWORD *)a3 = a2;
      if ( v38 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      *((_DWORD *)a3 + 2) = 0;
      *((_QWORD *)a3 + 2) = v37;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v95);
    }
    if ( AttributeValueStringFromQuery == 1 )
    {
      AttributeValueStringFromQuery = -2146958844;
LABEL_64:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x135,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\visualelements\\splashscreeninstall.cpp",
        (const char *)AttributeValueStringFromQuery,
        (int)ppv);
      if ( pszMore[1] )
        operator delete((void *)pszMore[1], v39);
      v40 = v91;
      if ( v91 )
      {
        v91 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v40 + 16LL))(v40);
      }
      v41 = v88;
      if ( v88 )
      {
        v88 = 0;
        (*(void (__fastcall **)(struct IResourceValidator *))(*(_QWORD *)v41 + 16LL))(v41);
      }
      v42 = v89;
      if ( v89 )
      {
        v89 = 0;
        (*(void (__fastcall **)(struct IResourceMap *))(*(_QWORD *)v42 + 16LL))(v42);
      }
      v43 = v90;
      if ( v90 )
      {
        v90 = 0;
        (*(void (__fastcall **)(struct IResourceMap *))(*(_QWORD *)v43 + 16LL))(v43);
      }
      return AttributeValueStringFromQuery;
    }
    if ( (AttributeValueStringFromQuery & 0x80000000) != 0 )
      goto LABEL_64;
    v44 = *(_QWORD *)a3;
    if ( *((_QWORD *)this + 22) != *(_QWORD *)a3 )
    {
      if ( v44 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v44 + 8LL))(*(_QWORD *)a3);
      v45 = *((_QWORD *)this + 22);
      *((_QWORD *)this + 22) = v44;
      if ( v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    }
    *((_DWORD *)this + 46) = *((_DWORD *)a3 + 2);
    *((_QWORD *)this + 24) = *((_QWORD *)a3 + 2);
    if ( !v36 )
    {
      v7 = -2147467259;
      v46 = 2147500037LL;
      v47 = 312;
LABEL_148:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v47,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\visualelements\\splashscreeninstall.cpp",
        (const char *)v46,
        (int)ppv);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)pszMore);
      goto LABEL_149;
    }
    v48 = (char *)this + 80;
    v49 = v90;
    if ( v89 )
      v49 = v89;
    *v48 = 0;
    v50 = OSIntegration::DEH::CSplashScreenApplication::_FullyQualifyResource(
            this,
            v49,
            v88,
            a3,
            (struct Common::StringBuffer *)pszMore,
            (bool *)this + 80);
    v7 = v50;
    if ( v50 < 0 )
    {
      v51 = 266;
LABEL_91:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v51,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\visualelements\\splashscreeninstall.cpp",
        (const char *)(unsigned int)v50,
        ppvb);
      v46 = v7;
      v47 = 315;
      goto LABEL_148;
    }
    if ( !*v48 )
    {
      v50 = PathCchCombine(pszPathOut, 0x104u, *((PCWSTR *)this + 19), pszMore[1]);
      v7 = v50;
      if ( v50 < 0 )
      {
        v51 = 270;
        goto LABEL_91;
      }
      v50 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)pszMore, pszPathOut);
      v7 = v50;
      if ( v50 < 0 )
      {
        v51 = 271;
        goto LABEL_91;
      }
    }
    Common::StringBuffer::SetValue(
      (OSIntegration::DEH::CSplashScreenApplication *)((char *)this + 56),
      pszMore[1],
      (unsigned int)pszMore[0]);
    LODWORD(v87) = 0;
    v52 = Common::Xml::GetAttributeValueStringFromQuery(
            (OLECHAR *)L"./*[local-name()='SplashScreen']",
            (const unsigned __int16 *)a2,
            L"BackgroundColor",
            (unsigned __int16 *)pszMore,
            (struct Common::StringBuffer *)&v87);
    if ( v52 || (v53 = 1, !(_DWORD)v87) )
      v53 = 0;
    v54 = *((_QWORD *)this + 25);
    v95 = a2;
    Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(&v95);
    v96 = 2;
    v97 = v54;
    v95 = 0;
    v55 = *(_QWORD *)a3;
    *(_QWORD *)a3 = a2;
    if ( v55 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    *((_DWORD *)a3 + 2) = 2;
    *((_QWORD *)a3 + 2) = v54;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v95);
    if ( v52 == 1 || v52 < 0 )
    {
      LODWORD(v87) = 0;
      AttributeValueStringFromQuery = Common::Xml::GetAttributeValueStringFromElement(
                                        (Common::Xml *)a2,
                                        (struct IXMLDOMElement *)L"BackgroundColor",
                                        (const unsigned __int16 *)pszMore,
                                        (struct Common::StringBuffer *)&v87,
                                        ppv);
      if ( AttributeValueStringFromQuery || (v53 = 1, !(_DWORD)v87) )
        v53 = 0;
      v56 = *((_QWORD *)this + 25);
      v95 = a2;
      Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(&v95);
      v96 = 3;
      v97 = v56;
      v95 = 0;
      v57 = *(_QWORD *)a3;
      *(_QWORD *)a3 = a2;
      if ( v57 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
      *((_DWORD *)a3 + 2) = 3;
      *((_QWORD *)a3 + 2) = v56;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v95);
      if ( AttributeValueStringFromQuery == 1 )
      {
        AttributeValueStringFromQuery = -2146958844;
LABEL_107:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x142,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\visualelements\\splashscreeninstall.cpp",
          (const char *)AttributeValueStringFromQuery,
          (int)ppv);
        if ( pszMore[1] )
          operator delete((void *)pszMore[1], v58);
        v59 = v91;
        if ( v91 )
        {
          v91 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v59 + 16LL))(v59);
        }
        v60 = v88;
        if ( v88 )
        {
          v88 = 0;
          (*(void (__fastcall **)(struct IResourceValidator *))(*(_QWORD *)v60 + 16LL))(v60);
        }
        v61 = v89;
        if ( v89 )
        {
          v89 = 0;
          (*(void (__fastcall **)(struct IResourceMap *))(*(_QWORD *)v61 + 16LL))(v61);
        }
        v62 = v90;
        if ( v90 )
        {
          v90 = 0;
          (*(void (__fastcall **)(struct IResourceMap *))(*(_QWORD *)v62 + 16LL))(v62);
        }
        return AttributeValueStringFromQuery;
      }
      if ( (AttributeValueStringFromQuery & 0x80000000) != 0 )
        goto LABEL_107;
    }
    if ( !v53 )
    {
      v7 = -2147467259;
      v46 = 2147500037LL;
      v47 = 324;
      goto LABEL_148;
    }
    v63 = Common::StringBuffer::SetValue(
            (OSIntegration::DEH::CSplashScreenApplication *)((char *)this + 32),
            pszMore[1],
            (unsigned int)pszMore[0]);
    v7 = v63;
    if ( v63 < 0 )
    {
      v47 = 325;
LABEL_147:
      v46 = (unsigned int)v63;
      goto LABEL_148;
    }
    LODWORD(v87) = 0;
    AttributeValueStringFromQuery = Common::Xml::GetAttributeValueStringFromElement(
                                      (Common::Xml *)a2,
                                      (struct IXMLDOMElement *)L"DisplayName",
                                      (const unsigned __int16 *)pszMore,
                                      (struct Common::StringBuffer *)&v87,
                                      ppv);
    if ( AttributeValueStringFromQuery || (v64 = 1, !(_DWORD)v87) )
      v64 = 0;
    v65 = *((_QWORD *)this + 25);
    v95 = a2;
    Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(&v95);
    v96 = 1;
    v97 = v65;
    v95 = 0;
    v66 = *(_QWORD *)a3;
    *(_QWORD *)a3 = a2;
    if ( v66 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
    *((_DWORD *)a3 + 2) = 1;
    *((_QWORD *)a3 + 2) = v65;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v95);
    if ( AttributeValueStringFromQuery == 1 )
    {
      AttributeValueStringFromQuery = -2146958844;
LABEL_130:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x147,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\visualelements\\splashscreeninstall.cpp",
        (const char *)AttributeValueStringFromQuery,
        (int)ppv);
      if ( pszMore[1] )
        operator delete((void *)pszMore[1], v67);
      v68 = v91;
      if ( v91 )
      {
        v91 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v68 + 16LL))(v68);
      }
      v69 = v88;
      if ( v88 )
      {
        v88 = 0;
        (*(void (__fastcall **)(struct IResourceValidator *))(*(_QWORD *)v69 + 16LL))(v69);
      }
      v70 = v89;
      if ( v89 )
      {
        v89 = 0;
        (*(void (__fastcall **)(struct IResourceMap *))(*(_QWORD *)v70 + 16LL))(v70);
      }
      v71 = v90;
      if ( v90 )
      {
        v90 = 0;
        (*(void (__fastcall **)(struct IResourceMap *))(*(_QWORD *)v71 + 16LL))(v71);
      }
      return AttributeValueStringFromQuery;
    }
    if ( (AttributeValueStringFromQuery & 0x80000000) != 0 )
      goto LABEL_130;
    if ( !v64 )
    {
      v7 = -2147467259;
      v46 = 2147500037LL;
      v47 = 328;
      goto LABEL_148;
    }
    v72 = OSIntegration::DEH::CSplashScreenApplication::_FullyQualifyResource(
            this,
            v90,
            v88,
            a3,
            (struct Common::StringBuffer *)pszMore,
            &v94);
    v7 = v72;
    if ( v72 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x103,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\visualelements\\splashscreeninstall.cpp",
        (const char *)(unsigned int)v72,
        (int)ppv);
      v46 = v7;
      v47 = 331;
      goto LABEL_148;
    }
    v73 = (WCHAR *)pszMore[1];
    v63 = Common::StringBuffer::SetValue(
            (OSIntegration::DEH::CSplashScreenApplication *)((char *)this + 8),
            pszMore[1],
            (unsigned int)pszMore[0]);
    v7 = v63;
    if ( v63 < 0 )
    {
      v47 = 332;
      goto LABEL_147;
    }
    if ( v73 )
      operator delete(v73, v74);
  }
  v75 = OSIntegration::DEH::CSplashScreenApplication::_ParseOrientationValues(this, a2, a3);
  AttributeValueStringFromQuery = v75;
  if ( v75 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x150,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\visualelements\\splashscreeninstall.cpp",
      (const char *)(unsigned int)v75,
      (int)ppv);
    v76 = v91;
    if ( v91 )
    {
      v91 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v76 + 16LL))(v76);
    }
    v77 = v88;
    if ( v88 )
    {
      v88 = 0;
      (*(void (__fastcall **)(struct IResourceValidator *))(*(_QWORD *)v77 + 16LL))(v77);
    }
    v78 = v89;
    if ( v89 )
    {
      v89 = 0;
      (*(void (__fastcall **)(struct IResourceMap *))(*(_QWORD *)v78 + 16LL))(v78);
    }
    v79 = v90;
    if ( v90 )
    {
      v90 = 0;
      (*(void (__fastcall **)(struct IResourceMap *))(*(_QWORD *)v79 + 16LL))(v79);
    }
    return AttributeValueStringFromQuery;
  }
  v80 = v91;
  if ( v91 )
  {
    v91 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v80 + 16LL))(v80);
  }
  v81 = v88;
  if ( v88 )
  {
    v88 = 0;
    (*(void (__fastcall **)(struct IResourceValidator *))(*(_QWORD *)v81 + 16LL))(v81);
  }
  v82 = v89;
  if ( v89 )
  {
    v89 = 0;
    (*(void (__fastcall **)(struct IResourceMap *))(*(_QWORD *)v82 + 16LL))(v82);
  }
  v83 = v90;
  if ( v90 )
  {
    v90 = 0;
    (*(void (__fastcall **)(struct IResourceMap *))(*(_QWORD *)v83 + 16LL))(v83);
  }
  return 0;
}

```

## disassembly

```asm
0x18004254c  mov     [rsp-8+arg_18], rbx
0x180042551  push    rbp
0x180042552  push    rsi
0x180042553  push    rdi
0x180042554  push    r12
0x180042556  push    r13
0x180042558  push    r14
0x18004255a  push    r15
0x18004255c  lea     rbp, [rsp-1C0h]
0x180042564  sub     rsp, 2C0h
0x18004256b  mov     rax, cs:__security_cookie
0x180042572  xor     rax, rsp
0x180042575  mov     [rbp+1F0h+var_40], rax
0x18004257c  mov     r14, r8
0x18004257f  mov     r12, rdx
0x180042582  mov     r15, rcx
0x180042585  xor     r13d, r13d
0x180042588  mov     [rsp+2F0h+var_2A8], r13
0x18004258d  mov     [rsp+2F0h+var_2B0], r13
0x180042592  mov     [rsp+2F0h+var_2B8], r13
0x180042597  mov     [rsp+2F0h+var_2A0], r13
0x18004259c  lea     rcx, [rsp+2F0h+var_2A0]
0x1800425a1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800425a6  mov     [rbp+1F0h+var_260], r13
0x1800425aa  mov     [rsp+2F0h+var_2C0], r13
0x1800425af  mov     ebx, r13d
0x1800425b2  test    r12, r12
0x1800425b5  jnz     short loc_1800425DB
0x1800425b7  mov     esi, 80070057h
0x1800425bc  mov     rcx, [rbp+1F8h]; this
0x1800425c3  lea     edx, [r13+7Ch]; void *
0x1800425c7  mov     r9d, esi; char *
0x1800425ca  lea     r8, aOnecoreAdminAp_141; "onecore\\admin\\appmodel\\common\\xmlto"...
0x1800425d1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800425d6  jmp     loc_180042715
0x1800425db  xor     ecx, ecx; bstrString
0x1800425dd  call    cs:__imp_SysFreeString
0x1800425e3  mov     rbx, r13
0x1800425e6  mov     [rbp+1F0h+var_258], rbx
0x1800425ea  mov     r9d, 7FFFFFFFh
0x1800425f0  mov     ecx, r9d
0x1800425f3  lea     rax, aLocalNameSplas; "./*[local-name()='SplashScreen']"
0x1800425fa  cmp     [rax], r13w
0x1800425fe  jz      short loc_18004260A
0x180042600  add     rax, 2
0x180042604  sub     rcx, 1
0x180042608  jnz     short loc_1800425FA
0x18004260a  mov     rax, rcx
0x18004260d  neg     rax
0x180042610  sbb     edx, edx
0x180042612  not     edx
0x180042614  mov     esi, 80070057h
0x180042619  and     edx, esi
0x18004261b  mov     rax, rcx
0x18004261e  sub     r9, rcx
0x180042621  neg     rax
0x180042624  sbb     r8, r8
0x180042627  and     r8, r9
0x18004262a  test    rcx, rcx
0x18004262d  jnz     short loc_180042633
0x18004262f  mov     esi, edx
0x180042631  jmp     short loc_180042660
0x180042633  cmp     r8d, 3FFFFFFFh
0x18004263a  ja      short loc_180042660
0x18004263c  mov     edx, r8d; ui
0x18004263f  lea     rcx, aLocalNameSplas; "./*[local-name()='SplashScreen']"
0x180042646  call    cs:__imp_SysAllocStringLen
0x18004264c  mov     rbx, rax
0x18004264f  mov     [rbp+1F0h+var_258], rax
0x180042653  neg     rax
0x180042656  sbb     esi, esi
0x180042658  not     esi
0x18004265a  and     esi, 8007000Eh
0x180042660  mov     rcx, [rbp+1F8h]
0x180042667  test    esi, esi
0x180042669  jns     short loc_180042675
0x18004266b  mov     edx, 7Fh
0x180042670  jmp     loc_1800425C7
0x180042675  mov     rax, [r12]
0x180042679  mov     rdi, [rax+128h]
0x180042680  lea     rcx, [rbp+1F0h+var_260]
0x180042684  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042689  lea     r8, [rbp+1F0h+var_260]
0x18004268d  mov     rdx, rbx
0x180042690  mov     rcx, r12
0x180042693  mov     rax, rdi
0x180042696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004269b  mov     esi, eax
0x18004269d  mov     rcx, [rbp+1F8h]
0x1800426a4  test    eax, eax
0x1800426a6  jns     short loc_1800426B5
0x1800426a8  mov     r9d, eax
0x1800426ab  mov     edx, 83h
0x1800426b0  jmp     loc_1800425CA
0x1800426b5  mov     rdi, [rbp+1F0h+var_260]
0x1800426b9  test    rdi, rdi
0x1800426bc  jz      short loc_180042710
0x1800426be  mov     rax, [rdi]
0x1800426c1  mov     rsi, [rax]
0x1800426c4  lea     rcx, [rsp+2F0h+var_2C0]
0x1800426c9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800426ce  lea     r8, [rsp+2F0h+var_2C0]
0x1800426d3  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x1800426da  mov     rcx, rdi
0x1800426dd  mov     rax, rsi
0x1800426e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800426e5  mov     esi, eax
0x1800426e7  mov     rcx, [rbp+1F8h]
0x1800426ee  test    eax, eax
0x1800426f0  jns     short loc_1800426FF
0x1800426f2  mov     r9d, eax
0x1800426f5  mov     edx, 89h
0x1800426fa  jmp     loc_1800425CA
0x1800426ff  mov     rax, [rsp+2F0h+var_2C0]
0x180042704  mov     [rsp+2F0h+var_2C0], r13
0x180042709  mov     [rsp+2F0h+var_2A0], rax
0x18004270e  jmp     short loc_180042715
0x180042710  mov     [rsp+2F0h+var_2A0], r13
0x180042715  mov     rcx, rbx; bstrString
0x180042718  call    cs:__imp_SysFreeString
0x18004271e  nop
0x18004271f  mov     rcx, [rsp+2F0h+var_2C0]
0x180042724  test    rcx, rcx
0x180042727  jz      short loc_18004273B
0x180042729  mov     [rsp+2F0h+var_2C0], r13
0x18004272e  mov     rax, [rcx]
0x180042731  mov     rax, [rax+10h]
0x180042735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004273a  nop
0x18004273b  mov     rcx, [rbp+1F0h+var_260]
0x18004273f  test    rcx, rcx
0x180042742  jz      short loc_180042755
0x180042744  mov     [rbp+1F0h+var_260], r13
0x180042748  mov     rax, [rcx]
0x18004274b  mov     rax, [rax+10h]
0x18004274f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042754  nop
0x180042755  cmp     esi, 1
0x180042758  jnz     loc_180042869
0x18004275e  mov     [r15], r13b
0x180042761  lea     rcx, [rsp+2F0h+var_2B8]
0x180042766  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004276b  lea     rcx, [rsp+2F0h+var_2B0]
0x180042770  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042775  lea     rcx, [rsp+2F0h+var_2A8]
0x18004277a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004277f  mov     [rsp+2F0h+var_2B0], r13
0x180042784  mov     [rsp+2F0h+var_2A8], r13
0x180042789  mov     [rsp+2F0h+var_2B8], r13
0x18004278e  mov     rbx, [r15+0C8h]
0x180042795  test    rbx, rbx
0x180042798  jz      loc_180042989
0x18004279e  mov     rbx, [rbx+10h]
0x1800427a2  test    rbx, rbx
0x1800427a5  jz      short loc_1800427B7
0x1800427a7  mov     rax, [rbx]
0x1800427aa  mov     rcx, rbx
0x1800427ad  mov     rax, [rax+8]
0x1800427b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800427b6  nop
0x1800427b7  mov     [rsp+2F0h+var_2B0], rbx
0x1800427bc  mov     rax, [r15+0C8h]
0x1800427c3  mov     rdi, [rax+18h]
0x1800427c7  test    rdi, rdi
0x1800427ca  jz      short loc_1800427E0
0x1800427cc  mov     rax, [rdi]
0x1800427cf  mov     rcx, rdi
0x1800427d2  mov     rax, [rax+8]
0x1800427d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800427db  mov     rbx, [rsp+2F0h+var_2B0]
0x1800427e0  mov     [rsp+2F0h+var_2A8], rdi
0x1800427e5  test    rbx, rbx
0x1800427e8  jnz     short loc_1800427F3
0x1800427ea  test    rdi, rdi
0x1800427ed  jz      loc_180042989
0x1800427f3  mov     [rsp+2F0h+var_2C0], r13
0x1800427f8  lea     rcx, [rsp+2F0h+var_2C0]
0x1800427fd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042802  lea     rax, [rsp+2F0h+var_2C0]
0x180042807  mov     [rsp+2F0h+ppv], rax; int
0x18004280c  lea     r9, _GUID_7bb324ba_6dfe_4551_945f_935e101ecb96; riid
0x180042813  xor     edx, edx; pUnkOuter
0x180042815  lea     r8d, [rdx+1]; dwClsContext
0x180042819  lea     rcx, CLSID_ResourceValidator; rclsid
0x180042820  call    cs:__imp_CoCreateInstance
0x180042826  mov     ebx, eax
0x180042828  test    eax, eax
0x18004282a  jns     short loc_180042891
0x18004282c  mov     rcx, [rbp+1F8h]; this
0x180042833  mov     r9d, eax; char *
0x180042836  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18004283d  mov     edx, 0BEh; void *
0x180042842  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042847  nop
0x180042848  mov     rcx, [rsp+2F0h+var_2C0]
0x18004284d  test    rcx, rcx
0x180042850  jz      short loc_180042864
0x180042852  mov     [rsp+2F0h+var_2C0], r13
0x180042857  mov     rax, [rcx]
0x18004285a  mov     rax, [rax+10h]
0x18004285e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042863  nop
0x180042864  jmp     loc_1800428E9
0x180042869  test    esi, esi
0x18004286b  jns     loc_180042761
0x180042871  mov     rcx, [rbp+1F8h]; this
0x180042878  mov     r9d, esi; char *
0x18004287b  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180042882  mov     edx, 12Ch; void *
0x180042887  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004288c  jmp     loc_180043008
0x180042891  mov     rcx, [rsp+2F0h+var_2C0]
0x180042896  mov     rax, [rcx]
0x180042899  mov     edx, 1
0x18004289e  mov     rax, [rax+18h]
0x1800428a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800428a7  mov     ebx, eax
0x1800428a9  test    eax, eax
0x1800428ab  jns     loc_18004297F
0x1800428b1  mov     rcx, [rbp+1F8h]; this
0x1800428b8  mov     r9d, eax; char *
0x1800428bb  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800428c2  mov     edx, 0C0h; void *
0x1800428c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800428cc  nop
0x1800428cd  mov     rcx, [rsp+2F0h+var_2C0]
0x1800428d2  test    rcx, rcx
0x1800428d5  jz      short loc_1800428E9
0x1800428d7  mov     [rsp+2F0h+var_2C0], r13
0x1800428dc  mov     rax, [rcx]
0x1800428df  mov     rax, [rax+10h]
0x1800428e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800428e8  nop
0x1800428e9  mov     rcx, [rbp+1F8h]; this
0x1800428f0  mov     r9d, ebx; char *
0x1800428f3  lea     r8, aOnecoreAdminAp_117; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800428fa  mov     edx, 12Fh; void *
0x1800428ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042904  nop
0x180042905  mov     rcx, [rsp+2F0h+var_2A0]
0x18004290a  test    rcx, rcx
0x18004290d  jz      short loc_180042921
0x18004290f  mov     [rsp+2F0h+var_2A0], r13
0x180042914  mov     rax, [rcx]
0x180042917  mov     rax, [rax+10h]
0x18004291b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042920  nop
0x180042921  mov     rcx, [rsp+2F0h+var_2B8]
0x180042926  test    rcx, rcx
0x180042929  jz      short loc_18004293D
0x18004292b  mov     [rsp+2F0h+var_2B8], r13
0x180042930  mov     rax, [rcx]
0x180042933  mov     rax, [rax+10h]
0x180042937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004293c  nop
0x18004293d  mov     rcx, [rsp+2F0h+var_2B0]
0x180042942  test    rcx, rcx
0x180042945  jz      short loc_180042959
0x180042947  mov     [rsp+2F0h+var_2B0], r13
0x18004294c  mov     rax, [rcx]
0x18004294f  mov     rax, [rax+10h]
0x180042953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042958  nop
0x180042959  mov     rdx, [rsp+2F0h+var_2A8]
0x18004295e  test    rdx, rdx
0x180042961  jz      short loc_180042978
0x180042963  mov     [rsp+2F0h+var_2A8], r13
0x180042968  mov     rcx, [rdx]
0x18004296b  mov     rax, [rcx+10h]
0x18004296f  mov     rcx, rdx
0x180042972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042977  nop
0x180042978  mov     eax, ebx
0x18004297a  jmp     loc_180043162
0x18004297f  mov     rax, [rsp+2F0h+var_2C0]
0x180042984  mov     [rsp+2F0h+var_2B8], rax
0x180042989  cmp     [r15], r13b
0x18004298c  jz      loc_180043047
0x180042992  xorps   xmm0, xmm0
0x180042995  movups  xmmword ptr [rsp+2F0h+pszMore], xmm0
0x18004299a  mov     [rsp+2F0h+var_288], r13d
0x18004299f  mov     dword ptr [rsp+2F0h+var_2C0], r13d
0x1800429a4  lea     rax, [rsp+2F0h+var_2C0]
0x1800429a9  mov     [rsp+2F0h+ppv], rax; int
0x1800429ae  lea     r9, [rsp+2F0h+pszMore]; unsigned __int16 *
0x1800429b3  mov     r8, cs:off_180212068; struct IXMLDOMElement *
0x1800429ba  mov     rdx, r12; unsigned __int16 *
0x1800429bd  lea     rcx, aLocalNameSplas; "./*[local-name()='SplashScreen']"
0x1800429c4  call    ?GetAttributeValueStringFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@0AEAVStringBuffer@2@PEAH@Z; Common::Xml::GetAttributeValueStringFromQuery(ushort const *,IXMLDOMElement *,ushort const *,Common::StringBuffer &,int *)
0x1800429c9  mov     ebx, eax
0x1800429cb  test    eax, eax
0x1800429cd  jnz     short loc_1800429D9
0x1800429cf  cmp     dword ptr [rsp+2F0h+var_2C0], r13d
0x1800429d4  mov     sil, 1
0x1800429d7  jnz     short loc_1800429DC
0x1800429d9  mov     sil, r13b
0x1800429dc  test    r14, r14
0x1800429df  jz      short loc_180042A2E
0x1800429e1  mov     rdi, [r15+0C8h]
0x1800429e8  mov     [rsp+2F0h+var_278], r12
  ... truncated ...
```
