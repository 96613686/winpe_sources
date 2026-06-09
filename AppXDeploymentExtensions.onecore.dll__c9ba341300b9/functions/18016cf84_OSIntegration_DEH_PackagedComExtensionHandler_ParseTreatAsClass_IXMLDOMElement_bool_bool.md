# OSIntegration::DEH::PackagedComExtensionHandler::ParseTreatAsClass(IXMLDOMElement *,bool,bool)

- ea: `0x18016cf84`
- end: `0x18016d561`
- name: `?ParseTreatAsClass@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@_N1@Z`
- size: `1501`
- prototype: `__int64 __fastcall(OSIntegration::DEH::PackagedComExtensionHandler *__hidden this, struct IXMLDOMElement *, bool, bool)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180166d20`

## callees

- `0x18003a300`
- `0x1800550f4`
- `0x180077608`
- `0x180078a44`
- `0x18007d350`
- `0x180083aa4`
- `0x180089c5c`
- `0x180098ed0`
- `0x18009924c`
- `0x18009aff4`
- `0x1800f0260`
- `0x1800fc21d`
- `0x18013ced4`
- `0x18013d6f8`
- `0x18016cf84`
- `0x18016f6f4`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016d120`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016d120`

## string_xrefs

- `0x18016cffc`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016d088`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016d0f0`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016d1d4`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016d2cf`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016d37d`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016d41e`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016d4b9`: `onecore\admin\appmodel\osim\src\deh\winrt\packagedcomdeh\packagedcomextensionhandler.cpp`
- `0x18016d36a`: `APPX_E_INVALID_MANIFEST`
- `0x18016d465`: `registryCompatibility->SetHasRegistryCompatibility(true)`
- `0x18016d262`: `ParseAndRetrieveGuid(root, Internal::PackagedComConstants::autoConvertToAttribute, &autoConvertToGuid, &autoConvertToFound)`
- `0x18016d412`: `treatAs.query_to(&registryCompatibility)`
- `0x18016cfe9`: `ParseAndRetrieveGuid( root, Internal::PackagedComConstants::idAttribute, &idGuid)`
- `0x18016cff5`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseTreatAsClass`
- `0x18016d08f`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseTreatAsClass`
- `0x18016d0e9`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseTreatAsClass`
- `0x18016d1db`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseTreatAsClass`
- `0x18016d2c8`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseTreatAsClass`
- `0x18016d376`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseTreatAsClass`
- `0x18016d425`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseTreatAsClass`
- `0x18016d4c0`: `OSIntegration::DEH::PackagedComExtensionHandler::ParseTreatAsClass`
- `0x18016d045`: `_collector->CreateTreatAsClassRegistration(idGuid, &treatAs)`
- `0x18016d07c`: `ParseAndRetrieveGuid( root, Internal::PackagedComConstants::treatAsAttribute, &treatAsGuid)`
- `0x18016d0d4`: `VerifyTreatAsChain(root, &terminalClsid)`
- `0x18016d142`: `GetArchitecturesSupportedForActivationByClsid(root, wil::str_raw_ptr(terminalClsid), &supportedArchitectures)`
- `0x18016d1c8`: `ParseAndRetrieveLocalizableAttribute(root, Internal::PackagedComConstants::displayNameAttribute, &displayName, &displayNameFound)`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall OSIntegration::DEH::PackagedComExtensionHandler::ParseTreatAsClass(
        OSIntegration::Package **this,
        struct IXMLDOMElement *a2,
        char a3,
        char a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  OSIntegration::Package *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  OSIntegration::DEH::PackagedComExtensionHandler *v13; // rcx
  const char *v14; // rax
  __int64 v15; // rdx
  int v16; // eax
  int v17; // eax
  const char *v18; // rax
  __int64 v19; // rdx
  const unsigned __int16 *StringRawBuffer; // rax
  int ArchitecturesSupportedForActivationByClsid; // eax
  int v22; // eax
  int v23; // eax
  OSIntegration::DEH::PackagedComExtensionHandler *v24; // rcx
  const char *v25; // rax
  __int64 v26; // rdx
  int v27; // eax
  int v28; // eax
  OSIntegration::Package *v29; // rcx
  __int64 v30; // rbx
  unsigned int v31; // eax
  const unsigned __int16 *v32; // rax
  __int64 v33; // rdx
  int v34; // eax
  int v35; // eax
  __int64 v36; // rdx
  const char *v37; // rax
  __int64 v38; // rdx
  int v39; // eax
  int v40; // eax
  __int64 v41; // rdx
  const char *v42; // rax
  __int64 v43; // rdx
  int v44; // eax
  bool *v46; // [rsp+20h] [rbp-79h]
  char *v47; // [rsp+28h] [rbp-71h]
  char *v48; // [rsp+28h] [rbp-71h]
  char *v49; // [rsp+28h] [rbp-71h]
  int v50; // [rsp+30h] [rbp-69h]
  bool v51; // [rsp+40h] [rbp-59h] BYREF
  HSTRING string; // [rsp+48h] [rbp-51h] BYREF
  HSTRING v53; // [rsp+50h] [rbp-49h] BYREF
  __int64 v54; // [rsp+58h] [rbp-41h] BYREF
  int v55; // [rsp+60h] [rbp-39h] BYREF
  __int64 v56; // [rsp+68h] [rbp-31h] BYREF
  _QWORD v57[2]; // [rsp+70h] [rbp-29h] BYREF
  struct _GUID v58; // [rsp+80h] [rbp-19h] BYREF
  struct _GUID Buf1; // [rsp+90h] [rbp-9h] BYREF
  struct _GUID Buf2; // [rsp+A0h] [rbp+7h] BYREF
  struct _GUID v61; // [rsp+B0h] [rbp+17h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+F8h] [rbp+5Fh]

  Buf1 = 0;
  v8 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveGuid(
         (OSIntegration::DEH::PackagedComExtensionHandler *)this,
         a2,
         (const unsigned __int16 *)&stru_180231B98,
         &Buf1,
         0);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v54 = 0;
    v10 = this[6];
    v11 = *(_QWORD *)v10;
    v54 = 0;
    v58 = Buf1;
    v12 = (*(__int64 (__fastcall **)(OSIntegration::Package *, struct _GUID *, __int64 *))(v11 + 96))(v10, &v58, &v54);
    v9 = v12;
    if ( v12 < 0 )
    {
      LODWORD(v47) = v12;
      v14 = "_collector->CreateTreatAsClassRegistration(idGuid, &treatAs)";
      v15 = 1808;
LABEL_7:
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::ParseTreatAsClass",
        v14,
        v47,
        v50);
LABEL_48:
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v54);
      return v9;
    }
    v61 = 0;
    v16 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveGuid(v13, a2, L"TreatAs", &v61, 0);
    v9 = v16;
    if ( v16 < 0 )
    {
      LODWORD(v47) = v16;
      v14 = "ParseAndRetrieveGuid( root, Internal::PackagedComConstants::treatAsAttribute, &treatAsGuid)";
      v15 = 1814;
      goto LABEL_7;
    }
    string = 0;
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &string,
      0);
    v17 = OSIntegration::DEH::PackagedComExtensionHandler::VerifyTreatAsChain(this, a2, &string, 0);
    v9 = v17;
    if ( v17 < 0 )
    {
      LODWORD(v47) = v17;
      v18 = "VerifyTreatAsChain(root, &terminalClsid)";
      v19 = 1817;
LABEL_10:
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::ParseTreatAsClass",
        v18,
        v47,
        v50);
