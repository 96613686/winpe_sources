# wil::svchost_service<ServiceTraits,svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>,svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>,svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>,svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>>::start(void)

- ea: `0x1800198c8`
- end: `0x180019b3d`
- name: `?start@?$svchost_service@UServiceTraits@@U?$svchost_singleton_coclass_factory@VIndexerSemanticStoreManager@@UIndexerSemanticStoreManagerImpl@@@@U?$svchost_singleton_coclass_factory@VIndexerSemanticSearchServices@@UIndexerSemanticSearchServicesImpl@@@@U?$svchost_singleton_coclass_factory@VSessionManagerBroker@@USessionManagerBrokerImpl@@@@U?$svchost_singleton_coclass_factory@VAIFabricResourceManager@@UAIFabricResourceManagerImpl@@@@@wil@@AEAAXXZ`
- size: `629`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800192d4`

## callees

- `0x180005140`
- `0x180007ad0`
- `0x180012f24`
- `0x1800139a8`
- `0x180014754`
- `0x180018c30`
- `0x180018c70`
- `0x180018d50`
- `0x180018f0c`
- `0x1800198c8`
- `0x180019c3c`
- `0x180019f40`
- `0x18001cdac`
- `0x18002239c`
- `0x180027f48`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ab9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ab9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019acc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019acc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180019ac4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180019ac4`
- `combase!__imp_CoGetSharedServiceId` at `0x18001990c`
- `combase!__imp_CoGetSharedServiceId` at `0x18001990c`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180019954`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180019954`

## pseudocode

```c
__int64 __fastcall wil::svchost_service<ServiceTraits,svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>,svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>,svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>,svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>>::start(
        void *a1)
{
  int SharedServiceId; // eax
  int v2; // eax
  struct DependencyManager *Instance; // rax
  __int64 v4; // rax
  AIFabricSvcCallout *v5; // rcx
  __int64 v6; // rdx
  volatile signed __int32 *v7; // rbx
  volatile signed __int32 *v8; // rbx
  void *v9; // rax
  void *v10; // rbx
  void (__fastcall *v11)(HANDLE *, const WCHAR *, __int64, __int64 (__fastcall *)(void *, unsigned __int8), __int64 *, int); // r14
  __int64 v12; // rsi
  HANDLE v13; // rdi
  DWORD LastError; // ebx
  int v16; // [rsp+40h] [rbp-28h] BYREF
  __int128 v17; // [rsp+48h] [rbp-20h]
  void *v18; // [rsp+A0h] [rbp+38h] BYREF

  v18 = a1;
  wil::svchost_service<ServiceTraits,svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>,svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>,svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>,svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>>::update_status(
    &g_service,
    2);
  LODWORD(v18) = 0;
  v16 = 0;
  v17 = 0;
  SharedServiceId = CoGetSharedServiceId(&v18);
  if ( SharedServiceId < 0 )
    winrt::throw_hresult((unsigned int)SharedServiceId, &v16);
  wil::details::g_service_id = (unsigned int)v18;
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    &qword_1800AFD18,
    1,
    0);
  v16 = 0;
  v17 = 0;
  v2 = CoRegisterServerShutdownDelay(qword_1800AFD18, 120000);
  if ( v2 < 0 )
    winrt::throw_hresult((unsigned int)v2, &v16);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_52926939>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_52926939>::GetImpl'::`2'::impl)
    || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID57666987>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID57666987>::GetImpl'::`2'::impl) )
  {
    StartHcfDetection();
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_51718004>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_51718004>::GetImpl'::`2'::impl) )
  {
    Instance = DependencyManager::GetInstance();
    v4 = std::make_shared<AIFabricSvcCallout,DependencyManager &>(&v16, Instance);
    v5 = *(AIFabricSvcCallout **)v4;
    v6 = *(_QWORD *)(v4 + 8);
    *(_QWORD *)v4 = 0;
    *(_QWORD *)(v4 + 8) = 0;
    g_aiFabricSvcCallout = v5;
    v7 = (volatile signed __int32 *)qword_1800AFD58;
    qword_1800AFD58 = v6;
    if ( v7 )
    {
      if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
        if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      }
    }
    v8 = (volatile signed __int32 *)v17;
    if ( (_QWORD)v17 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v17 + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
    AIFabricSvcCallout::OnServiceMain(g_aiFabricSvcCallout);
  }
  v18 = operator new(0x20u);
  v9 = (void *)wil::details::svchost_module<svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>,svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>,svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>,svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>>::svchost_module<svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>,svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>,svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>,svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>>(v18);
  v10 = qword_1800AFD20;
  qword_1800AFD20 = v9;
  if ( v10 )
  {
    wil::details::svchost_module<svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>,svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>,svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>,svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>>::~svchost_module<svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>,svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>,svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>,svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>>(v10);
    operator delete(v10, 0x20u);
  }
  v11 = *(void (__fastcall **)(HANDLE *, const WCHAR *, __int64, __int64 (__fastcall *)(void *, unsigned __int8), __int64 *, int))(g_service + 192);
  v12 = qword_1800AFD18;
  v13 = WaitHandle;
  if ( WaitHandle )
  {
    LastError = GetLastError();
    UnregisterWait(v13);
    SetLastError(LastError);
  }
  WaitHandle = 0;
  v11(
    &WaitHandle,
    L"WSAIFabricSvc",
    v12,
    _lambda_2b60315af233edcc87a71efee55d4376_::_lambda_invoker_cdecl_,
    &g_service,
    8);
  return wil::svchost_service<ServiceTraits,svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>,svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>,svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>,svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>>::update_status(
           &g_service,
           4);
}

