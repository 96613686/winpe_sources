# OSIntegration::DEH::ExtensionCatalogCollector::CreateExtensionRegistration(Windows::Internal::String const &,Windows::Internal::String const &,OSIntegration::DEH::ExtensionRegistration * *)

- ea: `0x1800263cc`
- end: `0x180026fe2`
- name: `?CreateExtensionRegistration@ExtensionCatalogCollector@DEH@OSIntegration@@QEAAJAEBVString@Internal@Windows@@0PEAPEAUExtensionRegistration@23@@Z`
- size: `3094`
- prototype: `__int64 __fastcall(OSIntegration::DEH::ExtensionCatalogCollector *__hidden this, const struct Windows::Internal::String *, const struct Windows::Internal::String *, struct OSIntegration::DEH::ExtensionRegistration **)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180026354`

## callees

- `0x180006970`
- `0x180024444`
- `0x180025b1c`
- `0x1800261ec`
- `0x1800263cc`
- `0x180026fe8`
- `0x18002703c`
- `0x18002774c`
- `0x18006a4c8`
- `0x180073fc4`
- `0x180074000`
- `0x180074248`
- `0x180074504`
- `0x18008a740`
- `0x1800aed10`
- `0x1800ba02c`
- `0x1800d7ad0`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026e16`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026e16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180026412`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180026608`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180026412`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180026608`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180026439`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180026637`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180026653`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18002666a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180026439`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180026637`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180026653`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18002666a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180026426`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180026620`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180026426`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180026620`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002670c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180026763`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002670c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180026763`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026495`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800264bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026ef1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026f1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026f8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026fb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026495`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800264bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026ef1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026f1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026f8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026fb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800266c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800266c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002659d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800265b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800266f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002674c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026b40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026b54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026c7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026c8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026dc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026dd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002659d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800265b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800266f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002674c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026b40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026b54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026c7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026c8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026dc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026dd6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180026a2f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180026a2f`
- `KERNEL32!InitializeSRWLock` at `0x18002698c`
- `KERNEL32!InitializeSRWLock` at `0x18002698c`
- `OLE32!CoGetApartmentType` at `0x180026951`
- `OLE32!CoGetApartmentType` at `0x180026951`

## string_xrefs

- `0x180026469`: `OSIntegration::DEH::ExtensionCatalogCollector::CreateExtensionRegistration`
- `0x180026722`: `OSIntegration::DEH::ExtensionCatalogCollector::CreateExtensionRegistration`
- `0x180026ec5`: `OSIntegration::DEH::ExtensionCatalogCollector::CreateExtensionRegistration`
- `0x180026f60`: `OSIntegration::DEH::ExtensionCatalogCollector::CreateExtensionRegistration`
- `0x180026473`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\extensioncatalogcollector.cpp`
- `0x180026729`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\extensioncatalogcollector.cpp`
- `0x180026ecf`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\extensioncatalogcollector.cpp`
- `0x180026f6a`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\extensioncatalogcollector.cpp`
- `0x1800264ea`: `APPX_E_INVALID_MANIFEST`
- `0x180026e2b`: `contractIdCopy.Set(contractId.Get())`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall OSIntegration::DEH::ExtensionCatalogCollector::CreateExtensionRegistration(
        OSIntegration::DEH::ExtensionCatalogCollector *this,
        HSTRING *a2,
        HSTRING *a3,
        struct OSIntegration::DEH::ExtensionRegistration **a4)
{
  unsigned int v8; // ebx
  PCWSTR StringRawBuffer; // rax
  PCWSTR v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  RTL_SRWLOCK *v16; // rcx
  _QWORD *v17; // rcx
  __int64 v18; // rcx
  HSTRING v20; // rbx
  HSTRING v21; // r13
  __int64 v22; // rcx
  HSTRING v23; // rbx
  HRESULT v24; // eax
  int v25; // r14d
  HSTRING v26; // rbx
  _QWORD *v27; // rax
  _QWORD *v28; // rbx
  bool v29; // dl
  RTL_SRWLOCK *v30; // rax
  RTL_SRWLOCK *v31; // rbx
  int v32; // eax
  _DWORD *v33; // rax
  int v34; // r14d
  HSTRING v35; // rbx
  __int64 v36; // rcx
  __int64 v37; // rbx
  void *v38; // rax
  struct OSIntegration::DEH::ExtensionRegistration *v39; // r14
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  RTL_SRWLOCK *v44; // rcx
  _QWORD *v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  RTL_SRWLOCK *v49; // rcx
  _QWORD *v50; // rcx
  __int64 v51; // rcx
  PCWSTR v52; // rax
  PCWSTR v53; // rax
  __int64 v54; // rdx
  PCWSTR v55; // rax
  PCWSTR v56; // rax
  __int64 v57; // rdx
  wil::details *v58; // [rsp+28h] [rbp-81h]
  wil::details *v59; // [rsp+28h] [rbp-81h]
  wil::details *v60; // [rsp+28h] [rbp-81h]
  wil::details *v61; // [rsp+28h] [rbp-81h]
  wil::details *v62; // [rsp+28h] [rbp-81h]
  wil::details *v63; // [rsp+28h] [rbp-81h]
  int v64; // [rsp+30h] [rbp-79h] BYREF
  BOOL hasEmbedNull[2]; // [rsp+38h] [rbp-71h] BYREF
  HSTRING string; // [rsp+40h] [rbp-69h] BYREF
  APTTYPEQUALIFIER pAptQualifier; // [rsp+48h] [rbp-61h] BYREF
  __int64 v68; // [rsp+50h] [rbp-59h] BYREF
  RTL_SRWLOCK *v69; // [rsp+58h] [rbp-51h] BYREF
  _QWORD *v70; // [rsp+60h] [rbp-49h] BYREF
  __int64 v71; // [rsp+68h] [rbp-41h] BYREF
  HSTRING newString[2]; // [rsp+70h] [rbp-39h] BYREF
  _QWORD v73[2]; // [rsp+80h] [rbp-29h] BYREF
  HSTRING v74; // [rsp+90h] [rbp-19h]
  HSTRING v75; // [rsp+98h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-9h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+108h] [rbp+5Fh]