LABEL_11:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&string);
      goto LABEL_48;
    }
    v55 = 15;
    if ( a3 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      ArchitecturesSupportedForActivationByClsid = OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid(
                                                     (OSIntegration::DEH::PackagedComExtensionHandler *)this,
                                                     a2,
                                                     StringRawBuffer,
                                                     (enum OSIntegration::DEH::SupportedArchitectureFlags *)&v55);
      v9 = ArchitecturesSupportedForActivationByClsid;
      if ( ArchitecturesSupportedForActivationByClsid < 0 )
      {
        LODWORD(v47) = ArchitecturesSupportedForActivationByClsid;
        v18 = "GetArchitecturesSupportedForActivationByClsid(root, wil::str_raw_ptr(terminalClsid), &supportedArchitectures)";
        v19 = 1828;
        goto LABEL_10;
      }
    }
    v58 = v61;
    v22 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v54 + 72LL))(v54, &v58);
    v9 = v22;
    if ( v22 < 0 )
    {
      LODWORD(v47) = v22;
      v18 = "treatAs->SetTreatAsWithSupportedArchitectures(treatAsGuid, supportedArchitectures)";
      v19 = 1831;
      goto LABEL_10;
    }
    v53 = 0;
    v51 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &v53,
      0);
    v23 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveLocalizableAttribute(
            (OSIntegration::DEH::PackagedComExtensionHandler *)this,
            a2,
            L"DisplayName",
            &v53,
            &v51);
    v9 = v23;
    if ( v23 < 0 )
    {
      LODWORD(v47) = v23;
      v25 = "ParseAndRetrieveLocalizableAttribute(root, Internal::PackagedComConstants::displayNameAttribute, &displayNam"
            "e, &displayNameFound)";
      v26 = 1836;
LABEL_19:
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
        "OSIntegration::DEH::PackagedComExtensionHandler::ParseTreatAsClass",
        v25,
        v47,
        v50);
