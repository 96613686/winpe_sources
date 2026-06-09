# CDPComBinaryHost::BinaryCallback::~BinaryCallback(void)

- ea: `0x180018540`
- end: `0x18001862a`
- name: `??1BinaryCallback@CDPComBinaryHost@@UEAA@XZ`
- size: `234`
- prototype: `void __fastcall(CDPComBinaryHost::BinaryCallback *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e5d0`

## callees

- `0x180003e60`
- `0x180004928`
- `0x180006668`
- `0x18000a52c`
- `0x180018540`
- `0x180018630`
- `0x1800186fc`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180018584`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180018584`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180018592`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180018592`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CDPComBinaryHost::BinaryCallback::~BinaryCallback(CDPComBinaryHost::BinaryCallback *this)
{
  PTP_TIMER *v2; // rdi
  struct _TP_TIMER *v3; // rcx
  __int64 v4; // rcx
  std::_Ref_count_base *v5; // rcx

  *(_QWORD *)this = &CDPComBinaryHost::BinaryCallback::`vftable'{for `ICDPBinaryHostCallback'};
  *((_QWORD *)this + 1) = &CDPComBinaryHost::BinaryCallback::`vftable'{for `ICDPParticipantHandler'};
  *((_QWORD *)this + 2) = &CDPComBinaryHost::BinaryCallback::`vftable'{for `ICDPResourcePolicyHandler'};
  v2 = (PTP_TIMER *)((char *)this + 240);
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 30);
  if ( v3 )
  {
    SetThreadpoolTimer(v3, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*v2, 1);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      v2,
      0);
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>(v2);
  v4 = *((_QWORD *)this + 28);
  if ( v4 )
  {
    *((_QWORD *)this + 28) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease((char *)this + 216);
  std::string::~string((char *)this + 184);
  ServiceCallbackNotifier<enum CDPComBinaryHostNotificationType,CDPComBinaryHostNotificationResult>::~ServiceCallbackNotifier<enum CDPComBinaryHostNotificationType,CDPComBinaryHostNotificationResult>((char *)this + 48);
  *(_QWORD *)this = &cdp::unknown<ICDPBinaryHostCallback,ICDPParticipantHandler,ICDPResourcePolicyHandler>::`vftable'{for `ICDPBinaryHostCallback'};
  *((_QWORD *)this + 1) = &cdp::unknown<ICDPBinaryHostCallback,ICDPParticipantHandler,ICDPResourcePolicyHandler>::`vftable'{for `ICDPParticipantHandler'};
  *((_QWORD *)this + 2) = &cdp::unknown<ICDPBinaryHostCallback,ICDPParticipantHandler,ICDPResourcePolicyHandler>::`vftable'{for `ICDPResourcePolicyHandler'};
  v5 = (std::_Ref_count_base *)*((_QWORD *)this + 5);
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
}

```

## disassembly

```asm
0x180018540  mov     [rsp+arg_0], rbx
0x180018545  push    rdi
0x180018546  sub     rsp, 20h
0x18001854a  mov     rbx, rcx
0x18001854d  lea     rax, ??_7BinaryCallback@CDPComBinaryHost@@6BICDPBinaryHostCallback@@@; const CDPComBinaryHost::BinaryCallback::`vftable'{for `ICDPBinaryHostCallback'}
0x180018554  mov     [rcx], rax
0x180018557  lea     rax, ??_7BinaryCallback@CDPComBinaryHost@@6BICDPParticipantHandler@@@; const CDPComBinaryHost::BinaryCallback::`vftable'{for `ICDPParticipantHandler'}
0x18001855e  mov     [rcx+8], rax
0x180018562  lea     rax, ??_7BinaryCallback@CDPComBinaryHost@@6BICDPResourcePolicyHandler@@@; const CDPComBinaryHost::BinaryCallback::`vftable'{for `ICDPResourcePolicyHandler'}
0x180018569  mov     [rcx+10h], rax
0x18001856d  lea     rdi, [rcx+0F0h]
0x180018574  mov     rcx, [rdi]; pti
0x180018577  test    rcx, rcx
0x18001857a  jz      short loc_1800185A2
0x18001857c  xor     r9d, r9d; msWindowLength
0x18001857f  xor     r8d, r8d; msPeriod
0x180018582  xor     edx, edx; pftDueTime
0x180018584  call    cs:__imp_SetThreadpoolTimer
0x18001858a  mov     edx, 1; fCancelPendingCallbacks
0x18001858f  mov     rcx, [rdi]; pti
0x180018592  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180018598  xor     edx, edx
0x18001859a  mov     rcx, rdi
0x18001859d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800185a2  mov     rcx, rdi
0x1800185a5  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>(void)
0x1800185aa  nop
0x1800185ab  mov     rcx, [rbx+0E0h]
0x1800185b2  test    rcx, rcx
0x1800185b5  jz      short loc_1800185CF
0x1800185b7  mov     qword ptr [rbx+0E0h], 0
0x1800185c2  mov     rax, [rcx]
0x1800185c5  mov     rax, [rax+10h]
0x1800185c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185ce  nop
0x1800185cf  lea     rcx, [rbx+0D8h]
0x1800185d6  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800185db  lea     rcx, [rbx+0B8h]
0x1800185e2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800185e7  lea     rcx, [rbx+30h]
0x1800185eb  call    ??1?$ServiceCallbackNotifier@W4CDPComBinaryHostNotificationType@@UCDPComBinaryHostNotificationResult@@@@QEAA@XZ; ServiceCallbackNotifier<CDPComBinaryHostNotificationType,CDPComBinaryHostNotificationResult>::~ServiceCallbackNotifier<CDPComBinaryHostNotificationType,CDPComBinaryHostNotificationResult>(void)
0x1800185f0  lea     rax, ??_7?$unknown@VICDPBinaryHostCallback@@VICDPParticipantHandler@@VICDPResourcePolicyHandler@@@cdp@@6BICDPBinaryHostCallback@@@; const cdp::unknown<ICDPBinaryHostCallback,ICDPParticipantHandler,ICDPResourcePolicyHandler>::`vftable'{for `ICDPBinaryHostCallback'}
0x1800185f7  mov     [rbx], rax
0x1800185fa  lea     rax, ??_7?$unknown@VICDPBinaryHostCallback@@VICDPParticipantHandler@@VICDPResourcePolicyHandler@@@cdp@@6BICDPParticipantHandler@@@; const cdp::unknown<ICDPBinaryHostCallback,ICDPParticipantHandler,ICDPResourcePolicyHandler>::`vftable'{for `ICDPParticipantHandler'}
0x180018601  mov     [rbx+8], rax
0x180018605  lea     rax, ??_7?$unknown@VICDPBinaryHostCallback@@VICDPParticipantHandler@@VICDPResourcePolicyHandler@@@cdp@@6BICDPResourcePolicyHandler@@@; const cdp::unknown<ICDPBinaryHostCallback,ICDPParticipantHandler,ICDPResourcePolicyHandler>::`vftable'{for `ICDPResourcePolicyHandler'}
0x18001860c  mov     [rbx+10h], rax
0x180018610  mov     rcx, [rbx+28h]; this
0x180018614  test    rcx, rcx
0x180018617  jz      short loc_18001861F
0x180018619  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001861e  nop
0x18001861f  mov     rbx, [rsp+28h+arg_0]
0x180018624  add     rsp, 20h
0x180018628  pop     rdi
0x180018629  retn
```
