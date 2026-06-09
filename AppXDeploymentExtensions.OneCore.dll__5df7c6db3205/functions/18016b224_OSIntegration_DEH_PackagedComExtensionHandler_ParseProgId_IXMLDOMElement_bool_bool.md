# OSIntegration::DEH::PackagedComExtensionHandler::ParseProgId(IXMLDOMElement *,bool,bool)

- ea: `0x18016b224`
- end: `0x18016b767`
- name: `?ParseProgId@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@_N1@Z`
- size: `1347`
- prototype: `__int64 __fastcall(OSIntegration::DEH::PackagedComExtensionHandler *__hidden this, struct IXMLDOMElement *, bool, bool)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180166d20`

## callees

- `0x18000b9e0`
- `0x18003a300`
- `0x180077608`
- `0x180078a44`
- `0x180089c5c`
- `0x18009aff4`
- `0x1800d9e70`
- `0x1800f0260`
- `0x1801654b0`
- `0x1801655cc`
- `0x18016b224`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016b3d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016b45e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016b3d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016b45e`

## string_xrefs

- `0x18016b2a7`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016b2f3`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016b3b8`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016b4a0`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016b533`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016b624`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016b6bf`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016b66b`: `registryCompatibility->SetHasRegistryCompatibility(true)`
- `0x18016b294`: `ParseAndRetrieveAttribute(root, Internal::PackagedComConstants::idAttribute, &id)`
- `0x18016b2a0`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseProgId`
- `0x18016b2fa`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseProgId`
- `0x18016b3b1`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseProgId`
- `0x18016b499`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseProgId`
- `0x18016b53a`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseProgId`
- `0x18016b62b`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseProgId`
- `0x18016b6c6`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseProgId`
- `0x18016b2e7`: `_collector->CreateProgIdRegistration(id.get(), &progId)`
- `0x18016b34f`: `ParseAndRetrieveGuid(root, Internal::PackagedComConstants::clsidAttribute, &clsid, &clsidFound)`
- `0x18016b39c`: `ParseAndRetrieveAttribute(root, Internal::PackagedComConstants::clsidAttribute, &clsidString)`
- `0x18016b3fb`: `GetClsidIsInsertableObject(root, wil::str_raw_ptr(clsidString), &isInsertableObject)`
- `0x18016b434`: `progId->SetClsidWithIsInsertableObject(clsid, isInsertableObject)`
- `0x18016b48d`: `GetClsidDisplayNameOrShortName(root, wil::str_raw_ptr(clsidString), &displayName, &displayNameFound)`
- `0x18016b527`: `ParseAndRetrieveAttribute(root, Internal::PackagedComConstants::currentVersionAttribute, &currentVersion, &currentVersionFound)`
- `0x18016b618`: `progId.query_to(&registryCompatibility)`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall OSIntegration::DEH::PackagedComExtensionHandler::ParseProgId(
        OSIntegration::DEH::PackagedComExtensionHandler *this,
        struct IXMLDOMElement *a2,
        char a3,
        char a4)
{
  OSIntegration::DEH::PackagedComExtensionHandler *v8; // rcx
  int Attribute; // eax
  unsigned int v10; // ebx
  __int64 *v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  OSIntegration::DEH::PackagedComExtensionHandler *v14; // rcx
  const char *v15; // rax
  __int64 v16; // rdx
  int v17; // eax
  OSIntegration::DEH::PackagedComExtensionHandler *v18; // rcx
  int v19; // eax
  const char *v20; // rax
  __int64 v21; // rdx
  HSTRING *p_string; // rcx
  const unsigned __int16 *StringRawBuffer; // rax
  int IsInsertableObject; // eax
  __int64 v25; // r8
  int v26; // eax
  const unsigned __int16 *v27; // rax
  int ClsidDisplayNameOrShortName; // eax
  OSIntegration::DEH::PackagedComExtensionHandler *v29; // rcx
  int v30; // eax
  const char *v31; // rax
  __int64 v32; // rdx
  int v33; // eax
  int v34; // eax
  int v35; // eax
  int v36; // eax
  __int64 v37; // rdx
  const char *v38; // rax
  __int64 v39; // rdx
  int v40; // eax
  int v41; // eax
  __int64 v42; // rdx
  const char *v43; // rax
  __int64 v44; // rdx
  int v45; // eax
  char *v47; // [rsp+28h] [rbp-41h]
  struct IXMLDOMElement v48; // [rsp+30h] [rbp-39h] BYREF
  __int64 v49; // [rsp+38h] [rbp-31h] BYREF
  HSTRING v50; // [rsp+40h] [rbp-29h] BYREF
  HSTRING string; // [rsp+48h] [rbp-21h] BYREF
  HSTRING v52; // [rsp+50h] [rbp-19h] BYREF
  __int64 v53; // [rsp+58h] [rbp-11h] BYREF
  HSTRING v54[2]; // [rsp+60h] [rbp-9h] BYREF
  struct _GUID v55; // [rsp+70h] [rbp+7h] BYREF
  struct _GUID v56; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v54[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    v54,
    0);
  Attribute = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(
                v8,
                a2,
                (const unsigned __int16 *)&stru_180231B98,
                v54,
                0);
  v10 = Attribute;
  if ( Attribute >= 0 )
  {
    v49 = 0;
    v11 = (__int64 *)*((_QWORD *)this + 6);
    v12 = *v11;
    v49 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v12 + 88))(v11, v54[0], &v49);
    v10 = v13;
    if ( v13 < 0 )
    {
      LODWORD(v47) = v13;
      v15 = "_collector->CreateProgIdRegistration(id.get(), &progId)";
      v16 = 1894;
LABEL_5:
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::ParseProgId",
        v15,
        v47,
        (int)v48.lpVtbl);
LABEL_6:
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v49);
      goto LABEL_50;
    }
    v56 = 0;
    LOBYTE(v48.lpVtbl) = 0;
    v17 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveGuid(
            v14,
            a2,
            (const unsigned __int16 *)&stru_180255228,
            &v56,
            (bool *)&v48);
    v10 = v17;
    if ( v17 < 0 )
    {
      LODWORD(v47) = v17;
      v15 = "ParseAndRetrieveGuid(root, Internal::PackagedComConstants::clsidAttribute, &clsid, &clsidFound)";
      v16 = 1899;
      goto LABEL_5;
    }
    if ( LOBYTE(v48.lpVtbl) )
    {
      LOBYTE(v48.lpVtbl) = 0;
      string = 0;
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &string,
        0);
      v19 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(
              v18,
              a2,
              (const unsigned __int16 *)&stru_180255228,
              &string,
              0);
      v10 = v19;
      if ( v19 < 0 )
      {
        LODWORD(v47) = v19;
        v20 = "ParseAndRetrieveAttribute(root, Internal::PackagedComConstants::clsidAttribute, &clsidString)";
        v21 = 1908;
LABEL_12:
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::ParseProgId",
          v20,
          v47,
          (int)v48.lpVtbl);
LABEL_13:
        p_string = &string;
LABEL_14:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(p_string);
        goto LABEL_6;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      IsInsertableObject = OSIntegration::DEH::PackagedComExtensionHandler::GetClsidIsInsertableObject(
                             this,
                             a2,
                             StringRawBuffer,
                             (bool *)&v48);
      v10 = IsInsertableObject;
      if ( IsInsertableObject < 0 )
      {
        LODWORD(v47) = IsInsertableObject;
        v20 = "GetClsidIsInsertableObject(root, wil::str_raw_ptr(clsidString), &isInsertableObject)";
        v21 = 1909;
        goto LABEL_12;
      }
      v55 = v56;
      LOBYTE(v25) = v48.lpVtbl;
      v26 = (*(__int64 (__fastcall **)(__int64, struct _GUID *, __int64))(*(_QWORD *)v49 + 64LL))(v49, &v55, v25);
      v10 = v26;
      if ( v26 < 0 )
      {
        LODWORD(v47) = v26;
        v20 = "progId->SetClsidWithIsInsertableObject(clsid, isInsertableObject)";
        v21 = 1910;
        goto LABEL_12;
      }
      v52 = 0;
      LOBYTE(v48.lpVtbl) = 0;
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &v52,
        0);
      v27 = WindowsGetStringRawBuffer(string, 0);
      ClsidDisplayNameOrShortName = OSIntegration::DEH::PackagedComExtensionHandler::GetClsidDisplayNameOrShortName(
                                      this,
                                      a2,
                                      v27,
                                      &v52,
                                      &v48);
      v10 = ClsidDisplayNameOrShortName;
      if ( ClsidDisplayNameOrShortName < 0 )
      {
        LODWORD(v47) = ClsidDisplayNameOrShortName;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x779,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::ParseProgId",
          "GetClsidDisplayNameOrShortName(root, wil::str_raw_ptr(clsidString), &displayName, &displayNameFound)",
          v47,
          (int)v48.lpVtbl);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v52);
        goto LABEL_13;
      }
      if ( LOBYTE(v48.lpVtbl) )
        (*(void (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v49 + 72LL))(v49, v52);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v52);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&string);
    }
    v50 = 0;
    LOBYTE(v48.lpVtbl) = 0;
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &v50,
      0);
    v30 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(
            v29,
            a2,
            L"CurrentVersion",
            &v50,
            (bool *)&v48);
    v10 = v30;
    if ( v30 < 0 )
    {
      LODWORD(v47) = v30;
      v31 = "ParseAndRetrieveAttribute(root, Internal::PackagedComConstants::currentVersionAttribute, &currentVersion, &c"
            "urrentVersionFound)";
      v32 = 1923;
LABEL_26:
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)v32,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::ParseProgId",
        v31,
        v47,
        (int)v48.lpVtbl);
LABEL_27:
      p_string = &v50;
      goto LABEL_14;
    }
    if ( LOBYTE(v48.lpVtbl) )
    {
      v33 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 96LL))(*((_QWORD *)this + 7));
      v10 = v33;
      if ( v33 < 0 )
      {
        LODWORD(v47) = v33;
        v31 = "_progIdHelperList->Clear()";
        v32 = 1926;
        goto LABEL_26;
      }
      v34 = OSIntegration::DEH::PackagedComExtensionHandler::FollowProgIdChain(
              this,
              (const struct IXMLDOMNode *)a2,
              v50,
              0);
      v10 = v34;
      if ( v34 < 0 )
      {
        LODWORD(v47) = v34;
        v31 = "FollowProgIdChain(root, currentVersion.get())";
        v32 = 1927;
        goto LABEL_26;
      }
      v35 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v49 + 56LL))(v49, v50);
      v10 = v35;
      if ( v35 < 0 )
      {
        LODWORD(v47) = v35;
        v31 = "progId->SetCurrentVersion(currentVersion.get())";
        v32 = 1928;
        goto LABEL_26;
      }
    }
    if ( a3 )
    {
      v53 = 0;
      v36 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v49)(
              v49,
              &GUID_f74eae70_01a3_405c_aa49_bc7c92dd9de3,
              &v53);
      v10 = v36;
      if ( v36 < 0 )
      {
        LODWORD(v47) = v36;
        v38 = "progId.query_to(&registryCompatibility)";
        v39 = 1934;
LABEL_38:
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)v39,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::ParseProgId",
          v38,
          v47,
          (int)v48.lpVtbl);
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v53);
        goto LABEL_27;
      }
      LOBYTE(v37) = 1;
      v40 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v53 + 48LL))(v53, v37);
      v10 = v40;
      if ( v40 < 0 )
      {
        LODWORD(v47) = v40;
        v38 = "registryCompatibility->SetHasRegistryCompatibility(true)";
        v39 = 1935;
        goto LABEL_38;
      }
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v53);
    }
    if ( a4 )
    {
      *(_QWORD *)&v55.Data1 = 0;
      v41 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct _GUID *))v49)(
              v49,
              &GUID_6b3024bd_050b_4ef2_8ec9_2aa58da513ac,
              &v55);
      v10 = v41;
      if ( v41 < 0 )
      {
        LODWORD(v47) = v41;
        v43 = "progId.query_to(&scope)";
        v44 = 1941;
LABEL_45:
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)v44,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::ParseProgId",
          v43,
          v47,
          (int)v48.lpVtbl);
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v55);
        goto LABEL_27;
      }
      LOBYTE(v42) = 1;
      v45 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)&v55.Data1 + 48LL))(*(_QWORD *)&v55.Data1, v42);
      v10 = v45;
      if ( v45 < 0 )
      {
        LODWORD(v47) = v45;
        v43 = "scope->SetHasMachineScope(true)";
        v44 = 1942;
        goto LABEL_45;
      }
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v55);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v50);
    wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v49);
    v10 = 0;
    goto LABEL_50;
  }
  LODWORD(v47) = Attribute;
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)0x763,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
    "OSIntegration::DEH::PackagedComExtensionHandler::ParseProgId",
    "ParseAndRetrieveAttribute(root, Internal::PackagedComConstants::idAttribute, &id)",
    v47,
    (int)v48.lpVtbl);
LABEL_50:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(v54);
  return v10;
}

```

