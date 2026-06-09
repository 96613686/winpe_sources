# SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::RecommendationNotificationBase> const &>::Unregister(SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::RecommendationNotificationBase> const &>::CCallback *)

- ea: `0x1800343ec`
- end: `0x1800345b8`
- name: `?Unregister@?$CSingletonHelper@AEBV?$shared_ptr@URecommendationNotificationBase@StorageSenseHandlers@SystemSettings@@@std@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `460`
- prototype: ``
- caller_count: `21`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800294e0`
- `0x180029644`
- `0x18003b964`
- `0x180061c1c`
- `0x180061cf0`
- `0x180061f24`
- `0x180061fdc`
- `0x180062078`
- `0x180071dac`
- `0x180071e70`
- `0x18007d5d4`
- `0x18007d668`
- `0x18007d718`
- `0x18007d858`
- `0x18007d94c`
- `0x180087b94`
- `0x180087cb8`
- `0x180087eec`
- `0x180094828`
- `0x1800bb4f8`
- `0x1800c8ee0`

## callees

- `0x18000ad80`
- `0x18001f53c`
- `0x180026d9c`
- `0x180031050`
- `0x1800323d0`
- `0x180032520`
- `0x180032cd0`
- `0x1800343ec`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034460`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800344b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034460`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800344b2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180034517`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180034517`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180034533`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180034533`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180034595`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180034595`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18003443f`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18003443f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::RecommendationNotificationBase> const &>::Unregister(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // r15
  __int64 v4; // rdi
  _BYTE *v5; // r14
  char v6; // r12
  __int64 v7; // r8
  __int64 v8; // rdx
  HANDLE EventW; // rbx
  __int64 v10; // rdx
  __int64 v11; // r8
  const char *v12; // r9
  void *v13; // rcx
  _BYTE *v15; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v20; // [rsp+78h] [rbp+10h] BYREF
  __int64 lpdwindex; // [rsp+80h] [rbp+18h] BYREF
  __int64 v22; // [rsp+88h] [rbp+20h] BYREF

  v20 = a2;
  v3 = a2;
  v4 = a1;
  v5 = (_BYTE *)(a1 + 106);
  v15 = (_BYTE *)(a1 + 106);
  if ( !*(_BYTE *)(a1 + 106) && *(_QWORD *)(a1 + 16) )
  {
    LODWORD(lpdwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, (LPHANDLE)(a1 + 16), (LPDWORD)&lpdwindex);
  }
  LOBYTE(a3) = 3;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    a2,
    a3);
  EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 160));
  v22 = v4 + 160;
  SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::CCallback::LockHandleNotificationExclusive(
    v3,
    &lpdwindex);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::CCallback *>(
    v4 + 40,
    &v20);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lpdwindex);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v22);
  v6 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 112));
  lpdwindex = v4 + 112;
  LOBYTE(v7) = 3;
  LOBYTE(v8) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v8,
    v7);
  if ( !*(_DWORD *)(v4 + 152) && !*(_QWORD *)(v4 + 56) && !*(_BYTE *)(v4 + 208) && *(int *)(v4 + 224) >= 0 )
  {
    v6 = 1;
    *(_BYTE *)(v4 + 208) = 1;
    EventW = *(HANDLE *)(v4 + 200);
    if ( EventW
      || (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(v4 + 200),
          (*(_QWORD *)(v4 + 200) = EventW) != 0) )
    {
      ResetEvent(EventW);
    }
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&lpdwindex);
  if ( v6 )
  {
    try
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x545,
        (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingHandlersBaseCore.h",
        v12);
      v4 = a1;
      v5 = v15;
    }
    *v5 = 0;
    *(_DWORD *)(v4 + 224) = -2147418113;
    SystemSettings::DataModel::AutoMTAUsageCookie::Release((SystemSettings::DataModel::AutoMTAUsageCookie *)(v4 + 216));
    *(_BYTE *)(v4 + 208) = 0;
    v13 = *(void **)(v4 + 200);
    if ( v13 )
      SetEvent(v13);
  }
  LOBYTE(v11) = 3;
  LOBYTE(v10) = 1;
  return wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
           &`wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
           v10,
           v11);
}

