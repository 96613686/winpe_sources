# SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::Unregister(SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::CCallback *)

- ea: `0x18002a1f8`
- end: `0x18002a3ba`
- name: `?Unregister@?$CSingletonHelper@W4BatterySaverInfoType@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `450`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001a6dc`
- `0x180024f30`
- `0x18002cd2c`
- `0x18002f620`
- `0x18002fb74`

## callees

- `0x18000b508`
- `0x180012c58`
- `0x18001314c`
- `0x18001760c`
- `0x180024214`
- `0x180026bf0`
- `0x1800271c0`
- `0x18002a1f8`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002a315`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002a315`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002a399`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002a399`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a267`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a2b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a267`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a2b3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002a339`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002a339`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18002a246`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18002a246`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::Unregister(
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
  if ( !byte_1800656AA && qword_180065650 )
  {
    LODWORD(lpdwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &qword_180065650, (LPDWORD)&lpdwindex);
  }
  LOBYTE(a3) = 3;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    a2,
    a3);
  EnterCriticalSection(&stru_1800656E0);
  v13 = &stru_1800656E0;
  SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::CCallback::LockHandleNotificationExclusive(
    v3,
    &lpdwindex);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>(
    qword_180065668,
    (unsigned __int8 *)&v12);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lpdwindex);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v13);
  v4 = 0;
  EnterCriticalSection(&stru_1800656B0);
  lpdwindex = (RTL_SRWLOCK *)&stru_1800656B0;
  LOBYTE(v5) = 3;
  LOBYTE(v6) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v6,
    v5);
  if ( !dword_1800656D8 && !qword_180065678 && !byte_180065710 && dword_180065720 >= 0 )
  {
    v4 = 1;
    byte_180065710 = 1;
    EventW = qword_180065708;
    if ( qword_180065708
      || (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&qword_180065708),
          (qword_180065708 = EventW) != 0) )
    {
      ResetEvent(EventW);
    }
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&lpdwindex);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64 *))(SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverBatteryInfoSingleton
                                      + 16))(&SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverBatteryInfoSingleton);
    byte_1800656AA = 0;
    dword_180065720 = -2147418113;
    SystemSettings::DataModel::AutoMTAUsageCookie::Release((SystemSettings::DataModel::AutoMTAUsageCookie *)&qword_180065718);
    byte_180065710 = 0;
    if ( qword_180065708 )
      SetEvent(qword_180065708);
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
0x18002a1f8  mov     rax, rsp
0x18002a1fb  mov     [rax+20h], rsi
0x18002a1ff  mov     [rax+10h], rdx
0x18002a203  mov     [rax+8], rcx
0x18002a207  push    rdi
0x18002a208  sub     rsp, 30h
0x18002a20c  mov     rdi, rdx
0x18002a20f  cmp     cs:byte_1800656AA, 0
0x18002a216  jnz     short loc_18002A24C
0x18002a218  cmp     cs:qword_180065650, 0
0x18002a220  jz      short loc_18002A24C
0x18002a222  mov     dword ptr [rax+8], 0
0x18002a229  lea     rax, [rax+8]
0x18002a22d  mov     [rsp+38h+lpdwindex], rax; lpdwindex
0x18002a232  lea     r9, qword_180065650; pHandles
0x18002a239  mov     r8d, 1; cHandles
0x18002a23f  or      edx, 0FFFFFFFFh; dwTimeout
0x18002a242  lea     ecx, [r8+7]; dwFlags
0x18002a246  call    cs:__imp_CoWaitForMultipleHandles
0x18002a24c  mov     r8b, 3
0x18002a24f  mov     dl, 1
0x18002a251  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18002a258  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002a25d  lea     rsi, stru_1800656E0
0x18002a264  mov     rcx, rsi; lpCriticalSection
0x18002a267  call    cs:__imp_EnterCriticalSection
0x18002a26d  mov     [rsp+38h+arg_10], rsi
0x18002a272  lea     rdx, [rsp+38h+arg_0]
0x18002a277  mov     rcx, rdi
0x18002a27a  call    ?LockHandleNotificationExclusive@CCallback@?$CSingletonHelper@UPowerAdapter@1Internal@Windows@winrt@@@DataModel@SystemSettings@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::CCallback::LockHandleNotificationExclusive(void)
0x18002a27f  nop
0x18002a280  lea     rdx, [rsp+38h+arg_8]
0x18002a285  lea     rcx, qword_180065668
0x18002a28c  call    ??$_Erase@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@6@$0A@@std@@@std@@AEAA_KAEBQEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>(SystemSettings::DataModel::CSingletonHelper<int>::CCallback * const &)
0x18002a291  nop
0x18002a292  lea     rcx, [rsp+38h+arg_0]
0x18002a297  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002a29c  lea     rcx, [rsp+38h+arg_10]; this
0x18002a2a1  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18002a2a6  xor     sil, sil
0x18002a2a9  lea     rdi, stru_1800656B0
0x18002a2b0  mov     rcx, rdi; lpCriticalSection
0x18002a2b3  call    cs:__imp_EnterCriticalSection
0x18002a2b9  mov     [rsp+38h+arg_0], rdi
0x18002a2be  mov     r8b, 3
0x18002a2c1  mov     dl, 1
0x18002a2c3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18002a2ca  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002a2cf  cmp     cs:dword_1800656D8, 0
0x18002a2d6  jnz     short loc_18002A340
0x18002a2d8  cmp     cs:qword_180065678, 0
0x18002a2e0  jnz     short loc_18002A340
0x18002a2e2  cmp     cs:byte_180065710, sil
0x18002a2e9  jnz     short loc_18002A340
0x18002a2eb  cmp     cs:dword_180065720, 0
0x18002a2f2  jl      short loc_18002A340
0x18002a2f4  mov     sil, 1
0x18002a2f7  mov     cs:byte_180065710, sil
0x18002a2fe  mov     rdi, cs:qword_180065708
0x18002a305  test    rdi, rdi
0x18002a308  jnz     short loc_18002A336
0x18002a30a  xor     r9d, r9d; lpName
0x18002a30d  xor     r8d, r8d; bInitialState
0x18002a310  lea     edx, [rdi+1]; bManualReset
0x18002a313  xor     ecx, ecx; lpEventAttributes
0x18002a315  call    cs:__imp_CreateEventW
0x18002a31b  mov     rdi, rax
0x18002a31e  lea     rcx, qword_180065708
0x18002a325  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18002a32a  mov     cs:qword_180065708, rdi
0x18002a331  test    rdi, rdi
0x18002a334  jz      short loc_18002A340
0x18002a336  mov     rcx, rdi; hEvent
0x18002a339  call    cs:__imp_ResetEvent
0x18002a33f  nop
0x18002a340  lea     rcx, [rsp+38h+arg_0]; this
0x18002a345  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18002a34a  test    sil, sil
0x18002a34d  jz      short loc_18002A39F
0x18002a34f  mov     rax, cs:?g_CBatterySaverBatteryInfoSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCBatterySaverBatteryInfoSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverBatteryInfoSingleton SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverBatteryInfoSingleton
0x18002a356  lea     rcx, ?g_CBatterySaverBatteryInfoSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCBatterySaverBatteryInfoSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverBatteryInfoSingleton SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverBatteryInfoSingleton
0x18002a35d  mov     rax, [rax+10h]
0x18002a361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a366  nop
0x18002a367  jmp     short $+2
0x18002a369  mov     cs:byte_1800656AA, 0
0x18002a370  mov     cs:dword_180065720, 8000FFFFh
0x18002a37a  lea     rcx, qword_180065718; this
0x18002a381  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x18002a386  mov     cs:byte_180065710, 0
0x18002a38d  mov     rcx, cs:qword_180065708; hEvent
0x18002a394  test    rcx, rcx
0x18002a397  jz      short loc_18002A39F
0x18002a399  call    cs:__imp_SetEvent
0x18002a39f  mov     r8b, 3
0x18002a3a2  mov     dl, 1
0x18002a3a4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18002a3ab  mov     rsi, [rsp+38h+arg_18]
0x18002a3b0  add     rsp, 30h
0x18002a3b4  pop     rdi
0x18002a3b5  jmp     ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
```