  v73[0] = this;
  *a4 = 0;
  hasEmbedNull[0] = 0;
  WindowsStringHasEmbeddedNull(*a2, hasEmbedNull);
  if ( hasEmbedNull[0] || WindowsIsStringEmpty(*a2) || WindowsGetStringLen(*a2) > 0x7FFF )
  {
    v8 = -2146958844;
    LODWORD(v58) = -2146958844;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0x1CF,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
      "OSIntegration::DEH::ExtensionCatalogCollector::CreateExtensionRegistration",
      "((HRESULT)0x80080204L)",
      v58,
      v64);
    if ( (byte_180245605 & 0x20) != 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(*a2, 0);
      McTemplateU0dz_EventWriteTransfer(
        &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
        ContractIdentifierInvalidLength,
        2148008452LL,
        StringRawBuffer);
    }
    v10 = WindowsGetStringRawBuffer(*a2, 0);
    details::appxLog<long,unsigned short const *>(
      -2146958844,
      v11,
      (const struct _EVENT_DESCRIPTOR *)ContractIdentifierInvalidLength,
      -2146958844,
      v10);
    v12 = 465;
LABEL_7:
    LODWORD(v59) = -2146958844;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
      "OSIntegration::DEH::ExtensionCatalogCollector::CreateExtensionRegistration",
      "APPX_E_INVALID_MANIFEST",
      (const char *)v59,
      v64);
    return v8;
  }
  v20 = *a3;
  hasEmbedNull[0] = 0;
  WindowsStringHasEmbeddedNull(v20, hasEmbedNull);
  if ( hasEmbedNull[0] || WindowsIsStringEmpty(v20) || WindowsGetStringLen(v20) > 0x100 )
  {
    v8 = -2146958844;
    LODWORD(v58) = -2146958844;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0x1DA,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
      "OSIntegration::DEH::ExtensionCatalogCollector::CreateExtensionRegistration",
      "((HRESULT)0x80080204L)",
      v58,
      v64);
    if ( (byte_180245605 & 0x20) != 0 )
    {
      v55 = WindowsGetStringRawBuffer(*a3, 0);
      McTemplateU0dz_EventWriteTransfer(
        &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
        ActivatableClassIdentifierInvalid,
        2148008452LL,
        v55);
    }
    v56 = WindowsGetStringRawBuffer(*a3, 0);
    details::appxLog<long,unsigned short const *>(
      -2146958844,
      v57,
      (const struct _EVENT_DESCRIPTOR *)ActivatableClassIdentifierInvalid,
      -2146958844,
      v56);
    v12 = 476;
    goto LABEL_7;
  }
  if ( WindowsGetStringLen(*a2) > 0x100 || WindowsGetStringLen(*a3) > 0x100 )
  {
    v8 = -2146958844;
    LODWORD(v58) = -2146958844;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0x1E6,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
      "OSIntegration::DEH::ExtensionCatalogCollector::CreateExtensionRegistration",
      "((HRESULT)0x80080204L)",
      v58,
      v64);
    if ( (byte_180245605 & 0x20) != 0 )
    {
      v52 = WindowsGetStringRawBuffer(*a3, 0);
      McTemplateU0dz_EventWriteTransfer(
        &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
        ActivatableClassIdentifierInvalidLength,
        2148008452LL,
        v52);
    }
    v53 = WindowsGetStringRawBuffer(*a3, 0);
    details::appxLog<long,unsigned short const *>(
      -2146958844,
      v54,
      (const struct _EVENT_DESCRIPTOR *)ActivatableClassIdentifierInvalidLength,
      -2146958844,
      v53);
    v12 = 488;
    goto LABEL_7;
  }
  v21 = *a2;
  v74 = *a3;
  v71 = 0;
  v22 = *((_QWORD *)this + 4);
  newString[0] = v21;
  newString[1] = v74;
  if ( (*(int (__fastcall **)(__int64, HSTRING *, __int64 *))(*(_QWORD *)v22 + 48LL))(v22, newString, &v71) >= 0 )
    goto LABEL_16;
  if ( WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &v75) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  newString[0] = 0;
  string = 0;
  v70 = 0;
  v69 = 0;
  v68 = 0;
  v23 = *a2;
  WindowsDeleteString(0);
  newString[0] = 0;
  v24 = WindowsDuplicateString(v23, newString);
  v25 = -2147024882;
  if ( v24 < 0 )
  {
    LODWORD(v58) = v24;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0x204,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
      "OSIntegration::DEH::ExtensionCatalogCollector::CreateExtensionRegistration",
      "contractIdCopy.Set(contractId.Get())",
      v58,
      v64);
    goto LABEL_63;
  }
  v26 = *a3;
  if ( !*a3 || v26 != string )
  {
    WindowsDeleteString(string);
    string = 0;
    if ( WindowsDuplicateString(v26, &string) < 0 )
      goto LABEL_63;
  }
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v70);
  v70 = 0;
  v27 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  v28 = v27;
  if ( !v27 )
    goto LABEL_32;
  Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>>::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>>(v27);
  *v28 = &Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::`vftable';
  v28[1] = &Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::`vftable'{for `IWeakReferenceSource'};
  v28[2] = &Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>>'};
  v28[5] = v28;
  v28[6] = 0;
  v28[7] = 0;
  *((_DWORD *)v28 + 16) = 17;
  v28[10] = 0xFFFFFFFFLL;
  v28[11] = 0;
  *((_DWORD *)v28 + 24) = 0;
  *((_DWORD *)v28 + 25) = 10;
  v28[13] = 0;
  v28[14] = 0;
  *((_DWORD *)v28 + 17) = 1061158912;
  *((_DWORD *)v28 + 18) = 1048576000;
  *((_DWORD *)v28 + 19) = 1074790400;
  XWinRT::XHashMap<HSTRING__ *,OSIntegration::DEH::IComTypeLibRegistration *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,OSIntegration::DEH::ComTypeLibRegistration *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<OSIntegration::DEH::ComTypeLibRegistration *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,OSIntegration::DEH::ComTypeLibRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<OSIntegration::DEH::IComTypeLibRegistration *>>::UpdateRehashThresholds();
  XWinRT::ComLock::ComLock((XWinRT::ComLock *)(v28 + 16), v29);
  v28[18] = 0;
  *((_BYTE *)v28 + 152) = 0;
  *((_DWORD *)v28 + 39) = 0;
  v25 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Initialize(v28);
  if ( v25 >= 0 )
  {
    v70 = v28;
LABEL_32:
    v28 = 0;
  }
  if ( v28 )
    (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
  if ( v25 < 0 )
    goto LABEL_63;
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v69);
  v69 = 0;
  v30 = (RTL_SRWLOCK *)operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  v31 = v30;
  if ( !v30 )
  {
    v34 = -2147024882;
    goto LABEL_47;
  }
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::ComTreatAsClassRegistration *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<_GUID,OSIntegration::DEH::ComTreatAsClassRegistration *> *>>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::ComTreatAsClassRegistration *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<_GUID,OSIntegration::DEH::ComTreatAsClassRegistration *> *>>(v30);
  v31->Ptr = &Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::`vftable';
  v31[1].Ptr = &Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::`vftable'{for `IWeakReferenceSource'};
  v31[2].Ptr = &Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  v31->Ptr = &Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::`vftable';
  v31[1].Ptr = &Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::`vftable'{for `IWeakReferenceSource'};
  v31[2].Ptr = &Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>'};
  v31[5].Ptr = v31;
  v31[6].Ptr = 0;
  v31[7].Ptr = 0;
  LODWORD(v31[8].Ptr) = 17;
  v31[10].Ptr = (PVOID)0xFFFFFFFFLL;
  v31[11].Ptr = 0;
  LODWORD(v31[12].Ptr) = 0;
  HIDWORD(v31[12].Ptr) = 10;
  v31[13].Ptr = 0;
  v31[14].Ptr = 0;
  HIDWORD(v31[8].Ptr) = 1061158912;
  LODWORD(v31[9].Ptr) = 1048576000;
  HIDWORD(v31[9].Ptr) = 1074790400;
  XWinRT::XHashMap<HSTRING__ *,OSIntegration::DEH::IComTypeLibRegistration *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,OSIntegration::DEH::ComTypeLibRegistration *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<OSIntegration::DEH::ComTypeLibRegistration *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,OSIntegration::DEH::ComTypeLibRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<OSIntegration::DEH::IComTypeLibRegistration *>>::UpdateRehashThresholds();
  hasEmbedNull[0] = 0;
  pAptQualifier = APTTYPEQUALIFIER_NONE;
  if ( CoGetApartmentType((APTTYPE *)hasEmbedNull, &pAptQualifier) >= 0 )
  {
    v32 = hasEmbedNull[0];
  }
  else
  {
    v32 = 1;
    hasEmbedNull[0] = 1;
  }
  if ( v32 == 3 || !v32 )
  {
    LODWORD(v31[16].Ptr) = 1;
    LODWORD(v31[17].Ptr) = 0;
  }
  else
  {
    LODWORD(v31[16].Ptr) = 0;
    InitializeSRWLock(v31 + 17);
  }
  v31[18].Ptr = 0;
  LOBYTE(v31[19].Ptr) = 0;
  HIDWORD(v31[19].Ptr) = 0;
  v33 = operator new(4u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v33 )
  {
    *v33 = 1;
    v31[18].Ptr = v33;
    LOBYTE(v31[19].Ptr) = 1;
    v69 = v31;
    v34 = 0;
LABEL_47:
    v31 = 0;
    goto LABEL_48;
  }
  v31[18].Ptr = 0;
  v34 = -2147024882;
