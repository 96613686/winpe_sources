# SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BackgroundCapability>::Unregister(SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BackgroundCapability>::CCallback *)

- ea: `0x18004c1b8`
- end: `0x18004c378`
- name: `?Unregister@?$CSingletonHelper@W4BackgroundCapability@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `448`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004a430`
- `0x18004cbe8`

## callees

- `0x18000607c`
- `0x18000d51c`
- `0x18000fa10`
- `0x18000fab8`
- `0x180010030`
- `0x1800101f8`
- `0x1800103d0`
- `0x18004c1b8`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004c357`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004c357`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004c2d5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004c2d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c227`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c273`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c227`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c273`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18004c2f9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18004c2f9`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18004c206`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18004c206`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BackgroundCapability>::Unregister(
        RTL_SRWLOCK *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rdi
  char v4; // si
  __int64 v5; // r8
  __int64 v6; // rdx
  HANDLE EventW; // rdi
  __int64 v8; // rdx
  __int64 v9; // r8
  const char *v10; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  RTL_SRWLOCK *lpdwindex; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF
  struct _RTL_CRITICAL_SECTION *v15; // [rsp+50h] [rbp+18h] BYREF

  v14 = a2;
  lpdwindex = a1;
  v3 = a2;
  if ( !byte_180079FEA && hEvent )
  {
    LODWORD(lpdwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &hEvent, (LPDWORD)&lpdwindex);
  }
  LOBYTE(a3) = 3;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    a2,
    a3);
  EnterCriticalSection(&stru_18007A020);
  v15 = &stru_18007A020;
  SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback::LockHandleNotificationExclusive(
    v3,
    &lpdwindex);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *>(
    qword_180079FA8,
    (const unsigned __int8 *)&v14);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lpdwindex);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v15);
  v4 = 0;
  EnterCriticalSection(&stru_180079FF0);
  lpdwindex = (RTL_SRWLOCK *)&stru_180079FF0;
  LOBYTE(v5) = 3;
  LOBYTE(v6) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v6,
    v5);
  if ( !dword_18007A018 && !qword_180079FB8 && !byte_18007A050 && dword_18007A060 >= 0 )
  {
    v4 = 1;
    byte_18007A050 = 1;
    EventW = pHandles;
    if ( pHandles
      || (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&pHandles),
          (pHandles = EventW) != 0) )
    {
      ResetEvent(EventW);
    }
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&lpdwindex);
  if ( v4 )
  {
    try
    {
      (*(void (__fastcall **)(__int64 *))(SystemSettings::BatteryUsageHandlers::g_BackgroundCapabilitySingleton + 16))(&SystemSettings::BatteryUsageHandlers::g_BackgroundCapabilitySingleton);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x545,
        (unsigned int)"OneCoreUap\\Internal\\Shell\\inc\\SettingHandlersBaseCore.h",
        v10);
    }
    byte_180079FEA = 0;
    dword_18007A060 = -2147418113;
    SystemSettings::DataModel::AutoMTAUsageCookie::Release((SystemSettings::DataModel::AutoMTAUsageCookie *)&qword_18007A058);
    byte_18007A050 = 0;
    if ( pHandles )
      SetEvent(pHandles);
  }
  LOBYTE(v9) = 3;
  LOBYTE(v8) = 1;
  return wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
           `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
           v8,
           v9);
}

