# Windows::Storage::ApplicationDataCompositeValueServer::`vector deleting destructor'(uint)

- ea: `0x180004630`
- end: `0x1800047be`
- name: `??_EApplicationDataCompositeValueServer@Storage@Windows@@UEAAPEAXI@Z`
- size: `398`
- prototype: `Windows::Storage::ApplicationDataCompositeValueServer *__fastcall(Windows::Storage::ApplicationDataCompositeValueServer *this, char)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180004630`
- `0x180004870`
- `0x1800097b4`
- `0x18000f7b0`
- `0x180025004`
- `0x180042010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x1800046b4`
- `ntdll!EtwEventEnabled` at `0x1800046b4`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800046df`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000476e`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800046df`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000476e`
- `ntdll!RtlAcquireSRWLockShared` at `0x180004697`
- `ntdll!RtlAcquireSRWLockShared` at `0x180004788`
- `ntdll!RtlAcquireSRWLockShared` at `0x180004697`
- `ntdll!RtlAcquireSRWLockShared` at `0x180004788`
- `ntdll!EtwEventWrite` at `0x1800046d2`
- `ntdll!EtwEventWrite` at `0x1800046d2`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CloseStateAtom` at `0x1800046f0`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CloseStateAtom` at `0x1800046f0`

## pseudocode

```c
Windows::Storage::ApplicationDataCompositeValueServer *__fastcall Windows::Storage::ApplicationDataCompositeValueServer::`vector deleting destructor'(
        Windows::Storage::ApplicationDataCompositeValueServer *this,
        char a2)
{
  unsigned __int64 v4; // rcx
  Microsoft::WRL::Details::EventTargetArray *ptr; // rcx
  Windows::Foundation::IPropertyValueStatics *v6; // rcx
  Microsoft::WRL::Details::ReferenceCountOrWeakReferencePointer v7; // rcx
  IMarshal *v8; // rcx

  this->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>::Windows::Foundation::Collections::IMap_impl<HSTRING__ *,IInspectable *>::IInspectable::IUnknown::__vftable = (Windows::Storage::ApplicationDataCompositeValueServer_vtbl *)Windows::Storage::ApplicationDataCompositeValueServer::`vftable';
  this->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::IWeakReferenceSource::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>_vtbl *)Windows::Storage::ApplicationDataCompositeValueServer::`vftable'{for `IWeakReferenceSource'};
  this->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>::Windows::Foundation::Collections::IIterable_impl<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>_vtbl *)Windows::Storage::ApplicationDataCompositeValueServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>'};
  this->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>::Windows::Foundation::Collections::IObservableMap_impl<HSTRING__ *,IInspectable *>::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>_vtbl *)Windows::Storage::ApplicationDataCompositeValueServer::`vftable'{for `Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>'};
  this->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Windows::Foundation::Collections::IPropertySet::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>_vtbl *)Windows::Storage::ApplicationDataCompositeValueServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>'};
  this->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Windows::Storage::Private::IApplicationDataCompositeValueInternal::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>_vtbl *)Windows::Storage::ApplicationDataCompositeValueServer::`vftable'{for `Windows::Storage::Private::IApplicationDataCompositeValueInternal'};
  this->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >::Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> > >::Microsoft::WRL::FtmBase::Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMarshal>::IMarshal::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >_vtbl *)Windows::Storage::ApplicationDataCompositeValueServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  RtlAcquireSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
  v4 = Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle;
  if ( Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle )
    goto LABEL_2;
  RtlReleaseSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
  if ( !Windows::Storage::StateABIHelpers::Logging::Initialize() )
  {
    RtlAcquireSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
    v4 = Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle;
    if ( !Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle )
    {
LABEL_4:
      RtlReleaseSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
      goto LABEL_5;
    }
LABEL_2:
    if ( (unsigned __int8)EtwEventEnabled(v4, &APPMODELSTATE_WINRT_APPLICATIONDATACOMPOSITEVALUESERVER_LIFESPAN_STOP) )
      EtwEventWrite(
        Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle,
        &APPMODELSTATE_WINRT_APPLICATIONDATACOMPOSITEVALUESERVER_LIFESPAN_STOP,
        0,
        0);
    goto LABEL_4;
  }