## disassembly

```asm
0x18016b224  mov     [rsp-8+arg_10], rbx
0x18016b229  mov     [rsp-8+arg_18], rsi
0x18016b22e  push    rbp
0x18016b22f  push    rdi
0x18016b230  push    r12
0x18016b232  push    r14
0x18016b234  push    r15
0x18016b236  lea     rbp, [rsp-37h]
0x18016b23b  sub     rsp, 0A0h
0x18016b242  mov     rax, cs:__security_cookie
0x18016b249  xor     rax, rsp
0x18016b24c  mov     [rbp+57h+var_30], rax
0x18016b250  mov     r15b, r9b
0x18016b253  mov     r14b, r8b
0x18016b256  mov     rdi, rdx
0x18016b259  mov     rsi, rcx
0x18016b25c  xor     r12d, r12d
0x18016b25f  mov     [rbp+57h+var_60], r12
0x18016b263  xor     edx, edx
0x18016b265  lea     rcx, [rbp+57h+var_60]
0x18016b269  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18016b26e  mov     [rsp+0C0h+var_A0], r12; bool *
0x18016b273  lea     r9, [rbp+57h+var_60]; HSTRING *
0x18016b277  lea     r8, stru_180231B98; unsigned __int16 *
0x18016b27e  mov     rdx, rdi; struct IXMLDOMElement *
0x18016b281  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x18016b286  mov     ebx, eax
0x18016b288  test    eax, eax
0x18016b28a  jns     short loc_18016B2BD
0x18016b28c  mov     rcx, [rbp+5Fh]; this
0x18016b290  mov     dword ptr [rsp+0C0h+var_98], eax; char *
0x18016b294  lea     rax, aParseandretrie_86; "ParseAndRetrieveAttribute(root, Interna"...
0x18016b29b  mov     [rsp+0C0h+var_A0], rax; char *
0x18016b2a0  lea     r9, aOsintegrationD_394; "OSIntegration::DEH::PackagedComExtensio"...
0x18016b2a7  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016b2ae  mov     edx, 763h; void *
0x18016b2b3  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016b2b8  jmp     loc_18016B734
0x18016b2bd  mov     [rbp+57h+var_88], r12
0x18016b2c1  mov     rcx, [rsi+30h]
0x18016b2c5  mov     rax, [rcx]
0x18016b2c8  mov     [rbp+57h+var_88], r12
0x18016b2cc  lea     r8, [rbp+57h+var_88]
0x18016b2d0  mov     rdx, [rbp+57h+var_60]
0x18016b2d4  mov     rax, [rax+58h]
0x18016b2d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b2dd  mov     ebx, eax
0x18016b2df  test    eax, eax
0x18016b2e1  jns     short loc_18016B31E
0x18016b2e3  mov     dword ptr [rsp+0C0h+var_98], eax; char *
0x18016b2e7  lea     rax, aCollectorCreat_5; "_collector->CreateProgIdRegistration(id"...
0x18016b2ee  mov     edx, 766h; void *
0x18016b2f3  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016b2fa  lea     r9, aOsintegrationD_394; "OSIntegration::DEH::PackagedComExtensio"...
0x18016b301  mov     [rsp+0C0h+var_A0], rax; char *
0x18016b306  mov     rcx, [rbp+5Fh]; this
0x18016b30a  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016b30f  nop
0x18016b310  lea     rcx, [rbp+57h+var_88]
0x18016b314  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18016b319  jmp     loc_18016B734
0x18016b31e  xorps   xmm0, xmm0
0x18016b321  movups  xmmword ptr [rbp+57h+var_40.Data1], xmm0
0x18016b325  mov     byte ptr [rbp+57h+var_90.lpVtbl], r12b
0x18016b329  lea     rax, [rbp+57h+var_90]
0x18016b32d  mov     [rsp+0C0h+var_A0], rax; bool *
0x18016b332  lea     r9, [rbp+57h+var_40]; struct _GUID *
0x18016b336  lea     r8, stru_180255228; unsigned __int16 *
0x18016b33d  mov     rdx, rdi; struct IXMLDOMElement *
0x18016b340  call    ?ParseAndRetrieveGuid@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAU_GUID@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveGuid(IXMLDOMElement *,ushort const *,_GUID *,bool *)
0x18016b345  mov     ebx, eax
0x18016b347  test    eax, eax
0x18016b349  jns     short loc_18016B35D
0x18016b34b  mov     dword ptr [rsp+0C0h+var_98], eax
0x18016b34f  lea     rax, aParseandretrie_23; "ParseAndRetrieveGuid(root, Internal::Pa"...
0x18016b356  mov     edx, 76Bh
0x18016b35b  jmp     short loc_18016B2F3
0x18016b35d  cmp     byte ptr [rbp+57h+var_90.lpVtbl], r12b
0x18016b361  jz      loc_18016B4EE
0x18016b367  mov     byte ptr [rbp+57h+var_90.lpVtbl], r12b
0x18016b36b  mov     [rbp+57h+string], r12
0x18016b36f  xor     edx, edx
0x18016b371  lea     rcx, [rbp+57h+string]
0x18016b375  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18016b37a  mov     [rsp+0C0h+var_A0], r12; bool *
0x18016b37f  lea     r9, [rbp+57h+string]; HSTRING *
0x18016b383  lea     r8, stru_180255228; unsigned __int16 *
0x18016b38a  mov     rdx, rdi; struct IXMLDOMElement *
0x18016b38d  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x18016b392  mov     ebx, eax
0x18016b394  test    eax, eax
0x18016b396  jns     short loc_18016B3D3
0x18016b398  mov     dword ptr [rsp+0C0h+var_98], eax; char *
0x18016b39c  lea     rax, aParseandretrie_55; "ParseAndRetrieveAttribute(root, Interna"...
0x18016b3a3  mov     edx, 774h; void *
0x18016b3a8  mov     rcx, [rbp+5Fh]; this
0x18016b3ac  mov     [rsp+0C0h+var_A0], rax; char *
0x18016b3b1  lea     r9, aOsintegrationD_394; "OSIntegration::DEH::PackagedComExtensio"...
0x18016b3b8  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016b3bf  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016b3c4  nop
0x18016b3c5  lea     rcx, [rbp+57h+string]
0x18016b3c9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x18016b3ce  jmp     loc_18016B310
0x18016b3d3  xor     edx, edx; length
0x18016b3d5  mov     rcx, [rbp+57h+string]; string
0x18016b3d9  call    cs:__imp_WindowsGetStringRawBuffer
0x18016b3df  lea     r9, [rbp+57h+var_90]; bool *
0x18016b3e3  mov     r8, rax; unsigned __int16 *
0x18016b3e6  mov     rdx, rdi; struct IXMLDOMElement *
0x18016b3e9  mov     rcx, rsi; this
0x18016b3ec  call    ?GetClsidIsInsertableObject@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::GetClsidIsInsertableObject(IXMLDOMElement *,ushort const *,bool *)
0x18016b3f1  mov     ebx, eax
0x18016b3f3  test    eax, eax
0x18016b3f5  jns     short loc_18016B409
0x18016b3f7  mov     dword ptr [rsp+0C0h+var_98], eax
0x18016b3fb  lea     rax, aGetclsidisinse; "GetClsidIsInsertableObject(root, wil::s"...
0x18016b402  mov     edx, 775h
0x18016b407  jmp     short loc_18016B3A8
0x18016b409  mov     rcx, [rbp+57h+var_88]
0x18016b40d  movaps  xmm0, xmmword ptr [rbp+57h+var_40.Data1]
0x18016b411  movdqa  [rbp+57h+var_50], xmm0
0x18016b416  mov     rax, [rcx]
0x18016b419  mov     r8b, byte ptr [rbp+57h+var_90.lpVtbl]
0x18016b41d  lea     rdx, [rbp+57h+var_50]
0x18016b421  mov     rax, [rax+40h]
0x18016b425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b42a  mov     ebx, eax
0x18016b42c  test    eax, eax
0x18016b42e  jns     short loc_18016B445
0x18016b430  mov     dword ptr [rsp+0C0h+var_98], eax
0x18016b434  lea     rax, aProgidSetclsid; "progId->SetClsidWithIsInsertableObject("...
0x18016b43b  mov     edx, 776h
0x18016b440  jmp     loc_18016B3A8
0x18016b445  mov     [rbp+57h+var_70], r12
0x18016b449  mov     byte ptr [rbp+57h+var_90.lpVtbl], r12b
0x18016b44d  xor     edx, edx
0x18016b44f  lea     rcx, [rbp+57h+var_70]
0x18016b453  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18016b458  xor     edx, edx; length
0x18016b45a  mov     rcx, [rbp+57h+string]; string
0x18016b45e  call    cs:__imp_WindowsGetStringRawBuffer
0x18016b464  lea     rcx, [rbp+57h+var_90]
0x18016b468  mov     [rsp+0C0h+var_A0], rcx; struct IXMLDOMElement *
0x18016b46d  lea     r9, [rbp+57h+var_70]; HSTRING *
0x18016b471  mov     r8, rax; unsigned __int16 *
0x18016b474  mov     rdx, rdi; struct IXMLDOMElement *
0x18016b477  mov     rcx, rsi; this
0x18016b47a  call    ?GetClsidDisplayNameOrShortName@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::GetClsidDisplayNameOrShortName(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x18016b47f  mov     ebx, eax
0x18016b481  test    eax, eax
0x18016b483  jns     short loc_18016B4C0
0x18016b485  mov     rcx, [rbp+5Fh]; this
0x18016b489  mov     dword ptr [rsp+0C0h+var_98], eax; char *
0x18016b48d  lea     rax, aGetclsiddispla; "GetClsidDisplayNameOrShortName(root, wi"...
0x18016b494  mov     [rsp+0C0h+var_A0], rax; char *
0x18016b499  lea     r9, aOsintegrationD_394; "OSIntegration::DEH::PackagedComExtensio"...
0x18016b4a0  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016b4a7  mov     edx, 779h; void *
0x18016b4ac  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016b4b1  nop
0x18016b4b2  lea     rcx, [rbp+57h+var_70]
0x18016b4b6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x18016b4bb  jmp     loc_18016B3C5
0x18016b4c0  cmp     byte ptr [rbp+57h+var_90.lpVtbl], r12b
0x18016b4c4  jz      short loc_18016B4DB
0x18016b4c6  mov     rcx, [rbp+57h+var_88]
0x18016b4ca  mov     rax, [rcx]
0x18016b4cd  mov     rdx, [rbp+57h+var_70]
0x18016b4d1  mov     rax, [rax+48h]
0x18016b4d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b4da  nop
0x18016b4db  lea     rcx, [rbp+57h+var_70]
0x18016b4df  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x18016b4e4  nop
0x18016b4e5  lea     rcx, [rbp+57h+string]
0x18016b4e9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x18016b4ee  mov     [rbp+57h+var_80], r12
0x18016b4f2  mov     byte ptr [rbp+57h+var_90.lpVtbl], r12b
0x18016b4f6  xor     edx, edx
0x18016b4f8  lea     rcx, [rbp+57h+var_80]
0x18016b4fc  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18016b501  lea     rax, [rbp+57h+var_90]
0x18016b505  mov     [rsp+0C0h+var_A0], rax; bool *
0x18016b50a  lea     r9, [rbp+57h+var_80]; HSTRING *
0x18016b50e  lea     r8, aCurrentversion; "CurrentVersion"
0x18016b515  mov     rdx, rdi; struct IXMLDOMElement *
0x18016b518  call    ?ParseAndRetrieveAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x18016b51d  mov     ebx, eax
0x18016b51f  test    eax, eax
0x18016b521  jns     short loc_18016B559
0x18016b523  mov     dword ptr [rsp+0C0h+var_98], eax; char *
0x18016b527  lea     rax, aParseandretrie_59; "ParseAndRetrieveAttribute(root, Interna"...
0x18016b52e  mov     edx, 783h; void *
0x18016b533  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016b53a  lea     r9, aOsintegrationD_394; "OSIntegration::DEH::PackagedComExtensio"...
0x18016b541  mov     [rsp+0C0h+var_A0], rax; char *
0x18016b546  mov     rcx, [rbp+5Fh]; this
0x18016b54a  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016b54f  nop
0x18016b550  lea     rcx, [rbp+57h+var_80]
0x18016b554  jmp     loc_18016B3C9
0x18016b559  cmp     byte ptr [rbp+57h+var_90.lpVtbl], r12b
0x18016b55d  jz      loc_18016B5E7
0x18016b563  mov     rcx, [rsi+38h]
0x18016b567  mov     rax, [rcx]
0x18016b56a  mov     rax, [rax+60h]
0x18016b56e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b573  mov     ebx, eax
0x18016b575  test    eax, eax
0x18016b577  jns     short loc_18016B58B
0x18016b579  mov     dword ptr [rsp+0C0h+var_98], eax
0x18016b57d  lea     rax, aProgidhelperli_0; "_progIdHelperList->Clear()"
0x18016b584  mov     edx, 786h
0x18016b589  jmp     short loc_18016B533
0x18016b58b  xor     r9d, r9d; HSTRING *
0x18016b58e  mov     r8, [rbp+57h+var_80]; HSTRING
0x18016b592  mov     rdx, rdi; struct IXMLDOMElement *
0x18016b595  mov     rcx, rsi; this
0x18016b598  call    ?FollowProgIdChain@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEAUHSTRING__@@PEAPEAU5@@Z; OSIntegration::DEH::PackagedComExtensionHandler::FollowProgIdChain(IXMLDOMElement *,HSTRING__ *,HSTRING__ * *)
0x18016b59d  mov     ebx, eax
0x18016b59f  test    eax, eax
0x18016b5a1  jns     short loc_18016B5B8
0x18016b5a3  mov     dword ptr [rsp+0C0h+var_98], eax
0x18016b5a7  lea     rax, aFollowprogidch_0; "FollowProgIdChain(root, currentVersion."...
0x18016b5ae  mov     edx, 787h
0x18016b5b3  jmp     loc_18016B533
0x18016b5b8  mov     rcx, [rbp+57h+var_88]
0x18016b5bc  mov     rax, [rcx]
0x18016b5bf  mov     rdx, [rbp+57h+var_80]
0x18016b5c3  mov     rax, [rax+38h]
0x18016b5c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b5cc  mov     ebx, eax
0x18016b5ce  test    eax, eax
0x18016b5d0  jns     short loc_18016B5E7
0x18016b5d2  mov     dword ptr [rsp+0C0h+var_98], eax
0x18016b5d6  lea     rax, aProgidSetcurre; "progId->SetCurrentVersion(currentVersio"...
0x18016b5dd  mov     edx, 788h
0x18016b5e2  jmp     loc_18016B533
0x18016b5e7  test    r14b, r14b
0x18016b5ea  jz      loc_18016B682
0x18016b5f0  mov     [rbp+57h+var_68], r12
0x18016b5f4  mov     rcx, [rbp+57h+var_88]
0x18016b5f8  mov     rax, [rcx]
0x18016b5fb  lea     r8, [rbp+57h+var_68]
0x18016b5ff  lea     rdx, _GUID_f74eae70_01a3_405c_aa49_bc7c92dd9de3
0x18016b606  mov     rax, [rax]
0x18016b609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b60e  mov     ebx, eax
0x18016b610  test    eax, eax
0x18016b612  jns     short loc_18016B64F
0x18016b614  mov     dword ptr [rsp+0C0h+var_98], eax; char *
0x18016b618  lea     rax, aProgidQueryToR; "progId.query_to(&registryCompatibility)"
0x18016b61f  mov     edx, 78Eh; void *
0x18016b624  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016b62b  lea     r9, aOsintegrationD_394; "OSIntegration::DEH::PackagedComExtensio"...
0x18016b632  mov     [rsp+0C0h+var_A0], rax; char *
0x18016b637  mov     rcx, [rbp+5Fh]; this
0x18016b63b  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016b640  nop
0x18016b641  lea     rcx, [rbp+57h+var_68]
0x18016b645  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18016b64a  jmp     loc_18016B550
0x18016b64f  mov     rcx, [rbp+57h+var_68]
0x18016b653  mov     rax, [rcx]
0x18016b656  mov     dl, 1
0x18016b658  mov     rax, [rax+30h]
0x18016b65c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b661  mov     ebx, eax
0x18016b663  test    eax, eax
0x18016b665  jns     short loc_18016B679
0x18016b667  mov     dword ptr [rsp+0C0h+var_98], eax
0x18016b66b  lea     rax, aRegistrycompat_6; "registryCompatibility->SetHasRegistryCo"...
0x18016b672  mov     edx, 78Fh
0x18016b677  jmp     short loc_18016B624
0x18016b679  lea     rcx, [rbp+57h+var_68]
0x18016b67d  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18016b682  test    r15b, r15b
0x18016b685  jz      loc_18016B71E
0x18016b68b  mov     qword ptr [rbp+57h+var_50], r12
0x18016b68f  mov     rcx, [rbp+57h+var_88]
0x18016b693  mov     rax, [rcx]
0x18016b696  lea     r8, [rbp+57h+var_50]
0x18016b69a  lea     rdx, _GUID_6b3024bd_050b_4ef2_8ec9_2aa58da513ac
0x18016b6a1  mov     rax, [rax]
0x18016b6a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b6a9  mov     ebx, eax
0x18016b6ab  test    eax, eax
0x18016b6ad  jns     short loc_18016B6EA
0x18016b6af  mov     dword ptr [rsp+0C0h+var_98], eax; char *
0x18016b6b3  lea     rax, aProgidQueryToS; "progId.query_to(&scope)"
0x18016b6ba  mov     edx, 795h; void *
0x18016b6bf  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016b6c6  lea     r9, aOsintegrationD_394; "OSIntegration::DEH::PackagedComExtensio"...
0x18016b6cd  mov     [rsp+0C0h+var_A0], rax; char *
0x18016b6d2  mov     rcx, [rbp+5Fh]; this
0x18016b6d6  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016b6db  nop
0x18016b6dc  lea     rcx, [rbp+57h+var_50]
0x18016b6e0  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
  ... truncated ...
```
