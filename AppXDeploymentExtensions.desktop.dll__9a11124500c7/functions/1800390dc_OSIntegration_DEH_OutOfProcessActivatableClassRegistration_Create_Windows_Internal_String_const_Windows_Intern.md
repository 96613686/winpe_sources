# OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create(Windows::Internal::String const &,Windows::Internal::String const &,OSIntegration::DEH::Collectors *,OSIntegration::DEH::OutOfProcessActivatableClassRegistration * *)

- ea: `0x1800390dc`
- end: `0x180039d13`
- name: `?Create@OutOfProcessActivatableClassRegistration@DEH@OSIntegration@@SAJAEBVString@Internal@Windows@@0PEAVCollectors@23@PEAPEAU123@@Z`
- size: `3127`
- prototype: `__int64 __fastcall(const struct Windows::Internal::String *, const struct Windows::Internal::String *, struct OSIntegration::DEH::Collectors *, struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration **)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007a670`

## callees

- `0x180006970`
- `0x180036e58`
- `0x1800390dc`
- `0x180039eec`
- `0x18004aaac`
- `0x18006a4c8`
- `0x180073fc4`
- `0x180074504`
- `0x18008a740`
- `0x1800ba02c`
- `0x180136174`
- `0x18013a4ac`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180039116`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180039116`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180039145`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180039145`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18003912e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18003912e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180039803`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180039803`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800399e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039a10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039b53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039b7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039bbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039be8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039c80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039caa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800399e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039a10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039b53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039b7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039bbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039be8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039c80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039caa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800397ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003981a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800397ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003981a`

## string_xrefs

- `0x1800391b1`: `_inProcessActivatableClasses->HasKey(activatableClassId, found)`
- `0x180039261`: `OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create`
- `0x18003940d`: `OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create`
- `0x1800395b3`: `OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create`
- `0x18003987f`: `OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create`
- `0x18003994c`: `OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create`
- `0x1800399c0`: `OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create`
- `0x180039a4a`: `OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create`
- `0x180039b1b`: `OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create`
- `0x180039c23`: `OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create`
- `0x180039c5a`: `OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create`
- `0x180039ce0`: `OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create`
- `0x180039255`: `collectors->GetActivationCatalogCollector()->RetrieveInProcessActivatableClassRegistration(activatableClassId, &found, &retrievedInProcClassRegistration)`
- `0x180039873`: `OutOfProcessActivatableClassRegistration_Impl::Create(activatableClassId, serverRegistration.Get(), &classRegistration)`
- `0x180039401`: `collectors->GetActivationCatalogCollector()->RetrieveOutOfProcessActivatableClassRegistration(activatableClassId, &found, &retrievedOutOfProcClassRegistration)`
- `0x1800396bc`: `OSIntegration::DEH::Internal::OutOfProcessActivatableClassRegistration_Impl::Create`
- `0x180039709`: `OSIntegration::DEH::Internal::OutOfProcessActivatableClassRegistration_Impl::Create`
- `0x180039793`: `OSIntegration::DEH::Internal::OutOfProcessActivatableClassRegistration_Impl::Create`
- `0x180039842`: `OSIntegration::DEH::Internal::OutOfProcessActivatableClassRegistration_Impl::Create`
- `0x1800396fd`: `registration->Initialize(activatableClassId)`
- `0x180039cd4`: `APPX_E_INVALID_MANIFEST`
- `0x18003935d`: `_outOfProcessActivatableClasses->HasKey(activatableClassId, found)`
- `0x180039220`: `_inProcessActivatableClasses->Lookup(activatableClassId, &registration)`
- `0x1800393cc`: `_outOfProcessActivatableClasses->Lookup(activatableClassId, &registration)`
- `0x180039787`: `static_cast<ExeServerRegistration_Impl*>(exeServer)->AddActivatableClass(activatableClassId)`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create(
        HSTRING *a1,
        HSTRING *a2,
        struct OSIntegration::DEH::Collectors *a3,
        struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration **a4)
{
  char v8; // si
  HSTRING v9; // rbx
  struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *v10; // rbx
  __int64 v11; // rdi
  char v12; // al
  __int64 v13; // rcx
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING, struct OSIntegration::DEH::ExeServerRegistration **); // rbx
  int v18; // eax
  __int64 v19; // rcx
  struct OSIntegration::DEH::ExeServerRegistration *v20; // rax
  __int64 v21; // rdi
  char v22; // al
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, HSTRING, struct OSIntegration::DEH::ExeServerRegistration **); // rbx
  int v27; // eax
  __int64 v28; // rcx
  struct OSIntegration::DEH::ExeServerRegistration *v29; // rax
  __int64 v30; // rdi
  char v31; // al
  __int64 v32; // rcx
  int v33; // eax
  int v34; // eax
  struct OSIntegration::DEH::ExeServerRegistration *v35; // rcx
  struct OSIntegration::DEH::ExeServerRegistration *v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  struct OSIntegration::DEH::ExeServerRegistration *v39; // r15
  __int64 v40; // rdi
  OSIntegration::DEH::Internal::OutOfProcessActivatableClassRegistration_Impl *v41; // rax
  HRESULT v42; // esi
  int v43; // eax
  int v44; // eax
  HSTRING *v45; // r14
  HSTRING v46; // r15
  struct OSIntegration::DEH::ExeServerRegistration *v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *v50; // rcx
  int v52; // eax
  struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *v53; // rax
  PCWSTR v54; // rax
  __int64 v55; // rdx
  Windows::Internal::String *v56; // rax
  Windows::Internal::String *v57; // rax
  PCWSTR v58; // rax
  __int64 v59; // rdx
  __int64 v60; // rdx
  PCWSTR v61; // rax
  __int64 v62; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v64; // rdx
  wil::details *v65; // [rsp+28h] [rbp-38h]
  wil::details *v66; // [rsp+28h] [rbp-38h]
  wil::details *v67; // [rsp+28h] [rbp-38h]
  wil::details *v68; // [rsp+28h] [rbp-38h]
  wil::details *v69; // [rsp+28h] [rbp-38h]
  wil::details *v70; // [rsp+28h] [rbp-38h]
  wil::details *v71; // [rsp+28h] [rbp-38h]
  wil::details *v72; // [rsp+28h] [rbp-38h]
  wil::details *v73; // [rsp+28h] [rbp-38h]
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  __int64 v75; // [rsp+38h] [rbp-28h] BYREF
  struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *v76; // [rsp+40h] [rbp-20h] BYREF
  __int64 v77; // [rsp+48h] [rbp-18h] BYREF
  struct OSIntegration::DEH::ExeServerRegistration *v78; // [rsp+50h] [rbp-10h] BYREF
  char v79[8]; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+98h] [rbp+38h]
  char v81; // [rsp+A0h] [rbp+40h] BYREF
  struct OSIntegration::DEH::ExeServerRegistration *hasEmbedNull; // [rsp+B8h] [rbp+58h] BYREF

  v8 = 0;
  LODWORD(string) = 0;
  *a4 = 0;
  v9 = *a1;
  LODWORD(hasEmbedNull) = 0;
  WindowsStringHasEmbeddedNull(v9, (BOOL *)&hasEmbedNull);
  if ( (_DWORD)hasEmbedNull || WindowsIsStringEmpty(v9) || WindowsGetStringLen(v9) > 0x100 )
  {
    v15 = -2146958844;
    LODWORD(v65) = -2146958844;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0x24B,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create",
      "((HRESULT)0x80080204L)",
      v65,
      (int)string);
    if ( (byte_180245605 & 0x20) != 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(*a1, 0);
      McTemplateU0dz_EventWriteTransfer(
        &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
        ActivatableClassIdentifierInvalid,
        2148008452LL,
        StringRawBuffer);
    }
    WindowsGetStringRawBuffer(*a1, 0);
    details::appxLog<long,unsigned short const *>(2148008452LL, v64, ActivatableClassIdentifierInvalid, 2148008452LL);
    LODWORD(v73) = -2146958844;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x24D,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create",
      "APPX_E_INVALID_MANIFEST",
      (const char *)v73,
      (int)string);
    return v15;
  }
  v10 = 0;
  v76 = 0;
  v77 = 0;
  v75 = 0;
  v81 = 0;
  v11 = *((_QWORD *)a3 + 5);
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v77);
  v12 = 0;
  v81 = 0;
  v77 = 0;
  v13 = *(_QWORD *)(v11 + 40);
  if ( v13 )
  {
    v14 = (*(__int64 (__fastcall **)(__int64, HSTRING, char *))(*(_QWORD *)v13 + 64LL))(v13, *a1, &v81);
    v15 = v14;
    if ( v14 < 0 )
    {
      LODWORD(v65) = v14;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0xA7,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
        "OSIntegration::DEH::ActivationCatalogCollector::RetrieveInProcessActivatableClassRegistration",
        "_inProcessActivatableClasses->HasKey(activatableClassId, found)",
        (const char *)v65,
        (int)string);
      goto LABEL_10;
    }
    v10 = 0;
    if ( !v81 )
      goto LABEL_15;
    hasEmbedNull = 0;
    v16 = *(_QWORD *)(v11 + 40);
    v17 = *(__int64 (__fastcall **)(__int64, HSTRING, struct OSIntegration::DEH::ExeServerRegistration **))(*(_QWORD *)v16 + 48LL);
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&hasEmbedNull);
    v18 = v17(v16, *a1, &hasEmbedNull);
    v15 = v18;
    if ( v18 < 0 )
    {
      LODWORD(v65) = v18;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0xAB,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
        "OSIntegration::DEH::ActivationCatalogCollector::RetrieveInProcessActivatableClassRegistration",
        "_inProcessActivatableClasses->Lookup(activatableClassId, &registration)",
        (const char *)v65,
        (int)string);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&hasEmbedNull);
LABEL_10:
      LODWORD(v66) = v15;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x254,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
        "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create",
        "collectors->GetActivationCatalogCollector()->RetrieveInProcessActivatableClassRegistration(activatableClassId, &"
        "found, &retrievedInProcClassRegistration)",
        (const char *)v66,
        (int)string);
      v19 = v77;
      if ( v77 )
      {
        v77 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      return v15;
    }
    v20 = hasEmbedNull;
    v10 = 0;
    hasEmbedNull = 0;
    v77 = ((unsigned __int64)v20 - 16) & -(__int64)(v20 != 0);
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&hasEmbedNull);
    v12 = v81;
  }
  if ( v12 )
    goto LABEL_74;
LABEL_15:
  v21 = *((_QWORD *)a3 + 5);
  v22 = 0;
  v81 = 0;
  v75 = 0;
  v23 = *(_QWORD *)(v21 + 48);
  if ( !v23 )
    goto LABEL_25;
  v24 = (*(__int64 (__fastcall **)(__int64, HSTRING, char *))(*(_QWORD *)v23 + 64LL))(v23, *a1, &v81);
  v15 = v24;
  if ( v24 < 0 )
  {
    LODWORD(v65) = v24;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xC3,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::ActivationCatalogCollector::RetrieveOutOfProcessActivatableClassRegistration",
      "_outOfProcessActivatableClasses->HasKey(activatableClassId, found)",
      (const char *)v65,
      (int)string);
    goto LABEL_21;
  }
  v10 = 0;
  if ( v81 )
  {
    hasEmbedNull = 0;
    v25 = *(_QWORD *)(v21 + 48);
    v26 = *(__int64 (__fastcall **)(__int64, HSTRING, struct OSIntegration::DEH::ExeServerRegistration **))(*(_QWORD *)v25 + 48LL);
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&hasEmbedNull);
    v27 = v26(v25, *a1, &hasEmbedNull);
    v15 = v27;
    if ( v27 < 0 )
    {
      LODWORD(v65) = v27;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0xC7,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
        "OSIntegration::DEH::ActivationCatalogCollector::RetrieveOutOfProcessActivatableClassRegistration",
        "_outOfProcessActivatableClasses->Lookup(activatableClassId, &registration)",
        (const char *)v65,
        (int)string);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&hasEmbedNull);
LABEL_21:
      LODWORD(v67) = v15;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x257,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
        "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create",
        "collectors->GetActivationCatalogCollector()->RetrieveOutOfProcessActivatableClassRegistration(activatableClassId"
        ", &found, &retrievedOutOfProcClassRegistration)",
        (const char *)v67,
        (int)string);
      v28 = v77;
      if ( v77 )
      {
        v77 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
      return v15;
    }
    v29 = hasEmbedNull;
    v10 = 0;
    hasEmbedNull = 0;
    v75 = ((unsigned __int64)v29 - 16) & -(__int64)(v29 != 0);
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&hasEmbedNull);
    v22 = v81;
LABEL_25:
    if ( !v22 )
      goto LABEL_26;
LABEL_74:
    if ( v77
      && (v56 = (Windows::Internal::String *)(*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v77 + 88LL))(
                                               v77,
                                               v79),
          v8 = 1,
          LODWORD(string) = 1,
          !(unsigned int)Windows::Internal::String::CompareOrdinal(v56, (const struct Windows::Internal::String *)a1))
      || v75
      && (v57 = (Windows::Internal::String *)(*(__int64 (__fastcall **)(__int64, struct OSIntegration::DEH::ExeServerRegistration **))(*(_QWORD *)v75 + 88LL))(
                                               v75,
                                               &hasEmbedNull),
          v8 |= 2u,
          !(unsigned int)Windows::Internal::String::CompareOrdinal(v57, (const struct Windows::Internal::String *)a1)) )
    {
      LOBYTE(v10) = 1;
    }
    if ( (v8 & 2) != 0 )
    {
      v8 &= ~2u;
      Windows::Internal::String::~String((Windows::Internal::String *)&hasEmbedNull);
    }
    if ( (v8 & 1) != 0 )
      Windows::Internal::String::~String((Windows::Internal::String *)v79);
    LODWORD(v65) = -2147024736;
    if ( (_BYTE)v10 )
    {
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0x263,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
        "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create",
        "HRESULT_FROM_WIN32(160L)",
        v65,
        (int)string);
      if ( (byte_180245605 & 0x20) != 0 )
      {
        v58 = WindowsGetStringRawBuffer(*a1, 0);
        McTemplateU0dz_EventWriteTransfer(
          &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
          CollidingActivatableClassIdentifiers,
          2147942560LL,
          v58);
      }
      WindowsGetStringRawBuffer(*a1, 0);
      details::appxLog<long,unsigned short const *>(
        2147942560LL,
        v59,
        CollidingActivatableClassIdentifiers,
        2147942560LL);
      v60 = 613;
    }
    else
    {
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0x26D,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
        "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create",
        "HRESULT_FROM_WIN32(160L)",
        v65,
        (int)string);
      if ( (byte_180245605 & 0x20) != 0 )
      {
        v61 = WindowsGetStringRawBuffer(*a1, 0);
        McTemplateU0dz_EventWriteTransfer(
          &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
          DuplicateActivatableClassIdentifiers,
          2147942560LL,
          v61);
      }
      WindowsGetStringRawBuffer(*a1, 0);
      details::appxLog<long,unsigned short const *>(
        2147942560LL,
        v62,
        DuplicateActivatableClassIdentifiers,
        2147942560LL);
      v60 = 623;
    }
    LODWORD(v72) = 160;
    v15 = wil::details::in1diag5::Return_Win32(
            retaddr,
            (void *)v60,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
            "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create",
            "ERROR_BAD_ARGUMENTS",
            v72,
            (unsigned int)string);
    goto LABEL_73;
  }
LABEL_26:
  v78 = 0;
  v30 = *((_QWORD *)a3 + 5);
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v78);
  v31 = 0;
  v81 = 0;
  v78 = 0;
  v32 = *(_QWORD *)(v30 + 56);
  if ( v32 )
  {
    v33 = (*(__int64 (__fastcall **)(__int64, HSTRING, char *))(*(_QWORD *)v32 + 64LL))(v32, *a2, &v81);
    v15 = v33;
    if ( v33 < 0 )
    {
      LODWORD(v65) = v33;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
        "OSIntegration::DEH::ActivationCatalogCollector::RetrieveServerRegistration",
        "_exeServers->HasKey(serverName, found)",
        (const char *)v65,
        (int)string);
LABEL_33:
      LODWORD(v68) = v15;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x274,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
        "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create",
        "collectors->GetActivationCatalogCollector()->RetrieveServerRegistration(serverName, &found, &serverRegistration)",
        (const char *)v68,
        (int)string);
      v36 = v78;
      if ( v78 )
      {
        v78 = 0;
        (*(void (__fastcall **)(struct OSIntegration::DEH::ExeServerRegistration *))(*(_QWORD *)v36 + 16LL))(v36);
      }
      v37 = v75;
      if ( v75 )
      {
        v75 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      }
      v38 = v77;
      if ( v77 )
      {
        v77 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      }
      return v15;
    }
    if ( !v81 )
      goto LABEL_69;
    hasEmbedNull = 0;
    v34 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, struct OSIntegration::DEH::ExeServerRegistration **))(**(_QWORD **)(v30 + 56) + 48LL))(
            *(_QWORD *)(v30 + 56),
            *a2,
            &hasEmbedNull);
    v15 = v34;
    if ( v34 < 0 )
    {
      LODWORD(v65) = v34;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0xE2,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
        "OSIntegration::DEH::ActivationCatalogCollector::RetrieveServerRegistration",
        "_exeServers->Lookup(serverName, &registration)",
        (const char *)v65,
        (int)string);
      v35 = hasEmbedNull;
      if ( hasEmbedNull )
      {
        hasEmbedNull = 0;
        (*(void (__fastcall **)(struct OSIntegration::DEH::ExeServerRegistration *))(*(_QWORD *)v35 + 16LL))(v35);
      }
      goto LABEL_33;
    }
    v78 = hasEmbedNull;
    v31 = v81;
    v10 = 0;
  }
  if ( !v31 )
  {
LABEL_69:
    LODWORD(v65) = -2147024883;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0x282,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create",
      "HRESULT_FROM_WIN32(13L)",
      v65,
      (int)string);
    if ( (byte_180245605 & 0x20) != 0 )
    {
      v54 = WindowsGetStringRawBuffer(*a2, 0);
      McTemplateU0dz_EventWriteTransfer(
        &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
        MissingServerName,
        2147942413LL,
        v54);
    }
    WindowsGetStringRawBuffer(*a2, 0);
    details::appxLog<long,unsigned short const *>(2147942413LL, v55, MissingServerName, 2147942413LL);
    LODWORD(v71) = 13;
    v15 = wil::details::in1diag5::Return_Win32(
            retaddr,
            (void *)0x284,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
            "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create",
            "ERROR_INVALID_DATA",
            v71,
            (unsigned int)string);
LABEL_72:
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v78);
LABEL_73:
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v75);
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v77);
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v76);
    return v15;
  }
  v39 = v78;
  v40 = 0;
  hasEmbedNull = 0;
  v41 = (OSIntegration::DEH::Internal::OutOfProcessActivatableClassRegistration_Impl *)operator new(
                                                                                         0xC0u,
                                                                                         (const struct std::nothrow_t *)&std::nothrow);
  if ( v41 )
  {
    v40 = OSIntegration::DEH::Internal::OutOfProcessActivatableClassRegistration_Impl::OutOfProcessActivatableClassRegistration_Impl(
            v41,
            v39);
    hasEmbedNull = (struct OSIntegration::DEH::ExeServerRegistration *)v40;
    v10 = (struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *)v40;
  }
  if ( v10 )
  {
    v43 = (*(__int64 (__fastcall **)(struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *, HSTRING *))(*(_QWORD *)v10 + 144LL))(
            v10,
            a1);
    v42 = v43;
    if ( v43 < 0 )
    {
      LODWORD(v65) = v43;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x198,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activatableclassregistration.cpp",
        "OSIntegration::DEH::Internal::OutOfProcessActivatableClassRegistration_Impl::Create",
        "registration->Initialize(activatableClassId)",
        (const char *)v65,
        (int)string);
      (*(void (__fastcall **)(struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *))(*(_QWORD *)v10 + 16LL))(v10);
      goto LABEL_57;
    }
    v44 = (*(__int64 (__fastcall **)(_QWORD, HSTRING))(**((_QWORD **)v39 + 31) + 104LL))(*((_QWORD *)v39 + 31), *a1);
    v42 = v44;
    if ( v44 < 0 )
    {
      LODWORD(v65) = v44;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x244,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activatableclassregistration.cpp",
        "OSIntegration::DEH::Internal::ExeServerRegistration_Impl::AddActivatableClass",
        "_classNames->Append(className.Get())",
        (const char *)v65,
        (int)string);
      LODWORD(v70) = v42;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x19D,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activatableclassregistration.cpp",
        "OSIntegration::DEH::Internal::OutOfProcessActivatableClassRegistration_Impl::Create",
        "static_cast<ExeServerRegistration_Impl*>(exeServer)->AddActivatableClass(activatableClassId)",
        (const char *)v70,
        (int)string);
      (*(void (__fastcall **)(struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *))(*(_QWORD *)v10 + 16LL))(v10);
      goto LABEL_57;
    }
    v45 = (HSTRING *)(v40 + 64);
    v46 = *(HSTRING *)(*(__int64 (__fastcall **)(struct OSIntegration::DEH::ExeServerRegistration *, HSTRING *))(*(_QWORD *)v39 + 112LL))(
                        v39,
                        &string);
    if ( !v46 || (v42 = 0, v46 != *v45) )
    {
      WindowsDeleteString(*v45);
      *v45 = 0;
      v42 = WindowsDuplicateString(v46, (HSTRING *)(v40 + 64));
    }
    if ( string )
      WindowsDeleteString(string);
    if ( v42 < 0 )
    {
      LODWORD(v65) = v42;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x1A0,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activatableclassregistration.cpp",
        "OSIntegration::DEH::Internal::OutOfProcessActivatableClassRegistration_Impl::Create",
        "registration->_properties.Server.Value.Set(exeServer->get_ServerName().Get())",
        (const char *)v65,
        (int)string);
      (*(void (__fastcall **)(struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *))(*(_QWORD *)v10 + 16LL))(v10);
      goto LABEL_57;
    }
    *(_BYTE *)(v40 + 56) = 1;
    *(_DWORD *)(v40 + 48) = 1;
    v76 = v10;
    v52 = OSIntegration::DEH::ActivationCatalogCollector::AddOutOfProcessActivatableClassRegistration(
            *((OSIntegration::DEH::ActivationCatalogCollector **)a3 + 5),
            v10);
    v15 = v52;
    if ( v52 >= 0 )
    {
      v53 = v76;
      v76 = 0;
      *a4 = v53;
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v78);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v75);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v77);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v76);
      return 0;
    }
    LODWORD(v65) = v52;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x27A,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create",
      "collectors->GetActivationCatalogCollector()->AddOutOfProcessActivatableClassRegistration(classRegistration.Get())",
      (const char *)v65,
      (int)string);
    goto LABEL_72;
  }
  v42 = -2147024882;
  LODWORD(v65) = -2147024882;
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)0x196,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activatableclassregistration.cpp",
    "OSIntegration::DEH::Internal::OutOfProcessActivatableClassRegistration_Impl::Create",
    "registration",
    (const char *)v65,
    (int)string);
LABEL_57:
  LODWORD(v69) = v42;
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)0x278,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
    "OSIntegration::DEH::OutOfProcessActivatableClassRegistration::Create",
    "OutOfProcessActivatableClassRegistration_Impl::Create(activatableClassId, serverRegistration.Get(), &classRegistration)",
    (const char *)v69,
    (int)string);
  v47 = v78;
  if ( v78 )
  {
    v78 = 0;
    (*(void (__fastcall **)(struct OSIntegration::DEH::ExeServerRegistration *))(*(_QWORD *)v47 + 16LL))(v47);
  }
  v48 = v75;
  if ( v75 )
  {
    v75 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  }
  v49 = v77;
  if ( v77 )
  {
    v77 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  }
  v50 = v76;
  if ( v76 )
  {
    v76 = 0;
    (*(void (__fastcall **)(struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *))(*(_QWORD *)v50 + 16LL))(v50);
  }
  return (unsigned int)v42;
}

```

