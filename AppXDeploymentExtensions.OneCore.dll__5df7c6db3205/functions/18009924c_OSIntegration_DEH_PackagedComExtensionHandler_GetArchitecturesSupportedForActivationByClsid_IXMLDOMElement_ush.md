# OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid(IXMLDOMElement *,ushort const *,OSIntegration::DEH::SupportedArchitectureFlags *)

- ea: `0x18009924c`
- end: `0x180099980`
- name: `?GetArchitecturesSupportedForActivationByClsid@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAW4SupportedArchitectureFlags@23@@Z`
- size: `1844`
- prototype: `int(OSIntegration::DEH::PackagedComExtensionHandler *__hidden this, struct IXMLDOMElement *, const unsigned __int16 *, enum OSIntegration::DEH::SupportedArchitectureFlags *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18016cf84`

## callees

- `0x18000b7d0`
- `0x180012964`
- `0x18003f850`
- `0x180077608`
- `0x18008d84c`
- `0x18009924c`
- `0x18009aff4`
- `0x18009b1b8`
- `0x180165d30`
- `0x180211010`

## string_xrefs

- `0x1800992f2`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180099350`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800993d6`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18009946b`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800994c6`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180099548`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180099600`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180099695`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180099715`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800997a1`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180099807`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x180099889`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x1800992f9`: `OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid`
- `0x180099349`: `OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid`
- `0x1800993dd`: `OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid`
- `0x180099464`: `OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid`
- `0x1800994cd`: `OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid`
- `0x18009954f`: `OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid`
- `0x180099607`: `OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid`
- `0x18009968e`: `OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid`
- `0x18009971c`: `OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid`
- `0x1800997a8`: `OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid`
- `0x18009980e`: `OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid`
- `0x180099890`: `OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid`
- `0x1800993ca`: `inProcessServerClassXPath`
- `0x1800992b9`: `outofprocClassXPath`
- `0x1800995f4`: `managedInProcessServerClassXPath`
- `0x180099709`: `inProcessHandlerClassXPath`
- `0x1800992ca`: `//*[local-name()='Extension' and @Category='windows.comServer']/*[local-name()='ComServer']/*[local-name()='ExeServer' or local-name()='SurrogateServer' or local-name()='ServiceServer']/*[(local-name()='Class' or local-name()='ClassReference' or local-name()='InProcessServerClassReference') and @Id='%ls']`
- `0x180099404`: `//*[local-name()='Extension' and @Category='windows.comServer']/*[local-name()='ComServer']/*[local-name()='InProcessServer']/*[(local-name()='Class' or local-name()='ClassReference') and @Id='%ls']`
- `0x18009973e`: `//*[local-name()='Extension' and @Category='windows.comServer']/*[local-name()='ComServer']/*[local-name()='InProcessHandler']/*[(local-name()='Class' or local-name()='ClassReference') and @Id='%ls']`
- `0x18009962e`: `//*[local-name()='Extension' and @Category='windows.comServer']/*[local-name()='ComServer']/*[local-name()='ManagedInProcessServer']/*[(local-name()='Class' or local-name()='ClassReference') and @Id='%ls']`
- `0x180099577`: `InProcessServerDll`
- `0x1800998b8`: `InProcessHandlerDll`
- `0x180099761`: `StringCchPrintf(inProcessHandlerClassXPath.get(), cchInProcessHandlerClassXPath, Internal::PackagedComConstants::inProcessHandlerClassWithIdFormat, clsid)`
- `0x180099795`: `GetXMLElementFromQuery(inProcessHandlerClassXPath.get(), root, &inProcessHandlerClassElement)`
- `0x1800998d6`: `GetSupportedArchitecturesBasedOnDllPaths(inProcessHandlerElement.get(), Internal::PackagedComConstants::inProcessHandlerDllElement, &supportedArchitecturesForInprocHandler)`
- `0x1800992e6`: `StringCchPrintf(outofprocClassXPath.get(), cchOutofprocClassXPath, Internal::PackagedComConstants::outofprocClassWithIdFormat, clsid)`
- `0x18009933d`: `GetXMLElementFromQuery(outofprocClassXPath.get(), root, &outofprocClassElement)`
- `0x180099420`: `StringCchPrintf(inProcessServerClassXPath.get(), cchInProcessServerClassXPath, Internal::PackagedComConstants::inProcessServerClassWithIdFormat, clsid)`
- `0x180099458`: `GetXMLElementFromQuery(inProcessServerClassXPath.get(), root, &inProcessServerClassElement)`
- `0x180099595`: `GetSupportedArchitecturesBasedOnDllPaths(inProcessServerElement.get(), Internal::PackagedComConstants::inProcessServerDllElement, &supportedArchitecturesForInprocServer)`
- `0x18009964a`: `StringCchPrintf(managedInProcessServerClassXPath.get(), cchManagedInProcessServerClassXPath, Internal::PackagedComConstants::managedInProcessServerClassWithIdFormat, clsid)`
- `0x180099682`: `GetXMLElementFromQuery(managedInProcessServerClassXPath.get(), root, &managedInProcessServerClassElement)`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid(
        OSIntegration::DEH::PackagedComExtensionHandler *this,
        struct IXMLDOMElement *a2,
        const unsigned __int16 *a3,
        enum OSIntegration::DEH::SupportedArchitectureFlags *a4)
{
  __int64 v7; // r13
  __int64 v8; // rax
  unsigned __int64 v9; // rdi
  OLECHAR *v10; // rbx
  unsigned int v11; // edi
  const char *v12; // rax
  __int64 v13; // rdx
  int v14; // eax
  struct IXMLDOMElement **v15; // r9
  int XMLElementFromQuery; // eax
  int v17; // esi
  int v18; // r15d
  __int64 v19; // rax
  unsigned __int64 v20; // rdi
  wchar_t *v21; // rbx
  const char *v22; // rax
  __int64 v23; // rdx
  int v24; // eax
  struct IXMLDOMElement **v25; // r9
  int v26; // eax
  HRESULT (__stdcall *QueryInterface)(IXMLDOMElement *, const IID *const, void **); // rax
  int v28; // eax
  const char *v29; // rax
  __int64 v30; // rdx
  int v31; // eax
  const char *v32; // rax
  __int64 v33; // rdx
  int SupportedArchitecturesBasedOnDllPaths; // eax
  __int64 v35; // rax
  unsigned __int64 v36; // rdi
  wchar_t *v37; // rbx
  const char *v38; // rax
  __int64 v39; // rdx
  wchar_t **v40; // rcx
  int v41; // eax
  struct IXMLDOMElement **v42; // r9
  int v43; // eax
  wchar_t *v44; // rbx
  const char *v45; // rax
  __int64 v46; // rdx
  int v47; // eax
  struct IXMLDOMElement **v48; // r9
  int v49; // eax
  const char *v50; // rax
  __int64 v51; // rdx
  HRESULT (__stdcall *v52)(IXMLDOMElement *, const IID *const, void **); // rax
  int v53; // eax
  const char *v54; // rax
  __int64 v55; // rdx
  int v56; // eax
  const char *v57; // rax
  __int64 v58; // rdx
  int v59; // eax
  const char *v61; // [rsp+30h] [rbp-41h]
  struct IXMLDOMElement v62; // [rsp+38h] [rbp-39h] BYREF
  struct IXMLDOMElement v63; // [rsp+40h] [rbp-31h] BYREF
  wchar_t *strIn; // [rsp+48h] [rbp-29h] BYREF
  wchar_t *v65; // [rsp+50h] [rbp-21h] BYREF
  struct IXMLDOMElement v66; // [rsp+58h] [rbp-19h] BYREF
  int v67; // [rsp+60h] [rbp-11h] BYREF
  struct IXMLDOMElement v68; // [rsp+68h] [rbp-9h] BYREF
  wchar_t *v69; // [rsp+70h] [rbp-1h] BYREF
  __int64 (__fastcall ***v70)(_QWORD, GUID *, wchar_t **); // [rsp+78h] [rbp+7h] BYREF
  __int64 (__fastcall ***v71)(_QWORD, GUID *, struct IXMLDOMElement *); // [rsp+80h] [rbp+Fh] BYREF
  wchar_t *Buffer[8]; // [rsp+88h] [rbp+17h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+D0h] [rbp+5Fh]

