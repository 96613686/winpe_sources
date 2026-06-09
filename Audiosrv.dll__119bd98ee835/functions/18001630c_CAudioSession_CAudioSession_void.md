# CAudioSession::~CAudioSession(void)

- ea: `0x18001630c`
- end: `0x180016532`
- name: `??1CAudioSession@@MEAA@XZ`
- size: `550`
- prototype: `void __fastcall(CAudioSession *__hidden this)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002e12c`
- `0x1800af348`
- `0x1800e5f60`

## callees

- `0x180009910`
- `0x18000ae1c`
- `0x18001534c`
- `0x1800162a8`
- `0x1800162d8`
- `0x18001630c`
- `0x1800166a4`
- `0x1800182e8`
- `0x18001d8d8`
- `0x18002d3a8`
- `0x18002e7a8`
- `0x180030bc4`
- `0x1800489c0`
- `0x18004f354`
- `0x180060150`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800163d5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800163ee`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016407`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016424`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016455`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016462`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800164be`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016502`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800163d5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800163ee`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016407`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016424`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016455`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016462`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800164be`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016502`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016362`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001638c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016362`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001638c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001637c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001651d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001637c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001651d`

## pseudocode

```c
void __fastcall CAudioSession::~CAudioSession(CAudioSession *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  _QWORD *v3; // rsi
  _QWORD *v4; // r14
  __int64 v5; // rcx
  __int64 v6; // rdx

  *(_QWORD *)this = &CAudioSession::`vftable'{for `IInspectable'};
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  *((_QWORD *)this + 1) = &CAudioSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::ChainInterfaces<IAudioSessionPolicyControl,IAudioSessionInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IWeakReferenceSource,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>'};
  *((_QWORD *)this + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::ChainInterfaces<IAudioSessionPolicyControl,IAudioSessionInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 3) = &CAudioSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>'};
  *((_QWORD *)this + 4) = &CAudioSession::`vftable'{for `IAudioSessionDuckingControl'};
  *((_QWORD *)this + 5) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::ChainInterfaces<IAudioSessionPolicyControl,IAudioSessionInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IInspectable>'};
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v3 = (_QWORD *)((char *)this + 112);
  std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::clear((char *)this + 112);
  if ( v2 )
    LeaveCriticalSection(v2);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v4 = (_QWORD *)((char *)this + 176);
  std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::clear((char *)this + 176);
  if ( this != (CAudioSession *)-136LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease((char *)this + 912);
  std::unique_ptr<float [0]>::~unique_ptr<float [0]>((char *)this + 896);
  AudioSrvVolumeTelemetrySessionVolume::~AudioSrvVolumeTelemetrySessionVolume((CAudioSession *)((char *)this + 792));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 736));
  std::vector<wil::com_ptr_t<IAudioProcess,wil::err_returncode_policy>>::_Tidy((char *)this + 704);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 664));
  CAudioSessionInstanceId::~CAudioSessionInstanceId((CAudioSession *)((char *)this + 584));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 544));
  v6 = *((_QWORD *)this + 67);
  if ( v6 )
    std::default_delete<_RecurringTask>::operator()(v5, v6);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 496));
  CLockedList_UniqueValuesOnly<ATL::CComPtr<ISessionInternalEvents>,0>::~CLockedList_UniqueValuesOnly<ATL::CComPtr<ISessionInternalEvents>,0>((char *)this + 432);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>((char *)this + 416);
  std::forward_list<wil::com_ptr_t<CPBMStreamClassVolumeGainStage,wil::err_returncode_policy>>::clear((char *)this + 400);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 9);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 7);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 256);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 248);
  if ( *v4 )
  {
    std::_Destroy_range<std::allocator<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>>(
      *v4,
      *((_QWORD *)this + 23));
    std::_Deallocate<16>(*v4, (*((_QWORD *)this + 24) - *((_QWORD *)this + 22)) & 0xFFFFFFFFFFFFFFF8uLL);
    *v4 = 0;
    *((_QWORD *)this + 23) = 0;
    *((_QWORD *)this + 24) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( *v3 )
  {
    std::_Destroy_range<std::allocator<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>>(
      *v3,
      *((_QWORD *)this + 15));
    std::_Deallocate<16>(*v3, (*((_QWORD *)this + 16) - *((_QWORD *)this + 14)) & 0xFFFFFFFFFFFFFFF8uLL);
    *v3 = 0;
    *((_QWORD *)this + 15) = 0;
    *((_QWORD *)this + 16) = 0;
  }
  DeleteCriticalSection(v2);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<IAudioSessionPolicyControl,IAudioSessionInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<IAudioSessionPolicyControl,IAudioSessionInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>(this);
}

