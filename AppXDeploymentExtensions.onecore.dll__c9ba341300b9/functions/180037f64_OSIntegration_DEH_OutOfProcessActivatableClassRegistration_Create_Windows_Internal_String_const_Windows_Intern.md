# OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create(Windows::Internal::String const &,Windows::Internal::String const &,OSIntegration::DEH::Collectors *,OSIntegration::DEH::OutOfProcessActivatableClassRegistration * *)

- ea: `0x180037f64`
- end: `0x18003887c`
- name: `?Create@OutOfProcessActivatableClassRegistration@DEH@OSIntegration@@SAJAEBVString@Internal@Windows@@0PEAVCollectors@23@PEAPEAU123@@Z`
- size: `2328`
- prototype: `__int64 __fastcall(const struct Windows::Internal::String *, const struct Windows::Internal::String *, struct OSIntegration::DEH::Collectors *, struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration **)`
- caller_count: `5`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180046944`
- `0x1800ad8f4`
- `0x1801384e0`
- `0x18013a9d4`
- `0x18014b788`

## callees

- `0x18000b3bc`
- `0x180037f64`
- `0x180038884`
- `0x18003a300`
- `0x1800464a4`
- `0x1800467fc`
- `0x180059968`
- `0x180098ed0`
- `0x18009aff4`
- `0x1800cc418`
- `0x1800cdcbc`
- `0x18012ba10`
- `0x1801a705c`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003851d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180038541`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003865e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180038683`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180038789`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800387ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800387e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003880c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003851d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180038541`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003865e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180038683`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180038789`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800387ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800387e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003880c`

## string_xrefs