## disassembly

```asm
0x1800390dc  mov     [rsp-38h+arg_8], rbx
0x1800390e1  push    rbp
0x1800390e2  push    rsi
0x1800390e3  push    rdi
0x1800390e4  push    r12
0x1800390e6  push    r13
0x1800390e8  push    r14
0x1800390ea  push    r15
0x1800390ec  mov     rbp, rsp
0x1800390ef  sub     rsp, 60h
0x1800390f3  mov     r12, r9
0x1800390f6  mov     r13, r8
0x1800390f9  mov     r15, rdx
0x1800390fc  mov     r14, rcx
0x1800390ff  xor     edi, edi
0x180039101  mov     esi, edi
0x180039103  mov     dword ptr [rbp+string], edi
0x180039106  mov     [r9], rdi
0x180039109  mov     rbx, [rcx]
0x18003910c  mov     dword ptr [rbp+hasEmbedNull], edi
0x18003910f  lea     rdx, [rbp+hasEmbedNull]; hasEmbedNull
0x180039113  mov     rcx, rbx; string
0x180039116  call    cs:__imp_WindowsStringHasEmbeddedNull
0x18003911d  nop     dword ptr [rax+rax+00h]
0x180039122  cmp     dword ptr [rbp+hasEmbedNull], edi
0x180039125  jnz     loc_180039C41
0x18003912b  mov     rcx, rbx; string
0x18003912e  call    cs:__imp_WindowsIsStringEmpty
0x180039135  nop     dword ptr [rax+rax+00h]
0x18003913a  test    eax, eax
0x18003913c  jnz     loc_180039C41
0x180039142  mov     rcx, rbx; string
0x180039145  call    cs:__imp_WindowsGetStringLen
0x18003914c  nop     dword ptr [rax+rax+00h]
0x180039151  cmp     eax, 100h
0x180039156  ja      loc_180039C41
0x18003915c  xor     ebx, ebx
0x18003915e  mov     [rbp+var_20], rbx
0x180039162  mov     [rbp+var_18], rbx
0x180039166  mov     [rbp+var_28], rbx
0x18003916a  mov     [rbp+arg_0], bl
0x18003916d  mov     rdi, [r13+28h]
0x180039171  lea     rcx, [rbp+var_18]
0x180039175  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x18003917a  mov     al, bl
0x18003917c  mov     [rbp+arg_0], bl
0x18003917f  mov     [rbp+var_18], rbx
0x180039183  mov     rcx, [rdi+28h]
0x180039187  test    rcx, rcx
0x18003918a  jz      loc_180039300
0x180039190  mov     rax, [rcx]
0x180039193  lea     r8, [rbp+arg_0]
0x180039197  mov     rdx, [r14]
0x18003919a  mov     rax, [rax+40h]
0x18003919e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391a3  mov     ebx, eax
0x1800391a5  test    eax, eax
0x1800391a7  jns     short loc_1800391D7
0x1800391a9  mov     rcx, [rbp+38h]; this
0x1800391ad  mov     dword ptr [rsp+60h+var_38], eax; char *
0x1800391b1  lea     rax, aInprocessactiv_0; "_inProcessActivatableClasses->HasKey(ac"...
0x1800391b8  mov     [rsp+60h+var_40], rax; char *
0x1800391bd  lea     r9, aOsintegrationD_3; "OSIntegration::DEH::ActivationCatalogCo"...
0x1800391c4  lea     r8, aOnecoreAdminAp_86; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800391cb  mov     edx, 0A7h; void *
0x1800391d0  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800391d5  jmp     short loc_18003924D
0x1800391d7  mov     al, [rbp+arg_0]
0x1800391da  xor     ebx, ebx
0x1800391dc  test    al, al
0x1800391de  jz      loc_180039308
0x1800391e4  mov     [rbp+hasEmbedNull], rbx
0x1800391e8  mov     rdi, [rdi+28h]
0x1800391ec  mov     rax, [rdi]
0x1800391ef  mov     rbx, [rax+30h]
0x1800391f3  lea     rcx, [rbp+hasEmbedNull]
0x1800391f7  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800391fc  lea     r8, [rbp+hasEmbedNull]
0x180039200  mov     rdx, [r14]
0x180039203  mov     rcx, rdi
0x180039206  mov     rax, rbx
0x180039209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003920e  mov     ebx, eax
0x180039210  test    eax, eax
0x180039212  jns     loc_1800392D9
0x180039218  mov     rcx, [rbp+38h]; this
0x18003921c  mov     dword ptr [rsp+60h+var_38], eax; char *
0x180039220  lea     rax, aInprocessactiv; "_inProcessActivatableClasses->Lookup(ac"...
0x180039227  mov     [rsp+60h+var_40], rax; char *
0x18003922c  lea     r9, aOsintegrationD_3; "OSIntegration::DEH::ActivationCatalogCo"...
0x180039233  lea     r8, aOnecoreAdminAp_86; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003923a  mov     edx, 0ABh; void *
0x18003923f  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180039244  lea     rcx, [rbp+hasEmbedNull]
0x180039248  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x18003924d  mov     rcx, [rbp+38h]; this
0x180039251  mov     dword ptr [rsp+60h+var_38], ebx; char *
0x180039255  lea     rax, aCollectorsGeta_5; "collectors->GetActivationCatalogCollect"...
0x18003925c  mov     [rsp+60h+var_40], rax; char *
0x180039261  lea     r9, aOsintegrationD_160; "OSIntegration::DEH::OutOfProcessActivat"...
0x180039268  lea     r8, aOnecoreAdminAp_86; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003926f  mov     edx, 254h; void *
0x180039274  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180039279  nop
0x18003927a  mov     rcx, [rbp+var_28]
0x18003927e  test    rcx, rcx
0x180039281  jz      short loc_180039298
0x180039283  mov     [rbp+var_28], 0
0x18003928b  mov     rax, [rcx]
0x18003928e  mov     rax, [rax+10h]
0x180039292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039297  nop
0x180039298  mov     rcx, [rbp+var_18]
0x18003929c  test    rcx, rcx
0x18003929f  jz      short loc_1800392B6
0x1800392a1  mov     [rbp+var_18], 0
0x1800392a9  mov     rax, [rcx]
0x1800392ac  mov     rax, [rax+10h]
0x1800392b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392b5  nop
0x1800392b6  mov     rcx, [rbp+var_20]
0x1800392ba  test    rcx, rcx
0x1800392bd  jz      short loc_1800392D4
0x1800392bf  mov     [rbp+var_20], 0
0x1800392c7  mov     rdx, [rcx]
0x1800392ca  mov     rax, [rdx+10h]
0x1800392ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392d3  nop
0x1800392d4  jmp     loc_180039CF8
0x1800392d9  mov     rax, [rbp+hasEmbedNull]
0x1800392dd  xor     ebx, ebx
0x1800392df  mov     [rbp+hasEmbedNull], rbx
0x1800392e3  lea     rcx, [rax-10h]
0x1800392e7  neg     rax
0x1800392ea  sbb     rax, rax
0x1800392ed  and     rax, rcx
0x1800392f0  mov     [rbp+var_18], rax
0x1800392f4  lea     rcx, [rbp+hasEmbedNull]
0x1800392f8  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800392fd  mov     al, [rbp+arg_0]
0x180039300  test    al, al
0x180039302  jnz     loc_180039A90
0x180039308  mov     rdi, [r13+28h]
0x18003930c  mov     rcx, [rbp+var_28]
0x180039310  test    rcx, rcx
0x180039313  jz      short loc_180039326
0x180039315  mov     [rbp+var_28], rbx
0x180039319  mov     rax, [rcx]
0x18003931c  mov     rax, [rax+10h]
0x180039320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039325  nop
0x180039326  mov     al, bl
0x180039328  mov     [rbp+arg_0], bl
0x18003932b  mov     [rbp+var_28], rbx
0x18003932f  mov     rcx, [rdi+30h]
0x180039333  test    rcx, rcx
0x180039336  jz      loc_1800394AC
0x18003933c  mov     rax, [rcx]
0x18003933f  lea     r8, [rbp+arg_0]
0x180039343  mov     rdx, [r14]
0x180039346  mov     rax, [rax+40h]
0x18003934a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003934f  mov     ebx, eax
0x180039351  test    eax, eax
0x180039353  jns     short loc_180039383
0x180039355  mov     rcx, [rbp+38h]; this
0x180039359  mov     dword ptr [rsp+60h+var_38], eax; char *
0x18003935d  lea     rax, aOutofprocessac_3; "_outOfProcessActivatableClasses->HasKey"...
0x180039364  mov     [rsp+60h+var_40], rax; char *
0x180039369  lea     r9, aOsintegrationD_292; "OSIntegration::DEH::ActivationCatalogCo"...
0x180039370  lea     r8, aOnecoreAdminAp_86; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180039377  mov     edx, 0C3h; void *
0x18003937c  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180039381  jmp     short loc_1800393F9
0x180039383  mov     al, [rbp+arg_0]
0x180039386  xor     ebx, ebx
0x180039388  test    al, al
0x18003938a  jz      loc_1800394B4
0x180039390  mov     [rbp+hasEmbedNull], rbx
0x180039394  mov     rdi, [rdi+30h]
0x180039398  mov     rax, [rdi]
0x18003939b  mov     rbx, [rax+30h]
0x18003939f  lea     rcx, [rbp+hasEmbedNull]
0x1800393a3  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800393a8  lea     r8, [rbp+hasEmbedNull]
0x1800393ac  mov     rdx, [r14]
0x1800393af  mov     rcx, rdi
0x1800393b2  mov     rax, rbx
0x1800393b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393ba  mov     ebx, eax
0x1800393bc  test    eax, eax
0x1800393be  jns     loc_180039485
0x1800393c4  mov     rcx, [rbp+38h]; this
0x1800393c8  mov     dword ptr [rsp+60h+var_38], eax; char *
0x1800393cc  lea     rax, aOutofprocessac; "_outOfProcessActivatableClasses->Lookup"...
0x1800393d3  mov     [rsp+60h+var_40], rax; char *
0x1800393d8  lea     r9, aOsintegrationD_292; "OSIntegration::DEH::ActivationCatalogCo"...
0x1800393df  lea     r8, aOnecoreAdminAp_86; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800393e6  mov     edx, 0C7h; void *
0x1800393eb  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800393f0  lea     rcx, [rbp+hasEmbedNull]
0x1800393f4  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800393f9  mov     rcx, [rbp+38h]; this
0x1800393fd  mov     dword ptr [rsp+60h+var_38], ebx; char *
0x180039401  lea     rax, aCollectorsGeta_4; "collectors->GetActivationCatalogCollect"...
0x180039408  mov     [rsp+60h+var_40], rax; char *
0x18003940d  lea     r9, aOsintegrationD_160; "OSIntegration::DEH::OutOfProcessActivat"...
0x180039414  lea     r8, aOnecoreAdminAp_86; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003941b  mov     edx, 257h; void *
0x180039420  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180039425  nop
0x180039426  mov     rcx, [rbp+var_28]
0x18003942a  test    rcx, rcx
0x18003942d  jz      short loc_180039444
0x18003942f  mov     [rbp+var_28], 0
0x180039437  mov     rax, [rcx]
0x18003943a  mov     rax, [rax+10h]
0x18003943e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039443  nop
0x180039444  mov     rcx, [rbp+var_18]
0x180039448  test    rcx, rcx
0x18003944b  jz      short loc_180039462
0x18003944d  mov     [rbp+var_18], 0
0x180039455  mov     rax, [rcx]
0x180039458  mov     rax, [rax+10h]
0x18003945c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039461  nop
0x180039462  mov     rcx, [rbp+var_20]
0x180039466  test    rcx, rcx
0x180039469  jz      short loc_180039480
0x18003946b  mov     [rbp+var_20], 0
0x180039473  mov     rdx, [rcx]
0x180039476  mov     rax, [rdx+10h]
0x18003947a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003947f  nop
0x180039480  jmp     loc_180039CF8
0x180039485  mov     rax, [rbp+hasEmbedNull]
0x180039489  xor     ebx, ebx
0x18003948b  mov     [rbp+hasEmbedNull], rbx
0x18003948f  lea     rcx, [rax-10h]
0x180039493  neg     rax
0x180039496  sbb     rax, rax
0x180039499  and     rax, rcx
0x18003949c  mov     [rbp+var_28], rax
0x1800394a0  lea     rcx, [rbp+hasEmbedNull]
0x1800394a4  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800394a9  mov     al, [rbp+arg_0]
0x1800394ac  test    al, al
0x1800394ae  jnz     loc_180039A90
0x1800394b4  mov     [rbp+var_10], rbx
0x1800394b8  mov     rdi, [r13+28h]
0x1800394bc  lea     rcx, [rbp+var_10]
0x1800394c0  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800394c5  mov     al, bl
0x1800394c7  mov     [rbp+arg_0], bl
0x1800394ca  mov     [rbp+var_10], rbx
0x1800394ce  mov     rcx, [rdi+38h]
0x1800394d2  test    rcx, rcx
0x1800394d5  jz      loc_180039646
0x1800394db  mov     rax, [rcx]
0x1800394de  lea     r8, [rbp+arg_0]
0x1800394e2  mov     rdx, [r15]
0x1800394e5  mov     rax, [rax+40h]
0x1800394e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800394ee  mov     ebx, eax
0x1800394f0  test    eax, eax
0x1800394f2  jns     short loc_180039524
0x1800394f4  mov     rcx, [rbp+38h]; this
0x1800394f8  mov     dword ptr [rsp+60h+var_38], eax; char *
0x1800394fc  lea     rax, aExeserversHask; "_exeServers->HasKey(serverName, found)"
0x180039503  mov     [rsp+60h+var_40], rax; char *
0x180039508  lea     r9, aOsintegrationD_138; "OSIntegration::DEH::ActivationCatalogCo"...
0x18003950f  lea     r8, aOnecoreAdminAp_86; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180039516  mov     edx, 0DEh; void *
0x18003951b  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180039520  xor     edi, edi
0x180039522  jmp     short loc_18003959F
0x180039524  mov     al, [rbp+arg_0]
0x180039527  xor     ebx, ebx
0x180039529  test    al, al
0x18003952b  jz      loc_1800399A7
0x180039531  mov     [rbp+hasEmbedNull], rbx
0x180039535  mov     rcx, [rdi+38h]
0x180039539  mov     rax, [rcx]
0x18003953c  lea     r8, [rbp+hasEmbedNull]
0x180039540  mov     rdx, [r15]
0x180039543  mov     rax, [rax+30h]
0x180039547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003954c  mov     ebx, eax
0x18003954e  xor     edi, edi
0x180039550  test    eax, eax
0x180039552  jns     loc_180039639
0x180039558  mov     rcx, [rbp+38h]; this
0x18003955c  mov     dword ptr [rsp+60h+var_38], eax; char *
0x180039560  lea     rax, aExeserversLook; "_exeServers->Lookup(serverName, &regist"...
0x180039567  mov     [rsp+60h+var_40], rax; char *
0x18003956c  lea     r9, aOsintegrationD_138; "OSIntegration::DEH::ActivationCatalogCo"...
0x180039573  lea     r8, aOnecoreAdminAp_86; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003957a  mov     edx, 0E2h; void *
0x18003957f  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
  ... truncated ...
```
