# OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer(IXMLDOMElement *,bool,bool,std::optional<AppModel::TrustLevel>,std::optional<AppModel::RuntimeBehavior>,std::optional<AppModel::BnoIsolation>)

- ea: `0x18016c4e4`
- end: `0x18016cf7d`
- name: `?ParseSurrogateServer@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@_N1V?$optional@W4TrustLevel@AppModel@@@std@@V?$optional@W4RuntimeBehavior@AppModel@@@6@V?$optional@W4BnoIsolation@AppModel@@@6@@Z`
- size: `2713`
- prototype: `__int64 __fastcall(OSIntegration::DEH::PackagedComExtensionHandler *this, struct IXMLDOMElement *, bool, bool, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180166d20`

## callees

- `0x18000b9e0`
- `0x18000cb0c`
- `0x18003a300`
- `0x1800550f4`
- `0x180077608`
- `0x180078a44`
- `0x18007d350`
- `0x18008892c`
- `0x180089c5c`
- `0x18008d84c`
- `0x180098ed0`
- `0x18009aff4`
- `0x1800b8300`
- `0x1800f0260`
- `0x18013ced4`
- `0x18013d6f8`
- `0x180166b50`
- `0x18016b770`
- `0x18016c4e4`
- `0x18016f2dc`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016c76e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016c76e`

## string_xrefs

- `0x18016c560`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016c5b1`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016c669`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016c72b`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016c79c`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016c843`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016c9ca`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016ca78`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016cacf`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016cb12`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016cc66`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016cd06`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016cd9b`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016cebc`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016ceff`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016ca65`: `APPX_E_INVALID_MANIFEST`
- `0x18016c60d`: `ParseServer(root, server.get(), extensionTrustLevel, extensionRuntimeBehavior, extensionBnoIsolation)`
- `0x18016cbd3`: `ParseAndRetrieveGuid(root, Internal::PackagedComConstants::appIdAttribute, &appId, &appIdFound)`
- `0x18016cc5a`: `surrogateServer.query_to(&registryCompatibility)`
- `0x18016ce9e`: `ParseSurrogateClass(classElement.get(), surrogateServer.get(), hasRegistryCompatibility, hasMachineScope)`
- `0x18016ccad`: `registryCompatibility->SetHasRegistryCompatibility(true)`
- `0x18016c54d`: `_collector->CreateSurrogateServerRegistration(&surrogateServer)`
- `0x18016c559`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer`
- `0x18016c5b8`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer`
- `0x18016c670`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer`
- `0x18016c724`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer`
- `0x18016c7a3`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer`
- `0x18016c83c`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer`
- `0x18016c9c3`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer`
- `0x18016ca71`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer`
- `0x18016cad6`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer`
- `0x18016cb0b`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer`
- `0x18016cc6d`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer`
- `0x18016cd0d`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer`
- `0x18016cda2`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer`
- `0x18016cec3`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer`
- `0x18016cef8`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer`
- `0x18016c65d`: `ParseAndRetrievePath(root, Internal::PackagedComConstants::customSurrogateExecutableAttribute, &customSurrogateExecutable, &customSurrogateExecutableFound)`
- `0x18016c70f`: `ParseAndRetrieveAttribute(root, Internal::PackagedComConstants::systemSurrogateAttribute, &systemSurrogateEnumString, &systemSurrogateFound)`
- `0x18016c790`: `MapEnumStringToHstringValue(Internal::PackagedComConstants::systemSurrogateMap, ARRAYSIZE(Internal::PackagedComConstants::systemSurrogateMap), wil::str_raw_ptr(systemSurrogateEnumString), &systemSurrogateExecutable)`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer(
        OSIntegration::DEH::PackagedComExtensionHandler *this,
        struct IXMLDOMElement *a2,
        char a3,
        bool a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  bool v7; // si
  __int64 *v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // eax
  const char *v16; // rax
  __int64 v17; // rdx
  int v18; // eax
  OSIntegration::DEH::PackagedComExtensionHandler *v19; // rcx
  int v20; // eax
  const char *v21; // rax
  __int64 v22; // rdx
  int v23; // eax
  OSIntegration::DEH::PackagedComExtensionHandler *v24; // rcx
  int v25; // eax
  OSIntegration::DEH::PackagedComExtensionHandler *v26; // rcx
  const char *v27; // rax
  __int64 v28; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  int v32; // eax
  __int64 v33; // r8
  const char *v34; // rax
  __int64 v35; // rdx
  int v36; // eax
  struct IXMLDOMElementVtbl *v37; // rax
  int v38; // eax
  int v39; // eax
  __int64 v40; // rcx
  unsigned int v41; // edx
  unsigned int j; // ebx
  __int64 v43; // rax
  int v44; // eax
  int ArchitectureOfSurrogateClass; // esi
  int v46; // edi
  __int64 v47; // rcx
  __int64 v48; // rbx
  unsigned int v49; // eax
  const unsigned __int16 *v50; // rax
  __int64 v51; // rdx
  const char *v52; // rax
  __int64 v53; // rdx
  int v54; // eax
  int v55; // eax
  int v56; // eax
  int v57; // eax
  __int64 v58; // rdx
  const char *v59; // rax
  __int64 v60; // rdx
  int v61; // eax
  int v62; // eax
  __int64 v63; // rdx
  const char *v64; // rax
  __int64 v65; // rdx
  int v66; // eax
  struct IXMLDOMElementVtbl *lpVtbl; // rax
  int v68; // eax
  int v69; // eax
  unsigned int i; // ebx
  __int64 v71; // rax
  int v72; // eax
  const char *v73; // rax
  __int64 v74; // rdx
  char *v76; // [rsp+28h] [rbp-D8h]
  char *v77; // [rsp+28h] [rbp-D8h]
  int v78; // [rsp+30h] [rbp-D0h]
  bool v79; // [rsp+40h] [rbp-C0h] BYREF
  bool v80; // [rsp+41h] [rbp-BFh] BYREF
  __int64 v81; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v82; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  bool v84; // [rsp+60h] [rbp-A0h]
  __int64 v85; // [rsp+68h] [rbp-98h] BYREF
  struct OSIntegration::DEH::IComSurrogateServerRegistration *v86; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v87; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v88; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v89; // [rsp+88h] [rbp-78h] BYREF
  __int64 (__fastcall ***v90)(_QWORD, GUID *, struct IXMLDOMElement **); // [rsp+90h] [rbp-70h] BYREF
  struct IXMLDOMElement *v91; // [rsp+98h] [rbp-68h] BYREF
  __int64 (__fastcall ***v92)(_QWORD, GUID *, struct IXMLDOMElement **); // [rsp+A0h] [rbp-60h] BYREF
  struct IXMLDOMElement *v93; // [rsp+A8h] [rbp-58h] BYREF
  int v94; // [rsp+B0h] [rbp-50h] BYREF
  int v95; // [rsp+B4h] [rbp-4Ch] BYREF
  __int64 v96; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v97[2]; // [rsp+C0h] [rbp-40h] BYREF
  struct _GUID v98; // [rsp+D0h] [rbp-30h] BYREF
  struct _GUID v99; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+138h] [rbp+38h]

  v7 = a4;
  v84 = a4;
  v86 = 0;
  v11 = (__int64 *)*((_QWORD *)this + 6);
  v12 = *v11;
  v86 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64 *, struct OSIntegration::DEH::IComSurrogateServerRegistration **))(v12 + 56))(
          v11,
          &v86);
  v14 = v13;
  if ( v13 < 0 )
  {
    LODWORD(v76) = v13;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x261,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer",
      "_collector->CreateSurrogateServerRegistration(&surrogateServer)",
      v76,
      v78);
    goto LABEL_94;
  }
  v81 = 0;
  v15 = (**(__int64 (__fastcall ***)(struct OSIntegration::DEH::IComSurrogateServerRegistration *, GUID *, __int64 *))v86)(
          v86,
          &GUID_f76c7cd7_3680_4053_9ec9_1ffb74ee02a7,
          &v81);
  v14 = v15;
  if ( v15 < 0 )
  {
    LODWORD(v76) = v15;
    v16 = "surrogateServer.query_to(&server)";
    v17 = 613;
LABEL_5:
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer",
      v16,
      v76,
      v78);
    goto LABEL_6;
  }
  v18 = OSIntegration::DEH::PackagedComExtensionHandler::ParseServer(this, a2, v81, a5, a6, a7);
  v14 = v18;
  if ( v18 < 0 )
  {
    LODWORD(v76) = v18;
    v16 = "ParseServer(root, server.get(), extensionTrustLevel, extensionRuntimeBehavior, extensionBnoIsolation)";
    v17 = 614;
    goto LABEL_5;
  }
  v82 = 0;
  v80 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    &v82,
    0);
  v20 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrievePath(
          v19,
          a2,
          (struct IXMLDOMElement *)L"CustomSurrogateExecutable",
          &v82,
          &v80);
  v14 = v20;
  if ( v20 < 0 )
  {
    LODWORD(v76) = v20;
    v21 = "ParseAndRetrievePath(root, Internal::PackagedComConstants::customSurrogateExecutableAttribute, &customSurrogat"
          "eExecutable, &customSurrogateExecutableFound)";
    v22 = 621;
LABEL_11:
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer",
      v21,
      v76,
      v78);
    goto LABEL_12;
  }
  if ( v80 )
  {
    v23 = (*(__int64 (__fastcall **)(struct OSIntegration::DEH::IComSurrogateServerRegistration *, HSTRING, _QWORD))(*(_QWORD *)v86 + 56LL))(
            v86,
            v82,
            0);
    v14 = v23;
    if ( v23 < 0 )
    {
      LODWORD(v76) = v23;
      v21 = "surrogateServer->SetCustomSurrogateExecutable(customSurrogateExecutable.get(), FALSE)";
      v22 = 624;
      goto LABEL_11;
    }
  }
  string = 0;
  v79 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    &string,
    0);
  v25 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(
          v24,
          a2,
          (struct IXMLDOMElement *)L"SystemSurrogate",
          &string,
          &v79);
  v14 = v25;
  if ( v25 < 0 )
  {
    LODWORD(v76) = v25;
    v27 = "ParseAndRetrieveAttribute(root, Internal::PackagedComConstants::systemSurrogateAttribute, &systemSurrogateEnum"
          "String, &systemSurrogateFound)";
    v28 = 631;
LABEL_18:
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer",
      v27,
      v76,
      v78);
    goto LABEL_19;
  }
  if ( !v79 )
  {
LABEL_45:
    if ( v80 && v79 )
    {
      v96 = 0;
      OSIntegration::Package::GetXmlLineInformation(
        *((OSIntegration::Package **)this + 5),
        (const struct IXMLDOMNode *)a2,
        0,
        (struct APPX_XML_LINE_INFORMATION *)&v96);
      v46 = -2146958844;
      LODWORD(v76) = -2146958844;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0x2C3,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer",
        "((HRESULT)0x80080204L)",
        v76,
        v78);
      if ( (byte_1802E21CA & 4) != 0 )
      {
        v47 = *((_QWORD *)this + 5);
        v48 = *(_QWORD *)(v47 + 224);
        v49 = (unsigned int)RemovePIIfromFilePath(*(const unsigned __int16 **)(v47 + 272));
        McTemplateU0zqqdz_EventWriteTransfer(
          HIDWORD(v96),
          (unsigned int)PackagedComInvalidSurrogateServer,
          v49,
          v96,
          SBYTE4(v96),
          4,
          v48);
      }
      v50 = RemovePIIfromFilePath(*(const unsigned __int16 **)(*((_QWORD *)this + 5) + 272LL));
      details::appxLog<unsigned short const *,unsigned int,unsigned int,long,unsigned short *>(
        2148008452LL,
        v51,
        PackagedComInvalidSurrogateServer,
        v50,
        v96,
        HIDWORD(v96));
      LODWORD(v77) = -2146958844;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x2C5,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer",
        "APPX_E_INVALID_MANIFEST",
        v77,
        -2146958844);
LABEL_50:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&string);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v82);
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v81);
      v14 = v46;
      goto LABEL_94;
    }
    v99 = 0;
    v79 = 0;
    v55 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveGuid(v26, a2, L"AppId", &v99, &v79);
    v14 = v55;
    if ( v55 < 0 )
    {
      LODWORD(v76) = v55;
      v27 = "ParseAndRetrieveGuid(root, Internal::PackagedComConstants::appIdAttribute, &appId, &appIdFound)";
      v28 = 715;
      goto LABEL_18;
    }
    if ( v79 )
    {
      v98 = v99;
      v56 = (*(__int64 (__fastcall **)(struct OSIntegration::DEH::IComSurrogateServerRegistration *, struct _GUID *))(*(_QWORD *)v86 + 64LL))(
              v86,
              &v98);
      v14 = v56;
      if ( v56 < 0 )
      {
        LODWORD(v76) = v56;
        v27 = "surrogateServer->SetAppId(appId)";
        v28 = 721;
        goto LABEL_18;
      }
    }
    if ( a3 )
    {
      v97[0] = 0;
      v57 = (**(__int64 (__fastcall ***)(struct OSIntegration::DEH::IComSurrogateServerRegistration *, GUID *, _QWORD *))v86)(
              v86,
              &GUID_f74eae70_01a3_405c_aa49_bc7c92dd9de3,
              v97);
      v14 = v57;
      if ( v57 < 0 )
      {
        LODWORD(v76) = v57;
        v59 = "surrogateServer.query_to(&registryCompatibility)";
        v60 = 727;
LABEL_66:
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)v60,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer",
          v59,
          v76,
          v78);
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(v97);
        goto LABEL_19;
      }
      LOBYTE(v58) = 1;
      v61 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v97[0] + 48LL))(v97[0], v58);
      v14 = v61;
      if ( v61 < 0 )
      {
        LODWORD(v76) = v61;
        v59 = "registryCompatibility->SetHasRegistryCompatibility(true)";
        v60 = 728;
        goto LABEL_66;
      }
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(v97);
    }
    if ( v7 )
    {
      *(_QWORD *)&v98.Data1 = 0;
      v62 = (**(__int64 (__fastcall ***)(struct OSIntegration::DEH::IComSurrogateServerRegistration *, GUID *, struct _GUID *))v86)(
              v86,
              &GUID_6b3024bd_050b_4ef2_8ec9_2aa58da513ac,
              &v98);
      v14 = v62;
      if ( v62 < 0 )
      {
        LODWORD(v76) = v62;
        v64 = "surrogateServer.query_to(&scope)";
        v65 = 734;
LABEL_73:
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)v65,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer",
          v64,
          v76,
          v78);
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v98);
        goto LABEL_19;
      }
      LOBYTE(v63) = 1;
      v66 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)&v98.Data1 + 48LL))(*(_QWORD *)&v98.Data1, v63);
      v14 = v66;
      if ( v66 < 0 )
      {
        LODWORD(v76) = v66;
        v64 = "scope->SetHasMachineScope(true)";
        v65 = 735;
        goto LABEL_73;
      }
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v98);
    }
    lpVtbl = a2->lpVtbl;
    v89 = 0;
    v68 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 **))lpVtbl->get_childNodes)(a2, &v89);
    v14 = v68;
    if ( v68 >= 0 )
    {
      v95 = 0;
      v69 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v89 + 64))(v89, &v95);
      v14 = v69;
      if ( v69 >= 0 )
      {
        for ( i = 0; (int)i < v95; ++i )
        {
          v92 = 0;
          v71 = *v89;
          v92 = 0;
          v72 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(v71 + 56))(v89, i, &v92);
          v46 = v72;
          if ( v72 < 0 )
          {
            LODWORD(v76) = v72;
            wil::details::in1diag5::Return_Hr(
              retaddr,
              (void *)0x2EC,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
              "OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer",
              "classes->get_item(classIndex, &nodeClass)",
              v76,
              v78);
            goto LABEL_92;
          }
          v93 = 0;
          wil::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>::reset(&v93);
          v46 = (**v92)(v92, &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60, &v93);
          if ( v46 < 0 )
          {
            v73 = "nodeClass.query_to(&classElement)";
            v74 = 751;
LABEL_90:
            LODWORD(v76) = v46;
            wil::details::in1diag5::Return_Hr(
              retaddr,
              (void *)v74,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
              "OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer",
              v73,
              v76,
              v78);
            wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v93);
LABEL_92:
            wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v92);
            wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v89);
            goto LABEL_50;
          }
          v46 = OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateClass(this, v93, v86, a3, v7);
          if ( v46 < 0 )
          {
            v73 = "ParseSurrogateClass(classElement.get(), surrogateServer.get(), hasRegistryCompatibility, hasMachineScope)";
            v74 = 755;
            goto LABEL_90;
          }
          wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v93);
          wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v92);
        }
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v89);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&string);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v82);
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v81);
        v14 = 0;
        goto LABEL_94;
      }
      LODWORD(v76) = v69;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x2E6,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer",
        "classes->get_length(&listLength)",
        v76,
        v78);
    }
    else
    {
      LODWORD(v76) = v68;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x2E3,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer",
        "root->get_childNodes(&classes)",
        v76,
        v78);
    }
    wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v89);
    goto LABEL_19;
  }
  v85 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    &v85,
    0);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v32 = OSIntegration::DEH::PackagedComExtensionHandler::MapEnumStringToHstringValue(
          &v85,
          v30,
          v31,
          StringRawBuffer,
          &v85);
  v14 = v32;
  if ( v32 < 0 )
  {
    LODWORD(v76) = v32;
    v34 = "MapEnumStringToHstringValue(Internal::PackagedComConstants::systemSurrogateMap, ARRAYSIZE(Internal::PackagedCo"
          "mConstants::systemSurrogateMap), wil::str_raw_ptr(systemSurrogateEnumString), &systemSurrogateExecutable)";
    v35 = 637;
LABEL_23:
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer",
      v34,
      v76,
      v78);
    goto LABEL_24;
  }
  LOBYTE(v33) = 1;
  v36 = (*(__int64 (__fastcall **)(struct OSIntegration::DEH::IComSurrogateServerRegistration *, __int64, __int64))(*(_QWORD *)v86 + 56LL))(
          v86,
          v85,
          v33);
  v14 = v36;
  if ( v36 < 0 )
  {
    LODWORD(v76) = v36;
    v34 = "surrogateServer->SetCustomSurrogateExecutable(systemSurrogateExecutable.get(), TRUE)";
    v35 = 639;
    goto LABEL_23;
  }
  if ( !a3 )
  {
LABEL_44:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v85);
    goto LABEL_45;
  }
  v37 = a2->lpVtbl;
  v87 = 0;
  v38 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 **))v37->get_childNodes)(a2, &v87);
  v14 = v38;
  if ( v38 < 0 )
  {
    LODWORD(v76) = v38;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x28D,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer",
      "root->get_childNodes(&classes)",
      v76,
      v78);
    goto LABEL_30;
  }
  v94 = 0;
  v39 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v87 + 64))(v87, &v94);
  v14 = v39;
  if ( v39 < 0 )
  {
    LODWORD(v76) = v39;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x290,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
      "OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer",
      "classes->get_length(&listLength)",
      v76,
      v78);
    goto LABEL_30;
  }
  v41 = 0;
  v88 = 0;
  for ( j = 0; ; ++j )
  {
    if ( (int)j >= v94 )
      goto LABEL_41;
    v90 = 0;
    v43 = *v87;
    v90 = 0;
    v44 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(v43 + 56))(v87, j, &v90);
    ArchitectureOfSurrogateClass = v44;
    if ( v44 < 0 )
    {
      LODWORD(v76) = v44;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x296,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer",
        "classes->get_item(classIndex, &nodeClass)",
        v76,
        v78);
      goto LABEL_55;
    }
    v91 = 0;
    wil::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>::reset(&v91);
    ArchitectureOfSurrogateClass = (**v90)(v90, &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60, &v91);
    if ( ArchitectureOfSurrogateClass < 0 )
    {
      v52 = "nodeClass.query_to(&classElement)";
      v53 = 665;
      goto LABEL_53;
    }
    ArchitectureOfSurrogateClass = OSIntegration::DEH::PackagedComExtensionHandler::TryGetArchitectureOfSurrogateClass(
                                     this,
                                     v91,
                                     &v88);
    if ( ArchitectureOfSurrogateClass < 0 )
    {
      v52 = "TryGetArchitectureOfSurrogateClass(classElement.get(), &calculatedClassArchitecture)";
      v53 = 668;
LABEL_53:
      LODWORD(v76) = ArchitectureOfSurrogateClass;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)v53,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer",
        v52,
        v76,
        v78);
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v91);
LABEL_55:
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v90);
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v87);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v85);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&string);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v82);
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v81);
      v14 = ArchitectureOfSurrogateClass;
      goto LABEL_94;
    }
    if ( v88 )
      break;
    wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v91);
    wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v90);
    v41 = v88;
  }
  wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v91);
  wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v90);
  v41 = v88;
LABEL_41:
  if ( !v41 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v40);
LABEL_43:
    wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v87);
    v7 = v84;
    goto LABEL_44;
  }
  v54 = (*(__int64 (__fastcall **)(struct OSIntegration::DEH::IComSurrogateServerRegistration *))(*(_QWORD *)v86 + 72LL))(v86);
  v14 = v54;
  if ( v54 >= 0 )
    goto LABEL_43;
  LODWORD(v76) = v54;
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)0x2B1,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
    "OSIntegration::DEH::PackagedComExtensionHandler::ParseSurrogateServer",
    "surrogateServer->SetCustomSurrogateSystemExecutableArchitecture( calculatedClassArchitecture)",
    v76,
    v78);
LABEL_30:
  wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v87);
LABEL_24:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v85);
LABEL_19:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&string);
LABEL_12:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v82);
LABEL_6:
  wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v81);
LABEL_94:
  wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v86);
  return v14;
}

```

