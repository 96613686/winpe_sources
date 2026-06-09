# CAudioSession::~CAudioSession(void)

- ea: `0x1800161bc`
- end: `0x1800163e2`
- name: `??1CAudioSession@@MEAA@XZ`
- size: `550`
- prototype: `void __fastcall(CAudioSession *__hidden this)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002dfcc`
- `0x1800b1038`
- `0x1800e66e0`

## callees

- `0x1800097c0`
- `0x18000accc`
- `0x1800151fc`
- `0x180016158`
- `0x180016188`
- `0x1800161bc`
- `0x180016554`
- `0x180018198`
- `0x18001d788`
- `0x18002d248`
- `0x18002e648`
- `0x180030a64`
- `0x180048e50`
- `0x18004f7e4`
- `0x1800605e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016285`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001629e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800162b7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800162d4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016305`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016312`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001636e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800163b2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016285`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001629e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800162b7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800162d4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016305`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016312`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001636e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800163b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016212`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001623c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016212`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001623c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001622c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800163cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001622c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800163cd`

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
0x1800161bc  push    rbx
0x1800161be  push    rbp
0x1800161bf  push    rsi
0x1800161c0  push    rdi
0x1800161c1  push    r14
0x1800161c3  sub     rsp, 20h
0x1800161c7  lea     rax, ??_7CAudioSession@@6BIInspectable@@@; const CAudioSession::`vftable'{for `IInspectable'}
0x1800161ce  mov     rbx, rcx
0x1800161d1  mov     [rcx], rax
0x1800161d4  lea     rbp, [rcx+40h]
0x1800161d8  lea     rax, ??_7CAudioSession@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ChainInterfaces@UIAudioSessionPolicyControl@@UIAudioSessionInfo@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIWeakReferenceSource@@UIAudioSessionInfoInternal@@UIAudioSessionDuckingControl@@UIInspectable@@@Details@WRL@Microsoft@@@; const CAudioSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::ChainInterfaces<IAudioSessionPolicyControl,IAudioSessionInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IWeakReferenceSource,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>'}
0x1800161df  mov     [rcx+8], rax
0x1800161e3  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$ChainInterfaces@UIAudioSessionPolicyControl@@UIAudioSessionInfo@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIAudioSessionInfoInternal@@UIAudioSessionDuckingControl@@UIInspectable@@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::ChainInterfaces<IAudioSessionPolicyControl,IAudioSessionInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>::`vftable'{for `IWeakReferenceSource'}
0x1800161ea  mov     [rcx+10h], rax
0x1800161ee  lea     rax, ??_7CAudioSession@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAudioSessionInfoInternal@@UIAudioSessionDuckingControl@@UIInspectable@@@Details@WRL@Microsoft@@@; const CAudioSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>'}
0x1800161f5  mov     [rcx+18h], rax
0x1800161f9  lea     rax, ??_7CAudioSession@@6BIAudioSessionDuckingControl@@@; const CAudioSession::`vftable'{for `IAudioSessionDuckingControl'}
0x180016200  mov     [rcx+20h], rax
0x180016204  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$ChainInterfaces@UIAudioSessionPolicyControl@@UIAudioSessionInfo@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIAudioSessionInfoInternal@@UIAudioSessionDuckingControl@@UIInspectable@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIInspectable@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::ChainInterfaces<IAudioSessionPolicyControl,IAudioSessionInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IInspectable>'}
0x18001620b  mov     [rcx+28h], rax
0x18001620f  mov     rcx, rbp; lpCriticalSection
0x180016212  call    cs:__imp_EnterCriticalSection
0x180016218  lea     rsi, [rbx+70h]
0x18001621c  mov     rcx, rsi
0x18001621f  call    ?clear@?$vector@V?$com_ptr_t@VCAudioStream@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCAudioStream@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAAXXZ; std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::clear(void)
0x180016224  test    rbp, rbp
0x180016227  jz      short loc_180016232
0x180016229  mov     rcx, rbp; lpCriticalSection
0x18001622c  call    cs:__imp_LeaveCriticalSection
0x180016232  lea     rdi, [rbx+88h]
0x180016239  mov     rcx, rdi; lpCriticalSection
0x18001623c  call    cs:__imp_EnterCriticalSection
0x180016242  lea     r14, [rbx+0B0h]
0x180016249  mov     rcx, r14
0x18001624c  call    ?clear@?$vector@V?$com_ptr_t@VCAudioStream@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCAudioStream@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAAXXZ; std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::clear(void)
0x180016251  test    rdi, rdi
0x180016254  jnz     loc_1800163CA
0x18001625a  lea     rcx, [rbx+390h]
0x180016261  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180016266  lea     rcx, [rbx+380h]
0x18001626d  call    ??1?$unique_ptr@$$BY0A@MU?$default_delete@$$BY0A@M@std@@@std@@QEAA@XZ; std::unique_ptr<float [0]>::~unique_ptr<float [0]>(void)
0x180016272  lea     rcx, [rbx+318h]; this
0x180016279  call    ??1AudioSrvVolumeTelemetrySessionVolume@@QEAA@XZ; AudioSrvVolumeTelemetrySessionVolume::~AudioSrvVolumeTelemetrySessionVolume(void)
0x18001627e  lea     rcx, [rbx+2E0h]; lpCriticalSection
0x180016285  call    cs:__imp_DeleteCriticalSection
0x18001628b  lea     rcx, [rbx+2C0h]
0x180016292  call    ?_Tidy@?$vector@V?$com_ptr_t@UIAudioProcess@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIAudioProcess@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::com_ptr_t<IAudioProcess,wil::err_returncode_policy>>::_Tidy(void)
0x180016297  lea     rcx, [rbx+298h]; lpCriticalSection
0x18001629e  call    cs:__imp_DeleteCriticalSection
0x1800162a4  lea     rcx, [rbx+248h]; this
0x1800162ab  call    ??1CAudioSessionInstanceId@@QEAA@XZ; CAudioSessionInstanceId::~CAudioSessionInstanceId(void)
0x1800162b0  lea     rcx, [rbx+220h]; lpCriticalSection
0x1800162b7  call    cs:__imp_DeleteCriticalSection
0x1800162bd  mov     rdx, [rbx+218h]
0x1800162c4  test    rdx, rdx
0x1800162c7  jnz     loc_1800163D8
0x1800162cd  lea     rcx, [rbx+1F0h]; lpCriticalSection
0x1800162d4  call    cs:__imp_DeleteCriticalSection
0x1800162da  lea     rcx, [rbx+1B0h]
0x1800162e1  call    ??1?$CLockedList_UniqueValuesOnly@V?$CComPtr@UISessionInternalEvents@@@ATL@@$0A@@@QEAA@XZ; CLockedList_UniqueValuesOnly<ATL::CComPtr<ISessionInternalEvents>,0>::~CLockedList_UniqueValuesOnly<ATL::CComPtr<ISessionInternalEvents>,0>(void)
0x1800162e6  lea     rcx, [rbx+1A0h]
0x1800162ed  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800162f2  lea     rcx, [rbx+190h]
0x1800162f9  call    ?clear@?$forward_list@V?$com_ptr_t@VCPBMStreamClassVolumeGainStage@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCPBMStreamClassVolumeGainStage@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAAXXZ; std::forward_list<wil::com_ptr_t<CPBMStreamClassVolumeGainStage,wil::err_returncode_policy>>::clear(void)
0x1800162fe  lea     rcx, [rbx+168h]; lpCriticalSection
0x180016305  call    cs:__imp_DeleteCriticalSection
0x18001630b  lea     rcx, [rbx+118h]; lpCriticalSection
0x180016312  call    cs:__imp_DeleteCriticalSection
0x180016318  lea     rcx, [rbx+100h]
0x18001631f  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180016324  lea     rcx, [rbx+0F8h]
0x18001632b  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180016330  mov     rcx, [r14]
0x180016333  test    rcx, rcx
0x180016336  jz      short loc_18001636B
0x180016338  mov     rdx, [r14+8]
0x18001633c  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>>(wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> *,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> * const,std::allocator<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>> &)
0x180016341  mov     rdx, [r14+10h]
0x180016345  sub     rdx, [r14]
0x180016348  mov     rcx, [r14]
0x18001634b  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001634f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180016354  mov     qword ptr [r14], 0
0x18001635b  mov     qword ptr [r14+8], 0
0x180016363  mov     qword ptr [r14+10h], 0
0x18001636b  mov     rcx, rdi; lpCriticalSection
0x18001636e  call    cs:__imp_DeleteCriticalSection
0x180016374  mov     rcx, [rsi]
0x180016377  test    rcx, rcx
0x18001637a  jz      short loc_1800163AF
0x18001637c  mov     rdx, [rsi+8]
0x180016380  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>>(wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> *,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> * const,std::allocator<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>> &)
0x180016385  mov     rdx, [rsi+10h]
0x180016389  sub     rdx, [rsi]
0x18001638c  mov     rcx, [rsi]
0x18001638f  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180016393  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180016398  mov     qword ptr [rsi], 0
0x18001639f  mov     qword ptr [rsi+8], 0
0x1800163a7  mov     qword ptr [rsi+10h], 0
0x1800163af  mov     rcx, rbp; lpCriticalSection
0x1800163b2  call    cs:__imp_DeleteCriticalSection
0x1800163b8  mov     rcx, rbx
0x1800163bb  add     rsp, 20h
0x1800163bf  pop     r14
0x1800163c1  pop     rdi
0x1800163c2  pop     rsi
0x1800163c3  pop     rbp
0x1800163c4  pop     rbx
0x1800163c5  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$ChainInterfaces@UIAudioSessionPolicyControl@@UIAudioSessionInfo@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIAudioSessionInfoInternal@@UIAudioSessionDuckingControl@@UIInspectable@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<IAudioSessionPolicyControl,IAudioSessionInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<IAudioSessionPolicyControl,IAudioSessionInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioSessionInfoInternal,IAudioSessionDuckingControl,IInspectable>(void)
0x1800163ca  mov     rcx, rdi; lpCriticalSection
0x1800163cd  call    cs:__imp_LeaveCriticalSection
0x1800163d3  jmp     loc_18001625A
0x1800163d8  call    ??R?$default_delete@U_RecurringTask@@@std@@QEBAXPEAU_RecurringTask@@@Z; std::default_delete<_RecurringTask>::operator()(_RecurringTask *)
0x1800163dd  jmp     loc_1800162CD
```
