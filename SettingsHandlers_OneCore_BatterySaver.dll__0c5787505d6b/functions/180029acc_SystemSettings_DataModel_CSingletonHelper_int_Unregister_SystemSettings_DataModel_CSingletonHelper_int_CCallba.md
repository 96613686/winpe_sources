# SystemSettings::DataModel::CSingletonHelper<int>::Unregister(SystemSettings::DataModel::CSingletonHelper<int>::CCallback *)

- ea: `0x180029acc`
- end: `0x180029c98`
- name: `?Unregister@?$CSingletonHelper@H@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `460`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001a528`
- `0x1800345d8`
- `0x1800346b4`
- `0x1800366a0`
- `0x180036700`
- `0x18003d000`
- `0x18003dea0`
- `0x1800452dc`

## callees

- `0x18000b508`
- `0x180012c58`
- `0x18001314c`
- `0x18001760c`
- `0x180024214`
- `0x180026bf0`
- `0x1800271c0`
- `0x180029acc`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029bf7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029bf7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180029c75`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180029c75`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029b40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029b92`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029b40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029b92`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180029c13`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180029c13`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180029b1f`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180029b1f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<int>::Unregister(__int64 a1, __int64 a2, __int64 a3)
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
  SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::CCallback::LockHandleNotificationExclusive(
    v3,
    &lpdwindex);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>(
    (_QWORD *)(v4 + 40),
    (unsigned __int8 *)&v20);
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
           `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
           v10,
           v11);
}

```

## disassembly

```asm
0x180029acc  mov     rax, rsp
0x180029acf  mov     [rax+10h], rdx
0x180029ad3  mov     [rax+8], rcx
0x180029ad7  push    rbx
0x180029ad8  push    rdi
0x180029ad9  push    r12
0x180029adb  push    r14
0x180029add  push    r15
0x180029adf  sub     rsp, 40h
0x180029ae3  mov     r15, rdx
0x180029ae6  mov     rdi, rcx
0x180029ae9  lea     r14, [rcx+6Ah]
0x180029aed  mov     [rsp+68h+var_38], r14
0x180029af2  cmp     byte ptr [r14], 0
0x180029af6  jnz     short loc_180029B25
0x180029af8  lea     r9, [rcx+10h]; pHandles
0x180029afc  cmp     qword ptr [r9], 0
0x180029b00  jz      short loc_180029B25
0x180029b02  mov     dword ptr [rax+18h], 0
0x180029b09  lea     rax, [rax+18h]
0x180029b0d  mov     [rsp+68h+lpdwindex], rax; lpdwindex
0x180029b12  mov     r8d, 1; cHandles
0x180029b18  or      edx, 0FFFFFFFFh; dwTimeout
0x180029b1b  lea     ecx, [r8+7]; dwFlags
0x180029b1f  call    cs:__imp_CoWaitForMultipleHandles
0x180029b25  mov     r8b, 3
0x180029b28  mov     dl, 1
0x180029b2a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180029b31  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180029b36  lea     rbx, [rdi+0A0h]
0x180029b3d  mov     rcx, rbx; lpCriticalSection
0x180029b40  call    cs:__imp_EnterCriticalSection
0x180029b46  mov     [rsp+68h+arg_18], rbx
0x180029b4e  lea     rdx, [rsp+68h+arg_10]
0x180029b56  mov     rcx, r15
0x180029b59  call    ?LockHandleNotificationExclusive@CCallback@?$CSingletonHelper@UPowerAdapter@1Internal@Windows@winrt@@@DataModel@SystemSettings@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::CCallback::LockHandleNotificationExclusive(void)
0x180029b5e  nop
0x180029b5f  lea     rcx, [rdi+28h]
0x180029b63  lea     rdx, [rsp+68h+arg_8]
0x180029b68  call    ??$_Erase@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@6@$0A@@std@@@std@@AEAA_KAEBQEAVCCallback@?$CSingletonHelper@H@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<int>::CCallback *>(SystemSettings::DataModel::CSingletonHelper<int>::CCallback * const &)
0x180029b6d  nop
0x180029b6e  lea     rcx, [rsp+68h+arg_10]
0x180029b76  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180029b7b  lea     rcx, [rsp+68h+arg_18]; this
0x180029b83  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180029b88  xor     r12b, r12b
0x180029b8b  lea     rbx, [rdi+70h]
0x180029b8f  mov     rcx, rbx; lpCriticalSection
0x180029b92  call    cs:__imp_EnterCriticalSection
0x180029b98  mov     [rsp+68h+arg_10], rbx
0x180029ba0  mov     r8b, 3
0x180029ba3  mov     dl, 1
0x180029ba5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180029bac  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180029bb1  cmp     dword ptr [rdi+98h], 0
0x180029bb8  jnz     short loc_180029C1A
0x180029bba  cmp     qword ptr [rdi+38h], 0
0x180029bbf  jnz     short loc_180029C1A
0x180029bc1  cmp     [rdi+0D0h], r12b
0x180029bc8  jnz     short loc_180029C1A
0x180029bca  cmp     dword ptr [rdi+0E0h], 0
0x180029bd1  jl      short loc_180029C1A
0x180029bd3  mov     r12b, 1
0x180029bd6  mov     [rdi+0D0h], r12b
0x180029bdd  lea     r15, [rdi+0C8h]
0x180029be4  mov     rbx, [r15]
0x180029be7  test    rbx, rbx
0x180029bea  jnz     short loc_180029C10
0x180029bec  xor     r9d, r9d; lpName
0x180029bef  xor     r8d, r8d; bInitialState
0x180029bf2  lea     edx, [rbx+1]; bManualReset
0x180029bf5  xor     ecx, ecx; lpEventAttributes
0x180029bf7  call    cs:__imp_CreateEventW
0x180029bfd  mov     rbx, rax
0x180029c00  mov     rcx, r15
0x180029c03  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180029c08  mov     [r15], rbx
0x180029c0b  test    rbx, rbx
0x180029c0e  jz      short loc_180029C1A
0x180029c10  mov     rcx, rbx; hEvent
0x180029c13  call    cs:__imp_ResetEvent
0x180029c19  nop
0x180029c1a  lea     rcx, [rsp+68h+arg_10]; this
0x180029c22  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180029c27  test    r12b, r12b
0x180029c2a  jz      short loc_180029C7B
0x180029c2c  mov     rax, [rdi]
0x180029c2f  mov     rcx, rdi
0x180029c32  mov     rax, [rax+10h]
0x180029c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c3b  nop
0x180029c3c  jmp     short loc_180029C48
0x180029c3e  mov     rdi, [rsp+68h+arg_0]
0x180029c43  mov     r14, [rsp+68h+var_38]
0x180029c48  mov     byte ptr [r14], 0
0x180029c4c  mov     dword ptr [rdi+0E0h], 8000FFFFh
0x180029c56  lea     rcx, [rdi+0D8h]; this
0x180029c5d  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x180029c62  mov     byte ptr [rdi+0D0h], 0
0x180029c69  mov     rcx, [rdi+0C8h]; hEvent
0x180029c70  test    rcx, rcx
0x180029c73  jz      short loc_180029C7B
0x180029c75  call    cs:__imp_SetEvent
0x180029c7b  mov     r8b, 3
0x180029c7e  mov     dl, 1
0x180029c80  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180029c87  add     rsp, 40h
0x180029c8b  pop     r15
0x180029c8d  pop     r14
0x180029c8f  pop     r12
0x180029c91  pop     rdi
0x180029c92  pop     rbx
0x180029c93  jmp     ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
```