LABEL_48:
  if ( v31 )
    (*((void (__fastcall **)(RTL_SRWLOCK *))v31->Ptr + 2))(v31);
  if ( v34 >= 0 )
  {
    v35 = v75;
    v36 = v68;
    if ( v68 )
    {
      v68 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
    if ( (int)RoGetActivationFactory(v35, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v68) >= 0 )
    {
      v37 = 0;
      *(_QWORD *)hasEmbedNull = 0;
      v38 = operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v38 )
      {
        v37 = OSIntegration::DEH::Internal::CExtensionRegistration::CExtensionRegistration(
                (_DWORD)v38,
                (unsigned int)newString,
                (unsigned int)&string,
                (unsigned int)&v70,
                (__int64)&v69,
                (__int64)&v68);
        *(_QWORD *)hasEmbedNull = v37;
        v39 = (struct OSIntegration::DEH::ExtensionRegistration *)v37;
      }
      else
      {
        v39 = 0;
      }
      if ( !v39 )
      {
        v8 = -2147024882;
        LODWORD(v58) = -2147024882;
        wil::details::in1diag5::_Log_Hr(
          retaddr,
          (void *)0x227,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
          "OSIntegration::DEH::ExtensionCatalogCollector::CreateExtensionRegistration",
          "((HRESULT)0x8007000EL)",
          v58,
          v64);
        if ( (byte_180245605 & 0x20) != 0 )
          McTemplateU0d_EventWriteTransfer(v41, &CollectorIsOutOfMemory, 2147942414LL);
        details::appxLog<long>(-2147024882, v40, &CollectorIsOutOfMemory, -2147024882);
        LODWORD(v60) = -2147024882;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x228,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
          "OSIntegration::DEH::ExtensionCatalogCollector::CreateExtensionRegistration",
          "E_OUTOFMEMORY",
          (const char *)v60,
          v64);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(hasEmbedNull);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v68);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v69);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v70);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(newString[0]);
        newString[0] = 0;
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v71);
        return v8;
      }
      LOBYTE(v64) = 0;
      v13 = *(_QWORD *)(v73[0] + 32LL);
      v73[0] = v21;
      v73[1] = v74;
      v14 = (*(__int64 (__fastcall **)(__int64, _QWORD *, __int64, int *))(*(_QWORD *)v13 + 80LL))(v13, v73, v37, &v64);
      v8 = v14;
      if ( v14 < 0 )
      {
        LODWORD(v58) = v14;
        wil::details::in1diag5::_Log_Hr(
          retaddr,
          (void *)0x214,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
          "OSIntegration::DEH::ExtensionCatalogCollector::CreateExtensionRegistration",
          "hrInsert",
          v58,
          v64);
        LODWORD(v62) = -2147024882;
        wil::details::in1diag5::_Log_Hr(
          retaddr,
          (void *)0x21E,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
          "OSIntegration::DEH::ExtensionCatalogCollector::CreateExtensionRegistration",
          "((HRESULT)0x8007000EL)",
          v62,
          v64);
        if ( (byte_180245605 & 0x20) != 0 )
          McTemplateU0d_EventWriteTransfer(v47, &CollectorIsOutOfMemory, 2147942414LL);
        pAptQualifier = -2147024882;
        SetAppXErrorFromLogMessage(
          -2147024882,
          &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID,
          &CollectorIsOutOfMemory,
          1u,
          &pAptQualifier);
        LODWORD(v63) = v8;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x21F,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
          "OSIntegration::DEH::ExtensionCatalogCollector::CreateExtensionRegistration",
          "hrInsert",
          (const char *)v63,
          v64);
        (*(void (__fastcall **)(struct OSIntegration::DEH::ExtensionRegistration *))(*(_QWORD *)v39 + 16LL))(v39);
        v48 = v68;
        if ( v68 )
        {
          v68 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
        }
        v49 = v69;
        if ( v69 )
        {
          v69 = 0;
          (*((void (__fastcall **)(RTL_SRWLOCK *))v49->Ptr + 2))(v49);
        }
        v50 = v70;
        if ( v70 )
        {
          v70 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v50 + 16LL))(v50);
        }
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(newString[0]);
        newString[0] = 0;
        v51 = v71;
        if ( v71 )
        {
          v71 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        }
        return v8;
      }
      *a4 = v39;
      v15 = v68;
      if ( v68 )
      {
        v68 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      v16 = v69;
      if ( v69 )
      {
        v69 = 0;
        (*((void (__fastcall **)(RTL_SRWLOCK *))v16->Ptr + 2))(v16);
      }
      v17 = v70;
      if ( v70 )
      {
        v70 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v17 + 16LL))(v17);
      }
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(newString[0]);
LABEL_16:
      v18 = v71;
      if ( v71 )
      {
        v71 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
      return 0;
    }
  }
