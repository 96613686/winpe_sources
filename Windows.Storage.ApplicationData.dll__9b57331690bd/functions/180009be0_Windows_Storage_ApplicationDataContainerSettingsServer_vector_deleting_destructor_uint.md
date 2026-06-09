# Windows::Storage::ApplicationDataContainerSettingsServer::`vector deleting destructor'(uint)

- ea: `0x180009be0`
- end: `0x180009d30`
- name: `??_EApplicationDataContainerSettingsServer@Storage@Windows@@UEAAPEAXI@Z`
- size: `336`
- prototype: `Windows::Storage::ApplicationDataContainerSettingsServer *__fastcall(Windows::Storage::ApplicationDataContainerSettingsServer *this, char)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180004870`
- `0x1800097b4`
- `0x180009be0`
- `0x180009d40`
- `0x180025004`
- `0x180042010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180009c6e`
- `ntdll!EtwEventEnabled` at `0x180009c6e`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009c99`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009cf1`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009c99`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009cf1`
- `ntdll!RtlAcquireSRWLockShared` at `0x180009c51`
- `ntdll!RtlAcquireSRWLockShared` at `0x180009d07`
- `ntdll!RtlAcquireSRWLockShared` at `0x180009c51`
- `ntdll!RtlAcquireSRWLockShared` at `0x180009d07`
- `ntdll!EtwEventWrite` at `0x180009c8c`
- `ntdll!EtwEventWrite` at `0x180009c8c`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CloseStateContainer` at `0x180009c40`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CloseStateContainer` at `0x180009c40`

## pseudocode

```c
Windows::Storage::ApplicationDataContainerSettingsServer *__fastcall Windows::Storage::ApplicationDataContainerSettingsServer::`vector deleting destructor'(
        Windows::Storage::ApplicationDataContainerSettingsServer *this,
        char a2)
{
  unsigned __int64 v4; // rcx
  Microsoft::WRL::Details::EventTargetArray *ptr; // rcx
  Windows::Foundation::IPropertyValueStatics *v6; // rcx

  this->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>::Windows::Foundation::Collections::IMap_impl<HSTRING__ *,IInspectable *>::IInspectable::IUnknown::__vftable = (Windows::Storage::ApplicationDataContainerSettingsServer_vtbl *)Windows::Storage::ApplicationDataContainerSettingsServer::`vftable'{for `Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>'};
  this->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::IWeakReferenceSource::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>_vtbl *)Windows::Storage::ApplicationDataContainerSettingsServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'};
  this->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>::Windows::Foundation::Collections::IIterable_impl<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>_vtbl *)Windows::Storage::ApplicationDataContainerSettingsServer::`vftable'{for `Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>'};
  this->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>::Windows::Foundation::Collections::IObservableMap_impl<HSTRING__ *,IInspectable *>::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>_vtbl *)Windows::Storage::ApplicationDataContainerSettingsServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'};
  this->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Windows::Foundation::Collections::IPropertySet::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>_vtbl *)Windows::Storage::ApplicationDataContainerSettingsServer::`vftable'{for `Windows::Foundation::Collections::IPropertySet'};
  this->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >::Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> > >::Microsoft::WRL::FtmBase::Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMarshal>::IMarshal::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >_vtbl *)Windows::Storage::ApplicationDataContainerSettingsServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( this->m_containerHandle )
  {
    CloseStateContainer();
    this->m_containerHandle = 0;
  }
  RtlAcquireSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
  v4 = Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle;
  if ( Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle )
    goto LABEL_4;
  RtlReleaseSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
  if ( !Windows::Storage::StateABIHelpers::Logging::Initialize() )
  {
    RtlAcquireSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
    v4 = Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle;
    if ( !Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle )
    {
LABEL_6:
      RtlReleaseSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
      goto LABEL_7;
    }
LABEL_4:
    if ( (unsigned __int8)EtwEventEnabled(v4, &APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LIFESPAN_STOP) )
      EtwEventWrite(
        Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle,
        &APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LIFESPAN_STOP,
        0,
        0);
    goto LABEL_6;
  }
