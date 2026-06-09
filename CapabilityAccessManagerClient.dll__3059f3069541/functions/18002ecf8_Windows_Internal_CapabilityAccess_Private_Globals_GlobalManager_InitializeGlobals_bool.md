# Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::InitializeGlobals(bool)

- ea: `0x18002ecf8`
- end: `0x18002eddc`
- name: `?InitializeGlobals@GlobalManager@Globals@Private@CapabilityAccess@Internal@Windows@@SAJ_N@Z`
- size: `228`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800242c0`

## callees

- `0x18000aa04`
- `0x180024aa4`
- `0x18002e788`
- `0x18002e954`
- `0x18002ea0c`
- `0x18002eb34`
- `0x18002ec54`
- `0x18002eca4`
- `0x18002ecf8`
- `0x18002f128`
- `0x18002f164`
- `0x180032b34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ed0b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ed0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::InitializeGlobals()
{
  __int64 result; // rax
  __int64 v1; // rdx
  __int64 v2; // r8
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  RTL_SRWLOCK *v5; // [rsp+48h] [rbp+10h] BYREF

  AcquireSRWLockExclusive(&Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::m_initLock);
  v5 = &Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::m_initLock;
  if ( Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::m_initializationState == 2 )
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v5);
    return 0;
  }
  else
  {
    Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::m_testCode = 0;
    try
    {
      Windows::Internal::CapabilityAccess::Private::Globals::ServiceStateTracker::Initialize();
      Windows::Internal::CapabilityAccess::Private::Globals::SemaphoreManager::Initialize();
      _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)&Windows::Internal::CapabilityAccess::Private::Globals::EventManager::m_microphoneToastTriedEvent);
      _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)&Windows::Internal::CapabilityAccess::Private::Globals::EventManager::m_locationToastTriedEvent);
      _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)&Windows::Internal::CapabilityAccess::Private::Globals::EventManager::m_webcamToastTriedEvent);
      _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)&Windows::Internal::CapabilityAccess::Private::Globals::EventManager::m_testToastTriedEvent);
      Windows::Internal::CapabilityAccess::Private::Globals::RegistryConfig::Initialize();
      Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::Initialize();
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload>::GetImpl'::`2'::impl) )
        Windows::Internal::CapabilityAccess::Private::Globals::UsageDatabaseManager::Initialize();
      _InterlockedExchange(
        &Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::m_initializationState,
        1);
      LOBYTE(v2) = 3;
      LOBYTE(v1) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_CAM_CUASupport>::GetImpl'::`2'::impl,
        v1,
        v2);
      Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::Initialize();
      Windows::Internal::CapabilityAccess::Private::Globals::FriendlyNameMapping::Initialize();
      _InterlockedExchange(
        &Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::m_initializationState,
        2);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v5);
      result = 0;
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x7F,
                             (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
                             v3);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002ecf8  mov     byte ptr [rsp+arg_0], cl
0x18002ecfc  push    rbx
0x18002ecfd  sub     rsp, 30h
0x18002ed01  lea     rbx, ?m_initLock@GlobalManager@Globals@Private@CapabilityAccess@Internal@Windows@@0Vsrwlock@wil@@A; wil::srwlock Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::m_initLock
0x18002ed08  mov     rcx, rbx; SRWLock
0x18002ed0b  call    cs:__imp_AcquireSRWLockExclusive
0x18002ed11  mov     [rsp+38h+arg_8], rbx
0x18002ed16  mov     eax, cs:?m_initializationState@GlobalManager@Globals@Private@CapabilityAccess@Internal@Windows@@0U?$atomic@K@std@@A; std::atomic<ulong> Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::m_initializationState
0x18002ed1c  nop
0x18002ed1d  mov     ebx, 2
0x18002ed22  cmp     eax, ebx
0x18002ed24  jnz     short loc_18002ED37
0x18002ed26  lea     rcx, [rsp+38h+arg_8]
0x18002ed2b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002ed30  xor     eax, eax
0x18002ed32  jmp     loc_18002EDD5
0x18002ed37  mov     cs:?m_testCode@GlobalManager@Globals@Private@CapabilityAccess@Internal@Windows@@0_NA, 0; bool Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::m_testCode
0x18002ed3e  call    ?Initialize@ServiceStateTracker@Globals@Private@CapabilityAccess@Internal@Windows@@CAXXZ; Windows::Internal::CapabilityAccess::Private::Globals::ServiceStateTracker::Initialize(void)
0x18002ed43  call    ?Initialize@SemaphoreManager@Globals@Private@CapabilityAccess@Internal@Windows@@CAXXZ; Windows::Internal::CapabilityAccess::Private::Globals::SemaphoreManager::Initialize(void)
0x18002ed48  lea     rcx, ?m_microphoneToastTriedEvent@EventManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@A
0x18002ed4f  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002ed54  lea     rcx, ?m_locationToastTriedEvent@EventManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@A
0x18002ed5b  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002ed60  lea     rcx, ?m_webcamToastTriedEvent@EventManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@A
0x18002ed67  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002ed6c  lea     rcx, ?m_testToastTriedEvent@EventManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@A
0x18002ed73  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002ed78  call    ?Initialize@RegistryConfig@Globals@Private@CapabilityAccess@Internal@Windows@@CAXXZ; Windows::Internal::CapabilityAccess::Private::Globals::RegistryConfig::Initialize(void)
0x18002ed7d  call    ?Initialize@FilePathCache@Globals@Private@CapabilityAccess@Internal@Windows@@CAXXZ; Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::Initialize(void)
0x18002ed82  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload> `wil::Feature<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload>::GetImpl(void)'::`2'::impl
0x18002ed89  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload>::__private_IsEnabled(void)
0x18002ed8e  test    al, al
0x18002ed90  jz      short loc_18002ED97
0x18002ed92  call    ?Initialize@UsageDatabaseManager@Globals@Private@CapabilityAccess@Internal@Windows@@SAXXZ; Windows::Internal::CapabilityAccess::Private::Globals::UsageDatabaseManager::Initialize(void)
0x18002ed97  mov     eax, 1
0x18002ed9c  xchg    eax, cs:?m_initializationState@GlobalManager@Globals@Private@CapabilityAccess@Internal@Windows@@0U?$atomic@K@std@@A; std::atomic<ulong> Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::m_initializationState
0x18002eda2  mov     r8b, 3
0x18002eda5  mov     dl, 1
0x18002eda7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAM_CUASupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_CUASupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport> `wil::Feature<__WilFeatureTraits_Feature_CAM_CUASupport>::GetImpl(void)'::`2'::impl
0x18002edae  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_CUASupport@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002edb3  call    ?Initialize@PolicyManager@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@SAXXZ; Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::Initialize(void)
0x18002edb8  call    ?Initialize@FriendlyNameMapping@Globals@Private@CapabilityAccess@Internal@Windows@@CAXXZ; Windows::Internal::CapabilityAccess::Private::Globals::FriendlyNameMapping::Initialize(void)
0x18002edbd  xchg    ebx, cs:?m_initializationState@GlobalManager@Globals@Private@CapabilityAccess@Internal@Windows@@0U?$atomic@K@std@@A; std::atomic<ulong> Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::m_initializationState
0x18002edc3  lea     rcx, [rsp+38h+arg_8]
0x18002edc8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002edcd  xor     eax, eax
0x18002edcf  jmp     short loc_18002EDD5
0x18002edd1  mov     eax, [rsp+38h+arg_0]
0x18002edd5  add     rsp, 30h
0x18002edd9  pop     rbx
0x18002edda  retn
```
