# OSIntegration::DEH::Internal::ActivatableClassHelper::ParseAndSubmitInProcessServer(Microsoft::WRL::ComPtr<IXMLDOMNode>)

- ea: `0x1800436a8`
- end: `0x180043ec3`
- name: `?ParseAndSubmitInProcessServer@ActivatableClassHelper@Internal@DEH@OSIntegration@@AEAAJV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@@Z`
- size: `2075`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::ActivatableClassHelper *this, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180042194`

## callees

- `0x18000b3bc`
- `0x18000b7d0`
- `0x1800129f8`
- `0x18003a300`
- `0x18003f5e0`
- `0x180041c70`
- `0x1800436a8`
- `0x180043ed0`
- `0x180098bf4`
- `0x18009aff4`
- `0x1800a219c`
- `0x1800f0260`
- `0x1800f0700`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004371e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004371e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180043731`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180043731`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004387e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004387e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800437ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800437ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043896`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004399c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043ab3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043baf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043c77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043d70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043dfe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043896`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004399c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043ab3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043baf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043c77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043d70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043dfe`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabledForPackage2` at `0x180043a32`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabledForPackage2` at `0x180043a32`

## string_xrefs

- `0x180043a56`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x180043ea9`: `onecore\admin\appmodel\osim\src\deh\appx\common\package.cpp`
- `0x18004381a`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180043958`: `Common::Xml::GetXMLElementsFromQuery( ActivatableClassConstants::classesXPath, element.Get(), classes.ReleaseAndGetAddressOf())`
- `0x180043ae6`: `Common::Xml::GetValueStringFromQuery( query.GetRawBuffer(nullptr), element.Get(), buffer)`
- `0x180043a6f`: `_sourcePackage->QuirkIsEnabled(QUIRK_REX_ActivationDEHErrorOverwrite, &ignoreErrorsForCompatibility)`
- `0x180043e23`: `RetrieveValue(dllPathQuery, root, dllPath)`
- `0x180043e35`: `CalculateAbsolutePathIfNecessary(dllPath, &isPackageRelativePath)`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::ActivatableClassHelper::ParseAndSubmitInProcessServer(
        OSIntegration::DEH::Internal::ActivatableClassHelper *this,
        __int64 (__fastcall ****a2)(_QWORD, _QWORD, _QWORD))
{
  const WCHAR *v4; // rdi
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // rbx
  unsigned __int16 *v7; // rbx
  __int64 (__fastcall *v8)(unsigned __int16 *, GUID *, unsigned __int16 **); // rdi
  int v9; // eax
  HRESULT v10; // ebx
  unsigned __int16 *v11; // rdi
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v13; // rdx
  OLECHAR *v14; // rbx
  struct IXMLDOMElement **v15; // r9
  int XMLElementFromQuery; // eax
  int *v17; // r9
  wil::details::in1diag3 *v18; // rcx
  __int64 v19; // rdx
  HSTRING v20; // rcx
  WCHAR *v21; // rdi
  HSTRING v22; // rcx
  unsigned __int16 *v23; // rcx
  WCHAR *v24; // rcx
  int v25; // eax
  unsigned __int16 *v26; // rdi
  __int64 (__fastcall *v27)(unsigned __int16 *, GUID *, unsigned __int16 **); // rbx
  int v28; // eax
  struct IXMLDOMNodeList **v29; // r9
  int XMLElementsFromQuery; // eax
  unsigned __int16 *v31; // rcx
  struct IXMLDOMElementVtbl *lpVtbl; // rdi
  int v34; // eax
  __int64 v35; // rbx
  int IsEnabledForPackage2; // eax
  HRESULT v37; // esi
  unsigned __int16 *v38; // rcx
  unsigned __int16 *v39; // rcx
  unsigned __int16 *v40; // rcx
  unsigned __int16 *v41; // rcx
  unsigned __int16 *v42; // rcx
  unsigned __int16 *v43; // rcx
  unsigned __int16 *v44; // rcx
  int v45; // eax
  bool v46; // r14
  unsigned int i; // ebx
  int v48; // eax
  __int64 v49; // r9
  int v50; // eax
  unsigned __int16 *v51; // rcx
  unsigned __int16 *v52; // rcx
  unsigned __int16 *v53; // rcx
  unsigned __int16 *v54; // rcx
  const char *v55; // rax
  __int64 v56; // rdx
  int v57; // [rsp+20h] [rbp-79h]
  char *v58; // [rsp+28h] [rbp-71h]
  unsigned __int16 *v59; // [rsp+30h] [rbp-69h] BYREF
  bool v60; // [rsp+38h] [rbp-61h] BYREF
  unsigned __int16 *v61; // [rsp+40h] [rbp-59h] BYREF
  HSTRING v62; // [rsp+48h] [rbp-51h] BYREF
  HSTRING v63; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int16 *v64; // [rsp+58h] [rbp-41h] BYREF
  int v65; // [rsp+60h] [rbp-39h] BYREF
  struct IXMLDOMElement v66; // [rsp+68h] [rbp-31h] BYREF
  unsigned __int16 **v67; // [rsp+70h] [rbp-29h]
  PCNZWCH sourceString[2]; // [rsp+78h] [rbp-21h] BYREF
  int v69; // [rsp+88h] [rbp-11h]
  __int64 (__fastcall ****v70)(_QWORD, _QWORD, _QWORD); // [rsp+90h] [rbp-9h]
  HSTRING string; // [rsp+98h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp+7h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v70 = a2;
  v66.lpVtbl = 0;
  v62 = 0;
  v65 = 0;
  v4 = off_1802E0670;
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( off_1802E0670[v6] );
  if ( v6 > 0xFFFFFFFF )
  {
    LODWORD(v6) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v4, v6, &hstringHeader, &string);
  v7 = (unsigned __int16 *)*a2;
  v64 = v7;
  if ( v7 )
  {
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v7 + 8LL))(v7);
    v7 = v64;
  }
  v67 = &v64;
  *(_OWORD *)sourceString = 0;
  v69 = 0;
  v59 = 0;
  v8 = **(__int64 (__fastcall ***)(unsigned __int16 *, GUID *, unsigned __int16 **))v7;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
  v9 = v8(v7, &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60, &v59);
  v10 = v9;
  if ( v9 < 0 )
  {
    LODWORD(v58) = v9;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x331,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::RetrieveValue",
      "node.As(&element)",
      v58,
      (int)v59);
    v42 = v59;
    if ( v59 )
    {
      v59 = 0;
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v42 + 16LL))(v42);
    }
    goto LABEL_31;
  }
  v11 = v59;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v14 = (OLECHAR *)StringRawBuffer;
  v63 = 0;
  if ( v11 && StringRawBuffer )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    XMLElementFromQuery = Common::Xml::GetXMLElementFromQuery(v14, v11, (struct IXMLDOMElement *)&v63, v15);
    v10 = XMLElementFromQuery;
    v18 = retaddr;
    if ( XMLElementFromQuery < 0 )
    {
      v19 = 930;
      goto LABEL_15;
    }
    if ( v63 )
    {
      XMLElementFromQuery = Common::Xml::GetValueStringFromElement(
                              (Common::Xml *)v63,
                              (struct IXMLDOMElement *)sourceString,
                              0,
                              v17);
      v10 = XMLElementFromQuery;
      v18 = retaddr;
      if ( XMLElementFromQuery < 0 )
      {
        v19 = 941;
LABEL_15:
        wil::details::in1diag3::_Log_Hr(
          v18,
          (void *)v19,
          (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
          (const char *)(unsigned int)XMLElementFromQuery,
          v57);
      }
    }
  }
  else
  {
    v10 = -2147024809;
  }
  v20 = v63;
  if ( v63 )
  {
    v63 = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v20 + 16LL))(v20);
  }
  if ( v10 < 0 )
  {
    LODWORD(v58) = v10;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x336,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::RetrieveValue",
      "Common::Xml::GetValueStringFromQuery( query.GetRawBuffer(nullptr), element.Get(), buffer)",
      v58,
      (int)v59);
    v39 = v59;
    if ( v59 )
    {
      v59 = 0;
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v39 + 16LL))(v39);
    }
    v24 = (WCHAR *)sourceString[1];
    if ( sourceString[1] )
      goto LABEL_30;
  }
  else
  {
    v21 = (WCHAR *)sourceString[1];
    if ( sourceString[1] )
    {
      v63 = 0;
      do
        ++v5;
      while ( sourceString[1][v5] );
      if ( v5 > 0xFFFFFFFF )
      {
        v10 = -2147024362;
      }
      else
      {
        v10 = WindowsCreateString(sourceString[1], v5, &v63);
        if ( v10 >= 0 )
        {
          v22 = v62;
          v62 = v63;
          WindowsDeleteString(v22);
        }
      }
      if ( v10 >= 0 )
      {
        v40 = v59;
        if ( v59 )
        {
          v59 = 0;
          (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v40 + 16LL))(v40);
        }
        if ( v21 )
          operator delete(v21, v13);
        v10 = 0;
        goto LABEL_31;
      }
    }
    else
    {
      v10 = -2147467261;
    }
    v23 = v59;
    if ( v59 )
    {
      v59 = 0;
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v23 + 16LL))(v23);
    }
    if ( v21 )
    {
      v24 = v21;
LABEL_30:
      operator delete(v24, v13);
    }
  }
