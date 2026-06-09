# CAudioSessionControl::~CAudioSessionControl(void)

- ea: `0x180027f9c`
- end: `0x1800281fe`
- name: `??1CAudioSessionControl@@UEAA@XZ`
- size: `610`
- prototype: `void __fastcall(CAudioSessionControl *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180027f60`

## callees

- `0x180007f00`
- `0x18000c55c`
- `0x18000cb1c`
- `0x180011bd0`
- `0x18001bbb0`
- `0x1800230ec`
- `0x180023f10`
- `0x180027f9c`
- `0x1800429bc`
- `0x18004fa8c`
- `0x18005b5c8`
- `0x180074d28`
- `0x180087ea4`
- `0x180095600`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800281ad`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800281ad`
- `ntdll!RtlDllShutdownInProgress` at `0x1800280c4`
- `ntdll!RtlDllShutdownInProgress` at `0x1800280c4`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x1800280e3`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x1800280e3`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x1800280f9`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x1800280f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028162`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028162`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CAudioSessionControl::~CAudioSessionControl(CAudioSessionControl *this)
{
  __int64 *v2; // rax
  CAudioSessionControl *v3; // rcx
  __int64 *v4; // rbx
  char *v5; // rbp
  _QWORD *v6; // r14
  __int64 v7; // rax
  __int64 v8; // r15
  int v9; // eax
  void *v10; // rcx
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  char v13; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)this = &CAudioSessionControl::`vftable'{for `IInspectable'};
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IInspectable,Microsoft::WRL::ChainInterfaces<IAudioSessionControlInternal,IAudioSessionControl2,IAudioSessionControl,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,ISimpleAudioVolume,IChannelAudioVolume,IAudioMeterInformation,IPropertyStore,ICrossVmMediaNotificationProducer,ICrossVmMediaNotificationConsumer,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::ChainInterfaces<IAudioSessionControlInternal,IAudioSessionControl2,IAudioSessionControl,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,ISimpleAudioVolume,IChannelAudioVolume,IAudioMeterInformation,IPropertyStore,ICrossVmMediaNotificationProducer,ICrossVmMediaNotificationConsumer,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &CAudioSessionControl::`vftable'{for `Microsoft::WRL::ChainInterfaces<IAudioSessionControlInternal,IAudioSessionControl2,IAudioSessionControl,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
  *((_QWORD *)this + 3) = &CAudioSessionControl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ISimpleAudioVolume,IChannelAudioVolume,IAudioMeterInformation,IPropertyStore,ICrossVmMediaNotificationProducer,ICrossVmMediaNotificationConsumer,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 4) = &CAudioSessionControl::`vftable'{for `IChannelAudioVolume'};
  *((_QWORD *)this + 5) = &CAudioSessionControl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioMeterInformation,IPropertyStore,ICrossVmMediaNotificationProducer,ICrossVmMediaNotificationConsumer,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 6) = &CAudioSessionControl::`vftable'{for `IPropertyStore'};
  *((_QWORD *)this + 7) = &CAudioSessionControl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ICrossVmMediaNotificationProducer,ICrossVmMediaNotificationConsumer,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 8) = &CAudioSessionControl::`vftable'{for `ICrossVmMediaNotificationConsumer'};
  *((_QWORD *)this + 9) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IInspectable,Microsoft::WRL::ChainInterfaces<IAudioSessionControlInternal,IAudioSessionControl2,IAudioSessionControl,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,ISimpleAudioVolume,IChannelAudioVolume,IAudioMeterInformation,IPropertyStore,ICrossVmMediaNotificationProducer,ICrossVmMediaNotificationConsumer,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v2 = (__int64 *)operator new(0x20u);
  v4 = v2;
  if ( !v2 )
  {
    v6 = (_QWORD *)((char *)this + 328);
    v5 = (char *)this + 304;
LABEL_21:
    v4 = 0;
    goto LABEL_22;
  }
  *v2 = 0;
  v2[1] = 0;
  v2[2] = 0;
  v2[3] = 0;
  if ( *((_QWORD *)this + 37) && *((_DWORD *)this + 80) != 2 )
    wil::com_ptr_t<IAudioVolumeDuckNotification,wil::err_returncode_policy>::operator=(v2 + 2, (char *)this + 296);
  v5 = (char *)this + 304;
  if ( *((_QWORD *)this + 38) )
    wil::com_ptr_t<IAudioVolumeDuckNotification,wil::err_returncode_policy>::operator=(v4 + 1, (char *)this + 304);
  v6 = (_QWORD *)((char *)this + 328);
  v7 = *((_QWORD *)this + 41);
  if ( v7 )
  {
    *v6 = 0;
    v3 = (CAudioSessionControl *)v4[3];
    v4[3] = v7;
    if ( v3 )
      (*(void (__fastcall **)(CAudioSessionControl *))(*(_QWORD *)v3 + 16LL))(v3);
  }
  if ( v4[2] || v4[1] || v4[3] )
  {
    if ( !RtlDllShutdownInProgress() )
    {
      v8 = *v4;
      if ( *v4 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v13);
        CoDecrementMTAUsage(v8);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v13);
      }
      *v4 = 0;
      v9 = CoIncrementMTAUsage(v4);
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xF2,
          (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientsubmix.cpp",
          (const char *)(unsigned int)v9,
          v11);
    }
    if ( (unsigned int)TrySubmitAudioCleanupTask(lambda_34db553a8efe7b99ad2cc560367b169a_::_lambda_invoker_cdecl_, v4) )
      goto LABEL_21;
  }
