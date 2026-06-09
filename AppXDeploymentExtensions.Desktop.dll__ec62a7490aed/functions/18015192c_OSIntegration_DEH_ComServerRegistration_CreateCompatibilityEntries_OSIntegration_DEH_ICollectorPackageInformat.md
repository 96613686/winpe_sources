# OSIntegration::DEH::ComServerRegistration::CreateCompatibilityEntries(OSIntegration::DEH::ICollectorPackageInformation const *)

- ea: `0x18015192c`
- end: `0x1801520fd`
- name: `?CreateCompatibilityEntries@ComServerRegistration@DEH@OSIntegration@@AEBAJPEBUICollectorPackageInformation@23@@Z`
- size: `2001`
- prototype: `__int64 __fastcall(OSIntegration::DEH::ComServerRegistration *__hidden this, const struct OSIntegration::DEH::ICollectorPackageInformation *)`
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18015f930`

## callees

- `0x180048cd4`
- `0x18004eac0`
- `0x180056bd4`
- `0x180059424`
- `0x180066780`
- `0x180066938`
- `0x1800669b0`
- `0x180066a2c`
- `0x180078760`
- `0x180078818`
- `0x18007cdc0`
- `0x18009b6f8`
- `0x18009d504`
- `0x1800aed10`
- `0x1800db594`
- `0x1800f6e48`
- `0x1800f74bc`
- `0x1800f7bd8`
- `0x180100f58`
- `0x180142478`
- `0x180142650`
- `0x1801426a4`
- `0x180142930`
- `0x18015192c`
- `0x180155964`
- `0x180158f78`
- `0x18015a2f0`
- `0x18015ce0c`
- `0x180169c98`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180151e39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180151e73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180151e39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180151e73`

## string_xrefs