```

## disassembly

```asm
0x18004c1b8  mov     rax, rsp
0x18004c1bb  mov     [rax+20h], rsi
0x18004c1bf  mov     [rax+10h], rdx
0x18004c1c3  mov     [rax+8], rcx
0x18004c1c7  push    rdi
0x18004c1c8  sub     rsp, 30h
0x18004c1cc  mov     rdi, rdx
0x18004c1cf  cmp     cs:byte_180079FEA, 0
0x18004c1d6  jnz     short loc_18004C20C
0x18004c1d8  cmp     cs:hEvent, 0
0x18004c1e0  jz      short loc_18004C20C
0x18004c1e2  mov     dword ptr [rax+8], 0
0x18004c1e9  lea     rax, [rax+8]
0x18004c1ed  mov     [rsp+38h+lpdwindex], rax; lpdwindex
0x18004c1f2  lea     r9, hEvent; pHandles
0x18004c1f9  mov     r8d, 1; cHandles
0x18004c1ff  or      edx, 0FFFFFFFFh; dwTimeout
0x18004c202  lea     ecx, [r8+7]; dwFlags
0x18004c206  call    cs:__imp_CoWaitForMultipleHandles
0x18004c20c  mov     r8b, 3
0x18004c20f  mov     dl, 1
0x18004c211  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18004c218  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004c21d  lea     rsi, stru_18007A020
0x18004c224  mov     rcx, rsi; lpCriticalSection
0x18004c227  call    cs:__imp_EnterCriticalSection
0x18004c22d  mov     [rsp+38h+arg_10], rsi
0x18004c232  lea     rdx, [rsp+38h+arg_0]
0x18004c237  mov     rcx, rdi
0x18004c23a  call    ?LockHandleNotificationExclusive@CCallback@?$CSingletonHelper@W4BatteryGraphNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback::LockHandleNotificationExclusive(void)
0x18004c23f  nop
0x18004c240  lea     rdx, [rsp+38h+arg_8]
0x18004c245  lea     rcx, qword_180079FA8
0x18004c24c  call    ??$_Erase@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@@6@$0A@@std@@@std@@AEAA_KAEBQEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *>(SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback * const &)
0x18004c251  nop
0x18004c252  lea     rcx, [rsp+38h+arg_0]
0x18004c257  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004c25c  lea     rcx, [rsp+38h+arg_10]; this
0x18004c261  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18004c266  xor     sil, sil
0x18004c269  lea     rdi, stru_180079FF0
0x18004c270  mov     rcx, rdi; lpCriticalSection
0x18004c273  call    cs:__imp_EnterCriticalSection
0x18004c279  mov     [rsp+38h+arg_0], rdi
0x18004c27e  mov     r8b, 3
0x18004c281  mov     dl, 1
0x18004c283  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18004c28a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004c28f  cmp     cs:dword_18007A018, 0
0x18004c296  jnz     short loc_18004C300
0x18004c298  cmp     cs:qword_180079FB8, 0
0x18004c2a0  jnz     short loc_18004C300
0x18004c2a2  cmp     cs:byte_18007A050, sil
0x18004c2a9  jnz     short loc_18004C300
0x18004c2ab  cmp     cs:dword_18007A060, 0
0x18004c2b2  jl      short loc_18004C300
0x18004c2b4  mov     sil, 1
0x18004c2b7  mov     cs:byte_18007A050, sil
0x18004c2be  mov     rdi, cs:pHandles
0x18004c2c5  test    rdi, rdi
0x18004c2c8  jnz     short loc_18004C2F6
0x18004c2ca  xor     r9d, r9d; lpName
0x18004c2cd  xor     r8d, r8d; bInitialState
0x18004c2d0  lea     edx, [rdi+1]; bManualReset
0x18004c2d3  xor     ecx, ecx; lpEventAttributes
0x18004c2d5  call    cs:__imp_CreateEventW
0x18004c2db  mov     rdi, rax
0x18004c2de  lea     rcx, pHandles
0x18004c2e5  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18004c2ea  mov     cs:pHandles, rdi
0x18004c2f1  test    rdi, rdi
0x18004c2f4  jz      short loc_18004C300
0x18004c2f6  mov     rcx, rdi; hEvent
0x18004c2f9  call    cs:__imp_ResetEvent
0x18004c2ff  nop
0x18004c300  lea     rcx, [rsp+38h+arg_0]; this
0x18004c305  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18004c30a  test    sil, sil
0x18004c30d  jz      short loc_18004C35D
0x18004c30f  mov     rax, cs:?g_BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@3VBackgroundCapabilitySingleton@12@A; SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton SystemSettings::BatteryUsageHandlers::g_BackgroundCapabilitySingleton
0x18004c316  lea     rcx, ?g_BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@3VBackgroundCapabilitySingleton@12@A; SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton SystemSettings::BatteryUsageHandlers::g_BackgroundCapabilitySingleton
0x18004c31d  mov     rax, [rax+10h]
0x18004c321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c326  nop
0x18004c327  mov     cs:byte_180079FEA, 0
0x18004c32e  mov     cs:dword_18007A060, 8000FFFFh
0x18004c338  lea     rcx, qword_18007A058; this
0x18004c33f  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x18004c344  mov     cs:byte_18007A050, 0
0x18004c34b  mov     rcx, cs:pHandles; hEvent
0x18004c352  test    rcx, rcx
0x18004c355  jz      short loc_18004C35D
0x18004c357  call    cs:__imp_SetEvent
0x18004c35d  mov     r8b, 3
0x18004c360  mov     dl, 1
0x18004c362  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18004c369  mov     rsi, [rsp+38h+arg_18]
0x18004c36e  add     rsp, 30h
0x18004c372  pop     rdi
0x18004c373  jmp     ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
```
