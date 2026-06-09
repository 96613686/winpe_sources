# OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreateClsidKeyTemplateFromSharedProperties(void)

- ea: `0x18006715c`
- end: `0x18006833d`
- name: `?CreateClsidKeyTemplateFromSharedProperties@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@AEBA?AVKey@RegistryCompatibility@34@XZ`
- size: `4577`
- prototype: `struct OSIntegration::DEH::RegistryCompatibility::Key __high(void)`
- caller_count: `1`
- callee_count: `41`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18015052c`

## callees

- `0x180006970`
- `0x180036e58`
- `0x180036eb4`
- `0x180056bd4`
- `0x180059424`
- `0x1800606d4`
- `0x180066780`
- `0x180066938`
- `0x180066988`
- `0x1800669b0`
- `0x18006715c`
- `0x180068ae0`
- `0x180068b4c`
- `0x180078574`
- `0x180078760`
- `0x180078784`
- `0x180078818`
- `0x18008a340`
- `0x18008e10c`
- `0x18008f180`
- `0x18009f800`
- `0x1800a0370`
- `0x1800aed10`
- `0x1800f74bc`
- `0x180101090`
- `0x1801011f8`
- `0x180101528`
- `0x18010158c`
- `0x1801058d0`
- `0x18014240c`
- `0x180142930`
- `0x18014297c`
- `0x180148c94`
- `0x18014b57c`
- `0x18014b5dc`
- `0x18014c598`
- `0x18014c658`
- `0x18014e284`
- `0x1801502a8`
- `0x180169b38`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067535`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067576`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800675cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067cbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067ff9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067535`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067576`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800675cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067cbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067ff9`

## string_xrefs

- `0x180067475`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x180067660`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x180067b93`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x180067d6d`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x180067d96`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x180067dbf`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x180067ed8`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x1800680a8`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x1800680d1`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x1800680fa`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x180067462`: `_properties.ImplementedCategories.MapView.CopyTo(IID_PPV_ARGS(&implementedCategoriesIterable))`
- `0x18006746e`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreateClsidKeyTemplateFromSharedProperties`
- `0x180067659`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreateClsidKeyTemplateFromSharedProperties`
- `0x180067b8c`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreateClsidKeyTemplateFromSharedProperties`
- `0x180067d66`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreateClsidKeyTemplateFromSharedProperties`
- `0x180067d8f`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreateClsidKeyTemplateFromSharedProperties`
- `0x180067db8`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreateClsidKeyTemplateFromSharedProperties`
- `0x180067ed1`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreateClsidKeyTemplateFromSharedProperties`
- `0x1800680a1`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreateClsidKeyTemplateFromSharedProperties`
- `0x1800680ca`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreateClsidKeyTemplateFromSharedProperties`
- `0x1800680f3`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreateClsidKeyTemplateFromSharedProperties`
- `0x180067b80`: `_properties.Verbs.MapView.CopyTo(IID_PPV_ARGS(&verbsIterable))`
- `0x180067ec5`: `_properties.MiscStatusAspects.MapView.CopyTo( IID_PPV_ARGS(&miscStatusAspectsIterable))`
- `0x180067ae0`: `ReadWritable`

## pseudocode