- `0x180152099`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x1801520c1`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x1801520ea`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x180152086`: `Internal::GetSystemFileAbsolutePath( _properties.SystemExecutableArchitecture.Value, _properties.Executable.Value.GetRawBuffer(nullptr), surrogateExecutableAbsolutePath)`
- `0x1801520ae`: `Internal::GetPackagedFileAbsolutePath(incomingPackage, _properties.Executable.Value.GetRawBuffer(nullptr), surrogateExecutableAbsolutePath)`
- `0x180152092`: `OSIntegration::DEH::ComServerRegistration::CreateCompatibilityEntries`
- `0x1801520ba`: `OSIntegration::DEH::ComServerRegistration::CreateCompatibilityEntries`
- `0x1801520e3`: `OSIntegration::DEH::ComServerRegistration::CreateCompatibilityEntries`
- `0x1801520d7`: `registryCompatibilityCollector->AddKey( (_hasMachineScope ? Scope::Machine : Scope::User), Internal::GetAppIdKeyPath(_appId.Value), std::move(appIdKey))`
- `0x180151ed7`: `DllSurrogate`
- `0x180151f91`: `DllSurrogate`
- `0x180151b3a`: `LocalService`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall OSIntegration::DEH::ComServerRegistration::CreateCompatibilityEntries(
        OSIntegration::DEH::ComServerRegistration *this,
        const struct OSIntegration::DEH::ICollectorPackageInformation *a2)
{
  __int64 v4; // rcx
  __int64 result; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rdx
  unsigned __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rdx
  const WCHAR *StringRawBuffer; // rax
  int SystemFileAbsolutePath; // eax
  PCWSTR v22; // rax
  int PackagedFileAbsolutePath; // eax
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rdx
  _QWORD *v27; // rdi
  __int64 v28; // rsi
  __int64 AppIdKeyPath; // rax
  int v30; // eax
  char *v31; // [rsp+20h] [rbp-148h]
  char *v32; // [rsp+28h] [rbp-140h]
  char *v33; // [rsp+28h] [rbp-140h]
  int v34[2]; // [rsp+30h] [rbp-138h] BYREF
  _QWORD *v35; // [rsp+38h] [rbp-130h] BYREF
  _BYTE v36[48]; // [rsp+40h] [rbp-128h] BYREF
  _BYTE v37[48]; // [rsp+70h] [rbp-F8h] BYREF
  char v38; // [rsp+A0h] [rbp-C8h]
  void **v39; // [rsp+A8h] [rbp-C0h] BYREF
  int v40; // [rsp+B0h] [rbp-B8h]
  __int128 v41; // [rsp+B8h] [rbp-B0h] BYREF
  char v42; // [rsp+D8h] [rbp-90h]
  _BYTE v43[16]; // [rsp+E0h] [rbp-88h] BYREF
  _BYTE v44[32]; // [rsp+F0h] [rbp-78h] BYREF
  void **v45; // [rsp+110h] [rbp-58h] BYREF
  int v46; // [rsp+118h] [rbp-50h]
  _OWORD v47[2]; // [rsp+120h] [rbp-48h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+168h] [rbp+0h]

  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
      && *((_DWORD *)this + 87) == *((_DWORD *)this + 88) )
    {
      return 0;
    }
    if ( !*((_BYTE *)this + 341) )
      return 0;
    if ( !*((_BYTE *)this + 320) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v4);
      return 0;
    }
    v6 = (*(__int64 (__fastcall **)(const struct OSIntegration::DEH::ICollectorPackageInformation *))(*(_QWORD *)a2 + 72LL))(a2);
    wil::com_ptr_t<IXMLDOMElement,wil::err_exception_policy>::com_ptr_t<IXMLDOMElement,wil::err_exception_policy>(
      &v35,
      *(_QWORD *)(v6 + 72));
    OSIntegration::DEH::RegistryCompatibility::Key::Key((OSIntegration::DEH::RegistryCompatibility::Key *)v36);
    if ( *((_BYTE *)this + 104) )
    {
      v7 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
             v43,
             (char *)this + 112);
      std::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>(
        &v39,
        v8,
        v7);
      v42 = 5;
      OSIntegration::DEH::RegistryCompatibility::Key::AddDefaultValue(v36, &v39);
      std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(&v39);
      std::wstring::_Tidy_deallocate(v44);
    }
    if ( *((_BYTE *)this + 120) )
    {
      v9 = *((unsigned __int16 *)this + 68);
      HIDWORD(v45) = 0;
      OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData::RegBinaryValueData(
        (OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData *)&v45,
        v9,
        *((const void **)this + 16));
      v45 = &OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData::`vftable';
      v40 = 3;
      v39 = &OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData::`vftable';
      v41 = v47[0];
      v47[0] = 0;
      v42 = 0;
      OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1>::Name<0,16383,1>(v43, L"LaunchPermission");
      OSIntegration::DEH::RegistryCompatibility::Key::AddValue(v36, v43, &v39);
      std::wstring::_Tidy_deallocate(v43);
      std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(&v39);
      wil::unique_any_array_ptr<unsigned char,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::reset(v47);
    }
    if ( *((_BYTE *)this + 232) )
    {
      v10 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
              &v45,
              (char *)this + 240);
      std::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>(
        &v39,
        v11,
        v10);
      v42 = 5;
      OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1>::Name<0,16383,1>(v43, L"LocalService");
      OSIntegration::DEH::RegistryCompatibility::Key::AddValue(v36, v43, &v39);
      std::wstring::_Tidy_deallocate(v43);
      std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(&v39);
      std::wstring::_Tidy_deallocate(v47);
      if ( *((_BYTE *)this + 176) )
      {
        v12 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
                &v45,
                (char *)this + 184);
        std::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>(
          &v39,
          v13,
          v12);
        v42 = 5;
        OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1>::Name<0,16383,1>(v43);
        OSIntegration::DEH::RegistryCompatibility::Key::AddValue(v36, v43, &v39);
        std::wstring::_Tidy_deallocate(v43);
        std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(&v39);
LABEL_40:
        std::wstring::_Tidy_deallocate(v47);
        goto LABEL_41;
      }
      goto LABEL_41;
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    {
      v18 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(&v45);
      std::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>(
        &v39,
        v19,
        v18);
      v42 = 5;
      OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1>::Name<0,16383,1>(v43, L"RunAs");
      OSIntegration::DEH::RegistryCompatibility::Key::AddValue(v36, v43, &v39);
      std::wstring::_Tidy_deallocate(v43);
      std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(&v39);
      std::wstring::_Tidy_deallocate(v47);
      goto LABEL_29;
    }
    if ( OSIntegration::DEH::ComServerRegistration::IsActivateAsPackage(this) )
    {
      v14 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(&v45);
      std::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>(
        &v39,
        v15,
        v14);
      v42 = 5;
      OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1>::Name<0,16383,1>(v43, L"RunAs");
      OSIntegration::DEH::RegistryCompatibility::Key::AddValue(v36, v43, &v39);
      std::wstring::_Tidy_deallocate(v43);
      std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(&v39);
      std::wstring::_Tidy_deallocate(v47);
    }
    if ( OSIntegration::DEH::ComServerRegistration::IsActivateAsPackage(this) )
    {
      if ( *((_BYTE *)this + 280) )
        LOBYTE(v16) = *((_BYTE *)this + 281);
      else
        LOBYTE(v16) = 0;
      v17 = (_BYTE)v16 != 0;
    }
    else
    {
      if ( *((_BYTE *)this + 284) && *((_DWORD *)this + 72) )
        goto LABEL_29;
      v17 = 2;
    }
    if ( v17 )
    {
      v40 = 4;
      v39 = &OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>::`vftable';
      LODWORD(v41) = v17;
      v42 = 1;
      OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1>::Name<0,16383,1>(v43);
      OSIntegration::DEH::RegistryCompatibility::Key::AddValue(v36, v43, &v39);
      std::wstring::_Tidy_deallocate(v43);
      std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(&v39);
    }