LABEL_20:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v53);
      goto LABEL_11;
    }
    if ( v51 )
    {
      v27 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v54 + 56LL))(v54, v53);
      v9 = v27;
      if ( v27 < 0 )
      {
        LODWORD(v47) = v27;
        v25 = "treatAs->SetDisplayName(displayName.get())";
        v26 = 1839;
        goto LABEL_19;
      }
    }
    Buf2 = 0;
    v51 = 0;
    v28 = OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveGuid(
            v24,
            a2,
            (const unsigned __int16 *)&stru_18023EEF0,
            &Buf2,
            &v51);
    v9 = v28;
    if ( v28 < 0 )
    {
      LODWORD(v47) = v28;
      v25 = "ParseAndRetrieveGuid(root, Internal::PackagedComConstants::autoConvertToAttribute, &autoConvertToGuid, &autoConvertToFound)";
      v26 = 1845;
      goto LABEL_19;
    }
    if ( v51 )
    {
      if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
      {
        v56 = 0;
        OSIntegration::Package::GetXmlLineInformation(
          this[5],
          (const struct IXMLDOMNode *)a2,
          0,
          (struct APPX_XML_LINE_INFORMATION *)&v56);
        LODWORD(v47) = -2146958844;
        wil::details::in1diag5::_Log_Hr(
          retaddr,
          (void *)0x745,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::ParseTreatAsClass",
          "((HRESULT)0x80080204L)",
          v47,
          v50);
        if ( (byte_1802E21CA & 4) != 0 )
        {
          v29 = this[5];
          v30 = *((_QWORD *)v29 + 28);
          v31 = (unsigned int)RemovePIIfromFilePath(*((const unsigned __int16 **)v29 + 34));
          McTemplateU0zqqdz_EventWriteTransfer(
            HIDWORD(v56),
            (unsigned int)PackagedComInvalidAutoConvertTo,
            v31,
            v56,
            SBYTE4(v56),
            4,
            v30);
        }
        v32 = RemovePIIfromFilePath(*((const unsigned __int16 **)this[5] + 34));
        LODWORD(v48) = HIDWORD(v56);
        LODWORD(v46) = v56;
        details::appxLog<unsigned short const *,unsigned int,unsigned int,long,unsigned short *>(
          -2146958844,
          v33,
          (const struct _EVENT_DESCRIPTOR *)PackagedComInvalidAutoConvertTo,
          v32,
          v46,
          v48);
        LODWORD(v49) = -2146958844;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x747,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::ParseTreatAsClass",
          "APPX_E_INVALID_MANIFEST",
          v49,
          -2146958844);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v53);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&string);
        v9 = -2146958844;
        goto LABEL_48;
      }
      v58 = Buf2;
      v34 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v54 + 64LL))(v54, &v58);
      v9 = v34;
      if ( v34 < 0 )
      {
        LODWORD(v47) = v34;
        v25 = "treatAs->SetAutoConvertTo(autoConvertToGuid)";
        v26 = 1866;
        goto LABEL_19;
      }
    }
    if ( a3 )
    {
      v57[0] = 0;
      v35 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v54)(
              v54,
              &GUID_f74eae70_01a3_405c_aa49_bc7c92dd9de3,
              v57);
      v9 = v35;
      if ( v35 < 0 )
      {
        LODWORD(v47) = v35;
        v37 = "treatAs.query_to(&registryCompatibility)";
        v38 = 1872;
LABEL_36:
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)v38,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::ParseTreatAsClass",
          v37,
          v47,
          v50);
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(v57);
        goto LABEL_20;
      }
      LOBYTE(v36) = 1;
      v39 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v57[0] + 48LL))(v57[0], v36);
      v9 = v39;
      if ( v39 < 0 )
      {
        LODWORD(v47) = v39;
        v37 = "registryCompatibility->SetHasRegistryCompatibility(true)";
        v38 = 1873;
        goto LABEL_36;
      }
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(v57);
    }
    if ( a4 )
    {
      *(_QWORD *)&v58.Data1 = 0;
      v40 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct _GUID *))v54)(
              v54,
              &GUID_6b3024bd_050b_4ef2_8ec9_2aa58da513ac,
              &v58);
      v9 = v40;
      if ( v40 < 0 )
      {
        LODWORD(v47) = v40;
        v42 = "treatAs.query_to(&scope)";
        v43 = 1879;
LABEL_43:
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)v43,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
          "OSIntegration::DEH::PackagedComExtensionHandler::ParseTreatAsClass",
          v42,
          v47,
          v50);
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v58);
        goto LABEL_20;
      }
      LOBYTE(v41) = 1;
      v44 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)&v58.Data1 + 48LL))(*(_QWORD *)&v58.Data1, v41);
      v9 = v44;
      if ( v44 < 0 )
      {
        LODWORD(v47) = v44;
        v42 = "scope->SetHasMachineScope(true)";
        v43 = 1880;
        goto LABEL_43;
      }
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v58);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v53);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&string);
    v9 = 0;
    goto LABEL_48;
  }
  LODWORD(v47) = v8;
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)0x70D,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\packagedcomdeh\\packagedcomextensionhandler.cpp",
    "OSIntegration::DEH::PackagedComExtensionHandler::ParseTreatAsClass",
    "ParseAndRetrieveGuid( root, Internal::PackagedComConstants::idAttribute, &idGuid)",
    v47,
    v50);
  return v9;
}

