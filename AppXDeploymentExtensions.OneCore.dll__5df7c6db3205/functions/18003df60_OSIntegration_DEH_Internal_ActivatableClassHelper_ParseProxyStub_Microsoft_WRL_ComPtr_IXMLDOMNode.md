# OSIntegration::DEH::Internal::ActivatableClassHelper::ParseProxyStub(Microsoft::WRL::ComPtr<IXMLDOMNode>)

- ea: `0x18003df60`
- end: `0x18003e6c9`
- name: `?ParseProxyStub@ActivatableClassHelper@Internal@DEH@OSIntegration@@AEAAJV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@@Z`
- size: `1897`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003fa2c`

## callees

- `0x18000b3bc`
- `0x18003a300`
- `0x18003aec8`
- `0x18003df60`
- `0x18003e6d0`
- `0x18003e9d0`
- `0x18003f530`
- `0x18003f5e0`
- `0x18003f7e0`
- `0x180060510`
- `0x18007a728`
- `0x18009aff4`
- `0x1800cc418`
- `0x1800f0260`
- `0x1800fc21d`
- `0x1801a7478`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003e013`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003e3bb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003e013`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003e3bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e026`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e3ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e026`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e3ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e15a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e15a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e094`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e094`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e175`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e440`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e450`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e461`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e5cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e5db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e5ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e175`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e440`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e450`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e461`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e5cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e5db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e5ea`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18003e0ef`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18003e0ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e21e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e52c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e59f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e65b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e21e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e52c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e59f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e65b`
- `RPCRT4!UuidFromStringW` at `0x18003e0a1`
- `RPCRT4!UuidFromStringW` at `0x18003e0a1`

## string_xrefs

