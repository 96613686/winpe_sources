# SystemSettings::DataModel::CSingletonHelper<bool>::Unregister(SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *)

- ea: `0x180031464`
- end: `0x180031624`
- name: `?Unregister@?$CSingletonHelper@_N@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `448`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800306cc`
- `0x180030f60`

## callees

- `0x18000b508`
- `0x180012c58`
- `0x18001314c`
- `0x1800176bc`
- `0x180024214`
- `0x180026bf0`
- `0x1800271c0`
- `0x180031464`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180031581`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180031581`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180031603`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180031603`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800314d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003151f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800314d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003151f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800315a5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800315a5`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800314b2`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800314b2`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<bool>::Unregister(
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
  if ( !byte_180065AAA && qword_180065A50 )
  {
    LODWORD(lpdwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &qword_180065A50, (LPDWORD)&lpdwindex);
  }
  LOBYTE(a3) = 3;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    a2,
    a3);
  EnterCriticalSection(&stru_180065AE0);
  v13 = &stru_180065AE0;
  SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::CCallback::LockHandleNotificationExclusive(
    v3,
    &lpdwindex);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>(
    &qword_180065A68,
    (const unsigned __int8 *)&v12);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lpdwindex);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v13);
  v4 = 0;
  EnterCriticalSection(&stru_180065AB0);
  lpdwindex = (RTL_SRWLOCK *)&stru_180065AB0;
  LOBYTE(v5) = 3;
  LOBYTE(v6) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v6,
    v5);
  if ( !dword_180065AD8 && !qword_180065A78 && !byte_180065B10 && dword_180065B20 >= 0 )
  {
    v4 = 1;
    byte_180065B10 = 1;
    EventW = qword_180065B08;
    if ( qword_180065B08
      || (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&qword_180065B08),
          (qword_180065B08 = EventW) != 0) )
    {
      ResetEvent(EventW);
    }
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&lpdwindex);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64 *))(SystemSettings::BatterySaverOneCoreDataModel::g_CBatteryPercentageToggleSingleton
                                      + 16))(&SystemSettings::BatterySaverOneCoreDataModel::g_CBatteryPercentageToggleSingleton);
    byte_180065AAA = 0;
    dword_180065B20 = -2147418113;
    SystemSettings::DataModel::AutoMTAUsageCookie::Release((SystemSettings::DataModel::AutoMTAUsageCookie *)&qword_180065B18);
    byte_180065B10 = 0;
    if ( qword_180065B08 )
      SetEvent(qword_180065B08);
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
0x180031464  mov     rax, rsp
0x180031467  mov     [rax+20h], rsi
0x18003146b  mov     [rax+10h], rdx
0x18003146f  mov     [rax+8], rcx
0x180031473  push    rdi
0x180031474  sub     rsp, 30h
0x180031478  mov     rdi, rdx
0x18003147b  cmp     cs:byte_180065AAA, 0
0x180031482  jnz     short loc_1800314B8
0x180031484  cmp     cs:qword_180065A50, 0
0x18003148c  jz      short loc_1800314B8
0x18003148e  mov     dword ptr [rax+8], 0
0x180031495  lea     rax, [rax+8]
0x180031499  mov     [rsp+38h+lpdwindex], rax; lpdwindex
0x18003149e  lea     r9, qword_180065A50; pHandles
0x1800314a5  mov     r8d, 1; cHandles
0x1800314ab  or      edx, 0FFFFFFFFh; dwTimeout
0x1800314ae  lea     ecx, [r8+7]; dwFlags
0x1800314b2  call    cs:__imp_CoWaitForMultipleHandles
0x1800314b8  mov     r8b, 3
0x1800314bb  mov     dl, 1
0x1800314bd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x1800314c4  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800314c9  lea     rsi, stru_180065AE0
0x1800314d0  mov     rcx, rsi; lpCriticalSection
0x1800314d3  call    cs:__imp_EnterCriticalSection
0x1800314d9  mov     [rsp+38h+arg_10], rsi
0x1800314de  lea     rdx, [rsp+38h+arg_0]
0x1800314e3  mov     rcx, rdi
0x1800314e6  call    ?LockHandleNotificationExclusive@CCallback@?$CSingletonHelper@UPowerAdapter@1Internal@Windows@winrt@@@DataModel@SystemSettings@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::CCallback::LockHandleNotificationExclusive(void)
0x1800314eb  nop
0x1800314ec  lea     rdx, [rsp+38h+arg_8]
0x1800314f1  lea     rcx, qword_180065A68
0x1800314f8  call    ??$_Erase@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@6@$0A@@std@@@std@@AEAA_KAEBQEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>(SystemSettings::DataModel::CSingletonHelper<bool>::CCallback * const &)
0x1800314fd  nop
0x1800314fe  lea     rcx, [rsp+38h+arg_0]
0x180031503  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180031508  lea     rcx, [rsp+38h+arg_10]; this
0x18003150d  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180031512  xor     sil, sil
0x180031515  lea     rdi, stru_180065AB0
0x18003151c  mov     rcx, rdi; lpCriticalSection
0x18003151f  call    cs:__imp_EnterCriticalSection
0x180031525  mov     [rsp+38h+arg_0], rdi
0x18003152a  mov     r8b, 3
0x18003152d  mov     dl, 1
0x18003152f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180031536  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003153b  cmp     cs:dword_180065AD8, 0
0x180031542  jnz     short loc_1800315AC
0x180031544  cmp     cs:qword_180065A78, 0
0x18003154c  jnz     short loc_1800315AC
0x18003154e  cmp     cs:byte_180065B10, sil
0x180031555  jnz     short loc_1800315AC
0x180031557  cmp     cs:dword_180065B20, 0
0x18003155e  jl      short loc_1800315AC
0x180031560  mov     sil, 1
0x180031563  mov     cs:byte_180065B10, sil
0x18003156a  mov     rdi, cs:qword_180065B08
0x180031571  test    rdi, rdi
0x180031574  jnz     short loc_1800315A2
0x180031576  xor     r9d, r9d; lpName
0x180031579  xor     r8d, r8d; bInitialState
0x18003157c  lea     edx, [rdi+1]; bManualReset
0x18003157f  xor     ecx, ecx; lpEventAttributes
0x180031581  call    cs:__imp_CreateEventW
0x180031587  mov     rdi, rax
0x18003158a  lea     rcx, qword_180065B08
0x180031591  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180031596  mov     cs:qword_180065B08, rdi
0x18003159d  test    rdi, rdi
0x1800315a0  jz      short loc_1800315AC
0x1800315a2  mov     rcx, rdi; hEvent
0x1800315a5  call    cs:__imp_ResetEvent
0x1800315ab  nop
0x1800315ac  lea     rcx, [rsp+38h+arg_0]; this
0x1800315b1  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800315b6  test    sil, sil
0x1800315b9  jz      short loc_180031609
0x1800315bb  mov     rax, cs:?g_CBatteryPercentageToggleSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCBatteryPercentageToggleSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CBatteryPercentageToggleSingleton SystemSettings::BatterySaverOneCoreDataModel::g_CBatteryPercentageToggleSingleton
0x1800315c2  lea     rcx, ?g_CBatteryPercentageToggleSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCBatteryPercentageToggleSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CBatteryPercentageToggleSingleton SystemSettings::BatterySaverOneCoreDataModel::g_CBatteryPercentageToggleSingleton
0x1800315c9  mov     rax, [rax+10h]
0x1800315cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800315d2  nop
0x1800315d3  mov     cs:byte_180065AAA, 0
0x1800315da  mov     cs:dword_180065B20, 8000FFFFh
0x1800315e4  lea     rcx, qword_180065B18; this
0x1800315eb  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x1800315f0  mov     cs:byte_180065B10, 0
0x1800315f7  mov     rcx, cs:qword_180065B08; hEvent
0x1800315fe  test    rcx, rcx
0x180031601  jz      short loc_180031609
0x180031603  call    cs:__imp_SetEvent
0x180031609  mov     r8b, 3
0x18003160c  mov     dl, 1
0x18003160e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180031615  mov     rsi, [rsp+38h+arg_18]
0x18003161a  add     rsp, 30h
0x18003161e  pop     rdi
0x18003161f  jmp     ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
```
