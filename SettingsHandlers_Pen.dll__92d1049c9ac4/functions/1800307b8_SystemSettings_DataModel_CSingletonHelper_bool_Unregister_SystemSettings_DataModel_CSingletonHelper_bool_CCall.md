# SystemSettings::DataModel::CSingletonHelper<bool>::Unregister(SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *)

- ea: `0x1800307b8`
- end: `0x180030984`
- name: `?Unregister@?$CSingletonHelper@_N@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `460`
- prototype: ``
- caller_count: `19`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800207c4`
- `0x180020870`
- `0x180020988`
- `0x180020a18`
- `0x180020b08`
- `0x180020bdc`
- `0x180034ae4`
- `0x180034bac`
- `0x180034c4c`
- `0x180034cec`
- `0x180034d8c`
- `0x180034e48`
- `0x180034ee8`
- `0x180034f78`
- `0x180035070`
- `0x180035128`
- `0x1800351b8`
- `0x18003528c`
- `0x18003532c`

## callees

- `0x180005eec`
- `0x18001620c`
- `0x18001d500`
- `0x18002ca34`
- `0x18002d7e8`
- `0x18002d814`
- `0x18002e2b8`
- `0x1800307b8`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003082c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003087e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003082c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003087e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800308e3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800308e3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180030961`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180030961`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800308ff`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800308ff`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18003080b`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18003080b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CSingletonHelper<bool>::Unregister(__int64 a1, __int64 a2, __int64 a3)
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
  SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::CCallback::LockHandleNotificationExclusive(
    v3,
    &lpdwindex);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>(
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
0x1800307b8  mov     rax, rsp
0x1800307bb  mov     [rax+10h], rdx
0x1800307bf  mov     [rax+8], rcx
0x1800307c3  push    rbx
0x1800307c4  push    rdi
0x1800307c5  push    r12
0x1800307c7  push    r14
0x1800307c9  push    r15
0x1800307cb  sub     rsp, 40h
0x1800307cf  mov     r15, rdx
0x1800307d2  mov     rdi, rcx
0x1800307d5  lea     r14, [rcx+6Ah]
0x1800307d9  mov     [rsp+68h+var_38], r14
0x1800307de  cmp     byte ptr [r14], 0
0x1800307e2  jnz     short loc_180030811
0x1800307e4  lea     r9, [rcx+10h]; pHandles
0x1800307e8  cmp     qword ptr [r9], 0
0x1800307ec  jz      short loc_180030811
0x1800307ee  mov     dword ptr [rax+18h], 0
0x1800307f5  lea     rax, [rax+18h]
0x1800307f9  mov     [rsp+68h+lpdwindex], rax; lpdwindex
0x1800307fe  mov     r8d, 1; cHandles
0x180030804  or      edx, 0FFFFFFFFh; dwTimeout
0x180030807  lea     ecx, [r8+7]; dwFlags
0x18003080b  call    cs:__imp_CoWaitForMultipleHandles
0x180030811  mov     r8b, 3
0x180030814  mov     dl, 1
0x180030816  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18003081d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180030822  lea     rbx, [rdi+0A0h]
0x180030829  mov     rcx, rbx; lpCriticalSection
0x18003082c  call    cs:__imp_EnterCriticalSection
0x180030832  mov     [rsp+68h+arg_18], rbx
0x18003083a  lea     rdx, [rsp+68h+arg_10]
0x180030842  mov     rcx, r15
0x180030845  call    ?LockHandleNotificationExclusive@CCallback@?$CSingletonHelper@AEAUPenButtonAppPickerNotificationItem@PenSettings@SystemSettings@@@DataModel@SystemSettings@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::CCallback::LockHandleNotificationExclusive(void)
0x18003084a  nop
0x18003084b  lea     rcx, [rdi+28h]
0x18003084f  lea     rdx, [rsp+68h+arg_8]
0x180030854  call    ??$_Erase@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@6@$0A@@std@@@std@@AEAA_KAEBQEAVCCallback@?$CSingletonHelper@_N@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>,0>>::_Erase<SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *>(SystemSettings::DataModel::CSingletonHelper<bool>::CCallback * const &)
0x180030859  nop
0x18003085a  lea     rcx, [rsp+68h+arg_10]
0x180030862  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180030867  lea     rcx, [rsp+68h+arg_18]; this
0x18003086f  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180030874  xor     r12b, r12b
0x180030877  lea     rbx, [rdi+70h]
0x18003087b  mov     rcx, rbx; lpCriticalSection
0x18003087e  call    cs:__imp_EnterCriticalSection
0x180030884  mov     [rsp+68h+arg_10], rbx
0x18003088c  mov     r8b, 3
0x18003088f  mov     dl, 1
0x180030891  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180030898  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003089d  cmp     dword ptr [rdi+98h], 0
0x1800308a4  jnz     short loc_180030906
0x1800308a6  cmp     qword ptr [rdi+38h], 0
0x1800308ab  jnz     short loc_180030906
0x1800308ad  cmp     [rdi+0D0h], r12b
0x1800308b4  jnz     short loc_180030906
0x1800308b6  cmp     dword ptr [rdi+0E0h], 0
0x1800308bd  jl      short loc_180030906
0x1800308bf  mov     r12b, 1
0x1800308c2  mov     [rdi+0D0h], r12b
0x1800308c9  lea     r15, [rdi+0C8h]
0x1800308d0  mov     rbx, [r15]
0x1800308d3  test    rbx, rbx
0x1800308d6  jnz     short loc_1800308FC
0x1800308d8  xor     r9d, r9d; lpName
0x1800308db  xor     r8d, r8d; bInitialState
0x1800308de  lea     edx, [rbx+1]; bManualReset
0x1800308e1  xor     ecx, ecx; lpEventAttributes
0x1800308e3  call    cs:__imp_CreateEventW
0x1800308e9  mov     rbx, rax
0x1800308ec  mov     rcx, r15
0x1800308ef  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x1800308f4  mov     [r15], rbx
0x1800308f7  test    rbx, rbx
0x1800308fa  jz      short loc_180030906
0x1800308fc  mov     rcx, rbx; hEvent
0x1800308ff  call    cs:__imp_ResetEvent
0x180030905  nop
0x180030906  lea     rcx, [rsp+68h+arg_10]; this
0x18003090e  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180030913  test    r12b, r12b
0x180030916  jz      short loc_180030967
0x180030918  mov     rax, [rdi]
0x18003091b  mov     rcx, rdi
0x18003091e  mov     rax, [rax+10h]
0x180030922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030927  nop
0x180030928  jmp     short loc_180030934
0x18003092a  mov     rdi, [rsp+68h+arg_0]
0x18003092f  mov     r14, [rsp+68h+var_38]
0x180030934  mov     byte ptr [r14], 0
0x180030938  mov     dword ptr [rdi+0E0h], 8000FFFFh
0x180030942  lea     rcx, [rdi+0D8h]; this
0x180030949  call    ?Release@AutoMTAUsageCookie@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::AutoMTAUsageCookie::Release(void)
0x18003094e  mov     byte ptr [rdi+0D0h], 0
0x180030955  mov     rcx, [rdi+0C8h]; hEvent
0x18003095c  test    rcx, rcx
0x18003095f  jz      short loc_180030967
0x180030961  call    cs:__imp_SetEvent
0x180030967  mov     r8b, 3
0x18003096a  mov     dl, 1
0x18003096c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180030973  add     rsp, 40h
0x180030977  pop     r15
0x180030979  pop     r14
0x18003097b  pop     r12
0x18003097d  pop     rdi
0x18003097e  pop     rbx
0x18003097f  jmp     ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
```
