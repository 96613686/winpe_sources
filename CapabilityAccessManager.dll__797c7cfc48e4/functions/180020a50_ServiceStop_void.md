# ServiceStop(void)

- ea: `0x180020a50`
- end: `0x180020d1e`
- name: `?ServiceStop@@YAJXZ`
- size: `718`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180020310`
- `0x180020d30`

## callees

- `0x180016450`
- `0x18001ab9c`
- `0x18001b844`
- `0x18001d00c`
- `0x18001dd1c`
- `0x18001dfc0`
- `0x18001e32c`
- `0x180020a50`
- `0x180020e48`
- `0x1800210d4`
- `0x18002115c`
- `0x1800211d4`
- `0x1800212f8`
- `0x18002445c`
- `0x180029680`
- `0x18005b41c`
- `0x18005c3e0`
- `0x1800a2048`
- `0x1800b0208`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180020b75`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180020b75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020b92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020b92`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180020b02`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180020b02`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180020cfe`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180020cfe`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180020a99`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180020a99`

## string_xrefs

- `0x180020ab1`: `onecore\base\devices\cam\svc\servicemain.cpp`
- `0x180020aed`: `onecore\base\devices\cam\svc\servicemain.cpp`
- `0x180020b14`: `onecore\base\devices\cam\svc\servicemain.cpp`
- `0x180020b42`: `onecore\base\devices\cam\svc\servicemain.cpp`
- `0x180020c5d`: `onecore\base\devices\cam\svc\servicemain.cpp`
- `0x180020c7f`: `onecore\base\devices\cam\svc\servicemain.cpp`
- `0x180020c3c`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 ServiceStop(void)
{
  int v0; // eax
  unsigned int v1; // edx
  int v2; // ebx
  int v3; // eax
  int v4; // eax
  unsigned int v5; // edx
  int v6; // eax
  struct Microsoft::WRL::Details::ModuleBase *v7; // rdx
  const unsigned __int16 *v8; // r8
  bool v9; // r9
  __int64 v10; // rcx
  unsigned int i; // edi
  __int64 UsageRecordingSemaphore; // rax
  __int64 v13; // r8
  int v14; // eax
  int v15; // edi
  int v16; // eax
  const char *v17; // r9
  __int64 result; // rax
  int v19; // [rsp+20h] [rbp-38h]
  __int128 v20; // [rsp+30h] [rbp-28h] BYREF
  __int64 v21; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v23; // [rsp+68h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_329f17ae543231aead129cd668c645b8_Traceguids);
  }
  v0 = RoInitialize(1);
  v2 = v0;
  if ( v0 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x159,
      (unsigned int)"onecore\\base\\devices\\cam\\svc\\servicemain.cpp",
      (const char *)(unsigned int)v0,
      v19);
  UpdateServiceStatus(3u, v1);
  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57337766>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57337766>::GetImpl'::`2'::impl) )
    {
      v3 = Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::Shutdown();
      if ( v3 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x162,
          (unsigned int)"onecore\\base\\devices\\cam\\svc\\servicemain.cpp",
          (const char *)(unsigned int)v3,
          v19);
    }
    v4 = CoRegisterServerShutdownDelay(0, 0);
    if ( v4 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x165,
        (unsigned int)"onecore\\base\\devices\\cam\\svc\\servicemain.cpp",
        (const char *)(unsigned int)v4,
        v19);
    if ( ServiceGlobals::g_module )
    {
      v6 = ComServerModule::Unregister(ServiceGlobals::g_module);
      if ( v6 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x16C,
          (unsigned int)"onecore\\base\\devices\\cam\\svc\\servicemain.cpp",
          (const char *)(unsigned int)v6,
          v19);
      LOBYTE(v8) = 1;
      Microsoft::WRL::Details::TerminateMap(ServiceGlobals::g_module, v7, v8, v9);
      std::unique_ptr<ComServerModule>::reset(v10, 0);
    }
    if ( ServiceGlobals::g_tpWait )
    {
      CloseThreadpoolWait(ServiceGlobals::g_tpWait);
      ServiceGlobals::g_tpWait = 0;
    }
    if ( ServiceGlobals::g_hStopEvent )
    {
      CloseHandle(ServiceGlobals::g_hStopEvent);
      ServiceGlobals::g_hStopEvent = 0;
    }
    UpdateServiceStatus(1u, v5);
    *(_OWORD *)&ServiceGlobals::g_status.dwServiceType = 0;
    *(_OWORD *)&ServiceGlobals::g_status.dwWin32ExitCode = 0;
    ServiceGlobals::g_statusHandle = 0;
    v20 = 0;
    v21 = 0;
    for ( i = 0; i < 0xF; ++i )
    {
      UsageRecordingSemaphore = Windows::Internal::CapabilityAccess::Private::Globals::SemaphoreManager::GetUsageRecordingSemaphore();
      _acquire___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseSemaphore_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
        UsageRecordingSemaphore,
        &v23,
        v13,
        500);
      if ( !v23 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseSemaphore_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
        MicrosoftTelemetryAssertTriggeredNoArgs();
        goto LABEL_31;
      }
      ___emplace_back_V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseSemaphore_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil_____vector_V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseSemaphore_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__V__allocator_V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseSemaphore_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___std___std__QEAAAEAV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseSemaphore_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil____QEAV23__Z(
        &v20,
        &v23);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseSemaphore_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
    }
    v14 = StateRepository::Shutdown();
    v15 = v14;
    if ( v14 >= 0 )
      v15 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11F,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
        (const char *)(unsigned int)v14,
        v19);
    if ( v15 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1A2,
        (unsigned int)"onecore\\base\\devices\\cam\\svc\\servicemain.cpp",
        (const char *)(unsigned int)v15,
        v19);
