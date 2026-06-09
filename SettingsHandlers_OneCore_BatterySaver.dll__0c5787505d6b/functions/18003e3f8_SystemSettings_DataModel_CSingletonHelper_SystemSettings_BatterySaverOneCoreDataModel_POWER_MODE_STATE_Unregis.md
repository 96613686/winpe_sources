# SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_POWER_MODE_STATE>::Unregister(SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_POWER_MODE_STATE>::CCallback *)

- ea: `0x18003e3f8`
- end: `0x18003e5ba`
- name: `?Unregister@?$CSingletonHelper@U_POWER_MODE_STATE@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `450`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003d000`
- `0x18003dea0`

## callees

- `0x18000b508`
- `0x180012c58`
- `0x18001314c`
- `0x18001760c`
- `0x180024214`
- `0x180026bf0`
- `0x1800271c0`
- `0x18003e3f8`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003e515`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003e515`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003e599`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003e599`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e467`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e4b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e467`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e4b3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003e539`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003e539`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18003e446`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18003e446`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_POWER_MODE_STATE>::Unregister(
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
  if ( !byte_180065E9A && qword_180065E40 )
  {
    LODWORD(lpdwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &qword_180065E40, (LPDWORD)&lpdwindex);
  }
  LOBYTE(a3) = 3;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    a2,
    a3);
  EnterCriticalSection(&stru_180065ED0);
  v13 = &stru_180065ED0;
  SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::CCallback::LockHandleNotificationExclusive(
    v3,
    &lpdwindex);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>(
    qword_180065E58,
    (unsigned __int8 *)&v12);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lpdwindex);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v13);
  v4 = 0;
  EnterCriticalSection(&stru_180065EA0);
  lpdwindex = (RTL_SRWLOCK *)&stru_180065EA0;
  LOBYTE(v5) = 3;
  LOBYTE(v6) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v6,
    v5);
  if ( !dword_180065EC8 && !qword_180065E68 && !byte_180065F00 && dword_180065F10 >= 0 )
  {
    v4 = 1;
    byte_180065F00 = 1;
    EventW = qword_180065EF8;
    if ( qword_180065EF8
      || (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&qword_180065EF8),
          (qword_180065EF8 = EventW) != 0) )
    {
      ResetEvent(EventW);
    }
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&lpdwindex);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64 *))(SystemSettings::BatterySaverOneCoreDataModel::g_CPowerModeSingleton + 16))(&SystemSettings::BatterySaverOneCoreDataModel::g_CPowerModeSingleton);
    byte_180065E9A = 0;
    dword_180065F10 = -2147418113;
    SystemSettings::DataModel::AutoMTAUsageCookie::Release((SystemSettings::DataModel::AutoMTAUsageCookie *)&qword_180065F08);
    byte_180065F00 = 0;
    if ( qword_180065EF8 )
      SetEvent(qword_180065EF8);
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
0x18003e3f8  mov     rax, rsp
0x18003e3fb  mov     [rax+20h], rsi
0x18003e3ff  mov     [rax+10h], rdx
0x18003e403  mov     [rax+8], rcx
0x18003e407  push    rdi
0x18003e408  sub     rsp, 30h
0x18003e40c  mov     rdi, rdx
0x18003e40f  cmp     cs:byte_180065E9A, 0
0x18003e416  jnz     short loc_18003E44C
0x18003e418  cmp     cs:qword_180065E40, 0
0x18003e420  jz      short loc_18003E44C
0x18003e422  mov     dword ptr [rax+8], 0
0x18003e429  lea     rax, [rax+8]
0x18003e42d  mov     [rsp+38h+lpdwindex], rax; lpdwindex
0x18003e432  lea     r9, qword_180065E40; pHandles
0x18003e439  mov     r8d, 1; cHandles
0x18003e43f  or      edx, 0FFFFFFFFh; dwTimeout
0x18003e442  lea     ecx, [r8+7]; dwFlags
0x18003e446  call    cs:__imp_CoWaitForMultipleHandles
0x18003e44c  mov     r8b, 3
0x18003e44f  mov     dl, 1
0x18003e451  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18003e458  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003e45d  lea     rsi, stru_180065ED0
0x18003e464  mov     rcx, rsi; lpCriticalSection
0x18003e467  call    cs:__imp_EnterCriticalSection
0x18003e46d  mov     [rsp+38h+arg_10], rsi
0x18003e472  lea     rdx, [rsp+38h+arg_0]
0x18003e477  mov     rcx, rdi
0x18003e47a  call    ?LockHandleNotificationExclusive@CCallback@?$CSingletonHelper@UPowerAdapter@1Internal@Windows@winrt@@@DataModel@SystemSettings@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::CCallback::LockHandleNotificationExclusive(void)
0x18003e47f  nop
0x18003e480  lea     rdx, [rsp+38h+arg_8]
0x18003e485  lea     rcx, qword_180065E58
0x18003e48c  call    ??$_Erase@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@6@$0A@@std@@@std@@AEAA_KAEBQEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>(SystemSettings::DataModel::CSingletonHelper<int>::CCallback * const &)
0x18003e491  nop
0x18003e492  lea     rcx, [rsp+38h+arg_0]
0x18003e497  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003e49c  lea     rcx, [rsp+38h+arg_10]; this
0x18003e4a1  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18003e4a6  xor     sil, sil
0x18003e4a9  lea     rdi, stru_180065EA0
0x18003e4b0  mov     rcx, rdi; lpCriticalSection
0x18003e4b3  call    cs:__imp_EnterCriticalSection
0x18003e4b9  mov     [rsp+38h+arg_0], rdi
0x18003e4be  mov     r8b, 3
0x18003e4c1  mov     dl, 1
0x18003e4c3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18003e4ca  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003e4cf  cmp     cs:dword_180065EC8, 0
0x18003e4d6  jnz     short loc_18003E540
0x18003e4d8  cmp     cs:qword_180065E68, 0
0x18003e4e0  jnz     short loc_18003E540
0x18003e4e2  cmp     cs:byte_180065F00, sil
0x18003e4e9  jnz     short loc_18003E540
0x18003e4eb  cmp     cs:dword_180065F10, 0
0x18003e4f2  jl      short loc_18003E540
0x18003e4f4  mov     sil, 1
0x18003e4f7  mov     cs:byte_180065F00, sil
0x18003e4fe  mov     rdi, cs:qword_180065EF8
0x18003e505  test    rdi, rdi
0x18003e508  jnz     short loc_18003E536
0x18003e50a  xor     r9d, r9d; lpName
0x18003e50d  xor     r8d, r8d; bInitialState
0x18003e510  lea     edx, [rdi+1]; bManualReset
0x18003e513  xor     ecx, ecx; lpEventAttributes
0x18003e515  call    cs:__imp_CreateEventW
0x18003e51b  mov     rdi, rax
0x18003e51e  lea     rcx, qword_180065EF8
0x18003e525  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18003e52a  mov     cs:qword_180065EF8, rdi
0x18003e531  test    rdi, rdi
0x18003e534  jz      short loc_18003E540
0x18003e536  mov     rcx, rdi; hEvent
0x18003e539  call    cs:__imp_ResetEvent
0x18003e53f  nop
0x18003e540  lea     rcx, [rsp+38h+arg_0]; this
0x18003e545  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18003e54a  test    sil, sil
0x18003e54d  jz      short loc_18003E59F
0x18003e54f  mov     rax, cs:?g_CPowerModeSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCPowerModeSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CPowerModeSingleton SystemSettings::BatterySaverOneCoreDataModel::g_CPowerModeSingleton
0x18003e556  lea     rcx, ?g_CPowerModeSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCPowerModeSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CPowerModeSingleton SystemSettings::BatterySaverOneCoreDataModel::g_CPowerModeSingleton
0x18003e55d  mov     rax, [rax+10h]
0x18003e561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e566  nop
0x18003e567  jmp     short $+2
0x18003e569  mov     cs:byte_180065E9A, 0
0x18003e570  mov     cs:dword_180065F10, 8000FFFFh
0x18003e57a  lea     rcx, qword_180065F08; this
0x18003e581  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x18003e586  mov     cs:byte_180065F00, 0
0x18003e58d  mov     rcx, cs:qword_180065EF8; hEvent
0x18003e594  test    rcx, rcx
0x18003e597  jz      short loc_18003E59F
0x18003e599  call    cs:__imp_SetEvent
0x18003e59f  mov     r8b, 3
0x18003e5a2  mov     dl, 1
0x18003e5a4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18003e5ab  mov     rsi, [rsp+38h+arg_18]
0x18003e5b0  add     rsp, 30h
0x18003e5b4  pop     rdi
0x18003e5b5  jmp     ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
```
