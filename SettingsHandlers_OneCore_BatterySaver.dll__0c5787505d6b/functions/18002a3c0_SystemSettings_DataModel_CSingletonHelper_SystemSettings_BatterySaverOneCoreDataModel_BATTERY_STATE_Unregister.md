# SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::Unregister(SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::CCallback *)

- ea: `0x18002a3c0`
- end: `0x18002a542`
- name: `?Unregister@?$CSingletonHelper@W4_BATTERY_STATE@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `386`
- prototype: ``
- caller_count: `18`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001a630`
- `0x18001a91c`
- `0x18001a99c`
- `0x18001aac8`
- `0x18001ac14`
- `0x180024ed0`
- `0x180024f60`
- `0x180024fc0`
- `0x18002cd2c`
- `0x18002f620`
- `0x18003ac9c`
- `0x18003b138`
- `0x18003b3a0`
- `0x18003ba74`
- `0x18003c0f0`
- `0x18003d000`
- `0x18003dea0`
- `0x180046980`

## callees

- `0x18000b508`
- `0x180012c58`
- `0x18001314c`
- `0x18001760c`
- `0x18001eec8`
- `0x180024214`
- `0x180026bf0`
- `0x1800271c0`
- `0x18002a3c0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002a4a0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002a4a0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002a524`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002a524`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a3f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a442`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a3f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a442`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002a4c4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002a4c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::Unregister(
        RTL_SRWLOCK *a1,
        __int64 a2)
{
  __int64 v3; // r8
  __int64 v4; // rdx
  char v5; // si
  __int64 v6; // r8
  __int64 v7; // rdx
  HANDLE EventW; // rdi
  __int64 v9; // rdx
  __int64 v10; // r8
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  RTL_SRWLOCK *v14; // [rsp+40h] [rbp+8h] BYREF
  __int64 v15; // [rsp+48h] [rbp+10h] BYREF
  struct _RTL_CRITICAL_SECTION *v16; // [rsp+50h] [rbp+18h] BYREF

  v15 = a2;
  v14 = a1;
  SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::GetInitResultWait();
  LOBYTE(v3) = 3;
  LOBYTE(v4) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v4,
    v3);
  EnterCriticalSection(&stru_1800662F0);
  v16 = &stru_1800662F0;
  SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::CCallback::LockHandleNotificationExclusive(
    a2,
    &v14);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>(
    qword_180066278,
    (unsigned __int8 *)&v15);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v16);
  v5 = 0;
  EnterCriticalSection(&stru_1800662C0);
  v14 = (RTL_SRWLOCK *)&stru_1800662C0;
  LOBYTE(v6) = 3;
  LOBYTE(v7) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v7,
    v6);
  if ( !dword_1800662E8 && !qword_180066288 && !byte_180066320 && dword_180066330 >= 0 )
  {
    v5 = 1;
    byte_180066320 = 1;
    EventW = qword_180066318;
    if ( qword_180066318
      || (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&qword_180066318),
          (qword_180066318 = EventW) != 0) )
    {
      ResetEvent(EventW);
    }
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v14);
  if ( v5 )
  {
    try
    {
      (*(void (__fastcall **)(__int64 *))(SystemSettings::BatterySaverOneCoreDataModel::g_CBatteryStateSingleton + 16))(&SystemSettings::BatterySaverOneCoreDataModel::g_CBatteryStateSingleton);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x545,
        (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingHandlersBaseCore.h",
        v11);
    }
    byte_1800662BA = 0;
    dword_180066330 = -2147418113;
    SystemSettings::DataModel::AutoMTAUsageCookie::Release((SystemSettings::DataModel::AutoMTAUsageCookie *)&qword_180066328);
    byte_180066320 = 0;
    if ( qword_180066318 )
      SetEvent(qword_180066318);
  }
  LOBYTE(v10) = 3;
  LOBYTE(v9) = 1;
  return wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
           `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
           v9,
           v10);
}

