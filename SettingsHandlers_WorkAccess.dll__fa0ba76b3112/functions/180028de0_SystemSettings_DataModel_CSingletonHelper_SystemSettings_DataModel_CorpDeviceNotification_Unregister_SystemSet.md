# SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::Unregister(SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *)

- ea: `0x180028de0`
- end: `0x180028fd0`
- name: `?Unregister@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `496`
- prototype: ``
- caller_count: `11`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180023888`
- `0x18002ee98`
- `0x18002f0e4`
- `0x18002f1a8`
- `0x18002f230`
- `0x18002f304`
- `0x18002f38c`
- `0x18002f540`
- `0x18002f614`
- `0x18003b480`
- `0x18003b52c`

## callees

- `0x180005544`
- `0x180014d48`
- `0x180019b9c`
- `0x18001d8ac`
- `0x18001ed10`
- `0x18001ed44`
- `0x18001f070`
- `0x180028de0`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028e5a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028eb2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028e5a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028eb2`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180028f3f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180028f3f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028f1d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028f1d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180028fa7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180028fa7`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180028e33`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180028e33`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::Unregister(
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
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    a2,
    a3);
  EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 160));
  v22 = v4 + 160;
  SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::TokenBrokerUpdate>::CCallback::LockHandleNotificationExclusive(
    v3,
    &lpdwindex);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>(
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
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
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
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
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
           `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
           v10,
           v11);
}

```

## disassembly

```asm
0x180028de0  mov     rax, rsp
0x180028de3  mov     [rax+10h], rdx
0x180028de7  mov     [rax+8], rcx
0x180028deb  push    rbx
0x180028dec  push    rdi
0x180028ded  push    r12
0x180028def  push    r14
0x180028df1  push    r15
0x180028df3  sub     rsp, 40h
0x180028df7  mov     r15, rdx
0x180028dfa  mov     rdi, rcx
0x180028dfd  lea     r14, [rcx+6Ah]
0x180028e01  mov     [rsp+68h+var_38], r14
0x180028e06  cmp     byte ptr [r14], 0
0x180028e0a  jnz     short loc_180028E3F
0x180028e0c  lea     r9, [rcx+10h]; pHandles
0x180028e10  cmp     qword ptr [r9], 0
0x180028e14  jz      short loc_180028E3F
0x180028e16  mov     dword ptr [rax+18h], 0
0x180028e1d  lea     rax, [rax+18h]
0x180028e21  mov     [rsp+68h+lpdwindex], rax; lpdwindex
0x180028e26  mov     r8d, 1; cHandles
0x180028e2c  or      edx, 0FFFFFFFFh; dwTimeout
0x180028e2f  lea     ecx, [r8+7]; dwFlags
0x180028e33  call    cs:__imp_CoWaitForMultipleHandles
0x180028e3a  nop     dword ptr [rax+rax+00h]
0x180028e3f  mov     r8b, 3
0x180028e42  mov     dl, 1
0x180028e44  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180028e4b  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180028e50  lea     rbx, [rdi+0A0h]
0x180028e57  mov     rcx, rbx; lpCriticalSection
0x180028e5a  call    cs:__imp_EnterCriticalSection
0x180028e61  nop     dword ptr [rax+rax+00h]
0x180028e66  mov     [rsp+68h+arg_18], rbx
0x180028e6e  lea     rdx, [rsp+68h+arg_10]
0x180028e76  mov     rcx, r15
0x180028e79  call    ?LockHandleNotificationExclusive@CCallback@?$CSingletonHelper@W4TokenBrokerUpdate@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::TokenBrokerUpdate>::CCallback::LockHandleNotificationExclusive(void)
0x180028e7e  nop
0x180028e7f  lea     rcx, [rdi+28h]
0x180028e83  lea     rdx, [rsp+68h+arg_8]
0x180028e88  call    ??$_Erase@PEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@AEAA_KAEBQEAVCCallback@?$CSingletonHelper@W4MDMHTMLReportSettingPhase@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback *>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::CCallback * const &)
0x180028e8d  nop
0x180028e8e  lea     rcx, [rsp+68h+arg_10]
0x180028e96  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180028e9b  lea     rcx, [rsp+68h+arg_18]; this
0x180028ea3  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180028ea8  xor     r12b, r12b
0x180028eab  lea     rbx, [rdi+70h]
0x180028eaf  mov     rcx, rbx; lpCriticalSection
0x180028eb2  call    cs:__imp_EnterCriticalSection
0x180028eb9  nop     dword ptr [rax+rax+00h]
0x180028ebe  mov     [rsp+68h+arg_10], rbx
0x180028ec6  mov     r8b, 3
0x180028ec9  mov     dl, 1
0x180028ecb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180028ed2  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180028ed7  cmp     dword ptr [rdi+98h], 0
0x180028ede  jnz     short loc_180028F4C
0x180028ee0  cmp     qword ptr [rdi+38h], 0
0x180028ee5  jnz     short loc_180028F4C
0x180028ee7  cmp     [rdi+0D0h], r12b
0x180028eee  jnz     short loc_180028F4C
0x180028ef0  cmp     dword ptr [rdi+0E0h], 0
0x180028ef7  jl      short loc_180028F4C
0x180028ef9  mov     r12b, 1
0x180028efc  mov     [rdi+0D0h], r12b
0x180028f03  lea     r15, [rdi+0C8h]
0x180028f0a  mov     rbx, [r15]
0x180028f0d  test    rbx, rbx
0x180028f10  jnz     short loc_180028F3C
0x180028f12  xor     r9d, r9d; lpName
0x180028f15  xor     r8d, r8d; bInitialState
0x180028f18  lea     edx, [rbx+1]; bManualReset
0x180028f1b  xor     ecx, ecx; lpEventAttributes
0x180028f1d  call    cs:__imp_CreateEventW
0x180028f24  nop     dword ptr [rax+rax+00h]
0x180028f29  mov     rbx, rax
0x180028f2c  mov     rcx, r15
0x180028f2f  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180028f34  mov     [r15], rbx
0x180028f37  test    rbx, rbx
0x180028f3a  jz      short loc_180028F4C
0x180028f3c  mov     rcx, rbx; hEvent
0x180028f3f  call    cs:__imp_ResetEvent
0x180028f46  nop     dword ptr [rax+rax+00h]
0x180028f4b  nop
0x180028f4c  lea     rcx, [rsp+68h+arg_10]; this
0x180028f54  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180028f59  test    r12b, r12b
0x180028f5c  jz      short loc_180028FB3
0x180028f5e  mov     rax, [rdi]
0x180028f61  mov     rcx, rdi
0x180028f64  mov     rax, [rax+10h]
0x180028f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f6d  nop
0x180028f6e  jmp     short loc_180028F7A
0x180028f70  mov     rdi, [rsp+68h+arg_0]
0x180028f75  mov     r14, [rsp+68h+var_38]
0x180028f7a  mov     byte ptr [r14], 0
0x180028f7e  mov     dword ptr [rdi+0E0h], 8000FFFFh
0x180028f88  lea     rcx, [rdi+0D8h]; this
0x180028f8f  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x180028f94  mov     byte ptr [rdi+0D0h], 0
0x180028f9b  mov     rcx, [rdi+0C8h]; hEvent
0x180028fa2  test    rcx, rcx
0x180028fa5  jz      short loc_180028FB3
0x180028fa7  call    cs:__imp_SetEvent
0x180028fae  nop     dword ptr [rax+rax+00h]
0x180028fb3  mov     r8b, 3
0x180028fb6  mov     dl, 1
0x180028fb8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180028fbf  add     rsp, 40h
0x180028fc3  pop     r15
0x180028fc5  pop     r14
0x180028fc7  pop     r12
0x180028fc9  pop     rdi
0x180028fca  pop     rbx
0x180028fcb  jmp     ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
```