LABEL_22:
  if ( *((_QWORD *)this + 23) )
    CAudioSessionControl::DestroyAudioSession(v3, (void **)this + 23);
  v10 = (void *)_InterlockedExchange64((volatile __int64 *)this + 35, 0);
  if ( v10 )
    CoTaskMemFree(v10);
  if ( v4 )
  {
    CAudioSessionControl::_CAudioSessionControl_::_2_::SessionControlCleanupContext::_SessionControlCleanupContext(v4);
    operator delete(v4, 0x20u);
  }
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(v6);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 312);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(v5);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 296);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((char *)this + 208);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((char *)this + 200);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((char *)this + 192);
  CLockedList_AllowDuplicates<IAudioSessionEvents,1>::~CLockedList_AllowDuplicates<IAudioSessionEvents,1>((char *)this + 120);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IInspectable,Microsoft::WRL::ChainInterfaces<IAudioSessionControlInternal,IAudioSessionControl2,IAudioSessionControl,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,ISimpleAudioVolume,IChannelAudioVolume,IAudioMeterInformation,IPropertyStore,ICrossVmMediaNotificationProducer,ICrossVmMediaNotificationConsumer,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IInspectable,Microsoft::WRL::ChainInterfaces<IAudioSessionControlInternal,IAudioSessionControl2,IAudioSessionControl,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,ISimpleAudioVolume,IChannelAudioVolume,IAudioMeterInformation,IPropertyStore,ICrossVmMediaNotificationProducer,ICrossVmMediaNotificationConsumer,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x180027f9c  mov     [rsp+arg_8], rbx