  *(_DWORD *)a4 = 0;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  v9 = v8 + 305;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    Buffer,
    0,
    v8 + 305);
  v10 = Buffer[0];
  if ( Buffer[0] )
  {
    v14 = StringCchPrintfW(
            Buffer[0],
            v9,
            L"//*[local-name()='Extension' and @Category='windows.comServer']/*[local-name()='ComServer']/*[local-name()='"
             "ExeServer' or local-name()='SurrogateServer' or local-name()='ServiceServer']/*[(local-name()='Class' or lo"
             "cal-name()='ClassReference' or local-name()='InProcessServerClassReference') and @Id='%ls']",
            a3);
    v11 = v14;
    if ( v14 < 0 )
    {
      LODWORD(v61) = v14;
      v12 = "StringCchPrintf(outofprocClassXPath.get(), cchOutofprocClassXPath, Internal::PackagedComConstants::outofproc"
            "ClassWithIdFormat, clsid)";
      v13 = 4309;
      goto LABEL_7;
    }
    v62.lpVtbl = 0;
    wil::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>::reset(&v62);
    XMLElementFromQuery = Common::Xml::GetXMLElementFromQuery(v10, (const unsigned __int16 *)a2, &v62, v15);
    v11 = XMLElementFromQuery;
    if ( XMLElementFromQuery < 0 )
    {
      LODWORD(v61) = XMLElementFromQuery;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x10D8,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid",
        "GetXMLElementFromQuery(outofprocClassXPath.get(), root, &outofprocClassElement)",
        v61,
        (int)v62.lpVtbl);
LABEL_10:
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v62);
      goto LABEL_80;
    }
    if ( v62.lpVtbl )
    {
      *(_DWORD *)a4 = 15;
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v62);
      v11 = 0;
      goto LABEL_80;
    }
    v17 = 0;
    v18 = 0;
    v67 = 0;
    v19 = -1;
    do
      ++v19;
    while ( a3[v19] );
    v20 = v19 + 197;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &strIn,
      0,
      v19 + 197);
    v21 = strIn;
    if ( !strIn )
    {
      v11 = -2147024882;
      LODWORD(v61) = -2147024882;
      v22 = "inProcessServerClassXPath";
      v23 = 4333;
LABEL_17:
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid",
        v22,
        v61,
        (int)v62.lpVtbl);