```c
// Hidden C++ exception states: #wind=59
OSIntegration::DEH::RegistryCompatibility::Key *__fastcall OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreateClsidKeyTemplateFromSharedProperties(
        __int64 a1,
        OSIntegration::DEH::RegistryCompatibility::Key *a2)
{
  __int64 v4; // rdx
  int v5; // r14d
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  char v11; // al
  int v12; // eax
  _QWORD *v13; // rbx
  __int64 v14; // rax
  int v15; // eax
  PCWSTR v16; // rax
  char *v17; // r8
  int v18; // edx
  int v19; // ecx
  PCWSTR v20; // rax
  char *v21; // r8
  int v22; // edx
  int v23; // ecx
  const struct GuidString *v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  unsigned int v28; // r15d
  unsigned int v29; // edx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  int v33; // eax
  WCHAR *v34; // rbx
  __int64 v35; // rax
  int v36; // eax
  __int64 v37; // rax
  int v38; // eax
  __int64 v39; // rax
  int v40; // eax
  __int64 v41; // rax
  __int64 v42; // rdx
  __int64 v43; // rax
  int v44; // eax
  __int64 *v45; // rbx
  __int64 v46; // rax
  int v47; // eax
  __int64 v48; // rax
  int v49; // eax
  __int64 v50; // rax
  int v51; // eax
  __int64 v52; // rax
  __int64 v53; // rax
  const struct GuidString *v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  wil::details *v58; // [rsp+28h] [rbp-D8h]
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v60; // [rsp+38h] [rbp-C8h] BYREF
  PCWSTR StringRawBuffer; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v62; // [rsp+48h] [rbp-B8h] BYREF
  int v63; // [rsp+50h] [rbp-B0h]
  __int64 v64; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v65[3]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v66; // [rsp+78h] [rbp-88h] BYREF
  int v67; // [rsp+80h] [rbp-80h]
  __int64 v68; // [rsp+88h] [rbp-78h]
  _BYTE v69[16]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v70[32]; // [rsp+A8h] [rbp-58h] BYREF
  PCWSTR v71; // [rsp+C8h] [rbp-38h] BYREF
  int v72; // [rsp+D0h] [rbp-30h]
  __int64 v73; // [rsp+D8h] [rbp-28h]
  _BYTE v74[16]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v75[40]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v76[8]; // [rsp+118h] [rbp+18h] BYREF
  int v77; // [rsp+120h] [rbp+20h]
  OLECHAR v78[12]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v79[56]; // [rsp+148h] [rbp+48h] BYREF
  OLECHAR v80[40]; // [rsp+180h] [rbp+80h] BYREF
  OLECHAR sz[40]; // [rsp+1D0h] [rbp+D0h] BYREF
  OLECHAR v82[40]; // [rsp+220h] [rbp+120h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v65[2] = a2;
  OSIntegration::DEH::RegistryCompatibility::Key::Key(a2);
  v5 = 1;
  v63 = 1;
  if ( *(_BYTE *)(a1 + 72) )
  {
    v6 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
           (__int64)v69,
           (const struct OpaqueString *)(a1 + 80));
    OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData((__int64)v74, v6);
    OSIntegration::DEH::RegistryCompatibility::Key::AddDefaultValue(a2, v74);
    std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v74);
    std::wstring::_Tidy_deallocate(v70);
  }
  if ( *(_BYTE *)(a1 + 88) || *(_BYTE *)(a1 + 720) )
  {
    OSIntegration::DEH::RegistryCompatibility::Key::Key((OSIntegration::DEH::RegistryCompatibility::Key *)v78);
    if ( *(_BYTE *)(a1 + 88) )
    {
      Uint32String::Uint32String((Uint32String *)&v71, 2u);
      v7 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
             (__int64)v69,
             (const struct OpaqueString *)(a1 + 96));
      OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData((__int64)v74, v7);
      OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(
        &v66,
        (OSIntegration::DEH::RegistryCompatibility::Details *)&v71);
      OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(v78, &v66, v74);
      std::wstring::_Tidy_deallocate(&v66);
      std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v74);
      std::wstring::_Tidy_deallocate(v70);
    }
    if ( *(_BYTE *)(a1 + 720) )
    {
      Uint32String::Uint32String((Uint32String *)&v71, 3u);
      v8 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
             (__int64)v69,
             (const struct OpaqueString *)(a1 + 728));
      OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData((__int64)v74, v8);
      OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(
        &v66,
        (OSIntegration::DEH::RegistryCompatibility::Details *)&v71);
      OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(v78, &v66, v74);
      std::wstring::_Tidy_deallocate(&v66);
      std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v74);
      std::wstring::_Tidy_deallocate(v70);
    }
    OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(&v66, (__int64)L"AuxUserType");
    named_entries::emplace_unique<std::vector<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>,OSIntegration::DEH::RegistryCompatibility::Key>>,OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>,OSIntegration::DEH::RegistryCompatibility::Key>(
      (char *)a2 + 24,
      &v66,
      v78);
    std::wstring::_Tidy_deallocate(&v66);
    OSIntegration::DEH::RegistryCompatibility::Key::~Key((OSIntegration::DEH::RegistryCompatibility::Key *)v78);
  }
  if ( *(_BYTE *)(a1 + 104) )
  {
    v9 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
           (__int64)v69,
           (const struct OpaqueString *)(a1 + 112));
    OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData((__int64)v74, v9);
    OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(&v66, (__int64)L"ProgID");
    OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(a2, &v66, v74);
    std::wstring::_Tidy_deallocate(&v66);
    std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v74);
    std::wstring::_Tidy_deallocate(v70);
  }
  if ( *(_BYTE *)(a1 + 120) )
  {
    v10 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
            (__int64)v69,
            (const struct OpaqueString *)(a1 + 128));
    OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData((__int64)v74, v10);
    OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(&v66);
    OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(a2, &v66, v74);
    std::wstring::_Tidy_deallocate(&v66);
    std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v74);
    std::wstring::_Tidy_deallocate(v70);
  }
  if ( *(_BYTE *)(a1 + 138) )
    v11 = *(_BYTE *)(a1 + 139);
  else
    v11 = 0;
  if ( v11 )
  {
    OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(&v66, (__int64)L"Insertable");
    OSIntegration::DEH::RegistryCompatibility::Key::AddEmptySubkey(a2, &v66);
    std::wstring::_Tidy_deallocate(&v66);
  }
  if ( *(_QWORD *)(a1 + 144) )
  {
    v60 = 0;
    v12 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *>>::CopyTo(
            a1 + 144,
            v4,
            &v60);
    if ( v12 < 0 )
    {
      LODWORD(v58) = v12;
      wil::details::in1diag5::_FailFast_Hr(
        retaddr,
        (void *)0x853,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
        "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreateClsidKeyTemplateFromSharedProperties",
        "_properties.ImplementedCategories.MapView.CopyTo(IID_PPV_ARGS(&implementedCategoriesIterable))",
        v58,
        (int)string);
    }
    GuidString::GuidString(sz, (GUID *)&CATID_Control);
    GuidString::GuidString(v82, (GUID *)&CATID_Programmable);
    OSIntegration::DEH::RegistryCompatibility::Key::Key((OSIntegration::DEH::RegistryCompatibility::Key *)v69);
    wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<_GUID,OSIntegration::DEH::ComInterfaceRegistration *> *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(
      v76,
      v60);
    v5 = 3;
    v63 = 3;
    v71 = 0;
    v72 = -1;
    v73 = 0;
    while ( 1 )
    {
      if ( v77 == -1 )
      {
        wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<_GUID,OSIntegration::DEH::ComInterfaceRegistration *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(&v71);
        wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<_GUID,OSIntegration::DEH::ComInterfaceRegistration *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(v76);
        OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(&v66);
        named_entries::emplace_unique<std::vector<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>,OSIntegration::DEH::RegistryCompatibility::Key>>,OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>,OSIntegration::DEH::RegistryCompatibility::Key>(
          (char *)a2 + 24,
          &v66,
          v69);
        std::wstring::_Tidy_deallocate(&v66);
        OSIntegration::DEH::RegistryCompatibility::Key::~Key((OSIntegration::DEH::RegistryCompatibility::Key *)v69);
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v60);
        goto LABEL_39;
      }
      v13 = *(_QWORD **)wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *,wil::err_exception_policy>::iterable_iterator::operator*(v76);
      v62 = v13;
      Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(&v62);
      string = 0;
      v14 = *v13;
      string = 0;
      v15 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING *))(v14 + 48))(v13, &string);
      if ( v15 < 0 )
      {
        LODWORD(v58) = v15;
        wil::details::in1diag5::Throw_Hr(
          retaddr,
          (void *)0x85C,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
          "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreateClsidKeyTemplateFromSharedProperties",
          "implementedCategoryKeyValuePair->get_Key(&implementedCategory)",
          (const char *)v58,
          (int)string);
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(&v66, &StringRawBuffer);
      OSIntegration::DEH::RegistryCompatibility::Key::AddEmptySubkey(v69, &v66);
      std::wstring::_Tidy_deallocate(&v66);
      v16 = WindowsGetStringRawBuffer(string, 0);
      v17 = (char *)((char *)sz - (char *)v16);
      do
      {
        v18 = *(unsigned __int16 *)&v17[(_QWORD)v16];
        v19 = *v16 - v18;
        if ( v19 )
          break;
        ++v16;
      }
      while ( v18 );
      if ( !v19 )
        break;
      v20 = WindowsGetStringRawBuffer(string, 0);
      v21 = (char *)((char *)v82 - (char *)v20);
      do
      {
        v22 = *(unsigned __int16 *)&v21[(_QWORD)v20];
        v23 = *v20 - v22;
        if ( v23 )
          break;
        ++v20;
      }
      while ( v22 );
      if ( !v23 )
      {
        OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(&v66, (__int64)L"Programmable");
        OSIntegration::DEH::RegistryCompatibility::Key::AddEmptySubkey(a2, &v66);
        goto LABEL_35;
      }
LABEL_36:
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v62);
      wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *,wil::err_exception_policy>::iterable_iterator::operator++(v76);
    }
    OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(&v66, (__int64)L"Control");
    OSIntegration::DEH::RegistryCompatibility::Key::AddEmptySubkey(a2, &v66);
LABEL_35:
    std::wstring::_Tidy_deallocate(&v66);
    goto LABEL_36;
  }
LABEL_39:
  if ( *(_BYTE *)(a1 + 152) )
  {
    v24 = GuidString::GuidString(v80, (GUID *)(a1 + 156));
    v25 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
            (__int64)v69,
            v24);
    OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData((__int64)v74, v25);
    OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(&v66, (__int64)L"AutoConvertTo");
    OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(a2, &v66, v74);
    std::wstring::_Tidy_deallocate(&v66);
    std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v74);
    std::wstring::_Tidy_deallocate(v70);
  }
  if ( *(_BYTE *)(a1 + 176) )
  {
    StringRawBuffer = *(PCWSTR *)(a1 + 944);
    v26 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
            (__int64)v69,
            &StringRawBuffer);
    OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData((__int64)v74, v26);
    OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(&v66, (__int64)L"DefaultIcon");
    OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(a2, &v66, v74);
    std::wstring::_Tidy_deallocate(&v66);
    std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v74);
    std::wstring::_Tidy_deallocate(v70);
  }
  if ( *(_BYTE *)(a1 + 192) || *(_BYTE *)(a1 + 208) )
  {
    OSIntegration::DEH::RegistryCompatibility::Key::Key((OSIntegration::DEH::RegistryCompatibility::Key *)v78);
    if ( *(_BYTE *)(a1 + 192) )
    {
      v27 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
              (__int64)v69,
              (const struct OpaqueString *)(a1 + 200));
      OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData((__int64)v74, v27);
      OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(&v66, (__int64)L"DefaultFile");
      OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(v78, &v66, v74);
      std::wstring::_Tidy_deallocate(&v66);
      std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v74);
      std::wstring::_Tidy_deallocate(v70);
    }
    if ( *(_BYTE *)(a1 + 208) )
    {
      OSIntegration::DEH::RegistryCompatibility::Key::Key((OSIntegration::DEH::RegistryCompatibility::Key *)v69);
      v28 = 0;
      begin(&v71);
      end(v65, a1 + 216);
      while ( (unsigned __int8)MultiStringIterator::operator!=(&v71, v65) )
      {
        StringRawBuffer = *(PCWSTR *)MultiStringIterator::operator*(&v71);
        v29 = v28++;
        Uint32String::Uint32String((Uint32String *)v76, v29);
        v30 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
                (__int64)v74,
                &StringRawBuffer);
        OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData((__int64)v80, v30);
        OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(
          &v66,
          (OSIntegration::DEH::RegistryCompatibility::Details *)v76);
        OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(v69, &v66, v80);
        std::wstring::_Tidy_deallocate(&v66);
        std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v80);
        std::wstring::_Tidy_deallocate(v75);
        MultiStringIterator::operator++(&v71);
      }
      OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(&v66, (__int64)L"GetSet");
      named_entries::emplace_unique<std::vector<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>,OSIntegration::DEH::RegistryCompatibility::Key>>,OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>,OSIntegration::DEH::RegistryCompatibility::Key>(
        v79,
        &v66,
        v69);
      std::wstring::_Tidy_deallocate(&v66);
      OSIntegration::DEH::RegistryCompatibility::Key::~Key((OSIntegration::DEH::RegistryCompatibility::Key *)v69);
    }
    OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(&v66, (__int64)L"DataFormats");
    named_entries::emplace_unique<std::vector<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>,OSIntegration::DEH::RegistryCompatibility::Key>>,OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>,OSIntegration::DEH::RegistryCompatibility::Key>(
      (char *)a2 + 24,
      &v66,
      v78);
    std::wstring::_Tidy_deallocate(&v66);
    OSIntegration::DEH::RegistryCompatibility::Key::~Key((OSIntegration::DEH::RegistryCompatibility::Key *)v78);
  }
  if ( *(_BYTE *)(a1 + 224) || *(_BYTE *)(a1 + 240) )
  {
    OSIntegration::DEH::RegistryCompatibility::Key::Key((OSIntegration::DEH::RegistryCompatibility::Key *)v78);
    if ( *(_BYTE *)(a1 + 224) )
    {
      OSIntegration::DEH::RegistryCompatibility::Key::Key((OSIntegration::DEH::RegistryCompatibility::Key *)v69);
      v31 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
              (__int64)v74,
              (const struct OpaqueString *)(a1 + 232));
      OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData((__int64)v80, v31);
      OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(&v66, (__int64)L"Main");
      OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(v69, &v66, v80);
      std::wstring::_Tidy_deallocate(&v66);
      std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v80);
      std::wstring::_Tidy_deallocate(v75);
      OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(&v66);
      named_entries::emplace_unique<std::vector<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>,OSIntegration::DEH::RegistryCompatibility::Key>>,OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>,OSIntegration::DEH::RegistryCompatibility::Key>(
        v79,
        &v66,
        v69);
      std::wstring::_Tidy_deallocate(&v66);
      OSIntegration::DEH::RegistryCompatibility::Key::~Key((OSIntegration::DEH::RegistryCompatibility::Key *)v69);
    }
    if ( *(_BYTE *)(a1 + 240) )
    {
      OSIntegration::DEH::RegistryCompatibility::Key::Key((OSIntegration::DEH::RegistryCompatibility::Key *)v69);
      v32 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
              (__int64)v74,
              (const struct OpaqueString *)(a1 + 248));
      OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData((__int64)v80, v32);
      OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(&v66, (__int64)L"Main");
      OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(v69, &v66, v80);
      std::wstring::_Tidy_deallocate(&v66);
      std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v80);
      std::wstring::_Tidy_deallocate(v75);
      OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(&v66, (__int64)L"ReadWritable");
      named_entries::emplace_unique<std::vector<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>,OSIntegration::DEH::RegistryCompatibility::Key>>,OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>,OSIntegration::DEH::RegistryCompatibility::Key>(
        v79,
        &v66,
        v69);
      std::wstring::_Tidy_deallocate(&v66);
      OSIntegration::DEH::RegistryCompatibility::Key::~Key((OSIntegration::DEH::RegistryCompatibility::Key *)v69);
    }
    OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(&v66, (__int64)L"Conversion");
    named_entries::emplace_unique<std::vector<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>,OSIntegration::DEH::RegistryCompatibility::Key>>,OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>,OSIntegration::DEH::RegistryCompatibility::Key>(
      (char *)a2 + 24,
      &v66,
      v78);
    std::wstring::_Tidy_deallocate(&v66);
    OSIntegration::DEH::RegistryCompatibility::Key::~Key((OSIntegration::DEH::RegistryCompatibility::Key *)v78);
  }
  if ( *(_QWORD *)(a1 + 256) )
  {
    v62 = 0;
    v33 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *>>::CopyTo(
            a1 + 256,
            v4,
            &v62);
    if ( v33 < 0 )
    {
      LODWORD(v58) = v33;
      wil::details::in1diag5::_FailFast_Hr(
        retaddr,
        (void *)0x8B6,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
        "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreateClsidKeyTemplateFromSharedProperties",
        "_properties.Verbs.MapView.CopyTo(IID_PPV_ARGS(&verbsIterable))",
        v58,
        (int)string);
    }
    OSIntegration::DEH::RegistryCompatibility::Key::Key((OSIntegration::DEH::RegistryCompatibility::Key *)v69);
    wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<_GUID,OSIntegration::DEH::ComInterfaceRegistration *> *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(
      v76,
      v62);
    v5 |= 4u;
    v63 = v5;
    v66 = 0;
    v67 = -1;
    v68 = 0;
    while ( v77 != -1 )
    {
      v34 = *(WCHAR **)wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *,wil::err_exception_policy>::iterable_iterator::operator*(v76);
      StringRawBuffer = v34;
      Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(&StringRawBuffer);
      v60 = 0;
      v35 = *(_QWORD *)v34;
      v60 = 0;
      v36 = (*(__int64 (__fastcall **)(WCHAR *, HSTRING *))(v35 + 48))(v34, &v60);
      if ( v36 < 0 )
      {
        LODWORD(v58) = v36;
        wil::details::in1diag5::Throw_Hr(
          retaddr,
          (void *)0x8BD,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
          "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreateClsidKeyTemplateFromSharedProperties",
          "verbKeyValuePair->get_Key(&verbId)",
          (const char *)v58,
          (int)string);
      }
      v64 = 0;
      v37 = *(_QWORD *)v34;
      v64 = 0;
      v38 = (*(__int64 (__fastcall **)(WCHAR *, __int64 *))(v37 + 56))(v34, &v64);
      if ( v38 < 0 )
      {
        LODWORD(v58) = v38;
        wil::details::in1diag5::Throw_Hr(
          retaddr,
          (void *)0x8C0,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
          "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreateClsidKeyTemplateFromSharedProperties",
          "verbKeyValuePair->get_Value(&verbInspectable)",
          (const char *)v58,
          (int)string);
      }
      wil::com_ptr_t<IInspectable,wil::err_failfast_policy>::query<Windows::Foundation::IPropertyValue>(&v64, v65);
      string = 0;
      v39 = *(_QWORD *)v65[0];
      string = 0;
      v40 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(v39 + 152))(v65[0], &string);
      if ( v40 < 0 )
      {
        LODWORD(v58) = v40;
        wil::details::in1diag5::Throw_Hr(
          retaddr,
          (void *)0x8C5,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
          "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreateClsidKeyTemplateFromSharedProperties",
          "verbPropertyValue->GetString(&verb)",
          (const char *)v58,
          (int)string);
      }
      v41 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
              (__int64)v74,
              &string);
      OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData((__int64)v80, v41);
      v71 = WindowsGetStringRawBuffer(v60, 0);
      OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(v78, &v71);
      OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(v69, v78, v80);
      std::wstring::_Tidy_deallocate(v78);
      std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v80);
      std::wstring::_Tidy_deallocate(v75);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(v65);
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v64);
      Windows::Internal::String::~String((Windows::Internal::String *)&v60);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&StringRawBuffer);
      wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *,wil::err_exception_policy>::iterable_iterator::operator++(v76);
    }
    wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<_GUID,OSIntegration::DEH::ComInterfaceRegistration *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(&v66);
    wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<_GUID,OSIntegration::DEH::ComInterfaceRegistration *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(v76);
    OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(v78, (__int64)L"Verb");
    named_entries::emplace_unique<std::vector<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>,OSIntegration::DEH::RegistryCompatibility::Key>>,OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>,OSIntegration::DEH::RegistryCompatibility::Key>(
      (char *)a2 + 24,
      v78,
      v69);
    std::wstring::_Tidy_deallocate(v78);
    OSIntegration::DEH::RegistryCompatibility::Key::~Key((OSIntegration::DEH::RegistryCompatibility::Key *)v69);
    wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v62);
  }
  if ( *(_BYTE *)(a1 + 264) || *(_QWORD *)(a1 + 280) )
  {
    OSIntegration::DEH::RegistryCompatibility::Key::Key((OSIntegration::DEH::RegistryCompatibility::Key *)v69);
    if ( *(_BYTE *)(a1 + 264) )
    {
      v43 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
              (__int64)v74,
              (const struct OpaqueString *)(a1 + 272));
      OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData((__int64)v80, v43);
      OSIntegration::DEH::RegistryCompatibility::Key::AddDefaultValue(v69, v80);
      std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v80);
      std::wstring::_Tidy_deallocate(v75);
    }
    if ( *(_QWORD *)(a1 + 280) )
    {
      v62 = 0;
      v44 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *>>::CopyTo(
              a1 + 280,
              v42,
              &v62);
      if ( v44 < 0 )
      {
        LODWORD(v58) = v44;
        wil::details::in1diag5::_FailFast_Hr(
          retaddr,
          (void *)0x8DC,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
          "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreateClsidKeyTemplateFromSharedProperties",
          "_properties.MiscStatusAspects.MapView.CopyTo( IID_PPV_ARGS(&miscStatusAspectsIterable))",
          v58,
          (int)string);
      }
      wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<_GUID,OSIntegration::DEH::ComInterfaceRegistration *> *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(
        v76,
        v62);
      v63 = v5 | 8;
      v66 = 0;
      v67 = -1;
      v68 = 0;
      while ( v77 != -1 )
      {
        v45 = *(__int64 **)wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *,wil::err_exception_policy>::iterable_iterator::operator*(v76);
        v65[0] = v45;
        Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(v65);
        string = 0;
        v46 = *v45;
        string = 0;
        v47 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v46 + 48))(v45, &string);
        if ( v47 < 0 )
        {
          LODWORD(v58) = v47;
          wil::details::in1diag5::Throw_Hr(
            retaddr,
            (void *)0x8E1,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
            "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreateClsidKeyTemplateFromSharedProperties",
            "miscStatusAspectKeyValuePair->get_Key(&miscStatusAspect)",
            (const char *)v58,
            (int)string);
        }
        v64 = 0;
        v48 = *v45;
        v64 = 0;
        v49 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v48 + 56))(v45, &v64);
        if ( v49 < 0 )
        {
          LODWORD(v58) = v49;
          wil::details::in1diag5::Throw_Hr(
            retaddr,
            (void *)0x8E5,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
            "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreateClsidKeyTemplateFromSharedProperties",
            "miscStatusAspectKeyValuePair->get_Value( &miscStatusAspectFlagsInspectable)",
            (const char *)v58,
            (int)string);
        }
        wil::com_ptr_t<IInspectable,wil::err_failfast_policy>::query<Windows::Foundation::IPropertyValue>(
          &v64,
          &StringRawBuffer);
        v60 = 0;
        v50 = *(_QWORD *)StringRawBuffer;
        v60 = 0;
        v51 = (*(__int64 (__fastcall **)(PCWSTR, HSTRING *))(v50 + 152))(StringRawBuffer, &v60);
        if ( v51 < 0 )
        {
          LODWORD(v58) = v51;
          wil::details::in1diag5::Throw_Hr(
            retaddr,
            (void *)0x8EC,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
            "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreateClsidKeyTemplateFromSharedProperties",
            "miscStatusAspectFlagsPropertyValue->GetString( &miscStatusAspectFlagsString)",
            (const char *)v58,
            (int)string);
        }
        v52 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
                (__int64)v74,
                &v60);
        OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData((__int64)v80, v52);
        v71 = WindowsGetStringRawBuffer(string, 0);
        OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(v78, &v71);
        OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(v69, v78, v80);
        std::wstring::_Tidy_deallocate(v78);
        std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v80);
        std::wstring::_Tidy_deallocate(v75);
        Windows::Internal::String::~String((Windows::Internal::String *)&v60);
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&StringRawBuffer);
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v64);
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(v65);
        wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *,wil::err_exception_policy>::iterable_iterator::operator++(v76);
      }
      wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<_GUID,OSIntegration::DEH::ComInterfaceRegistration *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(&v66);
      wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<_GUID,OSIntegration::DEH::ComInterfaceRegistration *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(v76);
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v62);
    }
    OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(v78, (__int64)L"MiscStatus");
    named_entries::emplace_unique<std::vector<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>,OSIntegration::DEH::RegistryCompatibility::Key>>,OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>,OSIntegration::DEH::RegistryCompatibility::Key>(
      (char *)a2 + 24,
      v78,
      v69);
    std::wstring::_Tidy_deallocate(v78);
    OSIntegration::DEH::RegistryCompatibility::Key::~Key((OSIntegration::DEH::RegistryCompatibility::Key *)v69);
  }
  if ( *(_BYTE *)(a1 + 288) )
  {
    v71 = *(PCWSTR *)(a1 + 952);
    v53 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
            (__int64)v74,
            &v71);
    OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData((__int64)v80, v53);
    OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(v78, (__int64)L"ToolBoxBitmap32");
    OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(a2, v78, v80);
    std::wstring::_Tidy_deallocate(v78);
    std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v80);
    std::wstring::_Tidy_deallocate(v75);
  }
  if ( *(_BYTE *)(a1 + 488) )
  {
    OSIntegration::DEH::RegistryCompatibility::Key::Key((OSIntegration::DEH::RegistryCompatibility::Key *)v69);
    v54 = GuidString::GuidString(v78, (GUID *)(a1 + 492));
    v55 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
            (__int64)v74,
            v54);
    OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData((__int64)v80, v55);
    OSIntegration::DEH::RegistryCompatibility::Key::AddDefaultValue(v69, v80);
    std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v80);
    std::wstring::_Tidy_deallocate(v75);
    OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(v78, (__int64)L"TypeLib");
    named_entries::emplace_unique<std::vector<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>,OSIntegration::DEH::RegistryCompatibility::Key>>,OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>,OSIntegration::DEH::RegistryCompatibility::Key>(
      (char *)a2 + 24,
      v78,
      v69);
    std::wstring::_Tidy_deallocate(v78);
    OSIntegration::DEH::RegistryCompatibility::Key::~Key((OSIntegration::DEH::RegistryCompatibility::Key *)v69);
  }
  if ( *(_BYTE *)(a1 + 512) )
  {
    OSIntegration::DEH::RegistryCompatibility::Key::Key((OSIntegration::DEH::RegistryCompatibility::Key *)v69);
    v56 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
            (__int64)v74,
            (const struct OpaqueString *)(a1 + 520));
    OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData((__int64)v80, v56);
    OSIntegration::DEH::RegistryCompatibility::Key::AddDefaultValue(v69, v80);
    std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v80);
    std::wstring::_Tidy_deallocate(v75);
    OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(v78, (__int64)L"Version");
    named_entries::emplace_unique<std::vector<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>,OSIntegration::DEH::RegistryCompatibility::Key>>,OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>,OSIntegration::DEH::RegistryCompatibility::Key>(
      (char *)a2 + 24,
      v78,
      v69);
    std::wstring::_Tidy_deallocate(v78);
    OSIntegration::DEH::RegistryCompatibility::Key::~Key((OSIntegration::DEH::RegistryCompatibility::Key *)v69);
  }
  return a2;
}

```

