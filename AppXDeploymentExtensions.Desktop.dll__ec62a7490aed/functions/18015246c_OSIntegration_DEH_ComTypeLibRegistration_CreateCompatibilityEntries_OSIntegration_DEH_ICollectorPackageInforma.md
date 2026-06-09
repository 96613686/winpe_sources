# OSIntegration::DEH::ComTypeLibRegistration::CreateCompatibilityEntries(OSIntegration::DEH::ICollectorPackageInformation const *)

- ea: `0x18015246c`
- end: `0x180152a6c`
- name: `?CreateCompatibilityEntries@ComTypeLibRegistration@DEH@OSIntegration@@AEBAJPEBUICollectorPackageInformation@23@@Z`
- size: `1536`
- prototype: `__int64 __fastcall(OSIntegration::DEH::ComTypeLibRegistration *__hidden this, const struct OSIntegration::DEH::ICollectorPackageInformation *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18015fae0`

## callees

- `0x180048cd4`
- `0x180056bd4`
- `0x180059424`
- `0x180066780`
- `0x180066938`
- `0x1800669b0`
- `0x180078760`
- `0x180078784`
- `0x180078818`
- `0x18009f800`
- `0x1800aed10`
- `0x1800db594`
- `0x1800f6e48`
- `0x1800f74bc`
- `0x1801058d0`
- `0x180142930`
- `0x18014b51c`
- `0x18014e284`
- `0x18015246c`
- `0x180158f78`
- `0x18015a6a4`
- `0x180169c98`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015259e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180152681`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015283e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180152908`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015259e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180152681`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015283e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180152908`

## string_xrefs