- `0x18003e31e`: `_sourcePackage->QuirkIsEnabled(QUIRK_REX_ActivationDEHErrorOverwrite, &ignoreErrorsForCompatibility)`
- `0x18003e106`: `StringFromCLSID(clsid, &tempClsid)`
- `0x18003e25f`: `ProxyStubRegistration::FindOrCreate(strValidatedCLSID, dllPath, true , _sourcePackage->GetCollectors(), &proxyStub)`
- `0x18003e62c`: `strValidatedCLSID.Initialize(tempClsid.get())`
- `0x18003e1e4`: `RetrieveValue( dllPathQuery, root, dllPath)`
- `0x18003e29d`: `Common::Xml::GetXMLElementsFromQuery( ActivatableClassConstants::interfacesXPath, element.Get(), &interfaces)`
- `0x18003e05b`: `RetrieveAttribute(clsidQuery, root, strCLSID)`
- `0x18003e0b6`: `UuidFromString(const_cast<RPC_WSTR>(strCLSID.GetRawBuffer(nullptr)), &clsid)`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall OSIntegration::DEH::Internal::ActivatableClassHelper::ParseProxyStub(__int64 a1, __int64 *a2)
{
  HSTRING v4; // rbx
  int v5; // eax
  unsigned int v6; // edi
  const char *v7; // rax
  __int64 v8; // rdx
  const WCHAR *v9; // rsi
  unsigned __int64 v10; // rdi
  __int64 v11; // rcx
  int v12; // eax
  HSTRING v13; // rdi
  unsigned __int16 *StringRawBuffer; // rax
  RPC_STATUS v15; // eax
  HRESULT v16; // eax
  int XMLElementsFromQuery; // esi
  unsigned __int64 v18; // rdx
  HRESULT v19; // esi
  HSTRING v20; // rcx
  __int64 v21; // rcx
  int v22; // ebx
  const char *v23; // rax
  __int64 v24; // rdx
  bool v25; // r8
  struct IXMLDOMNodeList **v26; // r9
  const char *v27; // rax
  __int64 v28; // rdx
  unsigned int i; // r15d
  struct IXMLDOMElementVtbl *lpVtbl; // r14
  __int64 (__fastcall *v31)(struct IXMLDOMElementVtbl *, _QWORD, __int64 *); // rsi
  const WCHAR *v32; // r14
  unsigned __int64 v33; // rsi
  int v34; // eax
  __int64 v35; // rcx
  struct IXMLDOMElementVtbl *v37; // rcx
  unsigned __int16 *v38; // rcx
  struct OSIntegration::DEH::ProxyStubRegistration *v39; // rcx
  char *v40; // [rsp+28h] [rbp-D8h]
  unsigned int v41; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v42; // [rsp+38h] [rbp-C8h] BYREF
  LPOLESTR lpsz; // [rsp+40h] [rbp-C0h] BYREF
  struct IXMLDOMElement v44; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v45; // [rsp+50h] [rbp-B0h] BYREF
  int v46; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v47; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v48; // [rsp+68h] [rbp-98h] BYREF
  struct OSIntegration::DEH::ProxyStubRegistration *v49; // [rsp+70h] [rbp-90h] BYREF
  HSTRING v50; // [rsp+78h] [rbp-88h] BYREF
  HSTRING v51; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v52; // [rsp+88h] [rbp-78h] BYREF
  HSTRING v53; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v54[9]; // [rsp+98h] [rbp-68h] BYREF
  UUID Uuid; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v56; // [rsp+F0h] [rbp-10h] BYREF
  HSTRING string; // [rsp+100h] [rbp+0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+108h] [rbp+8h] BYREF
  HSTRING v59; // [rsp+120h] [rbp+20h] BYREF
  HSTRING_HEADER v60; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v61[32]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v54[8] = a2;
  v49 = 0;
  v4 = 0;
  v50 = 0;
  v51 = 0;
  v47 = 0;
  Uuid = 0;
  v48 = 0;
  v5 = Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(a2, &v48);
  v6 = v5;
  if ( v5 < 0 )
  {
    LODWORD(v40) = v5;
    v7 = "root.As(&element)";
    v8 = 522;
LABEL_9:
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseProxyStub",
      v7,
      v40,
      v41);
LABEL_64:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v47);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v51);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v50);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a2);
    return v6;
  }
  v9 = off_1802E05F8;
  v10 = -1;
  do
    ++v10;
  while ( off_1802E05F8[v10] );
  if ( v10 > 0xFFFFFFFF )
  {
    LODWORD(v10) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v9, v10, &hstringHeader, &string);
  v42 = *a2;
  Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(&v42);
  v12 = OSIntegration::DEH::Internal::ActivatableClassHelper::RetrieveAttribute(v11, &string, &v42, &v51);
  v6 = v12;
  if ( v12 < 0 )
  {
    LODWORD(v40) = v12;
    v7 = "RetrieveAttribute(clsidQuery, root, strCLSID)";
    v8 = 526;
    goto LABEL_9;
  }
  v13 = v51;
  StringRawBuffer = (unsigned __int16 *)WindowsGetStringRawBuffer(v51, 0);
  v15 = UuidFromStringW(StringRawBuffer, &Uuid);
  if ( v15 )
  {
    LODWORD(v40) = v15;
    v6 = wil::details::in1diag5::Return_Win32(
           retaddr,
           (void *)0x211,
           (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
           "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseProxyStub",
           "UuidFromString(const_cast<RPC_WSTR>(strCLSID.GetRawBuffer(nullptr)), &clsid)",
           v40,
           v41);
    goto LABEL_64;
  }
  lpsz = 0;
  v16 = StringFromCLSID(&Uuid, &lpsz);
  XMLElementsFromQuery = v16;
  if ( v16 < 0 )
  {
    LODWORD(v40) = v16;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x214,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseProxyStub",
      "StringFromCLSID(clsid, &tempClsid)",
      v40,
      v41);
LABEL_61:
    if ( lpsz )
      CoTaskMemFree(lpsz);
    v6 = XMLElementsFromQuery;
    goto LABEL_64;
  }
  if ( !lpsz )
  {
    v19 = -2147467261;
LABEL_81:
    LODWORD(v40) = v19;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x215,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseProxyStub",
      "strValidatedCLSID.Initialize(tempClsid.get())",
      v40,
      v41);
    if ( lpsz )
      CoTaskMemFree(lpsz);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v47);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v51);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v50);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a2);
    return (unsigned int)v19;
  }
  v45 = 0;
  v18 = -1;
  do
    ++v18;
  while ( lpsz[v18] );
  if ( v18 > 0xFFFFFFFF )
  {
    v19 = -2147024362;
  }
  else
  {
    v19 = WindowsCreateString(lpsz, v18, &v45);
    if ( v19 >= 0 )
    {
      v20 = v47;
      v47 = v45;
      WindowsDeleteString(v20);
    }
  }
  if ( v19 < 0 )
    goto LABEL_81;
  if ( memcmp_0(&Uuid, qword_1802E1810, 0x10u) )
  {
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v61, off_1802E0670);
    v42 = *a2;
    Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(&v42);
    v22 = OSIntegration::DEH::Internal::ActivatableClassHelper::RetrieveValue(v21, v61, &v42, &v50);
    if ( v22 < 0 )
    {
      v23 = "RetrieveValue( dllPathQuery, root, dllPath)";
      v24 = 538;
LABEL_25:
      LODWORD(v40) = v22;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
        "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseProxyStub",
        v23,
        v40,
        v41);
      if ( lpsz )
        CoTaskMemFree(lpsz);
      v6 = v22;
      goto LABEL_64;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    v22 = OSIntegration::DEH::ProxyStubRegistration::FindOrCreate(
            (const struct Windows::Internal::String *)&v47,
            (const struct Windows::Internal::String *)&v50,
            v25,
            *(struct OSIntegration::DEH::Collectors **)(*(_QWORD *)(a1 + 32) + 808LL),
            &v49);
    if ( v22 < 0 )
    {
      v23 = "ProxyStubRegistration::FindOrCreate(strValidatedCLSID, dllPath, true , _sourcePackage->GetCollectors(), &proxyStub)";
      v24 = 542;
      goto LABEL_25;
    }
    v4 = v50;
  }
  v44.lpVtbl = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
  XMLElementsFromQuery = Common::Xml::GetXMLElementsFromQuery((OLECHAR *)L"*[local-name()='Interface']", v48, &v44, v26);
  if ( XMLElementsFromQuery < 0 )
  {
    v27 = "Common::Xml::GetXMLElementsFromQuery( ActivatableClassConstants::interfacesXPath, element.Get(), &interfaces)";
    v28 = 549;
    goto LABEL_33;
  }
  v46 = 0;
  XMLElementsFromQuery = (*((__int64 (__fastcall **)(struct IXMLDOMElementVtbl *, int *))v44.lpVtbl->QueryInterface + 8))(
                           v44.lpVtbl,
                           &v46);
  if ( XMLElementsFromQuery < 0 )
  {
    v27 = "interfaces->get_length(&listLength)";
    v28 = 552;
    goto LABEL_33;
  }
  LOBYTE(v41) = 0;
  XMLElementsFromQuery = OSIntegration::Package::QuirkIsEnabled(
                           *(OSIntegration::Package **)(a1 + 32),
                           0x60004u,
                           (bool *)&v41);
  if ( XMLElementsFromQuery < 0 )
  {
    v27 = "_sourcePackage->QuirkIsEnabled(QUIRK_REX_ActivationDEHErrorOverwrite, &ignoreErrorsForCompatibility)";
    v28 = 554;
LABEL_33:
    LODWORD(v40) = XMLElementsFromQuery;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseProxyStub",
      v27,
      v40,
      v41);
