# Microsoft::WRL::Details::Make<Windows::Storage::ApplicationDataContainerSettingsServer,>(void)

- ea: `0x180008d20`
- end: `0x180008f77`
- name: `??$Make@VApplicationDataContainerSettingsServer@Storage@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VApplicationDataContainerSettingsServer@Storage@Windows@@@12@XZ`
- size: `599`
- prototype: `Microsoft::WRL::ComPtr<Windows::Storage::ApplicationDataContainerSettingsServer> *__fastcall(Microsoft::WRL::ComPtr<Windows::Storage::ApplicationDataContainerSettingsServer> *result)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ded0`

## callees

- `0x1800068d0`
- `0x180008d20`
- `0x180008f80`
- `0x180008fa4`
- `0x1800097b4`
- `0x1800254e8`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180008eb8`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180008ec5`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180008eb8`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180008ec5`
- `ntdll!EtwEventEnabled` at `0x180008ef0`
- `ntdll!EtwEventEnabled` at `0x180008ef0`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008f1b`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008f3f`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008f1b`
- `ntdll!RtlReleaseSRWLockShared` at `0x180008f3f`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008ed2`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008f55`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008ed2`
- `ntdll!RtlAcquireSRWLockShared` at `0x180008f55`
- `ntdll!EtwEventWrite` at `0x180008f0e`
- `ntdll!EtwEventWrite` at `0x180008f0e`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180008d91`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180008d91`

## pseudocode

```c
Microsoft::WRL::ComPtr<Windows::Storage::ApplicationDataContainerSettingsServer> *__fastcall Microsoft::WRL::Details::Make<Windows::Storage::ApplicationDataContainerSettingsServer,>(
        Microsoft::WRL::ComPtr<Windows::Storage::ApplicationDataContainerSettingsServer> *result)
{
  Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> *v2; // rax
  Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> *v3; // rdi
  Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> *> *v4; // rcx
  __int64 v5; // rcx
  __int64 *v6; // r14
  __int64 v7; // rcx
  Microsoft::WRL::ComPtr<Windows::Storage::ApplicationDataContainerSettingsServer> *v8; // rbx
  Windows::Storage::ApplicationDataContainerSettingsServer_vtbl *v9; // rbp
  Microsoft::WRL::ComPtr<Windows::Storage::ApplicationDataContainerSettingsServer> *v10; // rcx
  Microsoft::WRL::Details::ModuleBase *v11; // rcx
  unsigned __int64 v12; // rcx
  Microsoft::WRL::ComPtr<Windows::Storage::ApplicationDataContainerSettingsServer> *object; // [rsp+50h] [rbp+8h] BYREF

  result->ptr_ = 0;
  v2 = (Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> *)operator new(0x88u, &std::nothrow);
  v3 = v2;
  if ( !v2 )
    return result;
  Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>::IMap<HSTRING__ *,IInspectable *>(v2);
  Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>(v4 + 2);
  Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>::IKeyValuePair<HSTRING__ *,IInspectable *>((Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> *)&v3[3]);
  v6 = (__int64 *)(v5 + 40);
  object = 0;
  *(_QWORD *)(v5 + 16) = Microsoft::WRL::FtmBase::`vftable';
  *(_QWORD *)(v5 + 40) = 0;
  if ( CoCreateFreeThreadedMarshaler(0, (LPUNKNOWN *)&object) >= 0 )
  {
    v7 = *v6;
    v8 = object;
    v9 = object->ptr_->__vftable;
    if ( *v6 )
    {
      *v6 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    ((void (__fastcall *)(Microsoft::WRL::ComPtr<Windows::Storage::ApplicationDataContainerSettingsServer> *, GUID *, __int64 *))v9)(
      v8,
      &GUID_00000003_0000_0000_c000_000000000046,
      v6);
  }
  v10 = object;
  if ( object )
  {
    object = 0;
    ((void (__fastcall *)(Microsoft::WRL::ComPtr<Windows::Storage::ApplicationDataContainerSettingsServer> *))v10->ptr_->__vftable)(v10);
  }
  v11 = Microsoft::WRL::Details::ModuleBase::module_;
  v3->__vftable = (Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>_vtbl *)Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>'};
  v3[1].__vftable = (Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>_vtbl *)Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'};
  v3[2].__vftable = (Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>_vtbl *)Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>'};
  v3[3].__vftable = (Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>_vtbl *)Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'};
  v3[4].__vftable = (Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>_vtbl *)Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::Collections::IPropertySet'};
  v3[5].__vftable = (Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>_vtbl *)Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v3[10].__vftable = (Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>_vtbl *)1;
  if ( v11 )
    v11->IncrementObjectCount(v11);
  v3[11].__vftable = 0;
  v3->__vftable = (Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>_vtbl *)Windows::Storage::ApplicationDataContainerSettingsServer::`vftable'{for `Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>'};
  v3[1].__vftable = (Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>_vtbl *)Windows::Storage::ApplicationDataContainerSettingsServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'};
  v3[2].__vftable = (Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>_vtbl *)Windows::Storage::ApplicationDataContainerSettingsServer::`vftable'{for `Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>'};
  v3[3].__vftable = (Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>_vtbl *)Windows::Storage::ApplicationDataContainerSettingsServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'};
  v3[4].__vftable = (Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>_vtbl *)Windows::Storage::ApplicationDataContainerSettingsServer::`vftable'{for `Windows::Foundation::Collections::IPropertySet'};
  v3[5].__vftable = (Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>_vtbl *)Windows::Storage::ApplicationDataContainerSettingsServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v3[13].__vftable = 0;
  v3[14].__vftable = 0;
  InitializeSRWLock((PSRWLOCK)&v3[15]);
  InitializeSRWLock((PSRWLOCK)&v3[16]);
  RtlAcquireSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
  v12 = Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle;
  if ( Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle )
    goto LABEL_23;
  RtlReleaseSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
  if ( Windows::Storage::StateABIHelpers::Logging::Initialize() )
    goto LABEL_14;
  RtlAcquireSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
  v12 = Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle;
  if ( Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle )
  {
LABEL_23:
    if ( (unsigned __int8)EtwEventEnabled(
                            v12,
                            &APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LIFESPAN_START) )
      EtwEventWrite(
        Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle,
        &APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LIFESPAN_START,
        0,
        0);
  }
  RtlReleaseSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
LABEL_14:
  if ( result->ptr_ )
    result->ptr_->Release(result->ptr_);
  result->ptr_ = (Windows::Storage::ApplicationDataContainerSettingsServer *)v3;
  return result;
}