LABEL_29:
    if ( *((_BYTE *)this + 192) )
    {
      if ( *((_BYTE *)this + 144) )
      {
        *(_QWORD *)v34 = 0;
        if ( *((_BYTE *)this + 160) && *((_BYTE *)this + 161) )
        {
          if ( !*((_BYTE *)this + 164) )
            MicrosoftTelemetryAssertTriggeredNoArgs(v16);
          StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 19), 0);
          SystemFileAbsolutePath = OSIntegration::DEH::Internal::GetSystemFileAbsolutePath(
                                     (char *)*((unsigned int *)this + 42),
                                     StringRawBuffer,
                                     (PWSTR *)v34);
          if ( SystemFileAbsolutePath < 0 )
          {
            LODWORD(v33) = SystemFileAbsolutePath;
            wil::details::in1diag5::Throw_Hr(
              retaddr,
              (void *)0xE71,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
              "OSIntegration::DEH::ComServerRegistration::CreateCompatibilityEntries",
              "Internal::GetSystemFileAbsolutePath( _properties.SystemExecutableArchitecture.Value, _properties.Executabl"
              "e.Value.GetRawBuffer(nullptr), surrogateExecutableAbsolutePath)",
              v33,
              v34[0]);
          }
        }
        else
        {
          v22 = WindowsGetStringRawBuffer(*((HSTRING *)this + 19), 0);
          PackagedFileAbsolutePath = OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(a2, v22, v34);
          if ( PackagedFileAbsolutePath < 0 )
          {
            LODWORD(v33) = PackagedFileAbsolutePath;
            wil::details::in1diag5::Throw_Hr(
              retaddr,
              (void *)0xE77,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
              "OSIntegration::DEH::ComServerRegistration::CreateCompatibilityEntries",
              "Internal::GetPackagedFileAbsolutePath(incomingPackage, _properties.Executable.Value.GetRawBuffer(nullptr),"
              " surrogateExecutableAbsolutePath)",
              v33,
              v34[0]);
          }
        }
        v45 = *(void ***)v34;
        v24 = OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(
                &v39,
                &v45);
        std::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>(
          v37,
          v25,
          v24);
        v38 = 5;
        OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1>::Name<0,16383,1>(v43, L"DllSurrogate");
        OSIntegration::DEH::RegistryCompatibility::Key::AddValue(v36, v43, v37);
        std::wstring::_Tidy_deallocate(v43);
        std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v37);
        std::wstring::_Tidy_deallocate(&v41);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v34);
        goto LABEL_41;
      }
      v46 = 1;
      v45 = &OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::`vftable';
      std::wstring::wstring(v47, &Value);
      OSIntegration::DEH::RegistryCompatibility::Details::GetStringByteCountIncludingTerminator<OSIntegration::DEH::RegistryCompatibility::Details::String>(v47);
      std::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>(
        v37,
        v26,
        &v45);
      v38 = 5;
      OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1>::Name<0,16383,1>(v43, L"DllSurrogate");
      OSIntegration::DEH::RegistryCompatibility::Key::AddValue(v36, v43, v37);
      std::wstring::_Tidy_deallocate(v43);
      std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,unsigned int>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(v37);
      goto LABEL_40;
    }
LABEL_41:
    v27 = v35;
    v28 = *v35;
    AppIdKeyPath = OSIntegration::DEH::Internal::GetAppIdKeyPath(v43, (char *)this + 324);
    v30 = (*(__int64 (__fastcall **)(_QWORD *, bool, __int64, _BYTE *))(v28 + 48))(
            v27,
            *((_BYTE *)this + 340) == 0,
            AppIdKeyPath,
            v36);
    if ( v30 < 0 )
    {
      LODWORD(v33) = v30;
      wil::details::in1diag5::Throw_Hr(
        retaddr,
        (void *)0xE87,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
        "OSIntegration::DEH::ComServerRegistration::CreateCompatibilityEntries",
        "registryCompatibilityCollector->AddKey( (_hasMachineScope ? Scope::Machine : Scope::User), Internal::GetAppIdKey"
        "Path(_appId.Value), std::move(appIdKey))",
        v33,
        v34[0]);
    }
    std::wstring::_Tidy_deallocate(v43);
    OSIntegration::DEH::RegistryCompatibility::Key::~Key((OSIntegration::DEH::RegistryCompatibility::Key *)v36);
    wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v35);
    return 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag5::Return_CaughtException(
                           retaddr,
                           (void *)0xE8B,
                           (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
                           "OSIntegration::DEH::ComServerRegistration::CreateCompatibilityEntries",
                           v31,
                           v32);
  }
  return result;
}

```

## disassembly