```

## disassembly

```asm
0x18016cf84  mov     [rsp-8+arg_10], rbx
0x18016cf89  mov     [rsp-8+arg_18], rsi
0x18016cf8e  push    rbp
0x18016cf8f  push    rdi
0x18016cf90  push    r12
0x18016cf92  push    r14
0x18016cf94  push    r15
0x18016cf96  lea     rbp, [rsp-37h]
0x18016cf9b  sub     rsp, 0D0h
0x18016cfa2  mov     rax, cs:__security_cookie
0x18016cfa9  xor     rax, rsp
0x18016cfac  mov     [rbp+57h+var_30], rax
0x18016cfb0  mov     r15b, r9b
0x18016cfb3  mov     r14b, r8b
0x18016cfb6  mov     rdi, rdx
0x18016cfb9  mov     rsi, rcx
0x18016cfbc  xorps   xmm0, xmm0
0x18016cfbf  movups  [rbp+57h+Buf1], xmm0
0x18016cfc3  xor     r12d, r12d
0x18016cfc6  mov     [rsp+0F0h+var_D0], r12; bool *
0x18016cfcb  lea     r9, [rbp+57h+Buf1]; struct _GUID *
0x18016cfcf  lea     r8, stru_180231B98; unsigned __int16 *
0x18016cfd6  call    ?ParseAndRetrieveGuid@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAU_GUID@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveGuid(IXMLDOMElement *,ushort const *,_GUID *,bool *)
0x18016cfdb  mov     ebx, eax
0x18016cfdd  test    eax, eax
0x18016cfdf  jns     short loc_18016D012
0x18016cfe1  mov     rcx, [rbp+5Fh]; this
0x18016cfe5  mov     dword ptr [rsp+0F0h+var_C8], eax; char *
0x18016cfe9  lea     rax, aParseandretrie_32; "ParseAndRetrieveGuid( root, Internal::P"...
0x18016cff0  mov     [rsp+0F0h+var_D0], rax; char *
0x18016cff5  lea     r9, aOsintegrationD_25; "OSIntegration::DEH::PackagedComExtensio"...
0x18016cffc  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016d003  mov     edx, 70Dh; void *
0x18016d008  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016d00d  jmp     loc_18016D537
0x18016d012  mov     [rbp+57h+var_98], r12
0x18016d016  mov     rcx, [rsi+30h]
0x18016d01a  mov     rax, [rcx]
0x18016d01d  mov     [rbp+57h+var_98], r12
0x18016d021  movaps  xmm0, [rbp+57h+Buf1]
0x18016d025  movdqa  [rbp+57h+var_70], xmm0
0x18016d02a  lea     r8, [rbp+57h+var_98]
0x18016d02e  lea     rdx, [rbp+57h+var_70]
0x18016d032  mov     rax, [rax+60h]
0x18016d036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d03b  mov     ebx, eax
0x18016d03d  test    eax, eax
0x18016d03f  jns     short loc_18016D053
0x18016d041  mov     dword ptr [rsp+0F0h+var_C8], eax
0x18016d045  lea     rax, aCollectorCreat_1; "_collector->CreateTreatAsClassRegistrat"...
0x18016d04c  mov     edx, 710h
0x18016d051  jmp     short loc_18016D088
0x18016d053  xorps   xmm0, xmm0
0x18016d056  movups  xmmword ptr [rbp+57h+var_40.Data1], xmm0
0x18016d05a  mov     [rsp+0F0h+var_D0], r12; bool *
0x18016d05f  lea     r9, [rbp+57h+var_40]; struct _GUID *
0x18016d063  lea     r8, aTreatas; "TreatAs"
0x18016d06a  mov     rdx, rdi; struct IXMLDOMElement *
0x18016d06d  call    ?ParseAndRetrieveGuid@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAU_GUID@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveGuid(IXMLDOMElement *,ushort const *,_GUID *,bool *)
0x18016d072  mov     ebx, eax
0x18016d074  test    eax, eax
0x18016d076  jns     short loc_18016D0A9
0x18016d078  mov     dword ptr [rsp+0F0h+var_C8], eax; char *
0x18016d07c  lea     rax, aParseandretrie_65; "ParseAndRetrieveGuid( root, Internal::P"...
0x18016d083  mov     edx, 716h; void *
0x18016d088  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016d08f  lea     r9, aOsintegrationD_25; "OSIntegration::DEH::PackagedComExtensio"...
0x18016d096  mov     [rsp+0F0h+var_D0], rax; char *
0x18016d09b  mov     rcx, [rbp+5Fh]; this
0x18016d09f  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016d0a4  jmp     loc_18016D52E
0x18016d0a9  mov     [rbp+57h+string], r12
0x18016d0ad  xor     edx, edx
0x18016d0af  lea     rcx, [rbp+57h+string]
0x18016d0b3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18016d0b8  xor     r9d, r9d; struct IXMLDOMElement **
0x18016d0bb  lea     r8, [rbp+57h+string]; HSTRING *
0x18016d0bf  mov     rdx, rdi; struct IXMLDOMElement *
0x18016d0c2  mov     rcx, rsi; this
0x18016d0c5  call    ?VerifyTreatAsChain@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEAPEAUHSTRING__@@PEAPEAU4@@Z; OSIntegration::DEH::PackagedComExtensionHandler::VerifyTreatAsChain(IXMLDOMElement *,HSTRING__ * *,IXMLDOMElement * *)
0x18016d0ca  mov     ebx, eax
0x18016d0cc  test    eax, eax
0x18016d0ce  jns     short loc_18016D10B
0x18016d0d0  mov     dword ptr [rsp+0F0h+var_C8], eax; char *
0x18016d0d4  lea     rax, aVerifytreatasc; "VerifyTreatAsChain(root, &terminalClsid"...
0x18016d0db  mov     edx, 719h; void *
0x18016d0e0  mov     rcx, [rbp+5Fh]; this
0x18016d0e4  mov     [rsp+0F0h+var_D0], rax; char *
0x18016d0e9  lea     r9, aOsintegrationD_25; "OSIntegration::DEH::PackagedComExtensio"...
0x18016d0f0  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016d0f7  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016d0fc  nop
0x18016d0fd  lea     rcx, [rbp+57h+string]
0x18016d101  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x18016d106  jmp     loc_18016D52E
0x18016d10b  mov     r8d, 0Fh
0x18016d111  mov     [rbp+57h+var_90], r8d
0x18016d115  test    r14b, r14b
0x18016d118  jz      short loc_18016D154
0x18016d11a  xor     edx, edx; length
0x18016d11c  mov     rcx, [rbp+57h+string]; string
0x18016d120  call    cs:__imp_WindowsGetStringRawBuffer
0x18016d126  lea     r9, [rbp+57h+var_90]; enum OSIntegration::DEH::SupportedArchitectureFlags *
0x18016d12a  mov     r8, rax; unsigned __int16 *
0x18016d12d  mov     rdx, rdi; struct IXMLDOMElement *
0x18016d130  mov     rcx, rsi; this
0x18016d133  call    ?GetArchitecturesSupportedForActivationByClsid@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAW4SupportedArchitectureFlags@23@@Z; OSIntegration::DEH::PackagedComExtensionHandler::GetArchitecturesSupportedForActivationByClsid(IXMLDOMElement *,ushort const *,OSIntegration::DEH::SupportedArchitectureFlags *)
0x18016d138  mov     ebx, eax
0x18016d13a  test    eax, eax
0x18016d13c  jns     short loc_18016D150
0x18016d13e  mov     dword ptr [rsp+0F0h+var_C8], eax
0x18016d142  lea     rax, aGetarchitectur; "GetArchitecturesSupportedForActivationB"...
0x18016d149  mov     edx, 724h
0x18016d14e  jmp     short loc_18016D0E0
0x18016d150  mov     r8d, [rbp+57h+var_90]
0x18016d154  mov     rcx, [rbp+57h+var_98]
0x18016d158  movaps  xmm0, xmmword ptr [rbp+57h+var_40.Data1]
0x18016d15c  movdqa  [rbp+57h+var_70], xmm0
0x18016d161  mov     rax, [rcx]
0x18016d164  lea     rdx, [rbp+57h+var_70]
0x18016d168  mov     rax, [rax+48h]
0x18016d16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d171  mov     ebx, eax
0x18016d173  test    eax, eax
0x18016d175  jns     short loc_18016D18C
0x18016d177  mov     dword ptr [rsp+0F0h+var_C8], eax
0x18016d17b  lea     rax, aTreatasSettrea; "treatAs->SetTreatAsWithSupportedArchite"...
0x18016d182  mov     edx, 727h
0x18016d187  jmp     loc_18016D0E0
0x18016d18c  mov     [rbp+57h+var_A0], r12
0x18016d190  mov     [rbp+57h+var_B0], r12b
0x18016d194  xor     edx, edx
0x18016d196  lea     rcx, [rbp+57h+var_A0]
0x18016d19a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18016d19f  lea     rax, [rbp+57h+var_B0]
0x18016d1a3  mov     [rsp+0F0h+var_D0], rax; bool *
0x18016d1a8  lea     r9, [rbp+57h+var_A0]; HSTRING *
0x18016d1ac  lea     r8, aDisplayname; "DisplayName"
0x18016d1b3  mov     rdx, rdi; struct IXMLDOMElement *
0x18016d1b6  mov     rcx, rsi; this
0x18016d1b9  call    ?ParseAndRetrieveLocalizableAttribute@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAPEAUHSTRING__@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveLocalizableAttribute(IXMLDOMElement *,ushort const *,HSTRING__ * *,bool *)
0x18016d1be  mov     ebx, eax
0x18016d1c0  test    eax, eax
0x18016d1c2  jns     short loc_18016D1FF
0x18016d1c4  mov     dword ptr [rsp+0F0h+var_C8], eax; char *
0x18016d1c8  lea     rax, aParseandretrie_64; "ParseAndRetrieveLocalizableAttribute(ro"...
0x18016d1cf  mov     edx, 72Ch; void *
0x18016d1d4  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016d1db  lea     r9, aOsintegrationD_25; "OSIntegration::DEH::PackagedComExtensio"...
0x18016d1e2  mov     [rsp+0F0h+var_D0], rax; char *
0x18016d1e7  mov     rcx, [rbp+5Fh]; this
0x18016d1eb  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016d1f0  nop
0x18016d1f1  lea     rcx, [rbp+57h+var_A0]
0x18016d1f5  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x18016d1fa  jmp     loc_18016D0FD
0x18016d1ff  cmp     [rbp+57h+var_B0], r12b
0x18016d203  jz      short loc_18016D231
0x18016d205  mov     rcx, [rbp+57h+var_98]
0x18016d209  mov     rax, [rcx]
0x18016d20c  mov     rdx, [rbp+57h+var_A0]
0x18016d210  mov     rax, [rax+38h]
0x18016d214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d219  mov     ebx, eax
0x18016d21b  test    eax, eax
0x18016d21d  jns     short loc_18016D231
0x18016d21f  mov     dword ptr [rsp+0F0h+var_C8], eax
0x18016d223  lea     rax, aTreatasSetdisp; "treatAs->SetDisplayName(displayName.get"...
0x18016d22a  mov     edx, 72Fh
0x18016d22f  jmp     short loc_18016D1D4
0x18016d231  xorps   xmm0, xmm0
0x18016d234  movups  [rbp+57h+Buf2], xmm0
0x18016d238  mov     [rbp+57h+var_B0], r12b
0x18016d23c  lea     rax, [rbp+57h+var_B0]
0x18016d240  mov     [rsp+0F0h+var_D0], rax; bool *
0x18016d245  lea     r9, [rbp+57h+Buf2]; struct _GUID *
0x18016d249  lea     r8, stru_18023EEF0; unsigned __int16 *
0x18016d250  mov     rdx, rdi; struct IXMLDOMElement *
0x18016d253  call    ?ParseAndRetrieveGuid@PackagedComExtensionHandler@DEH@OSIntegration@@AEAAJPEAUIXMLDOMElement@@PEBGPEAU_GUID@@PEA_N@Z; OSIntegration::DEH::PackagedComExtensionHandler::ParseAndRetrieveGuid(IXMLDOMElement *,ushort const *,_GUID *,bool *)
0x18016d258  mov     ebx, eax
0x18016d25a  test    eax, eax
0x18016d25c  jns     short loc_18016D273
0x18016d25e  mov     dword ptr [rsp+0F0h+var_C8], eax
0x18016d262  lea     rax, aParseandretrie_50; "ParseAndRetrieveGuid(root, Internal::Pa"...
0x18016d269  mov     edx, 735h
0x18016d26e  jmp     loc_18016D1D4
0x18016d273  cmp     [rbp+57h+var_B0], r12b
0x18016d277  jz      loc_18016D3E1
0x18016d27d  mov     r8d, 10h; Size
0x18016d283  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18016d287  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18016d28b  call    memcmp_0
0x18016d290  test    eax, eax
0x18016d292  jnz     loc_18016D3A9
0x18016d298  mov     [rbp+57h+var_88], r12
0x18016d29c  lea     r9, [rbp+57h+var_88]; struct APPX_XML_LINE_INFORMATION *
0x18016d2a0  xor     r8d, r8d; unsigned __int16 *
0x18016d2a3  mov     rdx, rdi; struct IXMLDOMNode *
0x18016d2a6  mov     rcx, [rsi+28h]; this
0x18016d2aa  call    ?GetXmlLineInformation@Package@OSIntegration@@QEBAJPEBUIXMLDOMNode@@PEBGPEAUAPPX_XML_LINE_INFORMATION@@@Z; OSIntegration::Package::GetXmlLineInformation(IXMLDOMNode const *,ushort const *,APPX_XML_LINE_INFORMATION *)
0x18016d2af  mov     rcx, [rbp+5Fh]; this
0x18016d2b3  mov     edi, 80080204h
0x18016d2b8  mov     dword ptr [rsp+0F0h+var_C8], edi; char *
0x18016d2bc  lea     rax, aHresult0x80080; "((HRESULT)0x80080204L)"
0x18016d2c3  mov     [rsp+0F0h+var_D0], rax; char *
0x18016d2c8  lea     r9, aOsintegrationD_25; "OSIntegration::DEH::PackagedComExtensio"...
0x18016d2cf  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016d2d6  mov     edx, 745h; void *
0x18016d2db  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016d2e0  test    cs:byte_1802E21CA, 4
0x18016d2e7  jz      short loc_18016D323
0x18016d2e9  mov     rcx, [rsi+28h]
0x18016d2ed  mov     rbx, [rcx+0E0h]
0x18016d2f4  mov     rcx, [rcx+110h]; unsigned __int16 *
0x18016d2fb  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x18016d300  mov     qword ptr [rsp+0F0h+var_C0], rbx
0x18016d305  mov     dword ptr [rsp+0F0h+var_C8], edi
0x18016d309  mov     ecx, dword ptr [rbp+57h+var_88+4]
0x18016d30c  mov     dword ptr [rsp+0F0h+var_D0], ecx
0x18016d310  mov     r9d, dword ptr [rbp+57h+var_88]
0x18016d314  mov     r8, rax
0x18016d317  lea     rdx, PackagedComInvalidAutoConvertTo
0x18016d31e  call    McTemplateU0zqqdz_EventWriteTransfer
0x18016d323  mov     rcx, [rsi+28h]
0x18016d327  mov     rbx, [rcx+0E0h]
0x18016d32e  mov     rcx, [rcx+110h]; unsigned __int16 *
0x18016d335  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x18016d33a  mov     [rsp+0F0h+var_B8], rbx
0x18016d33f  mov     [rsp+0F0h+var_C0], edi; int
0x18016d343  mov     ecx, dword ptr [rbp+57h+var_88+4]
0x18016d346  mov     dword ptr [rsp+0F0h+var_C8], ecx
0x18016d34a  mov     ecx, dword ptr [rbp+57h+var_88]
0x18016d34d  mov     dword ptr [rsp+0F0h+var_D0], ecx
0x18016d351  mov     r9, rax
0x18016d354  lea     r8, PackagedComInvalidAutoConvertTo
0x18016d35b  mov     ecx, edi
0x18016d35d  call    ??$appxLog@PEBGIIJPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBGIIJPEAG@Z; details::appxLog<ushort const *,uint,uint,long,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort const *,uint,uint,long,ushort *)
0x18016d362  mov     rcx, [rbp+5Fh]; this
0x18016d366  mov     dword ptr [rsp+0F0h+var_C8], edi; char *
0x18016d36a  lea     rax, aAppxEInvalidMa; "APPX_E_INVALID_MANIFEST"
0x18016d371  mov     [rsp+0F0h+var_D0], rax; char *
0x18016d376  lea     r9, aOsintegrationD_25; "OSIntegration::DEH::PackagedComExtensio"...
0x18016d37d  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016d384  mov     edx, 747h; void *
0x18016d389  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016d38e  nop
0x18016d38f  lea     rcx, [rbp+57h+var_A0]
0x18016d393  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x18016d398  nop
0x18016d399  lea     rcx, [rbp+57h+string]
0x18016d39d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x18016d3a2  mov     ebx, edi
0x18016d3a4  jmp     loc_18016D52E
0x18016d3a9  mov     rcx, [rbp+57h+var_98]
0x18016d3ad  movaps  xmm0, [rbp+57h+Buf2]
0x18016d3b1  movdqa  [rbp+57h+var_70], xmm0
0x18016d3b6  mov     rax, [rcx]
0x18016d3b9  lea     rdx, [rbp+57h+var_70]
0x18016d3bd  mov     rax, [rax+40h]
0x18016d3c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d3c6  mov     ebx, eax
0x18016d3c8  test    eax, eax
0x18016d3ca  jns     short loc_18016D3E1
0x18016d3cc  mov     dword ptr [rsp+0F0h+var_C8], eax
0x18016d3d0  lea     rax, aTreatasSetauto; "treatAs->SetAutoConvertTo(autoConvertTo"...
0x18016d3d7  mov     edx, 74Ah
0x18016d3dc  jmp     loc_18016D1D4
0x18016d3e1  test    r14b, r14b
0x18016d3e4  jz      loc_18016D47C
0x18016d3ea  mov     [rbp+57h+var_80], r12
0x18016d3ee  mov     rcx, [rbp+57h+var_98]
0x18016d3f2  mov     rax, [rcx]
0x18016d3f5  lea     r8, [rbp+57h+var_80]
0x18016d3f9  lea     rdx, _GUID_f74eae70_01a3_405c_aa49_bc7c92dd9de3
0x18016d400  mov     rax, [rax]
0x18016d403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d408  mov     ebx, eax
0x18016d40a  test    eax, eax
0x18016d40c  jns     short loc_18016D449
0x18016d40e  mov     dword ptr [rsp+0F0h+var_C8], eax; char *
0x18016d412  lea     rax, aTreatasQueryTo_0; "treatAs.query_to(&registryCompatibility"...
0x18016d419  mov     edx, 750h; void *
0x18016d41e  lea     r8, aOnecoreAdminAp_93; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016d425  lea     r9, aOsintegrationD_25; "OSIntegration::DEH::PackagedComExtensio"...
0x18016d42c  mov     [rsp+0F0h+var_D0], rax; char *
0x18016d431  mov     rcx, [rbp+5Fh]; this
0x18016d435  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016d43a  nop
0x18016d43b  lea     rcx, [rbp+57h+var_80]
0x18016d43f  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18016d444  jmp     loc_18016D1F1
0x18016d449  mov     rcx, [rbp+57h+var_80]
0x18016d44d  mov     rax, [rcx]
0x18016d450  mov     dl, 1
0x18016d452  mov     rax, [rax+30h]
0x18016d456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016d45b  mov     ebx, eax
0x18016d45d  test    eax, eax
0x18016d45f  jns     short loc_18016D473
0x18016d461  mov     dword ptr [rsp+0F0h+var_C8], eax
  ... truncated ...
```