LABEL_31:
    v16 = DisableCAMRPCInterfaces();
    if ( v16 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1A5,
        (unsigned int)"onecore\\base\\devices\\cam\\svc\\servicemain.cpp",
        (const char *)(unsigned int)v16,
        v19);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_329f17ae543231aead129cd668c645b8_Traceguids);
    }
    if ( (_QWORD)v20 )
    {
      ____Destroy_range_V__allocator_V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseSemaphore_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___std___std__YAXPEAV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseSemaphore_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAV12_AEAV__allocator_V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseSemaphore_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___0__Z(
        v20,
        *((_QWORD *)&v20 + 1));
      std::_Deallocate<16>((void *)v20, (v21 - v20) & 0xFFFFFFFFFFFFFFF8uLL);
      v20 = 0;
      v21 = 0;
    }
    if ( v2 >= 0 )
      RoUninitialize();
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1AA,
                           (unsigned int)"onecore\\base\\devices\\cam\\svc\\servicemain.cpp",
                           v17);
  }
  return result;
}

```

## disassembly

```asm
0x180020a50  mov     [rsp+arg_10], rbx
0x180020a55  mov     [rsp+arg_18], rdi
0x180020a5a  push    r15
0x180020a5c  sub     rsp, 50h
0x180020a60  lea     r15, WPP_GLOBAL_Control
0x180020a67  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a6e  cmp     rcx, r15
0x180020a71  jz      short loc_180020A94
0x180020a73  test    byte ptr [rcx+1Ch], 1
0x180020a77  jz      short loc_180020A94
0x180020a79  cmp     byte ptr [rcx+19h], 5
0x180020a7d  jb      short loc_180020A94
0x180020a7f  mov     edx, 0Eh
0x180020a84  lea     r8, WPP_329f17ae543231aead129cd668c645b8_Traceguids
0x180020a8b  mov     rcx, [rcx+10h]
0x180020a8f  call    WPP_SF_
0x180020a94  mov     ecx, 1
0x180020a99  call    cs:__imp_RoInitialize
0x180020a9f  mov     ebx, eax
0x180020aa1  mov     [rsp+58h+arg_0], eax
0x180020aa5  mov     rcx, [rsp+58h]; this
0x180020aaa  test    eax, eax
0x180020aac  jns     short loc_180020AC2
0x180020aae  mov     r9d, eax; char *
0x180020ab1  lea     r8, aOnecoreBaseDev_47; "onecore\\base\\devices\\cam\\svc\\servi"...
0x180020ab8  mov     edx, 159h; void *
0x180020abd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020ac2  mov     ecx, 3; unsigned int
0x180020ac7  call    ?UpdateServiceStatus@@YAXKK@Z; UpdateServiceStatus(ulong,ulong)
0x180020acc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57337766@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57337766@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57337766> `wil::Feature<__WilFeatureTraits_Feature_57337766>::GetImpl(void)'::`2'::impl
0x180020ad3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57337766@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57337766>::__private_IsEnabled(void)
0x180020ad8  test    al, al
0x180020ada  jz      short loc_180020AFE
0x180020adc  call    ?Shutdown@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@SAJXZ; Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::Shutdown(void)
0x180020ae1  mov     rcx, [rsp+58h]; this
0x180020ae6  test    eax, eax
0x180020ae8  jns     short loc_180020AFE
0x180020aea  mov     r9d, eax; char *
0x180020aed  lea     r8, aOnecoreBaseDev_47; "onecore\\base\\devices\\cam\\svc\\servi"...
0x180020af4  mov     edx, 162h; void *
0x180020af9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020afe  xor     edx, edx
0x180020b00  xor     ecx, ecx
0x180020b02  call    cs:__imp_CoRegisterServerShutdownDelay
0x180020b08  mov     rcx, [rsp+58h]; this
0x180020b0d  test    eax, eax
0x180020b0f  jns     short loc_180020B25
0x180020b11  mov     r9d, eax; char *
0x180020b14  lea     r8, aOnecoreBaseDev_47; "onecore\\base\\devices\\cam\\svc\\servi"...
0x180020b1b  mov     edx, 165h; void *
0x180020b20  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020b25  mov     rcx, cs:?g_module@ServiceGlobals@@3V?$unique_ptr@VComServerModule@@U?$default_delete@VComServerModule@@@std@@@std@@A; this
0x180020b2c  test    rcx, rcx
0x180020b2f  jz      short loc_180020B69
0x180020b31  call    ?Unregister@ComServerModule@@QEAAJXZ; ComServerModule::Unregister(void)
0x180020b36  mov     rcx, [rsp+58h]; this
0x180020b3b  test    eax, eax
0x180020b3d  jns     short loc_180020B53
0x180020b3f  mov     r9d, eax; char *
0x180020b42  lea     r8, aOnecoreBaseDev_47; "onecore\\base\\devices\\cam\\svc\\servi"...
0x180020b49  mov     edx, 16Ch; void *
0x180020b4e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020b53  mov     r8b, 1; unsigned __int16 *
0x180020b56  mov     rcx, cs:?g_module@ServiceGlobals@@3V?$unique_ptr@VComServerModule@@U?$default_delete@VComServerModule@@@std@@@std@@A; this
0x180020b5d  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x180020b62  xor     edx, edx
0x180020b64  call    ?reset@?$unique_ptr@VComServerModule@@U?$default_delete@VComServerModule@@@std@@@std@@QEAAXPEAVComServerModule@@@Z; std::unique_ptr<ComServerModule>::reset(ComServerModule *)
0x180020b69  mov     rcx, cs:?g_tpWait@ServiceGlobals@@3PEAU_TP_WAIT@@EA; pwa
0x180020b70  test    rcx, rcx
0x180020b73  jz      short loc_180020B86
0x180020b75  call    cs:__imp_CloseThreadpoolWait
0x180020b7b  mov     cs:?g_tpWait@ServiceGlobals@@3PEAU_TP_WAIT@@EA, 0; _TP_WAIT * ServiceGlobals::g_tpWait
0x180020b86  mov     rcx, cs:?g_hStopEvent@ServiceGlobals@@3PEAXEA; hObject
0x180020b8d  test    rcx, rcx
0x180020b90  jz      short loc_180020BA3
0x180020b92  call    cs:__imp_CloseHandle
0x180020b98  mov     cs:?g_hStopEvent@ServiceGlobals@@3PEAXEA, 0; void * ServiceGlobals::g_hStopEvent
0x180020ba3  mov     ecx, 1; unsigned int
0x180020ba8  call    ?UpdateServiceStatus@@YAXKK@Z; UpdateServiceStatus(ulong,ulong)
0x180020bad  xorps   xmm0, xmm0
0x180020bb0  xor     eax, eax
0x180020bb2  movups  xmmword ptr cs:?g_status@ServiceGlobals@@3U_SERVICE_STATUS@@A.dwServiceType, xmm0; _SERVICE_STATUS ServiceGlobals::g_status ...
0x180020bb9  movups  xmmword ptr cs:?g_status@ServiceGlobals@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, xmm0; _SERVICE_STATUS ServiceGlobals::g_status ...
0x180020bc0  mov     cs:?g_statusHandle@ServiceGlobals@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * ServiceGlobals::g_statusHandle
0x180020bc7  movdqu  [rsp+58h+var_28], xmm0
0x180020bcd  mov     [rsp+58h+var_18], rax
0x180020bd2  xor     edi, edi
0x180020bd4  cmp     edi, 0Fh
0x180020bd7  jnb     short loc_180020C29
0x180020bd9  call    ?GetUsageRecordingSemaphore@SemaphoreManager@Globals@Private@CapabilityAccess@Internal@Windows@@SAAEAV?$unique_any_t@V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@XZ
0x180020bde  mov     r9d, 1F4h
0x180020be4  lea     rdx, [rsp+58h+arg_8]
0x180020be9  mov     rcx, rax
0x180020bec  call    ?acquire@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180020bf1  nop
0x180020bf2  cmp     [rsp+58h+arg_8], 0
0x180020bf8  jz      short loc_180020C18
0x180020bfa  lea     rdx, [rsp+58h+arg_8]
0x180020bff  lea     rcx, [rsp+58h+var_28]
0x180020c04  call    ??$emplace_back@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAV23@@Z
0x180020c09  nop
0x180020c0a  lea     rcx, [rsp+58h+arg_8]
0x180020c0f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180020c14  inc     edi
0x180020c16  jmp     short loc_180020BD4
0x180020c18  lea     rcx, [rsp+58h+arg_8]
0x180020c1d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180020c22  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180020c27  jmp     short loc_180020C6E
0x180020c29  call    ?Shutdown@StateRepository@@YAJP6AXXZW4InitializeFlags@1@@Z; StateRepository::Shutdown(void (*)(void),StateRepository::InitializeFlags)
0x180020c2e  mov     edi, eax
0x180020c30  test    eax, eax
0x180020c32  jns     short loc_180020C4F
0x180020c34  mov     rcx, [rsp+58h]; this
0x180020c39  mov     r9d, eax; char *
0x180020c3c  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x180020c43  mov     edx, 11Fh; void *
0x180020c48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020c4d  jmp     short loc_180020C51
0x180020c4f  xor     edi, edi
0x180020c51  mov     rcx, [rsp+58h]; this
0x180020c56  test    edi, edi
0x180020c58  jns     short loc_180020C6E
0x180020c5a  mov     r9d, edi; char *
0x180020c5d  lea     r8, aOnecoreBaseDev_47; "onecore\\base\\devices\\cam\\svc\\servi"...
0x180020c64  mov     edx, 1A2h; void *
0x180020c69  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020c6e  call    ?DisableCAMRPCInterfaces@@YAJXZ; DisableCAMRPCInterfaces(void)
0x180020c73  mov     rcx, [rsp+58h]; this
0x180020c78  test    eax, eax
0x180020c7a  jns     short loc_180020C90
0x180020c7c  mov     r9d, eax; char *
0x180020c7f  lea     r8, aOnecoreBaseDev_47; "onecore\\base\\devices\\cam\\svc\\servi"...
0x180020c86  mov     edx, 1A5h; void *
0x180020c8b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020c90  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c97  cmp     rcx, r15
0x180020c9a  jz      short loc_180020CBE
0x180020c9c  test    byte ptr [rcx+1Ch], 1
0x180020ca0  jz      short loc_180020CBE
0x180020ca2  cmp     byte ptr [rcx+19h], 5
0x180020ca6  jb      short loc_180020CBE
0x180020ca8  mov     edx, 0Fh
0x180020cad  lea     r8, WPP_329f17ae543231aead129cd668c645b8_Traceguids
0x180020cb4  mov     rcx, [rcx+10h]
0x180020cb8  call    WPP_SF_
0x180020cbd  nop
0x180020cbe  mov     rcx, qword ptr [rsp+58h+var_28]
0x180020cc3  test    rcx, rcx
0x180020cc6  jz      short loc_180020CFA
0x180020cc8  mov     rdx, qword ptr [rsp+58h+var_28+8]
0x180020ccd  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z
0x180020cd2  mov     rcx, qword ptr [rsp+58h+var_28]
0x180020cd7  mov     rdx, [rsp+58h+var_18]
0x180020cdc  sub     rdx, rcx
0x180020cdf  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180020ce3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180020ce8  xorps   xmm0, xmm0
0x180020ceb  movdqu  [rsp+58h+var_28], xmm0
0x180020cf1  mov     [rsp+58h+var_18], 0
0x180020cfa  test    ebx, ebx
0x180020cfc  js      short loc_180020D04
0x180020cfe  call    cs:__imp_RoUninitialize
0x180020d04  xor     eax, eax
0x180020d06  jmp     short loc_180020D0C
0x180020d08  mov     eax, [rsp+58h+arg_0]
0x180020d0c  mov     rbx, [rsp+58h+arg_10]
0x180020d11  mov     rdi, [rsp+58h+arg_18]
0x180020d16  add     rsp, 50h
0x180020d1a  pop     r15
0x180020d1c  retn
```