LABEL_31:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
  if ( v10 < 0 )
  {
    LODWORD(v58) = v10;
    v55 = "RetrieveValue(dllPathQuery, root, dllPath)";
    v56 = 119;
LABEL_113:
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v56,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseAndSubmitInProcessServer",
      v55,
      v58,
      (int)v59);
LABEL_115:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v62);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
    goto LABEL_41;
  }
  v60 = 0;
  v25 = OSIntegration::DEH::Internal::ActivatableClassHelper::CalculateAbsolutePathIfNecessary(
          this,
          (struct Windows::Internal::String *)&v62,
          &v60);
  v10 = v25;
  if ( v25 < 0 )
  {
    LODWORD(v58) = v25;
    v55 = "CalculateAbsolutePathIfNecessary(dllPath, &isPackageRelativePath)";
    v56 = 122;
    goto LABEL_113;
  }
  v61 = 0;
  v26 = (unsigned __int16 *)*a2;
  v27 = (__int64 (__fastcall *)(unsigned __int16 *, GUID *, unsigned __int16 **))***a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
  v28 = v27(v26, &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60, &v61);
  v10 = v28;
  if ( v28 < 0 )
  {
    LODWORD(v58) = v28;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseAndSubmitInProcessServer",
      "root.As(&element)",
      v58,
      (int)v59);
    v41 = v61;
    if ( v61 )
    {
      v61 = 0;
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v41 + 16LL))(v41);
    }
    if ( v62 )
      WindowsDeleteString(v62);
    goto LABEL_41;
  }
  XMLElementsFromQuery = Common::Xml::GetXMLElementsFromQuery(
                           (OLECHAR *)L"*[local-name()='ActivatableClass']",
                           v61,
                           &v66,
                           v29);
  v10 = XMLElementsFromQuery;
  if ( XMLElementsFromQuery < 0 )
  {
    LODWORD(v58) = XMLElementsFromQuery;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x81,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseAndSubmitInProcessServer",
      "Common::Xml::GetXMLElementsFromQuery( ActivatableClassConstants::classesXPath, element.Get(), classes.ReleaseAndGetAddressOf())",
      v58,
      (int)v59);
    v31 = v61;
    if ( v61 )
    {
      v61 = 0;
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v31 + 16LL))(v31);
    }
    if ( v62 )
      WindowsDeleteString(v62);
    if ( v66.lpVtbl )
      (*((void (__fastcall **)(struct IXMLDOMElementVtbl *))v66.lpVtbl->QueryInterface + 2))(v66.lpVtbl);
    goto LABEL_41;
  }
  lpVtbl = v66.lpVtbl;
  v34 = (*((__int64 (__fastcall **)(struct IXMLDOMElementVtbl *, int *))v66.lpVtbl->QueryInterface + 8))(
          v66.lpVtbl,
          &v65);
  v10 = v34;
  if ( v34 < 0 )
  {
    LODWORD(v58) = v34;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x82,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseAndSubmitInProcessServer",
      "classes->get_length(&listLength)",
      v58,
      (int)v59);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
    goto LABEL_115;
  }
  v35 = *((_QWORD *)this + 4);
  LODWORD(v59) = 0;
  IsEnabledForPackage2 = QuirkIsEnabledForPackage2(*(_QWORD *)(v35 + 224), 0, 393220, *(_QWORD *)(v35 + 424));
  v37 = IsEnabledForPackage2;
  if ( !*(_BYTE *)(v35 + 369) )
  {
    if ( IsEnabledForPackage2 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5A7,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
        (const char *)(unsigned int)IsEnabledForPackage2,
        (int)&v59);
      LODWORD(v58) = v37;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x86,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
        "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseAndSubmitInProcessServer",
        "_sourcePackage->QuirkIsEnabled(QUIRK_REX_ActivationDEHErrorOverwrite, &ignoreErrorsForCompatibility)",
        v58,
        (int)v59);
      v38 = v61;
      if ( v61 )
      {
        v61 = 0;
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v38 + 16LL))(v38);
      }
      if ( v62 )
        WindowsDeleteString(v62);
      if ( lpVtbl )
        (*((void (__fastcall **)(struct IXMLDOMElementVtbl *))lpVtbl->QueryInterface + 2))(lpVtbl);