```

## disassembly

```asm
0x18001630c  push    rbx
0x18001630e  push    rbp
0x18001630f  push    rsi
0x180016310  push    rdi
0x180016311  push    r14
0x180016313  sub     rsp, 20h
0x180016317  lea     rax, ??_7CAudioSession@@6BIInspectable@@@; const CAudioSession::`vftable'{for `IInspectable'}
0x18001631e  mov     rbx, rcx
0x180016321  mov     [rcx], rax
0x180016324  lea     rbp, [rcx+40h]
0x180016328  lea     rax, ??_7CAudioSession@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ChainInterfaces@UIAudioSessionPolicyControl@@UIAudioSessionInfo@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIWeakReferenceSource@@UIAudioSessionInfoInternal@@UIAudioSessionDuckingControl@@UIInspectable@@@Details@WRL@Microsoft@@@; const CAudioSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::ChainInterfaces<IAudioSessionPolicyControl,IAudioSessionInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IWeakReferenceSource,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>'}
0x18001632f  mov     [rcx+8], rax
0x180016333  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$ChainInterfaces@UIAudioSessionPolicyControl@@UIAudioSessionInfo@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIAudioSessionInfoInternal@@UIAudioSessionDuckingControl@@UIInspectable@@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::ChainInterfaces<IAudioSessionPolicyControl,IAudioSessionInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>::`vftable'{for `IWeakReferenceSource'}
0x18001633a  mov     [rcx+10h], rax
0x18001633e  lea     rax, ??_7CAudioSession@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAudioSessionInfoInternal@@UIAudioSessionDuckingControl@@UIInspectable@@@Details@WRL@Microsoft@@@; const CAudioSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>'}
0x180016345  mov     [rcx+18h], rax
0x180016349  lea     rax, ??_7CAudioSession@@6BIAudioSessionDuckingControl@@@; const CAudioSession::`vftable'{for `IAudioSessionDuckingControl'}
0x180016350  mov     [rcx+20h], rax
0x180016354  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$ChainInterfaces@UIAudioSessionPolicyControl@@UIAudioSessionInfo@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIAudioSessionInfoInternal@@UIAudioSessionDuckingControl@@UIInspectable@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIInspectable@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::ChainInterfaces<IAudioSessionPolicyControl,IAudioSessionInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IInspectable>'}
0x18001635b  mov     [rcx+28h], rax
0x18001635f  mov     rcx, rbp; lpCriticalSection
0x180016362  call    cs:__imp_EnterCriticalSection
0x180016368  lea     rsi, [rbx+70h]
0x18001636c  mov     rcx, rsi
0x18001636f  call    ?clear@?$vector@V?$com_ptr_t@VCAudioStream@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCAudioStream@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAAXXZ; std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::clear(void)
0x180016374  test    rbp, rbp
0x180016377  jz      short loc_180016382
0x180016379  mov     rcx, rbp; lpCriticalSection
0x18001637c  call    cs:__imp_LeaveCriticalSection
0x180016382  lea     rdi, [rbx+88h]
0x180016389  mov     rcx, rdi; lpCriticalSection
0x18001638c  call    cs:__imp_EnterCriticalSection
0x180016392  lea     r14, [rbx+0B0h]
0x180016399  mov     rcx, r14
0x18001639c  call    ?clear@?$vector@V?$com_ptr_t@VCAudioStream@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCAudioStream@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAAXXZ; std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::clear(void)
0x1800163a1  test    rdi, rdi
0x1800163a4  jnz     loc_18001651A
0x1800163aa  lea     rcx, [rbx+390h]
0x1800163b1  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800163b6  lea     rcx, [rbx+380h]
0x1800163bd  call    ??1?$unique_ptr@$$BY0A@MU?$default_delete@$$BY0A@M@std@@@std@@QEAA@XZ; std::unique_ptr<float [0]>::~unique_ptr<float [0]>(void)
0x1800163c2  lea     rcx, [rbx+318h]; this
0x1800163c9  call    ??1AudioSrvVolumeTelemetrySessionVolume@@QEAA@XZ; AudioSrvVolumeTelemetrySessionVolume::~AudioSrvVolumeTelemetrySessionVolume(void)
0x1800163ce  lea     rcx, [rbx+2E0h]; lpCriticalSection
0x1800163d5  call    cs:__imp_DeleteCriticalSection
0x1800163db  lea     rcx, [rbx+2C0h]
0x1800163e2  call    ?_Tidy@?$vector@V?$com_ptr_t@UIAudioProcess@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIAudioProcess@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::com_ptr_t<IAudioProcess,wil::err_returncode_policy>>::_Tidy(void)
0x1800163e7  lea     rcx, [rbx+298h]; lpCriticalSection
0x1800163ee  call    cs:__imp_DeleteCriticalSection
0x1800163f4  lea     rcx, [rbx+248h]; this
0x1800163fb  call    ??1CAudioSessionInstanceId@@QEAA@XZ; CAudioSessionInstanceId::~CAudioSessionInstanceId(void)
0x180016400  lea     rcx, [rbx+220h]; lpCriticalSection
0x180016407  call    cs:__imp_DeleteCriticalSection
0x18001640d  mov     rdx, [rbx+218h]
0x180016414  test    rdx, rdx
0x180016417  jnz     loc_180016528
0x18001641d  lea     rcx, [rbx+1F0h]; lpCriticalSection
0x180016424  call    cs:__imp_DeleteCriticalSection
0x18001642a  lea     rcx, [rbx+1B0h]
0x180016431  call    ??1?$CLockedList_UniqueValuesOnly@V?$CComPtr@UISessionInternalEvents@@@ATL@@$0A@@@QEAA@XZ; CLockedList_UniqueValuesOnly<ATL::CComPtr<ISessionInternalEvents>,0>::~CLockedList_UniqueValuesOnly<ATL::CComPtr<ISessionInternalEvents>,0>(void)
0x180016436  lea     rcx, [rbx+1A0h]
0x18001643d  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180016442  lea     rcx, [rbx+190h]
0x180016449  call    ?clear@?$forward_list@V?$com_ptr_t@VCPBMStreamClassVolumeGainStage@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCPBMStreamClassVolumeGainStage@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAAXXZ; std::forward_list<wil::com_ptr_t<CPBMStreamClassVolumeGainStage,wil::err_returncode_policy>>::clear(void)
0x18001644e  lea     rcx, [rbx+168h]; lpCriticalSection
0x180016455  call    cs:__imp_DeleteCriticalSection
0x18001645b  lea     rcx, [rbx+118h]; lpCriticalSection
0x180016462  call    cs:__imp_DeleteCriticalSection
0x180016468  lea     rcx, [rbx+100h]
0x18001646f  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180016474  lea     rcx, [rbx+0F8h]
0x18001647b  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180016480  mov     rcx, [r14]
0x180016483  test    rcx, rcx
0x180016486  jz      short loc_1800164BB
0x180016488  mov     rdx, [r14+8]
0x18001648c  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>>(wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> *,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> * const,std::allocator<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>> &)
0x180016491  mov     rdx, [r14+10h]
0x180016495  sub     rdx, [r14]
0x180016498  mov     rcx, [r14]
0x18001649b  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001649f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800164a4  mov     qword ptr [r14], 0
0x1800164ab  mov     qword ptr [r14+8], 0
0x1800164b3  mov     qword ptr [r14+10h], 0
0x1800164bb  mov     rcx, rdi; lpCriticalSection
0x1800164be  call    cs:__imp_DeleteCriticalSection
0x1800164c4  mov     rcx, [rsi]
0x1800164c7  test    rcx, rcx
0x1800164ca  jz      short loc_1800164FF
0x1800164cc  mov     rdx, [rsi+8]
0x1800164d0  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>>(wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> *,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> * const,std::allocator<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>> &)
0x1800164d5  mov     rdx, [rsi+10h]
0x1800164d9  sub     rdx, [rsi]
0x1800164dc  mov     rcx, [rsi]
0x1800164df  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800164e3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800164e8  mov     qword ptr [rsi], 0
0x1800164ef  mov     qword ptr [rsi+8], 0
0x1800164f7  mov     qword ptr [rsi+10h], 0
0x1800164ff  mov     rcx, rbp; lpCriticalSection
0x180016502  call    cs:__imp_DeleteCriticalSection
0x180016508  mov     rcx, rbx
0x18001650b  add     rsp, 20h
0x18001650f  pop     r14
0x180016511  pop     rdi
0x180016512  pop     rsi
0x180016513  pop     rbp
0x180016514  pop     rbx
0x180016515  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$ChainInterfaces@UIAudioSessionPolicyControl@@UIAudioSessionInfo@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIAudioSessionInfoInternal@@UIAudioSessionDuckingControl@@UIInspectable@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<IAudioSessionPolicyControl,IAudioSessionInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<IAudioSessionPolicyControl,IAudioSessionInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>(void)
0x18001651a  mov     rcx, rdi; lpCriticalSection
0x18001651d  call    cs:__imp_LeaveCriticalSection
0x180016523  jmp     loc_1800163AA
0x180016528  call    ??R?$default_delete@U_RecurringTask@@@std@@QEBAXPEAU_RecurringTask@@@Z; std::default_delete<_RecurringTask>::operator()(_RecurringTask *)
0x18001652d  jmp     loc_18001641D
```
