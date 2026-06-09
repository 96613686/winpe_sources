# SystemSettings::DataModel::CSingletonHelper<ulong>::Unregister(SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *)

- ea: `0x18001f84c`
- end: `0x18001fa30`
- name: `?Unregister@?$CSingletonHelper@K@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `484`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001ad58`
- `0x18003b480`

## callees

- `0x180005544`
- `0x180014d48`
- `0x180019b9c`
- `0x18001d8ac`
- `0x18001ed10`
- `0x18001ed44`
- `0x18001f070`
- `0x18001f84c`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f8c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f913`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f8c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f913`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001f9a5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001f9a5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f97b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f97b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001fa09`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001fa09`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001f89a`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001f89a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<unsigned long>::Unregister(
        struct _RTL_CRITICAL_SECTION *a1,
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
  struct _RTL_CRITICAL_SECTION *lpdwindex; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF
  struct _RTL_CRITICAL_SECTION *v15; // [rsp+50h] [rbp+18h] BYREF

  v14 = a2;
  lpdwindex = a1;
  v3 = a2;
  if ( !byte_18006C17A && hEvent )
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
  EnterCriticalSection(&stru_18006C1B0);
  v15 = &stru_18006C1B0;
  SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::TokenBrokerUpdate>::CCallback::LockHandleNotificationExclusive(
    v3,
    &lpdwindex);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>(
    &qword_18006C138,
    &v14);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lpdwindex);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v15);
  v4 = 0;
  EnterCriticalSection(&stru_18006C180);
  lpdwindex = &stru_18006C180;
  LOBYTE(v5) = 3;
  LOBYTE(v6) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v6,
    v5);
  if ( !dword_18006C1A8 && !qword_18006C148 && !byte_18006C1E0 && dword_18006C1F0 >= 0 )
  {
    v4 = 1;
    byte_18006C1E0 = 1;
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
      (*(void (__fastcall **)(void *))(SystemSettings::WorkAccess::g_WorkAccessSingleton + 16LL))(&SystemSettings::WorkAccess::g_WorkAccessSingleton);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x545,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
        v10);
    }
    byte_18006C17A = 0;
    dword_18006C1F0 = -2147418113;
    SystemSettings::DataModel::AutoMTAUsageCookie::Release((SystemSettings::DataModel::AutoMTAUsageCookie *)&qword_18006C1E8);
    byte_18006C1E0 = 0;
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
0x18001f84c  mov     rax, rsp
0x18001f84f  mov     [rax+20h], rsi
0x18001f853  mov     [rax+10h], rdx
0x18001f857  mov     [rax+8], rcx
0x18001f85b  push    rdi
0x18001f85c  sub     rsp, 30h
0x18001f860  mov     rdi, rdx
0x18001f863  cmp     cs:byte_18006C17A, 0
0x18001f86a  jnz     short loc_18001F8A6
0x18001f86c  cmp     cs:hEvent, 0
0x18001f874  jz      short loc_18001F8A6
0x18001f876  mov     dword ptr [rax+8], 0
0x18001f87d  lea     rax, [rax+8]
0x18001f881  mov     [rsp+38h+lpdwindex], rax; lpdwindex
0x18001f886  lea     r9, hEvent; pHandles
0x18001f88d  mov     r8d, 1; cHandles
0x18001f893  or      edx, 0FFFFFFFFh; dwTimeout
0x18001f896  lea     ecx, [r8+7]; dwFlags
0x18001f89a  call    cs:__imp_CoWaitForMultipleHandles
0x18001f8a1  nop     dword ptr [rax+rax+00h]
0x18001f8a6  mov     r8b, 3
0x18001f8a9  mov     dl, 1
0x18001f8ab  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001f8b2  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001f8b7  lea     rsi, stru_18006C1B0
0x18001f8be  mov     rcx, rsi; lpCriticalSection
0x18001f8c1  call    cs:__imp_EnterCriticalSection
0x18001f8c8  nop     dword ptr [rax+rax+00h]
0x18001f8cd  mov     [rsp+38h+arg_10], rsi
0x18001f8d2  lea     rdx, [rsp+38h+arg_0]
0x18001f8d7  mov     rcx, rdi
0x18001f8da  call    ?LockHandleNotificationExclusive@CCallback@?$CSingletonHelper@W4TokenBrokerUpdate@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::TokenBrokerUpdate>::CCallback::LockHandleNotificationExclusive(void)
0x18001f8df  nop
0x18001f8e0  lea     rdx, [rsp+38h+arg_8]
0x18001f8e5  lea     rcx, qword_18006C138
0x18001f8ec  call    ??$_Erase@PEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@AEAA_KAEBQEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback * const &)
0x18001f8f1  nop
0x18001f8f2  lea     rcx, [rsp+38h+arg_0]
0x18001f8f7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001f8fc  lea     rcx, [rsp+38h+arg_10]; this
0x18001f901  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18001f906  xor     sil, sil
0x18001f909  lea     rdi, stru_18006C180
0x18001f910  mov     rcx, rdi; lpCriticalSection
0x18001f913  call    cs:__imp_EnterCriticalSection
0x18001f91a  nop     dword ptr [rax+rax+00h]
0x18001f91f  mov     [rsp+38h+arg_0], rdi
0x18001f924  mov     r8b, 3
0x18001f927  mov     dl, 1
0x18001f929  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001f930  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001f935  cmp     cs:dword_18006C1A8, 0
0x18001f93c  jnz     short loc_18001F9B2
0x18001f93e  cmp     cs:qword_18006C148, 0
0x18001f946  jnz     short loc_18001F9B2
0x18001f948  cmp     cs:byte_18006C1E0, sil
0x18001f94f  jnz     short loc_18001F9B2
0x18001f951  cmp     cs:dword_18006C1F0, 0
0x18001f958  jl      short loc_18001F9B2
0x18001f95a  mov     sil, 1
0x18001f95d  mov     cs:byte_18006C1E0, sil
0x18001f964  mov     rdi, cs:pHandles
0x18001f96b  test    rdi, rdi
0x18001f96e  jnz     short loc_18001F9A2
0x18001f970  xor     r9d, r9d; lpName
0x18001f973  xor     r8d, r8d; bInitialState
0x18001f976  lea     edx, [rdi+1]; bManualReset
0x18001f979  xor     ecx, ecx; lpEventAttributes
0x18001f97b  call    cs:__imp_CreateEventW
0x18001f982  nop     dword ptr [rax+rax+00h]
0x18001f987  mov     rdi, rax
0x18001f98a  lea     rcx, pHandles
0x18001f991  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18001f996  mov     cs:pHandles, rdi
0x18001f99d  test    rdi, rdi
0x18001f9a0  jz      short loc_18001F9B2
0x18001f9a2  mov     rcx, rdi; hEvent
0x18001f9a5  call    cs:__imp_ResetEvent
0x18001f9ac  nop     dword ptr [rax+rax+00h]
0x18001f9b1  nop
0x18001f9b2  lea     rcx, [rsp+38h+arg_0]; this
0x18001f9b7  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18001f9bc  test    sil, sil
0x18001f9bf  jz      short loc_18001FA15
0x18001f9c1  mov     rax, cs:?g_WorkAccessSingleton@WorkAccess@SystemSettings@@3VCWorkAccessSingleton@12@A; SystemSettings::WorkAccess::CWorkAccessSingleton SystemSettings::WorkAccess::g_WorkAccessSingleton
0x18001f9c8  lea     rcx, ?g_WorkAccessSingleton@WorkAccess@SystemSettings@@3VCWorkAccessSingleton@12@A; SystemSettings::WorkAccess::CWorkAccessSingleton SystemSettings::WorkAccess::g_WorkAccessSingleton
0x18001f9cf  mov     rax, [rax+10h]
0x18001f9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9d8  nop
0x18001f9d9  mov     cs:byte_18006C17A, 0
0x18001f9e0  mov     cs:dword_18006C1F0, 8000FFFFh
0x18001f9ea  lea     rcx, qword_18006C1E8; this
0x18001f9f1  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x18001f9f6  mov     cs:byte_18006C1E0, 0
0x18001f9fd  mov     rcx, cs:pHandles; hEvent
0x18001fa04  test    rcx, rcx
0x18001fa07  jz      short loc_18001FA15
0x18001fa09  call    cs:__imp_SetEvent
0x18001fa10  nop     dword ptr [rax+rax+00h]
0x18001fa15  mov     r8b, 3
0x18001fa18  mov     dl, 1
0x18001fa1a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001fa21  mov     rsi, [rsp+38h+arg_18]
0x18001fa26  add     rsp, 30h
0x18001fa2a  pop     rdi
0x18001fa2b  jmp     ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
```