- `0x1801529de`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x180152a07`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x180152a30`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x180152a59`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x1801529d7`: `OSIntegration::DEH::ComTypeLibRegistration::CreateCompatibilityEntries`
- `0x180152a00`: `OSIntegration::DEH::ComTypeLibRegistration::CreateCompatibilityEntries`
- `0x180152a29`: `OSIntegration::DEH::ComTypeLibRegistration::CreateCompatibilityEntries`
- `0x180152a52`: `OSIntegration::DEH::ComTypeLibRegistration::CreateCompatibilityEntries`
- `0x1801529cb`: `Internal::GetPackagedFileAbsolutePath(incomingPackage, _properties.Win32Path.Value.GetRawBuffer(nullptr), absolutePath)`
- `0x180152a1d`: `Internal::GetPackagedFileAbsolutePath(incomingPackage, _properties.HelpDirectory.Value.GetRawBuffer(nullptr), absolutePath)`
- `0x1801529f4`: `Internal::GetPackagedFileAbsolutePath(incomingPackage, _properties.Win64Path.Value.GetRawBuffer(nullptr), absolutePath)`
- `0x180152a46`: `registryCompatibilityCollector->AddKey( (_properties.HasMachineScope.GetValueOrDefault(false) ? Scope::Machine : Scope::User), Internal::GetTypeLibVersionKeyPath(_id, _versionNumber.GetRawBuffer(nullptr)), std::move(typeLibVersionKey))`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall OSIntegration::DEH::ComTypeLibRegistration::CreateCompatibilityEntries(
        OSIntegration::DEH::ComTypeLibRegistration *this,
        const struct OSIntegration::DEH::ICollectorPackageInformation *a2)
{
  __int64 result; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rdx
  unsigned int v8; // edx
  PCWSTR StringRawBuffer; // rax
  int PackagedFileAbsolutePath; // eax
  __int64 v11; // rax
  __int64 v12; // rdx
  PCWSTR v13; // rax
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rdx
  PCWSTR v19; // rax
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rdx
  _QWORD *v23; // rdi
  __int64 v24; // rsi
  PCWSTR v25; // rax
  __int64 TypeLibVersionKeyPath; // rax
  char v27; // cl
  int v28; // eax
  char *v29; // [rsp+20h] [rbp-188h]
  char *v30; // [rsp+28h] [rbp-180h]
  char *v31; // [rsp+28h] [rbp-180h]
  int v32[2]; // [rsp+30h] [rbp-178h] BYREF
  _BYTE *v33; // [rsp+38h] [rbp-170h] BYREF
  _QWORD *v34; // [rsp+40h] [rbp-168h] BYREF
  _BYTE v35[24]; // [rsp+48h] [rbp-160h] BYREF
  _BYTE v36[24]; // [rsp+60h] [rbp-148h] BYREF
  _BYTE v37[48]; // [rsp+78h] [rbp-130h] BYREF
  char v38; // [rsp+A8h] [rbp-100h]
  _BYTE v39[48]; // [rsp+B0h] [rbp-F8h] BYREF
  _BYTE v40[32]; // [rsp+E0h] [rbp-C8h] BYREF
  _BYTE v41[16]; // [rsp+100h] [rbp-A8h] BYREF
  _BYTE v42[32]; // [rsp+110h] [rbp-98h] BYREF
  _BYTE v43[16]; // [rsp+130h] [rbp-78h] BYREF
  _BYTE v44[32]; // [rsp+140h] [rbp-68h] BYREF
  char v45; // [rsp+160h] [rbp-48h]
  _BYTE v46[24]; // [rsp+168h] [rbp-40h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+1A8h] [rbp+0h]

  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
      && *((_BYTE *)this + 180)
      && *((_DWORD *)this + 46) )
    {
      result = 0;
    }
    else
    {
      if ( *((_BYTE *)this + 208) )
      {
        v5 = (*(__int64 (__fastcall **)(const struct OSIntegration::DEH::ICollectorPackageInformation *))(*(_QWORD *)a2 + 72LL))(a2);
        wil::com_ptr_t<IXMLDOMElement,wil::err_exception_policy>::com_ptr_t<IXMLDOMElement,wil::err_exception_policy>(
          &v34,
          *(_QWORD *)(v5 + 72));
        OSIntegration::DEH::RegistryCompatibility::Key::Key((OSIntegration::DEH::RegistryCompatibility::Key *)v35);
        if ( *((_BYTE *)this + 128) )
        {
          v6 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
                 v41,
                 (char *)this + 136);
          std::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>(
            v43,
            v7,
            v6);
          v45 = 5;
          OSIntegration::DEH::RegistryCompatibility::Key::AddDefaultValue(v35, v43);
          std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v43);
          std::wstring::_Tidy_deallocate(v42);
        }
        if ( *((_BYTE *)this + 96) )
          v8 = *((_DWORD *)this + 25);
        else
          v8 = 0;
        Uint32HexString::Uint32HexString((Uint32HexString *)v46, v8);
        OSIntegration::DEH::RegistryCompatibility::Key::Key((OSIntegration::DEH::RegistryCompatibility::Key *)v39);
        if ( *((_BYTE *)this + 144) )
        {
          *(_QWORD *)v32 = 0;
          StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 19), 0);
          PackagedFileAbsolutePath = OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(a2, StringRawBuffer, v32);
          if ( PackagedFileAbsolutePath < 0 )
          {
            LODWORD(v31) = PackagedFileAbsolutePath;
            wil::details::in1diag5::Throw_Hr(
              retaddr,
              (void *)0x1213,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
              "OSIntegration::DEH::ComTypeLibRegistration::CreateCompatibilityEntries",
              "Internal::GetPackagedFileAbsolutePath(incomingPackage, _properties.Win32Path.Value.GetRawBuffer(nullptr), absolutePath)",
              v31,
              v32[0]);
          }
          v33 = *(_BYTE **)v32;
          v11 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
                  v41,
                  &v33);
          std::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>(
            v43,
            v12,
            v11);
          v45 = 5;
          OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(v40, L"win32");
          OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(v39, v40, v43);
          std::wstring::_Tidy_deallocate(v40);
          std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v43);
          std::wstring::_Tidy_deallocate(v42);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v32);
        }
        if ( *((_BYTE *)this + 160) )
        {
          *(_QWORD *)v32 = 0;
          v13 = WindowsGetStringRawBuffer(*((HSTRING *)this + 21), 0);
          v14 = OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(a2, v13, v32);
          if ( v14 < 0 )
          {
            LODWORD(v31) = v14;
            wil::details::in1diag5::Throw_Hr(
              retaddr,
              (void *)0x121E,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
              "OSIntegration::DEH::ComTypeLibRegistration::CreateCompatibilityEntries",
              "Internal::GetPackagedFileAbsolutePath(incomingPackage, _properties.Win64Path.Value.GetRawBuffer(nullptr), absolutePath)",
              v31,
              v32[0]);
          }
          v33 = *(_BYTE **)v32;
          v15 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
                  v41,
                  &v33);
          std::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>(
            v43,
            v16,
            v15);
          v45 = 5;
          OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(v40, L"win64");
          OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(v39, v40, v43);
          std::wstring::_Tidy_deallocate(v40);
          std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v43);
          std::wstring::_Tidy_deallocate(v42);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v32);
        }
        OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(v40, v46);
        named_entries::emplace_unique<std::vector<std::pair<OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>,OSIntegration::DEH::RegistryCompatibility::Key>>,OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>,OSIntegration::DEH::RegistryCompatibility::Key>(
          v36,
          v40,
          v39);
        std::wstring::_Tidy_deallocate(v40);
        if ( *((_BYTE *)this + 104) )
        {
          Uint32HexString::Uint32HexString((Uint32HexString *)v40, *((_DWORD *)this + 27));
          v33 = v40;
          v17 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
                  v43,
                  &v33);
          std::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>(
            v37,
            v18,
            v17);
          v38 = 5;
          OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(v41, L"FLAGS");
          OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(v35, v41, v37);
          std::wstring::_Tidy_deallocate(v41);
          std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v37);
          std::wstring::_Tidy_deallocate(v44);
        }
        if ( *((_BYTE *)this + 112) )
        {
          *(_QWORD *)v32 = 0;
          v19 = WindowsGetStringRawBuffer(*((HSTRING *)this + 15), 0);
          v20 = OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(a2, v19, v32);
          if ( v20 < 0 )
          {
            LODWORD(v31) = v20;
            wil::details::in1diag5::Throw_Hr(
              retaddr,
              (void *)0x1235,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
              "OSIntegration::DEH::ComTypeLibRegistration::CreateCompatibilityEntries",
              "Internal::GetPackagedFileAbsolutePath(incomingPackage, _properties.HelpDirectory.Value.GetRawBuffer(nullpt"
              "r), absolutePath)",
              v31,
              v32[0]);
          }
          v33 = *(_BYTE **)v32;
          v21 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
                  v43,
                  &v33);
          std::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>(
            v37,
            v22,
            v21);
          v38 = 5;
          OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(v41, L"HELPDIR");
          OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(v35, v41, v37);
          std::wstring::_Tidy_deallocate(v41);
          std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v37);
          std::wstring::_Tidy_deallocate(v44);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v32);
        }
        v23 = v34;
        v24 = *v34;
        v25 = WindowsGetStringRawBuffer(*((HSTRING *)this + 11), 0);
        TypeLibVersionKeyPath = OSIntegration::DEH::Internal::GetTypeLibVersionKeyPath(v41, (char *)this + 72, v25);
        if ( *((_BYTE *)this + 176) )
          v27 = *((_BYTE *)this + 177);
        else
          v27 = 0;
        v28 = (*(__int64 (__fastcall **)(_QWORD *, bool, __int64, _BYTE *))(v24 + 48))(
                v23,
                v27 == 0,
                TypeLibVersionKeyPath,
                v35);
        if ( v28 < 0 )
        {
          LODWORD(v31) = v28;
          wil::details::in1diag5::Throw_Hr(
            retaddr,
            (void *)0x123E,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
            "OSIntegration::DEH::ComTypeLibRegistration::CreateCompatibilityEntries",
            "registryCompatibilityCollector->AddKey( (_properties.HasMachineScope.GetValueOrDefault(false) ? Scope::Machi"
            "ne : Scope::User), Internal::GetTypeLibVersionKeyPath(_id, _versionNumber.GetRawBuffer(nullptr)), std::move("
            "typeLibVersionKey))",
            v31,
            v32[0]);
        }
        std::wstring::_Tidy_deallocate(v41);
        OSIntegration::DEH::RegistryCompatibility::Key::~Key((OSIntegration::DEH::RegistryCompatibility::Key *)v39);
        OSIntegration::DEH::RegistryCompatibility::Key::~Key((OSIntegration::DEH::RegistryCompatibility::Key *)v35);
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v34);
      }
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag5::Return_CaughtException(
                           retaddr,
                           (void *)0x1242,
                           (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
                           "OSIntegration::DEH::ComTypeLibRegistration::CreateCompatibilityEntries",
                           v29,
                           v30);
  }
  return result;
}