LABEL_60:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    goto LABEL_61;
  }
  for ( i = 0; (int)i < v46; ++i )
  {
    v42 = 0;
    lpVtbl = v44.lpVtbl;
    v31 = (__int64 (__fastcall *)(struct IXMLDOMElementVtbl *, _QWORD, __int64 *))*((_QWORD *)v44.lpVtbl->QueryInterface
                                                                                  + 7);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    XMLElementsFromQuery = v31(lpVtbl, i, &v42);
    if ( XMLElementsFromQuery < 0 )
    {
      LODWORD(v40) = XMLElementsFromQuery;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x22E,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
        "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseProxyStub",
        "interfaces->get_item(nodeIndex, &node)",
        v40,
        v41);
      goto LABEL_59;
    }
    v45 = 0;
    v53 = 0;
    v52 = 0;
    v56 = 0;
    v32 = off_1802E0608;
    v33 = -1;
    do
      ++v33;
    while ( off_1802E0608[v33] );
    if ( v33 > 0xFFFFFFFF )
    {
      LODWORD(v33) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(v32, v33, &v60, &v59);
    v54[0] = a1;
    v54[1] = &v59;
    v54[2] = &v42;
    v54[3] = &v53;
    v54[4] = &v56;
    v54[5] = &v52;
    v54[6] = &v45;
    v54[7] = &v47;
    v34 = lambda_4faec5f9e1de0d244e1a7c86b61b9810_::operator()(v54);
    XMLElementsFromQuery = v34;
    if ( (!(_BYTE)v41 || i == v46 - 1) && v34 < 0 )
    {
      LODWORD(v40) = v34;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x24F,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
        "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseProxyStub",
        "hrParse",
        v40,
        v41);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v52);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v53);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v45);