LABEL_18:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&strIn);
      goto LABEL_10;
    }
    v24 = StringCchPrintfW(
            strIn,
            v20,
            L"//*[local-name()='Extension' and @Category='windows.comServer']/*[local-name()='ComServer']/*[local-name()='"
             "InProcessServer']/*[(local-name()='Class' or local-name()='ClassReference') and @Id='%ls']",
            a3);
    v11 = v24;
    if ( v24 < 0 )
    {
      LODWORD(v61) = v24;
      v22 = "StringCchPrintf(inProcessServerClassXPath.get(), cchInProcessServerClassXPath, Internal::PackagedComConstant"
            "s::inProcessServerClassWithIdFormat, clsid)";
      v23 = 4336;
      goto LABEL_17;
    }
    v63.lpVtbl = 0;
    wil::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>::reset(&v63);
    v26 = Common::Xml::GetXMLElementFromQuery(v21, (const unsigned __int16 *)a2, &v63, v25);
    v11 = v26;
    if ( v26 < 0 )
    {
      LODWORD(v61) = v26;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x10F4,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid",
        "GetXMLElementFromQuery(inProcessServerClassXPath.get(), root, &inProcessServerClassElement)",
        v61,
        (int)v62.lpVtbl);
LABEL_23:
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v63);
      goto LABEL_18;
    }
    if ( v63.lpVtbl )
    {
      v70 = 0;
      QueryInterface = v63.lpVtbl->QueryInterface;
      v70 = 0;
      v28 = (*((__int64 (__fastcall **)(struct IXMLDOMElementVtbl *, __int64 (__fastcall ****)(_QWORD, GUID *, wchar_t **)))QueryInterface
             + 11))(
              v63.lpVtbl,
              &v70);
      v11 = v28;
      if ( v28 < 0 )
      {
        LODWORD(v61) = v28;
        v29 = "inProcessServerClassElement->get_parentNode(&inProcessServerNode)";
        v30 = 4344;
LABEL_27:
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid",
          v29,
          v61,
          (int)v62.lpVtbl);
LABEL_28:
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v70);
        goto LABEL_23;
      }
      if ( !v70 )
      {
        v11 = -2147418113;
        LODWORD(v61) = -2147418113;
        v29 = "!inProcessServerNode";
        v30 = 4345;
        goto LABEL_27;
      }
      v65 = 0;
      wil::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>::reset(&v65);
      v31 = (**v70)(v70, &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60, &v65);
      v11 = v31;
      if ( v31 < 0 )
      {
        LODWORD(v61) = v31;
        v32 = "inProcessServerNode.query_to(&inProcessServerElement)";
        v33 = 4348;
LABEL_33:
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)v33,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid",
          v32,
          v61,
          (int)v62.lpVtbl);
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v65);
        goto LABEL_28;
      }
      SupportedArchitecturesBasedOnDllPaths = OSIntegration::DEH::PackagedComExtensionHandler::GetSupportedArchitecturesBasedOnDllPaths(
                                                this,
                                                (struct IXMLDOMElement *)v65,
                                                L"InProcessServerDll",
                                                (enum OSIntegration::DEH::SupportedArchitectureFlags *)&v67);
      v11 = SupportedArchitecturesBasedOnDllPaths;
      if ( SupportedArchitecturesBasedOnDllPaths < 0 )
      {
        LODWORD(v61) = SupportedArchitecturesBasedOnDllPaths;
        v32 = "GetSupportedArchitecturesBasedOnDllPaths(inProcessServerElement.get(), Internal::PackagedComConstants::inP"
              "rocessServerDllElement, &supportedArchitecturesForInprocServer)";
        v33 = 4351;
        goto LABEL_33;
      }
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v65);
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v70);
      v18 = v67;