```

## disassembly

```asm
0x18015246c  mov     [rsp+arg_10], rbx
0x180152471  push    rsi
0x180152472  push    rdi
0x180152473  push    r14
0x180152475  sub     rsp, 190h
0x18015247c  mov     rax, cs:__security_cookie
0x180152483  xor     rax, rsp
0x180152486  mov     [rsp+1A8h+var_28], rax
0x18015248e  mov     rdi, rdx
0x180152491  mov     rbx, rcx
0x180152494  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18015249b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1801524a0  xor     r14d, r14d
0x1801524a3  test    al, al
0x1801524a5  jz      short loc_1801524C0
0x1801524a7  cmp     [rbx+0B4h], r14b
0x1801524ae  jz      short loc_1801524C0
0x1801524b0  cmp     [rbx+0B8h], r14d
0x1801524b7  jz      short loc_1801524C0
0x1801524b9  xor     eax, eax
0x1801524bb  jmp     loc_1801529A2
0x1801524c0  cmp     [rbx+0D0h], r14b
0x1801524c7  jz      loc_18015299A
0x1801524cd  mov     rax, [rdi]
0x1801524d0  mov     rcx, rdi
0x1801524d3  mov     rax, [rax+48h]
0x1801524d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801524dc  mov     rdx, [rax+48h]
0x1801524e0  lea     rcx, [rsp+1A8h+var_168]
0x1801524e5  call    ??0?$com_ptr_t@UIXMLDOMElement@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIXMLDOMElement@@@Z; wil::com_ptr_t<IXMLDOMElement,wil::err_exception_policy>::com_ptr_t<IXMLDOMElement,wil::err_exception_policy>(IXMLDOMElement *)
0x1801524ea  nop
0x1801524eb  lea     rcx, [rsp+1A8h+var_160]; this
0x1801524f0  call    ??0Key@RegistryCompatibility@DEH@OSIntegration@@QEAA@XZ; OSIntegration::DEH::RegistryCompatibility::Key::Key(void)
0x1801524f5  nop
0x1801524f6  cmp     [rbx+80h], r14b
0x1801524fd  jz      short loc_18015255A
0x1801524ff  lea     rdx, [rbx+88h]
0x180152506  lea     rcx, [rsp+1A8h+var_A8]
0x18015250e  call    ??$?0AEBVOpaqueString@@@?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEBVOpaqueString@@@Z; OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(OpaqueString const &)
0x180152513  nop
0x180152514  mov     r8, rax
0x180152517  lea     rcx, [rsp+1A8h+var_78]
0x18015251f  call    ??$?0$04V?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@$0A@@?$_Variant_storage_@$0A@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAA@U?$integral_constant@_K$04@1@$$QEAV?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@@Z; std::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>(std::integral_constant<unsigned __int64,5>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1> &&)
0x180152524  mov     [rsp+1A8h+var_48], 5
0x18015252c  lea     rdx, [rsp+1A8h+var_78]
0x180152534  lea     rcx, [rsp+1A8h+var_160]
0x180152539  call    ?AddDefaultValue@Key@RegistryCompatibility@DEH@OSIntegration@@QEAAX$$QEAVAnyValueData@234@@Z; OSIntegration::DEH::RegistryCompatibility::Key::AddDefaultValue(OSIntegration::DEH::RegistryCompatibility::AnyValueData &&)
0x18015253e  nop
0x18015253f  lea     rcx, [rsp+1A8h+var_78]
0x180152547  call    ?_Destroy@?$_Variant_base@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAAXXZ; std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(void)
0x18015254c  nop
0x18015254d  lea     rcx, [rsp+1A8h+var_98]
0x180152555  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18015255a  cmp     [rbx+60h], r14b
0x18015255e  jz      short loc_180152565
0x180152560  mov     edx, [rbx+64h]
0x180152563  jmp     short loc_180152568
0x180152565  mov     edx, r14d; unsigned int
0x180152568  lea     rcx, [rsp+1A8h+var_40]; this
0x180152570  call    ??0Uint32HexString@@QEAA@I@Z; Uint32HexString::Uint32HexString(uint)
0x180152575  lea     rcx, [rsp+1A8h+var_F8]; this
0x18015257d  call    ??0Key@RegistryCompatibility@DEH@OSIntegration@@QEAA@XZ; OSIntegration::DEH::RegistryCompatibility::Key::Key(void)
0x180152582  nop
0x180152583  cmp     [rbx+90h], r14b
0x18015258a  jz      loc_180152666
0x180152590  mov     qword ptr [rsp+1A8h+var_178], r14; int
0x180152595  xor     edx, edx; length
0x180152597  mov     rcx, [rbx+98h]; string
0x18015259e  call    cs:__imp_WindowsGetStringRawBuffer
0x1801525a5  nop     dword ptr [rax+rax+00h]
0x1801525aa  lea     r8, [rsp+1A8h+var_178]
0x1801525af  mov     rdx, rax
0x1801525b2  mov     rcx, rdi
0x1801525b5  call    ?GetPackagedFileAbsolutePath@Internal@DEH@OSIntegration@@YAJPEBUICollectorPackageInformation@23@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(OSIntegration::DEH::ICollectorPackageInformation const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1801525ba  mov     rcx, [rsp+1A8h]; this
0x1801525c2  test    eax, eax
0x1801525c4  js      loc_1801529C7
0x1801525ca  mov     rax, qword ptr [rsp+1A8h+var_178]
0x1801525cf  mov     [rsp+1A8h+var_170], rax
0x1801525d4  lea     rdx, [rsp+1A8h+var_170]
0x1801525d9  lea     rcx, [rsp+1A8h+var_A8]
0x1801525e1  call    ??$?0PEBG@?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@QEAA@$$QEAPEBG@Z; OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(ushort const * &&)
0x1801525e6  nop
0x1801525e7  mov     r8, rax
0x1801525ea  lea     rcx, [rsp+1A8h+var_78]
0x1801525f2  call    ??$?0$04V?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@$0A@@?$_Variant_storage_@$0A@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAA@U?$integral_constant@_K$04@1@$$QEAV?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@@Z; std::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>(std::integral_constant<unsigned __int64,5>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1> &&)
0x1801525f7  mov     [rsp+1A8h+var_48], 5
0x1801525ff  lea     rdx, ?win32@Constants@Catalog@Com@@3QBGB; "win32"
0x180152606  lea     rcx, [rsp+1A8h+var_C8]
0x18015260e  call    ??$?0AEAY0BA@$$CBG@?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEAY0BA@$$CBG@Z; OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(ushort const (&)[16])
0x180152613  nop
0x180152614  lea     r8, [rsp+1A8h+var_78]
0x18015261c  lea     rdx, [rsp+1A8h+var_C8]
0x180152624  lea     rcx, [rsp+1A8h+var_F8]
0x18015262c  call    ?AddSubkeyWithDefaultValue@Key@RegistryCompatibility@DEH@OSIntegration@@QEAAAEAV1234@$$QEAV?$Name@$00$0BAA@$0A@@234@$$QEAVAnyValueData@234@@Z; OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> &&,OSIntegration::DEH::RegistryCompatibility::AnyValueData &&)
0x180152631  nop
0x180152632  lea     rcx, [rsp+1A8h+var_C8]
0x18015263a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18015263f  nop
0x180152640  lea     rcx, [rsp+1A8h+var_78]
0x180152648  call    ?_Destroy@?$_Variant_base@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAAXXZ; std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(void)
0x18015264d  nop
0x18015264e  lea     rcx, [rsp+1A8h+var_98]
0x180152656  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18015265b  nop
0x18015265c  lea     rcx, [rsp+1A8h+var_178]
0x180152661  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180152666  cmp     [rbx+0A0h], r14b
0x18015266d  jz      loc_180152749
0x180152673  mov     qword ptr [rsp+1A8h+var_178], r14; int
0x180152678  xor     edx, edx; length
0x18015267a  mov     rcx, [rbx+0A8h]; string
0x180152681  call    cs:__imp_WindowsGetStringRawBuffer
0x180152688  nop     dword ptr [rax+rax+00h]
0x18015268d  lea     r8, [rsp+1A8h+var_178]
0x180152692  mov     rdx, rax
0x180152695  mov     rcx, rdi
0x180152698  call    ?GetPackagedFileAbsolutePath@Internal@DEH@OSIntegration@@YAJPEBUICollectorPackageInformation@23@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(OSIntegration::DEH::ICollectorPackageInformation const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18015269d  mov     rcx, [rsp+1A8h]; this
0x1801526a5  test    eax, eax
0x1801526a7  js      loc_1801529F0
0x1801526ad  mov     rax, qword ptr [rsp+1A8h+var_178]
0x1801526b2  mov     [rsp+1A8h+var_170], rax
0x1801526b7  lea     rdx, [rsp+1A8h+var_170]
0x1801526bc  lea     rcx, [rsp+1A8h+var_A8]
0x1801526c4  call    ??$?0PEBG@?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@QEAA@$$QEAPEBG@Z; OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(ushort const * &&)
0x1801526c9  nop
0x1801526ca  mov     r8, rax
0x1801526cd  lea     rcx, [rsp+1A8h+var_78]
0x1801526d5  call    ??$?0$04V?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@$0A@@?$_Variant_storage_@$0A@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAA@U?$integral_constant@_K$04@1@$$QEAV?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@@Z; std::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>(std::integral_constant<unsigned __int64,5>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1> &&)
0x1801526da  mov     [rsp+1A8h+var_48], 5
0x1801526e2  lea     rdx, ?win64@Constants@Catalog@Com@@3QBGB; "win64"
0x1801526e9  lea     rcx, [rsp+1A8h+var_C8]
0x1801526f1  call    ??$?0AEAY0BA@$$CBG@?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEAY0BA@$$CBG@Z; OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(ushort const (&)[16])
0x1801526f6  nop
0x1801526f7  lea     r8, [rsp+1A8h+var_78]
0x1801526ff  lea     rdx, [rsp+1A8h+var_C8]
0x180152707  lea     rcx, [rsp+1A8h+var_F8]
0x18015270f  call    ?AddSubkeyWithDefaultValue@Key@RegistryCompatibility@DEH@OSIntegration@@QEAAAEAV1234@$$QEAV?$Name@$00$0BAA@$0A@@234@$$QEAVAnyValueData@234@@Z; OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> &&,OSIntegration::DEH::RegistryCompatibility::AnyValueData &&)
0x180152714  nop
0x180152715  lea     rcx, [rsp+1A8h+var_C8]
0x18015271d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180152722  nop
0x180152723  lea     rcx, [rsp+1A8h+var_78]
0x18015272b  call    ?_Destroy@?$_Variant_base@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAAXXZ; std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(void)
0x180152730  nop
0x180152731  lea     rcx, [rsp+1A8h+var_98]
0x180152739  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18015273e  nop
0x18015273f  lea     rcx, [rsp+1A8h+var_178]
0x180152744  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180152749  lea     rdx, [rsp+1A8h+var_40]
0x180152751  lea     rcx, [rsp+1A8h+var_C8]
0x180152759  call    ??$?0AEAVUint32HexString@@@?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEAVUint32HexString@@@Z; OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(Uint32HexString &)
0x18015275e  nop
0x18015275f  lea     r8, [rsp+1A8h+var_F8]
0x180152767  lea     rdx, [rsp+1A8h+var_C8]
0x18015276f  lea     rcx, [rsp+1A8h+var_148]
0x180152774  call    ??$emplace_unique@V?$vector@U?$pair@V?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@VKey@234@@std@@V?$allocator@U?$pair@V?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@VKey@234@@std@@@2@@std@@V?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@VKey@456@@named_entries@@YAAEA_PAEAV?$vector@U?$pair@V?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@VKey@234@@std@@V?$allocator@U?$pair@V?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@VKey@234@@std@@@2@@std@@$$QEAV?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@$$QEAVKey@456@@Z
0x180152779  nop
0x18015277a  lea     rcx, [rsp+1A8h+var_C8]
0x180152782  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180152787  cmp     [rbx+68h], r14b
0x18015278b  jz      loc_180152829
0x180152791  mov     edx, [rbx+6Ch]; unsigned int
0x180152794  lea     rcx, [rsp+1A8h+var_C8]; this
0x18015279c  call    ??0Uint32HexString@@QEAA@I@Z; Uint32HexString::Uint32HexString(uint)
0x1801527a1  lea     rax, [rsp+1A8h+var_C8]
0x1801527a9  mov     [rsp+1A8h+var_170], rax
0x1801527ae  lea     rdx, [rsp+1A8h+var_170]
0x1801527b3  lea     rcx, [rsp+1A8h+var_78]
0x1801527bb  call    ??$?0PEBG@?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@QEAA@$$QEAPEBG@Z; OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(ushort const * &&)
0x1801527c0  nop
0x1801527c1  mov     r8, rax
0x1801527c4  lea     rcx, [rsp+1A8h+var_130]
0x1801527c9  call    ??$?0$04V?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@$0A@@?$_Variant_storage_@$0A@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAA@U?$integral_constant@_K$04@1@$$QEAV?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@@Z; std::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>(std::integral_constant<unsigned __int64,5>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1> &&)
0x1801527ce  mov     [rsp+1A8h+var_100], 5
0x1801527d6  lea     rdx, ?FLAGS@Constants@Catalog@Com@@3QBGB; "FLAGS"
0x1801527dd  lea     rcx, [rsp+1A8h+var_A8]
0x1801527e5  call    ??$?0AEAY0BA@$$CBG@?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEAY0BA@$$CBG@Z; OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(ushort const (&)[16])
0x1801527ea  nop
0x1801527eb  lea     r8, [rsp+1A8h+var_130]
0x1801527f0  lea     rdx, [rsp+1A8h+var_A8]
0x1801527f8  lea     rcx, [rsp+1A8h+var_160]
0x1801527fd  call    ?AddSubkeyWithDefaultValue@Key@RegistryCompatibility@DEH@OSIntegration@@QEAAAEAV1234@$$QEAV?$Name@$00$0BAA@$0A@@234@$$QEAVAnyValueData@234@@Z; OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> &&,OSIntegration::DEH::RegistryCompatibility::AnyValueData &&)
0x180152802  nop
0x180152803  lea     rcx, [rsp+1A8h+var_A8]
0x18015280b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180152810  nop
0x180152811  lea     rcx, [rsp+1A8h+var_130]
0x180152816  call    ?_Destroy@?$_Variant_base@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAAXXZ; std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(void)
0x18015281b  nop
0x18015281c  lea     rcx, [rsp+1A8h+var_68]
0x180152824  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180152829  cmp     [rbx+70h], r14b
0x18015282d  jz      loc_1801528FA
0x180152833  mov     qword ptr [rsp+1A8h+var_178], r14; int
0x180152838  xor     edx, edx; length
0x18015283a  mov     rcx, [rbx+78h]; string
0x18015283e  call    cs:__imp_WindowsGetStringRawBuffer
0x180152845  nop     dword ptr [rax+rax+00h]
0x18015284a  lea     r8, [rsp+1A8h+var_178]
0x18015284f  mov     rdx, rax
0x180152852  mov     rcx, rdi
0x180152855  call    ?GetPackagedFileAbsolutePath@Internal@DEH@OSIntegration@@YAJPEBUICollectorPackageInformation@23@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(OSIntegration::DEH::ICollectorPackageInformation const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18015285a  mov     rcx, [rsp+1A8h]; this
0x180152862  test    eax, eax
0x180152864  js      loc_180152A19
0x18015286a  mov     rax, qword ptr [rsp+1A8h+var_178]
0x18015286f  mov     [rsp+1A8h+var_170], rax
0x180152874  lea     rdx, [rsp+1A8h+var_170]
0x180152879  lea     rcx, [rsp+1A8h+var_78]
0x180152881  call    ??$?0PEBG@?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@QEAA@$$QEAPEBG@Z; OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(ushort const * &&)
0x180152886  nop
0x180152887  mov     r8, rax
0x18015288a  lea     rcx, [rsp+1A8h+var_130]
0x18015288f  call    ??$?0$04V?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@$0A@@?$_Variant_storage_@$0A@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAA@U?$integral_constant@_K$04@1@$$QEAV?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@@Z; std::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>(std::integral_constant<unsigned __int64,5>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1> &&)
0x180152894  mov     [rsp+1A8h+var_100], 5
0x18015289c  lea     rdx, ?HELPDIR@Constants@Catalog@Com@@3QBGB; "HELPDIR"
0x1801528a3  lea     rcx, [rsp+1A8h+var_A8]
0x1801528ab  call    ??$?0AEAY0BA@$$CBG@?$Name@$00$0BAA@$0A@@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEAY0BA@$$CBG@Z; OSIntegration::DEH::RegistryCompatibility::Name<1,256,0>::Name<1,256,0>(ushort const (&)[16])
0x1801528b0  nop
0x1801528b1  lea     r8, [rsp+1A8h+var_130]
0x1801528b6  lea     rdx, [rsp+1A8h+var_A8]
0x1801528be  lea     rcx, [rsp+1A8h+var_160]
0x1801528c3  call    ?AddSubkeyWithDefaultValue@Key@RegistryCompatibility@DEH@OSIntegration@@QEAAAEAV1234@$$QEAV?$Name@$00$0BAA@$0A@@234@$$QEAVAnyValueData@234@@Z; OSIntegration::DEH::RegistryCompatibility::Key::AddSubkeyWithDefaultValue(OSIntegration::DEH::RegistryCompatibility::Name<1,256,0> &&,OSIntegration::DEH::RegistryCompatibility::AnyValueData &&)
0x1801528c8  nop
0x1801528c9  lea     rcx, [rsp+1A8h+var_A8]
0x1801528d1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801528d6  nop
0x1801528d7  lea     rcx, [rsp+1A8h+var_130]
0x1801528dc  call    ?_Destroy@?$_Variant_base@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAAXXZ; std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(void)
0x1801528e1  nop
0x1801528e2  lea     rcx, [rsp+1A8h+var_68]
0x1801528ea  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801528ef  nop
0x1801528f0  lea     rcx, [rsp+1A8h+var_178]
0x1801528f5  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1801528fa  mov     rdi, [rsp+1A8h+var_168]
0x1801528ff  mov     rsi, [rdi]
0x180152902  xor     edx, edx; length
0x180152904  mov     rcx, [rbx+58h]; string
0x180152908  call    cs:__imp_WindowsGetStringRawBuffer
0x18015290f  nop     dword ptr [rax+rax+00h]
0x180152914  lea     rdx, [rbx+48h]
0x180152918  mov     r8, rax
0x18015291b  lea     rcx, [rsp+1A8h+var_A8]
0x180152923  call    ?GetTypeLibVersionKeyPath@Internal@DEH@OSIntegration@@YA?AVKeyPath@RegistryCompatibility@23@AEBU_GUID@@PEBG@Z; OSIntegration::DEH::Internal::GetTypeLibVersionKeyPath(_GUID const &,ushort const *)
0x180152928  nop
0x180152929  cmp     [rbx+0B0h], r14b
0x180152930  jz      short loc_18015293A
0x180152932  mov     cl, [rbx+0B1h]
0x180152938  jmp     short loc_18015293D
0x18015293a  mov     cl, r14b
0x18015293d  mov     edx, r14d
0x180152940  test    cl, cl
0x180152942  setz    dl
0x180152945  lea     r9, [rsp+1A8h+var_160]
0x18015294a  mov     r8, rax
0x18015294d  mov     rcx, rdi
0x180152950  mov     rax, [rsi+30h]
0x180152954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180152959  mov     rcx, [rsp+1A8h]; this
0x180152961  test    eax, eax
0x180152963  js      loc_180152A42
0x180152969  lea     rcx, [rsp+1A8h+var_A8]
0x180152971  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180152976  nop
0x180152977  lea     rcx, [rsp+1A8h+var_F8]; this
0x18015297f  call    ??1Key@RegistryCompatibility@DEH@OSIntegration@@QEAA@XZ; OSIntegration::DEH::RegistryCompatibility::Key::~Key(void)
0x180152984  nop
0x180152985  lea     rcx, [rsp+1A8h+var_160]; this
0x18015298a  call    ??1Key@RegistryCompatibility@DEH@OSIntegration@@QEAA@XZ; OSIntegration::DEH::RegistryCompatibility::Key::~Key(void)
0x18015298f  nop
0x180152990  lea     rcx, [rsp+1A8h+var_168]
0x180152995  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18015299a  xor     eax, eax
0x18015299c  jmp     short loc_1801529A2
0x18015299e  mov     eax, [rsp+1A8h+var_178]
0x1801529a2  mov     rcx, [rsp+1A8h+var_28]
0x1801529aa  xor     rcx, rsp; StackCookie
0x1801529ad  call    __security_check_cookie
0x1801529b2  mov     rbx, [rsp+1A8h+arg_10]
0x1801529ba  add     rsp, 190h
0x1801529c1  pop     r14
0x1801529c3  pop     rdi
0x1801529c4  pop     rsi
0x1801529c5  retn
0x1801529c7  mov     dword ptr [rsp+1A8h+var_180], eax; char *
0x1801529cb  lea     rax, aInternalGetpac_3; "Internal::GetPackagedFileAbsolutePath(i"...
0x1801529d2  mov     [rsp+1A8h+var_188], rax; char *
0x1801529d7  lea     r9, aOsintegrationD_194; "OSIntegration::DEH::ComTypeLibRegistrat"...
0x1801529de  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1801529e5  mov     edx, 1213h; void *
0x1801529ea  call    ?Throw_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Throw_Hr(void *,uint,char const *,char const *,char const *,long)
0x1801529f0  mov     dword ptr [rsp+1A8h+var_180], eax; char *
0x1801529f4  lea     rax, aInternalGetpac_1; "Internal::GetPackagedFileAbsolutePath(i"...
0x1801529fb  mov     [rsp+1A8h+var_188], rax; char *
0x180152a00  lea     r9, aOsintegrationD_194; "OSIntegration::DEH::ComTypeLibRegistrat"...
0x180152a07  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
  ... truncated ...
```