0x180027fa1  mov     [rsp+arg_10], rbp
0x180027fa6  push    rsi
0x180027fa7  push    rdi
0x180027fa8  push    r12
0x180027faa  push    r14
0x180027fac  push    r15; int
0x180027fae  sub     rsp, 20h
0x180027fb2  mov     rdi, rcx
0x180027fb5  lea     rax, ??_7CAudioSessionControl@@6BIInspectable@@@; const CAudioSessionControl::`vftable'{for `IInspectable'}
0x180027fbc  mov     [rcx], rax
0x180027fbf  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIInspectable@@U?$ChainInterfaces@UIAudioSessionControlInternal@@UIAudioSessionControl2@@UIAudioSessionControl@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@UISimpleAudioVolume@@UIChannelAudioVolume@@UIAudioMeterInformation@@UIPropertyStore@@UICrossVmMediaNotificationProducer@@UICrossVmMediaNotificationConsumer@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$ChainInterfaces@UIAudioSessionControlInternal@@UIAudioSessionControl2@@UIAudioSessionControl@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@UISimpleAudioVolume@@UIChannelAudioVolume@@UIAudioMeterInformation@@UIPropertyStore@@UICrossVmMediaNotificationProducer@@UICrossVmMediaNotificationConsumer@@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IInspectable,Microsoft::WRL::ChainInterfaces<IAudioSessionControlInternal,IAudioSessionControl2,IAudioSessionControl,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,ISimpleAudioVolume,IChannelAudioVolume,IAudioMeterInformation,IPropertyStore,ICrossVmMediaNotificationProducer,ICrossVmMediaNotificationConsumer,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::ChainInterfaces<IAudioSessionControlInternal,IAudioSessionControl2,IAudioSessionControl,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,ISimpleAudioVolume,IChannelAudioVolume,IAudioMeterInformation,IPropertyStore,ICrossVmMediaNotificationProducer,ICrossVmMediaNotificationConsumer,Microsoft::WRL::FtmBase>'}
0x180027fc6  mov     [rcx+8], rax
0x180027fca  lea     rax, ??_7CAudioSessionControl@@6B?$ChainInterfaces@UIAudioSessionControlInternal@@UIAudioSessionControl2@@UIAudioSessionControl@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@WRL@Microsoft@@@; const CAudioSessionControl::`vftable'{for `Microsoft::WRL::ChainInterfaces<IAudioSessionControlInternal,IAudioSessionControl2,IAudioSessionControl,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x180027fd1  mov     [rcx+10h], rax
0x180027fd5  lea     rax, ??_7CAudioSessionControl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UISimpleAudioVolume@@UIChannelAudioVolume@@UIAudioMeterInformation@@UIPropertyStore@@UICrossVmMediaNotificationProducer@@UICrossVmMediaNotificationConsumer@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CAudioSessionControl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ISimpleAudioVolume,IChannelAudioVolume,IAudioMeterInformation,IPropertyStore,ICrossVmMediaNotificationProducer,ICrossVmMediaNotificationConsumer,Microsoft::WRL::FtmBase>'}
0x180027fdc  mov     [rcx+18h], rax
0x180027fe0  lea     rax, ??_7CAudioSessionControl@@6BIChannelAudioVolume@@@; const CAudioSessionControl::`vftable'{for `IChannelAudioVolume'}
0x180027fe7  mov     [rcx+20h], rax
0x180027feb  lea     rax, ??_7CAudioSessionControl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAudioMeterInformation@@UIPropertyStore@@UICrossVmMediaNotificationProducer@@UICrossVmMediaNotificationConsumer@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CAudioSessionControl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioMeterInformation,IPropertyStore,ICrossVmMediaNotificationProducer,ICrossVmMediaNotificationConsumer,Microsoft::WRL::FtmBase>'}
0x180027ff2  mov     [rcx+28h], rax
0x180027ff6  lea     rax, ??_7CAudioSessionControl@@6BIPropertyStore@@@; const CAudioSessionControl::`vftable'{for `IPropertyStore'}
0x180027ffd  mov     [rcx+30h], rax
0x180028001  lea     rax, ??_7CAudioSessionControl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UICrossVmMediaNotificationProducer@@UICrossVmMediaNotificationConsumer@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CAudioSessionControl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ICrossVmMediaNotificationProducer,ICrossVmMediaNotificationConsumer,Microsoft::WRL::FtmBase>'}
0x180028008  mov     [rcx+38h], rax
0x18002800c  lea     rax, ??_7CAudioSessionControl@@6BICrossVmMediaNotificationConsumer@@@; const CAudioSessionControl::`vftable'{for `ICrossVmMediaNotificationConsumer'}
0x180028013  mov     [rcx+40h], rax
0x180028017  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIInspectable@@U?$ChainInterfaces@UIAudioSessionControlInternal@@UIAudioSessionControl2@@UIAudioSessionControl@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@UISimpleAudioVolume@@UIChannelAudioVolume@@UIAudioMeterInformation@@UIPropertyStore@@UICrossVmMediaNotificationProducer@@UICrossVmMediaNotificationConsumer@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IInspectable,Microsoft::WRL::ChainInterfaces<IAudioSessionControlInternal,IAudioSessionControl2,IAudioSessionControl,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,ISimpleAudioVolume,IChannelAudioVolume,IAudioMeterInformation,IPropertyStore,ICrossVmMediaNotificationProducer,ICrossVmMediaNotificationConsumer,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18002801e  mov     [rcx+48h], rax
0x180028022  mov     ecx, 20h ; ' '; unsigned __int64
0x180028027  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002802c  mov     rbx, rax
0x18002802f  xor     r12d, r12d
0x180028032  lea     rsi, [rdi+128h]
0x180028039  test    rax, rax
0x18002803c  jz      loc_180028131
0x180028042  mov     [rax], r12
0x180028045  mov     [rax+8], r12
0x180028049  mov     [rax+10h], r12
0x18002804d  mov     [rax+18h], r12
0x180028051  cmp     [rsi], r12
0x180028054  jz      short loc_18002806B
0x180028056  cmp     dword ptr [rdi+140h], 2
0x18002805d  jz      short loc_18002806B
0x18002805f  lea     rcx, [rax+10h]
0x180028063  mov     rdx, rsi
0x180028066  call    ??4?$com_ptr_t@UIAudioVolumeDuckNotification@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<IAudioVolumeDuckNotification,wil::err_returncode_policy>::operator=(wil::com_ptr_t<IAudioVolumeDuckNotification,wil::err_returncode_policy> &&)
0x18002806b  lea     rbp, [rdi+130h]
0x180028072  lea     r15, [rbx+8]
0x180028076  cmp     [rbp+0], r12
0x18002807a  jz      short loc_180028087
0x18002807c  mov     rdx, rbp
0x18002807f  mov     rcx, r15
0x180028082  call    ??4?$com_ptr_t@UIAudioVolumeDuckNotification@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<IAudioVolumeDuckNotification,wil::err_returncode_policy>::operator=(wil::com_ptr_t<IAudioVolumeDuckNotification,wil::err_returncode_policy> &&)
0x180028087  lea     r14, [rdi+148h]
0x18002808e  mov     rax, [r14]
0x180028091  test    rax, rax
0x180028094  jz      short loc_1800280B3
0x180028096  mov     [r14], r12
0x180028099  mov     rcx, [rbx+18h]
0x18002809d  mov     [rbx+18h], rax
0x1800280a1  test    rcx, rcx
0x1800280a4  jz      short loc_1800280B3
0x1800280a6  mov     rax, [rcx]
0x1800280a9  mov     rax, [rax+10h]
0x1800280ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280b2  nop
0x1800280b3  cmp     [rbx+10h], r12
0x1800280b7  jnz     short loc_1800280C4
0x1800280b9  cmp     [r15], r12
0x1800280bc  jnz     short loc_1800280C4
0x1800280be  cmp     [rbx+18h], r12
0x1800280c2  jz      short loc_180028142
0x1800280c4  call    cs:__imp_RtlDllShutdownInProgress
0x1800280ca  test    al, al
0x1800280cc  jnz     short loc_18002811C
0x1800280ce  mov     r15, [rbx]
0x1800280d1  test    r15, r15
0x1800280d4  jz      short loc_1800280F3
0x1800280d6  lea     rcx, [rsp+48h+arg_0]; this
0x1800280db  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800280e0  mov     rcx, r15
0x1800280e3  call    cs:__imp_CoDecrementMTAUsage
0x1800280e9  lea     rcx, [rsp+48h+arg_0]; this
0x1800280ee  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800280f3  mov     [rbx], r12
0x1800280f6  mov     rcx, rbx
0x1800280f9  call    cs:__imp_CoIncrementMTAUsage
0x1800280ff  test    eax, eax
0x180028101  jns     short loc_18002811C
0x180028103  mov     rcx, [rsp+48h]; this
0x180028108  mov     r9d, eax; char *
0x18002810b  lea     r8, aAvcoreAudiocor_29; "avcore\\audiocore\\client\\audioclient"...
0x180028112  mov     edx, 0F2h; void *
0x180028117  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002811c  mov     rdx, rbx; pv
0x18002811f  lea     rcx, _lambda_34db553a8efe7b99ad2cc560367b169a____lambda_invoker_cdecl_; pfns
0x180028126  call    ?TrySubmitAudioCleanupTask@@YAHP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z1@Z; TrySubmitAudioCleanupTask(void (*)(_TP_CALLBACK_INSTANCE *,void *),void *)
0x18002812b  test    eax, eax
0x18002812d  jz      short loc_180028142
0x18002812f  jmp     short loc_18002813F
0x180028131  lea     r14, [rdi+148h]
0x180028138  lea     rbp, [rdi+130h]
0x18002813f  mov     rbx, r12
0x180028142  lea     rdx, [rdi+0B8h]; void **
0x180028149  cmp     [rdx], r12
0x18002814c  jz      short loc_180028153
0x18002814e  call    ?DestroyAudioSession@CAudioSessionControl@@AEAAXPEAPEAX@Z; CAudioSessionControl::DestroyAudioSession(void * *)
0x180028153  mov     rcx, r12
0x180028156  xchg    rcx, [rdi+118h]; pv
0x18002815d  test    rcx, rcx
0x180028160  jz      short loc_180028168
0x180028162  call    cs:__imp_CoTaskMemFree
0x180028168  test    rbx, rbx
0x18002816b  jz      short loc_180028182
0x18002816d  mov     rcx, rbx
0x180028170  call    _CAudioSessionControl___CAudioSessionControl____2___SessionControlCleanupContext___SessionControlCleanupContext
0x180028175  mov     edx, 20h ; ' '; unsigned __int64
0x18002817a  mov     rcx, rbx; void *
0x18002817d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028182  mov     rcx, r14; void *
0x180028185  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x18002818a  lea     rcx, [rdi+138h]; void *
0x180028191  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x180028196  mov     rcx, rbp; void *
0x180028199  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x18002819e  mov     rcx, rsi; void *
0x1800281a1  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800281a6  lea     rcx, [rdi+0E0h]; lpCriticalSection
0x1800281ad  call    cs:__imp_DeleteCriticalSection
0x1800281b3  lea     rcx, [rdi+0D0h]
0x1800281ba  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800281bf  lea     rcx, [rdi+0C8h]
0x1800281c6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800281cb  lea     rcx, [rdi+0C0h]
0x1800281d2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800281d7  lea     rcx, [rdi+78h]
0x1800281db  call    ??1?$CLockedList_AllowDuplicates@UIAudioSessionEvents@@$00@@QEAA@XZ; CLockedList_AllowDuplicates<IAudioSessionEvents,1>::~CLockedList_AllowDuplicates<IAudioSessionEvents,1>(void)
0x1800281e0  mov     rcx, rdi
0x1800281e3  mov     rbx, [rsp+48h+arg_8]
0x1800281e8  mov     rbp, [rsp+48h+arg_10]
0x1800281ed  add     rsp, 20h
0x1800281f1  pop     r15
0x1800281f3  pop     r14
0x1800281f5  pop     r12
0x1800281f7  pop     rdi
0x1800281f8  pop     rsi
0x1800281f9  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIInspectable@@U?$ChainInterfaces@UIAudioSessionControlInternal@@UIAudioSessionControl2@@UIAudioSessionControl@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@UISimpleAudioVolume@@UIChannelAudioVolume@@UIAudioMeterInformation@@UIPropertyStore@@UICrossVmMediaNotificationProducer@@UICrossVmMediaNotificationConsumer@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IInspectable,Microsoft::WRL::ChainInterfaces<IAudioSessionControlInternal,IAudioSessionControl2,IAudioSessionControl,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,ISimpleAudioVolume,IChannelAudioVolume,IAudioMeterInformation,IPropertyStore,ICrossVmMediaNotificationProducer,ICrossVmMediaNotificationConsumer,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IInspectable,Microsoft::WRL::ChainInterfaces<IAudioSessionControlInternal,IAudioSessionControl2,IAudioSessionControl,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,ISimpleAudioVolume,IChannelAudioVolume,IAudioMeterInformation,IPropertyStore,ICrossVmMediaNotificationProducer,ICrossVmMediaNotificationConsumer,Microsoft::WRL::FtmBase>(void)
```
