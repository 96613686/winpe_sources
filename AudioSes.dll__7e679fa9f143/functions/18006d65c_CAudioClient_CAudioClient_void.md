# CAudioClient::~CAudioClient(void)

- ea: `0x18006d65c`
- end: `0x18006d930`
- name: `??1CAudioClient@@MEAA@XZ`
- size: `724`
- prototype: `void __fastcall(CAudioClient *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800551a0`

## callees

- `0x180007f00`
- `0x18000cb1c`
- `0x18000d11c`
- `0x18000d244`
- `0x18000eae8`
- `0x1800154e0`
- `0x1800239ec`
- `0x18004a4a4`
- `0x18004bb74`
- `0x18004e488`
- `0x18004faac`
- `0x1800560bc`
- `0x18005e734`
- `0x18006d65c`
- `0x18006d978`
- `0x180087e80`
- `0x1800957d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006d887`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006d887`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006d75c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006d7a9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006d75c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006d7a9`
- `ntdll!NtDeleteWnfStateName` at `0x18006d816`
- `ntdll!NtDeleteWnfStateName` at `0x18006d816`
- `api-ms-win-power-base-l1-1-0!PowerUnregisterSuspendResumeNotification` at `0x18006d860`
- `api-ms-win-power-base-l1-1-0!PowerUnregisterSuspendResumeNotification` at `0x18006d860`
- `ext-ms-win-advapi32-psm-app-l1-1-0!PsmUnregisterAppStateChangeNotification` at `0x18006d86e`
- `ext-ms-win-advapi32-psm-app-l1-1-0!PsmUnregisterAppStateChangeNotification` at `0x18006d86e`

## pseudocode