LABEL_59:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      goto LABEL_60;
    }
    if ( v52 )
      WindowsDeleteString(v52);
    if ( v53 )
      WindowsDeleteString(v53);
    if ( v45 )
      WindowsDeleteString(v45);
    v35 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
  }
  v37 = v44.lpVtbl;
  if ( v44.lpVtbl )
  {
    v44.lpVtbl = 0;
    (*((void (__fastcall **)(struct IXMLDOMElementVtbl *))v37->QueryInterface + 2))(v37);
  }
  if ( lpsz )
    CoTaskMemFree(lpsz);
  v38 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v38 + 16LL))(v38);
  }
  if ( v47 )
    WindowsDeleteString(v47);
  if ( v13 )
    WindowsDeleteString(v13);
  if ( v4 )
    WindowsDeleteString(v4);
  v39 = v49;
  if ( v49 )
  {
    v49 = 0;
    (*(void (__fastcall **)(struct OSIntegration::DEH::ProxyStubRegistration *))(*(_QWORD *)v39 + 16LL))(v39);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a2);
  return 0;
}

```

## disassembly

```asm
0x18003df60  mov     [rsp-8+arg_10], rbx
0x18003df65  push    rbp
0x18003df66  push    rsi
0x18003df67  push    rdi
0x18003df68  push    r12
0x18003df6a  push    r13
0x18003df6c  push    r14
0x18003df6e  push    r15
0x18003df70  lea     rbp, [rsp-70h]
0x18003df75  sub     rsp, 170h
0x18003df7c  mov     rax, cs:__security_cookie
0x18003df83  xor     rax, rsp
0x18003df86  mov     [rbp+0A0h+var_40], rax
0x18003df8a  mov     r12, rdx
0x18003df8d  mov     r13, rcx
0x18003df90  mov     [rbp+0A0h+var_C8], rdx
0x18003df94  xor     r14d, r14d
0x18003df97  mov     [rsp+1A0h+var_130], r14
0x18003df9c  mov     ebx, r14d
0x18003df9f  mov     [rsp+1A0h+var_128], rbx
0x18003dfa4  mov     [rbp+0A0h+var_120], r14
0x18003dfa8  mov     [rsp+1A0h+var_140], r14
0x18003dfad  xorps   xmm0, xmm0
0x18003dfb0  movups  xmmword ptr [rbp+0A0h+Uuid.Data1], xmm0
0x18003dfb4  mov     [rsp+1A0h+var_138], r14
0x18003dfb9  lea     rdx, [rsp+1A0h+var_138]
0x18003dfbe  mov     rcx, r12
0x18003dfc1  call    ??$As@UIXMLDOMElement@@@?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIXMLDOMElement@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IXMLDOMElement>>)
0x18003dfc6  mov     edi, eax
0x18003dfc8  test    eax, eax
0x18003dfca  jns     short loc_18003DFE1
0x18003dfcc  mov     dword ptr [rsp+1A0h+var_178], eax
0x18003dfd0  lea     rax, aRootAsElement; "root.As(&element)"
0x18003dfd7  mov     edx, 20Ah
0x18003dfdc  jmp     loc_18003E067
0x18003dfe1  mov     rsi, cs:off_1802E05F8; "ClassId"
0x18003dfe8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003dfec  inc     rdi
0x18003dfef  cmp     [rsi+rdi*2], r14w
0x18003dff4  jnz     short loc_18003DFEC
0x18003dff6  mov     r15d, 0FFFFFFFFh
0x18003dffc  cmp     rdi, r15
0x18003dfff  jbe     short loc_18003E019
0x18003e001  mov     edi, r15d
0x18003e004  xor     r9d, r9d; lpArguments
0x18003e007  xor     r8d, r8d; nNumberOfArguments
0x18003e00a  lea     edx, [r9+1]; dwExceptionFlags
0x18003e00e  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003e013  call    cs:__imp_RaiseException
0x18003e019  lea     r9, [rbp+0A0h+string]; string
0x18003e01d  lea     r8, [rbp+0A0h+hstringHeader]; hstringHeader
0x18003e021  mov     edx, edi; length
0x18003e023  mov     rcx, rsi; sourceString
0x18003e026  call    cs:__imp_WindowsCreateStringReference
0x18003e02c  mov     rax, [r12]
0x18003e030  mov     [rsp+1A0h+var_168], rax
0x18003e035  lea     rcx, [rsp+1A0h+var_168]
0x18003e03a  call    ?InternalAddRef@?$ComPtr@VExtensionCatalogCollector@DEH@OSIntegration@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(void)
0x18003e03f  lea     r9, [rbp+0A0h+var_120]
0x18003e043  lea     r8, [rsp+1A0h+var_168]
0x18003e048  lea     rdx, [rbp+0A0h+string]
0x18003e04c  call    ?RetrieveAttribute@ActivatableClassHelper@Internal@DEH@OSIntegration@@AEAAJAEBVString@2Windows@@V?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@AEAV526@@Z; OSIntegration::DEH::Internal::ActivatableClassHelper::RetrieveAttribute(Windows::Internal::String const &,Microsoft::WRL::ComPtr<IXMLDOMNode>,Windows::Internal::String &)
0x18003e051  mov     edi, eax
0x18003e053  test    eax, eax
0x18003e055  jns     short loc_18003E08B
0x18003e057  mov     dword ptr [rsp+1A0h+var_178], eax; char *
0x18003e05b  lea     rax, aRetrieveattrib; "RetrieveAttribute(clsidQuery, root, str"...
0x18003e062  mov     edx, 20Eh; void *
0x18003e067  lea     r8, aOnecoreAdminAp_130; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003e06e  lea     r9, aOsintegrationD_90; "OSIntegration::DEH::Internal::Activatab"...
0x18003e075  mov     [rsp+1A0h+var_180], rax; char *
0x18003e07a  mov     rcx, [rbp+0A8h]; this
0x18003e081  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003e086  jmp     loc_18003E534
0x18003e08b  xor     edx, edx; length
0x18003e08d  mov     rdi, [rbp+0A0h+var_120]
0x18003e091  mov     rcx, rdi; string
0x18003e094  call    cs:__imp_WindowsGetStringRawBuffer
0x18003e09a  lea     rdx, [rbp+0A0h+Uuid]; Uuid
0x18003e09e  mov     rcx, rax; StringUuid
0x18003e0a1  call    cs:__imp_UuidFromStringW
0x18003e0a7  test    eax, eax
0x18003e0a9  jz      short loc_18003E0E1
0x18003e0ab  mov     rcx, [rbp+0A8h]; this
0x18003e0b2  mov     dword ptr [rsp+1A0h+var_178], eax; char *
0x18003e0b6  lea     rax, aUuidfromstring_0; "UuidFromString(const_cast<RPC_WSTR>(str"...
0x18003e0bd  mov     [rsp+1A0h+var_180], rax; char *
0x18003e0c2  lea     r9, aOsintegrationD_90; "OSIntegration::DEH::Internal::Activatab"...
0x18003e0c9  lea     r8, aOnecoreAdminAp_130; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003e0d0  mov     edx, 211h; void *
0x18003e0d5  call    ?Return_Win32@in1diag5@details@wil@@YAJPEAXIPEBD11K@Z; wil::details::in1diag5::Return_Win32(void *,uint,char const *,char const *,char const *,ulong)
0x18003e0da  mov     edi, eax
0x18003e0dc  jmp     loc_18003E534
0x18003e0e1  mov     [rsp+1A0h+lpsz], r14
0x18003e0e6  lea     rdx, [rsp+1A0h+lpsz]; lplpsz
0x18003e0eb  lea     rcx, [rbp+0A0h+Uuid]; rclsid
0x18003e0ef  call    cs:__imp_StringFromCLSID
0x18003e0f5  mov     esi, eax
0x18003e0f7  test    eax, eax
0x18003e0f9  jns     short loc_18003E12F
0x18003e0fb  mov     rcx, [rbp+0A8h]; this
0x18003e102  mov     dword ptr [rsp+1A0h+var_178], eax; char *
0x18003e106  lea     rax, aStringfromclsi; "StringFromCLSID(clsid, &tempClsid)"
0x18003e10d  mov     [rsp+1A0h+var_180], rax; char *
0x18003e112  lea     r9, aOsintegrationD_90; "OSIntegration::DEH::Internal::Activatab"...
0x18003e119  lea     r8, aOnecoreAdminAp_130; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003e120  mov     edx, 214h; void *
0x18003e125  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003e12a  jmp     loc_18003E522
0x18003e12f  mov     rcx, [rsp+1A0h+lpsz]; sourceString
0x18003e134  test    rcx, rcx
0x18003e137  jz      loc_18003E61C
0x18003e13d  mov     [rsp+1A0h+var_150], r14
0x18003e142  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003e146  inc     rdx; length
0x18003e149  cmp     [rcx+rdx*2], r14w
0x18003e14e  jnz     short loc_18003E146
0x18003e150  cmp     rdx, r15
0x18003e153  ja      short loc_18003E17D
0x18003e155  lea     r8, [rsp+1A0h+var_150]; string
0x18003e15a  call    cs:__imp_WindowsCreateString
0x18003e160  mov     esi, eax
0x18003e162  test    eax, eax
0x18003e164  js      short loc_18003E182
0x18003e166  mov     rcx, [rsp+1A0h+var_140]; string
0x18003e16b  mov     rax, [rsp+1A0h+var_150]
0x18003e170  mov     [rsp+1A0h+var_140], rax
0x18003e175  call    cs:__imp_WindowsDeleteString
0x18003e17b  jmp     short loc_18003E182
0x18003e17d  mov     esi, 80070216h
0x18003e182  test    esi, esi
0x18003e184  js      loc_18003E621
0x18003e18a  mov     r8d, 10h; Size
0x18003e190  lea     rdx, qword_1802E1810; Buf2
0x18003e197  lea     rcx, [rbp+0A0h+Uuid]; Buf1
0x18003e19b  call    memcmp_0
0x18003e1a0  test    eax, eax
0x18003e1a2  jz      loc_18003E272
0x18003e1a8  mov     rdx, cs:off_1802E0670; unsigned __int16 *
0x18003e1af  lea     rcx, [rbp+0A0h+var_60]; this
0x18003e1b3  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18003e1b8  mov     rax, [r12]
0x18003e1bc  mov     [rsp+1A0h+var_168], rax
0x18003e1c1  lea     rcx, [rsp+1A0h+var_168]
0x18003e1c6  call    ?InternalAddRef@?$ComPtr@VExtensionCatalogCollector@DEH@OSIntegration@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(void)
0x18003e1cb  lea     r9, [rsp+1A0h+var_128]
0x18003e1d0  lea     r8, [rsp+1A0h+var_168]
0x18003e1d5  lea     rdx, [rbp+0A0h+var_60]
0x18003e1d9  call    ?RetrieveValue@ActivatableClassHelper@Internal@DEH@OSIntegration@@AEAAJAEBVString@2Windows@@V?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@AEAV526@@Z; OSIntegration::DEH::Internal::ActivatableClassHelper::RetrieveValue(Windows::Internal::String const &,Microsoft::WRL::ComPtr<IXMLDOMNode>,Windows::Internal::String &)
0x18003e1de  mov     ebx, eax
0x18003e1e0  test    eax, eax
0x18003e1e2  jns     short loc_18003E22B
0x18003e1e4  lea     rax, aRetrievevalueD; "RetrieveValue( dllPathQuery, root, dllP"...
0x18003e1eb  mov     edx, 21Ah; void *
0x18003e1f0  mov     dword ptr [rsp+1A0h+var_178], ebx; char *
0x18003e1f4  lea     r8, aOnecoreAdminAp_130; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003e1fb  lea     r9, aOsintegrationD_90; "OSIntegration::DEH::Internal::Activatab"...
0x18003e202  mov     [rsp+1A0h+var_180], rax; char *
0x18003e207  mov     rcx, [rbp+0A8h]; this
0x18003e20e  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003e213  nop
0x18003e214  mov     rcx, [rsp+1A0h+lpsz]; pv
0x18003e219  test    rcx, rcx
0x18003e21c  jz      short loc_18003E224
0x18003e21e  call    cs:__imp_CoTaskMemFree
0x18003e224  mov     edi, ebx
0x18003e226  jmp     loc_18003E534
0x18003e22b  lea     rcx, [rsp+1A0h+var_130]
0x18003e230  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003e235  mov     r9, [r13+20h]
0x18003e239  lea     rax, [rsp+1A0h+var_130]
0x18003e23e  mov     [rsp+1A0h+var_180], rax; struct OSIntegration::DEH::ProxyStubRegistration **
0x18003e243  mov     r9, [r9+328h]; struct OSIntegration::DEH::Collectors *
0x18003e24a  lea     rdx, [rsp+1A0h+var_128]; struct Windows::Internal::String *
0x18003e24f  lea     rcx, [rsp+1A0h+var_140]; struct Windows::Internal::String *
0x18003e254  call    ?FindOrCreate@ProxyStubRegistration@DEH@OSIntegration@@SAJAEBVString@Internal@Windows@@0_NPEAVCollectors@23@PEAPEAU123@@Z; OSIntegration::DEH::ProxyStubRegistration::FindOrCreate(Windows::Internal::String const &,Windows::Internal::String const &,bool,OSIntegration::DEH::Collectors *,OSIntegration::DEH::ProxyStubRegistration * *)
0x18003e259  mov     ebx, eax
0x18003e25b  test    eax, eax
0x18003e25d  jns     short loc_18003E26D
0x18003e25f  lea     rax, aProxystubregis_2; "ProxyStubRegistration::FindOrCreate(str"...
0x18003e266  mov     edx, 21Eh
0x18003e26b  jmp     short loc_18003E1F0
0x18003e26d  mov     rbx, [rsp+1A0h+var_128]
0x18003e272  mov     [rsp+1A0h+var_158.lpVtbl], r14
0x18003e277  lea     rcx, [rsp+1A0h+var_158]
0x18003e27c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003e281  lea     r8, [rsp+1A0h+var_158]; struct IXMLDOMElement *
0x18003e286  mov     rdx, [rsp+1A0h+var_138]; unsigned __int16 *
0x18003e28b  lea     rcx, aLocalNameInter; "*[local-name()='Interface']"
0x18003e292  call    ?GetXMLElementsFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@PEAPEAUIXMLDOMNodeList@@@Z; Common::Xml::GetXMLElementsFromQuery(ushort const *,IXMLDOMElement *,IXMLDOMNodeList * *)
0x18003e297  mov     esi, eax
0x18003e299  test    eax, eax
0x18003e29b  jns     short loc_18003E2D1
0x18003e29d  lea     rax, aCommonXmlGetxm_1; "Common::Xml::GetXMLElementsFromQuery( A"...
0x18003e2a4  mov     edx, 225h; void *
0x18003e2a9  mov     dword ptr [rsp+1A0h+var_178], esi; char *
0x18003e2ad  mov     rcx, [rbp+0A8h]; this
0x18003e2b4  mov     [rsp+1A0h+var_180], rax; char *
0x18003e2b9  lea     r9, aOsintegrationD_90; "OSIntegration::DEH::Internal::Activatab"...
0x18003e2c0  lea     r8, aOnecoreAdminAp_130; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003e2c7  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003e2cc  jmp     loc_18003E517
0x18003e2d1  mov     [rsp+1A0h+var_148], r14d
0x18003e2d6  mov     rcx, [rsp+1A0h+var_158.lpVtbl]
0x18003e2db  mov     rax, [rcx]
0x18003e2de  lea     rdx, [rsp+1A0h+var_148]
0x18003e2e3  mov     rax, [rax+40h]
0x18003e2e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e2ec  mov     esi, eax
0x18003e2ee  test    eax, eax
0x18003e2f0  jns     short loc_18003E300
0x18003e2f2  lea     rax, aInterfacesGetL; "interfaces->get_length(&listLength)"
0x18003e2f9  mov     edx, 228h
0x18003e2fe  jmp     short loc_18003E2A9
0x18003e300  mov     byte ptr [rsp+1A0h+var_170], r14b; int
0x18003e305  lea     r8, [rsp+1A0h+var_170]; bool *
0x18003e30a  mov     edx, 60004h; unsigned int
0x18003e30f  mov     rcx, [r13+20h]; this
0x18003e313  call    ?QuirkIsEnabled@Package@OSIntegration@@QEBAJKPEA_N@Z; OSIntegration::Package::QuirkIsEnabled(ulong,bool *)
0x18003e318  mov     esi, eax
0x18003e31a  test    eax, eax
0x18003e31c  jns     short loc_18003E32F
0x18003e31e  lea     rax, aSourcepackageQ; "_sourcePackage->QuirkIsEnabled(QUIRK_RE"...
0x18003e325  mov     edx, 22Ah
0x18003e32a  jmp     loc_18003E2A9
0x18003e32f  mov     r15d, r14d
0x18003e332  cmp     r15d, [rsp+1A0h+var_148]
0x18003e337  jge     loc_18003E579
0x18003e33d  mov     [rsp+1A0h+var_168], r14
0x18003e342  mov     r14, [rsp+1A0h+var_158.lpVtbl]
0x18003e347  mov     rax, [r14]
0x18003e34a  mov     rsi, [rax+38h]
0x18003e34e  lea     rcx, [rsp+1A0h+var_168]
0x18003e353  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003e358  lea     r8, [rsp+1A0h+var_168]
0x18003e35d  mov     edx, r15d
0x18003e360  mov     rcx, r14
0x18003e363  mov     rax, rsi
0x18003e366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e36b  mov     esi, eax
0x18003e36d  xor     eax, eax
0x18003e36f  test    esi, esi
0x18003e371  js      loc_18003E4DC
0x18003e377  mov     [rsp+1A0h+var_150], rax
0x18003e37c  mov     [rbp+0A0h+var_110], rax
0x18003e380  mov     [rbp+0A0h+var_118], rax
0x18003e384  xorps   xmm0, xmm0
0x18003e387  movups  [rbp+0A0h+var_B0], xmm0
0x18003e38b  mov     r14, cs:off_1802E0608; "InterfaceId"
0x18003e392  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003e396  inc     rsi
0x18003e399  cmp     [r14+rsi*2], ax
0x18003e39e  jnz     short loc_18003E396
0x18003e3a0  mov     eax, 0FFFFFFFFh
0x18003e3a5  cmp     rsi, rax
0x18003e3a8  jbe     short loc_18003E3C1
0x18003e3aa  mov     esi, eax
0x18003e3ac  xor     r9d, r9d; lpArguments
0x18003e3af  xor     r8d, r8d; nNumberOfArguments
0x18003e3b2  lea     edx, [r9+1]; dwExceptionFlags
0x18003e3b6  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003e3bb  call    cs:__imp_RaiseException
0x18003e3c1  lea     r9, [rbp+0A0h+var_80]; string
0x18003e3c5  lea     r8, [rbp+0A0h+var_78]; hstringHeader
0x18003e3c9  mov     edx, esi; length
0x18003e3cb  mov     rcx, r14; sourceString
0x18003e3ce  call    cs:__imp_WindowsCreateStringReference
0x18003e3d4  mov     [rbp+0A0h+var_108], r13
0x18003e3d8  lea     rax, [rbp+0A0h+var_80]
0x18003e3dc  mov     [rbp+0A0h+var_100], rax
0x18003e3e0  lea     rax, [rsp+1A0h+var_168]
0x18003e3e5  mov     [rbp+0A0h+var_F8], rax
0x18003e3e9  lea     rax, [rbp+0A0h+var_110]
0x18003e3ed  mov     [rbp+0A0h+var_F0], rax
0x18003e3f1  lea     rax, [rbp+0A0h+var_B0]
0x18003e3f5  mov     [rbp+0A0h+var_E8], rax
0x18003e3f9  lea     rax, [rbp+0A0h+var_118]
0x18003e3fd  mov     [rbp+0A0h+var_E0], rax
0x18003e401  lea     rax, [rsp+1A0h+var_150]
0x18003e406  mov     [rbp+0A0h+var_D8], rax
0x18003e40a  lea     rax, [rsp+1A0h+var_140]
0x18003e40f  mov     [rbp+0A0h+var_D0], rax
0x18003e413  lea     rcx, [rbp+0A0h+var_108]
0x18003e417  call    _lambda_4faec5f9e1de0d244e1a7c86b61b9810___operator__
0x18003e41c  mov     esi, eax
0x18003e41e  xor     r14d, r14d
0x18003e421  cmp     byte ptr [rsp+1A0h+var_170], r14b
0x18003e426  jz      short loc_18003E433
0x18003e428  mov     ecx, [rsp+1A0h+var_148]
0x18003e42c  dec     ecx
0x18003e42e  cmp     r15d, ecx
0x18003e431  jnz     short loc_18003E437
0x18003e433  test    esi, esi
0x18003e435  js      short loc_18003E48C
0x18003e437  mov     rcx, [rbp+0A0h+var_118]; string
0x18003e43b  test    rcx, rcx
0x18003e43e  jz      short loc_18003E447
0x18003e440  call    cs:__imp_WindowsDeleteString
0x18003e446  nop
0x18003e447  mov     rcx, [rbp+0A0h+var_110]; string
  ... truncated ...
```