## disassembly

```asm
0x18006715c  mov     [rsp-8+arg_10], rbx
0x180067161  mov     [rsp-8+arg_18], rsi
0x180067166  push    rbp
0x180067167  push    rdi
0x180067168  push    r12
0x18006716a  push    r14
0x18006716c  push    r15
0x18006716e  lea     rbp, [rsp-180h]
0x180067176  sub     rsp, 280h
0x18006717d  mov     rax, cs:__security_cookie
0x180067184  xor     rax, rsp
0x180067187  mov     [rbp+1A0h+var_30], rax
0x18006718e  mov     rsi, rdx
0x180067191  mov     rdi, rcx
0x180067194  mov     [rsp+2A0h+var_230], rdx
0x180067199  xor     r12d, r12d
0x18006719c  mov     [rsp+2A0h+var_250], r12d
0x1800671a1  mov     rcx, rdx; this
0x1800671a4  call    ??0Key@RegistryCompatibility@DEH@OSIntegration@@QEAA@XZ; OSIntegration::DEH::RegistryCompatibility::Key::Key(void)
0x1800671a9  lea     r14d, [r12+1]
0x1800671ae  mov     [rsp+2A0h+var_250], r14d
0x1800671b3  cmp     [rdi+48h], r12b
0x1800671b7  jz      short loc_1800671F4
0x1800671b9  lea     rdx, [rdi+50h]
0x1800671bd  lea     rcx, [rbp+1A0h+var_208]
0x1800671c1  call    ??$?0AEBVOpaqueString@@@?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEBVOpaqueString@@@Z; OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(OpaqueString const &)
0x1800671c6  nop
0x1800671c7  mov     rdx, rax
0x1800671ca  lea     rcx, [rbp+1A0h+var_1C0]
0x1800671ce  call    ??$?0V?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@$0A@$0A@@AnyValueData@RegistryCompatibility@DEH@OSIntegration@@QEAA@$$QEAV?$StringTypeValueData@$00@Details@123@@Z; OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData(OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1> &&)
0x1800671d3  nop
0x1800671d4  lea     rdx, [rbp+1A0h+var_1C0]
0x1800671d8  mov     rcx, rsi
0x1800671db  call    ?AddDefaultValue@Key@RegistryCompatibility@DEH@OSIntegration@@QEAAX$$QEAVAnyValueData@234@@Z; OSIntegration::DEH::RegistryCompatibility::Key::AddDefaultValue(OSIntegration::DEH::RegistryCompatibility::AnyValueData &&)
0x1800671e0  nop
0x1800671e1  lea     rcx, [rbp+1A0h+var_1C0]
0x1800671e5  call    ?_Destroy@?$_Variant_base@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAAXXZ; std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(void)
0x1800671ea  nop
0x1800671eb  lea     rcx, [rbp+1A0h+var_1F8]
0x1800671ef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800671f4  mov     ebx, 3
0x1800671f9  cmp     [rdi+58h], r12b
0x1800671fd  jnz     short loc_18006720C
0x1800671ff  cmp     [rdi+2D0h], r12b
0x180067206  jz      loc_180067330
0x18006720c  lea     rcx, [rbp+1A0h+var_170]; this
0x180067210  call    ??0Key@RegistryCompatibility@DEH@OSIntegration@@QEAA@XZ; OSIntegration::DEH::RegistryCompatibility::Key::Key(void)
0x180067215  nop
0x180067216  cmp     [rdi+58h], r12b
0x18006721a  jz      short loc_180067285
0x18006721c  mov     edx, 2; unsigned int
0x180067221  lea     rcx, [rbp+1A0h+var_1D8]; this
0x180067225  call    ??0Uint32String@@QEAA@I@Z; Uint32String::Uint32String(uint)
0x18006722a  lea     rdx, [rdi+60h]
0x18006722e  lea     rcx, [rbp+1A0h+var_208]
0x180067232  call    ??$?0AEBVOpaqueString@@@?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEBVOpaqueString@@@Z; OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(OpaqueString const &)
0x180067237  nop
0x180067238  mov     rdx, rax
0x18006723b  lea     rcx, [rbp+1A0h+var_1C0]
0x18006723f  call    ??$?0V?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@$0A@$0A@@AnyValueData@RegistryCompatibility@DEH@OSIntegration@@QEAA@$$QEAV?$StringTypeValueData@$00@Details@123@@Z; OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData(OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1> &&)
0x180067244  nop
0x180067245  lea     rdx, [rbp+1A0h+var_1D8]
0x180067249  lea     rcx, [rsp+2A0h+var_228]
0x18006724e  call    ??$?0AEAVUint32HexString@@@?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEAVUint32HexString@@@Z; OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(Uint32HexString &)
0x180067253  nop
0x180067254  lea     r8, [rbp+1A0h+var_1C0]
0x180067258  lea     rdx, [rsp+2A0h+var_228]
0x18006725d  lea     rcx, [rbp+1A0h+var_170]
0x180067261  call    ?AddSubkeyWithDefaultValue@Key@RegistryCompatibility@DEH@OSIntegration@@QEAAAEAV1234@$$QEAV?$Name@$00$0BAA@$0A@@234@$$QEAVAnyValueData@234@@Z; OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> &&,OSIntegration::DEH::RegistryCompatibility::AnyValueData &&)
0x180067266  nop
0x180067267  lea     rcx, [rsp+2A0h+var_228]
0x18006726c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180067271  nop
0x180067272  lea     rcx, [rbp+1A0h+var_1C0]
0x180067276  call    ?_Destroy@?$_Variant_base@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAAXXZ; std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(void)
0x18006727b  nop
0x18006727c  lea     rcx, [rbp+1A0h+var_1F8]
0x180067280  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180067285  cmp     [rdi+2D0h], r12b
0x18006728c  jz      short loc_1800672F7
0x18006728e  mov     edx, ebx; unsigned int
0x180067290  lea     rcx, [rbp+1A0h+var_1D8]; this
0x180067294  call    ??0Uint32String@@QEAA@I@Z; Uint32String::Uint32String(uint)
0x180067299  lea     rdx, [rdi+2D8h]
0x1800672a0  lea     rcx, [rbp+1A0h+var_208]
0x1800672a4  call    ??$?0AEBVOpaqueString@@@?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEBVOpaqueString@@@Z; OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(OpaqueString const &)
0x1800672a9  nop
0x1800672aa  mov     rdx, rax
0x1800672ad  lea     rcx, [rbp+1A0h+var_1C0]
0x1800672b1  call    ??$?0V?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@$0A@$0A@@AnyValueData@RegistryCompatibility@DEH@OSIntegration@@QEAA@$$QEAV?$StringTypeValueData@$00@Details@123@@Z; OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData(OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1> &&)
0x1800672b6  nop
0x1800672b7  lea     rdx, [rbp+1A0h+var_1D8]
0x1800672bb  lea     rcx, [rsp+2A0h+var_228]
0x1800672c0  call    ??$?0AEAVUint32HexString@@@?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEAVUint32HexString@@@Z; OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(Uint32HexString &)
0x1800672c5  nop
0x1800672c6  lea     r8, [rbp+1A0h+var_1C0]
0x1800672ca  lea     rdx, [rsp+2A0h+var_228]
0x1800672cf  lea     rcx, [rbp+1A0h+var_170]
0x1800672d3  call    ?AddSubkeyWithDefaultValue@Key@RegistryCompatibility@DEH@OSIntegration@@QEAAAEAV1234@$$QEAV?$Name@$00$0BAA@$0A@@234@$$QEAVAnyValueData@234@@Z; OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> &&,OSIntegration::DEH::RegistryCompatibility::AnyValueData &&)
0x1800672d8  nop
0x1800672d9  lea     rcx, [rsp+2A0h+var_228]
0x1800672de  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800672e3  nop
0x1800672e4  lea     rcx, [rbp+1A0h+var_1C0]
0x1800672e8  call    ?_Destroy@?$_Variant_base@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAAXXZ; std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(void)
0x1800672ed  nop
0x1800672ee  lea     rcx, [rbp+1A0h+var_1F8]
0x1800672f2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800672f7  lea     rdx, ?AuxUserType@Constants@Catalog@Com@@3QBGB; "AuxUserType"
0x1800672fe  lea     rcx, [rsp+2A0h+var_228]
0x180067303  call    ??$?0AEAY0BA@$$CBG@?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEAY0BA@$$CBG@Z; OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(ushort const (&)[16])
0x180067308  nop
0x180067309  lea     rcx, [rsi+18h]
0x18006730d  lea     r8, [rbp+1A0h+var_170]
0x180067311  lea     rdx, [rsp+2A0h+var_228]
0x180067316  call    ??$emplace_unique@V?$vector@U?$pair@V?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@VKey@234@@std@@V?$allocator@U?$pair@V?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@VKey@234@@std@@@2@@std@@V?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@VKey@456@@named_entries@@YAAEA_PAEAV?$vector@U?$pair@V?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@VKey@234@@std@@V?$allocator@U?$pair@V?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@VKey@234@@std@@@2@@std@@$$QEAV?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@$$QEAVKey@456@@Z
0x18006731b  nop
0x18006731c  lea     rcx, [rsp+2A0h+var_228]
0x180067321  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180067326  nop
0x180067327  lea     rcx, [rbp+1A0h+var_170]; this
0x18006732b  call    ??1Key@RegistryCompatibility@DEH@OSIntegration@@QEAA@XZ; OSIntegration::DEH::RegistryCompatibility::Key::~Key(void)
0x180067330  cmp     [rdi+68h], r12b
0x180067334  jz      short loc_180067393
0x180067336  lea     rdx, [rdi+70h]
0x18006733a  lea     rcx, [rbp+1A0h+var_208]
0x18006733e  call    ??$?0AEBVOpaqueString@@@?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEBVOpaqueString@@@Z; OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(OpaqueString const &)
0x180067343  nop
0x180067344  mov     rdx, rax
0x180067347  lea     rcx, [rbp+1A0h+var_1C0]
0x18006734b  call    ??$?0V?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@$0A@$0A@@AnyValueData@RegistryCompatibility@DEH@OSIntegration@@QEAA@$$QEAV?$StringTypeValueData@$00@Details@123@@Z; OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData(OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1> &&)
0x180067350  nop
0x180067351  lea     rdx, ?ProgID@Constants@Catalog@Com@@3QBGB; "ProgID"
0x180067358  lea     rcx, [rsp+2A0h+var_228]
0x18006735d  call    ??$?0AEAY0BA@$$CBG@?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEAY0BA@$$CBG@Z; OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(ushort const (&)[16])
0x180067362  nop
0x180067363  lea     r8, [rbp+1A0h+var_1C0]
0x180067367  lea     rdx, [rsp+2A0h+var_228]
0x18006736c  mov     rcx, rsi
0x18006736f  call    ?AddSubkeyWithDefaultValue@Key@RegistryCompatibility@DEH@OSIntegration@@QEAAAEAV1234@$$QEAV?$Name@$00$0BAA@$0A@@234@$$QEAVAnyValueData@234@@Z; OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> &&,OSIntegration::DEH::RegistryCompatibility::AnyValueData &&)
0x180067374  nop
0x180067375  lea     rcx, [rsp+2A0h+var_228]
0x18006737a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006737f  nop
0x180067380  lea     rcx, [rbp+1A0h+var_1C0]
0x180067384  call    ?_Destroy@?$_Variant_base@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAAXXZ; std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(void)
0x180067389  nop
0x18006738a  lea     rcx, [rbp+1A0h+var_1F8]
0x18006738e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180067393  cmp     [rdi+78h], r12b
0x180067397  jz      short loc_1800673F2
0x180067399  lea     rdx, [rdi+80h]
0x1800673a0  lea     rcx, [rbp+1A0h+var_208]
0x1800673a4  call    ??$?0AEBVOpaqueString@@@?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEBVOpaqueString@@@Z; OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(OpaqueString const &)
0x1800673a9  nop
0x1800673aa  mov     rdx, rax
0x1800673ad  lea     rcx, [rbp+1A0h+var_1C0]
0x1800673b1  call    ??$?0V?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@$0A@$0A@@AnyValueData@RegistryCompatibility@DEH@OSIntegration@@QEAA@$$QEAV?$StringTypeValueData@$00@Details@123@@Z; OSIntegration::DEH::RegistryCompatibility::AnyValueData::AnyValueData(OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1> &&)
0x1800673b6  nop
0x1800673b7  lea     rcx, [rsp+2A0h+var_228]
0x1800673bc  call    ??$?0AEAY0BJ@$$CBG@?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEAY0BJ@$$CBG@Z; OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(ushort const (&)[25])
0x1800673c1  nop
0x1800673c2  lea     r8, [rbp+1A0h+var_1C0]
0x1800673c6  lea     rdx, [rsp+2A0h+var_228]
0x1800673cb  mov     rcx, rsi
0x1800673ce  call    ?AddSubkeyWithDefaultValue@Key@RegistryCompatibility@DEH@OSIntegration@@QEAAAEAV1234@$$QEAV?$Name@$00$0BAA@$0A@@234@$$QEAVAnyValueData@234@@Z; OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> &&,OSIntegration::DEH::RegistryCompatibility::AnyValueData &&)
0x1800673d3  nop
0x1800673d4  lea     rcx, [rsp+2A0h+var_228]
0x1800673d9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800673de  nop
0x1800673df  lea     rcx, [rbp+1A0h+var_1C0]
0x1800673e3  call    ?_Destroy@?$_Variant_base@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAAXXZ; std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(void)
0x1800673e8  nop
0x1800673e9  lea     rcx, [rbp+1A0h+var_1F8]
0x1800673ed  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800673f2  cmp     [rdi+8Ah], r12b
0x1800673f9  jz      short loc_180067403
0x1800673fb  mov     al, [rdi+8Bh]
0x180067401  jmp     short loc_180067406
0x180067403  mov     al, r12b
0x180067406  test    al, al
0x180067408  jz      short loc_180067434
0x18006740a  lea     rdx, ?Insertable@Constants@Catalog@Com@@3QBGB; "Insertable"
0x180067411  lea     rcx, [rsp+2A0h+var_228]
0x180067416  call    ??$?0AEAY0BA@$$CBG@?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEAY0BA@$$CBG@Z; OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(ushort const (&)[16])
0x18006741b  nop
0x18006741c  lea     rdx, [rsp+2A0h+var_228]
0x180067421  mov     rcx, rsi
0x180067424  call    ?AddEmptySubkey@Key@RegistryCompatibility@DEH@OSIntegration@@QEAAAEAV1234@$$QEAV?$Name@$00$0BAA@$0A@@234@@Z; OSIntegration::DEH::RegistryCompatibility::Key::AddEmptySubkey(OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> &&)
0x180067429  nop
0x18006742a  lea     rcx, [rsp+2A0h+var_228]
0x18006742f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180067434  lea     rcx, [rdi+90h]
0x18006743b  cmp     [rcx], r12
0x18006743e  jz      loc_1800676C2
0x180067444  mov     [rsp+2A0h+var_268], r12
0x180067449  lea     r8, [rsp+2A0h+var_268]
0x18006744e  call    ?CopyTo@?$ComPtr@U?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *>>::CopyTo(_GUID const &,void * *)
0x180067453  mov     rcx, [rbp+1A8h]; this
0x18006745a  test    eax, eax
0x18006745c  jns     short loc_180067487
0x18006745e  mov     dword ptr [rsp+2A0h+var_278], eax; wil::details *
0x180067462  lea     rax, aPropertiesImpl; "_properties.ImplementedCategories.MapVi"...
0x180067469  mov     [rsp+2A0h+var_280], rax; char *
0x18006746e  lea     r9, aOsintegrationD_85; "OSIntegration::DEH::Internal::ComClassR"...
0x180067475  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006747c  mov     edx, 853h; void *
0x180067481  call    ?_FailFast_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_FailFast_Hr(void *,uint,char const *,char const *,char const *,long)
0x180067487  lea     rdx, CATID_Control; rguid
0x18006748e  lea     rcx, [rbp+1A0h+sz]; lpsz
0x180067495  call    ??0GuidString@@QEAA@AEBU_GUID@@@Z; GuidString::GuidString(_GUID const &)
0x18006749a  lea     rdx, CATID_Programmable; rguid
0x1800674a1  lea     rcx, [rbp+1A0h+var_80]; lpsz
0x1800674a8  call    ??0GuidString@@QEAA@AEBU_GUID@@@Z; GuidString::GuidString(_GUID const &)
0x1800674ad  lea     rcx, [rbp+1A0h+var_208]; this
0x1800674b1  call    ??0Key@RegistryCompatibility@DEH@OSIntegration@@QEAA@XZ; OSIntegration::DEH::RegistryCompatibility::Key::Key(void)
0x1800674b6  nop
0x1800674b7  mov     rdx, [rsp+2A0h+var_268]
0x1800674bc  lea     rcx, [rbp+1A0h+var_188]
0x1800674c0  call    ??0iterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@U_GUID@@PEAVComInterfaceRegistration@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAU?$IIterable@PEAU?$IKeyValuePair@U_GUID@@PEAVComInterfaceRegistration@DEH@OSIntegration@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@Z; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<_GUID,OSIntegration::DEH::ComInterfaceRegistration *> *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<_GUID,OSIntegration::DEH::ComInterfaceRegistration *> *> *)
0x1800674c5  mov     r14d, ebx
0x1800674c8  mov     [rsp+2A0h+var_250], ebx
0x1800674cc  mov     [rbp+1A0h+var_1D8], r12
0x1800674d0  mov     [rbp+1A0h+var_1D0], 0FFFFFFFFh
0x1800674d7  mov     [rbp+1A0h+var_1C8], r12
0x1800674db  cmp     [rbp+1A0h+var_180], 0FFFFFFFFh
0x1800674df  jz      loc_180067672
0x1800674e5  lea     rcx, [rbp+1A0h+var_188]
0x1800674e9  call    ??Diterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@U?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *,wil::err_exception_policy>::iterable_iterator::operator*(void)
0x1800674ee  mov     rbx, [rax]
0x1800674f1  mov     [rsp+2A0h+var_258], rbx
0x1800674f6  lea     rcx, [rsp+2A0h+var_258]
0x1800674fb  call    ?InternalAddRef@?$ComPtr@VExtensionCatalogCollector@DEH@OSIntegration@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(void)
0x180067500  nop
0x180067501  mov     [rsp+2A0h+string], r12
0x180067506  mov     rax, [rbx]
0x180067509  mov     [rsp+2A0h+string], r12; int
0x18006750e  lea     rdx, [rsp+2A0h+string]
0x180067513  mov     rcx, rbx
0x180067516  mov     rax, [rax+30h]
0x18006751a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006751f  mov     rcx, [rbp+1A8h]; this
0x180067526  test    eax, eax
0x180067528  js      loc_180067649
0x18006752e  xor     edx, edx; length
0x180067530  mov     rcx, [rsp+2A0h+string]; string
0x180067535  call    cs:__imp_WindowsGetStringRawBuffer
0x18006753c  nop     dword ptr [rax+rax+00h]
0x180067541  mov     [rsp+2A0h+var_260], rax
0x180067546  lea     rdx, [rsp+2A0h+var_260]
0x18006754b  lea     rcx, [rsp+2A0h+var_228]
0x180067550  call    ??$?0PEBG@?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@QEAA@$$QEAPEBG@Z; OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(ushort const * &&)
0x180067555  nop
0x180067556  lea     rdx, [rsp+2A0h+var_228]
0x18006755b  lea     rcx, [rbp+1A0h+var_208]
0x18006755f  call    ?AddEmptySubkey@Key@RegistryCompatibility@DEH@OSIntegration@@QEAAAEAV1234@$$QEAV?$Name@$00$0BAA@$0A@@234@@Z; OSIntegration::DEH::RegistryCompatibility::Key::AddEmptySubkey(OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> &&)
0x180067564  nop
0x180067565  lea     rcx, [rsp+2A0h+var_228]
0x18006756a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006756f  xor     edx, edx; length
0x180067571  mov     rcx, [rsp+2A0h+string]; string
0x180067576  call    cs:__imp_WindowsGetStringRawBuffer
0x18006757d  nop     dword ptr [rax+rax+00h]
0x180067582  lea     r8, [rbp+1A0h+sz]
0x180067589  sub     r8, rax
0x18006758c  movzx   ecx, word ptr [rax]
0x18006758f  movzx   edx, word ptr [rax+r8]
0x180067594  sub     ecx, edx
0x180067596  jnz     short loc_1800675A0
0x180067598  add     rax, 2
0x18006759c  test    edx, edx
0x18006759e  jnz     short loc_18006758C
0x1800675a0  test    ecx, ecx
0x1800675a2  jnz     short loc_1800675C6
0x1800675a4  lea     rdx, ?Control@Constants@Catalog@Com@@3QBGB; "Control"
0x1800675ab  lea     rcx, [rsp+2A0h+var_228]
0x1800675b0  call    ??$?0AEAY0BA@$$CBG@?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEAY0BA@$$CBG@Z; OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(ushort const (&)[16])
0x1800675b5  nop
0x1800675b6  lea     rdx, [rsp+2A0h+var_228]
0x1800675bb  mov     rcx, rsi
0x1800675be  call    ?AddEmptySubkey@Key@RegistryCompatibility@DEH@OSIntegration@@QEAAAEAV1234@$$QEAV?$Name@$00$0BAA@$0A@@234@@Z; OSIntegration::DEH::RegistryCompatibility::Key::AddEmptySubkey(OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> &&)
0x1800675c3  nop
0x1800675c4  jmp     short loc_18006761B
0x1800675c6  xor     edx, edx; length
0x1800675c8  mov     rcx, [rsp+2A0h+string]; string
0x1800675cd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800675d4  nop     dword ptr [rax+rax+00h]
0x1800675d9  lea     r8, [rbp+1A0h+var_80]
0x1800675e0  sub     r8, rax
0x1800675e3  movzx   ecx, word ptr [rax]
0x1800675e6  movzx   edx, word ptr [rax+r8]
0x1800675eb  sub     ecx, edx
0x1800675ed  jnz     short loc_1800675F7
0x1800675ef  add     rax, 2
0x1800675f3  test    edx, edx
0x1800675f5  jnz     short loc_1800675E3
0x1800675f7  test    ecx, ecx
0x1800675f9  jnz     short loc_180067626
0x1800675fb  lea     rdx, ?Programmable@Constants@Catalog@Com@@3QBGB; "Programmable"
0x180067602  lea     rcx, [rsp+2A0h+var_228]
  ... truncated ...
```