LABEL_5:
  if ( this->atomHandle )
  {
    CloseStateAtom();
    this->atomHandle = 0;
  }
  ptr = this->dataChangedSignaler.targets_.ptr_;
  if ( ptr )
  {
    this->dataChangedSignaler.targets_.ptr_ = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(ptr);
  }
  v6 = this->propertyValueStaticInterface.ptr_;
  if ( v6 )
  {
    this->propertyValueStaticInterface.ptr_ = 0;
    v6->Release(v6);
  }
  v7.refCount = (unsigned __int64)this->refCount_;
  if ( v7.rawValue < 0 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release((Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference> *)(2 * v7.refCount));
  v8 = this->marshaller_.ptr_;
  if ( v8 )
  {
    this->marshaller_.ptr_ = 0;
    v8->Release(v8);
  }
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180004630  mov     [rsp+arg_0], rbx
0x180004635  mov     [rsp+arg_8], rsi
0x18000463a  push    rdi
0x18000463b  sub     rsp, 20h
0x18000463f  lea     rax, ??_7ApplicationDataCompositeValueServer@Storage@Windows@@6B@; const Windows::Storage::ApplicationDataCompositeValueServer::`vftable'
0x180004646  mov     rbx, this
0x180004649  mov     [this], rax
0x18000464c  mov     edi, edx
0x18000464e  lea     rax, ??_7ApplicationDataCompositeValueServer@Storage@Windows@@6BIWeakReferenceSource@@@; const Windows::Storage::ApplicationDataCompositeValueServer::`vftable'{for `IWeakReferenceSource'}
0x180004655  mov     [this+8], rax
0x180004659  lea     rax, ??_7ApplicationDataCompositeValueServer@Storage@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@567@UIPropertySet@567@UIApplicationDataCompositeValueInternal@Private@Storage@7@VFtmBase@23@@Details@WRL@Microsoft@@@; const Windows::Storage::ApplicationDataCompositeValueServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>'}
0x180004660  mov     [this+10h], rax
0x180004664  lea     rax, ??_7ApplicationDataCompositeValueServer@Storage@Windows@@6B?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@2@@; const Windows::Storage::ApplicationDataCompositeValueServer::`vftable'{for `Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>'}
0x18000466b  mov     [this+18h], rax
0x18000466f  lea     rax, ??_7ApplicationDataCompositeValueServer@Storage@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIPropertySet@Collections@Foundation@Windows@@UIApplicationDataCompositeValueInternal@Private@Storage@7@VFtmBase@23@@Details@WRL@Microsoft@@@; const Windows::Storage::ApplicationDataCompositeValueServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>'}
0x180004676  mov     [this+20h], rax
0x18000467a  lea     rax, ??_7ApplicationDataCompositeValueServer@Storage@Windows@@6BIApplicationDataCompositeValueInternal@Private@12@@; const Windows::Storage::ApplicationDataCompositeValueServer::`vftable'{for `Windows::Storage::Private::IApplicationDataCompositeValueInternal'}
0x180004681  mov     [this+28h], rax
0x180004685  lea     rax, ??_7ApplicationDataCompositeValueServer@Storage@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Storage::ApplicationDataCompositeValueServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000468c  mov     [this+30h], rax
0x180004690  lea     this, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x180004697  call    cs:__imp_RtlAcquireSRWLockShared
0x18000469d  mov     this, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x1800046a4  test    this, this
0x1800046a7  jz      loc_180004767
0x1800046ad  lea     rdx, APPMODELSTATE_WINRT_APPLICATIONDATACOMPOSITEVALUESERVER_LIFESPAN_STOP
0x1800046b4  call    cs:__imp_EtwEventEnabled
0x1800046ba  test    al, al
0x1800046bc  jz      short loc_1800046D8
0x1800046be  mov     this, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x1800046c5  lea     rdx, APPMODELSTATE_WINRT_APPLICATIONDATACOMPOSITEVALUESERVER_LIFESPAN_STOP
0x1800046cc  xor     r9d, r9d
0x1800046cf  xor     r8d, r8d
0x1800046d2  call    cs:__imp_EtwEventWrite
0x1800046d8  lea     this, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x1800046df  call    cs:__imp_RtlReleaseSRWLockShared
0x1800046e5  mov     this, [rbx+60h]
0x1800046e9  xor     esi, esi
0x1800046eb  test    this, this
0x1800046ee  jz      short loc_1800046FA
0x1800046f0  call    cs:__imp_CloseStateAtom
0x1800046f6  mov     [rbx+60h], rsi
0x1800046fa  mov     this, [rbx+70h]; this
0x1800046fe  test    this, this
0x180004701  jnz     loc_1800047A3
0x180004707  mov     this, [rbx+68h]
0x18000470b  test    this, this
0x18000470e  jz      short loc_180004720
0x180004710  mov     [rbx+68h], rsi
0x180004714  mov     rax, [this]
0x180004717  mov     rax, [rax+10h]
0x18000471b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004720  mov     this, [rbx+58h]
0x180004724  test    this, this
0x180004727  js      loc_1800047B1
0x18000472d  mov     this, [rbx+48h]
0x180004731  test    this, this
0x180004734  jz      short loc_180004746
0x180004736  mov     [rbx+48h], rsi
0x18000473a  mov     rax, [this]
0x18000473d  mov     rax, [rax+10h]
0x180004741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004746  test    dil, 1
0x18000474a  jz      short loc_180004754
0x18000474c  mov     this, rbx; p
0x18000474f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004754  mov     rsi, [rsp+28h+arg_8]
0x180004759  mov     rax, rbx
0x18000475c  mov     rbx, [rsp+28h+arg_0]
0x180004761  add     rsp, 20h
0x180004765  pop     rdi
0x180004766  retn
0x180004767  lea     this, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x18000476e  call    cs:__imp_RtlReleaseSRWLockShared
0x180004774  call    ?Initialize@Logging@StateABIHelpers@Storage@Windows@@CAJXZ; Windows::Storage::StateABIHelpers::Logging::Initialize(void)
0x180004779  test    eax, eax
0x18000477b  jnz     loc_1800046E5
0x180004781  lea     this, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x180004788  call    cs:__imp_RtlAcquireSRWLockShared
0x18000478e  mov     this, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x180004795  test    this, this
0x180004798  jnz     loc_1800046AD
0x18000479e  jmp     loc_1800046D8
0x1800047a3  mov     [rbx+70h], rsi
0x1800047a7  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x1800047ac  jmp     loc_180004707
0x1800047b1  add     this, this; this
0x1800047b4  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x1800047b9  jmp     loc_18000472D
```