```

## disassembly

```asm
0x18002a3c0  mov     [rsp+arg_8], rdx
0x18002a3c5  mov     [rsp+arg_0], rcx
0x18002a3ca  push    rbx
0x18002a3cb  push    rsi
0x18002a3cc  push    rdi
0x18002a3cd  sub     rsp, 20h
0x18002a3d1  mov     rbx, rdx
0x18002a3d4  call    ?GetInitResultWait@?$CSingletonHelper@W4_BATTERY_STATE@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAJXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::GetInitResultWait(void)
0x18002a3d9  mov     r8b, 3
0x18002a3dc  mov     dl, 1
0x18002a3de  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18002a3e5  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002a3ea  lea     rdi, stru_1800662F0
0x18002a3f1  mov     rcx, rdi; lpCriticalSection
0x18002a3f4  call    cs:__imp_EnterCriticalSection
0x18002a3fa  mov     [rsp+38h+arg_10], rdi
0x18002a3ff  lea     rdx, [rsp+38h+arg_0]
0x18002a404  mov     rcx, rbx
0x18002a407  call    ?LockHandleNotificationExclusive@CCallback@?$CSingletonHelper@UPowerAdapter@1Internal@Windows@winrt@@@DataModel@SystemSettings@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::CCallback::LockHandleNotificationExclusive(void)
0x18002a40c  nop
0x18002a40d  lea     rdx, [rsp+38h+arg_8]
0x18002a412  lea     rcx, qword_180066278
0x18002a419  call    ??$_Erase@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@6@$0A@@std@@@std@@AEAA_KAEBQEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>(SystemSettings::DataModel::CSingletonHelper<int>::CCallback * const &)
0x18002a41e  nop
0x18002a41f  lea     rcx, [rsp+38h+arg_0]
0x18002a424  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002a429  lea     rcx, [rsp+38h+arg_10]; this
0x18002a42e  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18002a433  xor     ebx, ebx
0x18002a435  mov     sil, bl
0x18002a438  lea     rdi, stru_1800662C0
0x18002a43f  mov     rcx, rdi; lpCriticalSection
0x18002a442  call    cs:__imp_EnterCriticalSection
0x18002a448  mov     [rsp+38h+arg_0], rdi
0x18002a44d  mov     r8b, 3
0x18002a450  mov     dl, 1
0x18002a452  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18002a459  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002a45e  cmp     cs:dword_1800662E8, ebx
0x18002a464  jnz     short loc_18002A4CB
0x18002a466  cmp     cs:qword_180066288, rbx
0x18002a46d  jnz     short loc_18002A4CB
0x18002a46f  cmp     cs:byte_180066320, bl
0x18002a475  jnz     short loc_18002A4CB
0x18002a477  cmp     cs:dword_180066330, ebx
0x18002a47d  jl      short loc_18002A4CB
0x18002a47f  mov     sil, 1
0x18002a482  mov     cs:byte_180066320, sil
0x18002a489  mov     rdi, cs:qword_180066318
0x18002a490  test    rdi, rdi
0x18002a493  jnz     short loc_18002A4C1
0x18002a495  xor     r9d, r9d; lpName
0x18002a498  xor     r8d, r8d; bInitialState
0x18002a49b  lea     edx, [rbx+1]; bManualReset
0x18002a49e  xor     ecx, ecx; lpEventAttributes
0x18002a4a0  call    cs:__imp_CreateEventW
0x18002a4a6  mov     rdi, rax
0x18002a4a9  lea     rcx, qword_180066318
0x18002a4b0  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18002a4b5  mov     cs:qword_180066318, rdi
0x18002a4bc  test    rdi, rdi
0x18002a4bf  jz      short loc_18002A4CB
0x18002a4c1  mov     rcx, rdi; hEvent
0x18002a4c4  call    cs:__imp_ResetEvent
0x18002a4ca  nop
0x18002a4cb  lea     rcx, [rsp+38h+arg_0]; this
0x18002a4d0  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18002a4d5  test    sil, sil
0x18002a4d8  jz      short loc_18002A52A
0x18002a4da  mov     rax, cs:?g_CBatteryStateSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCBatteryStateSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CBatteryStateSingleton SystemSettings::BatterySaverOneCoreDataModel::g_CBatteryStateSingleton
0x18002a4e1  lea     rcx, ?g_CBatteryStateSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCBatteryStateSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CBatteryStateSingleton SystemSettings::BatterySaverOneCoreDataModel::g_CBatteryStateSingleton
0x18002a4e8  mov     rax, [rax+10h]
0x18002a4ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a4f1  nop
0x18002a4f2  jmp     short loc_18002A4F6
0x18002a4f4  xor     ebx, ebx
0x18002a4f6  mov     cs:byte_1800662BA, bl
0x18002a4fc  mov     cs:dword_180066330, 8000FFFFh
0x18002a506  lea     rcx, qword_180066328; this
0x18002a50d  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x18002a512  mov     cs:byte_180066320, bl
0x18002a518  mov     rcx, cs:qword_180066318; hEvent
0x18002a51f  test    rcx, rcx
0x18002a522  jz      short loc_18002A52A
0x18002a524  call    cs:__imp_SetEvent
0x18002a52a  mov     r8b, 3
0x18002a52d  mov     dl, 1
0x18002a52f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18002a536  add     rsp, 20h
0x18002a53a  pop     rdi
0x18002a53b  pop     rsi
0x18002a53c  pop     rbx
0x18002a53d  jmp     ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
```
