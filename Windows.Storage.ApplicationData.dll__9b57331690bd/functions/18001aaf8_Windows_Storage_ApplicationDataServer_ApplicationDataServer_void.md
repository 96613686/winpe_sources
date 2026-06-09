# Windows::Storage::ApplicationDataServer::~ApplicationDataServer(void)

- ea: `0x18001aaf8`
- end: `0x18001aba0`
- name: `??1ApplicationDataServer@Storage@Windows@@UEAA@XZ`
- size: `168`
- prototype: `void __fastcall(Windows::Storage::ApplicationDataServer *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001aac0`

## callees

- `0x180002ebc`
- `0x180003820`
- `0x1800092d0`
- `0x1800093d0`
- `0x18000cdb0`
- `0x180019580`
- `0x18001aaf8`
- `0x18001bdd4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ab84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ab84`

## pseudocode

```c
void __fastcall Windows::Storage::ApplicationDataServer::~ApplicationDataServer(
        Windows::Storage::ApplicationDataServer *this)
{
  HSTRING__ *hstring; // rcx

  this->Microsoft::WRL::RuntimeClass<Windows::Storage::IApplicationData,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Storage::IApplicationData,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Storage::IApplicationData,IWeakReferenceSource,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Windows::Storage::IApplicationData::IInspectable::IUnknown::__vftable = (Windows::Storage::ApplicationDataServer_vtbl *)Windows::Storage::ApplicationDataServer::`vftable'{for `Windows::Storage::IApplicationData'};
  this->Microsoft::WRL::RuntimeClass<Windows::Storage::IApplicationData,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Storage::IApplicationData,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Storage::IApplicationData,IWeakReferenceSource,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::IWeakReferenceSource::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>_vtbl *)Windows::Storage::ApplicationDataServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>'};
  this->Microsoft::WRL::RuntimeClass<Windows::Storage::IApplicationData,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Storage::IApplicationData,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Storage::IApplicationData,IWeakReferenceSource,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Windows::Storage::IApplicationData2::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>_vtbl *)Windows::Storage::ApplicationDataServer::`vftable'{for `Windows::Storage::IApplicationData2'};
  this->Microsoft::WRL::RuntimeClass<Windows::Storage::IApplicationData,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Storage::IApplicationData,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Storage::IApplicationData,IWeakReferenceSource,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Windows::Storage::IApplicationData3::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>_vtbl *)Windows::Storage::ApplicationDataServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>'};
  this->Microsoft::WRL::RuntimeClass<Windows::Storage::IApplicationData,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Storage::IApplicationData,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Storage::IApplicationData,IWeakReferenceSource,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Windows::Foundation::IClosable::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>_vtbl *)Windows::Storage::ApplicationDataServer::`vftable'{for `Windows::Foundation::IClosable'};
  this->Microsoft::WRL::RuntimeClass<Windows::Storage::IApplicationData,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Storage::IApplicationData,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Storage::IApplicationData,IWeakReferenceSource,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >::Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> > >::Microsoft::WRL::FtmBase::Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMarshal>::IMarshal::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >_vtbl *)Windows::Storage::ApplicationDataServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATASERVER_LIFESPAN_STOP);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&this->m_token);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&this->m_user);
  Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Storage::IApplicationDataContainer> *)&this->m_propertyValueStaticInterface);
  Windows::Storage::StateABIImplementation::DataChangedSignaler<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Windows::Storage::IApplicationData>::~DataChangedSignaler<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Windows::Storage::IApplicationData>(&this->m_dataChangedSignaler);
  hstring = this->m_packageFamilyNameForFullTrustActivation._hstring;
  if ( hstring )
    WindowsDeleteString(hstring);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&this->m_applicationStateHandle);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Storage::IApplicationData,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Storage::IApplicationData,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x18001aaf8  push    rbx
0x18001aafa  sub     rsp, 20h
0x18001aafe  lea     rax, ??_7ApplicationDataServer@Storage@Windows@@6BIApplicationData@12@@; const Windows::Storage::ApplicationDataServer::`vftable'{for `Windows::Storage::IApplicationData'}
0x18001ab05  mov     rbx, this
0x18001ab08  mov     [this], rax
0x18001ab0b  lea     rax, ??_7ApplicationDataServer@Storage@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIApplicationData2@Storage@Windows@@UIApplicationData3@67@UIClosable@Foundation@7@VFtmBase@23@@Details@WRL@Microsoft@@@; const Windows::Storage::ApplicationDataServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>'}
0x18001ab12  mov     [this+8], rax
0x18001ab16  lea     rax, ??_7ApplicationDataServer@Storage@Windows@@6BIApplicationData2@12@@; const Windows::Storage::ApplicationDataServer::`vftable'{for `Windows::Storage::IApplicationData2'}
0x18001ab1d  mov     [this+10h], rax
0x18001ab21  lea     rax, ??_7ApplicationDataServer@Storage@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIApplicationData3@Storage@Windows@@UIClosable@Foundation@6@VFtmBase@23@@Details@WRL@Microsoft@@@; const Windows::Storage::ApplicationDataServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>'}
0x18001ab28  mov     [this+18h], rax
0x18001ab2c  lea     rax, ??_7ApplicationDataServer@Storage@Windows@@6BIClosable@Foundation@2@@; const Windows::Storage::ApplicationDataServer::`vftable'{for `Windows::Foundation::IClosable'}
0x18001ab33  mov     [this+20h], rax
0x18001ab37  lea     rax, ??_7ApplicationDataServer@Storage@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Storage::ApplicationDataServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001ab3e  mov     [this+28h], rax
0x18001ab42  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATASERVER_LIFESPAN_STOP; eventDescriptor
0x18001ab49  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x18001ab4e  lea     this, [rbx+0E0h]; this
0x18001ab55  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001ab5a  lea     this, [rbx+0D8h]; this
0x18001ab61  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001ab66  lea     this, [rbx+0C8h]; this
0x18001ab6d  call    ?InternalRelease@?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>::InternalRelease(void)
0x18001ab72  lea     this, [rbx+68h]; this
0x18001ab76  call    ??1?$DataChangedSignaler@U?$ITypedEventHandler@PEAVApplicationData@Storage@Windows@@PEAUIInspectable@@@Foundation@Windows@@UIApplicationData@Storage@3@@StateABIImplementation@Storage@Windows@@QEAA@XZ; Windows::Storage::StateABIImplementation::DataChangedSignaler<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Windows::Storage::IApplicationData>::~DataChangedSignaler<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Windows::Storage::IApplicationData>(void)
0x18001ab7b  mov     this, [rbx+60h]; string
0x18001ab7f  test    this, this
0x18001ab82  jz      short loc_18001AB8A
0x18001ab84  call    cs:__imp_WindowsDeleteString
0x18001ab8a  lea     this, [rbx+58h]; this
0x18001ab8e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001ab93  mov     this, rbx
0x18001ab96  add     rsp, 20h
0x18001ab9a  pop     rbx
0x18001ab9b  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIApplicationData@Storage@Windows@@UIApplicationData2@56@UIApplicationData3@56@UIClosable@Foundation@6@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Storage::IApplicationData,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Storage::IApplicationData,Windows::Storage::IApplicationData2,Windows::Storage::IApplicationData3,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>(void)
```