LABEL_79:
      v10 = v37;
      goto LABEL_41;
    }
    goto LABEL_82;
  }
  if ( IsEnabledForPackage2 >= 0 )
  {
LABEL_82:
    v45 = (int)v59;
    goto LABEL_83;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x59F,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\package.cpp",
    (const char *)(unsigned int)IsEnabledForPackage2,
    (int)&v59);
  v45 = 0;
LABEL_83:
  v46 = v45 != 0;
  for ( i = 0; (int)i < v65; ++i )
  {
    v59 = 0;
    v48 = (*((__int64 (__fastcall **)(struct IXMLDOMElementVtbl *, _QWORD, unsigned __int16 **))lpVtbl->QueryInterface
           + 7))(
            lpVtbl,
            i,
            &v59);
    v37 = v48;
    if ( v48 < 0 )
    {
      LODWORD(v58) = v48;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x8A,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
        "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseAndSubmitInProcessServer",
        "classes->get_item(nodeIndex, &node)",
        v58,
        (int)v59);
      v43 = v59;
      if ( v59 )
      {
        v59 = 0;
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v43 + 16LL))(v43);
      }
      v44 = v61;
      if ( v61 )
      {
        v61 = 0;
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v44 + 16LL))(v44);
      }
      if ( v62 )
        WindowsDeleteString(v62);
      if ( lpVtbl )
        (*((void (__fastcall **)(struct IXMLDOMElementVtbl *))lpVtbl->QueryInterface + 2))(lpVtbl);
      goto LABEL_79;
    }
    v64 = v59;
    if ( v59 )
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v59 + 8LL))(v59);
    LOBYTE(v49) = v60;
    v50 = OSIntegration::DEH::Internal::ActivatableClassHelper::ParseAndSubmitIAMActivatableClass(this, &v64, &v62, v49);
    v37 = v50;
    if ( (!v46 || i == v65 - 1) && v50 < 0 )
    {
      LODWORD(v58) = v50;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x94,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
        "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseAndSubmitInProcessServer",
        "hrParse",
        v58,
        (int)v59);
      v53 = v59;
      if ( v59 )
      {
        v59 = 0;
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v53 + 16LL))(v53);
      }
      v54 = v61;
      if ( v61 )
      {
        v61 = 0;
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v54 + 16LL))(v54);
      }
      if ( v62 )
        WindowsDeleteString(v62);
      if ( lpVtbl )
        (*((void (__fastcall **)(struct IXMLDOMElementVtbl *))lpVtbl->QueryInterface + 2))(lpVtbl);
      goto LABEL_79;
    }
    v51 = v59;
    if ( v59 )
    {
      v59 = 0;
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v51 + 16LL))(v51);
    }
  }
  v52 = v61;
  if ( v61 )
  {
    v61 = 0;
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v52 + 16LL))(v52);
  }
  if ( v62 )
    WindowsDeleteString(v62);
  if ( lpVtbl )
    (*((void (__fastcall **)(struct IXMLDOMElementVtbl *))lpVtbl->QueryInterface + 2))(lpVtbl);
  v10 = 0;
