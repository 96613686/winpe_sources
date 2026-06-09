# Windows::Storage::ApplicationDataContainerServer::~ApplicationDataContainerServer(void)

- ea: `0x180013590`
- end: `0x1800136b9`
- name: `??1ApplicationDataContainerServer@Storage@Windows@@UEAA@XZ`
- size: `297`
- prototype: `void __fastcall(Windows::Storage::ApplicationDataContainerServer *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180013550`

## callees

- `0x1800092d0`
- `0x180013590`
- `0x180021fc4`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013616`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013616`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CloseStateContainer` at `0x1800135cd`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CloseStateContainer` at `0x1800135cd`

## pseudocode

```c
void __fastcall Windows::Storage::ApplicationDataContainerServer::~ApplicationDataContainerServer(
        Windows::Storage::ApplicationDataContainerServer *this)
{
  Windows::Foundation::IPropertyValueStatics *ptr; // rcx
  HSTRING__ *hstring; // rcx
  Microsoft::WRL::Details::ReferenceCountOrWeakReferencePointer v4; // r8
  volatile signed __int32 *v5; // r8
  signed __int32 i; // edx
  IMarshal *v7; // rcx

  this->Microsoft::WRL::RuntimeClass<Windows::Storage::IApplicationDataContainer,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Storage::IApplicationDataContainer,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Storage::IApplicationDataContainer,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Windows::Storage::IApplicationDataContainer::IInspectable::IUnknown::__vftable = (Windows::Storage::ApplicationDataContainerServer_vtbl *)Windows::Storage::ApplicationDataContainerServer::`vftable'{for `Windows::Storage::IApplicationDataContainer'};
  this->Microsoft::WRL::RuntimeClass<Windows::Storage::IApplicationDataContainer,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Storage::IApplicationDataContainer,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Storage::IApplicationDataContainer,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::IWeakReferenceSource::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>_vtbl *)Windows::Storage::ApplicationDataContainerServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>'};
  this->Microsoft::WRL::RuntimeClass<Windows::Storage::IApplicationDataContainer,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Storage::IApplicationDataContainer,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Storage::IApplicationDataContainer,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Windows::Foundation::IClosable::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>_vtbl *)Windows::Storage::ApplicationDataContainerServer::`vftable'{for `Windows::Foundation::IClosable'};
  this->Microsoft::WRL::RuntimeClass<Windows::Storage::IApplicationDataContainer,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Storage::IApplicationDataContainer,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Storage::IApplicationDataContainer,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >::Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> > >::Microsoft::WRL::FtmBase::Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMarshal>::IMarshal::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >_vtbl *)Windows::Storage::ApplicationDataContainerServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( this->m_containerHandle )
  {
    if ( !(unsigned int)CloseStateContainer() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    this->m_containerHandle = 0;
  }
  Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSERVER_LIFESPAN_STOP);
  ptr = this->m_propertyValueStaticInterface.ptr_;
  if ( ptr )
  {
    this->m_propertyValueStaticInterface.ptr_ = 0;
    ptr->Release(ptr);
  }
  hstring = this->m_name._hstring;
  if ( hstring )
    WindowsDeleteString(hstring);
  v4.refCount = (unsigned __int64)this->refCount_;
  if ( v4.rawValue < 0 )
  {
    v5 = (volatile signed __int32 *)(2 * v4.refCount);
    for ( i = *((_DWORD *)v5 + 3); i != 0x7FFFFFFF; i = *((_DWORD *)v5 + 3) )
    {
      if ( i == _InterlockedCompareExchange(v5 + 3, i - 1, i) )
        break;
    }
    if ( i == 1 )
    {
      if ( v5 )
        (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v5 + 32LL))(v5, 1);
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        Microsoft::WRL::Details::ModuleBase::module_->DecrementObjectCount(Microsoft::WRL::Details::ModuleBase::module_);
    }
  }
  v7 = this->marshaller_.ptr_;
  if ( v7 )
  {
    this->marshaller_.ptr_ = 0;
    v7->Release(v7);
  }
}