LABEL_51:
      v67 = 0;
      do
        ++v7;
      while ( a3[v7] );
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v69,
        0,
        v7 + 198);
      v44 = v69;
      if ( !v69 )
      {
        v11 = -2147024882;
        LODWORD(v61) = -2147024882;
        v45 = "inProcessHandlerClassXPath";
        v46 = 4389;
LABEL_55:
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)v46,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid",
          v45,
          v61,
          (int)v62.lpVtbl);
LABEL_56:
        v40 = &v69;
        goto LABEL_43;
      }
      v47 = StringCchPrintfW(
              v69,
              v7 + 198,
              L"//*[local-name()='Extension' and @Category='windows.comServer']/*[local-name()='ComServer']/*[local-name()"
               "='InProcessHandler']/*[(local-name()='Class' or local-name()='ClassReference') and @Id='%ls']",
              a3);
      v11 = v47;
      if ( v47 < 0 )
      {
        LODWORD(v61) = v47;
        v45 = "StringCchPrintf(inProcessHandlerClassXPath.get(), cchInProcessHandlerClassXPath, Internal::PackagedComCons"
              "tants::inProcessHandlerClassWithIdFormat, clsid)";
        v46 = 4392;
        goto LABEL_55;
      }
      v68.lpVtbl = 0;
      wil::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>::reset(&v68);
      v49 = Common::Xml::GetXMLElementFromQuery(v44, (const unsigned __int16 *)a2, &v68, v48);
      v11 = v49;
      if ( v49 < 0 )
      {
        LODWORD(v61) = v49;
        v50 = "GetXMLElementFromQuery(inProcessHandlerClassXPath.get(), root, &inProcessHandlerClassElement)";
        v51 = 4396;
LABEL_61:
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)v51,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid",
          v50,
          v61,
          (int)v62.lpVtbl);
LABEL_62:
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v68);
        goto LABEL_56;
      }
      if ( v68.lpVtbl )
      {
        v71 = 0;
        v52 = v68.lpVtbl->QueryInterface;
        v71 = 0;
        v53 = (*((__int64 (__fastcall **)(struct IXMLDOMElementVtbl *, __int64 (__fastcall ****)(_QWORD, GUID *, struct IXMLDOMElement *)))v52
               + 11))(
                v68.lpVtbl,
                &v71);
        v11 = v53;
        if ( v53 < 0 )
        {
          LODWORD(v61) = v53;
          v54 = "inProcessHandlerClassElement->get_parentNode(&inProcessHandlerNode)";
          v55 = 4400;
LABEL_66:
          wil::details::in1diag5::Return_Hr(
            retaddr,
            (void *)v55,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
            "OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid",
            v54,
            v61,
            (int)v62.lpVtbl);
LABEL_67:
          wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v71);
          goto LABEL_62;
        }
        if ( !v71 )
        {
          v11 = -2147418113;
          LODWORD(v61) = -2147418113;
          v54 = "!inProcessHandlerNode";
          v55 = 4401;
          goto LABEL_66;
        }
        v66.lpVtbl = 0;
        wil::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>::reset(&v66);
        v56 = (**v71)(v71, &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60, &v66);
        v11 = v56;
        if ( v56 < 0 )
        {
          LODWORD(v61) = v56;
          v57 = "inProcessHandlerNode.query_to(&inProcessHandlerElement)";
          v58 = 4404;
LABEL_72:
          wil::details::in1diag5::Return_Hr(
            retaddr,
            (void *)v58,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
            "OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid",
            v57,
            v61,
            (int)v62.lpVtbl);
          wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v66);
          goto LABEL_67;
        }
        v59 = OSIntegration::DEH::PackagedComExtensionHandler::GetSupportedArchitecturesBasedOnDllPaths(
                this,
                (struct IXMLDOMElement *)v66.lpVtbl,
                L"InProcessHandlerDll",
                (enum OSIntegration::DEH::SupportedArchitectureFlags *)&v67);
        v11 = v59;
        if ( v59 < 0 )
        {
          LODWORD(v61) = v59;
          v57 = "GetSupportedArchitecturesBasedOnDllPaths(inProcessHandlerElement.get(), Internal::PackagedComConstants::"
                "inProcessHandlerDllElement, &supportedArchitecturesForInprocHandler)";
          v58 = 4408;
          goto LABEL_72;
        }
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v66);
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v71);
        v17 = v67;
      }
      if ( v18 || v17 )
      {
        *(_DWORD *)a4 = v18 | v17;
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v68);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v69);
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v63);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&strIn);
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v62);
        v11 = 0;
        goto LABEL_80;
      }
      v11 = -2146958844;
      LODWORD(v61) = -2146958844;
      v50 = "(supportedArchitecturesForInprocServer == SupportedArchitectureFlags{}) && (supportedArchitecturesForInprocH"
            "andler == SupportedArchitectureFlags{})";
      v51 = 4413;
      goto LABEL_61;
    }
    v35 = -1;
    do
      ++v35;
    while ( a3[v35] );
    v36 = v35 + 204;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v65,
      0,
      v35 + 204);
    v37 = v65;
    if ( v65 )
    {
      v41 = StringCchPrintfW(
              v65,
              v36,
              L"//*[local-name()='Extension' and @Category='windows.comServer']/*[local-name()='ComServer']/*[local-name()"
               "='ManagedInProcessServer']/*[(local-name()='Class' or local-name()='ClassReference') and @Id='%ls']",
              a3);
      v11 = v41;
      if ( v41 >= 0 )
      {
        v66.lpVtbl = 0;
        wil::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>::reset(&v66);
        v43 = Common::Xml::GetXMLElementFromQuery(v37, (const unsigned __int16 *)a2, &v66, v42);
        v11 = v43;
        if ( v43 >= 0 )
        {
          if ( v66.lpVtbl )
            v18 = 15;
          wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v66);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v65);
          goto LABEL_51;
        }
        LODWORD(v61) = v43;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x1114,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid",
          "GetXMLElementFromQuery(managedInProcessServerClassXPath.get(), root, &managedInProcessServerClassElement)",
          v61,
          (int)v62.lpVtbl);
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v66);
LABEL_42:
        v40 = &v65;