- `0x180038095`: `OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create`
- `0x18003814d`: `OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create`
- `0x180038339`: `OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create`
- `0x1800383d3`: `OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create`
- `0x1800384f7`: `OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create`
- `0x180038571`: `OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create`
- `0x18003863e`: `OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create`
- `0x1800386b7`: `OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create`
- `0x1800386f8`: `OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create`
- `0x180038751`: `OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create`
- `0x180038841`: `OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create`
- `0x180038565`: `APPX_E_INVALID_MANIFEST`
- `0x1800383c7`: `OutOfProcessActivatableClassRegistration_Impl::Create(activatableClassId, serverRegistration.Get(), &classRegistration)`
- `0x180038089`: `collectors->GetActivationCatalogCollector()->RetrieveOutOfProcessActivatableClassRegistration(activatableClassId, &found, &retrievedOutOfProcClassRegistration)`
- `0x180038115`: `_inProcessActivatableClasses->HasKey(activatableClassId, found)`
- `0x180038141`: `collectors->GetActivationCatalogCollector()->RetrieveInProcessActivatableClassRegistration(activatableClassId, &found, &retrievedInProcClassRegistration)`
- `0x1800385ca`: `_inProcessActivatableClasses->Lookup(activatableClassId, &registration)`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create(
        HSTRING *a1,
        HSTRING *a2,
        struct OSIntegration::DEH::Collectors *a3,
        struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration **a4)
{
  char v8; // si
  __int64 v9; // rdi
  unsigned __int8 v10; // al
  __int64 v11; // rcx
  Windows::Internal::String *v12; // rax
  Windows::Internal::String *v13; // rax
  bool v14; // bl
  int v15; // eax
  unsigned int v16; // ebx
  OSIntegration::DEH::ActivationCatalogCollector *v17; // rbx
  int v18; // eax
  struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *v19; // rcx
  __int64 v20; // rcx
  int v22; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, HSTRING, struct OSIntegration::DEH::ExeServerRegistration **); // rbx
  int v25; // eax
  unsigned __int8 v26; // al
  int v27; // eax
  int v28; // eax
  struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *v29; // rax
  struct OSIntegration::DEH::ExeServerRegistration *v30; // rcx
  struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *v31; // rcx
  __int64 v32; // rcx
  struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *v33; // rcx
  struct OSIntegration::DEH::ExeServerRegistration *v34; // rcx
  struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *v35; // rcx
  __int64 v36; // rcx
  struct OSIntegration::DEH::ExeServerRegistration *v37; // rcx
  struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *v38; // rcx
  __int64 v39; // rcx
  struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *v40; // rcx
  __int64 v41; // rdi
  __int64 v42; // rcx
  struct OSIntegration::DEH::ExeServerRegistration *v43; // rcx
  PCWSTR StringRawBuffer; // rax
  PCWSTR v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rdi
  __int64 (__fastcall *v48)(__int64, HSTRING, struct OSIntegration::DEH::ExeServerRegistration **); // rbx
  int v49; // eax
  struct OSIntegration::DEH::ExeServerRegistration *v50; // rax
  PCWSTR v51; // rax
  PCWSTR v52; // rax
  __int64 v53; // rdx
  PCWSTR v54; // rax
  PCWSTR v55; // rax
  __int64 v56; // rdx
  __int64 v57; // rdx
  PCWSTR v58; // rax
  PCWSTR v59; // rax
  __int64 v60; // rdx
  char *v61; // [rsp+28h] [rbp-50h]
  char *v62; // [rsp+28h] [rbp-50h]
  char *v63; // [rsp+28h] [rbp-50h]
  char *v64; // [rsp+28h] [rbp-50h]
  char *v65; // [rsp+28h] [rbp-50h]
  char *v66; // [rsp+28h] [rbp-50h]
  int v67; // [rsp+30h] [rbp-48h]
  int v68; // [rsp+30h] [rbp-48h]
  int v69; // [rsp+30h] [rbp-48h]
  int v70; // [rsp+30h] [rbp-48h]
  unsigned int v71; // [rsp+30h] [rbp-48h]
  unsigned int v72; // [rsp+30h] [rbp-48h]
  struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *v73; // [rsp+38h] [rbp-40h] BYREF
  struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *v74; // [rsp+40h] [rbp-38h] BYREF
  __int64 v75; // [rsp+48h] [rbp-30h] BYREF
  struct OSIntegration::DEH::ExeServerRegistration *v76; // [rsp+50h] [rbp-28h] BYREF
  struct OSIntegration::DEH::ExeServerRegistration *v77; // [rsp+58h] [rbp-20h] BYREF
  _BYTE v78[24]; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+B8h] [rbp+40h]
  unsigned __int8 v80; // [rsp+D8h] [rbp+60h] BYREF

  v8 = 0;
  v67 = 0;
  *a4 = 0;
  if ( !WinRTIsValidActivatableClassId(*a1) )
  {
    v16 = -2146958844;
    LODWORD(v61) = -2146958844;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0x24B,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create",
      "((HRESULT)0x80080204L)",
      v61,
      0);
    if ( (byte_1802E21C5 & 0x20) != 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(*a1, 0);
      McTemplateU0dz_EventWriteTransfer(
        &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
        ActivatableClassIdentifierInvalid,
        2148008452LL,
        StringRawBuffer);
    }
    v45 = WindowsGetStringRawBuffer(*a1, 0);
    details::appxLog<long,unsigned short const *>(
      -2146958844,
      v46,
      (const struct _EVENT_DESCRIPTOR *)ActivatableClassIdentifierInvalid,
      -2146958844,
      v45);
    LODWORD(v64) = -2146958844;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x24D,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create",
      "APPX_E_INVALID_MANIFEST",
      v64,
      v70);
    return v16;
  }
  v73 = 0;
  v74 = 0;
  v9 = *((_QWORD *)a3 + 5);
  v10 = 0;
  v80 = 0;
  v75 = 0;
  v11 = *(_QWORD *)(v9 + 40);
  if ( v11 )
  {
    v15 = (*(__int64 (__fastcall **)(__int64, HSTRING, unsigned __int8 *))(*(_QWORD *)v11 + 64LL))(v11, *a1, &v80);
    v16 = v15;
    if ( v15 < 0 )
    {
      LODWORD(v61) = v15;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0xA7,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
        "OSIntegration::DEH::ActivationCatalogCollector::RetrieveInProcessActivatableClassRegistration",
        "_inProcessActivatableClasses->HasKey(activatableClassId, found)",
        v61,
        0);
    }
    else
    {
      if ( !v80 )
        goto LABEL_11;
      v77 = 0;
      v47 = *(_QWORD *)(v9 + 40);
      v48 = *(__int64 (__fastcall **)(__int64, HSTRING, struct OSIntegration::DEH::ExeServerRegistration **))(*(_QWORD *)v47 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
      v49 = v48(v47, *a1, &v77);
      v16 = v49;
      if ( v49 >= 0 )
      {
        v50 = v77;
        v77 = 0;
        v75 = ((unsigned __int64)v50 - 16) & -(__int64)(v50 != 0);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
        v10 = v80;
        goto LABEL_3;
      }
      LODWORD(v61) = v49;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0xAB,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
        "OSIntegration::DEH::ActivationCatalogCollector::RetrieveInProcessActivatableClassRegistration",
        "_inProcessActivatableClasses->Lookup(activatableClassId, &registration)",
        v61,
        0);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
    }
    LODWORD(v62) = v16;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x254,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create",
      "collectors->GetActivationCatalogCollector()->RetrieveInProcessActivatableClassRegistration(activatableClassId, &fo"
      "und, &retrievedInProcClassRegistration)",
      v62,
      v68);
    return v16;
  }
