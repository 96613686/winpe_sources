# SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::Unregister(SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::CCallback *)

- ea: `0x18002a030`
- end: `0x18002a1f2`
- name: `?Unregister@?$CSingletonHelper@W4BatterySaverCallbackSetting@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `450`
- prototype: ``
- caller_count: `10`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001a630`
- `0x18001a99c`
- `0x18001aa48`
- `0x18001aac8`
- `0x18001ac14`
- `0x180024ed0`
- `0x180024f90`
- `0x180024fc0`
- `0x18003ac9c`
- `0x180046980`

## callees

- `0x18000b508`
- `0x180012c58`
- `0x18001314c`
- `0x18001760c`
- `0x180024214`
- `0x180026bf0`
- `0x1800271c0`
- `0x18002a030`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002a14d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002a14d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002a1d1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002a1d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a09f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a0eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a09f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a0eb`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002a171`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002a171`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18002a07e`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18002a07e`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::Unregister(
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
  RTL_SRWLOCK *lpdwindex; // [rsp+40h] [rbp+8h] BYREF
  __int64 v12; // [rsp+48h] [rbp+10h] BYREF
  struct _RTL_CRITICAL_SECTION *v13; // [rsp+50h] [rbp+18h] BYREF

  v12 = a2;
  lpdwindex = a1;
  v3 = a2;
  if ( !byte_1800655AA && qword_180065550 )
  {
    LODWORD(lpdwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &qword_180065550, (LPDWORD)&lpdwindex);
  }
  LOBYTE(a3) = 3;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    a2,
    a3);
  EnterCriticalSection(&stru_1800655E0);
  v13 = &stru_1800655E0;
  SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::CCallback::LockHandleNotificationExclusive(
    v3,
    &lpdwindex);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>(
    &qword_180065568,
    (unsigned __int8 *)&v12);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lpdwindex);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v13);
  v4 = 0;
  EnterCriticalSection(&stru_1800655B0);
  lpdwindex = (RTL_SRWLOCK *)&stru_1800655B0;
  LOBYTE(v5) = 3;
  LOBYTE(v6) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v6,
    v5);
  if ( !dword_1800655D8 && !qword_180065578 && !byte_180065610 && dword_180065620 >= 0 )
  {
    v4 = 1;
    byte_180065610 = 1;
    EventW = qword_180065608;
    if ( qword_180065608
      || (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&qword_180065608),
          (qword_180065608 = EventW) != 0) )
    {
      ResetEvent(EventW);
    }
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&lpdwindex);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64 *))(SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverSettingsSingleton
                                      + 16))(&SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverSettingsSingleton);
    byte_1800655AA = 0;
    dword_180065620 = -2147418113;
    SystemSettings::DataModel::AutoMTAUsageCookie::Release((SystemSettings::DataModel::AutoMTAUsageCookie *)&qword_180065618);
    byte_180065610 = 0;
    if ( qword_180065608 )
      SetEvent(qword_180065608);
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
0x18002a030  mov     rax, rsp
0x18002a033  mov     [rax+20h], rsi
0x18002a037  mov     [rax+10h], rdx
0x18002a03b  mov     [rax+8], rcx
0x18002a03f  push    rdi
0x18002a040  sub     rsp, 30h
0x18002a044  mov     rdi, rdx
0x18002a047  cmp     cs:byte_1800655AA, 0
0x18002a04e  jnz     short loc_18002A084
0x18002a050  cmp     cs:qword_180065550, 0
0x18002a058  jz      short loc_18002A084
0x18002a05a  mov     dword ptr [rax+8], 0
0x18002a061  lea     rax, [rax+8]
0x18002a065  mov     [rsp+38h+lpdwindex], rax; lpdwindex
0x18002a06a  lea     r9, qword_180065550; pHandles
0x18002a071  mov     r8d, 1; cHandles
0x18002a077  or      edx, 0FFFFFFFFh; dwTimeout
0x18002a07a  lea     ecx, [r8+7]; dwFlags
0x18002a07e  call    cs:__imp_CoWaitForMultipleHandles
0x18002a084  mov     r8b, 3
0x18002a087  mov     dl, 1
0x18002a089  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18002a090  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002a095  lea     rsi, stru_1800655E0
0x18002a09c  mov     rcx, rsi; lpCriticalSection
0x18002a09f  call    cs:__imp_EnterCriticalSection
0x18002a0a5  mov     [rsp+38h+arg_10], rsi
0x18002a0aa  lea     rdx, [rsp+38h+arg_0]
0x18002a0af  mov     rcx, rdi
0x18002a0b2  call    ?LockHandleNotificationExclusive@CCallback@?$CSingletonHelper@UPowerAdapter@1Internal@Windows@winrt@@@DataModel@SystemSettings@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::CCallback::LockHandleNotificationExclusive(void)
0x18002a0b7  nop
0x18002a0b8  lea     rdx, [rsp+38h+arg_8]
0x18002a0bd  lea     rcx, qword_180065568
0x18002a0c4  call    ??$_Erase@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@6@$0A@@std@@@std@@AEAA_KAEBQEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>(SystemSettings::DataModel::CSingletonHelper<int>::CCallback * const &)
0x18002a0c9  nop
0x18002a0ca  lea     rcx, [rsp+38h+arg_0]
0x18002a0cf  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002a0d4  lea     rcx, [rsp+38h+arg_10]; this
0x18002a0d9  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18002a0de  xor     sil, sil
0x18002a0e1  lea     rdi, stru_1800655B0
0x18002a0e8  mov     rcx, rdi; lpCriticalSection
0x18002a0eb  call    cs:__imp_EnterCriticalSection
0x18002a0f1  mov     [rsp+38h+arg_0], rdi
0x18002a0f6  mov     r8b, 3
0x18002a0f9  mov     dl, 1
0x18002a0fb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18002a102  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002a107  cmp     cs:dword_1800655D8, 0
0x18002a10e  jnz     short loc_18002A178
0x18002a110  cmp     cs:qword_180065578, 0
0x18002a118  jnz     short loc_18002A178
0x18002a11a  cmp     cs:byte_180065610, sil
0x18002a121  jnz     short loc_18002A178
0x18002a123  cmp     cs:dword_180065620, 0
0x18002a12a  jl      short loc_18002A178
0x18002a12c  mov     sil, 1
0x18002a12f  mov     cs:byte_180065610, sil
0x18002a136  mov     rdi, cs:qword_180065608
0x18002a13d  test    rdi, rdi
0x18002a140  jnz     short loc_18002A16E
0x18002a142  xor     r9d, r9d; lpName
0x18002a145  xor     r8d, r8d; bInitialState
0x18002a148  lea     edx, [rdi+1]; bManualReset
0x18002a14b  xor     ecx, ecx; lpEventAttributes
0x18002a14d  call    cs:__imp_CreateEventW
0x18002a153  mov     rdi, rax
0x18002a156  lea     rcx, qword_180065608
0x18002a15d  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18002a162  mov     cs:qword_180065608, rdi
0x18002a169  test    rdi, rdi
0x18002a16c  jz      short loc_18002A178
0x18002a16e  mov     rcx, rdi; hEvent
0x18002a171  call    cs:__imp_ResetEvent
0x18002a177  nop
0x18002a178  lea     rcx, [rsp+38h+arg_0]; this
0x18002a17d  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18002a182  test    sil, sil
0x18002a185  jz      short loc_18002A1D7
0x18002a187  mov     rax, cs:?g_CBatterySaverSettingsSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCBatterySaverSettingsSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsSingleton SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverSettingsSingleton
0x18002a18e  lea     rcx, ?g_CBatterySaverSettingsSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCBatterySaverSettingsSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsSingleton SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverSettingsSingleton
0x18002a195  mov     rax, [rax+10h]
0x18002a199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a19e  nop
0x18002a19f  jmp     short $+2
0x18002a1a1  mov     cs:byte_1800655AA, 0
0x18002a1a8  mov     cs:dword_180065620, 8000FFFFh
0x18002a1b2  lea     rcx, qword_180065618; this
0x18002a1b9  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x18002a1be  mov     cs:byte_180065610, 0
0x18002a1c5  mov     rcx, cs:qword_180065608; hEvent
0x18002a1cc  test    rcx, rcx
0x18002a1cf  jz      short loc_18002A1D7
0x18002a1d1  call    cs:__imp_SetEvent
0x18002a1d7  mov     r8b, 3
0x18002a1da  mov     dl, 1
0x18002a1dc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18002a1e3  mov     rsi, [rsp+38h+arg_18]
0x18002a1e8  add     rsp, 30h
0x18002a1ec  pop     rdi
0x18002a1ed  jmp     ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
```
