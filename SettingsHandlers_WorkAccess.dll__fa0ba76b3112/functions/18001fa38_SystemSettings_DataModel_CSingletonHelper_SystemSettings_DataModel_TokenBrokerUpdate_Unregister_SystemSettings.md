# SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::TokenBrokerUpdate>::Unregister(SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::TokenBrokerUpdate>::CCallback *)

- ea: `0x18001fa38`
- end: `0x18001fc1c`
- name: `?Unregister@?$CSingletonHelper@W4TokenBrokerUpdate@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `484`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001ad58`

## callees

- `0x180005544`
- `0x180014d48`
- `0x180019b9c`
- `0x18001d8ac`
- `0x18001ed10`
- `0x18001ed44`
- `0x18001f070`
- `0x18001fa38`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001faad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001faff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001faad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001faff`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001fb91`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001fb91`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001fb67`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001fb67`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001fbf5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001fbf5`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001fa86`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001fa86`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::TokenBrokerUpdate>::Unregister(
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
  struct _RTL_CRITICAL_SECTION *lpdwindex; // [rsp+40h] [rbp+8h] BYREF
  __int64 v12; // [rsp+48h] [rbp+10h] BYREF
  struct _RTL_CRITICAL_SECTION *v13; // [rsp+50h] [rbp+18h] BYREF

  v12 = a2;
  lpdwindex = a1;
  v3 = a2;
  if ( !byte_18006C01A && qword_18006BFC0 )
  {
    LODWORD(lpdwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &qword_18006BFC0, (LPDWORD)&lpdwindex);
  }
  LOBYTE(a3) = 3;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    a2,
    a3);
  EnterCriticalSection(&stru_18006C050);
  v13 = &stru_18006C050;
  SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::TokenBrokerUpdate>::CCallback::LockHandleNotificationExclusive(
    v3,
    &lpdwindex);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>(
    qword_18006BFD8,
    &v12);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lpdwindex);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v13);
  v4 = 0;
  EnterCriticalSection(&CriticalSection);
  lpdwindex = &CriticalSection;
  LOBYTE(v5) = 3;
  LOBYTE(v6) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v6,
    v5);
  if ( !dword_18006C048 && !qword_18006BFE8 && !byte_18006C080 && dword_18006C090 >= 0 )
  {
    v4 = 1;
    byte_18006C080 = 1;
    EventW = qword_18006C078;
    if ( qword_18006C078
      || (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&qword_18006C078),
          (qword_18006C078 = EventW) != 0) )
    {
      ResetEvent(EventW);
    }
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&lpdwindex);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64 *))(SystemSettings::DataModel::g_TokenBrokerSingleton + 16))(&SystemSettings::DataModel::g_TokenBrokerSingleton);
    byte_18006C01A = 0;
    dword_18006C090 = -2147418113;
    SystemSettings::DataModel::AutoMTAUsageCookie::Release((SystemSettings::DataModel::AutoMTAUsageCookie *)&qword_18006C088);
    byte_18006C080 = 0;
    if ( qword_18006C078 )
      SetEvent(qword_18006C078);
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
0x18001fa38  mov     rax, rsp
0x18001fa3b  mov     [rax+20h], rsi
0x18001fa3f  mov     [rax+10h], rdx
0x18001fa43  mov     [rax+8], rcx
0x18001fa47  push    rdi
0x18001fa48  sub     rsp, 30h
0x18001fa4c  mov     rdi, rdx
0x18001fa4f  cmp     cs:byte_18006C01A, 0
0x18001fa56  jnz     short loc_18001FA92
0x18001fa58  cmp     cs:qword_18006BFC0, 0
0x18001fa60  jz      short loc_18001FA92
0x18001fa62  mov     dword ptr [rax+8], 0
0x18001fa69  lea     rax, [rax+8]
0x18001fa6d  mov     [rsp+38h+lpdwindex], rax; lpdwindex
0x18001fa72  lea     r9, qword_18006BFC0; pHandles
0x18001fa79  mov     r8d, 1; cHandles
0x18001fa7f  or      edx, 0FFFFFFFFh; dwTimeout
0x18001fa82  lea     ecx, [r8+7]; dwFlags
0x18001fa86  call    cs:__imp_CoWaitForMultipleHandles
0x18001fa8d  nop     dword ptr [rax+rax+00h]
0x18001fa92  mov     r8b, 3
0x18001fa95  mov     dl, 1
0x18001fa97  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001fa9e  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001faa3  lea     rsi, stru_18006C050
0x18001faaa  mov     rcx, rsi; lpCriticalSection
0x18001faad  call    cs:__imp_EnterCriticalSection
0x18001fab4  nop     dword ptr [rax+rax+00h]
0x18001fab9  mov     [rsp+38h+arg_10], rsi
0x18001fabe  lea     rdx, [rsp+38h+arg_0]
0x18001fac3  mov     rcx, rdi
0x18001fac6  call    ?LockHandleNotificationExclusive@CCallback@?$CSingletonHelper@W4TokenBrokerUpdate@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::TokenBrokerUpdate>::CCallback::LockHandleNotificationExclusive(void)
0x18001facb  nop
0x18001facc  lea     rdx, [rsp+38h+arg_8]
0x18001fad1  lea     rcx, qword_18006BFD8
0x18001fad8  call    ??$_Erase@PEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@AEAA_KAEBQEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback * const &)
0x18001fadd  nop
0x18001fade  lea     rcx, [rsp+38h+arg_0]
0x18001fae3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001fae8  lea     rcx, [rsp+38h+arg_10]; this
0x18001faed  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18001faf2  xor     sil, sil
0x18001faf5  lea     rdi, CriticalSection
0x18001fafc  mov     rcx, rdi; lpCriticalSection
0x18001faff  call    cs:__imp_EnterCriticalSection
0x18001fb06  nop     dword ptr [rax+rax+00h]
0x18001fb0b  mov     [rsp+38h+arg_0], rdi
0x18001fb10  mov     r8b, 3
0x18001fb13  mov     dl, 1
0x18001fb15  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001fb1c  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001fb21  cmp     cs:dword_18006C048, 0
0x18001fb28  jnz     short loc_18001FB9E
0x18001fb2a  cmp     cs:qword_18006BFE8, 0
0x18001fb32  jnz     short loc_18001FB9E
0x18001fb34  cmp     cs:byte_18006C080, sil
0x18001fb3b  jnz     short loc_18001FB9E
0x18001fb3d  cmp     cs:dword_18006C090, 0
0x18001fb44  jl      short loc_18001FB9E
0x18001fb46  mov     sil, 1
0x18001fb49  mov     cs:byte_18006C080, sil
0x18001fb50  mov     rdi, cs:qword_18006C078
0x18001fb57  test    rdi, rdi
0x18001fb5a  jnz     short loc_18001FB8E
0x18001fb5c  xor     r9d, r9d; lpName
0x18001fb5f  xor     r8d, r8d; bInitialState
0x18001fb62  lea     edx, [rdi+1]; bManualReset
0x18001fb65  xor     ecx, ecx; lpEventAttributes
0x18001fb67  call    cs:__imp_CreateEventW
0x18001fb6e  nop     dword ptr [rax+rax+00h]
0x18001fb73  mov     rdi, rax
0x18001fb76  lea     rcx, qword_18006C078
0x18001fb7d  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18001fb82  mov     cs:qword_18006C078, rdi
0x18001fb89  test    rdi, rdi
0x18001fb8c  jz      short loc_18001FB9E
0x18001fb8e  mov     rcx, rdi; hEvent
0x18001fb91  call    cs:__imp_ResetEvent
0x18001fb98  nop     dword ptr [rax+rax+00h]
0x18001fb9d  nop
0x18001fb9e  lea     rcx, [rsp+38h+arg_0]; this
0x18001fba3  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18001fba8  test    sil, sil
0x18001fbab  jz      short loc_18001FC01
0x18001fbad  mov     rax, cs:?g_TokenBrokerSingleton@DataModel@SystemSettings@@3VTokenBrokerSingleton@12@A; SystemSettings::DataModel::TokenBrokerSingleton SystemSettings::DataModel::g_TokenBrokerSingleton
0x18001fbb4  lea     rcx, ?g_TokenBrokerSingleton@DataModel@SystemSettings@@3VTokenBrokerSingleton@12@A; SystemSettings::DataModel::TokenBrokerSingleton SystemSettings::DataModel::g_TokenBrokerSingleton
0x18001fbbb  mov     rax, [rax+10h]
0x18001fbbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbc4  nop
0x18001fbc5  mov     cs:byte_18006C01A, 0
0x18001fbcc  mov     cs:dword_18006C090, 8000FFFFh
0x18001fbd6  lea     rcx, qword_18006C088; this
0x18001fbdd  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x18001fbe2  mov     cs:byte_18006C080, 0
0x18001fbe9  mov     rcx, cs:qword_18006C078; hEvent
0x18001fbf0  test    rcx, rcx
0x18001fbf3  jz      short loc_18001FC01
0x18001fbf5  call    cs:__imp_SetEvent
0x18001fbfc  nop     dword ptr [rax+rax+00h]
0x18001fc01  mov     r8b, 3
0x18001fc04  mov     dl, 1
0x18001fc06  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001fc0d  mov     rsi, [rsp+38h+arg_18]
0x18001fc12  add     rsp, 30h
0x18001fc16  pop     rdi
0x18001fc17  jmp     ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
```