```

## disassembly

```asm
0x180008d20  push    rsi
0x180008d22  push    rdi
0x180008d23  push    r12
0x180008d25  sub     rsp, 30h
0x180008d29  mov     rsi, rcx
0x180008d2c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; __formal
0x180008d33  xor     r12d, r12d
0x180008d36  mov     [rcx], r12
0x180008d39  mov     ecx, 88h; count
0x180008d3e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008d43  mov     rdi, rax
0x180008d46  test    rax, rax
0x180008d49  jz      loc_180008F2C
0x180008d4f  mov     [rsp+48h+var_20], r14
0x180008d54  mov     rcx, rax; this
0x180008d57  mov     [rsp+48h+var_28], r15
0x180008d5c  call    ??0?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@QEAA@XZ; Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>::IMap<HSTRING__ *,IInspectable *>(void)
0x180008d61  lea     rcx, [rcx+10h]; this
0x180008d65  call    ??0?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@QEAA@XZ; Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>(void)
0x180008d6a  lea     rcx, [rdi+18h]; this
0x180008d6e  call    ??0?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@QEAA@XZ; Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>::IKeyValuePair<HSTRING__ *,IInspectable *>(void)
0x180008d73  lea     r14, [rcx+28h]
0x180008d77  mov     [rsp+48h+object], r12
0x180008d7c  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180008d83  mov     [rcx+10h], rax
0x180008d87  lea     rdx, [rsp+48h+object]; ppunkMarshal
0x180008d8c  xor     ecx, ecx; punkOuter
0x180008d8e  mov     [r14], r12
0x180008d91  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180008d97  test    eax, eax
0x180008d99  js      short loc_180008DE6
0x180008d9b  mov     rcx, [r14]
0x180008d9e  mov     [rsp+48h+arg_8], rbx
0x180008da3  mov     rbx, [rsp+48h+object]
0x180008da8  mov     [rsp+48h+arg_10], rbp
0x180008dad  mov     rax, [rbx]
0x180008db0  mov     rbp, [rax]
0x180008db3  test    rcx, rcx
0x180008db6  jz      short loc_180008DC7
0x180008db8  mov     [r14], r12
0x180008dbb  mov     rdx, [rcx]
0x180008dbe  mov     rax, [rdx+10h]
0x180008dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dc7  mov     r8, r14
0x180008dca  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180008dd1  mov     rcx, rbx
0x180008dd4  mov     rax, rbp
0x180008dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ddc  mov     rbp, [rsp+48h+arg_10]
0x180008de1  mov     rbx, [rsp+48h+arg_8]
0x180008de6  mov     rcx, [rsp+48h+object]
0x180008deb  mov     r14, [rsp+48h+var_20]
0x180008df0  test    rcx, rcx
0x180008df3  jz      short loc_180008E06
0x180008df5  mov     [rsp+48h+object], r12
0x180008dfa  mov     rax, [rcx]
0x180008dfd  mov     rax, [rax+10h]
0x180008e01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e06  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180008e0d  lea     rax, ??_7?$RuntimeClass@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@234@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@234@UIPropertySet@234@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>'}
0x180008e14  mov     [rdi], rax
0x180008e17  lea     rax, ??_7?$RuntimeClass@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@234@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@234@UIPropertySet@234@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@678@UIPropertySet@678@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'}
0x180008e1e  mov     [rdi+8], rax
0x180008e22  lea     rax, ??_7?$RuntimeClass@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@234@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@234@UIPropertySet@234@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>'}
0x180008e29  mov     [rdi+10h], rax
0x180008e2d  lea     rax, ??_7?$RuntimeClass@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@234@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@234@UIPropertySet@234@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@UIPropertySet@567@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'}
0x180008e34  mov     [rdi+18h], rax
0x180008e38  lea     rax, ??_7?$RuntimeClass@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@234@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@234@UIPropertySet@234@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6BIPropertySet@Collections@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::Collections::IPropertySet'}
0x180008e3f  mov     [rdi+20h], rax
0x180008e43  lea     rax, ??_7?$RuntimeClass@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@234@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@234@UIPropertySet@234@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180008e4a  mov     [rdi+28h], rax
0x180008e4e  mov     qword ptr [rdi+50h], 1
0x180008e56  test    rcx, rcx
0x180008e59  jz      short loc_180008E67
0x180008e5b  mov     rax, [rcx]
0x180008e5e  mov     rax, [rax+8]
0x180008e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e67  mov     [rdi+58h], r12
0x180008e6b  lea     rax, ??_7ApplicationDataContainerSettingsServer@Storage@Windows@@6B?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@2@@; const Windows::Storage::ApplicationDataContainerSettingsServer::`vftable'{for `Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>'}
0x180008e72  mov     [rdi], rax
0x180008e75  lea     rcx, [rdi+78h]; SRWLock
0x180008e79  lea     rax, ??_7ApplicationDataContainerSettingsServer@Storage@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@678@UIPropertySet@678@VFtmBase@23@@Details@WRL@Microsoft@@@; const Windows::Storage::ApplicationDataContainerSettingsServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'}
0x180008e80  mov     [rdi+8], rax
0x180008e84  lea     rax, ??_7ApplicationDataContainerSettingsServer@Storage@Windows@@6B?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@2@@; const Windows::Storage::ApplicationDataContainerSettingsServer::`vftable'{for `Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>'}
0x180008e8b  mov     [rdi+10h], rax
0x180008e8f  lea     rax, ??_7ApplicationDataContainerSettingsServer@Storage@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@UIPropertySet@567@VFtmBase@23@@Details@WRL@Microsoft@@@; const Windows::Storage::ApplicationDataContainerSettingsServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'}
0x180008e96  mov     [rdi+18h], rax
0x180008e9a  lea     rax, ??_7ApplicationDataContainerSettingsServer@Storage@Windows@@6BIPropertySet@Collections@Foundation@2@@; const Windows::Storage::ApplicationDataContainerSettingsServer::`vftable'{for `Windows::Foundation::Collections::IPropertySet'}
0x180008ea1  mov     [rdi+20h], rax
0x180008ea5  lea     rax, ??_7ApplicationDataContainerSettingsServer@Storage@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Storage::ApplicationDataContainerSettingsServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180008eac  mov     [rdi+28h], rax
0x180008eb0  mov     [rdi+68h], r12
0x180008eb4  mov     [rdi+70h], r12
0x180008eb8  call    cs:__imp_InitializeSRWLock
0x180008ebe  lea     rcx, [rdi+80h]; SRWLock
0x180008ec5  call    cs:__imp_InitializeSRWLock
0x180008ecb  lea     rcx, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x180008ed2  call    cs:__imp_RtlAcquireSRWLockShared
0x180008ed8  mov     rcx, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x180008edf  mov     r15, [rsp+48h+var_28]
0x180008ee4  test    rcx, rcx
0x180008ee7  jz      short loc_180008F38
0x180008ee9  lea     rdx, APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LIFESPAN_START
0x180008ef0  call    cs:__imp_EtwEventEnabled
0x180008ef6  test    al, al
0x180008ef8  jz      short loc_180008F14
0x180008efa  mov     rcx, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x180008f01  lea     rdx, APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LIFESPAN_START
0x180008f08  xor     r9d, r9d
0x180008f0b  xor     r8d, r8d
0x180008f0e  call    cs:__imp_EtwEventWrite
0x180008f14  lea     rcx, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x180008f1b  call    cs:__imp_RtlReleaseSRWLockShared
0x180008f21  mov     rcx, [rsi]
0x180008f24  test    rcx, rcx
0x180008f27  jnz     short loc_180008F69
0x180008f29  mov     [rsi], rdi
0x180008f2c  mov     rax, rsi
0x180008f2f  add     rsp, 30h
0x180008f33  pop     r12
0x180008f35  pop     rdi
0x180008f36  pop     rsi
0x180008f37  retn
0x180008f38  lea     rcx, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x180008f3f  call    cs:__imp_RtlReleaseSRWLockShared
0x180008f45  call    ?Initialize@Logging@StateABIHelpers@Storage@Windows@@CAJXZ; Windows::Storage::StateABIHelpers::Logging::Initialize(void)
0x180008f4a  test    eax, eax
0x180008f4c  jnz     short loc_180008F21
0x180008f4e  lea     rcx, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x180008f55  call    cs:__imp_RtlAcquireSRWLockShared
0x180008f5b  mov     rcx, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x180008f62  test    rcx, rcx
0x180008f65  jnz     short loc_180008EE9
0x180008f67  jmp     short loc_180008F14
0x180008f69  mov     rax, [rcx]
0x180008f6c  mov     rax, [rax+10h]
0x180008f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f75  jmp     short loc_180008F29
```