LABEL_43:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v40);
        goto LABEL_23;
      }
      LODWORD(v61) = v41;
      v38 = "StringCchPrintf(managedInProcessServerClassXPath.get(), cchManagedInProcessServerClassXPath, Internal::Packa"
            "gedComConstants::managedInProcessServerClassWithIdFormat, clsid)";
      v39 = 4368;
    }
    else
    {
      v11 = -2147024882;
      LODWORD(v61) = -2147024882;
      v38 = "managedInProcessServerClassXPath";
      v39 = 4364;
    }
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v39,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid",
      v38,
      v61,
      (int)v62.lpVtbl);
    goto LABEL_42;
  }
  v11 = -2147024882;
  LODWORD(v61) = -2147024882;
  v12 = "outofprocClassXPath";
  v13 = 4306;
LABEL_7:
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
    "OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid",
    v12,
    v61,
    (int)v62.lpVtbl);
LABEL_80:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(Buffer);
  return v11;
}

```

## disassembly

```asm
0x18009924c  mov     rax, rsp
0x18009924f  mov     [rax+10h], rbx
0x180099253  mov     [rax+20h], r9
0x180099257  mov     [rax+8], rcx
0x18009925b  push    rbp
0x18009925c  push    rsi
0x18009925d  push    rdi
0x18009925e  push    r12
0x180099260  push    r13
0x180099262  push    r14
0x180099264  push    r15
0x180099266  lea     rbp, [rax-5Fh]
0x18009926a  sub     rsp, 90h
0x180099271  mov     rsi, r9
0x180099274  mov     r14, r8
0x180099277  mov     r12, rdx
0x18009927a  xor     r15d, r15d
0x18009927d  mov     [r9], r15d
0x180099280  or      r13, 0FFFFFFFFFFFFFFFFh
0x180099284  mov     rax, r13
0x180099287  inc     rax
0x18009928a  cmp     [r8+rax*2], r15w
0x18009928f  jnz     short loc_180099287
0x180099291  lea     rdi, [rax+131h]
0x180099298  mov     r8, rdi
0x18009929b  xor     edx, edx
0x18009929d  lea     rcx, [rbp+57h+Buffer]
0x1800992a1  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800992a6  nop
0x1800992a7  mov     rbx, [rbp+57h+Buffer]
0x1800992ab  test    rbx, rbx
0x1800992ae  jnz     short loc_1800992C7
0x1800992b0  mov     edi, 8007000Eh
0x1800992b5  mov     [rsp+28h], edi
0x1800992b9  lea     rax, aOutofprocclass; "outofprocClassXPath"
0x1800992c0  mov     edx, 10D2h
0x1800992c5  jmp     short loc_1800992F2
0x1800992c7  mov     r9, r14
0x1800992ca  lea     r8, aLocalNameExten_1; "//*[local-name()='Extension' and @Categ"...
0x1800992d1  mov     rdx, rdi; unsigned __int64
0x1800992d4  mov     rcx, rbx; Buffer
0x1800992d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800992dc  mov     edi, eax
0x1800992de  test    eax, eax
0x1800992e0  jns     short loc_180099313
0x1800992e2  mov     [rsp+28h], eax; char *
0x1800992e6  lea     rax, aStringcchprint_10; "StringCchPrintf(outofprocClassXPath.get"...
0x1800992ed  mov     edx, 10D5h; void *
0x1800992f2  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800992f9  lea     r9, aOsintegrationD_320; "OSIntegration::DEH::PackagedComExtensio"...
0x180099300  mov     [rsp+0C0h+var_A0], rax; char *
0x180099305  mov     rcx, [rbp+5Fh]; this
0x180099309  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18009930e  jmp     loc_18009995A
0x180099313  mov     [rbp+57h+var_90.lpVtbl], r15
0x180099317  lea     rcx, [rbp+57h+var_90]
0x18009931b  call    ?reset@?$com_ptr_t@UIXMLDOMElement@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>::reset(void)
0x180099320  lea     r8, [rbp+57h+var_90]; struct IXMLDOMElement *
0x180099324  mov     rdx, r12; unsigned __int16 *
0x180099327  mov     rcx, rbx; strIn
0x18009932a  call    ?GetXMLElementFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@PEAPEAU3@@Z; Common::Xml::GetXMLElementFromQuery(ushort const *,IXMLDOMElement *,IXMLDOMElement * *)
0x18009932f  mov     edi, eax
0x180099331  test    eax, eax
0x180099333  jns     short loc_180099370
0x180099335  mov     rcx, [rbp+5Fh]; this
0x180099339  mov     [rsp+28h], eax; char *
0x18009933d  lea     rax, aGetxmlelementf_4; "GetXMLElementFromQuery(outofprocClassXP"...
0x180099344  mov     [rsp+0C0h+var_A0], rax; char *
0x180099349  lea     r9, aOsintegrationD_320; "OSIntegration::DEH::PackagedComExtensio"...
0x180099350  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180099357  mov     edx, 10D8h; void *
0x18009935c  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180099361  nop
0x180099362  lea     rcx, [rbp+57h+var_90]
0x180099366  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18009936b  jmp     loc_18009995A
0x180099370  cmp     [rbp+57h+var_90.lpVtbl], r15
0x180099374  jz      short loc_18009938D
0x180099376  mov     dword ptr [rsi], 0Fh
0x18009937c  lea     rcx, [rbp+57h+var_90]
0x180099380  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x180099385  mov     edi, r15d
0x180099388  jmp     loc_18009995A
0x18009938d  xor     esi, esi
0x18009938f  mov     r15d, esi
0x180099392  mov     [rbp+57h+var_68], esi
0x180099395  mov     rax, r13
0x180099398  inc     rax
0x18009939b  cmp     [r14+rax*2], si
0x1800993a0  jnz     short loc_180099398
0x1800993a2  lea     rdi, [rax+0C5h]
0x1800993a9  mov     r8, rdi
0x1800993ac  xor     edx, edx
0x1800993ae  lea     rcx, [rbp+57h+strIn]
0x1800993b2  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800993b7  nop
0x1800993b8  mov     rbx, [rbp+57h+strIn]
0x1800993bc  test    rbx, rbx
0x1800993bf  jnz     short loc_180099401
0x1800993c1  mov     edi, 8007000Eh
0x1800993c6  mov     [rsp+28h], edi; char *
0x1800993ca  lea     rax, aInprocessserve_4; "inProcessServerClassXPath"
0x1800993d1  mov     edx, 10EDh; void *
0x1800993d6  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800993dd  lea     r9, aOsintegrationD_320; "OSIntegration::DEH::PackagedComExtensio"...
0x1800993e4  mov     [rsp+0C0h+var_A0], rax; char *
0x1800993e9  mov     rcx, [rbp+5Fh]; this
0x1800993ed  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800993f2  nop
0x1800993f3  lea     rcx, [rbp+57h+strIn]
0x1800993f7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800993fc  jmp     loc_180099362
0x180099401  mov     r9, r14
0x180099404  lea     r8, aLocalNameExten_8; "//*[local-name()='Extension' and @Categ"...
0x18009940b  mov     rdx, rdi; unsigned __int64
0x18009940e  mov     rcx, rbx; Buffer
0x180099411  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180099416  mov     edi, eax
0x180099418  test    eax, eax
0x18009941a  jns     short loc_18009942E
0x18009941c  mov     [rsp+28h], eax
0x180099420  lea     rax, aStringcchprint_23; "StringCchPrintf(inProcessServerClassXPa"...
0x180099427  mov     edx, 10F0h
0x18009942c  jmp     short loc_1800993D6
0x18009942e  mov     [rbp+57h+var_88.lpVtbl], rsi
0x180099432  lea     rcx, [rbp+57h+var_88]
0x180099436  call    ?reset@?$com_ptr_t@UIXMLDOMElement@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>::reset(void)
0x18009943b  lea     r8, [rbp+57h+var_88]; struct IXMLDOMElement *
0x18009943f  mov     rdx, r12; unsigned __int16 *
0x180099442  mov     rcx, rbx; strIn
0x180099445  call    ?GetXMLElementFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@PEAPEAU3@@Z; Common::Xml::GetXMLElementFromQuery(ushort const *,IXMLDOMElement *,IXMLDOMElement * *)
0x18009944a  mov     edi, eax
0x18009944c  test    eax, eax
0x18009944e  jns     short loc_18009948B
0x180099450  mov     rcx, [rbp+5Fh]; this
0x180099454  mov     [rsp+28h], eax; char *
0x180099458  lea     rax, aGetxmlelementf_1; "GetXMLElementFromQuery(inProcessServerC"...
0x18009945f  mov     [rsp+0C0h+var_A0], rax; char *
0x180099464  lea     r9, aOsintegrationD_320; "OSIntegration::DEH::PackagedComExtensio"...
0x18009946b  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180099472  mov     edx, 10F4h; void *
0x180099477  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18009947c  nop
0x18009947d  lea     rcx, [rbp+57h+var_88]
0x180099481  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x180099486  jmp     loc_1800993F3
0x18009948b  mov     rcx, [rbp+57h+var_88.lpVtbl]
0x18009948f  test    rcx, rcx
0x180099492  jz      loc_1800995BF
0x180099498  mov     [rbp+57h+var_50], rsi
0x18009949c  mov     rax, [rcx]
0x18009949f  mov     [rbp+57h+var_50], rsi
0x1800994a3  lea     rdx, [rbp+57h+var_50]
0x1800994a7  mov     rax, [rax+58h]
0x1800994ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800994b0  mov     edi, eax
0x1800994b2  test    eax, eax
0x1800994b4  jns     short loc_1800994EE
0x1800994b6  mov     [rsp+28h], eax; char *
0x1800994ba  lea     rax, aInprocessserve_3; "inProcessServerClassElement->get_parent"...
0x1800994c1  mov     edx, 10F8h; void *
0x1800994c6  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800994cd  lea     r9, aOsintegrationD_320; "OSIntegration::DEH::PackagedComExtensio"...
0x1800994d4  mov     [rsp+0C0h+var_A0], rax; char *
0x1800994d9  mov     rcx, [rbp+5Fh]; this
0x1800994dd  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800994e2  nop
0x1800994e3  lea     rcx, [rbp+57h+var_50]
0x1800994e7  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x1800994ec  jmp     short loc_18009947D
0x1800994ee  cmp     [rbp+57h+var_50], rsi
0x1800994f2  jnz     short loc_18009950B
0x1800994f4  mov     edi, 8000FFFFh
0x1800994f9  mov     [rsp+28h], edi
0x1800994fd  lea     rax, aInprocessserve_0; "!inProcessServerNode"
0x180099504  mov     edx, 10F9h
0x180099509  jmp     short loc_1800994C6
0x18009950b  mov     [rbp+57h+var_78], rsi
0x18009950f  lea     rcx, [rbp+57h+var_78]
0x180099513  call    ?reset@?$com_ptr_t@UIXMLDOMElement@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>::reset(void)
0x180099518  mov     rcx, [rbp+57h+var_50]
0x18009951c  mov     rax, [rcx]
0x18009951f  lea     r8, [rbp+57h+var_78]
0x180099523  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x18009952a  mov     rax, [rax]
0x18009952d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099532  mov     edi, eax
0x180099534  test    eax, eax
0x180099536  jns     short loc_180099573
0x180099538  mov     [rsp+28h], eax; char *
0x18009953c  lea     rax, aInprocessserve; "inProcessServerNode.query_to(&inProcess"...
0x180099543  mov     edx, 10FCh; void *
0x180099548  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009954f  lea     r9, aOsintegrationD_320; "OSIntegration::DEH::PackagedComExtensio"...
0x180099556  mov     [rsp+0C0h+var_A0], rax; char *
0x18009955b  mov     rcx, [rbp+5Fh]; this
0x18009955f  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180099564  nop
0x180099565  lea     rcx, [rbp+57h+var_78]
0x180099569  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18009956e  jmp     loc_1800994E3
0x180099573  lea     r9, [rbp+57h+var_68]; enum OSIntegration::DEH::SupportedArchitectureFlags *
0x180099577  lea     r8, aInprocessserve_1; "InProcessServerDll"
0x18009957e  mov     rdx, [rbp+57h+var_78]; struct IXMLDOMElement *
0x180099582  mov     rcx, [rbp+57h+arg_0]; this
0x180099586  call    ?GetSupportedArchitecturesBasedOnDllPaths@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAW4SupportedArchitectureFlags@23@@Z; OSIntegration::DEH::PackagedComExtensionHandler::GetSupportedArchitecturesBasedOnDllPaths(IXMLDOMElement *,ushort const *,OSIntegration::DEH::SupportedArchitectureFlags *)
0x18009958b  mov     edi, eax
0x18009958d  test    eax, eax
0x18009958f  jns     short loc_1800995A3
0x180099591  mov     [rsp+28h], eax
0x180099595  lea     rax, aGetsupportedar; "GetSupportedArchitecturesBasedOnDllPath"...
0x18009959c  mov     edx, 10FFh
0x1800995a1  jmp     short loc_180099548
0x1800995a3  lea     rcx, [rbp+57h+var_78]
0x1800995a7  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x1800995ac  nop
0x1800995ad  lea     rcx, [rbp+57h+var_50]
0x1800995b1  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x1800995b6  mov     r15d, [rbp+57h+var_68]
0x1800995ba  jmp     loc_1800996D5
0x1800995bf  mov     rax, r13
0x1800995c2  inc     rax
0x1800995c5  cmp     [r14+rax*2], si
0x1800995ca  jnz     short loc_1800995C2
0x1800995cc  lea     rdi, [rax+0CCh]
0x1800995d3  mov     r8, rdi
0x1800995d6  xor     edx, edx
0x1800995d8  lea     rcx, [rbp+57h+var_78]
0x1800995dc  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800995e1  nop
0x1800995e2  mov     rbx, [rbp+57h+var_78]
0x1800995e6  test    rbx, rbx
0x1800995e9  jnz     short loc_18009962B
0x1800995eb  mov     edi, 8007000Eh
0x1800995f0  mov     [rsp+28h], edi; char *
0x1800995f4  lea     rax, aManagedinproce; "managedInProcessServerClassXPath"
0x1800995fb  mov     edx, 110Ch; void *
0x180099600  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180099607  lea     r9, aOsintegrationD_320; "OSIntegration::DEH::PackagedComExtensio"...
0x18009960e  mov     [rsp+0C0h+var_A0], rax; char *
0x180099613  mov     rcx, [rbp+5Fh]; this
0x180099617  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18009961c  nop
0x18009961d  lea     rcx, [rbp+57h+var_78]
0x180099621  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180099626  jmp     loc_18009947D
0x18009962b  mov     r9, r14
0x18009962e  lea     r8, aLocalNameExten; "//*[local-name()='Extension' and @Categ"...
0x180099635  mov     rdx, rdi; unsigned __int64
0x180099638  mov     rcx, rbx; Buffer
0x18009963b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180099640  mov     edi, eax
0x180099642  test    eax, eax
0x180099644  jns     short loc_180099658
0x180099646  mov     [rsp+28h], eax
0x18009964a  lea     rax, aStringcchprint; "StringCchPrintf(managedInProcessServerC"...
0x180099651  mov     edx, 1110h
0x180099656  jmp     short loc_180099600
0x180099658  mov     [rbp+57h+var_70.lpVtbl], rsi
0x18009965c  lea     rcx, [rbp+57h+var_70]
0x180099660  call    ?reset@?$com_ptr_t@UIXMLDOMElement@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>::reset(void)
0x180099665  lea     r8, [rbp+57h+var_70]; struct IXMLDOMElement *
0x180099669  mov     rdx, r12; unsigned __int16 *
0x18009966c  mov     rcx, rbx; strIn
0x18009966f  call    ?GetXMLElementFromQuery@Xml@Common@@YAJPEBGPEAUIXMLDOMElement@@PEAPEAU3@@Z; Common::Xml::GetXMLElementFromQuery(ushort const *,IXMLDOMElement *,IXMLDOMElement * *)
0x180099674  mov     edi, eax
0x180099676  test    eax, eax
0x180099678  jns     short loc_1800996B5
0x18009967a  mov     rcx, [rbp+5Fh]; this
0x18009967e  mov     [rsp+28h], eax; char *
0x180099682  lea     rax, aGetxmlelementf_0; "GetXMLElementFromQuery(managedInProcess"...
0x180099689  mov     [rsp+0C0h+var_A0], rax; char *
0x18009968e  lea     r9, aOsintegrationD_320; "OSIntegration::DEH::PackagedComExtensio"...
0x180099695  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009969c  mov     edx, 1114h; void *
0x1800996a1  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800996a6  nop
0x1800996a7  lea     rcx, [rbp+57h+var_70]
0x1800996ab  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x1800996b0  jmp     loc_18009961D
0x1800996b5  mov     eax, 0Fh
0x1800996ba  cmp     [rbp+57h+var_70.lpVtbl], rsi
0x1800996be  cmovnz  r15d, eax
0x1800996c2  lea     rcx, [rbp+57h+var_70]
0x1800996c6  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x1800996cb  nop
0x1800996cc  lea     rcx, [rbp+57h+var_78]
0x1800996d0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800996d5  mov     [rbp+57h+var_68], esi
0x1800996d8  xor     edi, edi
0x1800996da  inc     r13
0x1800996dd  cmp     [r14+r13*2], di
0x1800996e2  jnz     short loc_1800996DA
0x1800996e4  lea     r8, [r13+0C6h]
0x1800996eb  xor     edx, edx
0x1800996ed  lea     rcx, [rbp+57h+var_58]
0x1800996f1  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800996f6  nop
0x1800996f7  mov     rbx, [rbp+57h+var_58]
0x1800996fb  test    rbx, rbx
  ... truncated ...
```