LABEL_3:
  if ( v10 )
  {
LABEL_4:
    v14 = 1;
    if ( !v75
      || (v12 = (Windows::Internal::String *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v75 + 88LL))(
                                               v75,
                                               v78),
          v8 = 1,
          v67 = 1,
          (unsigned int)Windows::Internal::String::CompareOrdinal(v12, (const struct Windows::Internal::String *)a1)) )
    {
      if ( !v74
        || (v13 = (Windows::Internal::String *)(*(__int64 (__fastcall **)(struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *, struct OSIntegration::DEH::ExeServerRegistration **))(*(_QWORD *)v74 + 88LL))(
                                                 v74,
                                                 &v77),
            v8 |= 2u,
            (unsigned int)Windows::Internal::String::CompareOrdinal(v13, (const struct Windows::Internal::String *)a1)) )
      {
        v14 = 0;
      }
    }
    if ( (v8 & 2) != 0 )
    {
      v8 &= ~2u;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v77);
    }
    if ( (v8 & 1) != 0 )
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(v78);
    LODWORD(v61) = -2147024736;
    if ( v14 )
    {
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0x263,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
        "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create",
        "HRESULT_FROM_WIN32(160L)",
        v61,
        v67);
      if ( (byte_1802E21C5 & 0x20) != 0 )
      {
        v54 = WindowsGetStringRawBuffer(*a1, 0);
        McTemplateU0dz_EventWriteTransfer(
          &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
          CollidingActivatableClassIdentifiers,
          2147942560LL,
          v54);
      }
      v55 = WindowsGetStringRawBuffer(*a1, 0);
      details::appxLog<long,unsigned short const *>(
        -2147024736,
        v56,
        (const struct _EVENT_DESCRIPTOR *)CollidingActivatableClassIdentifiers,
        -2147024736,
        v55);
      v57 = 613;
    }
    else
    {
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0x26D,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
        "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create",
        "HRESULT_FROM_WIN32(160L)",
        v61,
        v67);
      if ( (byte_1802E21C5 & 0x20) != 0 )
      {
        v58 = WindowsGetStringRawBuffer(*a1, 0);
        McTemplateU0dz_EventWriteTransfer(
          &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
          DuplicateActivatableClassIdentifiers,
          2147942560LL,
          v58);
      }
      v59 = WindowsGetStringRawBuffer(*a1, 0);
      details::appxLog<long,unsigned short const *>(
        -2147024736,
        v60,
        (const struct _EVENT_DESCRIPTOR *)DuplicateActivatableClassIdentifiers,
        -2147024736,
        v59);
      v57 = 623;
    }
    LODWORD(v66) = 160;
    v16 = wil::details::in1diag5::Return_Win32(
            retaddr,
            (void *)v57,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
            "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create",
            "ERROR_BAD_ARGUMENTS",
            v66,
            v72);
    goto LABEL_83;
  }