LABEL_7:
  ptr = this->m_dataChangedSignaler.targets_.ptr_;
  if ( ptr )
  {
    this->m_dataChangedSignaler.targets_.ptr_ = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(ptr);
  }
  v6 = this->m_propertyValueStaticInterface.ptr_;
  if ( v6 )
  {
    this->m_propertyValueStaticInterface.ptr_ = 0;
    v6->Release(v6);
  }
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180009be0  mov     [rsp+arg_0], rbx
0x180009be5  mov     [rsp+arg_8], rsi
0x180009bea  push    rdi
0x180009beb  sub     rsp, 20h
0x180009bef  lea     rax, ??_7ApplicationDataContainerSettingsServer@Storage@Windows@@6B?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@2@@; const Windows::Storage::ApplicationDataContainerSettingsServer::`vftable'{for `Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>'}
0x180009bf6  mov     rbx, this
0x180009bf9  mov     [this], rax
0x180009bfc  xor     esi, esi
0x180009bfe  lea     rax, ??_7ApplicationDataContainerSettingsServer@Storage@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@678@UIPropertySet@678@VFtmBase@23@@Details@WRL@Microsoft@@@; const Windows::Storage::ApplicationDataContainerSettingsServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'}
0x180009c05  mov     edi, edx
0x180009c07  mov     [this+8], rax
0x180009c0b  lea     rax, ??_7ApplicationDataContainerSettingsServer@Storage@Windows@@6B?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@2@@; const Windows::Storage::ApplicationDataContainerSettingsServer::`vftable'{for `Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>'}
0x180009c12  mov     [this+10h], rax
0x180009c16  lea     rax, ??_7ApplicationDataContainerSettingsServer@Storage@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@UIPropertySet@567@VFtmBase@23@@Details@WRL@Microsoft@@@; const Windows::Storage::ApplicationDataContainerSettingsServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'}
0x180009c1d  mov     [this+18h], rax
0x180009c21  lea     rax, ??_7ApplicationDataContainerSettingsServer@Storage@Windows@@6BIPropertySet@Collections@Foundation@2@@; const Windows::Storage::ApplicationDataContainerSettingsServer::`vftable'{for `Windows::Foundation::Collections::IPropertySet'}
0x180009c28  mov     [this+20h], rax
0x180009c2c  lea     rax, ??_7ApplicationDataContainerSettingsServer@Storage@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Storage::ApplicationDataContainerSettingsServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180009c33  mov     [this+28h], rax
0x180009c37  mov     this, [this+58h]
0x180009c3b  test    this, this
0x180009c3e  jz      short loc_180009C4A
0x180009c40  call    cs:__imp_CloseStateContainer
0x180009c46  mov     [rbx+58h], rsi
0x180009c4a  lea     this, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x180009c51  call    cs:__imp_RtlAcquireSRWLockShared
0x180009c57  mov     this, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x180009c5e  test    this, this
0x180009c61  jz      loc_180009CEA
0x180009c67  lea     rdx, APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LIFESPAN_STOP
0x180009c6e  call    cs:__imp_EtwEventEnabled
0x180009c74  test    al, al
0x180009c76  jz      short loc_180009C92
0x180009c78  mov     this, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x180009c7f  lea     rdx, APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LIFESPAN_STOP
0x180009c86  xor     r9d, r9d
0x180009c89  xor     r8d, r8d
0x180009c8c  call    cs:__imp_EtwEventWrite
0x180009c92  lea     this, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x180009c99  call    cs:__imp_RtlReleaseSRWLockShared
0x180009c9f  mov     this, [rbx+70h]; this
0x180009ca3  test    this, this
0x180009ca6  jnz     short loc_180009D22
0x180009ca8  mov     this, [rbx+68h]
0x180009cac  test    this, this
0x180009caf  jz      short loc_180009CC1
0x180009cb1  mov     [rbx+68h], rsi
0x180009cb5  mov     rax, [this]
0x180009cb8  mov     rax, [rax+10h]
0x180009cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cc1  mov     this, rbx; this
0x180009cc4  call    ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@567@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@567@UIPropertySet@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>(void)
0x180009cc9  test    dil, 1
0x180009ccd  jz      short loc_180009CD7
0x180009ccf  mov     this, rbx; p
0x180009cd2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009cd7  mov     rsi, [rsp+28h+arg_8]
0x180009cdc  mov     rax, rbx
0x180009cdf  mov     rbx, [rsp+28h+arg_0]
0x180009ce4  add     rsp, 20h
0x180009ce8  pop     rdi
0x180009ce9  retn
0x180009cea  lea     this, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x180009cf1  call    cs:__imp_RtlReleaseSRWLockShared
0x180009cf7  call    ?Initialize@Logging@StateABIHelpers@Storage@Windows@@CAJXZ; Windows::Storage::StateABIHelpers::Logging::Initialize(void)
0x180009cfc  test    eax, eax
0x180009cfe  jnz     short loc_180009C9F
0x180009d00  lea     this, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x180009d07  call    cs:__imp_RtlAcquireSRWLockShared
0x180009d0d  mov     this, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x180009d14  test    this, this
0x180009d17  jnz     loc_180009C67
0x180009d1d  jmp     loc_180009C92
0x180009d22  mov     [rbx+70h], rsi
0x180009d26  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180009d2b  jmp     loc_180009CA8
```