```

## disassembly

```asm
0x180013590  push    rbx
0x180013592  sub     rsp, 20h
0x180013596  lea     rax, ??_7ApplicationDataContainerServer@Storage@Windows@@6BIApplicationDataContainer@12@@; const Windows::Storage::ApplicationDataContainerServer::`vftable'{for `Windows::Storage::IApplicationDataContainer'}
0x18001359d  mov     rbx, this
0x1800135a0  mov     [this], rax
0x1800135a3  lea     rax, ??_7ApplicationDataContainerServer@Storage@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIClosable@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@; const Windows::Storage::ApplicationDataContainerServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::FtmBase>'}
0x1800135aa  mov     [this+8], rax
0x1800135ae  lea     rax, ??_7ApplicationDataContainerServer@Storage@Windows@@6BIClosable@Foundation@2@@; const Windows::Storage::ApplicationDataContainerServer::`vftable'{for `Windows::Foundation::IClosable'}
0x1800135b5  mov     [this+10h], rax
0x1800135b9  lea     rax, ??_7ApplicationDataContainerServer@Storage@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Storage::ApplicationDataContainerServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800135c0  mov     [this+18h], rax
0x1800135c4  mov     this, [this+58h]
0x1800135c8  test    this, this
0x1800135cb  jz      short loc_1800135E4
0x1800135cd  call    cs:__imp_CloseStateContainer
0x1800135d3  test    eax, eax
0x1800135d5  jnz     short loc_1800135DC
0x1800135d7  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "StateApiSet::CloseStateContainer(m_containerHandle)", "Failed to close state container handle")
0x1800135dc  mov     qword ptr [rbx+58h], 0
0x1800135e4  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSERVER_LIFESPAN_STOP; eventDescriptor
0x1800135eb  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x1800135f0  mov     this, [rbx+60h]
0x1800135f4  test    this, this
0x1800135f7  jz      short loc_18001360D
0x1800135f9  mov     qword ptr [rbx+60h], 0
0x180013601  mov     rax, [this]
0x180013604  mov     rax, [rax+10h]
0x180013608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001360d  mov     this, [rbx+48h]; string
0x180013611  test    this, this
0x180013614  jz      short loc_18001361C
0x180013616  call    cs:__imp_WindowsDeleteString
0x18001361c  mov     r8, [rbx+40h]
0x180013620  test    r8, r8
0x180013623  jns     short loc_180013691
0x180013625  add     r8, r8
0x180013628  mov     edx, [r8+0Ch]
0x18001362c  cmp     edx, 7FFFFFFFh
0x180013632  jz      short loc_180013659
0x180013634  nop     dword ptr [rax+00h]
0x180013638  nop     dword ptr [rax+rax+00000000h]
0x180013640  lea     ecx, [rdx-1]
0x180013643  mov     eax, edx
0x180013645  lock cmpxchg [r8+0Ch], ecx
0x18001364b  jz      short loc_180013659
0x18001364d  mov     edx, [r8+0Ch]
0x180013651  cmp     edx, 7FFFFFFFh
0x180013657  jnz     short loc_180013640
0x180013659  lea     eax, [rdx-1]
0x18001365c  test    eax, eax
0x18001365e  jnz     short loc_180013691
0x180013660  test    r8, r8
0x180013663  jz      short loc_180013679
0x180013665  mov     rax, [r8]
0x180013668  mov     edx, 1
0x18001366d  mov     this, r8
0x180013670  mov     rax, [rax+20h]
0x180013674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013679  mov     this, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180013680  test    this, this
0x180013683  jz      short loc_180013691
0x180013685  mov     rax, [this]
0x180013688  mov     rax, [rax+10h]
0x18001368c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013691  mov     this, [rbx+30h]
0x180013695  test    this, this
0x180013698  jz      short loc_1800136B3
0x18001369a  mov     qword ptr [rbx+30h], 0
0x1800136a2  mov     rax, [this]
0x1800136a5  mov     rax, [rax+10h]
0x1800136a9  add     rsp, 20h
0x1800136ad  pop     rbx
0x1800136ae  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800136b3  add     rsp, 20h
0x1800136b7  pop     rbx
0x1800136b8  retn
```
