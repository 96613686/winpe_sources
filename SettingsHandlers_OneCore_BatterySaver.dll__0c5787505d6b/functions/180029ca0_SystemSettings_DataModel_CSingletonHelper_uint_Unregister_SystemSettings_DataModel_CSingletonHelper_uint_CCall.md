# SystemSettings::DataModel::CSingletonHelper<uint>::Unregister(SystemSettings::DataModel::CSingletonHelper<uint>::CCallback *)

- ea: `0x180029ca0`
- end: `0x180029e62`
- name: `?Unregister@?$CSingletonHelper@I@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `450`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001a5b0`
- `0x18002cd2c`
- `0x18002f620`

## callees

- `0x18000b508`
- `0x180012c58`
- `0x18001314c`
- `0x18001760c`
- `0x180024214`
- `0x180026bf0`
- `0x1800271c0`
- `0x180029ca0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029dbd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029dbd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180029e41`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180029e41`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029d0f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029d5b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029d0f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029d5b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180029de1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180029de1`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180029cee`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180029cee`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<unsigned int>::Unregister(
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
  if ( !byte_1800658EA && hEvent )
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
  EnterCriticalSection(&stru_180065920);
  v15 = &stru_180065920;
  SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::CCallback::LockHandleNotificationExclusive(
    v3,
    &lpdwindex);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>(
    qword_1800658A8,
    (unsigned __int8 *)&v14);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lpdwindex);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v15);
  v4 = 0;
  EnterCriticalSection(&CriticalSection);
  lpdwindex = (RTL_SRWLOCK *)&CriticalSection;
  LOBYTE(v5) = 3;
  LOBYTE(v6) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v6,
    v5);
  if ( !dword_180065918 && !qword_1800658B8 && !byte_180065950 && dword_180065960 >= 0 )
  {
    v4 = 1;
    byte_180065950 = 1;
    EventW = qword_180065948;
    if ( qword_180065948
      || (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&qword_180065948),
          (qword_180065948 = EventW) != 0) )
    {
      ResetEvent(EventW);
    }
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&lpdwindex);
  if ( v4 )
  {
    try
    {
      (*(void (__fastcall **)(__int64 *))(SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverMultipleBatterySingleton
                                        + 16))(&SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverMultipleBatterySingleton);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x545,
        (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingHandlersBaseCore.h",
        v10);
    }
    byte_1800658EA = 0;
    dword_180065960 = -2147418113;
    SystemSettings::DataModel::AutoMTAUsageCookie::Release((SystemSettings::DataModel::AutoMTAUsageCookie *)&qword_180065958);
    byte_180065950 = 0;
    if ( qword_180065948 )
      SetEvent(qword_180065948);
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
0x180029ca0  mov     rax, rsp
0x180029ca3  mov     [rax+20h], rsi
0x180029ca7  mov     [rax+10h], rdx
0x180029cab  mov     [rax+8], rcx
0x180029caf  push    rdi
0x180029cb0  sub     rsp, 30h
0x180029cb4  mov     rdi, rdx
0x180029cb7  cmp     cs:byte_1800658EA, 0
0x180029cbe  jnz     short loc_180029CF4
0x180029cc0  cmp     cs:hEvent, 0
0x180029cc8  jz      short loc_180029CF4
0x180029cca  mov     dword ptr [rax+8], 0
0x180029cd1  lea     rax, [rax+8]
0x180029cd5  mov     [rsp+38h+lpdwindex], rax; lpdwindex
0x180029cda  lea     r9, hEvent; pHandles
0x180029ce1  mov     r8d, 1; cHandles
0x180029ce7  or      edx, 0FFFFFFFFh; dwTimeout
0x180029cea  lea     ecx, [r8+7]; dwFlags
0x180029cee  call    cs:__imp_CoWaitForMultipleHandles
0x180029cf4  mov     r8b, 3
0x180029cf7  mov     dl, 1
0x180029cf9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180029d00  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180029d05  lea     rsi, stru_180065920
0x180029d0c  mov     rcx, rsi; lpCriticalSection
0x180029d0f  call    cs:__imp_EnterCriticalSection
0x180029d15  mov     [rsp+38h+arg_10], rsi
0x180029d1a  lea     rdx, [rsp+38h+arg_0]
0x180029d1f  mov     rcx, rdi
0x180029d22  call    ?LockHandleNotificationExclusive@CCallback@?$CSingletonHelper@UPowerAdapter@1Internal@Windows@winrt@@@DataModel@SystemSettings@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::CCallback::LockHandleNotificationExclusive(void)
0x180029d27  nop
0x180029d28  lea     rdx, [rsp+38h+arg_8]
0x180029d2d  lea     rcx, qword_1800658A8
0x180029d34  call    ??$_Erase@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@6@$0A@@std@@@std@@AEAA_KAEBQEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>(SystemSettings::DataModel::CSingletonHelper<int>::CCallback * const &)
0x180029d39  nop
0x180029d3a  lea     rcx, [rsp+38h+arg_0]
0x180029d3f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180029d44  lea     rcx, [rsp+38h+arg_10]; this
0x180029d49  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180029d4e  xor     sil, sil
0x180029d51  lea     rdi, CriticalSection
0x180029d58  mov     rcx, rdi; lpCriticalSection
0x180029d5b  call    cs:__imp_EnterCriticalSection
0x180029d61  mov     [rsp+38h+arg_0], rdi
0x180029d66  mov     r8b, 3
0x180029d69  mov     dl, 1
0x180029d6b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180029d72  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180029d77  cmp     cs:dword_180065918, 0
0x180029d7e  jnz     short loc_180029DE8
0x180029d80  cmp     cs:qword_1800658B8, 0
0x180029d88  jnz     short loc_180029DE8
0x180029d8a  cmp     cs:byte_180065950, sil
0x180029d91  jnz     short loc_180029DE8
0x180029d93  cmp     cs:dword_180065960, 0
0x180029d9a  jl      short loc_180029DE8
0x180029d9c  mov     sil, 1
0x180029d9f  mov     cs:byte_180065950, sil
0x180029da6  mov     rdi, cs:qword_180065948
0x180029dad  test    rdi, rdi
0x180029db0  jnz     short loc_180029DDE
0x180029db2  xor     r9d, r9d; lpName
0x180029db5  xor     r8d, r8d; bInitialState
0x180029db8  lea     edx, [rdi+1]; bManualReset
0x180029dbb  xor     ecx, ecx; lpEventAttributes
0x180029dbd  call    cs:__imp_CreateEventW
0x180029dc3  mov     rdi, rax
0x180029dc6  lea     rcx, qword_180065948
0x180029dcd  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180029dd2  mov     cs:qword_180065948, rdi
0x180029dd9  test    rdi, rdi
0x180029ddc  jz      short loc_180029DE8
0x180029dde  mov     rcx, rdi; hEvent
0x180029de1  call    cs:__imp_ResetEvent
0x180029de7  nop
0x180029de8  lea     rcx, [rsp+38h+arg_0]; this
0x180029ded  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180029df2  test    sil, sil
0x180029df5  jz      short loc_180029E47
0x180029df7  mov     rax, cs:?g_CBatterySaverMultipleBatterySingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCBatterySaverMultipleBatterySingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverMultipleBatterySingleton SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverMultipleBatterySingleton
0x180029dfe  lea     rcx, ?g_CBatterySaverMultipleBatterySingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCBatterySaverMultipleBatterySingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverMultipleBatterySingleton SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverMultipleBatterySingleton
0x180029e05  mov     rax, [rax+10h]
0x180029e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e0e  nop
0x180029e0f  jmp     short $+2
0x180029e11  mov     cs:byte_1800658EA, 0
0x180029e18  mov     cs:dword_180065960, 8000FFFFh
0x180029e22  lea     rcx, qword_180065958; this
0x180029e29  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x180029e2e  mov     cs:byte_180065950, 0
0x180029e35  mov     rcx, cs:qword_180065948; hEvent
0x180029e3c  test    rcx, rcx
0x180029e3f  jz      short loc_180029E47
0x180029e41  call    cs:__imp_SetEvent
0x180029e47  mov     r8b, 3
0x180029e4a  mov     dl, 1
0x180029e4c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180029e53  mov     rsi, [rsp+38h+arg_18]
0x180029e58  add     rsp, 30h
0x180029e5c  pop     rdi
0x180029e5d  jmp     ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
```
