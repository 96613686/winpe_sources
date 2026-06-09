# SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::Unregister(SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback *)

- ea: `0x180010cdc`
- end: `0x180010ea8`
- name: `?Unregister@?$CSingletonHelper@W4BatteryGraphNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `460`
- prototype: ``
- caller_count: `16`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000df48`
- `0x180015d08`
- `0x180015ef0`
- `0x18001fbe0`
- `0x18001fc68`
- `0x18001fcf0`
- `0x180026760`
- `0x1800271a0`
- `0x1800277f4`
- `0x18002b5c4`
- `0x180031e80`
- `0x180034e80`
- `0x180037314`
- `0x1800376c0`
- `0x180049954`
- `0x180049a5c`

## callees

- `0x18000607c`
- `0x18000d51c`
- `0x18000fa10`
- `0x18000fab8`
- `0x180010030`
- `0x1800101f8`
- `0x1800103d0`
- `0x180010cdc`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010e85`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010e85`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010e07`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010e07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010d50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010da2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010d50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010da2`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180010e23`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180010e23`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180010d2f`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180010d2f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::Unregister(
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
  RTL_SRWLOCK *lpdwindex; // [rsp+80h] [rbp+18h] BYREF
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
  SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback::LockHandleNotificationExclusive(
    v3,
    &lpdwindex);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *>(
    (_QWORD *)(v4 + 40),
    (const unsigned __int8 *)&v20);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lpdwindex);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v22);
  v6 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 112));
  lpdwindex = (RTL_SRWLOCK *)(v4 + 112);
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
        (unsigned int)"OneCoreUap\\Internal\\Shell\\inc\\SettingHandlersBaseCore.h",
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
0x180010cdc  mov     rax, rsp
0x180010cdf  mov     [rax+10h], rdx
0x180010ce3  mov     [rax+8], rcx
0x180010ce7  push    rbx
0x180010ce8  push    rdi
0x180010ce9  push    r12
0x180010ceb  push    r14
0x180010ced  push    r15
0x180010cef  sub     rsp, 40h
0x180010cf3  mov     r15, rdx
0x180010cf6  mov     rdi, rcx
0x180010cf9  lea     r14, [rcx+6Ah]
0x180010cfd  mov     [rsp+68h+var_38], r14
0x180010d02  cmp     byte ptr [r14], 0
0x180010d06  jnz     short loc_180010D35
0x180010d08  lea     r9, [rcx+10h]; pHandles
0x180010d0c  cmp     qword ptr [r9], 0
0x180010d10  jz      short loc_180010D35
0x180010d12  mov     dword ptr [rax+18h], 0
0x180010d19  lea     rax, [rax+18h]
0x180010d1d  mov     [rsp+68h+lpdwindex], rax; lpdwindex
0x180010d22  mov     r8d, 1; cHandles
0x180010d28  or      edx, 0FFFFFFFFh; dwTimeout
0x180010d2b  lea     ecx, [r8+7]; dwFlags
0x180010d2f  call    cs:__imp_CoWaitForMultipleHandles
0x180010d35  mov     r8b, 3
0x180010d38  mov     dl, 1
0x180010d3a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180010d41  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180010d46  lea     rbx, [rdi+0A0h]
0x180010d4d  mov     rcx, rbx; lpCriticalSection
0x180010d50  call    cs:__imp_EnterCriticalSection
0x180010d56  mov     [rsp+68h+arg_18], rbx
0x180010d5e  lea     rdx, [rsp+68h+arg_10]
0x180010d66  mov     rcx, r15
0x180010d69  call    ?LockHandleNotificationExclusive@CCallback@?$CSingletonHelper@W4BatteryGraphNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryGraphNotification>::CCallback::LockHandleNotificationExclusive(void)
0x180010d6e  nop
0x180010d6f  lea     rcx, [rdi+28h]
0x180010d73  lea     rdx, [rsp+68h+arg_8]
0x180010d78  call    ??$_Erase@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@@6@$0A@@std@@@std@@AEAA_KAEBQEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *>(SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback * const &)
0x180010d7d  nop
0x180010d7e  lea     rcx, [rsp+68h+arg_10]
0x180010d86  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180010d8b  lea     rcx, [rsp+68h+arg_18]; this
0x180010d93  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180010d98  xor     r12b, r12b
0x180010d9b  lea     rbx, [rdi+70h]
0x180010d9f  mov     rcx, rbx; lpCriticalSection
0x180010da2  call    cs:__imp_EnterCriticalSection
0x180010da8  mov     [rsp+68h+arg_10], rbx
0x180010db0  mov     r8b, 3
0x180010db3  mov     dl, 1
0x180010db5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180010dbc  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180010dc1  cmp     dword ptr [rdi+98h], 0
0x180010dc8  jnz     short loc_180010E2A
0x180010dca  cmp     qword ptr [rdi+38h], 0
0x180010dcf  jnz     short loc_180010E2A
0x180010dd1  cmp     [rdi+0D0h], r12b
0x180010dd8  jnz     short loc_180010E2A
0x180010dda  cmp     dword ptr [rdi+0E0h], 0
0x180010de1  jl      short loc_180010E2A
0x180010de3  mov     r12b, 1
0x180010de6  mov     [rdi+0D0h], r12b
0x180010ded  lea     r15, [rdi+0C8h]
0x180010df4  mov     rbx, [r15]
0x180010df7  test    rbx, rbx
0x180010dfa  jnz     short loc_180010E20
0x180010dfc  xor     r9d, r9d; lpName
0x180010dff  xor     r8d, r8d; bInitialState
0x180010e02  lea     edx, [rbx+1]; bManualReset
0x180010e05  xor     ecx, ecx; lpEventAttributes
0x180010e07  call    cs:__imp_CreateEventW
0x180010e0d  mov     rbx, rax
0x180010e10  mov     rcx, r15
0x180010e13  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180010e18  mov     [r15], rbx
0x180010e1b  test    rbx, rbx
0x180010e1e  jz      short loc_180010E2A
0x180010e20  mov     rcx, rbx; hEvent
0x180010e23  call    cs:__imp_ResetEvent
0x180010e29  nop
0x180010e2a  lea     rcx, [rsp+68h+arg_10]; this
0x180010e32  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180010e37  test    r12b, r12b
0x180010e3a  jz      short loc_180010E8B
0x180010e3c  mov     rax, [rdi]
0x180010e3f  mov     rcx, rdi
0x180010e42  mov     rax, [rax+10h]
0x180010e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e4b  nop
0x180010e4c  jmp     short loc_180010E58
0x180010e4e  mov     rdi, [rsp+68h+arg_0]
0x180010e53  mov     r14, [rsp+68h+var_38]
0x180010e58  mov     byte ptr [r14], 0
0x180010e5c  mov     dword ptr [rdi+0E0h], 8000FFFFh
0x180010e66  lea     rcx, [rdi+0D8h]; this
0x180010e6d  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x180010e72  mov     byte ptr [rdi+0D0h], 0
0x180010e79  mov     rcx, [rdi+0C8h]; hEvent
0x180010e80  test    rcx, rcx
0x180010e83  jz      short loc_180010E8B
0x180010e85  call    cs:__imp_SetEvent
0x180010e8b  mov     r8b, 3
0x180010e8e  mov     dl, 1
0x180010e90  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180010e97  add     rsp, 40h
0x180010e9b  pop     r15
0x180010e9d  pop     r14
0x180010e9f  pop     r12
0x180010ea1  pop     rdi
0x180010ea2  pop     rbx
0x180010ea3  jmp     ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
```
