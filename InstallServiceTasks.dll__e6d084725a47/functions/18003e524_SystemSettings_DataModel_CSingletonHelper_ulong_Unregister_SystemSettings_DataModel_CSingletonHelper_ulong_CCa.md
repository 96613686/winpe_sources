# SystemSettings::DataModel::CSingletonHelper<ulong>::Unregister(SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *)

- ea: `0x18003e524`
- end: `0x18003e6f0`
- name: `?Unregister@?$CSingletonHelper@K@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003b85c`

## callees

- `0x180005bfc`
- `0x18003ac00`
- `0x18003d418`
- `0x18003d518`
- `0x18003d900`
- `0x18003da68`
- `0x18003ddac`
- `0x18003e524`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003e66b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003e66b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003e6cd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003e6cd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003e64f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003e64f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e598`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e5ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e598`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e5ea`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18003e577`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18003e577`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<unsigned long>::Unregister(
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
  SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback::LockHandleNotificationExclusive(v3, &lpdwindex);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *>(
    (_QWORD *)(v4 + 40),
    (__int64)&v20);
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
0x18003e524  mov     rax, rsp
0x18003e527  mov     [rax+10h], rdx
0x18003e52b  mov     [rax+8], rcx
0x18003e52f  push    rbx
0x18003e530  push    rdi
0x18003e531  push    r12
0x18003e533  push    r14
0x18003e535  push    r15
0x18003e537  sub     rsp, 40h
0x18003e53b  mov     r15, rdx
0x18003e53e  mov     rdi, rcx
0x18003e541  lea     r14, [rcx+6Ah]
0x18003e545  mov     [rsp+68h+var_38], r14
0x18003e54a  cmp     byte ptr [r14], 0
0x18003e54e  jnz     short loc_18003E57D
0x18003e550  lea     r9, [rcx+10h]; pHandles
0x18003e554  cmp     qword ptr [r9], 0
0x18003e558  jz      short loc_18003E57D
0x18003e55a  mov     dword ptr [rax+18h], 0
0x18003e561  lea     rax, [rax+18h]
0x18003e565  mov     [rsp+68h+lpdwindex], rax; lpdwindex
0x18003e56a  mov     r8d, 1; cHandles
0x18003e570  or      edx, 0FFFFFFFFh; dwTimeout
0x18003e573  lea     ecx, [r8+7]; dwFlags
0x18003e577  call    cs:__imp_CoWaitForMultipleHandles
0x18003e57d  mov     r8b, 3
0x18003e580  mov     dl, 1
0x18003e582  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18003e589  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003e58e  lea     rbx, [rdi+0A0h]
0x18003e595  mov     rcx, rbx; lpCriticalSection
0x18003e598  call    cs:__imp_EnterCriticalSection
0x18003e59e  mov     [rsp+68h+arg_18], rbx
0x18003e5a6  lea     rdx, [rsp+68h+arg_10]
0x18003e5ae  mov     rcx, r15
0x18003e5b1  call    ?LockHandleNotificationExclusive@CCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback::LockHandleNotificationExclusive(void)
0x18003e5b6  nop
0x18003e5b7  lea     rcx, [rdi+28h]
0x18003e5bb  lea     rdx, [rsp+68h+arg_8]
0x18003e5c0  call    ??$_Erase@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@@6@$0A@@std@@@std@@AEAA_KAEBQEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *>(SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback * const &)
0x18003e5c5  nop
0x18003e5c6  lea     rcx, [rsp+68h+arg_10]
0x18003e5ce  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003e5d3  lea     rcx, [rsp+68h+arg_18]; this
0x18003e5db  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18003e5e0  xor     r12b, r12b
0x18003e5e3  lea     rbx, [rdi+70h]
0x18003e5e7  mov     rcx, rbx; lpCriticalSection
0x18003e5ea  call    cs:__imp_EnterCriticalSection
0x18003e5f0  mov     [rsp+68h+arg_10], rbx
0x18003e5f8  mov     r8b, 3
0x18003e5fb  mov     dl, 1
0x18003e5fd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18003e604  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003e609  cmp     dword ptr [rdi+98h], 0
0x18003e610  jnz     short loc_18003E672
0x18003e612  cmp     qword ptr [rdi+38h], 0
0x18003e617  jnz     short loc_18003E672
0x18003e619  cmp     [rdi+0D0h], r12b
0x18003e620  jnz     short loc_18003E672
0x18003e622  cmp     dword ptr [rdi+0E0h], 0
0x18003e629  jl      short loc_18003E672
0x18003e62b  mov     r12b, 1
0x18003e62e  mov     [rdi+0D0h], r12b
0x18003e635  lea     r15, [rdi+0C8h]
0x18003e63c  mov     rbx, [r15]
0x18003e63f  test    rbx, rbx
0x18003e642  jnz     short loc_18003E668
0x18003e644  xor     r9d, r9d; lpName
0x18003e647  xor     r8d, r8d; bInitialState
0x18003e64a  lea     edx, [rbx+1]; bManualReset
0x18003e64d  xor     ecx, ecx; lpEventAttributes
0x18003e64f  call    cs:__imp_CreateEventW
0x18003e655  mov     rbx, rax
0x18003e658  mov     rcx, r15
0x18003e65b  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18003e660  mov     [r15], rbx
0x18003e663  test    rbx, rbx
0x18003e666  jz      short loc_18003E672
0x18003e668  mov     rcx, rbx; hEvent
0x18003e66b  call    cs:__imp_ResetEvent
0x18003e671  nop
0x18003e672  lea     rcx, [rsp+68h+arg_10]; this
0x18003e67a  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18003e67f  test    r12b, r12b
0x18003e682  jz      short loc_18003E6D3
0x18003e684  mov     rax, [rdi]
0x18003e687  mov     rcx, rdi
0x18003e68a  mov     rax, [rax+10h]
0x18003e68e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e693  nop
0x18003e694  jmp     short loc_18003E6A0
0x18003e696  mov     rdi, [rsp+68h+arg_0]
0x18003e69b  mov     r14, [rsp+68h+var_38]
0x18003e6a0  mov     byte ptr [r14], 0
0x18003e6a4  mov     dword ptr [rdi+0E0h], 8000FFFFh
0x18003e6ae  lea     rcx, [rdi+0D8h]; this
0x18003e6b5  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x18003e6ba  mov     byte ptr [rdi+0D0h], 0
0x18003e6c1  mov     rcx, [rdi+0C8h]; hEvent
0x18003e6c8  test    rcx, rcx
0x18003e6cb  jz      short loc_18003E6D3
0x18003e6cd  call    cs:__imp_SetEvent
0x18003e6d3  mov     r8b, 3
0x18003e6d6  mov     dl, 1
0x18003e6d8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18003e6df  add     rsp, 40h
0x18003e6e3  pop     r15
0x18003e6e5  pop     r14
0x18003e6e7  pop     r12
0x18003e6e9  pop     rdi
0x18003e6ea  pop     rbx
0x18003e6eb  jmp     ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
```
