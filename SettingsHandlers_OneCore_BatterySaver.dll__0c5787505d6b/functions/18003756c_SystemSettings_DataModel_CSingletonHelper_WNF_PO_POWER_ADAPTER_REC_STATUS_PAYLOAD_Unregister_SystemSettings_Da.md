# SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::Unregister(SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *)

- ea: `0x18003756c`
- end: `0x18003772c`
- name: `?Unregister@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `448`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800346b4`
- `0x180036700`

## callees

- `0x18000b508`
- `0x180012c58`
- `0x18001314c`
- `0x1800176bc`
- `0x180024214`
- `0x180026bf0`
- `0x1800271c0`
- `0x18003756c`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180037689`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180037689`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003770b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003770b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800375db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037627`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800375db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037627`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800376ad`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800376ad`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800375ba`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800375ba`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::Unregister(
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
  if ( !byte_180065C8A && qword_180065C30 )
  {
    LODWORD(lpdwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &qword_180065C30, (LPDWORD)&lpdwindex);
  }
  LOBYTE(a3) = 3;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    a2,
    a3);
  EnterCriticalSection(&stru_180065CC0);
  v13 = &stru_180065CC0;
  SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::CCallback::LockHandleNotificationExclusive(
    v3,
    &lpdwindex);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>(
    qword_180065C48,
    (const unsigned __int8 *)&v12);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lpdwindex);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v13);
  v4 = 0;
  EnterCriticalSection(&stru_180065C90);
  lpdwindex = (RTL_SRWLOCK *)&stru_180065C90;
  LOBYTE(v5) = 3;
  LOBYTE(v6) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v6,
    v5);
  if ( !dword_180065CB8 && !qword_180065C58 && !byte_180065CF0 && dword_180065D00 >= 0 )
  {
    v4 = 1;
    byte_180065CF0 = 1;
    EventW = qword_180065CE8;
    if ( qword_180065CE8
      || (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&qword_180065CE8),
          (qword_180065CE8 = EventW) != 0) )
    {
      ResetEvent(EventW);
    }
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&lpdwindex);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64 *))(SystemSettings::BatterySaverOneCoreDataModel::g_CRenewableChargingStatusSingleton
                                      + 16))(&SystemSettings::BatterySaverOneCoreDataModel::g_CRenewableChargingStatusSingleton);
    byte_180065C8A = 0;
    dword_180065D00 = -2147418113;
    SystemSettings::DataModel::AutoMTAUsageCookie::Release((SystemSettings::DataModel::AutoMTAUsageCookie *)&qword_180065CF8);
    byte_180065CF0 = 0;
    if ( qword_180065CE8 )
      SetEvent(qword_180065CE8);
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
0x18003756c  mov     rax, rsp
0x18003756f  mov     [rax+20h], rsi
0x180037573  mov     [rax+10h], rdx
0x180037577  mov     [rax+8], rcx
0x18003757b  push    rdi
0x18003757c  sub     rsp, 30h
0x180037580  mov     rdi, rdx
0x180037583  cmp     cs:byte_180065C8A, 0
0x18003758a  jnz     short loc_1800375C0
0x18003758c  cmp     cs:qword_180065C30, 0
0x180037594  jz      short loc_1800375C0
0x180037596  mov     dword ptr [rax+8], 0
0x18003759d  lea     rax, [rax+8]
0x1800375a1  mov     [rsp+38h+lpdwindex], rax; lpdwindex
0x1800375a6  lea     r9, qword_180065C30; pHandles
0x1800375ad  mov     r8d, 1; cHandles
0x1800375b3  or      edx, 0FFFFFFFFh; dwTimeout
0x1800375b6  lea     ecx, [r8+7]; dwFlags
0x1800375ba  call    cs:__imp_CoWaitForMultipleHandles
0x1800375c0  mov     r8b, 3
0x1800375c3  mov     dl, 1
0x1800375c5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x1800375cc  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800375d1  lea     rsi, stru_180065CC0
0x1800375d8  mov     rcx, rsi; lpCriticalSection
0x1800375db  call    cs:__imp_EnterCriticalSection
0x1800375e1  mov     [rsp+38h+arg_10], rsi
0x1800375e6  lea     rdx, [rsp+38h+arg_0]
0x1800375eb  mov     rcx, rdi
0x1800375ee  call    ?LockHandleNotificationExclusive@CCallback@?$CSingletonHelper@UPowerAdapter@1Internal@Windows@winrt@@@DataModel@SystemSettings@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::CCallback::LockHandleNotificationExclusive(void)
0x1800375f3  nop
0x1800375f4  lea     rdx, [rsp+38h+arg_8]
0x1800375f9  lea     rcx, qword_180065C48
0x180037600  call    ??$_Erase@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@6@$0A@@std@@@std@@AEAA_KAEBQEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>(SystemSettings::DataModel::CSingletonHelper<bool>::CCallback * const &)
0x180037605  nop
0x180037606  lea     rcx, [rsp+38h+arg_0]
0x18003760b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180037610  lea     rcx, [rsp+38h+arg_10]; this
0x180037615  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18003761a  xor     sil, sil
0x18003761d  lea     rdi, stru_180065C90
0x180037624  mov     rcx, rdi; lpCriticalSection
0x180037627  call    cs:__imp_EnterCriticalSection
0x18003762d  mov     [rsp+38h+arg_0], rdi
0x180037632  mov     r8b, 3
0x180037635  mov     dl, 1
0x180037637  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18003763e  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180037643  cmp     cs:dword_180065CB8, 0
0x18003764a  jnz     short loc_1800376B4
0x18003764c  cmp     cs:qword_180065C58, 0
0x180037654  jnz     short loc_1800376B4
0x180037656  cmp     cs:byte_180065CF0, sil
0x18003765d  jnz     short loc_1800376B4
0x18003765f  cmp     cs:dword_180065D00, 0
0x180037666  jl      short loc_1800376B4
0x180037668  mov     sil, 1
0x18003766b  mov     cs:byte_180065CF0, sil
0x180037672  mov     rdi, cs:qword_180065CE8
0x180037679  test    rdi, rdi
0x18003767c  jnz     short loc_1800376AA
0x18003767e  xor     r9d, r9d; lpName
0x180037681  xor     r8d, r8d; bInitialState
0x180037684  lea     edx, [rdi+1]; bManualReset
0x180037687  xor     ecx, ecx; lpEventAttributes
0x180037689  call    cs:__imp_CreateEventW
0x18003768f  mov     rdi, rax
0x180037692  lea     rcx, qword_180065CE8
0x180037699  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18003769e  mov     cs:qword_180065CE8, rdi
0x1800376a5  test    rdi, rdi
0x1800376a8  jz      short loc_1800376B4
0x1800376aa  mov     rcx, rdi; hEvent
0x1800376ad  call    cs:__imp_ResetEvent
0x1800376b3  nop
0x1800376b4  lea     rcx, [rsp+38h+arg_0]; this
0x1800376b9  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800376be  test    sil, sil
0x1800376c1  jz      short loc_180037711
0x1800376c3  mov     rax, cs:?g_CRenewableChargingStatusSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCRenewableChargingStatusSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CRenewableChargingStatusSingleton SystemSettings::BatterySaverOneCoreDataModel::g_CRenewableChargingStatusSingleton
0x1800376ca  lea     rcx, ?g_CRenewableChargingStatusSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCRenewableChargingStatusSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CRenewableChargingStatusSingleton SystemSettings::BatterySaverOneCoreDataModel::g_CRenewableChargingStatusSingleton
0x1800376d1  mov     rax, [rax+10h]
0x1800376d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376da  nop
0x1800376db  mov     cs:byte_180065C8A, 0
0x1800376e2  mov     cs:dword_180065D00, 8000FFFFh
0x1800376ec  lea     rcx, qword_180065CF8; this
0x1800376f3  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x1800376f8  mov     cs:byte_180065CF0, 0
0x1800376ff  mov     rcx, cs:qword_180065CE8; hEvent
0x180037706  test    rcx, rcx
0x180037709  jz      short loc_180037711
0x18003770b  call    cs:__imp_SetEvent
0x180037711  mov     r8b, 3
0x180037714  mov     dl, 1
0x180037716  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18003771d  mov     rsi, [rsp+38h+arg_18]
0x180037722  add     rsp, 30h
0x180037726  pop     rdi
0x180037727  jmp     ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
```