LABEL_41:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a2);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800436a8  mov     [rsp-8+arg_10], rbx
0x1800436ad  push    rbp
0x1800436ae  push    rsi
0x1800436af  push    rdi
0x1800436b0  push    r12
0x1800436b2  push    r13
0x1800436b4  push    r14
0x1800436b6  push    r15
0x1800436b8  lea     rbp, [rsp-27h]
0x1800436bd  sub     rsp, 0C0h
0x1800436c4  mov     rax, cs:__security_cookie
0x1800436cb  xor     rax, rsp
0x1800436ce  mov     [rbp+57h+var_38], rax
0x1800436d2  mov     r12, rdx
0x1800436d5  mov     r15, rcx
0x1800436d8  mov     [rbp+57h+var_60], rdx
0x1800436dc  xor     r13d, r13d
0x1800436df  mov     [rbp+57h+var_88.lpVtbl], r13
0x1800436e3  mov     [rbp+57h+var_A8], r13
0x1800436e7  mov     [rbp+57h+var_90], r13d
0x1800436eb  mov     rdi, cs:off_1802E0670; "*[local-name()='Path']"
0x1800436f2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800436f6  mov     rbx, rsi
0x1800436f9  inc     rbx
0x1800436fc  cmp     [rdi+rbx*2], r13w
0x180043701  jnz     short loc_1800436F9
0x180043703  mov     eax, 0FFFFFFFFh
0x180043708  cmp     rbx, rax
0x18004370b  jbe     short loc_180043724
0x18004370d  mov     ebx, eax
0x18004370f  xor     r9d, r9d; lpArguments
0x180043712  xor     r8d, r8d; nNumberOfArguments
0x180043715  lea     edx, [r9+1]; dwExceptionFlags
0x180043719  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004371e  call    cs:__imp_RaiseException
0x180043724  lea     r9, [rbp+57h+string]; string
0x180043728  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18004372c  mov     edx, ebx; length
0x18004372e  mov     rcx, rdi; sourceString
0x180043731  call    cs:__imp_WindowsCreateStringReference
0x180043737  mov     rbx, [r12]
0x18004373b  mov     [rbp+57h+var_98], rbx
0x18004373f  test    rbx, rbx
0x180043742  jz      short loc_180043757
0x180043744  mov     rax, [rbx]
0x180043747  mov     rcx, rbx
0x18004374a  mov     rax, [rax+8]
0x18004374e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043753  mov     rbx, [rbp+57h+var_98]
0x180043757  lea     rax, [rbp+57h+var_98]
0x18004375b  mov     [rbp+57h+var_80], rax
0x18004375f  xorps   xmm0, xmm0
0x180043762  movups  xmmword ptr [rbp+57h+sourceString], xmm0
0x180043766  mov     [rbp+57h+var_68], r13d
0x18004376a  mov     [rbp+57h+var_C0], r13
0x18004376e  mov     rax, [rbx]
0x180043771  mov     rdi, [rax]
0x180043774  lea     rcx, [rbp+57h+var_C0]
0x180043778  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004377d  lea     r8, [rbp+57h+var_C0]
0x180043781  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x180043788  mov     rcx, rbx
0x18004378b  mov     rax, rdi
0x18004378e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043793  mov     ebx, eax
0x180043795  lea     r14, aOnecoreAdminAp_130; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18004379c  test    eax, eax
0x18004379e  js      loc_180043BBB
0x1800437a4  mov     rdi, [rbp+57h+var_C0]
0x1800437a8  xor     edx, edx; length
0x1800437aa  mov     rcx, [rbp+57h+string]; string
0x1800437ae  call    cs:__imp_WindowsGetStringRawBuffer
0x1800437b4  mov     rbx, rax
0x1800437b7  mov     [rbp+57h+var_A0], r13
0x1800437bb  test    rdi, rdi
0x1800437be  jz      loc_180043C03
0x1800437c4  test    rax, rax
0x1800437c7  jz      loc_180043C03
0x1800437cd  lea     rcx, [rbp+57h+var_A0]
0x1800437d1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800437d6  lea     r8, [rbp+57h+var_A0]; struct IXMLDOMElement *
0x1800437da  mov     rdx, rdi; unsigned __int16 *
0x1800437dd  mov     rcx, rbx; strIn
0x1800437e0  call    ?GetXMLElementFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@PEAPEAU3@@Z; Common::Xml::GetXMLElementFromQuery(ushort const *,IXMLDOMElement *,IXMLDOMElement * *)
0x1800437e5  mov     ebx, eax
0x1800437e7  mov     rcx, [rbp+5Fh]; this
0x1800437eb  test    eax, eax
0x1800437ed  js      short loc_180043815
0x1800437ef  mov     rcx, [rbp+57h+var_A0]; this
0x1800437f3  test    rcx, rcx
0x1800437f6  jz      short loc_18004382A
0x1800437f8  xor     r8d, r8d; struct Common::StringBuffer *
0x1800437fb  lea     rdx, [rbp+57h+sourceString]; struct IXMLDOMElement *
0x1800437ff  call    ?GetValueStringFromElement@Xml@Common@@YAJPEAUIXMLDOMElement@@AEAVStringBuffer@2@PEAH@Z; Common::Xml::GetValueStringFromElement(IXMLDOMElement *,Common::StringBuffer &,int *)
0x180043804  mov     ebx, eax
0x180043806  mov     rcx, [rbp+5Fh]
0x18004380a  test    eax, eax
0x18004380c  jns     short loc_18004382A
0x18004380e  mov     edx, 3ADh
0x180043813  jmp     short loc_18004381A
0x180043815  mov     edx, 3A2h; void *
0x18004381a  lea     r8, aOnecoreAdminAp_141; "onecore\\admin\\appmodel\\common\\xmlto"...
0x180043821  mov     r9d, eax; char *
0x180043824  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180043829  nop
0x18004382a  mov     rcx, [rbp+57h+var_A0]
0x18004382e  test    rcx, rcx
0x180043831  jz      short loc_180043844
0x180043833  mov     [rbp+57h+var_A0], r13
0x180043837  mov     rax, [rcx]
0x18004383a  mov     rax, [rax+10h]
0x18004383e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043843  nop
0x180043844  test    ebx, ebx
0x180043846  js      loc_180043ADE
0x18004384c  mov     rdi, [rbp+57h+sourceString+8]
0x180043850  test    rdi, rdi
0x180043853  jz      loc_180043C9A
0x180043859  mov     [rbp+57h+var_A0], r13
0x18004385d  inc     rsi
0x180043860  cmp     [rdi+rsi*2], r13w
0x180043865  jnz     short loc_18004385D
0x180043867  mov     eax, 0FFFFFFFFh
0x18004386c  cmp     rsi, rax
0x18004386f  ja      loc_180043AD4
0x180043875  mov     edx, esi; length
0x180043877  lea     r8, [rbp+57h+var_A0]; string
0x18004387b  mov     rcx, rdi; sourceString
0x18004387e  call    cs:__imp_WindowsCreateString
0x180043884  mov     ebx, eax
0x180043886  test    eax, eax
0x180043888  js      short loc_18004389C
0x18004388a  mov     rcx, [rbp+57h+var_A8]; string
0x18004388e  mov     rax, [rbp+57h+var_A0]
0x180043892  mov     [rbp+57h+var_A8], rax
0x180043896  call    cs:__imp_WindowsDeleteString
0x18004389c  test    ebx, ebx
0x18004389e  jns     loc_180043B33
0x1800438a4  mov     rcx, [rbp+57h+var_C0]
0x1800438a8  test    rcx, rcx
0x1800438ab  jz      short loc_1800438BE
0x1800438ad  mov     [rbp+57h+var_C0], r13
0x1800438b1  mov     rax, [rcx]
0x1800438b4  mov     rax, [rax+10h]
0x1800438b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800438bd  nop
0x1800438be  test    rdi, rdi
0x1800438c1  jz      short loc_1800438CC
0x1800438c3  mov     rcx, rdi; void *
0x1800438c6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800438cb  nop
0x1800438cc  lea     rcx, [rbp+57h+var_98]
0x1800438d0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800438d5  test    ebx, ebx
0x1800438d7  js      loc_180043E1F
0x1800438dd  mov     [rbp+57h+var_B8], r13b
0x1800438e1  lea     r8, [rbp+57h+var_B8]; bool *
0x1800438e5  lea     rdx, [rbp+57h+var_A8]; struct Windows::Internal::String *
0x1800438e9  mov     rcx, r15; this
0x1800438ec  call    ?CalculateAbsolutePathIfNecessary@ActivatableClassHelper@Internal@DEH@OSIntegration@@AEAAJAEAVString@2Windows@@PEA_N@Z; OSIntegration::DEH::Internal::ActivatableClassHelper::CalculateAbsolutePathIfNecessary(Windows::Internal::String &,bool *)
0x1800438f1  mov     ebx, eax
0x1800438f3  test    eax, eax
0x1800438f5  js      loc_180043E31
0x1800438fb  mov     [rbp+57h+var_B0], r13
0x1800438ff  mov     rdi, [r12]
0x180043903  mov     rax, [rdi]
0x180043906  mov     rbx, [rax]
0x180043909  lea     rcx, [rbp+57h+var_B0]
0x18004390d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180043912  lea     r8, [rbp+57h+var_B0]
0x180043916  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x18004391d  mov     rcx, rdi
0x180043920  mov     rax, rbx
0x180043923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043928  mov     ebx, eax
0x18004392a  test    eax, eax
0x18004392c  js      loc_180043B63
0x180043932  lea     r8, [rbp+57h+var_88]; struct IXMLDOMElement *
0x180043936  mov     rdx, [rbp+57h+var_B0]; unsigned __int16 *
0x18004393a  lea     rcx, aLocalNameActiv; "*[local-name()='ActivatableClass']"
0x180043941  call    ?GetXMLElementsFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@PEAPEAUIXMLDOMNodeList@@@Z; Common::Xml::GetXMLElementsFromQuery(ushort const *,IXMLDOMElement *,IXMLDOMNodeList * *)
0x180043946  mov     ebx, eax
0x180043948  test    eax, eax
0x18004394a  jns     loc_1800439EA
0x180043950  mov     rcx, [rbp+5Fh]; this
0x180043954  mov     dword ptr [rsp+0F0h+var_C8], eax; char *
0x180043958  lea     rax, aCommonXmlGetxm; "Common::Xml::GetXMLElementsFromQuery( A"...
0x18004395f  mov     [rsp+0F0h+var_D0], rax; char *
0x180043964  lea     r9, aOsintegrationD_105; "OSIntegration::DEH::Internal::Activatab"...
0x18004396b  mov     r8, r14; unsigned int
0x18004396e  mov     edx, 81h; void *
0x180043973  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180043978  nop
0x180043979  mov     rcx, [rbp+57h+var_B0]
0x18004397d  test    rcx, rcx
0x180043980  jz      short loc_180043993
0x180043982  mov     [rbp+57h+var_B0], r13
0x180043986  mov     rax, [rcx]
0x180043989  mov     rax, [rax+10h]
0x18004398d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043992  nop
0x180043993  mov     rcx, [rbp+57h+var_A8]; string
0x180043997  test    rcx, rcx
0x18004399a  jz      short loc_1800439A3
0x18004399c  call    cs:__imp_WindowsDeleteString
0x1800439a2  nop
0x1800439a3  mov     rcx, [rbp+57h+var_88.lpVtbl]
0x1800439a7  test    rcx, rcx
0x1800439aa  jz      short loc_1800439B9
0x1800439ac  mov     rax, [rcx]
0x1800439af  mov     rax, [rax+10h]
0x1800439b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800439b8  nop
0x1800439b9  mov     rcx, r12
0x1800439bc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800439c1  mov     eax, ebx
0x1800439c3  mov     rcx, [rbp+57h+var_38]
0x1800439c7  xor     rcx, rsp; StackCookie
0x1800439ca  call    __security_check_cookie
0x1800439cf  mov     rbx, [rsp+0F0h+arg_10]
0x1800439d7  add     rsp, 0C0h
0x1800439de  pop     r15
0x1800439e0  pop     r14
0x1800439e2  pop     r13
0x1800439e4  pop     r12
0x1800439e6  pop     rdi
0x1800439e7  pop     rsi
0x1800439e8  pop     rbp
0x1800439e9  retn
0x1800439ea  mov     rdi, [rbp+57h+var_88.lpVtbl]
0x1800439ee  mov     rax, [rdi]
0x1800439f1  lea     rdx, [rbp+57h+var_90]
0x1800439f5  mov     rcx, rdi
0x1800439f8  mov     rax, [rax+40h]
0x1800439fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043a01  mov     ebx, eax
0x180043a03  test    eax, eax
0x180043a05  js      loc_180043E5B
0x180043a0b  mov     rbx, [r15+20h]
0x180043a0f  mov     dword ptr [rbp+57h+var_C0], r13d
0x180043a13  lea     rax, [rbp+57h+var_C0]
0x180043a17  mov     [rsp+0F0h+var_D0], rax; int
0x180043a1c  mov     r9, [rbx+1A8h]
0x180043a23  xor     edx, edx
0x180043a25  mov     r8d, 60004h
0x180043a2b  mov     rcx, [rbx+0E0h]
0x180043a32  call    cs:__imp_QuirkIsEnabledForPackage2
0x180043a38  mov     esi, eax
0x180043a3a  cmp     [rbx+171h], r13b
0x180043a41  jnz     loc_180043CA4
0x180043a47  test    eax, eax
0x180043a49  jns     loc_180043CB0
0x180043a4f  mov     rcx, [rbp+5Fh]; this
0x180043a53  mov     r9d, eax; char *
0x180043a56  lea     r8, aOnecoreAdminAp_85; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180043a5d  mov     edx, 5A7h; void *
0x180043a62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043a67  mov     rcx, [rbp+5Fh]; this
0x180043a6b  mov     dword ptr [rsp+0F0h+var_C8], esi; char *
0x180043a6f  lea     rax, aSourcepackageQ; "_sourcePackage->QuirkIsEnabled(QUIRK_RE"...
0x180043a76  mov     [rsp+0F0h+var_D0], rax; char *
0x180043a7b  lea     r9, aOsintegrationD_105; "OSIntegration::DEH::Internal::Activatab"...
0x180043a82  mov     r8, r14; unsigned int
0x180043a85  mov     edx, 86h; void *
0x180043a8a  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180043a8f  nop
0x180043a90  mov     rcx, [rbp+57h+var_B0]
0x180043a94  test    rcx, rcx
0x180043a97  jz      short loc_180043AAA
0x180043a99  mov     [rbp+57h+var_B0], r13
0x180043a9d  mov     rax, [rcx]
0x180043aa0  mov     rax, [rax+10h]
0x180043aa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043aa9  nop
0x180043aaa  mov     rcx, [rbp+57h+var_A8]; string
0x180043aae  test    rcx, rcx
0x180043ab1  jz      short loc_180043ABA
0x180043ab3  call    cs:__imp_WindowsDeleteString
0x180043ab9  nop
0x180043aba  test    rdi, rdi
0x180043abd  jz      short loc_180043ACF
0x180043abf  mov     rax, [rdi]
0x180043ac2  mov     rcx, rdi
0x180043ac5  mov     rax, [rax+10h]
0x180043ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043ace  nop
0x180043acf  jmp     loc_180043C93
0x180043ad4  mov     ebx, 80070216h
0x180043ad9  jmp     loc_18004389C
0x180043ade  mov     rcx, [rbp+5Fh]; this
0x180043ae2  mov     dword ptr [rsp+0F0h+var_C8], ebx; char *
0x180043ae6  lea     rax, aCommonXmlGetva; "Common::Xml::GetValueStringFromQuery( q"...
0x180043aed  mov     [rsp+0F0h+var_D0], rax; char *
0x180043af2  lea     r9, aOsintegrationD_226; "OSIntegration::DEH::Internal::Activatab"...
0x180043af9  mov     r8, r14; unsigned int
0x180043afc  mov     edx, 336h; void *
0x180043b01  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180043b06  nop
0x180043b07  mov     rcx, [rbp+57h+var_C0]
0x180043b0b  test    rcx, rcx
  ... truncated ...
```
