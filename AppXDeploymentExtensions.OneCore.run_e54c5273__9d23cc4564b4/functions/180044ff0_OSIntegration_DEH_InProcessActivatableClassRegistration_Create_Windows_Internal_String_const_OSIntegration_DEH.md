# OSIntegration::DEH::InProcessActivatableClassRegistration::Create(Windows::Internal::String const &,OSIntegration::DEH::Collectors *,OSIntegration::DEH::InProcessActivatableClassRegistration * *)

- ea: `0x180044ff0`
- end: `0x1800459fc`
- name: `?Create@InProcessActivatableClassRegistration@DEH@OSIntegration@@SAJAEBVString@Internal@Windows@@PEAVCollectors@23@PEAPEAU123@@Z`
- size: `2572`
- prototype: `__int64 __fastcall(const struct Windows::Internal::String *, struct OSIntegration::DEH::Collectors *, struct OSIntegration::DEH::InProcessActivatableClassRegistration **)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180043ed0`

## callees

- `0x18000b3bc`
- `0x18003a300`
- `0x180044ff0`
- `0x180046230`
- `0x180059bbc`
- `0x180059d30`
- `0x180098ed0`
- `0x18009aff4`
- `0x1800cc418`
- `0x1800cdcbc`
- `0x1800fc0ec`
- `0x18012ba10`
- `0x1801a705c`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18004504f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18004504f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18004503e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18004503e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800451de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800451de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18004502b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18004502b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045876`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004589a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800458d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800458f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004598b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800459af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045876`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004589a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800458d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800458f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004598b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800459af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800451fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045209`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045252`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004546f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800451fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045209`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045252`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004546f`

## string_xrefs

- `0x1800459d3`: `APPX_E_INVALID_MANIFEST`
- `0x180045385`: `OSIntegration::DEH::InProcessActivatableClassRegistration::Create`
- `0x180045489`: `OSIntegration::DEH::InProcessActivatableClassRegistration::Create`
- `0x18004554d`: `OSIntegration::DEH::InProcessActivatableClassRegistration::Create`
- `0x1800455fb`: `OSIntegration::DEH::InProcessActivatableClassRegistration::Create`
- `0x18004583e`: `OSIntegration::DEH::InProcessActivatableClassRegistration::Create`
- `0x18004592e`: `OSIntegration::DEH::InProcessActivatableClassRegistration::Create`
- `0x180045965`: `OSIntegration::DEH::InProcessActivatableClassRegistration::Create`
- `0x1800459df`: `OSIntegration::DEH::InProcessActivatableClassRegistration::Create`
- `0x180045541`: `collectors->GetActivationCatalogCollector()->RetrieveOutOfProcessActivatableClassRegistration(activatableClassId, &found, &retrievedOutOfProcClassRegistration)`
- `0x180045379`: `InProcessActivatableClassRegistration_Impl::Create(activatableClassId, &classRegistration)`
- `0x1800455c3`: `_inProcessActivatableClasses->HasKey(activatableClassId, found)`
- `0x1800455ef`: `collectors->GetActivationCatalogCollector()->RetrieveInProcessActivatableClassRegistration(activatableClassId, &found, &retrievedInProcClassRegistration)`
- `0x1800454cc`: `_outOfProcessActivatableClasses->HasKey(activatableClassId, found)`
- `0x1800454fa`: `_outOfProcessActivatableClasses->Lookup(activatableClassId, &registration)`
- `0x180045337`: `registration->Initialize(activatableClassId)`
- `0x180045343`: `OSIntegration::DEH::Internal::InProcessActivatableClassRegistration_Impl::Create`
- `0x180045713`: `OSIntegration::DEH::Internal::InProcessActivatableClassRegistration_Impl::Create`
- `0x18004543e`: `_inProcessActivatableClasses->Insert(acid.Get(), static_cast<IDllServerActivatableClassRegistration*>(activatableClass), &replaced)`
- `0x1800456b2`: `RegistryMapFactory< IDllServerActivatableClassRegistration * >::RegistryMap::Make(&_inProcessActivatableClasses)`
- `0x180045739`: `acid.Initialize(activatableClass->get_ActivatableClassId())`
- `0x18004579e`: `_inProcessActivatableClasses->Lookup(activatableClassId, &registration)`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall OSIntegration::DEH::InProcessActivatableClassRegistration::Create(
        HSTRING *a1,
        struct OSIntegration::DEH::Collectors *a2,
        struct OSIntegration::DEH::InProcessActivatableClassRegistration **a3)
{
  char v6; // r14
  HSTRING v7; // rbx
  __int64 v8; // rdi
  char v9; // al
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdi
  char v14; // al
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING, _DWORD **); // rbx
  int v19; // eax
  struct OSIntegration::DEH::InProcessActivatableClassRegistration *v20; // r14
  int v21; // eax
  HRESULT v22; // edi
  HSTRING v23; // rbx
  __int64 v24; // r15
  HSTRING *v25; // rax
  HSTRING v26; // rsi
  int v27; // eax
  struct OSIntegration::DEH::InProcessActivatableClassRegistration *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rcx
  struct OSIntegration::DEH::InProcessActivatableClassRegistration *v31; // rcx
  Windows::Internal::String *v33; // rax
  Windows::Internal::String *v34; // rax
  bool v35; // bl
  __int64 v36; // rcx
  __int64 v37; // rcx
  void *v38; // rax
  _BYTE *v39; // rsi
  const char *v40; // rax
  __int64 v41; // rdx
  bool v42; // zf
  _DWORD *v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rdi
  __int64 (__fastcall *v49)(__int64, HSTRING, _DWORD **); // rbx
  int v50; // eax
  _DWORD *v51; // rax
  PCWSTR v52; // rax
  PCWSTR v53; // rax
  __int64 v54; // rdx
  __int64 v55; // rdx
  PCWSTR v56; // rax
  PCWSTR v57; // rax
  __int64 v58; // rdx
  PCWSTR StringRawBuffer; // rax
  PCWSTR v60; // rax
  __int64 v61; // rdx
  char *v62; // [rsp+28h] [rbp-38h]
  char *v63; // [rsp+28h] [rbp-38h]
  char *v64; // [rsp+28h] [rbp-38h]
  char *v65; // [rsp+28h] [rbp-38h]
  char *v66; // [rsp+28h] [rbp-38h]
  char *v67; // [rsp+28h] [rbp-38h]
  char *v68; // [rsp+28h] [rbp-38h]
  __int64 v69; // [rsp+30h] [rbp-30h] BYREF
  struct OSIntegration::DEH::InProcessActivatableClassRegistration *v70; // [rsp+38h] [rbp-28h] BYREF
  __int64 v71; // [rsp+40h] [rbp-20h] BYREF
  HSTRING v72; // [rsp+48h] [rbp-18h]
  HSTRING string[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+98h] [rbp+38h]
  char v75; // [rsp+A0h] [rbp+40h] BYREF
  _DWORD *hasEmbedNull; // [rsp+B0h] [rbp+50h] BYREF
  HSTRING newString; // [rsp+B8h] [rbp+58h] BYREF

  v6 = 0;
  LODWORD(newString) = 0;
  *a3 = 0;
  v7 = *a1;
  LODWORD(hasEmbedNull) = 0;
  WindowsStringHasEmbeddedNull(v7, (BOOL *)&hasEmbedNull);
  if ( (_DWORD)hasEmbedNull || WindowsIsStringEmpty(v7) || WindowsGetStringLen(v7) > 0x100 )
  {
    v12 = -2146958844;
    LODWORD(v62) = -2146958844;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0x20C,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::InProcessActivatableClassRegistration::Create",
      "((HRESULT)0x80080204L)",
      v62,
      v69);
    if ( (byte_1802E21C5 & 0x20) != 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(*a1, 0);
      McTemplateU0dz_EventWriteTransfer(
        &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
        ActivatableClassIdentifierInvalid,
        2148008452LL,
        StringRawBuffer);
    }
    v60 = WindowsGetStringRawBuffer(*a1, 0);
    details::appxLog<long,unsigned short const *>(
      2148008452LL,
      v61,
      ActivatableClassIdentifierInvalid,
      2148008452LL,
      v60);
    LODWORD(v68) = -2146958844;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x20E,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::InProcessActivatableClassRegistration::Create",
      "APPX_E_INVALID_MANIFEST",
      v68,
      v69);
    return v12;
  }
  v70 = 0;
  v69 = 0;
  v8 = *((_QWORD *)a2 + 5);
  v9 = 0;
  v75 = 0;
  v71 = 0;
  v10 = *(_QWORD *)(v8 + 40);
  if ( v10 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, HSTRING, char *))(*(_QWORD *)v10 + 64LL))(v10, *a1, &v75);
    v12 = v11;
    if ( v11 < 0 )
    {
      LODWORD(v62) = v11;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0xA7,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
        "OSIntegration::DEH::ActivationCatalogCollector::RetrieveInProcessActivatableClassRegistration",
        "_inProcessActivatableClasses->HasKey(activatableClassId, found)",
        v62,
        v69);
      goto LABEL_63;
    }
    if ( !v75 )
      goto LABEL_7;
    hasEmbedNull = 0;
    v48 = *(_QWORD *)(v8 + 40);
    v49 = *(__int64 (__fastcall **)(__int64, HSTRING, _DWORD **))(*(_QWORD *)v48 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hasEmbedNull);
    v50 = v49(v48, *a1, &hasEmbedNull);
    v12 = v50;
    if ( v50 < 0 )
    {
      LODWORD(v62) = v50;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0xAB,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
        "OSIntegration::DEH::ActivationCatalogCollector::RetrieveInProcessActivatableClassRegistration",
        "_inProcessActivatableClasses->Lookup(activatableClassId, &registration)",
        v62,
        v69);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hasEmbedNull);
LABEL_63:
      LODWORD(v66) = v12;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x215,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
        "OSIntegration::DEH::InProcessActivatableClassRegistration::Create",
        "collectors->GetActivationCatalogCollector()->RetrieveInProcessActivatableClassRegistration(activatableClassId, &"
        "found, &retrievedInProcClassRegistration)",
        v66,
        v69);
      v46 = v69;
      if ( v69 )
      {
        v69 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      }
      return v12;
    }
    v51 = hasEmbedNull;
    hasEmbedNull = 0;
    v71 = (unsigned __int64)(v51 - 4) & -(__int64)(v51 != 0);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hasEmbedNull);
    v9 = v75;
  }
  if ( v9 )
    goto LABEL_33;
LABEL_7:
  v13 = *((_QWORD *)a2 + 5);
  v14 = 0;
  v75 = 0;
  v69 = 0;
  v15 = *(_QWORD *)(v13 + 48);
  if ( !v15 )
    goto LABEL_12;
  v16 = (*(__int64 (__fastcall **)(__int64, HSTRING, char *))(*(_QWORD *)v15 + 64LL))(v15, *a1, &v75);
  v12 = v16;
  if ( v16 < 0 )
  {
    LODWORD(v62) = v16;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xC3,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::ActivationCatalogCollector::RetrieveOutOfProcessActivatableClassRegistration",
      "_outOfProcessActivatableClasses->HasKey(activatableClassId, found)",
      v62,
      v69);
LABEL_57:
    LODWORD(v65) = v12;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x218,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::InProcessActivatableClassRegistration::Create",
      "collectors->GetActivationCatalogCollector()->RetrieveOutOfProcessActivatableClassRegistration(activatableClassId, "
      "&found, &retrievedOutOfProcClassRegistration)",
      v65,
      v69);
    v44 = v69;
    if ( v69 )
    {
      v69 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    }
    v45 = v71;
    if ( v71 )
    {
      v71 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    }
    return v12;
  }
  if ( !v75 )
    goto LABEL_13;
  hasEmbedNull = 0;
  v17 = *(_QWORD *)(v13 + 48);
  v18 = *(__int64 (__fastcall **)(__int64, HSTRING, _DWORD **))(*(_QWORD *)v17 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hasEmbedNull);
  v19 = v18(v17, *a1, &hasEmbedNull);
  v12 = v19;
  if ( v19 < 0 )
  {
    LODWORD(v62) = v19;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::ActivationCatalogCollector::RetrieveOutOfProcessActivatableClassRegistration",
      "_outOfProcessActivatableClasses->Lookup(activatableClassId, &registration)",
      v62,
      v69);
    v43 = hasEmbedNull;
    if ( hasEmbedNull )
    {
      hasEmbedNull = 0;
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v43 + 16LL))(v43);
    }
    goto LABEL_57;
  }
  v69 = (unsigned __int64)(hasEmbedNull - 4) & -(__int64)(hasEmbedNull != 0);
  v14 = v75;
LABEL_12:
  if ( v14 )
  {
LABEL_33:
    v35 = 1;
    if ( !v71
      || (v33 = (Windows::Internal::String *)(*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v71 + 88LL))(
                                               v71,
                                               string),
          v6 = 1,
          LODWORD(newString) = 1,
          (unsigned int)Windows::Internal::String::CompareOrdinal(v33, (const struct Windows::Internal::String *)a1)) )
    {
      if ( !v69
        || (v34 = (Windows::Internal::String *)(*(__int64 (__fastcall **)(__int64, _DWORD **))(*(_QWORD *)v69 + 88LL))(
                                                 v69,
                                                 &hasEmbedNull),
            v6 |= 2u,
            (unsigned int)Windows::Internal::String::CompareOrdinal(v34, (const struct Windows::Internal::String *)a1)) )
      {
        v35 = 0;
      }
    }
    if ( (v6 & 2) != 0 )
    {
      v6 &= ~2u;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&hasEmbedNull);
    }
    if ( (v6 & 1) != 0 )
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(string);
    LODWORD(v62) = -2147024736;
    if ( v35 )
    {
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0x224,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
        "OSIntegration::DEH::InProcessActivatableClassRegistration::Create",
        "HRESULT_FROM_WIN32(160L)",
        v62,
        v69);
      if ( (byte_1802E21C5 & 0x20) != 0 )
      {
        v52 = WindowsGetStringRawBuffer(*a1, 0);
        McTemplateU0dz_EventWriteTransfer(
          &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
          CollidingActivatableClassIdentifiers,
          2147942560LL,
          v52);
      }
      v53 = WindowsGetStringRawBuffer(*a1, 0);
      details::appxLog<long,unsigned short const *>(
        2147942560LL,
        v54,
        CollidingActivatableClassIdentifiers,
        2147942560LL,
        v53);
      v55 = 550;
    }
    else
    {
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0x22E,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
        "OSIntegration::DEH::InProcessActivatableClassRegistration::Create",
        "HRESULT_FROM_WIN32(160L)",
        v62,
        v69);
      if ( (byte_1802E21C5 & 0x20) != 0 )
      {
        v56 = WindowsGetStringRawBuffer(*a1, 0);
        McTemplateU0dz_EventWriteTransfer(
          &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
          DuplicateActivatableClassIdentifiers,
          2147942560LL,
          v56);
      }
      v57 = WindowsGetStringRawBuffer(*a1, 0);
      details::appxLog<long,unsigned short const *>(
        2147942560LL,
        v58,
        DuplicateActivatableClassIdentifiers,
        2147942560LL,
        v57);
      v55 = 560;
    }
    LODWORD(v67) = 160;
    v22 = wil::details::in1diag5::Return_Win32(
            retaddr,
            (void *)v55,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
            "OSIntegration::DEH::InProcessActivatableClassRegistration::Create",
            "ERROR_BAD_ARGUMENTS",
            v67,
            v69);
    goto LABEL_53;
  }
LABEL_13:
  Microsoft::WRL::Details::Make<OSIntegration::DEH::Internal::InProcessActivatableClassRegistration_Impl,>(&hasEmbedNull);
  v20 = (struct OSIntegration::DEH::InProcessActivatableClassRegistration *)hasEmbedNull;
  if ( !hasEmbedNull )
  {
    v22 = -2147024882;
    LODWORD(v62) = -2147024882;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x115,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activatableclassregistration.cpp",
      "OSIntegration::DEH::Internal::InProcessActivatableClassRegistration_Impl::Create",
      "registration",
      v62,
      v69);
LABEL_40:
    LODWORD(v63) = v22;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x234,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::InProcessActivatableClassRegistration::Create",
      "InProcessActivatableClassRegistration_Impl::Create(activatableClassId, &classRegistration)",
      v63,
      v69);
    v36 = v69;
    if ( v69 )
    {
      v69 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
    v37 = v71;
    if ( v71 )
    {
      v71 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
    return (unsigned int)v22;
  }
  v21 = (*(__int64 (__fastcall **)(_DWORD *, HSTRING *))(*(_QWORD *)hasEmbedNull + 176LL))(hasEmbedNull, a1);
  v22 = v21;
  if ( v21 < 0 )
  {
    LODWORD(v62) = v21;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x117,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activatableclassregistration.cpp",
      "OSIntegration::DEH::Internal::InProcessActivatableClassRegistration_Impl::Create",
      "registration->Initialize(activatableClassId)",
      v62,
      v69);
    if ( v20 )
      (*(void (__fastcall **)(struct OSIntegration::DEH::InProcessActivatableClassRegistration *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_40;
  }
  *((_DWORD *)v20 + 12) = 0;
  v70 = v20;
  v23 = 0;
  v72 = 0;
  if ( !v20 )
  {
    v22 = -2147024809;
    LODWORD(v62) = -2147024809;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::ActivationCatalogCollector::AddInProcessActivatableClassRegistration",
      "activatableClass",
      v62,
      v69);
LABEL_52:
    LODWORD(v64) = v22;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x236,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::InProcessActivatableClassRegistration::Create",
      "collectors->GetActivationCatalogCollector()->AddInProcessActivatableClassRegistration(classRegistration.Get())",
      v64,
      v69);
LABEL_53:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
    return (unsigned int)v22;
  }
  v24 = *((_QWORD *)a2 + 5);
  v25 = (HSTRING *)(*(__int64 (__fastcall **)(struct OSIntegration::DEH::InProcessActivatableClassRegistration *, HSTRING *))(*(_QWORD *)v20 + 88LL))(
                     v20,
                     string);
  newString = 0;
  v22 = WindowsDuplicateString(*v25, &newString);
  v26 = 0;
  if ( v22 >= 0 )
  {
    v23 = newString;
    v72 = newString;
    v26 = newString;
    WindowsDeleteString(0);
  }
  if ( string[0] )
    WindowsDeleteString(string[0]);
  if ( v22 < 0 )
  {
    LODWORD(v62) = v22;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::ActivationCatalogCollector::AddInProcessActivatableClassRegistration",
      "acid.Initialize(activatableClass->get_ActivatableClassId())",
      v62,
      v69);
    v42 = v26 == 0;
LABEL_50:
    if ( !v42 )
      WindowsDeleteString(v23);
    goto LABEL_52;
  }
  if ( *(_QWORD *)(v24 + 40) )
    goto LABEL_22;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v24 + 40);
  *(_QWORD *)(v24 + 40) = 0;
  v38 = operator new(0xA0u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v38 )
  {
    v39 = 0;
LABEL_47:
    v22 = -2147024882;
    goto LABEL_69;
  }
  v47 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Foundation::IDllServerActivatableClassRegistration *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IDllServerActivatableClassRegistration *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Foundation::IDllServerActivatableClassRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::HashMap<HSTRING__ *,Windows::Foundation::IDllServerActivatableClassRegistration *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IDllServerActivatableClassRegistration *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Foundation::IDllServerActivatableClassRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>(v38);
  v39 = (_BYTE *)v47;
  if ( !v47 )
    goto LABEL_47;
  v22 = XWinRT::SecureVersionTag::TagManager::Initialize((XWinRT::SecureVersionTag::TagManager *)(v47 + 144));
  if ( v22 >= 0 )
  {
    v39[152] = 1;
    *(_QWORD *)(v24 + 40) = v39;
    v39 = 0;
  }
LABEL_69:
  if ( v39 )
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v39 + 16LL))(v39);
  if ( v22 < 0 )
  {
    LODWORD(v62) = v22;
    v40 = "RegistryMapFactory< IDllServerActivatableClassRegistration * >::RegistryMap::Make(&_inProcessActivatableClasses)";
    v41 = 59;
    goto LABEL_49;
  }
LABEL_22:
  LOBYTE(hasEmbedNull) = 0;
  v27 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, _DWORD *, _DWORD **))(**(_QWORD **)(v24 + 40) + 80LL))(
          *(_QWORD *)(v24 + 40),
          v23,
          (_DWORD *)v20 + 4,
          &hasEmbedNull);
  v22 = v27;
  if ( v27 < 0 )
  {
    LODWORD(v62) = v27;
    v40 = "_inProcessActivatableClasses->Insert(acid.Get(), static_cast<IDllServerActivatableClassRegistration*>(activata"
          "bleClass), &replaced)";
    v41 = 65;
LABEL_49:
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v41,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::ActivationCatalogCollector::AddInProcessActivatableClassRegistration",
      v40,
      v62,
      v69);
    v42 = v23 == 0;
    goto LABEL_50;
  }
  if ( v23 )
    WindowsDeleteString(v23);
  v28 = v70;
  v70 = 0;
  *a3 = v28;
  v29 = v69;
  if ( v69 )
  {
    v69 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  v30 = v71;
  if ( v71 )
  {
    v71 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  v31 = v70;
  if ( v70 )
  {
    v70 = 0;
    (*(void (__fastcall **)(struct OSIntegration::DEH::InProcessActivatableClassRegistration *))(*(_QWORD *)v31 + 16LL))(v31);
  }
  return 0;
}

```