## disassembly

```asm
0x18016c4e4  push    rbp
0x18016c4e6  push    rbx
0x18016c4e7  push    rsi
0x18016c4e8  push    rdi
0x18016c4e9  push    r12
0x18016c4eb  push    r13
0x18016c4ed  lea     rbp, [rsp-8]
0x18016c4f2  sub     rsp, 108h
0x18016c4f9  mov     rax, cs:__security_cookie
0x18016c500  xor     rax, rsp
0x18016c503  mov     [rbp+30h+var_40], rax
0x18016c507  mov     sil, r9b
0x18016c50a  mov     [rsp+130h+var_D0], r9b
0x18016c50f  mov     r12b, r8b
0x18016c512  mov     rdi, rdx
0x18016c515  mov     r13, rcx
0x18016c518  mov     [rsp+130h+var_C0], 0
0x18016c521  mov     rcx, [rcx+30h]
0x18016c525  mov     rax, [rcx]
0x18016c528  mov     [rsp+130h+var_C0], 0
0x18016c531  lea     rdx, [rsp+130h+var_C0]
0x18016c536  mov     rax, [rax+38h]
0x18016c53a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016c53f  mov     ebx, eax
0x18016c541  test    eax, eax
0x18016c543  jns     short loc_18016C576
0x18016c545  mov     rcx, [rbp+38h]; this
0x18016c549  mov     dword ptr [rsp+130h+var_108], eax; char *
0x18016c54d  lea     rax, aCollectorCreat_2; "_collector->CreateSurrogateServerRegist"...
0x18016c554  mov     [rsp+130h+var_110], rax; char *
0x18016c559  lea     r9, aOsintegrationD_181; "OSIntegration::DEH::PackagedComExtensio"...
0x18016c560  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016c567  mov     edx, 261h; void *
0x18016c56c  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016c571  jmp     loc_18016CF55
0x18016c576  mov     [rsp+130h+var_E8], 0
0x18016c57f  mov     rcx, [rsp+130h+var_C0]
0x18016c584  mov     rax, [rcx]
0x18016c587  lea     r8, [rsp+130h+var_E8]
0x18016c58c  lea     rdx, _GUID_f76c7cd7_3680_4053_9ec9_1ffb74ee02a7
0x18016c593  mov     rax, [rax]
0x18016c596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016c59b  mov     ebx, eax
0x18016c59d  test    eax, eax
0x18016c59f  jns     short loc_18016C5DD
0x18016c5a1  mov     dword ptr [rsp+130h+var_108], eax; char *
0x18016c5a5  lea     rax, aSurrogateserve_4; "surrogateServer.query_to(&server)"
0x18016c5ac  mov     edx, 265h; void *
0x18016c5b1  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016c5b8  lea     r9, aOsintegrationD_181; "OSIntegration::DEH::PackagedComExtensio"...
0x18016c5bf  mov     [rsp+130h+var_110], rax; char *
0x18016c5c4  mov     rcx, [rbp+38h]; this
0x18016c5c8  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016c5cd  nop
0x18016c5ce  lea     rcx, [rsp+130h+var_E8]
0x18016c5d3  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18016c5d8  jmp     loc_18016CF55
0x18016c5dd  mov     rax, [rbp+30h+arg_30]
0x18016c5e1  mov     [rsp+130h+var_108], rax
0x18016c5e6  mov     rax, [rbp+30h+arg_28]
0x18016c5ea  mov     [rsp+130h+var_110], rax
0x18016c5ef  mov     r9, [rbp+30h+arg_20]
0x18016c5f3  mov     r8, [rsp+130h+var_E8]
0x18016c5f8  mov     rdx, rdi
0x18016c5fb  mov     rcx, r13
0x18016c5fe  call    ?ParseServer@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEAUIComServerRegistration@23@V?$optional@W4TrustLevel@AppModel@@@std@@V?$optional@W4RuntimeBehavior@AppModel@@@7@V?$optional@W4BnoIsolation@AppModel@@@7@@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseServer(IXMLDOMElement *,OSIntegration::DEH::IComServerRegistration *,std::optional<AppModel::TrustLevel>,std::optional<AppModel::RuntimeBehavior>,std::optional<AppModel::BnoIsolation>)
0x18016c603  mov     ebx, eax
0x18016c605  test    eax, eax
0x18016c607  jns     short loc_18016C61B
0x18016c609  mov     dword ptr [rsp+130h+var_108], eax
0x18016c60d  lea     rax, aParseserverRoo; "ParseServer(root, server.get(), extensi"...
0x18016c614  mov     edx, 266h
0x18016c619  jmp     short loc_18016C5B1
0x18016c61b  mov     [rsp+130h+var_E0], 0
0x18016c624  mov     [rsp+130h+var_EF], 0
0x18016c629  xor     edx, edx
0x18016c62b  lea     rcx, [rsp+130h+var_E0]
0x18016c630  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18016c635  lea     rax, [rsp+130h+var_EF]
0x18016c63a  mov     [rsp+130h+var_110], rax; bool *
0x18016c63f  lea     r9, [rsp+130h+var_E0]; HSTRING *
0x18016c644  lea     r8, aCustomsurrogat; "CustomSurrogateExecutable"
0x18016c64b  mov     rdx, rdi; struct IXMLDOMElement *
0x18016c64e  call    ?ParseAndRetrievePath@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrievePath(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x18016c653  mov     ebx, eax
0x18016c655  test    eax, eax
0x18016c657  jns     short loc_18016C695
0x18016c659  mov     dword ptr [rsp+130h+var_108], eax; char *
0x18016c65d  lea     rax, aParseandretrie_0; "ParseAndRetrievePath(root, Internal::Pa"...
0x18016c664  mov     edx, 26Dh; void *
0x18016c669  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016c670  lea     r9, aOsintegrationD_181; "OSIntegration::DEH::PackagedComExtensio"...
0x18016c677  mov     [rsp+130h+var_110], rax; char *
0x18016c67c  mov     rcx, [rbp+38h]; this
0x18016c680  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016c685  nop
0x18016c686  lea     rcx, [rsp+130h+var_E0]
0x18016c68b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x18016c690  jmp     loc_18016C5CE
0x18016c695  cmp     [rsp+130h+var_EF], 0
0x18016c69a  jz      short loc_18016C6CD
0x18016c69c  mov     rcx, [rsp+130h+var_C0]
0x18016c6a1  mov     rax, [rcx]
0x18016c6a4  xor     r8d, r8d
0x18016c6a7  mov     rdx, [rsp+130h+var_E0]
0x18016c6ac  mov     rax, [rax+38h]
0x18016c6b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016c6b5  mov     ebx, eax
0x18016c6b7  test    eax, eax
0x18016c6b9  jns     short loc_18016C6CD
0x18016c6bb  mov     dword ptr [rsp+130h+var_108], eax
0x18016c6bf  lea     rax, aSurrogateserve_3; "surrogateServer->SetCustomSurrogateExec"...
0x18016c6c6  mov     edx, 270h
0x18016c6cb  jmp     short loc_18016C669
0x18016c6cd  mov     [rsp+130h+string], 0
0x18016c6d6  mov     [rsp+130h+var_F0], 0
0x18016c6db  xor     edx, edx
0x18016c6dd  lea     rcx, [rsp+130h+string]
0x18016c6e2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18016c6e7  lea     rax, [rsp+130h+var_F0]
0x18016c6ec  mov     [rsp+130h+var_110], rax; bool *
0x18016c6f1  lea     r9, [rsp+130h+string]; HSTRING *
0x18016c6f6  lea     r8, aSystemsurrogat; "SystemSurrogate"
0x18016c6fd  mov     rdx, rdi; struct IXMLDOMElement *
0x18016c700  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x18016c705  mov     ebx, eax
0x18016c707  test    eax, eax
0x18016c709  jns     short loc_18016C747
0x18016c70b  mov     dword ptr [rsp+130h+var_108], eax; char *
0x18016c70f  lea     rax, aParseandretrie_18; "ParseAndRetrieveAttribute(root, Interna"...
0x18016c716  mov     edx, 277h; void *
0x18016c71b  mov     rcx, [rbp+38h]; this
0x18016c71f  mov     [rsp+130h+var_110], rax; char *
0x18016c724  lea     r9, aOsintegrationD_181; "OSIntegration::DEH::PackagedComExtensio"...
0x18016c72b  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016c732  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016c737  nop
0x18016c738  lea     rcx, [rsp+130h+string]
0x18016c73d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x18016c742  jmp     loc_18016C686
0x18016c747  cmp     [rsp+130h+var_F0], 0
0x18016c74c  jz      loc_18016C979
0x18016c752  mov     [rsp+130h+var_C8], 0
0x18016c75b  xor     edx, edx
0x18016c75d  lea     rcx, [rsp+130h+var_C8]
0x18016c762  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18016c767  xor     edx, edx; length
0x18016c769  mov     rcx, [rsp+130h+string]; string
0x18016c76e  call    cs:__imp_WindowsGetStringRawBuffer
0x18016c774  lea     rcx, [rsp+130h+var_C8]
0x18016c779  mov     [rsp+130h+var_110], rcx
0x18016c77e  mov     r9, rax
0x18016c781  call    ?MapEnumStringToHstringValue@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJQEBU?$EnumStringMapping@PEBG@23@_KPEBGPEAPEAUHSTRING__@@@Z; OSIntegration::DEH::PackagedComExtensionHandler::MapEnumStringToHstringValue(OSIntegration::DEH::EnumStringMapping<ushort const *> const * const,unsigned __int64,ushort const *,HSTRING__ * *)
0x18016c786  mov     ebx, eax
0x18016c788  test    eax, eax
0x18016c78a  jns     short loc_18016C7C8
0x18016c78c  mov     dword ptr [rsp+130h+var_108], eax; char *
0x18016c790  lea     rax, aMapenumstringt_1; "MapEnumStringToHstringValue(Internal::P"...
0x18016c797  mov     edx, 27Dh; void *
0x18016c79c  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016c7a3  lea     r9, aOsintegrationD_181; "OSIntegration::DEH::PackagedComExtensio"...
0x18016c7aa  mov     [rsp+130h+var_110], rax; char *
0x18016c7af  mov     rcx, [rbp+38h]; this
0x18016c7b3  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016c7b8  nop
0x18016c7b9  lea     rcx, [rsp+130h+var_C8]
0x18016c7be  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x18016c7c3  jmp     loc_18016C738
0x18016c7c8  mov     rcx, [rsp+130h+var_C0]
0x18016c7cd  mov     rax, [rcx]
0x18016c7d0  mov     r8b, 1
0x18016c7d3  mov     rdx, [rsp+130h+var_C8]
0x18016c7d8  mov     rax, [rax+38h]
0x18016c7dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016c7e1  mov     ebx, eax
0x18016c7e3  test    eax, eax
0x18016c7e5  jns     short loc_18016C7F9
0x18016c7e7  mov     dword ptr [rsp+130h+var_108], eax
0x18016c7eb  lea     rax, aSurrogateserve; "surrogateServer->SetCustomSurrogateExec"...
0x18016c7f2  mov     edx, 27Fh
0x18016c7f7  jmp     short loc_18016C79C
0x18016c7f9  test    r12b, r12b
0x18016c7fc  jz      loc_18016C96F
0x18016c802  mov     rax, [rdi]
0x18016c805  xor     esi, esi
0x18016c807  mov     [rsp+130h+var_B8], rsi
0x18016c80c  lea     rdx, [rsp+130h+var_B8]
0x18016c811  mov     rcx, rdi
0x18016c814  mov     rax, [rax+60h]
0x18016c818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016c81d  mov     ebx, eax
0x18016c81f  test    eax, eax
0x18016c821  jns     short loc_18016C85F
0x18016c823  mov     dword ptr [rsp+130h+var_108], eax; char *
0x18016c827  lea     rdx, aRootGetChildno_8; "root->get_childNodes(&classes)"
0x18016c82e  mov     [rsp+130h+var_110], rdx; char *
0x18016c833  mov     edx, 28Dh; void *
0x18016c838  mov     rcx, [rbp+38h]; this
0x18016c83c  lea     r9, aOsintegrationD_181; "OSIntegration::DEH::PackagedComExtensio"...
0x18016c843  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016c84a  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016c84f  nop
0x18016c850  lea     rcx, [rsp+130h+var_B8]
0x18016c855  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18016c85a  jmp     loc_18016C7B9
0x18016c85f  mov     [rbp+30h+var_80], esi
0x18016c862  mov     rcx, [rsp+130h+var_B8]
0x18016c867  mov     rax, [rcx]
0x18016c86a  lea     rdx, [rbp+30h+var_80]
0x18016c86e  mov     rax, [rax+40h]
0x18016c872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016c877  mov     ebx, eax
0x18016c879  test    eax, eax
0x18016c87b  jns     short loc_18016C894
0x18016c87d  mov     dword ptr [rsp+130h+var_108], eax
0x18016c881  lea     rdx, aClassesGetLeng; "classes->get_length(&listLength)"
0x18016c888  mov     [rsp+130h+var_110], rdx
0x18016c88d  mov     edx, 290h
0x18016c892  jmp     short loc_18016C838
0x18016c894  mov     edx, esi
0x18016c896  mov     [rbp+30h+var_B0], edx
0x18016c899  mov     ebx, esi
0x18016c89b  cmp     ebx, [rbp+30h+var_80]
0x18016c89e  jge     loc_18016C952
0x18016c8a4  mov     [rbp+30h+var_A0], rsi
0x18016c8a8  mov     rcx, [rsp+130h+var_B8]
0x18016c8ad  mov     rax, [rcx]
0x18016c8b0  mov     [rbp+30h+var_A0], rsi
0x18016c8b4  lea     r8, [rbp+30h+var_A0]
0x18016c8b8  mov     edx, ebx
0x18016c8ba  mov     rax, [rax+38h]
0x18016c8be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016c8c3  mov     esi, eax
0x18016c8c5  test    eax, eax
0x18016c8c7  js      loc_18016CAF7
0x18016c8cd  mov     [rbp+30h+var_98], 0
0x18016c8d5  lea     rcx, [rbp+30h+var_98]
0x18016c8d9  call    ?reset@?$com_ptr_t@UIXMLDOMElement@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IXMLDOMElement,wil::err_returncode_policy>::reset(void)
0x18016c8de  mov     rcx, [rbp+30h+var_A0]
0x18016c8e2  mov     rax, [rcx]
0x18016c8e5  lea     r8, [rbp+30h+var_98]
0x18016c8e9  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x18016c8f0  mov     rax, [rax]
0x18016c8f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016c8f8  mov     esi, eax
0x18016c8fa  test    eax, eax
0x18016c8fc  js      loc_18016CABF
0x18016c902  lea     r8, [rbp+30h+var_B0]; unsigned int *
0x18016c906  mov     rdx, [rbp+30h+var_98]; struct IXMLDOMElement *
0x18016c90a  mov     rcx, r13; this
0x18016c90d  call    ?TryGetArchitectureOfSurrogateClass@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEAK@Z; OSIntegration::DEH::PackagedComExtensionHandler::TryGetArchitectureOfSurrogateClass(IXMLDOMElement *,ulong *)
0x18016c912  mov     esi, eax
0x18016c914  test    eax, eax
0x18016c916  js      loc_18016CAB1
0x18016c91c  xor     esi, esi
0x18016c91e  lea     rcx, [rbp+30h+var_98]
0x18016c922  cmp     [rbp+30h+var_B0], esi
0x18016c925  jnz     short loc_18016C940
0x18016c927  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18016c92c  nop
0x18016c92d  lea     rcx, [rbp+30h+var_A0]
0x18016c931  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18016c936  inc     ebx
0x18016c938  mov     edx, [rbp+30h+var_B0]
0x18016c93b  jmp     loc_18016C89B
0x18016c940  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18016c945  nop
0x18016c946  lea     rcx, [rbp+30h+var_A0]
0x18016c94a  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18016c94f  mov     edx, [rbp+30h+var_B0]
0x18016c952  test    edx, edx
0x18016c954  jnz     loc_18016CB6B
0x18016c95a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18016c95f  nop
0x18016c960  lea     rcx, [rsp+130h+var_B8]
0x18016c965  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18016c96a  mov     sil, [rsp+130h+var_D0]
0x18016c96f  lea     rcx, [rsp+130h+var_C8]
0x18016c974  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x18016c979  cmp     [rsp+130h+var_EF], 0
0x18016c97e  jz      loc_18016CBA0
0x18016c984  cmp     [rsp+130h+var_F0], 0
0x18016c989  jz      loc_18016CBA0
0x18016c98f  mov     [rbp+30h+var_78], 0
0x18016c997  lea     r9, [rbp+30h+var_78]; struct APPX_XML_LINE_INFORMATION *
0x18016c99b  xor     r8d, r8d; unsigned __int16 *
0x18016c99e  mov     rdx, rdi; struct IXMLDOMNode *
0x18016c9a1  mov     rcx, [r13+28h]; this
0x18016c9a5  call    ?GetXmlLineInformation@Package@OSIntegration@@QEBAJPEBUIXMLDOMNode@@PEBGPEAUAPPX_XML_LINE_INFORMATION@@@Z; OSIntegration::Package::GetXmlLineInformation(IXMLDOMNode const *,ushort const *,APPX_XML_LINE_INFORMATION *)
0x18016c9aa  mov     rcx, [rbp+38h]; this
0x18016c9ae  mov     edi, 80080204h
0x18016c9b3  mov     dword ptr [rsp+130h+var_108], edi; char *
0x18016c9b7  lea     rax, aHresult0x80080; "((HRESULT)0x80080204L)"
0x18016c9be  mov     [rsp+130h+var_110], rax; char *
0x18016c9c3  lea     r9, aOsintegrationD_181; "OSIntegration::DEH::PackagedComExtensio"...
0x18016c9ca  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016c9d1  mov     edx, 2C3h; void *
0x18016c9d6  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016c9db  test    cs:byte_1802E21CA, 4
0x18016c9e2  jz      short loc_18016CA1E
  ... truncated ...
```