LABEL_63:
  LODWORD(v58) = -2147024882;
  wil::details::in1diag5::_Log_Hr(
    retaddr,
    (void *)0x230,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
    "OSIntegration::DEH::ExtensionCatalogCollector::CreateExtensionRegistration",
    "((HRESULT)0x8007000EL)",
    v58,
    v64);
  if ( (byte_180245605 & 0x20) != 0 )
    McTemplateU0d_EventWriteTransfer(v42, &CollectorIsOutOfMemory, 2147942414LL);
  pAptQualifier = -2147024882;
  SetAppXErrorFromLogMessage(
    -2147024882,
    &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID,
    &CollectorIsOutOfMemory,
    1u,
    &pAptQualifier);
  LODWORD(v61) = -2147024882;
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)0x231,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
    "OSIntegration::DEH::ExtensionCatalogCollector::CreateExtensionRegistration",
    "E_OUTOFMEMORY",
    (const char *)v61,
    v64);
  v43 = v68;
  if ( v68 )
  {
    v68 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  v44 = v69;
  if ( v69 )
  {
    v69 = 0;
    (*((void (__fastcall **)(RTL_SRWLOCK *))v44->Ptr + 2))(v44);
  }
  v45 = v70;
  if ( v70 )
  {
    v70 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v45 + 16LL))(v45);
  }
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(newString[0]);
  newString[0] = 0;
  v46 = v71;
  if ( v71 )
  {
    v71 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800263cc  push    rbp
0x1800263ce  push    rbx
0x1800263cf  push    rsi
0x1800263d0  push    rdi
0x1800263d1  push    r12
0x1800263d3  push    r13
0x1800263d5  push    r14
0x1800263d7  push    r15
0x1800263d9  lea     rbp, [rsp-1Fh]
0x1800263de  sub     rsp, 0C8h
0x1800263e5  mov     rax, cs:__security_cookie
0x1800263ec  xor     rax, rsp
0x1800263ef  mov     [rbp+57h+var_48], rax
0x1800263f3  mov     r12, r9
0x1800263f6  mov     r15, r8
0x1800263f9  mov     r14, rdx
0x1800263fc  mov     rdi, rcx
0x1800263ff  mov     [rbp+57h+var_80], rcx
0x180026403  xor     esi, esi
0x180026405  mov     [r9], rsi
0x180026408  mov     [rbp+57h+hasEmbedNull], esi
0x18002640b  lea     rdx, [rbp+57h+hasEmbedNull]; hasEmbedNull
0x18002640f  mov     rcx, [r14]; string
0x180026412  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180026419  nop     dword ptr [rax+rax+00h]
0x18002641e  cmp     [rbp+57h+hasEmbedNull], esi
0x180026421  jnz     short loc_180026450
0x180026423  mov     rcx, [r14]; string
0x180026426  call    cs:__imp_WindowsIsStringEmpty
0x18002642d  nop     dword ptr [rax+rax+00h]
0x180026432  test    eax, eax
0x180026434  jnz     short loc_180026450
0x180026436  mov     rcx, [r14]; string
0x180026439  call    cs:__imp_WindowsGetStringLen
0x180026440  nop     dword ptr [rax+rax+00h]
0x180026445  cmp     eax, 7FFFh
0x18002644a  jbe     loc_1800265FB
0x180026450  mov     rcx, [rbp+5Fh]; this
0x180026454  mov     ebx, 80080204h
0x180026459  mov     dword ptr [rsp+100h+var_D8], ebx; wil::details *
0x18002645d  lea     rax, aHresult0x80080; "((HRESULT)0x80080204L)"
0x180026464  mov     [rsp+100h+var_E0], rax; char *
0x180026469  lea     rdi, aOsintegrationD_338; "OSIntegration::DEH::ExtensionCatalogCol"...
0x180026470  mov     r9, rdi; char *
0x180026473  lea     rsi, aOnecoreAdminAp_25; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18002647a  mov     r8, rsi; unsigned int
0x18002647d  mov     edx, 1CFh; void *
0x180026482  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x180026487  test    cs:byte_180245605, 20h
0x18002648e  jz      short loc_1800264BA
0x180026490  xor     edx, edx; length
0x180026492  mov     rcx, [r14]; string
0x180026495  call    cs:__imp_WindowsGetStringRawBuffer
0x18002649c  nop     dword ptr [rax+rax+00h]
0x1800264a1  mov     r9, rax
0x1800264a4  mov     r8d, ebx
0x1800264a7  lea     rdx, ContractIdentifierInvalidLength
0x1800264ae  lea     rcx, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context
0x1800264b5  call    McTemplateU0dz_EventWriteTransfer
0x1800264ba  xor     edx, edx; length
0x1800264bc  mov     rcx, [r14]; string
0x1800264bf  call    cs:__imp_WindowsGetStringRawBuffer
0x1800264c6  nop     dword ptr [rax+rax+00h]
0x1800264cb  mov     [rsp+100h+var_E0], rax
0x1800264d0  mov     r9d, ebx
0x1800264d3  lea     r8, ContractIdentifierInvalidLength
0x1800264da  mov     ecx, ebx
0x1800264dc  call    ??$appxLog@JPEBG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@JPEBG@Z; details::appxLog<long,ushort const *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,long,ushort const *)
0x1800264e1  mov     edx, 1D1h; void *
0x1800264e6  mov     dword ptr [rsp+100h+var_D8], ebx; char *
0x1800264ea  lea     rax, aAppxEInvalidMa; "APPX_E_INVALID_MANIFEST"
0x1800264f1  mov     [rsp+100h+var_E0], rax; char *
0x1800264f6  mov     r9, rdi; char *
0x1800264f9  mov     r8, rsi; unsigned int
0x1800264fc  mov     rcx, [rbp+5Fh]; this
0x180026500  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180026505  jmp     loc_180026E00
0x18002650a  mov     byte ptr [rbp+57h+var_D0], r15b
0x18002650e  mov     rcx, [rbp+57h+var_80]
0x180026512  mov     rcx, [rcx+20h]
0x180026516  mov     [rbp+57h+var_80], r13
0x18002651a  mov     rax, [rbp+57h+var_70]
0x18002651e  mov     [rbp+57h+var_78], rax
0x180026522  mov     rax, [rcx]
0x180026525  lea     r9, [rbp+57h+var_D0]
0x180026529  mov     r8, rbx
0x18002652c  lea     rdx, [rbp+57h+var_80]
0x180026530  mov     rax, [rax+50h]
0x180026534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026539  mov     ebx, eax
0x18002653b  mov     rcx, [rbp+5Fh]; this
0x18002653f  test    eax, eax
0x180026541  js      loc_180026CC1
0x180026547  mov     [r12], r14
0x18002654b  mov     rcx, [rbp+57h+var_B0]
0x18002654f  test    rcx, rcx
0x180026552  jz      short loc_180026565
0x180026554  mov     [rbp+57h+var_B0], r15
0x180026558  mov     rax, [rcx]
0x18002655b  mov     rax, [rax+10h]
0x18002655f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026564  nop
0x180026565  mov     rcx, [rbp+57h+var_A8]
0x180026569  test    rcx, rcx
0x18002656c  jz      short loc_18002657F
0x18002656e  mov     [rbp+57h+var_A8], r15
0x180026572  mov     rax, [rcx]
0x180026575  mov     rax, [rax+10h]
0x180026579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002657e  nop
0x18002657f  mov     rcx, [rbp+57h+var_A0]
0x180026583  test    rcx, rcx
0x180026586  jz      short loc_180026599
0x180026588  mov     [rbp+57h+var_A0], r15
0x18002658c  mov     rax, [rcx]
0x18002658f  mov     rax, [rax+10h]
0x180026593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026598  nop
0x180026599  mov     rcx, [rbp+57h+string]; string
0x18002659d  call    cs:__imp_WindowsDeleteString
0x1800265a4  nop     dword ptr [rax+rax+00h]
0x1800265a9  mov     [rbp+57h+string], r15
0x1800265ad  mov     rcx, [rbp+57h+newString]; string
0x1800265b1  call    cs:__imp_WindowsDeleteString
0x1800265b8  nop     dword ptr [rax+rax+00h]
0x1800265bd  nop
0x1800265be  mov     rcx, [rbp+57h+var_98]
0x1800265c2  test    rcx, rcx
0x1800265c5  jz      short loc_1800265D8
0x1800265c7  mov     [rbp+57h+var_98], r15
0x1800265cb  mov     rax, [rcx]
0x1800265ce  mov     rax, [rax+10h]
0x1800265d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800265d7  nop
0x1800265d8  xor     eax, eax
0x1800265da  mov     rcx, [rbp+57h+var_48]
0x1800265de  xor     rcx, rsp; StackCookie
0x1800265e1  call    __security_check_cookie
0x1800265e6  add     rsp, 0C8h
0x1800265ed  pop     r15
0x1800265ef  pop     r14
0x1800265f1  pop     r13
0x1800265f3  pop     r12
0x1800265f5  pop     rdi
0x1800265f6  pop     rsi
0x1800265f7  pop     rbx
0x1800265f8  pop     rbp
0x1800265f9  retn
0x1800265fb  mov     rbx, [r15]
0x1800265fe  mov     [rbp+57h+hasEmbedNull], esi
0x180026601  lea     rdx, [rbp+57h+hasEmbedNull]; hasEmbedNull
0x180026605  mov     rcx, rbx; string
0x180026608  call    cs:__imp_WindowsStringHasEmbeddedNull
0x18002660f  nop     dword ptr [rax+rax+00h]
0x180026614  cmp     [rbp+57h+hasEmbedNull], esi
0x180026617  jnz     loc_180026F47
0x18002661d  mov     rcx, rbx; string
0x180026620  call    cs:__imp_WindowsIsStringEmpty
0x180026627  nop     dword ptr [rax+rax+00h]
0x18002662c  test    eax, eax
0x18002662e  jnz     loc_180026F47
0x180026634  mov     rcx, rbx; string
0x180026637  call    cs:__imp_WindowsGetStringLen
0x18002663e  nop     dword ptr [rax+rax+00h]
0x180026643  mov     ebx, 100h
0x180026648  cmp     eax, ebx
0x18002664a  ja      loc_180026F47
0x180026650  mov     rcx, [r14]; string
0x180026653  call    cs:__imp_WindowsGetStringLen
0x18002665a  nop     dword ptr [rax+rax+00h]
0x18002665f  cmp     eax, ebx
0x180026661  ja      loc_180026EAC
0x180026667  mov     rcx, [r15]; string
0x18002666a  call    cs:__imp_WindowsGetStringLen
0x180026671  nop     dword ptr [rax+rax+00h]
0x180026676  cmp     eax, ebx
0x180026678  ja      loc_180026EAC
0x18002667e  mov     r13, [r14]
0x180026681  mov     rax, [r15]
0x180026684  mov     [rbp+57h+var_70], rax
0x180026688  mov     [rbp+57h+var_98], rsi
0x18002668c  mov     rcx, [rdi+20h]
0x180026690  mov     [rbp+57h+newString], r13
0x180026694  mov     [rbp+57h+var_88], rax
0x180026698  mov     rax, [rcx]
0x18002669b  lea     r8, [rbp+57h+var_98]
0x18002669f  lea     rdx, [rbp+57h+newString]
0x1800266a3  mov     rax, [rax+30h]
0x1800266a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266ac  test    eax, eax
0x1800266ae  jns     loc_180026EA4
0x1800266b4  lea     r9, [rbp+57h+var_68]; string
0x1800266b8  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800266bc  mov     edx, 20h ; ' '; length
0x1800266c1  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x1800266c8  call    cs:__imp_WindowsCreateStringReference
0x1800266cf  nop     dword ptr [rax+rax+00h]
0x1800266d4  test    eax, eax
0x1800266d6  js      loc_180026E07
0x1800266dc  mov     [rbp+57h+newString], rsi
0x1800266e0  mov     [rbp+57h+string], rsi
0x1800266e4  mov     [rbp+57h+var_A0], rsi
0x1800266e8  mov     [rbp+57h+var_A8], rsi
0x1800266ec  mov     [rbp+57h+var_B0], rsi
0x1800266f0  mov     rbx, [r14]
0x1800266f3  xor     ecx, ecx; string
0x1800266f5  call    cs:__imp_WindowsDeleteString
0x1800266fc  nop     dword ptr [rax+rax+00h]
0x180026701  mov     [rbp+57h+newString], rsi
0x180026705  lea     rdx, [rbp+57h+newString]; newString
0x180026709  mov     rcx, rbx; string
0x18002670c  call    cs:__imp_WindowsDuplicateString
0x180026713  nop     dword ptr [rax+rax+00h]
0x180026718  mov     rcx, [rbp+5Fh]; this
0x18002671c  mov     r14d, 8007000Eh
0x180026722  lea     rdi, aOsintegrationD_338; "OSIntegration::DEH::ExtensionCatalogCol"...
0x180026729  lea     rsi, aOnecoreAdminAp_25; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180026730  test    eax, eax
0x180026732  js      loc_180026E27
0x180026738  mov     rbx, [r15]
0x18002673b  mov     rcx, [rbp+57h+string]; string
0x18002673f  xor     r15d, r15d
0x180026742  test    rbx, rbx
0x180026745  jz      short loc_18002674C
0x180026747  cmp     rbx, rcx
0x18002674a  jz      short loc_180026777
0x18002674c  call    cs:__imp_WindowsDeleteString
0x180026753  nop     dword ptr [rax+rax+00h]
0x180026758  mov     [rbp+57h+string], r15
0x18002675c  lea     rdx, [rbp+57h+string]; newString
0x180026760  mov     rcx, rbx; string
0x180026763  call    cs:__imp_WindowsDuplicateString
0x18002676a  nop     dword ptr [rax+rax+00h]
0x18002676f  test    eax, eax
0x180026771  js      loc_180026BA8
0x180026777  lea     rcx, [rbp+57h+var_A0]
0x18002677b  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180026780  mov     [rbp+57h+var_A0], r15
0x180026784  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002678b  mov     ecx, 0A0h; unsigned __int64
0x180026790  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180026795  mov     rbx, rax
0x180026798  test    rax, rax
0x18002679b  jnz     short loc_1800267A5
0x18002679d  mov     rbx, r15
0x1800267a0  jmp     loc_180026851
0x1800267a5  mov     rcx, rbx
0x1800267a8  call    ??0?$RuntimeClass@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@234@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>>::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>>(void)
0x1800267ad  lea     rax, ??_7?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@6B@; const Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::`vftable'
0x1800267b4  mov     [rbx], rax
0x1800267b7  lea     rax, ??_7?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@6BIWeakReferenceSource@@@; const Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::`vftable'{for `IWeakReferenceSource'}
0x1800267be  mov     [rbx+8], rax
0x1800267c2  lea     rax, ??_7?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@@; const Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>>'}
0x1800267c9  mov     [rbx+10h], rax
0x1800267cd  lea     rcx, [rbx+28h]
0x1800267d1  mov     [rcx], rbx
0x1800267d4  mov     [rcx+8], r15
0x1800267d8  mov     [rcx+10h], r15
0x1800267dc  mov     dword ptr [rcx+18h], 11h
0x1800267e3  mov     eax, 0FFFFFFFFh
0x1800267e8  mov     [rcx+28h], rax
0x1800267ec  mov     [rcx+30h], r15
0x1800267f0  mov     [rcx+38h], r15d
0x1800267f4  mov     dword ptr [rcx+3Ch], 0Ah
0x1800267fb  mov     [rcx+40h], r15
0x1800267ff  mov     [rcx+48h], r15
0x180026803  mov     dword ptr [rcx+1Ch], 3F400000h
0x18002680a  mov     dword ptr [rcx+20h], 3E800000h
0x180026811  mov     dword ptr [rcx+24h], 40100000h
0x180026818  call    ?UpdateRehashThresholds@?$XHashMap@PEAUHSTRING__@@PEAUIComTypeLibRegistration@DEH@OSIntegration@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAVComTypeLibRegistration@DEH@OSIntegration@@URegistryNameHashFunction@RegistryMapDetails@@URegistryNameEqualityPredicate@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVComTypeLibRegistration@DEH@OSIntegration@@@9Collections@Foundation@Windows@@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAVComTypeLibRegistration@DEH@OSIntegration@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@9Collections@Foundation@Windows@@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIComTypeLibRegistration@DEH@OSIntegration@@@XWinRT@@@XWinRT@@AEAAXXZ; XWinRT::XHashMap<HSTRING__ *,OSIntegration::DEH::IComTypeLibRegistration *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,OSIntegration::DEH::ComTypeLibRegistration *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<OSIntegration::DEH::ComTypeLibRegistration *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,OSIntegration::DEH::ComTypeLibRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<OSIntegration::DEH::IComTypeLibRegistration *>>::UpdateRehashThresholds(void)
0x18002681d  lea     rcx, [rbx+80h]; this
0x180026824  call    ??0ComLock@XWinRT@@QEAA@_N@Z; XWinRT::ComLock::ComLock(bool)
0x180026829  mov     [rbx+90h], r15
0x180026830  mov     [rbx+98h], r15b
0x180026837  mov     [rbx+9Ch], r15d
0x18002683e  mov     rcx, rbx
0x180026841  call    ?Initialize@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@AEAAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Initialize(void)
0x180026846  mov     r14d, eax
0x180026849  test    eax, eax
0x18002684b  jns     loc_180026E4F
0x180026851  test    rbx, rbx
0x180026854  jz      short loc_180026866
0x180026856  mov     rax, [rbx]
0x180026859  mov     rcx, rbx
0x18002685c  mov     rax, [rax+10h]
0x180026860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026865  nop
0x180026866  test    r14d, r14d
0x180026869  js      loc_180026BA2
0x18002686f  lea     rcx, [rbp+57h+var_A8]
0x180026873  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180026878  mov     [rbp+57h+var_A8], r15
0x18002687c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026883  mov     ecx, 0A0h; unsigned __int64
0x180026888  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002688d  mov     rbx, rax
0x180026890  test    rax, rax
0x180026893  jz      loc_180026E69
0x180026899  mov     rcx, rax
0x18002689c  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IMap@U_GUID@@PEAVComTreatAsClassRegistration@DEH@OSIntegration@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@U_GUID@@PEAVComTreatAsClassRegistration@DEH@OSIntegration@@@Collections@Foundation@Windows@@@567@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::ComTreatAsClassRegistration *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<_GUID,OSIntegration::DEH::ComTreatAsClassRegistration *> *>>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::ComTreatAsClassRegistration *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<_GUID,OSIntegration::DEH::ComTreatAsClassRegistration *> *>>(void)
  ... truncated ...
```