## disassembly

```asm
0x180044ff0  mov     [rsp-38h+arg_8], rbx
0x180044ff5  push    rbp
0x180044ff6  push    rsi
0x180044ff7  push    rdi
0x180044ff8  push    r12
0x180044ffa  push    r13
0x180044ffc  push    r14
0x180044ffe  push    r15
0x180045000  mov     rbp, rsp
0x180045003  sub     rsp, 60h
0x180045007  mov     r12, r8
0x18004500a  mov     r15, rdx
0x18004500d  mov     rsi, rcx
0x180045010  xor     r13d, r13d
0x180045013  mov     r14d, r13d
0x180045016  mov     dword ptr [rbp+newString], r13d
0x18004501a  mov     [r8], r13
0x18004501d  mov     rbx, [rcx]
0x180045020  mov     dword ptr [rbp+hasEmbedNull], r13d
0x180045024  lea     rdx, [rbp+hasEmbedNull]; hasEmbedNull
0x180045028  mov     rcx, rbx; string
0x18004502b  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180045031  cmp     dword ptr [rbp+hasEmbedNull], r13d
0x180045035  jnz     loc_18004594C
0x18004503b  mov     rcx, rbx; string
0x18004503e  call    cs:__imp_WindowsIsStringEmpty
0x180045044  test    eax, eax
0x180045046  jnz     loc_18004594C
0x18004504c  mov     rcx, rbx; string
0x18004504f  call    cs:__imp_WindowsGetStringLen
0x180045055  cmp     eax, 100h
0x18004505a  ja      loc_18004594C
0x180045060  mov     [rbp+var_28], r13
0x180045064  mov     [rbp+var_30], r13
0x180045068  mov     rdi, [r15+28h]
0x18004506c  mov     al, r13b
0x18004506f  mov     [rbp+arg_0], al
0x180045072  mov     [rbp+var_20], r13
0x180045076  mov     rcx, [rdi+28h]
0x18004507a  test    rcx, rcx
0x18004507d  jz      loc_1800452B9
0x180045083  mov     rax, [rcx]
0x180045086  lea     r8, [rbp+arg_0]
0x18004508a  mov     rdx, [rsi]
0x18004508d  mov     rax, [rax+40h]
0x180045091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045096  mov     ebx, eax
0x180045098  test    eax, eax
0x18004509a  js      loc_1800455BB
0x1800450a0  mov     al, [rbp+arg_0]
0x1800450a3  test    al, al
0x1800450a5  jnz     loc_180045766
0x1800450ab  mov     rdi, [r15+28h]
0x1800450af  mov     rcx, [rbp+var_30]
0x1800450b3  test    rcx, rcx
0x1800450b6  jz      short loc_1800450C9
0x1800450b8  mov     [rbp+var_30], r13
0x1800450bc  mov     rax, [rcx]
0x1800450bf  mov     rax, [rax+10h]
0x1800450c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800450c8  nop
0x1800450c9  mov     al, r13b
0x1800450cc  mov     [rbp+arg_0], al
0x1800450cf  mov     [rbp+var_30], r13
0x1800450d3  mov     rcx, [rdi+30h]
0x1800450d7  test    rcx, rcx
0x1800450da  jz      short loc_18004514C
0x1800450dc  mov     rax, [rcx]
0x1800450df  lea     r8, [rbp+arg_0]
0x1800450e3  mov     rdx, [rsi]
0x1800450e6  mov     rax, [rax+40h]
0x1800450ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800450ef  mov     ebx, eax
0x1800450f1  test    eax, eax
0x1800450f3  js      loc_1800454C4
0x1800450f9  mov     al, [rbp+arg_0]
0x1800450fc  test    al, al
0x1800450fe  jz      short loc_180045154
0x180045100  mov     [rbp+hasEmbedNull], r13
0x180045104  mov     rdi, [rdi+30h]
0x180045108  mov     rax, [rdi]
0x18004510b  mov     rbx, [rax+30h]
0x18004510f  lea     rcx, [rbp+hasEmbedNull]
0x180045113  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180045118  lea     r8, [rbp+hasEmbedNull]
0x18004511c  mov     rdx, [rsi]
0x18004511f  mov     rcx, rdi
0x180045122  mov     rax, rbx
0x180045125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004512a  mov     ebx, eax
0x18004512c  test    eax, eax
0x18004512e  js      loc_1800454F2
0x180045134  mov     rax, [rbp+hasEmbedNull]
0x180045138  lea     rcx, [rax-10h]
0x18004513c  neg     rax
0x18004513f  sbb     rax, rax
0x180045142  and     rax, rcx
0x180045145  mov     [rbp+var_30], rax
0x180045149  mov     al, [rbp+arg_0]
0x18004514c  test    al, al
0x18004514e  jnz     loc_1800452C1
0x180045154  mov     rcx, [rbp+var_28]
0x180045158  test    rcx, rcx
0x18004515b  jz      short loc_18004516E
0x18004515d  mov     [rbp+var_28], r13
0x180045161  mov     rax, [rcx]
0x180045164  mov     rax, [rax+10h]
0x180045168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004516d  nop
0x18004516e  lea     rcx, [rbp+hasEmbedNull]
0x180045172  call    ??$Make@VInProcessActivatableClassRegistration_Impl@Internal@DEH@OSIntegration@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VInProcessActivatableClassRegistration_Impl@Internal@DEH@OSIntegration@@@12@XZ; Microsoft::WRL::Details::Make<OSIntegration::DEH::Internal::InProcessActivatableClassRegistration_Impl,>(void)
0x180045177  nop
0x180045178  mov     r14, [rbp+hasEmbedNull]
0x18004517c  test    r14, r14
0x18004517f  jz      loc_1800456FA
0x180045185  mov     rax, [r14]
0x180045188  mov     rdx, rsi
0x18004518b  mov     rcx, r14
0x18004518e  mov     rax, [rax+0B0h]
0x180045195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004519a  mov     edi, eax
0x18004519c  test    eax, eax
0x18004519e  js      loc_18004532F
0x1800451a4  mov     [r14+30h], r13d
0x1800451a8  mov     [rbp+var_28], r14
0x1800451ac  mov     rbx, r13
0x1800451af  mov     [rbp+var_18], rbx
0x1800451b3  test    r14, r14
0x1800451b6  jz      loc_1800456C3
0x1800451bc  mov     r15, [r15+28h]
0x1800451c0  mov     rax, [r14]
0x1800451c3  lea     rdx, [rbp+string]
0x1800451c7  mov     rcx, r14
0x1800451ca  mov     rax, [rax+58h]
0x1800451ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800451d3  mov     [rbp+newString], r13
0x1800451d7  lea     rdx, [rbp+newString]; newString
0x1800451db  mov     rcx, [rax]; string
0x1800451de  call    cs:__imp_WindowsDuplicateString
0x1800451e4  mov     edi, eax
0x1800451e6  mov     rsi, r13
0x1800451e9  test    eax, eax
0x1800451eb  js      short loc_180045200
0x1800451ed  mov     rbx, [rbp+newString]
0x1800451f1  mov     [rbp+var_18], rbx
0x1800451f5  mov     rsi, rbx
0x1800451f8  xor     ecx, ecx; string
0x1800451fa  call    cs:__imp_WindowsDeleteString
0x180045200  mov     rcx, [rbp+string]; string
0x180045204  test    rcx, rcx
0x180045207  jz      short loc_18004520F
0x180045209  call    cs:__imp_WindowsDeleteString
0x18004520f  test    edi, edi
0x180045211  js      loc_180045731
0x180045217  cmp     [r15+28h], r13
0x18004521b  jz      loc_180045406
0x180045221  mov     byte ptr [rbp+hasEmbedNull], r13b
0x180045225  mov     rcx, [r15+28h]
0x180045229  mov     rax, [rcx]
0x18004522c  lea     r8, [r14+10h]
0x180045230  lea     r9, [rbp+hasEmbedNull]
0x180045234  mov     rdx, rbx
0x180045237  mov     rax, [rax+50h]
0x18004523b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045240  mov     edi, eax
0x180045242  test    eax, eax
0x180045244  js      loc_18004543A
0x18004524a  test    rbx, rbx
0x18004524d  jz      short loc_180045258
0x18004524f  mov     rcx, rbx; string
0x180045252  call    cs:__imp_WindowsDeleteString
0x180045258  mov     rax, [rbp+var_28]
0x18004525c  mov     [rbp+var_28], r13
0x180045260  mov     [r12], rax
0x180045264  mov     rcx, [rbp+var_30]
0x180045268  test    rcx, rcx
0x18004526b  jz      short loc_18004527E
0x18004526d  mov     [rbp+var_30], r13
0x180045271  mov     rax, [rcx]
0x180045274  mov     rax, [rax+10h]
0x180045278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004527d  nop
0x18004527e  mov     rcx, [rbp+var_20]
0x180045282  test    rcx, rcx
0x180045285  jz      short loc_180045298
0x180045287  mov     [rbp+var_20], r13
0x18004528b  mov     rax, [rcx]
0x18004528e  mov     rax, [rax+10h]
0x180045292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045297  nop
0x180045298  mov     rcx, [rbp+var_28]
0x18004529c  test    rcx, rcx
0x18004529f  jz      short loc_1800452B2
0x1800452a1  mov     [rbp+var_28], r13
0x1800452a5  mov     rax, [rcx]
0x1800452a8  mov     rax, [rax+10h]
0x1800452ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800452b1  nop
0x1800452b2  xor     eax, eax
0x1800452b4  jmp     loc_1800453EE
0x1800452b9  test    al, al
0x1800452bb  jz      loc_1800450AB
0x1800452c1  mov     rcx, [rbp+var_20]
0x1800452c5  test    rcx, rcx
0x1800452c8  jz      short loc_1800452F4
0x1800452ca  mov     rax, [rcx]
0x1800452cd  lea     rdx, [rbp+string]
0x1800452d1  mov     rax, [rax+58h]
0x1800452d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800452da  nop
0x1800452db  mov     r14d, 1
0x1800452e1  mov     dword ptr [rbp+newString], r14d
0x1800452e5  mov     rdx, rsi; struct Windows::Internal::String *
0x1800452e8  mov     rcx, rax; this
0x1800452eb  call    ?CompareOrdinal@String@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::String::CompareOrdinal(Windows::Internal::String const &)
0x1800452f0  test    eax, eax
0x1800452f2  jz      short loc_180045328
0x1800452f4  mov     rcx, [rbp+var_30]
0x1800452f8  test    rcx, rcx
0x1800452fb  jz      loc_18004580D
0x180045301  mov     rax, [rcx]
0x180045304  lea     rdx, [rbp+hasEmbedNull]
0x180045308  mov     rax, [rax+58h]
0x18004530c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045311  or      r14d, 2
0x180045315  mov     rdx, rsi; struct Windows::Internal::String *
0x180045318  mov     rcx, rax; this
0x18004531b  call    ?CompareOrdinal@String@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::String::CompareOrdinal(Windows::Internal::String const &)
0x180045320  test    eax, eax
0x180045322  jnz     loc_18004580D
0x180045328  mov     bl, 1
0x18004532a  jmp     loc_180045810
0x18004532f  mov     rcx, [rbp+38h]; this
0x180045333  mov     dword ptr [rsp+60h+var_38], eax; char *
0x180045337  lea     rax, aRegistrationIn; "registration->Initialize(activatableCla"...
0x18004533e  mov     [rsp+60h+var_40], rax; char *
0x180045343  lea     r9, aOsintegrationD_20; "OSIntegration::DEH::Internal::InProcess"...
0x18004534a  lea     r8, aOnecoreAdminAp_30; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180045351  mov     edx, 117h; void *
0x180045356  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18004535b  nop
0x18004535c  test    r14, r14
0x18004535f  jz      short loc_180045371
0x180045361  mov     rax, [r14]
0x180045364  mov     rcx, r14
0x180045367  mov     rax, [rax+10h]
0x18004536b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045370  nop
0x180045371  mov     rcx, [rbp+38h]; this
0x180045375  mov     dword ptr [rsp+60h+var_38], edi; char *
0x180045379  lea     rax, aInprocessactiv_3; "InProcessActivatableClassRegistration_I"...
0x180045380  mov     [rsp+60h+var_40], rax; char *
0x180045385  lea     r9, aOsintegrationD_125; "OSIntegration::DEH::InProcessActivatabl"...
0x18004538c  lea     r8, aOnecoreAdminAp_86; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180045393  mov     edx, 234h; void *
0x180045398  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18004539d  nop
0x18004539e  mov     rcx, [rbp+var_30]
0x1800453a2  test    rcx, rcx
0x1800453a5  jz      short loc_1800453B8
0x1800453a7  mov     [rbp+var_30], r13
0x1800453ab  mov     rax, [rcx]
0x1800453ae  mov     rax, [rax+10h]
0x1800453b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800453b7  nop
0x1800453b8  mov     rcx, [rbp+var_20]
0x1800453bc  test    rcx, rcx
0x1800453bf  jz      short loc_1800453D2
0x1800453c1  mov     [rbp+var_20], r13
0x1800453c5  mov     rax, [rcx]
0x1800453c8  mov     rax, [rax+10h]
0x1800453cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800453d1  nop
0x1800453d2  mov     rcx, [rbp+var_28]
0x1800453d6  test    rcx, rcx
0x1800453d9  jz      short loc_1800453EC
0x1800453db  mov     [rbp+var_28], r13
0x1800453df  mov     rax, [rcx]
0x1800453e2  mov     rax, [rax+10h]
0x1800453e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800453eb  nop
0x1800453ec  mov     eax, edi
0x1800453ee  mov     rbx, [rsp+60h+arg_8]
0x1800453f6  add     rsp, 60h
0x1800453fa  pop     r15
0x1800453fc  pop     r14
0x1800453fe  pop     r13
0x180045400  pop     r12
0x180045402  pop     rdi
0x180045403  pop     rsi
0x180045404  pop     rbp
0x180045405  retn
0x180045406  lea     rcx, [r15+28h]
0x18004540a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004540f  mov     [r15+28h], r13
0x180045413  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004541a  mov     ecx, 0A0h; unsigned __int64
0x18004541f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180045424  test    rax, rax
0x180045427  jnz     loc_180045667
  ... truncated ...
```