```asm
0x18015192c  mov     [rsp+arg_10], rbx
0x180151931  push    rsi
0x180151932  push    rdi
0x180151933  push    r14
0x180151935  sub     rsp, 150h
0x18015193c  mov     rax, cs:__security_cookie
0x180151943  xor     rax, rsp
0x180151946  mov     [rsp+168h+var_28], rax
0x18015194e  mov     rdi, rdx
0x180151951  mov     rbx, rcx
0x180151954  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18015195b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180151960  xor     r14d, r14d
0x180151963  test    al, al
0x180151965  jz      short loc_18015197C
0x180151967  mov     eax, [rbx+15Ch]
0x18015196d  cmp     eax, [rbx+160h]
0x180151973  jnz     short loc_18015197C
0x180151975  xor     eax, eax
0x180151977  jmp     loc_18015205D
0x18015197c  cmp     [rbx+155h], r14b
0x180151983  jz      loc_180152055
0x180151989  cmp     [rbx+140h], r14b
0x180151990  jnz     short loc_18015199C
0x180151992  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "AlreadyHasAppId()")
0x180151997  jmp     loc_180152055
0x18015199c  mov     rax, [rdi]
0x18015199f  mov     rcx, rdi
0x1801519a2  mov     rax, [rax+48h]
0x1801519a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801519ab  mov     rdx, [rax+48h]
0x1801519af  lea     rcx, [rsp+168h+var_130]
0x1801519b4  call    ??0?$com_ptr_t@UIXMLDOMElement@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIXMLDOMElement@@@Z; wil::com_ptr_t<IXMLDOMElement,wil::err_exception_policy>::com_ptr_t<IXMLDOMElement,wil::err_exception_policy>(IXMLDOMElement *)
0x1801519b9  nop
0x1801519ba  lea     rcx, [rsp+168h+var_128]; this
0x1801519bf  call    ??0Key@RegistryCompatibility@DEH@OSIntegration@@QEAA@XZ; OSIntegration::DEH::RegistryCompatibility::Key::Key(void)
0x1801519c4  nop
0x1801519c5  cmp     [rbx+68h], r14b
0x1801519c9  jz      short loc_180151A23
0x1801519cb  lea     rdx, [rbx+70h]
0x1801519cf  lea     rcx, [rsp+168h+var_88]
0x1801519d7  call    ??$?0AEBVOpaqueString@@@?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEBVOpaqueString@@@Z; OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(OpaqueString const &)
0x1801519dc  nop
0x1801519dd  mov     r8, rax
0x1801519e0  lea     rcx, [rsp+168h+var_C0]
0x1801519e8  call    ??$?0$04V?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@$0A@@?$_Variant_storage_@$0A@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAA@U?$integral_constant@_K$04@1@$$QEAV?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@@Z; std::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>(std::integral_constant<unsigned __int64,5>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1> &&)
0x1801519ed  mov     [rsp+168h+var_90], 5
0x1801519f5  lea     rdx, [rsp+168h+var_C0]
0x1801519fd  lea     rcx, [rsp+168h+var_128]
0x180151a02  call    ?AddDefaultValue@Key@RegistryCompatibility@DEH@OSIntegration@@QEAAX$$QEAVAnyValueData@234@@Z; OSIntegration::DEH::RegistryCompatibility::Key::AddDefaultValue(OSIntegration::DEH::RegistryCompatibility::AnyValueData &&)
0x180151a07  nop
0x180151a08  lea     rcx, [rsp+168h+var_C0]
0x180151a10  call    ?_Destroy@?$_Variant_base@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAAXXZ; std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(void)
0x180151a15  nop
0x180151a16  lea     rcx, [rsp+168h+var_78]
0x180151a1e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180151a23  cmp     [rbx+78h], r14b
0x180151a27  jz      loc_180151B00
0x180151a2d  movzx   edx, word ptr [rbx+88h]; unsigned __int64
0x180151a34  xor     ecx, ecx
0x180151a36  mov     dword ptr [rsp+168h+var_58+4], ecx
0x180151a3d  mov     r8, [rbx+80h]; void *
0x180151a44  lea     rcx, [rsp+168h+var_58]; this
0x180151a4c  call    ??0RegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@QEAA@_KPEBX@Z; OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData::RegBinaryValueData(unsigned __int64,void const *)
0x180151a51  lea     rax, ??_7RegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@6B@; const OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData::`vftable'
0x180151a58  mov     [rsp+168h+var_58], rax
0x180151a60  mov     [rsp+168h+var_B8], 3
0x180151a6b  mov     [rsp+168h+var_C0], rax
0x180151a73  mov     rax, qword ptr [rsp+168h+var_48]
0x180151a7b  mov     qword ptr [rsp+168h+var_B0], rax
0x180151a83  mov     rax, qword ptr [rsp+168h+var_48+8]
0x180151a8b  mov     qword ptr [rsp+168h+var_B0+8], rax
0x180151a93  xorps   xmm0, xmm0
0x180151a96  movdqu  [rsp+168h+var_48], xmm0
0x180151a9f  mov     [rsp+168h+var_90], r14b
0x180151aa7  lea     rdx, ?LaunchPermission@Constants@Catalog@Com@@3QBGB; "LaunchPermission"
0x180151aae  lea     rcx, [rsp+168h+var_88]
0x180151ab6  call    ??$?0AEAY0N@$$CBG@?$Name@$0A@$0DPPP@$00@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEAY0N@$$CBG@Z; OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1>::Name<0,16383,1>(ushort const (&)[13])
0x180151abb  nop
0x180151abc  lea     r8, [rsp+168h+var_C0]
0x180151ac4  lea     rdx, [rsp+168h+var_88]
0x180151acc  lea     rcx, [rsp+168h+var_128]
0x180151ad1  call    ?AddValue@Key@RegistryCompatibility@DEH@OSIntegration@@QEAAX$$QEAV?$Name@$0A@$0DPPP@$00@234@$$QEAVAnyValueData@234@@Z; OSIntegration::DEH::RegistryCompatibility::Key::AddValue(OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1> &&,OSIntegration::DEH::RegistryCompatibility::AnyValueData &&)
0x180151ad6  nop
0x180151ad7  lea     rcx, [rsp+168h+var_88]
0x180151adf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180151ae4  nop
0x180151ae5  lea     rcx, [rsp+168h+var_C0]
0x180151aed  call    ?_Destroy@?$_Variant_base@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAAXXZ; std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(void)
0x180151af2  nop
0x180151af3  lea     rcx, [rsp+168h+var_48]
0x180151afb  call    ?reset@?$unique_any_array_ptr@EUprocess_heap_deleter@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::reset(void)
0x180151b00  cmp     [rbx+0E8h], r14b
0x180151b07  jz      loc_180151C17
0x180151b0d  lea     rdx, [rbx+0F0h]
0x180151b14  lea     rcx, [rsp+168h+var_58]
0x180151b1c  call    ??$?0AEBVOpaqueString@@@?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEBVOpaqueString@@@Z; OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(OpaqueString const &)
0x180151b21  nop
0x180151b22  mov     r8, rax
0x180151b25  lea     rcx, [rsp+168h+var_C0]
0x180151b2d  call    ??$?0$04V?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@$0A@@?$_Variant_storage_@$0A@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAA@U?$integral_constant@_K$04@1@$$QEAV?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@@Z; std::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>(std::integral_constant<unsigned __int64,5>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1> &&)
0x180151b32  mov     [rsp+168h+var_90], 5
0x180151b3a  lea     rdx, ?LocalService@Constants@Catalog@Com@@3QBGB; "LocalService"
0x180151b41  lea     rcx, [rsp+168h+var_88]
0x180151b49  call    ??$?0AEAY0N@$$CBG@?$Name@$0A@$0DPPP@$00@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEAY0N@$$CBG@Z; OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1>::Name<0,16383,1>(ushort const (&)[13])
0x180151b4e  nop
0x180151b4f  lea     r8, [rsp+168h+var_C0]
0x180151b57  lea     rdx, [rsp+168h+var_88]
0x180151b5f  lea     rcx, [rsp+168h+var_128]
0x180151b64  call    ?AddValue@Key@RegistryCompatibility@DEH@OSIntegration@@QEAAX$$QEAV?$Name@$0A@$0DPPP@$00@234@$$QEAVAnyValueData@234@@Z; OSIntegration::DEH::RegistryCompatibility::Key::AddValue(OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1> &&,OSIntegration::DEH::RegistryCompatibility::AnyValueData &&)
0x180151b69  nop
0x180151b6a  lea     rcx, [rsp+168h+var_88]
0x180151b72  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180151b77  nop
0x180151b78  lea     rcx, [rsp+168h+var_C0]
0x180151b80  call    ?_Destroy@?$_Variant_base@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAAXXZ; std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(void)
0x180151b85  nop
0x180151b86  lea     rcx, [rsp+168h+var_48]
0x180151b8e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180151b93  cmp     [rbx+0B0h], r14b
0x180151b9a  jz      loc_180151FE4
0x180151ba0  lea     rdx, [rbx+0B8h]
0x180151ba7  lea     rcx, [rsp+168h+var_58]
0x180151baf  call    ??$?0AEBVOpaqueString@@@?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEBVOpaqueString@@@Z; OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(OpaqueString const &)
0x180151bb4  nop
0x180151bb5  mov     r8, rax
0x180151bb8  lea     rcx, [rsp+168h+var_C0]
0x180151bc0  call    ??$?0$04V?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@$0A@@?$_Variant_storage_@$0A@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAA@U?$integral_constant@_K$04@1@$$QEAV?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@@Z; std::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>(std::integral_constant<unsigned __int64,5>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1> &&)
0x180151bc5  mov     [rsp+168h+var_90], 5
0x180151bcd  lea     rcx, [rsp+168h+var_88]
0x180151bd5  call    ??$?0AEAY0BC@$$CBG@?$Name@$0A@$0DPPP@$00@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEAY0BC@$$CBG@Z; OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1>::Name<0,16383,1>(ushort const (&)[18])
0x180151bda  nop
0x180151bdb  lea     r8, [rsp+168h+var_C0]
0x180151be3  lea     rdx, [rsp+168h+var_88]
0x180151beb  lea     rcx, [rsp+168h+var_128]
0x180151bf0  call    ?AddValue@Key@RegistryCompatibility@DEH@OSIntegration@@QEAAX$$QEAV?$Name@$0A@$0DPPP@$00@234@$$QEAVAnyValueData@234@@Z; OSIntegration::DEH::RegistryCompatibility::Key::AddValue(OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1> &&,OSIntegration::DEH::RegistryCompatibility::AnyValueData &&)
0x180151bf5  nop
0x180151bf6  lea     rcx, [rsp+168h+var_88]
0x180151bfe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180151c03  nop
0x180151c04  lea     rcx, [rsp+168h+var_C0]
0x180151c0c  call    ?_Destroy@?$_Variant_base@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAAXXZ; std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(void)
0x180151c11  nop
0x180151c12  jmp     loc_180151FD7
0x180151c17  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180151c1e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180151c23  test    al, al
0x180151c25  jz      loc_180151D72
0x180151c2b  mov     rcx, rbx; this
0x180151c2e  call    ?IsActivateAsPackage@ComServerRegistration@DEH@OSIntegration@@IEBA_NXZ; OSIntegration::DEH::ComServerRegistration::IsActivateAsPackage(void)
0x180151c33  test    al, al
0x180151c35  jz      short loc_180151CB6
0x180151c37  lea     rcx, [rsp+168h+var_58]
0x180151c3f  call    ??$?0AEAY0BB@$$CBG@?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEAY0BB@$$CBG@Z; OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(ushort const (&)[17])
0x180151c44  nop
0x180151c45  mov     r8, rax
0x180151c48  lea     rcx, [rsp+168h+var_C0]
0x180151c50  call    ??$?0$04V?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@$0A@@?$_Variant_storage_@$0A@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAA@U?$integral_constant@_K$04@1@$$QEAV?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@@Z; std::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>(std::integral_constant<unsigned __int64,5>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1> &&)
0x180151c55  mov     [rsp+168h+var_90], 5
0x180151c5d  lea     rdx, ?RunAs@Constants@Catalog@Com@@3QBGB; "RunAs"
0x180151c64  lea     rcx, [rsp+168h+var_88]
0x180151c6c  call    ??$?0AEAY0N@$$CBG@?$Name@$0A@$0DPPP@$00@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEAY0N@$$CBG@Z; OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1>::Name<0,16383,1>(ushort const (&)[13])
0x180151c71  nop
0x180151c72  lea     r8, [rsp+168h+var_C0]
0x180151c7a  lea     rdx, [rsp+168h+var_88]
0x180151c82  lea     rcx, [rsp+168h+var_128]
0x180151c87  call    ?AddValue@Key@RegistryCompatibility@DEH@OSIntegration@@QEAAX$$QEAV?$Name@$0A@$0DPPP@$00@234@$$QEAVAnyValueData@234@@Z; OSIntegration::DEH::RegistryCompatibility::Key::AddValue(OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1> &&,OSIntegration::DEH::RegistryCompatibility::AnyValueData &&)
0x180151c8c  nop
0x180151c8d  lea     rcx, [rsp+168h+var_88]
0x180151c95  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180151c9a  nop
0x180151c9b  lea     rcx, [rsp+168h+var_C0]
0x180151ca3  call    ?_Destroy@?$_Variant_base@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAAXXZ; std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(void)
0x180151ca8  nop
0x180151ca9  lea     rcx, [rsp+168h+var_48]
0x180151cb1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180151cb6  mov     rcx, rbx; this
0x180151cb9  call    ?IsActivateAsPackage@ComServerRegistration@DEH@OSIntegration@@IEBA_NXZ; OSIntegration::DEH::ComServerRegistration::IsActivateAsPackage(void)
0x180151cbe  test    al, al
0x180151cc0  jz      short loc_180151CE0
0x180151cc2  cmp     [rbx+118h], r14b
0x180151cc9  jz      short loc_180151CD3
0x180151ccb  mov     cl, [rbx+119h]
0x180151cd1  jmp     short loc_180151CD6
0x180151cd3  mov     cl, r14b
0x180151cd6  mov     eax, r14d
0x180151cd9  test    cl, cl
0x180151cdb  setnz   al
0x180151cde  jmp     short loc_180151CFB
0x180151ce0  cmp     [rbx+11Ch], r14b
0x180151ce7  jz      short loc_180151CF6
0x180151ce9  cmp     [rbx+120h], r14d
0x180151cf0  jnz     loc_180151DF1
0x180151cf6  mov     eax, 2
0x180151cfb  test    eax, eax
0x180151cfd  jz      loc_180151DF1
0x180151d03  mov     [rsp+168h+var_B8], 4
0x180151d0e  lea     rcx, ??_7?$IntegralTypeValueData@$03I@Details@RegistryCompatibility@DEH@OSIntegration@@6B@; const OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>::`vftable'
0x180151d15  mov     [rsp+168h+var_C0], rcx
0x180151d1d  mov     dword ptr [rsp+168h+var_B0], eax
0x180151d24  mov     [rsp+168h+var_90], 1
0x180151d2c  lea     rcx, [rsp+168h+var_88]
0x180151d34  call    ??$?0AEAY0L@$$CBG@?$Name@$0A@$0DPPP@$00@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEAY0L@$$CBG@Z; OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1>::Name<0,16383,1>(ushort const (&)[11])
0x180151d39  nop
0x180151d3a  lea     r8, [rsp+168h+var_C0]
0x180151d42  lea     rdx, [rsp+168h+var_88]
0x180151d4a  lea     rcx, [rsp+168h+var_128]
0x180151d4f  call    ?AddValue@Key@RegistryCompatibility@DEH@OSIntegration@@QEAAX$$QEAV?$Name@$0A@$0DPPP@$00@234@$$QEAVAnyValueData@234@@Z; OSIntegration::DEH::RegistryCompatibility::Key::AddValue(OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1> &&,OSIntegration::DEH::RegistryCompatibility::AnyValueData &&)
0x180151d54  nop
0x180151d55  lea     rcx, [rsp+168h+var_88]
0x180151d5d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180151d62  nop
0x180151d63  lea     rcx, [rsp+168h+var_C0]
0x180151d6b  call    ?_Destroy@?$_Variant_base@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAAXXZ; std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(void)
0x180151d70  jmp     short loc_180151DF1
0x180151d72  lea     rcx, [rsp+168h+var_58]
0x180151d7a  call    ??$?0AEAY0BB@$$CBG@?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEAY0BB@$$CBG@Z; OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(ushort const (&)[17])
0x180151d7f  nop
0x180151d80  mov     r8, rax
0x180151d83  lea     rcx, [rsp+168h+var_C0]
0x180151d8b  call    ??$?0$04V?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@$0A@@?$_Variant_storage_@$0A@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAA@U?$integral_constant@_K$04@1@$$QEAV?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@@Z; std::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>(std::integral_constant<unsigned __int64,5>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1> &&)
0x180151d90  mov     [rsp+168h+var_90], 5
0x180151d98  lea     rdx, ?RunAs@Constants@Catalog@Com@@3QBGB; "RunAs"
0x180151d9f  lea     rcx, [rsp+168h+var_88]
0x180151da7  call    ??$?0AEAY0N@$$CBG@?$Name@$0A@$0DPPP@$00@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEAY0N@$$CBG@Z; OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1>::Name<0,16383,1>(ushort const (&)[13])
0x180151dac  nop
0x180151dad  lea     r8, [rsp+168h+var_C0]
0x180151db5  lea     rdx, [rsp+168h+var_88]
0x180151dbd  lea     rcx, [rsp+168h+var_128]
0x180151dc2  call    ?AddValue@Key@RegistryCompatibility@DEH@OSIntegration@@QEAAX$$QEAV?$Name@$0A@$0DPPP@$00@234@$$QEAVAnyValueData@234@@Z; OSIntegration::DEH::RegistryCompatibility::Key::AddValue(OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1> &&,OSIntegration::DEH::RegistryCompatibility::AnyValueData &&)
0x180151dc7  nop
0x180151dc8  lea     rcx, [rsp+168h+var_88]
0x180151dd0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180151dd5  nop
0x180151dd6  lea     rcx, [rsp+168h+var_C0]
0x180151dde  call    ?_Destroy@?$_Variant_base@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAAXXZ; std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(void)
0x180151de3  nop
0x180151de4  lea     rcx, [rsp+168h+var_48]
0x180151dec  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180151df1  cmp     [rbx+0C0h], r14b
0x180151df8  jz      loc_180151FE4
0x180151dfe  cmp     [rbx+90h], r14b
0x180151e05  jz      loc_180151F3A
0x180151e0b  mov     qword ptr [rsp+168h+var_138], r14; int
0x180151e10  cmp     [rbx+0A0h], r14b
0x180151e17  jz      short loc_180151E6A
0x180151e19  cmp     [rbx+0A1h], r14b
0x180151e20  jz      short loc_180151E6A
0x180151e22  cmp     [rbx+0A4h], r14b
0x180151e29  jnz     short loc_180151E30
0x180151e2b  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "_properties.SystemExecutableArchitecture.Present")
0x180151e30  xor     edx, edx; length
0x180151e32  mov     rcx, [rbx+98h]; string
0x180151e39  call    cs:__imp_WindowsGetStringRawBuffer
0x180151e40  nop     dword ptr [rax+rax+00h]
0x180151e45  lea     r8, [rsp+168h+var_138]
0x180151e4a  mov     rdx, rax
0x180151e4d  mov     ecx, [rbx+0A8h]
0x180151e53  call    ?GetSystemFileAbsolutePath@Internal@DEH@OSIntegration@@YAJIPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; OSIntegration::DEH::Internal::GetSystemFileAbsolutePath(uint,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180151e58  mov     rcx, [rsp+168h]; this
0x180151e60  test    eax, eax
0x180151e62  js      loc_180152082
0x180151e68  jmp     short loc_180151E9F
0x180151e6a  xor     edx, edx; length
0x180151e6c  mov     rcx, [rbx+98h]; string
0x180151e73  call    cs:__imp_WindowsGetStringRawBuffer
0x180151e7a  nop     dword ptr [rax+rax+00h]
0x180151e7f  lea     r8, [rsp+168h+var_138]
0x180151e84  mov     rdx, rax
0x180151e87  mov     rcx, rdi
0x180151e8a  call    ?GetPackagedFileAbsolutePath@Internal@DEH@OSIntegration@@YAJPEBUICollectorPackageInformation@23@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(OSIntegration::DEH::ICollectorPackageInformation const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180151e8f  mov     rcx, [rsp+168h]; this
0x180151e97  test    eax, eax
0x180151e99  js      loc_1801520AA
0x180151e9f  mov     rax, qword ptr [rsp+168h+var_138]
0x180151ea4  mov     [rsp+168h+var_58], rax
0x180151eac  lea     rdx, [rsp+168h+var_58]
0x180151eb4  lea     rcx, [rsp+168h+var_C0]
0x180151ebc  call    ??$?0PEBG@?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@QEAA@$$QEAPEBG@Z; OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>::StringTypeValueData<1>(ushort const * &&)
0x180151ec1  nop
0x180151ec2  mov     r8, rax
0x180151ec5  lea     rcx, [rsp+168h+var_F8]
0x180151eca  call    ??$?0$04V?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@$0A@@?$_Variant_storage_@$0A@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAA@U?$integral_constant@_K$04@1@$$QEAV?$StringTypeValueData@$00@Details@RegistryCompatibility@DEH@OSIntegration@@@Z; std::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Variant_storage_<0,OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>(std::integral_constant<unsigned __int64,5>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1> &&)
0x180151ecf  mov     [rsp+168h+var_C8], 5
0x180151ed7  lea     rdx, ?DllSurrogate@Constants@Catalog@Com@@3QBGB; "DllSurrogate"
0x180151ede  lea     rcx, [rsp+168h+var_88]
0x180151ee6  call    ??$?0AEAY0N@$$CBG@?$Name@$0A@$0DPPP@$00@RegistryCompatibility@DEH@OSIntegration@@QEAA@AEAY0N@$$CBG@Z; OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1>::Name<0,16383,1>(ushort const (&)[13])
0x180151eeb  nop
0x180151eec  lea     r8, [rsp+168h+var_F8]
0x180151ef1  lea     rdx, [rsp+168h+var_88]
0x180151ef9  lea     rcx, [rsp+168h+var_128]
0x180151efe  call    ?AddValue@Key@RegistryCompatibility@DEH@OSIntegration@@QEAAX$$QEAV?$Name@$0A@$0DPPP@$00@234@$$QEAVAnyValueData@234@@Z; OSIntegration::DEH::RegistryCompatibility::Key::AddValue(OSIntegration::DEH::RegistryCompatibility::Name<0,16383,1> &&,OSIntegration::DEH::RegistryCompatibility::AnyValueData &&)
0x180151f03  nop
0x180151f04  lea     rcx, [rsp+168h+var_88]
0x180151f0c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180151f11  nop
0x180151f12  lea     rcx, [rsp+168h+var_F8]
0x180151f17  call    ?_Destroy@?$_Variant_base@VRegBinaryValueData@RegistryCompatibility@DEH@OSIntegration@@V?$IntegralTypeValueData@$03I@Details@234@V?$StringTypeValueData@$01@6234@VRegMultiSzValueData@234@V?$IntegralTypeValueData@$0L@_K@6234@V?$StringTypeValueData@$00@6234@VGenericValueData@234@@std@@QEAAXXZ; std::_Variant_base<OSIntegration::DEH::RegistryCompatibility::RegBinaryValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<4,uint>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<2>,OSIntegration::DEH::RegistryCompatibility::RegMultiSzValueData,OSIntegration::DEH::RegistryCompatibility::Details::IntegralTypeValueData<11,unsigned __int64>,OSIntegration::DEH::RegistryCompatibility::Details::StringTypeValueData<1>,OSIntegration::DEH::RegistryCompatibility::GenericValueData>::_Destroy(void)
0x180151f1c  nop
0x180151f1d  lea     rcx, [rsp+168h+var_B0]
  ... truncated ...
```
