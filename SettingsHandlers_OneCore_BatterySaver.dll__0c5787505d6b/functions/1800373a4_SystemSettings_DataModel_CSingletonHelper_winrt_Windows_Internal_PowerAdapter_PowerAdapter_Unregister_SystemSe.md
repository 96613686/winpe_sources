# SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::Unregister(SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::CCallback *)

- ea: `0x1800373a4`
- end: `0x180037564`
- name: `?Unregister@?$CSingletonHelper@UPowerAdapter@1Internal@Windows@winrt@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `448`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800345d8`
- `0x1800366a0`

## callees

- `0x18000b508`
- `0x180012c58`
- `0x18001314c`
- `0x1800176bc`
- `0x180024214`
- `0x180026bf0`
- `0x1800271c0`
- `0x1800373a4`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800374c1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800374c1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180037543`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180037543`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037413`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003745f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037413`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003745f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800374e5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800374e5`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800373f2`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800373f2`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::Unregister(
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
  if ( !byte_180065D7A && qword_180065D20 )
  {
    LODWORD(lpdwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &qword_180065D20, (LPDWORD)&lpdwindex);
  }
  LOBYTE(a3) = 3;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    a2,
    a3);
  EnterCriticalSection(&stru_180065DB0);
  v13 = &stru_180065DB0;
  SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::CCallback::LockHandleNotificationExclusive(
    v3,
    &lpdwindex);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>(
    &qword_180065D38,
    (const unsigned __int8 *)&v12);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lpdwindex);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v13);
  v4 = 0;
  EnterCriticalSection(&stru_180065D80);
  lpdwindex = (RTL_SRWLOCK *)&stru_180065D80;
  LOBYTE(v5) = 3;
  LOBYTE(v6) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v6,
    v5);
  if ( !dword_180065DA8 && !qword_180065D48 && !byte_180065DE0 && dword_180065DF0 >= 0 )
  {
    v4 = 1;
    byte_180065DE0 = 1;
    EventW = qword_180065DD8;
    if ( qword_180065DD8
      || (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&qword_180065DD8),
          (qword_180065DD8 = EventW) != 0) )
    {
      ResetEvent(EventW);
    }
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&lpdwindex);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64 *))(SystemSettings::BatterySaverOneCoreDataModel::g_CRenewableChargingSupportSingleton
                                      + 16))(&SystemSettings::BatterySaverOneCoreDataModel::g_CRenewableChargingSupportSingleton);
    byte_180065D7A = 0;
    dword_180065DF0 = -2147418113;
    SystemSettings::DataModel::AutoMTAUsageCookie::Release((SystemSettings::DataModel::AutoMTAUsageCookie *)&qword_180065DE8);
    byte_180065DE0 = 0;
    if ( qword_180065DD8 )
      SetEvent(qword_180065DD8);
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
0x1800373a4  mov     rax, rsp
0x1800373a7  mov     [rax+20h], rsi
0x1800373ab  mov     [rax+10h], rdx
0x1800373af  mov     [rax+8], rcx
0x1800373b3  push    rdi
0x1800373b4  sub     rsp, 30h
0x1800373b8  mov     rdi, rdx
0x1800373bb  cmp     cs:byte_180065D7A, 0
0x1800373c2  jnz     short loc_1800373F8
0x1800373c4  cmp     cs:qword_180065D20, 0
0x1800373cc  jz      short loc_1800373F8
0x1800373ce  mov     dword ptr [rax+8], 0
0x1800373d5  lea     rax, [rax+8]
0x1800373d9  mov     [rsp+38h+lpdwindex], rax; lpdwindex
0x1800373de  lea     r9, qword_180065D20; pHandles
0x1800373e5  mov     r8d, 1; cHandles
0x1800373eb  or      edx, 0FFFFFFFFh; dwTimeout
0x1800373ee  lea     ecx, [r8+7]; dwFlags
0x1800373f2  call    cs:__imp_CoWaitForMultipleHandles
0x1800373f8  mov     r8b, 3
0x1800373fb  mov     dl, 1
0x1800373fd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180037404  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180037409  lea     rsi, stru_180065DB0
0x180037410  mov     rcx, rsi; lpCriticalSection
0x180037413  call    cs:__imp_EnterCriticalSection
0x180037419  mov     [rsp+38h+arg_10], rsi
0x18003741e  lea     rdx, [rsp+38h+arg_0]
0x180037423  mov     rcx, rdi
0x180037426  call    ?LockHandleNotificationExclusive@CCallback@?$CSingletonHelper@UPowerAdapter@1Internal@Windows@winrt@@@DataModel@SystemSettings@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::CCallback::LockHandleNotificationExclusive(void)
0x18003742b  nop
0x18003742c  lea     rdx, [rsp+38h+arg_8]
0x180037431  lea     rcx, qword_180065D38
0x180037438  call    ??$_Erase@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@6@$0A@@std@@@std@@AEAA_KAEBQEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>(SystemSettings::DataModel::CSingletonHelper<bool>::CCallback * const &)
0x18003743d  nop
0x18003743e  lea     rcx, [rsp+38h+arg_0]
0x180037443  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180037448  lea     rcx, [rsp+38h+arg_10]; this
0x18003744d  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180037452  xor     sil, sil
0x180037455  lea     rdi, stru_180065D80
0x18003745c  mov     rcx, rdi; lpCriticalSection
0x18003745f  call    cs:__imp_EnterCriticalSection
0x180037465  mov     [rsp+38h+arg_0], rdi
0x18003746a  mov     r8b, 3
0x18003746d  mov     dl, 1
0x18003746f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180037476  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003747b  cmp     cs:dword_180065DA8, 0
0x180037482  jnz     short loc_1800374EC
0x180037484  cmp     cs:qword_180065D48, 0
0x18003748c  jnz     short loc_1800374EC
0x18003748e  cmp     cs:byte_180065DE0, sil
0x180037495  jnz     short loc_1800374EC
0x180037497  cmp     cs:dword_180065DF0, 0
0x18003749e  jl      short loc_1800374EC
0x1800374a0  mov     sil, 1
0x1800374a3  mov     cs:byte_180065DE0, sil
0x1800374aa  mov     rdi, cs:qword_180065DD8
0x1800374b1  test    rdi, rdi
0x1800374b4  jnz     short loc_1800374E2
0x1800374b6  xor     r9d, r9d; lpName
0x1800374b9  xor     r8d, r8d; bInitialState
0x1800374bc  lea     edx, [rdi+1]; bManualReset
0x1800374bf  xor     ecx, ecx; lpEventAttributes
0x1800374c1  call    cs:__imp_CreateEventW
0x1800374c7  mov     rdi, rax
0x1800374ca  lea     rcx, qword_180065DD8
0x1800374d1  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x1800374d6  mov     cs:qword_180065DD8, rdi
0x1800374dd  test    rdi, rdi
0x1800374e0  jz      short loc_1800374EC
0x1800374e2  mov     rcx, rdi; hEvent
0x1800374e5  call    cs:__imp_ResetEvent
0x1800374eb  nop
0x1800374ec  lea     rcx, [rsp+38h+arg_0]; this
0x1800374f1  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800374f6  test    sil, sil
0x1800374f9  jz      short loc_180037549
0x1800374fb  mov     rax, cs:?g_CRenewableChargingSupportSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCRenewableChargingSupportSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CRenewableChargingSupportSingleton SystemSettings::BatterySaverOneCoreDataModel::g_CRenewableChargingSupportSingleton
0x180037502  lea     rcx, ?g_CRenewableChargingSupportSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCRenewableChargingSupportSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CRenewableChargingSupportSingleton SystemSettings::BatterySaverOneCoreDataModel::g_CRenewableChargingSupportSingleton
0x180037509  mov     rax, [rax+10h]
0x18003750d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037512  nop
0x180037513  mov     cs:byte_180065D7A, 0
0x18003751a  mov     cs:dword_180065DF0, 8000FFFFh
0x180037524  lea     rcx, qword_180065DE8; this
0x18003752b  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x180037530  mov     cs:byte_180065DE0, 0
0x180037537  mov     rcx, cs:qword_180065DD8; hEvent
0x18003753e  test    rcx, rcx
0x180037541  jz      short loc_180037549
0x180037543  call    cs:__imp_SetEvent
0x180037549  mov     r8b, 3
0x18003754c  mov     dl, 1
0x18003754e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180037555  mov     rsi, [rsp+38h+arg_18]
0x18003755a  add     rsp, 30h
0x18003755e  pop     rdi
0x18003755f  jmp     ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
```