```c
void __fastcall CAudioClient::~CAudioClient(CAudioClient *this)
{
  _QWORD *v2; // r14
  _QWORD *v3; // rsi
  wil::details **v4; // rdi
  struct wil::details::wnf_subscription_state_base *v5; // rdx
  void *v6; // rcx
  void *v7; // rdx
  wil::details *v8; // rcx
  void *v9; // rdx
  wil::details *v10; // rcx
  GUID ActivityId; // [rsp+30h] [rbp-38h] BYREF

  *(_QWORD *)this = &CAudioClient::`vftable'{for `IInspectable'};
  *((_QWORD *)this + 1) = &CAudioClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::ChainInterfaces<IAudioClient3,IAudioClient2,IAudioClient,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IWeakReferenceSource,IAudioClockAdjustment,IMFTrustedOutput,IAudioClientTrustedOutputPriv,IAudioClientInternal,IAudioClientTest,IAudioAmbisonicsControl,IAudioHistoryControl,ICrossVmMediaNotificationProducer,IAudioClientDuckingControl,IAudioEffectsManager,IAudioViewManagerService,IAcousticEchoCancellationControl,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::ChainInterfaces<IAudioClient3,IAudioClient2,IAudioClient,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioClockAdjustment,IMFTrustedOutput,IAudioClientTrustedOutputPriv,IAudioClientInternal,IAudioClientTest,IAudioAmbisonicsControl,IAudioHistoryControl,ICrossVmMediaNotificationProducer,IAudioClientDuckingControl,IAudioEffectsManager,IAudioViewManagerService,IAcousticEchoCancellationControl,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 3) = &CAudioClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioClockAdjustment,IMFTrustedOutput,IAudioClientTrustedOutputPriv,IAudioClientInternal,IAudioClientTest,IAudioAmbisonicsControl,IAudioHistoryControl,ICrossVmMediaNotificationProducer,IAudioClientDuckingControl,IAudioEffectsManager,IAudioViewManagerService,IAcousticEchoCancellationControl,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 4) = &CAudioClient::`vftable'{for `IMFTrustedOutput'};
  *((_QWORD *)this + 5) = &CAudioClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioClientTrustedOutputPriv,IAudioClientInternal,IAudioClientTest,IAudioAmbisonicsControl,IAudioHistoryControl,ICrossVmMediaNotificationProducer,IAudioClientDuckingControl,IAudioEffectsManager,IAudioViewManagerService,IAcousticEchoCancellationControl,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 6) = &CAudioClient::`vftable'{for `IAudioClientInternal'};
  *((_QWORD *)this + 7) = &CAudioClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioClientTest,IAudioAmbisonicsControl,IAudioHistoryControl,ICrossVmMediaNotificationProducer,IAudioClientDuckingControl,IAudioEffectsManager,IAudioViewManagerService,IAcousticEchoCancellationControl,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 8) = &CAudioClient::`vftable'{for `IAudioAmbisonicsControl'};
  *((_QWORD *)this + 9) = &CAudioClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioHistoryControl,ICrossVmMediaNotificationProducer,IAudioClientDuckingControl,IAudioEffectsManager,IAudioViewManagerService,IAcousticEchoCancellationControl,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 10) = &CAudioClient::`vftable'{for `ICrossVmMediaNotificationProducer'};
  *((_QWORD *)this + 11) = &CAudioClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioClientDuckingControl,IAudioEffectsManager,IAudioViewManagerService,IAcousticEchoCancellationControl,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 12) = &CAudioClient::`vftable'{for `IAudioEffectsManager'};
  *((_QWORD *)this + 13) = &CAudioClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioViewManagerService,IAcousticEchoCancellationControl,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 14) = &CAudioClient::`vftable'{for `IAcousticEchoCancellationControl'};
  *((_QWORD *)this + 15) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::ChainInterfaces<IAudioClient3,IAudioClient2,IAudioClient,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioClockAdjustment,IMFTrustedOutput,IAudioClientTrustedOutputPriv,IAudioClientInternal,IAudioClientTest,IAudioAmbisonicsControl,IAudioHistoryControl,ICrossVmMediaNotificationProducer,IAudioClientDuckingControl,IAudioEffectsManager,IAudioViewManagerService,IAcousticEchoCancellationControl,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  ActivityId = (GUID)*((_OWORD *)this + 33);
  EventActivityIdControl(4u, &ActivityId);
  CAudioClient::Cleanup(this, 0);
  v2 = (_QWORD *)((char *)this + 760);
  wil::details::unique_storage<wil::details::resource_policy<_PSM_APPSTATE_REGISTRATION *,void (*)(_PSM_APPSTATE_REGISTRATION *),&void PsmUnregisterAppStateChangeNotification(_PSM_APPSTATE_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_PSM_APPSTATE_REGISTRATION *,_PSM_APPSTATE_REGISTRATION *,0,std::nullptr_t>>::reset(
    (char *)this + 760,
    0);
  v3 = (_QWORD *)((char *)this + 768);
  wil::details::unique_storage<wil::details::resource_policy<void *,unsigned long (*)(void *),&unsigned long PowerUnregisterSuspendResumeNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    (char *)this + 768,
    0);
  v4 = (wil::details **)((char *)this + 896);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(
    (char *)this + 896,
    0);
  EventActivityIdControl(4u, &ActivityId);
  v6 = (void *)*((_QWORD *)this + 113);
  if ( v6 )
  {
    std::_Destroy_range<std::allocator<wil::com_ptr_t<IAudioVolumeDuckNotification,wil::err_returncode_policy>>>(v6);
    std::_Deallocate<16>(
      *((_QWORD *)this + 113),
      (*((_QWORD *)this + 115) - *((_QWORD *)this + 113)) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 113) = 0;
    *((_QWORD *)this + 114) = 0;
    *((_QWORD *)this + 115) = 0;
  }
  if ( *v4 )
    wil::details::delete_wnf_subscription_state(*v4, v5);
  NtDeleteWnfStateName((char *)this + 884);
  v8 = (wil::details *)*((_QWORD *)this + 109);
  if ( v8 )
    wil::details::CloseHandle(v8, v7);
  wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    (char *)this + 856,
    0);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 840);
  v10 = (wil::details *)*((_QWORD *)this + 99);
  if ( v10 )
    wil::details::CloseHandle(v10, v9);
  if ( *v3 )
    PowerUnregisterSuspendResumeNotification(*v3, v9);
  if ( *v2 )
    PsmUnregisterAppStateChangeNotification(*v2, v9);
  CAudioClientTraceLogger::~CAudioClientTraceLogger((CAudioClient *)((char *)this + 512));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 11);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 432);
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>((char *)this + 320);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 304);
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease((char *)this + 296);
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease((char *)this + 280);
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease((char *)this + 272);
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease((char *)this + 264);
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease((char *)this + 248);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((char *)this + 184);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((char *)this + 168);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<IAudioClient3,IAudioClient2,IAudioClient,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioClockAdjustment,IMFTrustedOutput,IAudioClientTrustedOutputPriv,IAudioClientInternal,IAudioClientTest,IAudioAmbisonicsControl,IAudioHistoryControl,ICrossVmMediaNotificationProducer,IAudioClientDuckingControl,IAudioEffectsManager,IAudioViewManagerService,IAcousticEchoCancellationControl,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<IAudioClient3,IAudioClient2,IAudioClient,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioClockAdjustment,IMFTrustedOutput,IAudioClientTrustedOutputPriv,IAudioClientInternal,IAudioClientTest,IAudioAmbisonicsControl,IAudioHistoryControl,ICrossVmMediaNotificationProducer,IAudioClientDuckingControl,IAudioEffectsManager,IAudioViewManagerService,IAcousticEchoCancellationControl,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x18006d65c  mov     r11, rsp
0x18006d65f  mov     [r11+10h], rbx
0x18006d663  mov     [r11+18h], rbp
0x18006d667  push    rsi
0x18006d668  push    rdi
0x18006d669  push    r14
0x18006d66b  sub     rsp, 50h
0x18006d66f  mov     rax, cs:__security_cookie
0x18006d676  xor     rax, rsp
0x18006d679  mov     [rsp+68h+var_28], rax
0x18006d67e  mov     rbx, rcx
0x18006d681  lea     rax, ??_7CAudioClient@@6BIInspectable@@@; const CAudioClient::`vftable'{for `IInspectable'}
0x18006d688  mov     [rcx], rax
0x18006d68b  lea     rax, ??_7CAudioClient@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ChainInterfaces@UIAudioClient3@@UIAudioClient2@@UIAudioClient@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@UIWeakReferenceSource@@UIAudioClockAdjustment@@UIMFTrustedOutput@@UIAudioClientTrustedOutputPriv@@UIAudioClientInternal@@UIAudioClientTest@@UIAudioAmbisonicsControl@@UIAudioHistoryControl@@UICrossVmMediaNotificationProducer@@UIAudioClientDuckingControl@@UIAudioEffectsManager@@UIAudioViewManagerService@@UIAcousticEchoCancellationControl@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CAudioClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::ChainInterfaces<IAudioClient3,IAudioClient2,IAudioClient,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IWeakReferenceSource,IAudioClockAdjustment,IMFTrustedOutput,IAudioClientTrustedOutputPriv,IAudioClientInternal,IAudioClientTest,IAudioAmbisonicsControl,IAudioHistoryControl,ICrossVmMediaNotificationProducer,IAudioClientDuckingControl,IAudioEffectsManager,IAudioViewManagerService,IAcousticEchoCancellationControl,Microsoft::WRL::FtmBase>'}
0x18006d692  mov     [rcx+8], rax
0x18006d696  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$ChainInterfaces@UIAudioClient3@@UIAudioClient2@@UIAudioClient@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@UIAudioClockAdjustment@@UIMFTrustedOutput@@UIAudioClientTrustedOutputPriv@@UIAudioClientInternal@@UIAudioClientTest@@UIAudioAmbisonicsControl@@UIAudioHistoryControl@@UICrossVmMediaNotificationProducer@@UIAudioClientDuckingControl@@UIAudioEffectsManager@@UIAudioViewManagerService@@UIAcousticEchoCancellationControl@@VFtmBase@23@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::ChainInterfaces<IAudioClient3,IAudioClient2,IAudioClient,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioClockAdjustment,IMFTrustedOutput,IAudioClientTrustedOutputPriv,IAudioClientInternal,IAudioClientTest,IAudioAmbisonicsControl,IAudioHistoryControl,ICrossVmMediaNotificationProducer,IAudioClientDuckingControl,IAudioEffectsManager,IAudioViewManagerService,IAcousticEchoCancellationControl,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'}
0x18006d69d  mov     [rcx+10h], rax
0x18006d6a1  lea     rax, ??_7CAudioClient@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAudioClockAdjustment@@UIMFTrustedOutput@@UIAudioClientTrustedOutputPriv@@UIAudioClientInternal@@UIAudioClientTest@@UIAudioAmbisonicsControl@@UIAudioHistoryControl@@UICrossVmMediaNotificationProducer@@UIAudioClientDuckingControl@@UIAudioEffectsManager@@UIAudioViewManagerService@@UIAcousticEchoCancellationControl@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CAudioClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioClockAdjustment,IMFTrustedOutput,IAudioClientTrustedOutputPriv,IAudioClientInternal,IAudioClientTest,IAudioAmbisonicsControl,IAudioHistoryControl,ICrossVmMediaNotificationProducer,IAudioClientDuckingControl,IAudioEffectsManager,IAudioViewManagerService,IAcousticEchoCancellationControl,Microsoft::WRL::FtmBase>'}
0x18006d6a8  mov     [rcx+18h], rax
0x18006d6ac  lea     rax, ??_7CAudioClient@@6BIMFTrustedOutput@@@; const CAudioClient::`vftable'{for `IMFTrustedOutput'}
0x18006d6b3  mov     [rcx+20h], rax
0x18006d6b7  lea     rax, ??_7CAudioClient@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAudioClientTrustedOutputPriv@@UIAudioClientInternal@@UIAudioClientTest@@UIAudioAmbisonicsControl@@UIAudioHistoryControl@@UICrossVmMediaNotificationProducer@@UIAudioClientDuckingControl@@UIAudioEffectsManager@@UIAudioViewManagerService@@UIAcousticEchoCancellationControl@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CAudioClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioClientTrustedOutputPriv,IAudioClientInternal,IAudioClientTest,IAudioAmbisonicsControl,IAudioHistoryControl,ICrossVmMediaNotificationProducer,IAudioClientDuckingControl,IAudioEffectsManager,IAudioViewManagerService,IAcousticEchoCancellationControl,Microsoft::WRL::FtmBase>'}
0x18006d6be  mov     [rcx+28h], rax
0x18006d6c2  lea     rax, ??_7CAudioClient@@6BIAudioClientInternal@@@; const CAudioClient::`vftable'{for `IAudioClientInternal'}
0x18006d6c9  mov     [rcx+30h], rax
0x18006d6cd  lea     rax, ??_7CAudioClient@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAudioClientTest@@UIAudioAmbisonicsControl@@UIAudioHistoryControl@@UICrossVmMediaNotificationProducer@@UIAudioClientDuckingControl@@UIAudioEffectsManager@@UIAudioViewManagerService@@UIAcousticEchoCancellationControl@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CAudioClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioClientTest,IAudioAmbisonicsControl,IAudioHistoryControl,ICrossVmMediaNotificationProducer,IAudioClientDuckingControl,IAudioEffectsManager,IAudioViewManagerService,IAcousticEchoCancellationControl,Microsoft::WRL::FtmBase>'}
0x18006d6d4  mov     [rcx+38h], rax
0x18006d6d8  lea     rax, ??_7CAudioClient@@6BIAudioAmbisonicsControl@@@; const CAudioClient::`vftable'{for `IAudioAmbisonicsControl'}
0x18006d6df  mov     [rcx+40h], rax
0x18006d6e3  lea     rax, ??_7CAudioClient@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAudioHistoryControl@@UICrossVmMediaNotificationProducer@@UIAudioClientDuckingControl@@UIAudioEffectsManager@@UIAudioViewManagerService@@UIAcousticEchoCancellationControl@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CAudioClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioHistoryControl,ICrossVmMediaNotificationProducer,IAudioClientDuckingControl,IAudioEffectsManager,IAudioViewManagerService,IAcousticEchoCancellationControl,Microsoft::WRL::FtmBase>'}
0x18006d6ea  mov     [rcx+48h], rax
0x18006d6ee  lea     rax, ??_7CAudioClient@@6BICrossVmMediaNotificationProducer@@@; const CAudioClient::`vftable'{for `ICrossVmMediaNotificationProducer'}
0x18006d6f5  mov     [rcx+50h], rax
0x18006d6f9  lea     rax, ??_7CAudioClient@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAudioClientDuckingControl@@UIAudioEffectsManager@@UIAudioViewManagerService@@UIAcousticEchoCancellationControl@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CAudioClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioClientDuckingControl,IAudioEffectsManager,IAudioViewManagerService,IAcousticEchoCancellationControl,Microsoft::WRL::FtmBase>'}
0x18006d700  mov     [rcx+58h], rax
0x18006d704  lea     rax, ??_7CAudioClient@@6BIAudioEffectsManager@@@; const CAudioClient::`vftable'{for `IAudioEffectsManager'}
0x18006d70b  mov     [rcx+60h], rax
0x18006d70f  lea     rax, ??_7CAudioClient@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAudioViewManagerService@@UIAcousticEchoCancellationControl@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CAudioClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioViewManagerService,IAcousticEchoCancellationControl,Microsoft::WRL::FtmBase>'}
0x18006d716  mov     [rcx+68h], rax
0x18006d71a  lea     rax, ??_7CAudioClient@@6BIAcousticEchoCancellationControl@@@; const CAudioClient::`vftable'{for `IAcousticEchoCancellationControl'}
0x18006d721  mov     [rcx+70h], rax
0x18006d725  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$ChainInterfaces@UIAudioClient3@@UIAudioClient2@@UIAudioClient@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@UIAudioClockAdjustment@@UIMFTrustedOutput@@UIAudioClientTrustedOutputPriv@@UIAudioClientInternal@@UIAudioClientTest@@UIAudioAmbisonicsControl@@UIAudioHistoryControl@@UICrossVmMediaNotificationProducer@@UIAudioClientDuckingControl@@UIAudioEffectsManager@@UIAudioViewManagerService@@UIAcousticEchoCancellationControl@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::ChainInterfaces<IAudioClient3,IAudioClient2,IAudioClient,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioClockAdjustment,IMFTrustedOutput,IAudioClientTrustedOutputPriv,IAudioClientInternal,IAudioClientTest,IAudioAmbisonicsControl,IAudioHistoryControl,ICrossVmMediaNotificationProducer,IAudioClientDuckingControl,IAudioEffectsManager,IAudioViewManagerService,IAcousticEchoCancellationControl,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18006d72c  mov     [rcx+78h], rax
0x18006d730  movups  xmm0, xmmword ptr [rcx+210h]
0x18006d737  movdqu  [rsp+68h+var_48], xmm0
0x18006d73d  mov     rax, [rcx+210h]
0x18006d744  mov     [r11-38h], rax
0x18006d748  mov     rax, [rcx+218h]
0x18006d74f  mov     [r11-30h], rax
0x18006d753  lea     rdx, [r11-38h]; ActivityId
0x18006d757  mov     ecx, 4; ControlCode
0x18006d75c  call    cs:__imp_EventActivityIdControl
0x18006d762  xor     edx, edx; int
0x18006d764  mov     rcx, rbx; this
0x18006d767  call    ?Cleanup@CAudioClient@@IEAAXH@Z; CAudioClient::Cleanup(int)
0x18006d76c  lea     r14, [rbx+2F8h]
0x18006d773  xor     edx, edx
0x18006d775  mov     rcx, r14
0x18006d778  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_PSM_APPSTATE_REGISTRATION@@P6AXPEAU1@@Z$1?PsmUnregisterAppStateChangeNotification@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_PSM_APPSTATE_REGISTRATION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_PSM_APPSTATE_REGISTRATION *,void (*)(_PSM_APPSTATE_REGISTRATION *),&PsmUnregisterAppStateChangeNotification(_PSM_APPSTATE_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_PSM_APPSTATE_REGISTRATION *,_PSM_APPSTATE_REGISTRATION *,0,std::nullptr_t>>::reset(_PSM_APPSTATE_REGISTRATION *)
0x18006d77d  lea     rsi, [rbx+300h]
0x18006d784  xor     edx, edx
0x18006d786  mov     rcx, rsi
0x18006d789  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AKPEAX@Z$1?PowerUnregisterSuspendResumeNotification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,ulong (*)(void *),&PowerUnregisterSuspendResumeNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18006d78e  lea     rdi, [rbx+380h]
0x18006d795  xor     edx, edx
0x18006d797  mov     rcx, rdi
0x18006d79a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUwnf_subscription_state_base@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(wil::details::wnf_subscription_state_base *)
0x18006d79f  lea     rdx, [rsp+68h+ActivityId]; ActivityId
0x18006d7a4  mov     ecx, 4; ControlCode
0x18006d7a9  call    cs:__imp_EventActivityIdControl
0x18006d7af  mov     rcx, [rbx+388h]
0x18006d7b6  test    rcx, rcx
0x18006d7b9  jz      short loc_18006D802
0x18006d7bb  mov     rdx, [rbx+390h]
0x18006d7c2  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@UIAudioVolumeDuckNotification@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@UIAudioVolumeDuckNotification@@Uerr_returncode_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@UIAudioVolumeDuckNotification@@Uerr_returncode_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<IAudioVolumeDuckNotification,wil::err_returncode_policy>>>(wil::com_ptr_t<IAudioVolumeDuckNotification,wil::err_returncode_policy> *,wil::com_ptr_t<IAudioVolumeDuckNotification,wil::err_returncode_policy> * const,std::allocator<wil::com_ptr_t<IAudioVolumeDuckNotification,wil::err_returncode_policy>> &)
0x18006d7c7  mov     rcx, [rbx+388h]
0x18006d7ce  mov     rdx, [rbx+398h]
0x18006d7d5  sub     rdx, rcx
0x18006d7d8  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18006d7dc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18006d7e1  mov     qword ptr [rbx+388h], 0
0x18006d7ec  mov     qword ptr [rbx+390h], 0
0x18006d7f7  mov     qword ptr [rbx+398h], 0
0x18006d802  mov     rcx, [rdi]; this
0x18006d805  test    rcx, rcx
0x18006d808  jz      short loc_18006D80F
0x18006d80a  call    ?delete_wnf_subscription_state@details@wil@@YAXPEAUwnf_subscription_state_base@12@@Z; wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *)
0x18006d80f  lea     rcx, [rbx+374h]
0x18006d816  call    cs:__imp_NtDeleteWnfStateName
0x18006d81c  mov     rcx, [rbx+368h]; this
0x18006d823  test    rcx, rcx
0x18006d826  jz      short loc_18006D82D
0x18006d828  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18006d82d  lea     rcx, [rbx+358h]
0x18006d834  xor     edx, edx
0x18006d836  call    ?reset@?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtWAVEFORMATEX@@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tWAVEFORMATEX *)
0x18006d83b  lea     rcx, [rbx+348h]; void *
0x18006d842  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x18006d847  mov     rcx, [rbx+318h]; this
0x18006d84e  test    rcx, rcx
0x18006d851  jz      short loc_18006D858
0x18006d853  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18006d858  mov     rcx, [rsi]
0x18006d85b  test    rcx, rcx
0x18006d85e  jz      short loc_18006D866
0x18006d860  call    cs:__imp_PowerUnregisterSuspendResumeNotification
0x18006d866  mov     rcx, [r14]
0x18006d869  test    rcx, rcx
0x18006d86c  jz      short loc_18006D874
0x18006d86e  call    cs:__imp_PsmUnregisterAppStateChangeNotification
0x18006d874  lea     rcx, [rbx+200h]; this
0x18006d87b  call    ??1CAudioClientTraceLogger@@QEAA@XZ; CAudioClientTraceLogger::~CAudioClientTraceLogger(void)
0x18006d880  lea     rcx, [rbx+1B8h]; lpCriticalSection
0x18006d887  call    cs:__imp_DeleteCriticalSection
0x18006d88d  lea     rcx, [rbx+1B0h]; void *
0x18006d894  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x18006d899  lea     rcx, [rbx+140h]
0x18006d8a0  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x18006d8a5  lea     rcx, [rbx+130h]; void *
0x18006d8ac  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x18006d8b1  lea     rcx, [rbx+128h]
0x18006d8b8  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18006d8bd  lea     rcx, [rbx+118h]
0x18006d8c4  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18006d8c9  lea     rcx, [rbx+110h]
0x18006d8d0  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18006d8d5  lea     rcx, [rbx+108h]
0x18006d8dc  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18006d8e1  lea     rcx, [rbx+0F8h]
0x18006d8e8  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18006d8ed  lea     rcx, [rbx+0B8h]
0x18006d8f4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18006d8f9  lea     rcx, [rbx+0A8h]
0x18006d900  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18006d905  mov     rcx, rbx
0x18006d908  call    ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$ChainInterfaces@UIAudioClient3@@UIAudioClient2@@UIAudioClient@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@UIAudioClockAdjustment@@UIMFTrustedOutput@@UIAudioClientTrustedOutputPriv@@UIAudioClientInternal@@UIAudioClientTest@@UIAudioAmbisonicsControl@@UIAudioHistoryControl@@UICrossVmMediaNotificationProducer@@UIAudioClientDuckingControl@@UIAudioEffectsManager@@UIAudioViewManagerService@@UIAcousticEchoCancellationControl@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<IAudioClient3,IAudioClient2,IAudioClient,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioClockAdjustment,IMFTrustedOutput,IAudioClientTrustedOutputPriv,IAudioClientInternal,IAudioClientTest,IAudioAmbisonicsControl,IAudioHistoryControl,ICrossVmMediaNotificationProducer,IAudioClientDuckingControl,IAudioEffectsManager,IAudioViewManagerService,IAcousticEchoCancellationControl,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<IAudioClient3,IAudioClient2,IAudioClient,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IAudioClockAdjustment,IMFTrustedOutput,IAudioClientTrustedOutputPriv,IAudioClientInternal,IAudioClientTest,IAudioAmbisonicsControl,IAudioHistoryControl,ICrossVmMediaNotificationProducer,IAudioClientDuckingControl,IAudioEffectsManager,IAudioViewManagerService,IAcousticEchoCancellationControl,Microsoft::WRL::FtmBase>(void)
0x18006d90d  nop
0x18006d90e  mov     rcx, [rsp+68h+var_28]
0x18006d913  xor     rcx, rsp; StackCookie
0x18006d916  call    __security_check_cookie
0x18006d91b  lea     r11, [rsp+68h+var_18]
0x18006d920  mov     rbx, [r11+28h]
0x18006d924  mov     rbp, [r11+30h]
0x18006d928  mov     rsp, r11
0x18006d92b  pop     r14
0x18006d92d  pop     rdi
0x18006d92e  pop     rsi
0x18006d92f  retn
```
