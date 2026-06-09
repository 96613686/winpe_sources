# SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::Unregister(SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *)

- ea: `0x180029e68`
- end: `0x18002a028`
- name: `?Unregister@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `448`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001aac8`
- `0x180024fc0`
- `0x18003ba74`
- `0x18003c0f0`

## callees

- `0x18000b508`
- `0x180012c58`
- `0x18001314c`
- `0x1800176bc`
- `0x180024214`
- `0x180026bf0`
- `0x1800271c0`
- `0x180029e68`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029f85`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029f85`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002a007`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002a007`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029ed7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029f23`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029ed7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029f23`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180029fa9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180029fa9`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180029eb6`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180029eb6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::Unregister(
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
  if ( !byte_18006679A && qword_180066740 )
  {
    LODWORD(lpdwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &qword_180066740, (LPDWORD)&lpdwindex);
  }
  LOBYTE(a3) = 3;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    a2,
    a3);
  EnterCriticalSection(&stru_1800667D0);
  v15 = &stru_1800667D0;
  SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::CCallback::LockHandleNotificationExclusive(
    v3,
    &lpdwindex);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>(
    qword_180066758,
    (const unsigned __int8 *)&v14);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lpdwindex);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v15);
  v4 = 0;
  EnterCriticalSection(&stru_1800667A0);
  lpdwindex = (RTL_SRWLOCK *)&stru_1800667A0;
  LOBYTE(v5) = 3;
  LOBYTE(v6) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v6,
    v5);
  if ( !dword_1800667C8 && !qword_180066768 && !byte_180066800 && dword_180066810 >= 0 )
  {
    v4 = 1;
    byte_180066800 = 1;
    EventW = qword_1800667F8;
    if ( qword_1800667F8
      || (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&qword_1800667F8),
          (qword_1800667F8 = EventW) != 0) )
    {
      ResetEvent(EventW);
    }
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&lpdwindex);
  if ( v4 )
  {
    try
    {
      (*(void (__fastcall **)(__int64 *))(SystemSettings::BatterySaverOneCoreDataModel::g_AdaptiveModeSingleton + 16))(&SystemSettings::BatterySaverOneCoreDataModel::g_AdaptiveModeSingleton);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x545,
        (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingHandlersBaseCore.h",
        v10);
    }
    byte_18006679A = 0;
    dword_180066810 = -2147418113;
    SystemSettings::DataModel::AutoMTAUsageCookie::Release((SystemSettings::DataModel::AutoMTAUsageCookie *)&qword_180066808);
    byte_180066800 = 0;
    if ( qword_1800667F8 )
      SetEvent(qword_1800667F8);
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
0x180029e68  mov     rax, rsp
0x180029e6b  mov     [rax+20h], rsi
0x180029e6f  mov     [rax+10h], rdx
0x180029e73  mov     [rax+8], rcx
0x180029e77  push    rdi
0x180029e78  sub     rsp, 30h
0x180029e7c  mov     rdi, rdx
0x180029e7f  cmp     cs:byte_18006679A, 0
0x180029e86  jnz     short loc_180029EBC
0x180029e88  cmp     cs:qword_180066740, 0
0x180029e90  jz      short loc_180029EBC
0x180029e92  mov     dword ptr [rax+8], 0
0x180029e99  lea     rax, [rax+8]
0x180029e9d  mov     [rsp+38h+lpdwindex], rax; lpdwindex
0x180029ea2  lea     r9, qword_180066740; pHandles
0x180029ea9  mov     r8d, 1; cHandles
0x180029eaf  or      edx, 0FFFFFFFFh; dwTimeout
0x180029eb2  lea     ecx, [r8+7]; dwFlags
0x180029eb6  call    cs:__imp_CoWaitForMultipleHandles
0x180029ebc  mov     r8b, 3
0x180029ebf  mov     dl, 1
0x180029ec1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180029ec8  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180029ecd  lea     rsi, stru_1800667D0
0x180029ed4  mov     rcx, rsi; lpCriticalSection
0x180029ed7  call    cs:__imp_EnterCriticalSection
0x180029edd  mov     [rsp+38h+arg_10], rsi
0x180029ee2  lea     rdx, [rsp+38h+arg_0]
0x180029ee7  mov     rcx, rdi
0x180029eea  call    ?LockHandleNotificationExclusive@CCallback@?$CSingletonHelper@UPowerAdapter@1Internal@Windows@winrt@@@DataModel@SystemSettings@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::CCallback::LockHandleNotificationExclusive(void)
0x180029eef  nop
0x180029ef0  lea     rdx, [rsp+38h+arg_8]
0x180029ef5  lea     rcx, qword_180066758
0x180029efc  call    ??$_Erase@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@6@$0A@@std@@@std@@AEAA_KAEBQEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>(SystemSettings::DataModel::CSingletonHelper<bool>::CCallback * const &)
0x180029f01  nop
0x180029f02  lea     rcx, [rsp+38h+arg_0]
0x180029f07  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180029f0c  lea     rcx, [rsp+38h+arg_10]; this
0x180029f11  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180029f16  xor     sil, sil
0x180029f19  lea     rdi, stru_1800667A0
0x180029f20  mov     rcx, rdi; lpCriticalSection
0x180029f23  call    cs:__imp_EnterCriticalSection
0x180029f29  mov     [rsp+38h+arg_0], rdi
0x180029f2e  mov     r8b, 3
0x180029f31  mov     dl, 1
0x180029f33  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180029f3a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180029f3f  cmp     cs:dword_1800667C8, 0
0x180029f46  jnz     short loc_180029FB0
0x180029f48  cmp     cs:qword_180066768, 0
0x180029f50  jnz     short loc_180029FB0
0x180029f52  cmp     cs:byte_180066800, sil
0x180029f59  jnz     short loc_180029FB0
0x180029f5b  cmp     cs:dword_180066810, 0
0x180029f62  jl      short loc_180029FB0
0x180029f64  mov     sil, 1
0x180029f67  mov     cs:byte_180066800, sil
0x180029f6e  mov     rdi, cs:qword_1800667F8
0x180029f75  test    rdi, rdi
0x180029f78  jnz     short loc_180029FA6
0x180029f7a  xor     r9d, r9d; lpName
0x180029f7d  xor     r8d, r8d; bInitialState
0x180029f80  lea     edx, [rdi+1]; bManualReset
0x180029f83  xor     ecx, ecx; lpEventAttributes
0x180029f85  call    cs:__imp_CreateEventW
0x180029f8b  mov     rdi, rax
0x180029f8e  lea     rcx, qword_1800667F8
0x180029f95  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180029f9a  mov     cs:qword_1800667F8, rdi
0x180029fa1  test    rdi, rdi
0x180029fa4  jz      short loc_180029FB0
0x180029fa6  mov     rcx, rdi; hEvent
0x180029fa9  call    cs:__imp_ResetEvent
0x180029faf  nop
0x180029fb0  lea     rcx, [rsp+38h+arg_0]; this
0x180029fb5  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180029fba  test    sil, sil
0x180029fbd  jz      short loc_18002A00D
0x180029fbf  mov     rax, cs:?g_AdaptiveModeSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VAdaptiveModeSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeSingleton SystemSettings::BatterySaverOneCoreDataModel::g_AdaptiveModeSingleton
0x180029fc6  lea     rcx, ?g_AdaptiveModeSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VAdaptiveModeSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeSingleton SystemSettings::BatterySaverOneCoreDataModel::g_AdaptiveModeSingleton
0x180029fcd  mov     rax, [rax+10h]
0x180029fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029fd6  nop
0x180029fd7  mov     cs:byte_18006679A, 0
0x180029fde  mov     cs:dword_180066810, 8000FFFFh
0x180029fe8  lea     rcx, qword_180066808; this
0x180029fef  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x180029ff4  mov     cs:byte_180066800, 0
0x180029ffb  mov     rcx, cs:qword_1800667F8; hEvent
0x18002a002  test    rcx, rcx
0x18002a005  jz      short loc_18002A00D
0x18002a007  call    cs:__imp_SetEvent
0x18002a00d  mov     r8b, 3
0x18002a010  mov     dl, 1
0x18002a012  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18002a019  mov     rsi, [rsp+38h+arg_18]
0x18002a01e  add     rsp, 30h
0x18002a022  pop     rdi
0x18002a023  jmp     ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
```