LABEL_11:
  v17 = (OSIntegration::DEH::ActivationCatalogCollector *)*((_QWORD *)a3 + 5);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
  v18 = OSIntegration::DEH::ActivationCatalogCollector::RetrieveOutOfProcessActivatableClassRegistration(
          v17,
          (const struct Windows::Internal::String *)a1,
          &v80,
          &v74);
  v16 = v18;
  if ( v18 < 0 )
  {
    LODWORD(v61) = v18;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x257,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create",
      "collectors->GetActivationCatalogCollector()->RetrieveOutOfProcessActivatableClassRegistration(activatableClassId, "
      "&found, &retrievedOutOfProcClassRegistration)",
      v61,
      0);
    v19 = v74;
    if ( v74 )
    {
      v74 = 0;
      (*(void (__fastcall **)(struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v75;
    if ( v75 )
    {
      v75 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    return v16;
  }
  if ( v80 )
    goto LABEL_4;
  v76 = 0;
  v41 = *((_QWORD *)a3 + 5);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
  v26 = 0;
  v80 = 0;
  v76 = 0;
  v42 = *(_QWORD *)(v41 + 56);
  if ( v42 )
  {
    v22 = (*(__int64 (__fastcall **)(__int64, HSTRING, unsigned __int8 *))(*(_QWORD *)v42 + 64LL))(v42, *a2, &v80);
    v16 = v22;
    if ( v22 < 0 )
    {
      LODWORD(v61) = v22;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
        "OSIntegration::DEH::ActivationCatalogCollector::RetrieveServerRegistration",
        "_exeServers->HasKey(serverName, found)",
        v61,
        0);
    }
    else
    {
      if ( !v80 )
      {
LABEL_68:
        LODWORD(v61) = -2147024883;
        wil::details::in1diag5::_Log_Hr(
          retaddr,
          (void *)0x282,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
          "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create",
          "HRESULT_FROM_WIN32(13L)",
          v61,
          0);
        if ( (byte_1802E21C5 & 0x20) != 0 )
        {
          v51 = WindowsGetStringRawBuffer(*a2, 0);
          McTemplateU0dz_EventWriteTransfer(
            &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
            MissingServerName,
            2147942413LL,
            v51);
        }
        v52 = WindowsGetStringRawBuffer(*a2, 0);
        details::appxLog<long,unsigned short const *>(
          -2147024883,
          v53,
          (const struct _EVENT_DESCRIPTOR *)MissingServerName,
          -2147024883,
          v52);
        LODWORD(v65) = 13;
        v16 = wil::details::in1diag5::Return_Win32(
                retaddr,
                (void *)0x284,
                (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
                "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create",
                "ERROR_INVALID_DATA",
                v65,
                v71);
        goto LABEL_67;
      }
      v77 = 0;
      v23 = *(_QWORD *)(v41 + 56);
      v24 = *(__int64 (__fastcall **)(__int64, HSTRING, struct OSIntegration::DEH::ExeServerRegistration **))(*(_QWORD *)v23 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
      v25 = v24(v23, *a2, &v77);
      v16 = v25;
      if ( v25 >= 0 )
      {
        v76 = v77;
        v26 = v80;
        goto LABEL_24;
      }
      LODWORD(v61) = v25;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0xE2,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
        "OSIntegration::DEH::ActivationCatalogCollector::RetrieveServerRegistration",
        "_exeServers->Lookup(serverName, &registration)",
        v61,
        0);
      v43 = v77;
      if ( v77 )
      {
        v77 = 0;
        (*(void (__fastcall **)(struct OSIntegration::DEH::ExeServerRegistration *))(*(_QWORD *)v43 + 16LL))(v43);
      }
    }
    LODWORD(v63) = v16;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x274,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create",
      "collectors->GetActivationCatalogCollector()->RetrieveServerRegistration(serverName, &found, &serverRegistration)",
      v63,
      v69);
    v34 = v76;
    if ( v76 )
    {
      v76 = 0;
      (*(void (__fastcall **)(struct OSIntegration::DEH::ExeServerRegistration *))(*(_QWORD *)v34 + 16LL))(v34);
    }
    v35 = v74;
    if ( v74 )
    {
      v74 = 0;
      (*(void (__fastcall **)(struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *))(*(_QWORD *)v35 + 16LL))(v35);
    }
    v36 = v75;
    if ( v75 )
    {
      v75 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
    return v16;
  }
LABEL_24:
  if ( !v26 )
    goto LABEL_68;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
  v27 = OSIntegration::DEH::Internal::OutOfProcessActivatableClassRegistration_Impl::Create(
          (const struct Windows::Internal::String *)a1,
          v76,
          &v73);
  v16 = v27;
  if ( v27 < 0 )
  {
    LODWORD(v61) = v27;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x278,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create",
      "OutOfProcessActivatableClassRegistration_Impl::Create(activatableClassId, serverRegistration.Get(), &classRegistration)",
      v61,
      0);
    v37 = v76;
    if ( v76 )
    {
      v76 = 0;
      (*(void (__fastcall **)(struct OSIntegration::DEH::ExeServerRegistration *))(*(_QWORD *)v37 + 16LL))(v37);
    }
    v38 = v74;
    if ( v74 )
    {
      v74 = 0;
      (*(void (__fastcall **)(struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *))(*(_QWORD *)v38 + 16LL))(v38);
    }
    v39 = v75;
    if ( v75 )
    {
      v75 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    v40 = v73;
    if ( v73 )
    {
      v73 = 0;
      (*(void (__fastcall **)(struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *))(*(_QWORD *)v40 + 16LL))(v40);
    }
    return v16;
  }
  v28 = OSIntegration::DEH::ActivationCatalogCollector::AddOutOfProcessActivatableClassRegistration(
          *((OSIntegration::DEH::ActivationCatalogCollector **)a3 + 5),
          v73);
  v16 = v28;
  if ( v28 < 0 )
  {
    LODWORD(v61) = v28;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x27A,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create",
      "collectors->GetActivationCatalogCollector()->AddOutOfProcessActivatableClassRegistration(classRegistration.Get())",
      v61,
      0);
LABEL_67:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
LABEL_83:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
    return v16;
  }
  v29 = v73;
  v73 = 0;
  *a4 = v29;
  v30 = v76;
  if ( v76 )
  {
    v76 = 0;
    (*(void (__fastcall **)(struct OSIntegration::DEH::ExeServerRegistration *))(*(_QWORD *)v30 + 16LL))(v30);
  }
  v31 = v74;
  if ( v74 )
  {
    v74 = 0;
    (*(void (__fastcall **)(struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *))(*(_QWORD *)v31 + 16LL))(v31);
  }
  v32 = v75;
  if ( v75 )
  {
    v75 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  v33 = v73;
  if ( v73 )
  {
    v73 = 0;
    (*(void (__fastcall **)(struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *))(*(_QWORD *)v33 + 16LL))(v33);
  }
  return 0;
}

```

## disassembly

```asm
0x180037f64  push    rbp
0x180037f66  push    rbx
0x180037f67  push    rsi
0x180037f68  push    rdi
0x180037f69  push    r12
0x180037f6b  push    r13
0x180037f6d  push    r14
0x180037f6f  push    r15
0x180037f71  mov     rbp, rsp
0x180037f74  sub     rsp, 78h
0x180037f78  mov     r13, r9
0x180037f7b  mov     r15, r8
0x180037f7e  mov     r12, rdx
0x180037f81  mov     r14, rcx
0x180037f84  xor     ebx, ebx
0x180037f86  mov     esi, ebx
0x180037f88  mov     [rbp+var_48], ebx
0x180037f8b  mov     [r9], rbx
0x180037f8e  mov     rcx, [rcx]; string
0x180037f91  call    ?WinRTIsValidActivatableClassId@@YA_NPEAUHSTRING__@@@Z; WinRTIsValidActivatableClassId(HSTRING__ *)
0x180037f96  test    al, al
0x180037f98  jz      loc_1800384DE
0x180037f9e  mov     [rbp+var_40], rbx
0x180037fa2  mov     [rbp+var_38], rbx
0x180037fa6  mov     rdi, [r15+28h]
0x180037faa  mov     al, bl
0x180037fac  mov     [rbp+arg_18], bl
0x180037faf  mov     [rbp+var_30], rbx
0x180037fb3  mov     rcx, [rdi+28h]
0x180037fb7  test    rcx, rcx
0x180037fba  jnz     short loc_18003802F
0x180037fbc  test    al, al
0x180037fbe  jz      loc_180038057
0x180037fc4  mov     rcx, [rbp+var_30]
0x180037fc8  test    rcx, rcx
0x180037fcb  jz      short loc_180037FF5
0x180037fcd  mov     rax, [rcx]
0x180037fd0  lea     rdx, [rbp+var_18]
0x180037fd4  mov     rax, [rax+58h]
0x180037fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037fdd  nop
0x180037fde  mov     esi, 1
0x180037fe3  mov     [rbp+var_48], esi
0x180037fe6  mov     rdx, r14; struct Windows::Internal::String *
0x180037fe9  mov     rcx, rax; this
0x180037fec  call    ?CompareOrdinal@String@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::String::CompareOrdinal(Windows::Internal::String const &)
0x180037ff1  test    eax, eax
0x180037ff3  jz      short loc_180038028
0x180037ff5  mov     rcx, [rbp+var_38]
0x180037ff9  test    rcx, rcx
0x180037ffc  jz      loc_180038722
0x180038002  mov     rax, [rcx]
0x180038005  lea     rdx, [rbp+var_20]
0x180038009  mov     rax, [rax+58h]
0x18003800d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038012  or      esi, 2
0x180038015  mov     rdx, r14; struct Windows::Internal::String *
0x180038018  mov     rcx, rax; this
0x18003801b  call    ?CompareOrdinal@String@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::String::CompareOrdinal(Windows::Internal::String const &)
0x180038020  test    eax, eax
0x180038022  jnz     loc_180038722
0x180038028  mov     bl, 1
0x18003802a  jmp     loc_180038724
0x18003802f  mov     rax, [rcx]
0x180038032  lea     r8, [rbp+arg_18]
0x180038036  mov     rdx, [r14]
0x180038039  mov     rax, [rax+40h]
0x18003803d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038042  mov     ebx, eax
0x180038044  test    eax, eax
0x180038046  js      loc_18003810D
0x18003804c  mov     al, [rbp+arg_18]
0x18003804f  test    al, al
0x180038051  jnz     loc_18003858E
0x180038057  mov     rbx, [r15+28h]
0x18003805b  lea     rcx, [rbp+var_38]
0x18003805f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180038064  lea     r9, [rbp+var_38]; struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration **
0x180038068  lea     r8, [rbp+arg_18]; unsigned __int8 *
0x18003806c  mov     rdx, r14; struct Windows::Internal::String *
0x18003806f  mov     rcx, rbx; this
0x180038072  call    ?RetrieveOutOfProcessActivatableClassRegistration@ActivationCatalogCollector@DEH@OSIntegration@@QEAAJAEBVString@Internal@Windows@@PEAEPEAPEAUOutOfProcessActivatableClassRegistration@23@@Z; OSIntegration::DEH::ActivationCatalogCollector::RetrieveOutOfProcessActivatableClassRegistration(Windows::Internal::String const &,uchar *,OSIntegration::DEH::OutOfProcessActivatableClassRegistration * *)
0x180038077  mov     ebx, eax
0x180038079  test    eax, eax
0x18003807b  jns     loc_180038459
0x180038081  mov     rcx, [rbp+40h]; this
0x180038085  mov     dword ptr [rsp+78h+var_50], eax; char *
0x180038089  lea     rax, aCollectorsGeta_8; "collectors->GetActivationCatalogCollect"...
0x180038090  mov     [rsp+78h+var_58], rax; char *
0x180038095  lea     r9, aOsintegrationD_236; "OSIntegration::DEH::OutOfProcessActivat"...
0x18003809c  lea     r8, aOnecoreAdminAp_86; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800380a3  mov     edx, 257h; void *
0x1800380a8  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800380ad  nop
0x1800380ae  mov     rcx, [rbp+var_38]
0x1800380b2  test    rcx, rcx
0x1800380b5  jz      short loc_1800380CC
0x1800380b7  mov     [rbp+var_38], 0
0x1800380bf  mov     rax, [rcx]
0x1800380c2  mov     rax, [rax+10h]
0x1800380c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800380cb  nop
0x1800380cc  mov     rcx, [rbp+var_30]
0x1800380d0  test    rcx, rcx
0x1800380d3  jz      short loc_1800380EA
0x1800380d5  mov     [rbp+var_30], 0
0x1800380dd  mov     rax, [rcx]
0x1800380e0  mov     rax, [rax+10h]
0x1800380e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800380e9  nop
0x1800380ea  mov     rcx, [rbp+var_40]
0x1800380ee  test    rcx, rcx
0x1800380f1  jz      short loc_180038108
0x1800380f3  mov     [rbp+var_40], 0
0x1800380fb  mov     rax, [rcx]
0x1800380fe  mov     rax, [rax+10h]
0x180038102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038107  nop
0x180038108  jmp     loc_1800381C0
0x18003810d  mov     rcx, [rbp+40h]; this
0x180038111  mov     dword ptr [rsp+78h+var_50], eax; char *
0x180038115  lea     rax, aInprocessactiv_1; "_inProcessActivatableClasses->HasKey(ac"...
0x18003811c  mov     [rsp+78h+var_58], rax; char *
0x180038121  lea     r9, aOsintegrationD_5; "OSIntegration::DEH::ActivationCatalogCo"...
0x180038128  lea     r8, aOnecoreAdminAp_86; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003812f  mov     edx, 0A7h; void *
0x180038134  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180038139  mov     rcx, [rbp+40h]; this
0x18003813d  mov     dword ptr [rsp+78h+var_50], ebx; char *
0x180038141  lea     rax, aCollectorsGeta_9; "collectors->GetActivationCatalogCollect"...
0x180038148  mov     [rsp+78h+var_58], rax; char *
0x18003814d  lea     r9, aOsintegrationD_236; "OSIntegration::DEH::OutOfProcessActivat"...
0x180038154  lea     r8, aOnecoreAdminAp_86; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003815b  mov     edx, 254h; void *
0x180038160  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180038165  nop
0x180038166  mov     rcx, [rbp+var_38]
0x18003816a  test    rcx, rcx
0x18003816d  jz      short loc_180038184
0x18003816f  mov     [rbp+var_38], 0
0x180038177  mov     rax, [rcx]
0x18003817a  mov     rax, [rax+10h]
0x18003817e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038183  nop
0x180038184  mov     rcx, [rbp+var_30]
0x180038188  test    rcx, rcx
0x18003818b  jz      short loc_1800381A2
0x18003818d  mov     [rbp+var_30], 0
0x180038195  mov     rax, [rcx]
0x180038198  mov     rax, [rax+10h]
0x18003819c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800381a1  nop
0x1800381a2  mov     rcx, [rbp+var_40]
0x1800381a6  test    rcx, rcx
0x1800381a9  jz      short loc_1800381C0
0x1800381ab  mov     [rbp+var_40], 0
0x1800381b3  mov     rdx, [rcx]
0x1800381b6  mov     rax, [rdx+10h]
0x1800381ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800381bf  nop
0x1800381c0  mov     eax, ebx
0x1800381c2  jmp     loc_1800382E8
0x1800381c7  mov     rax, [rcx]
0x1800381ca  lea     r8, [rbp+arg_18]
0x1800381ce  mov     rdx, [r12]
0x1800381d2  mov     rax, [rax+40h]
0x1800381d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800381db  mov     ebx, eax
0x1800381dd  test    eax, eax
0x1800381df  js      loc_1800382F9
0x1800381e5  mov     al, [rbp+arg_18]
0x1800381e8  test    al, al
0x1800381ea  jz      loc_1800386DF
0x1800381f0  mov     [rbp+var_20], rsi
0x1800381f4  mov     rdi, [rdi+38h]
0x1800381f8  mov     rax, [rdi]
0x1800381fb  mov     rbx, [rax+30h]
0x1800381ff  lea     rcx, [rbp+var_20]
0x180038203  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180038208  lea     r8, [rbp+var_20]
0x18003820c  mov     rdx, [r12]
0x180038210  mov     rcx, rdi
0x180038213  mov     rax, rbx
0x180038216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003821b  mov     ebx, eax
0x18003821d  test    eax, eax
0x18003821f  js      loc_180038492
0x180038225  mov     rax, [rbp+var_20]
0x180038229  mov     [rbp+var_28], rax
0x18003822d  mov     al, [rbp+arg_18]
0x180038230  test    al, al
0x180038232  jz      loc_1800386DF
0x180038238  lea     rcx, [rbp+var_40]
0x18003823c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180038241  lea     r8, [rbp+var_40]; struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration **
0x180038245  mov     rdx, [rbp+var_28]; struct OSIntegration::DEH::ExeServerRegistration *
0x180038249  mov     rcx, r14; struct Windows::Internal::String *
0x18003824c  call    ?Create@OutOfProcessActivatableClassRegistration_Impl@Internal@DEH@OSIntegration@@SAJAEBVString@2Windows@@PEAUExeServerRegistration@34@PEAPEAUOutOfProcessActivatableClassRegistration@34@@Z; OSIntegration::DEH::Internal::OutOfProcessActivatableClassRegistration_Impl::Create(Windows::Internal::String const &,OSIntegration::DEH::ExeServerRegistration *,OSIntegration::DEH::OutOfProcessActivatableClassRegistration * *)
0x180038251  mov     ebx, eax
0x180038253  test    eax, eax
0x180038255  js      loc_1800383BF
0x18003825b  mov     rdx, [rbp+var_40]; struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *
0x18003825f  mov     rcx, [r15+28h]; this
0x180038263  call    ?AddOutOfProcessActivatableClassRegistration@ActivationCatalogCollector@DEH@OSIntegration@@QEAAJPEAUOutOfProcessActivatableClassRegistration@23@@Z; OSIntegration::DEH::ActivationCatalogCollector::AddOutOfProcessActivatableClassRegistration(OSIntegration::DEH::OutOfProcessActivatableClassRegistration *)
0x180038268  mov     ebx, eax
0x18003826a  test    eax, eax
0x18003826c  js      loc_18003862A
0x180038272  mov     rax, [rbp+var_40]
0x180038276  mov     [rbp+var_40], rsi
0x18003827a  mov     [r13+0], rax
0x18003827e  mov     rcx, [rbp+var_28]
0x180038282  test    rcx, rcx
0x180038285  jz      short loc_180038298
0x180038287  mov     [rbp+var_28], rsi
0x18003828b  mov     rax, [rcx]
0x18003828e  mov     rax, [rax+10h]
0x180038292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038297  nop
0x180038298  mov     rcx, [rbp+var_38]
0x18003829c  test    rcx, rcx
0x18003829f  jz      short loc_1800382B2
0x1800382a1  mov     [rbp+var_38], rsi
0x1800382a5  mov     rax, [rcx]
0x1800382a8  mov     rax, [rax+10h]
0x1800382ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382b1  nop
0x1800382b2  mov     rcx, [rbp+var_30]
0x1800382b6  test    rcx, rcx
0x1800382b9  jz      short loc_1800382CC
0x1800382bb  mov     [rbp+var_30], rsi
0x1800382bf  mov     rax, [rcx]
0x1800382c2  mov     rax, [rax+10h]
0x1800382c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382cb  nop
0x1800382cc  mov     rcx, [rbp+var_40]
0x1800382d0  test    rcx, rcx
0x1800382d3  jz      short loc_1800382E6
0x1800382d5  mov     [rbp+var_40], rsi
0x1800382d9  mov     rax, [rcx]
0x1800382dc  mov     rax, [rax+10h]
0x1800382e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382e5  nop
0x1800382e6  xor     eax, eax
0x1800382e8  add     rsp, 78h
0x1800382ec  pop     r15
0x1800382ee  pop     r14
0x1800382f0  pop     r13
0x1800382f2  pop     r12
0x1800382f4  pop     rdi
0x1800382f5  pop     rsi
0x1800382f6  pop     rbx
0x1800382f7  pop     rbp
0x1800382f8  retn
0x1800382f9  mov     rcx, [rbp+40h]; this
0x1800382fd  mov     dword ptr [rsp+78h+var_50], eax; char *
0x180038301  lea     rax, aExeserversHask; "_exeServers->HasKey(serverName, found)"
0x180038308  mov     [rsp+78h+var_58], rax; char *
0x18003830d  lea     r9, aOsintegrationD_203; "OSIntegration::DEH::ActivationCatalogCo"...
0x180038314  lea     r8, aOnecoreAdminAp_86; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003831b  mov     edx, 0DEh; void *
0x180038320  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180038325  mov     rcx, [rbp+40h]; this
0x180038329  mov     dword ptr [rsp+78h+var_50], ebx; char *
0x18003832d  lea     rax, aCollectorsGeta_0; "collectors->GetActivationCatalogCollect"...
0x180038334  mov     [rsp+78h+var_58], rax; char *
0x180038339  lea     r9, aOsintegrationD_236; "OSIntegration::DEH::OutOfProcessActivat"...
0x180038340  lea     r8, aOnecoreAdminAp_86; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180038347  mov     edx, 274h; void *
0x18003834c  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180038351  nop
0x180038352  mov     rcx, [rbp+var_28]
0x180038356  test    rcx, rcx
0x180038359  jz      short loc_18003836C
0x18003835b  mov     [rbp+var_28], rsi
0x18003835f  mov     rax, [rcx]
0x180038362  mov     rax, [rax+10h]
0x180038366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003836b  nop
0x18003836c  mov     rcx, [rbp+var_38]
0x180038370  test    rcx, rcx
0x180038373  jz      short loc_180038386
0x180038375  mov     [rbp+var_38], rsi
0x180038379  mov     rax, [rcx]
0x18003837c  mov     rax, [rax+10h]
0x180038380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038385  nop
0x180038386  mov     rcx, [rbp+var_30]
0x18003838a  test    rcx, rcx
0x18003838d  jz      short loc_1800383A0
0x18003838f  mov     [rbp+var_30], rsi
0x180038393  mov     rax, [rcx]
0x180038396  mov     rax, [rax+10h]
0x18003839a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003839f  nop
0x1800383a0  mov     rcx, [rbp+var_40]
0x1800383a4  test    rcx, rcx
0x1800383a7  jz      short loc_1800383BA
0x1800383a9  mov     [rbp+var_40], rsi
0x1800383ad  mov     rdx, [rcx]
0x1800383b0  mov     rax, [rdx+10h]
  ... truncated ...
```