```

## disassembly

```asm
0x1800343ec  mov     rax, rsp
0x1800343ef  mov     [rax+10h], rdx
0x1800343f3  mov     [rax+8], rcx
0x1800343f7  push    rbx
0x1800343f8  push    rdi
0x1800343f9  push    r12
0x1800343fb  push    r14
0x1800343fd  push    r15
0x1800343ff  sub     rsp, 40h
0x180034403  mov     r15, rdx
0x180034406  mov     rdi, rcx
0x180034409  lea     r14, [rcx+6Ah]
0x18003440d  mov     [rsp+68h+var_38], r14
0x180034412  cmp     byte ptr [r14], 0
0x180034416  jnz     short loc_180034445
0x180034418  lea     r9, [rcx+10h]; pHandles
0x18003441c  cmp     qword ptr [r9], 0
0x180034420  jz      short loc_180034445
0x180034422  mov     dword ptr [rax+18h], 0
0x180034429  lea     rax, [rax+18h]
0x18003442d  mov     [rsp+68h+lpdwindex], rax; lpdwindex
0x180034432  mov     r8d, 1; cHandles
0x180034438  or      edx, 0FFFFFFFFh; dwTimeout
0x18003443b  lea     ecx, [r8+7]; dwFlags
0x18003443f  call    cs:__imp_CoWaitForMultipleHandles
0x180034445  mov     r8b, 3
0x180034448  mov     dl, 1
0x18003444a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180034451  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180034456  lea     rbx, [rdi+0A0h]
0x18003445d  mov     rcx, rbx; lpCriticalSection
0x180034460  call    cs:__imp_EnterCriticalSection
0x180034466  mov     [rsp+68h+arg_18], rbx
0x18003446e  lea     rdx, [rsp+68h+arg_10]
0x180034476  mov     rcx, r15
0x180034479  call    ?LockHandleNotificationExclusive@CCallback@?$CSingletonHelper@AEBV?$shared_ptr@UCleanupListHandlerEvent@StorageSenseHandlers@SystemSettings@@@std@@@DataModel@SystemSettings@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::CCallback::LockHandleNotificationExclusive(void)
0x18003447e  nop
0x18003447f  lea     rcx, [rdi+28h]
0x180034483  lea     rdx, [rsp+68h+arg_8]
0x180034488  call    ??$_Erase@PEAVCCallback@?$CSingletonHelper@PEAUAppListChangeNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@PEAUAppListChangeNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@PEAUAppListChangeNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@PEAUAppListChangeNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@PEAUAppListChangeNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@PEAUAppListChangeNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@AEAA_KAEBQEAVCCallback@?$CSingletonHelper@PEAUAppListChangeNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::CCallback *>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::CCallback * const &)
0x18003448d  nop
0x18003448e  lea     rcx, [rsp+68h+arg_10]
0x180034496  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003449b  lea     rcx, [rsp+68h+arg_18]; this
0x1800344a3  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800344a8  xor     r12b, r12b
0x1800344ab  lea     rbx, [rdi+70h]
0x1800344af  mov     rcx, rbx; lpCriticalSection
0x1800344b2  call    cs:__imp_EnterCriticalSection
0x1800344b8  mov     [rsp+68h+arg_10], rbx
0x1800344c0  mov     r8b, 3
0x1800344c3  mov     dl, 1
0x1800344c5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x1800344cc  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800344d1  cmp     dword ptr [rdi+98h], 0
0x1800344d8  jnz     short loc_18003453A
0x1800344da  cmp     qword ptr [rdi+38h], 0
0x1800344df  jnz     short loc_18003453A
0x1800344e1  cmp     [rdi+0D0h], r12b
0x1800344e8  jnz     short loc_18003453A
0x1800344ea  cmp     dword ptr [rdi+0E0h], 0
0x1800344f1  jl      short loc_18003453A
0x1800344f3  mov     r12b, 1
0x1800344f6  mov     [rdi+0D0h], r12b
0x1800344fd  lea     r15, [rdi+0C8h]
0x180034504  mov     rbx, [r15]
0x180034507  test    rbx, rbx
0x18003450a  jnz     short loc_180034530
0x18003450c  xor     r9d, r9d; lpName
0x18003450f  xor     r8d, r8d; bInitialState
0x180034512  lea     edx, [rbx+1]; bManualReset
0x180034515  xor     ecx, ecx; lpEventAttributes
0x180034517  call    cs:__imp_CreateEventW
0x18003451d  mov     rbx, rax
0x180034520  mov     rcx, r15
0x180034523  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180034528  mov     [r15], rbx
0x18003452b  test    rbx, rbx
0x18003452e  jz      short loc_18003453A
0x180034530  mov     rcx, rbx; hEvent
0x180034533  call    cs:__imp_ResetEvent
0x180034539  nop
0x18003453a  lea     rcx, [rsp+68h+arg_10]; this
0x180034542  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180034547  test    r12b, r12b
0x18003454a  jz      short loc_18003459B
0x18003454c  mov     rax, [rdi]
0x18003454f  mov     rcx, rdi
0x180034552  mov     rax, [rax+10h]
0x180034556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003455b  nop
0x18003455c  jmp     short loc_180034568
0x18003455e  mov     rdi, [rsp+68h+arg_0]
0x180034563  mov     r14, [rsp+68h+var_38]
0x180034568  mov     byte ptr [r14], 0
0x18003456c  mov     dword ptr [rdi+0E0h], 8000FFFFh
0x180034576  lea     rcx, [rdi+0D8h]; this
0x18003457d  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x180034582  mov     byte ptr [rdi+0D0h], 0
0x180034589  mov     rcx, [rdi+0C8h]; hEvent
0x180034590  test    rcx, rcx
0x180034593  jz      short loc_18003459B
0x180034595  call    cs:__imp_SetEvent
0x18003459b  mov     r8b, 3
0x18003459e  mov     dl, 1
0x1800345a0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x1800345a7  add     rsp, 40h
0x1800345ab  pop     r15
0x1800345ad  pop     r14
0x1800345af  pop     r12
0x1800345b1  pop     rdi
0x1800345b2  pop     rbx
0x1800345b3  jmp     ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
```
