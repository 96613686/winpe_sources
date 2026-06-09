# SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::Unregister(SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *)

- ea: `0x18001e5bc`
- end: `0x18001e7a0`
- name: `?Unregister@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `484`
- prototype: ``
- caller_count: `9`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180010b5c`
- `0x180010c10`
- `0x180010d98`
- `0x180010e30`
- `0x180010eb0`
- `0x180010f64`
- `0x180010ff0`
- `0x18001107c`
- `0x1800110fc`

## callees

- `0x18000468c`
- `0x180019c10`
- `0x18001a2f0`
- `0x18001b330`
- `0x18001b9a0`
- `0x18001c3f0`
- `0x18001e5bc`
- `0x180020794`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001e779`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001e779`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001e715`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001e715`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001e6eb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001e6eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e631`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e683`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e631`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e683`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001e60a`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001e60a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::Unregister(
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
  if ( !byte_18003EE9A && hEvent )
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
  EnterCriticalSection(&stru_18003EED0);
  v15 = &stru_18003EED0;
  SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback::LockHandleNotificationExclusive(
    v3,
    &lpdwindex);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>,0>>::erase(
    &qword_18003EE58,
    &v14);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lpdwindex);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v15);
  v4 = 0;
  EnterCriticalSection(&CriticalSection);
  lpdwindex = &CriticalSection;
  LOBYTE(v5) = 3;
  LOBYTE(v6) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v6,
    v5);
  if ( !dword_18003EEC8 && !qword_18003EE60 && !byte_18003EF00 && dword_18003EF10 >= 0 )
  {
    v4 = 1;
    byte_18003EF00 = 1;
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
      (*(void (__fastcall **)(__int64 *))(g_CProvisioningSingleton + 16))(&g_CProvisioningSingleton);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x545,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
        v10);
    }
    byte_18003EE9A = 0;
    dword_18003EF10 = -2147418113;
    SystemSettings::DataModel::AutoMTAUsageCookie::Release((SystemSettings::DataModel::AutoMTAUsageCookie *)&qword_18003EF08);
    byte_18003EF00 = 0;
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
0x18001e5bc  mov     rax, rsp
0x18001e5bf  mov     [rax+20h], rsi
0x18001e5c3  mov     [rax+10h], rdx
0x18001e5c7  mov     [rax+8], rcx
0x18001e5cb  push    rdi
0x18001e5cc  sub     rsp, 30h
0x18001e5d0  mov     rdi, rdx
0x18001e5d3  cmp     cs:byte_18003EE9A, 0
0x18001e5da  jnz     short loc_18001E616
0x18001e5dc  cmp     cs:hEvent, 0
0x18001e5e4  jz      short loc_18001E616
0x18001e5e6  mov     dword ptr [rax+8], 0
0x18001e5ed  lea     rax, [rax+8]
0x18001e5f1  mov     [rsp+38h+lpdwindex], rax; lpdwindex
0x18001e5f6  lea     r9, hEvent; pHandles
0x18001e5fd  mov     r8d, 1; cHandles
0x18001e603  or      edx, 0FFFFFFFFh; dwTimeout
0x18001e606  lea     ecx, [r8+7]; dwFlags
0x18001e60a  call    cs:__imp_CoWaitForMultipleHandles
0x18001e611  nop     dword ptr [rax+rax+00h]
0x18001e616  mov     r8b, 3
0x18001e619  mov     dl, 1
0x18001e61b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001e622  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001e627  lea     rsi, stru_18003EED0
0x18001e62e  mov     rcx, rsi; lpCriticalSection
0x18001e631  call    cs:__imp_EnterCriticalSection
0x18001e638  nop     dword ptr [rax+rax+00h]
0x18001e63d  mov     [rsp+38h+arg_10], rsi
0x18001e642  lea     rdx, [rsp+38h+arg_0]
0x18001e647  mov     rcx, rdi
0x18001e64a  call    ?LockHandleNotificationExclusive@CCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback::LockHandleNotificationExclusive(void)
0x18001e64f  nop
0x18001e650  lea     rdx, [rsp+38h+arg_8]
0x18001e655  lea     rcx, qword_18003EE58
0x18001e65c  call    ?erase@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA_KAEBQEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>,0>>::erase(SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback * const &)
0x18001e661  nop
0x18001e662  lea     rcx, [rsp+38h+arg_0]
0x18001e667  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001e66c  lea     rcx, [rsp+38h+arg_10]; this
0x18001e671  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18001e676  xor     sil, sil
0x18001e679  lea     rdi, CriticalSection
0x18001e680  mov     rcx, rdi; lpCriticalSection
0x18001e683  call    cs:__imp_EnterCriticalSection
0x18001e68a  nop     dword ptr [rax+rax+00h]
0x18001e68f  mov     [rsp+38h+arg_0], rdi
0x18001e694  mov     r8b, 3
0x18001e697  mov     dl, 1
0x18001e699  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001e6a0  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001e6a5  cmp     cs:dword_18003EEC8, 0
0x18001e6ac  jnz     short loc_18001E722
0x18001e6ae  cmp     cs:qword_18003EE60, 0
0x18001e6b6  jnz     short loc_18001E722
0x18001e6b8  cmp     cs:byte_18003EF00, sil
0x18001e6bf  jnz     short loc_18001E722
0x18001e6c1  cmp     cs:dword_18003EF10, 0
0x18001e6c8  jl      short loc_18001E722
0x18001e6ca  mov     sil, 1
0x18001e6cd  mov     cs:byte_18003EF00, sil
0x18001e6d4  mov     rdi, cs:pHandles
0x18001e6db  test    rdi, rdi
0x18001e6de  jnz     short loc_18001E712
0x18001e6e0  xor     r9d, r9d; lpName
0x18001e6e3  xor     r8d, r8d; bInitialState
0x18001e6e6  lea     edx, [rdi+1]; bManualReset
0x18001e6e9  xor     ecx, ecx; lpEventAttributes
0x18001e6eb  call    cs:__imp_CreateEventW
0x18001e6f2  nop     dword ptr [rax+rax+00h]
0x18001e6f7  mov     rdi, rax
0x18001e6fa  lea     rcx, pHandles
0x18001e701  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18001e706  mov     cs:pHandles, rdi
0x18001e70d  test    rdi, rdi
0x18001e710  jz      short loc_18001E722
0x18001e712  mov     rcx, rdi; hEvent
0x18001e715  call    cs:__imp_ResetEvent
0x18001e71c  nop     dword ptr [rax+rax+00h]
0x18001e721  nop
0x18001e722  lea     rcx, [rsp+38h+arg_0]; this
0x18001e727  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18001e72c  test    sil, sil
0x18001e72f  jz      short loc_18001E785
0x18001e731  mov     rax, cs:?g_CProvisioningSingleton@@3VCProvisioningSingleton@@A; CProvisioningSingleton g_CProvisioningSingleton
0x18001e738  lea     rcx, ?g_CProvisioningSingleton@@3VCProvisioningSingleton@@A; CProvisioningSingleton g_CProvisioningSingleton
0x18001e73f  mov     rax, [rax+10h]
0x18001e743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e748  nop
0x18001e749  mov     cs:byte_18003EE9A, 0
0x18001e750  mov     cs:dword_18003EF10, 8000FFFFh
0x18001e75a  lea     rcx, qword_18003EF08; this
0x18001e761  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x18001e766  mov     cs:byte_18003EF00, 0
0x18001e76d  mov     rcx, cs:pHandles; hEvent
0x18001e774  test    rcx, rcx
0x18001e777  jz      short loc_18001E785
0x18001e779  call    cs:__imp_SetEvent
0x18001e780  nop     dword ptr [rax+rax+00h]
0x18001e785  mov     r8b, 3
0x18001e788  mov     dl, 1
0x18001e78a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001e791  mov     rsi, [rsp+38h+arg_18]
0x18001e796  add     rsp, 30h
0x18001e79a  pop     rdi
0x18001e79b  jmp     ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
```