```

## disassembly

```asm
0x1800198c8  mov     [rsp-30h+arg_0], rcx
0x1800198cd  push    rbp
0x1800198ce  push    rbx
0x1800198cf  push    rsi
0x1800198d0  push    rdi
0x1800198d1  push    r12
0x1800198d3  push    r14
0x1800198d5  mov     rbp, rsp
0x1800198d8  sub     rsp, 68h
0x1800198dc  xor     r8d, r8d
0x1800198df  lea     edx, [r8+2]
0x1800198e3  lea     r12, ?g_service@@3V?$svchost_service@UServiceTraits@@U?$svchost_singleton_coclass_factory@VIndexerSemanticStoreManager@@UIndexerSemanticStoreManagerImpl@@@@U?$svchost_singleton_coclass_factory@VIndexerSemanticSearchServices@@UIndexerSemanticSearchServicesImpl@@@@U?$svchost_singleton_coclass_factory@VSessionManagerBroker@@USessionManagerBrokerImpl@@@@U?$svchost_singleton_coclass_factory@VAIFabricResourceManager@@UAIFabricResourceManagerImpl@@@@@wil@@A; wil::svchost_service<ServiceTraits,svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>,svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>,svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>,svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>> g_service
0x1800198ea  mov     rcx, r12
0x1800198ed  call    ?update_status@?$svchost_service@UServiceTraits@@U?$svchost_singleton_coclass_factory@VIndexerSemanticStoreManager@@UIndexerSemanticStoreManagerImpl@@@@U?$svchost_singleton_coclass_factory@VIndexerSemanticSearchServices@@UIndexerSemanticSearchServicesImpl@@@@U?$svchost_singleton_coclass_factory@VSessionManagerBroker@@USessionManagerBrokerImpl@@@@U?$svchost_singleton_coclass_factory@VAIFabricResourceManager@@UAIFabricResourceManagerImpl@@@@@wil@@AEAAXKK@Z; wil::svchost_service<ServiceTraits,svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>,svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>,svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>,svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>>::update_status(ulong,ulong)
0x1800198f2  mov     dword ptr [rbp+arg_0], 0
0x1800198f9  mov     [rbp+var_28], 0
0x180019900  xorps   xmm0, xmm0
0x180019903  movdqu  [rbp+var_20], xmm0
0x180019908  lea     rcx, [rbp+arg_0]
0x18001990c  call    cs:__imp_CoGetSharedServiceId
0x180019912  test    eax, eax
0x180019914  js      loc_180019B31
0x18001991a  mov     eax, dword ptr [rbp+arg_0]
0x18001991d  mov     cs:?g_service_id@details@wil@@3KA, eax; ulong wil::details::g_service_id
0x180019923  xor     r9d, r9d
0x180019926  xor     r8d, r8d
0x180019929  lea     edx, [r9+1]
0x18001992d  lea     rcx, qword_1800AFD18
0x180019934  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180019939  mov     [rbp+var_28], 0
0x180019940  xorps   xmm0, xmm0
0x180019943  movdqu  [rbp+var_20], xmm0
0x180019948  mov     edx, 1D4C0h
0x18001994d  mov     rcx, cs:qword_1800AFD18
0x180019954  call    cs:__imp_CoRegisterServerShutdownDelay
0x18001995a  test    eax, eax
0x18001995c  js      loc_180019B25
0x180019962  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_52926939@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_52926939@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_52926939> `wil::Feature<__WilFeatureTraits_Feature_52926939>::GetImpl(void)'::`2'::impl
0x180019969  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_52926939@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_52926939>::__private_IsEnabled(void)
0x18001996e  test    al, al
0x180019970  jnz     short loc_180019982
0x180019972  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID57666987@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID57666987@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID57666987> `wil::Feature<__WilFeatureTraits_Feature_ID57666987>::GetImpl(void)'::`2'::impl
0x180019979  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID57666987@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID57666987>::__private_IsEnabled(void)
0x18001997e  test    al, al
0x180019980  jz      short loc_180019987
0x180019982  call    ?StartHcfDetection@@YAXXZ; StartHcfDetection(void)
0x180019987  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_51718004@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_51718004@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_51718004> `wil::Feature<__WilFeatureTraits_Feature_51718004>::GetImpl(void)'::`2'::impl
0x18001998e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_51718004@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_51718004>::__private_IsEnabled(void)
0x180019993  test    al, al
0x180019995  jz      loc_180019A5A
0x18001999b  call    ?GetInstance@DependencyManager@@SAAEAU1@XZ; DependencyManager::GetInstance(void)
0x1800199a0  mov     rdx, rax
0x1800199a3  lea     rcx, [rbp+var_28]
0x1800199a7  call    ??$make_shared@VAIFabricSvcCallout@@AEAUDependencyManager@@@std@@YA?AV?$shared_ptr@VAIFabricSvcCallout@@@0@AEAUDependencyManager@@@Z; std::make_shared<AIFabricSvcCallout,DependencyManager &>(DependencyManager &)
0x1800199ac  mov     rcx, [rax]
0x1800199af  mov     rdx, [rax+8]
0x1800199b3  mov     qword ptr [rax], 0
0x1800199ba  mov     qword ptr [rax+8], 0
0x1800199c2  mov     cs:?g_aiFabricSvcCallout@@3V?$shared_ptr@VAIFabricSvcCallout@@@std@@A, rcx; std::shared_ptr<AIFabricSvcCallout> g_aiFabricSvcCallout
0x1800199c9  mov     rbx, cs:qword_1800AFD58
0x1800199d0  mov     cs:qword_1800AFD58, rdx
0x1800199d7  or      edi, 0FFFFFFFFh
0x1800199da  test    rbx, rbx
0x1800199dd  jz      short loc_180019A12
0x1800199df  mov     eax, edi
0x1800199e1  lock xadd [rbx+8], eax
0x1800199e6  add     eax, edi
0x1800199e8  jnz     short loc_180019A12
0x1800199ea  mov     rax, [rbx]
0x1800199ed  mov     rcx, rbx
0x1800199f0  mov     rax, [rax]
0x1800199f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199f8  mov     eax, edi
0x1800199fa  lock xadd [rbx+0Ch], eax
0x1800199ff  add     eax, edi
0x180019a01  jnz     short loc_180019A12
0x180019a03  mov     rax, [rbx]
0x180019a06  mov     rcx, rbx
0x180019a09  mov     rax, [rax+8]
0x180019a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a12  mov     rbx, qword ptr [rbp+var_20]
0x180019a16  test    rbx, rbx
0x180019a19  jz      short loc_180019A4E
0x180019a1b  mov     eax, edi
0x180019a1d  lock xadd [rbx+8], eax
0x180019a22  add     eax, edi
0x180019a24  jnz     short loc_180019A4E
0x180019a26  mov     rax, [rbx]
0x180019a29  mov     rcx, rbx
0x180019a2c  mov     rax, [rax]
0x180019a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a34  mov     eax, edi
0x180019a36  lock xadd [rbx+0Ch], eax
0x180019a3b  add     eax, edi
0x180019a3d  jnz     short loc_180019A4E
0x180019a3f  mov     rax, [rbx]
0x180019a42  mov     rcx, rbx
0x180019a45  mov     rax, [rax+8]
0x180019a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a4e  mov     rcx, cs:?g_aiFabricSvcCallout@@3V?$shared_ptr@VAIFabricSvcCallout@@@std@@A; this
0x180019a55  call    ?OnServiceMain@AIFabricSvcCallout@@QEAAXXZ; AIFabricSvcCallout::OnServiceMain(void)
0x180019a5a  mov     edi, 20h ; ' '
0x180019a5f  mov     ecx, edi; Size
0x180019a61  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019a66  mov     [rbp+arg_0], rax
0x180019a6a  mov     rcx, rax
0x180019a6d  call    ??0?$svchost_module@U?$svchost_singleton_coclass_factory@VIndexerSemanticStoreManager@@UIndexerSemanticStoreManagerImpl@@@@U?$svchost_singleton_coclass_factory@VIndexerSemanticSearchServices@@UIndexerSemanticSearchServicesImpl@@@@U?$svchost_singleton_coclass_factory@VSessionManagerBroker@@USessionManagerBrokerImpl@@@@U?$svchost_singleton_coclass_factory@VAIFabricResourceManager@@UAIFabricResourceManagerImpl@@@@@details@wil@@QEAA@XZ; wil::details::svchost_module<svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>,svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>,svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>,svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>>::svchost_module<svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>,svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>,svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>,svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>>(void)
0x180019a72  nop
0x180019a73  mov     rbx, cs:qword_1800AFD20
0x180019a7a  mov     cs:qword_1800AFD20, rax
0x180019a81  test    rbx, rbx
0x180019a84  jz      short loc_180019A98
0x180019a86  mov     rcx, rbx
0x180019a89  call    ??1?$svchost_module@U?$svchost_singleton_coclass_factory@VIndexerSemanticStoreManager@@UIndexerSemanticStoreManagerImpl@@@@U?$svchost_singleton_coclass_factory@VIndexerSemanticSearchServices@@UIndexerSemanticSearchServicesImpl@@@@U?$svchost_singleton_coclass_factory@VSessionManagerBroker@@USessionManagerBrokerImpl@@@@U?$svchost_singleton_coclass_factory@VAIFabricResourceManager@@UAIFabricResourceManagerImpl@@@@@details@wil@@QEAA@XZ; wil::details::svchost_module<svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>,svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>,svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>,svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>>::~svchost_module<svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>,svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>,svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>,svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>>(void)
0x180019a8e  mov     edx, edi; unsigned __int64
0x180019a90  mov     rcx, rbx; void *
0x180019a93  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019a98  mov     rax, cs:?g_service@@3V?$svchost_service@UServiceTraits@@U?$svchost_singleton_coclass_factory@VIndexerSemanticStoreManager@@UIndexerSemanticStoreManagerImpl@@@@U?$svchost_singleton_coclass_factory@VIndexerSemanticSearchServices@@UIndexerSemanticSearchServicesImpl@@@@U?$svchost_singleton_coclass_factory@VSessionManagerBroker@@USessionManagerBrokerImpl@@@@U?$svchost_singleton_coclass_factory@VAIFabricResourceManager@@UAIFabricResourceManagerImpl@@@@@wil@@A; wil::svchost_service<ServiceTraits,svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>,svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>,svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>,svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>> g_service
0x180019a9f  mov     r14, [rax+0C0h]
0x180019aa6  mov     rsi, cs:qword_1800AFD18
0x180019aad  mov     rdi, cs:WaitHandle
0x180019ab4  test    rdi, rdi
0x180019ab7  jz      short loc_180019AD2
0x180019ab9  call    cs:__imp_GetLastError
0x180019abf  mov     ebx, eax
0x180019ac1  mov     rcx, rdi; WaitHandle
0x180019ac4  call    cs:__imp_UnregisterWait
0x180019aca  mov     ecx, ebx; dwErrCode
0x180019acc  call    cs:__imp_SetLastError
0x180019ad2  mov     cs:WaitHandle, 0
0x180019add  mov     [rsp+68h+var_40], 8
0x180019ae5  mov     [rsp+68h+var_48], r12
0x180019aea  lea     r9, ?_lambda_invoker_cdecl_@_lambda_2b60315af233edcc87a71efee55d4376_@@CA@PEAXE@Z; _lambda_2b60315af233edcc87a71efee55d4376_::_lambda_invoker_cdecl_(void *,uchar)
0x180019af1  mov     r8, rsi
0x180019af4  lea     rdx, ServiceName; "WSAIFabricSvc"
0x180019afb  lea     rcx, WaitHandle
0x180019b02  mov     rax, r14
0x180019b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b0a  xor     r8d, r8d
0x180019b0d  lea     edx, [r8+4]
0x180019b11  mov     rcx, r12
0x180019b14  add     rsp, 68h
0x180019b18  pop     r14
0x180019b1a  pop     r12
0x180019b1c  pop     rdi
0x180019b1d  pop     rsi
0x180019b1e  pop     rbx
0x180019b1f  pop     rbp
0x180019b20  jmp     ?update_status@?$svchost_service@UServiceTraits@@U?$svchost_singleton_coclass_factory@VIndexerSemanticStoreManager@@UIndexerSemanticStoreManagerImpl@@@@U?$svchost_singleton_coclass_factory@VIndexerSemanticSearchServices@@UIndexerSemanticSearchServicesImpl@@@@U?$svchost_singleton_coclass_factory@VSessionManagerBroker@@USessionManagerBrokerImpl@@@@U?$svchost_singleton_coclass_factory@VAIFabricResourceManager@@UAIFabricResourceManagerImpl@@@@@wil@@AEAAXKK@Z; wil::svchost_service<ServiceTraits,svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>,svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>,svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>,svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>>::update_status(ulong,ulong)
0x180019b25  lea     rdx, [rbp+var_28]
0x180019b29  mov     ecx, eax
0x180019b2b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180019b31  lea     rdx, [rbp+var_28]
0x180019b35  mov     ecx, eax
0x180019b37  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
