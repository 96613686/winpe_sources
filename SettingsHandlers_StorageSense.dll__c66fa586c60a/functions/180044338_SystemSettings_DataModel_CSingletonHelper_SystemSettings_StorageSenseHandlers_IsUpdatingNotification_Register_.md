# SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::IsUpdatingNotification *>::Register(SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::IsUpdatingNotification *>::CCallback *)

- ea: `0x180044338`
- end: `0x1800444f4`
- name: `?Register@?$CSingletonHelper@PEAUIsUpdatingNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `444`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003a24c`
- `0x18003ac74`

## callees

- `0x18001f53c`
- `0x180027bc8`
- `0x1800323d0`
- `0x180032cd0`
- `0x180034afc`
- `0x180044338`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004435a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004447e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004435a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004447e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800443fd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800443fd`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18004442b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18004442b`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800443a5`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800443a5`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180044446`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180044446`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::IsUpdatingNotification *>::Register(
        __int64 a1,
        __int64 a2)
{
  char v2; // di
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // r8
  HANDLE EventW; // rsi
  __int64 v8; // r8
  __int64 v9; // rdx
  const char *v10; // r9
  __int64 v11; // rdx
  __int64 v12; // r8
  _BYTE v13[40]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  char v15; // [rsp+60h] [rbp+8h]
  __int64 v16; // [rsp+68h] [rbp+10h] BYREF
  struct _RTL_CRITICAL_SECTION *dwindex; // [rsp+70h] [rbp+18h] BYREF
  struct _RTL_CRITICAL_SECTION *v18; // [rsp+78h] [rbp+20h] BYREF

  v16 = a2;
  v2 = 0;
  v15 = 0;
  EnterCriticalSection(&stru_18018A620);
  v18 = &stru_18018A620;
  _InterlockedIncrement(&dword_18018A648);
  if ( byte_18018A680 && pHandles )
  {
    LODWORD(dwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &pHandles, (LPDWORD)&dwindex);
  }
  LOBYTE(v4) = 3;
  LOBYTE(v3) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v3,
    v4);
  if ( !byte_18018A61A && !(_BYTE)word_18018A618 )
  {
    if ( (LOBYTE(word_18018A618) = 1, !dword_18018A5B8)
      || (EventW = hEvent) == 0
      && (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&hEvent),
          (hEvent = EventW) == 0)
      || (dword_18018A690 = -2147483638,
          ResetEvent(EventW),
          !SHCreateThread(
             SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::s_InitializationThread,
             &SystemSettings::StorageSenseHandlers::isUpdatingSingleton,
             4u,
             0)) )
    {
      v2 = 1;
      v15 = 1;
    }
  }
  LOBYTE(v6) = 3;
  LOBYTE(v5) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v5,
    v6);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v18);
  EnterCriticalSection(&stru_18018A650);
  dwindex = &stru_18018A650;
  LOBYTE(v8) = 3;
  LOBYTE(v9) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v9,
    v8);
  try
  {
    std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback * const &>(
      (float *)&qword_18018A5D8,
      (__int64)v13,
      (unsigned __int8 *)&v16);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x4A5,
      (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingHandlersBaseCore.h",
      v10);
    v2 = v15;
  }
  _InterlockedDecrement(&dword_18018A648);
  LOBYTE(v12) = 3;
  LOBYTE(v11) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v11,
    v12);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&dwindex);
  if ( v2 )
    SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::_Initialization(&SystemSettings::StorageSenseHandlers::isUpdatingSingleton);
}

```

## disassembly

```asm
0x180044338  mov     [rsp+arg_8], rdx
0x18004433d  mov     [rsp+arg_0], rcx
0x180044342  push    rsi
0x180044343  push    rdi
0x180044344  sub     rsp, 48h
0x180044348  xor     dil, dil
0x18004434b  mov     byte ptr [rsp+58h+arg_0], dil
0x180044350  lea     rsi, stru_18018A620
0x180044357  mov     rcx, rsi; lpCriticalSection
0x18004435a  call    cs:__imp_EnterCriticalSection
0x180044360  mov     [rsp+58h+arg_18], rsi
0x180044365  lock inc cs:dword_18018A648
0x18004436c  cmp     cs:byte_18018A680, dil
0x180044373  jz      short loc_1800443AB
0x180044375  cmp     cs:pHandles, 0
0x18004437d  jz      short loc_1800443AB
0x18004437f  mov     dword ptr [rsp+58h+dwindex], 0
0x180044387  lea     rax, [rsp+58h+dwindex]
0x18004438c  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x180044391  lea     r9, pHandles; pHandles
0x180044398  mov     r8d, 1; cHandles
0x18004439e  or      edx, 0FFFFFFFFh; dwTimeout
0x1800443a1  lea     ecx, [r8+7]; dwFlags
0x1800443a5  call    cs:__imp_CoWaitForMultipleHandles
0x1800443ab  mov     r8b, 3
0x1800443ae  mov     dl, 1
0x1800443b0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x1800443b7  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800443bc  cmp     cs:byte_18018A61A, 0
0x1800443c3  jnz     loc_180044458
0x1800443c9  cmp     byte ptr cs:word_18018A618, 0
0x1800443d0  jnz     loc_180044458
0x1800443d6  mov     byte ptr cs:word_18018A618, 1
0x1800443dd  cmp     cs:dword_18018A5B8, 0
0x1800443e4  jz      short loc_180044450
0x1800443e6  mov     rsi, cs:hEvent
0x1800443ed  test    rsi, rsi
0x1800443f0  jnz     short loc_18004441E
0x1800443f2  xor     r9d, r9d; lpName
0x1800443f5  xor     r8d, r8d; bInitialState
0x1800443f8  lea     edx, [rsi+1]; bManualReset
0x1800443fb  xor     ecx, ecx; lpEventAttributes
0x1800443fd  call    cs:__imp_CreateEventW
0x180044403  mov     rsi, rax
0x180044406  lea     rcx, hEvent
0x18004440d  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180044412  mov     cs:hEvent, rsi
0x180044419  test    rsi, rsi
0x18004441c  jz      short loc_180044450
0x18004441e  mov     cs:dword_18018A690, 8000000Ah
0x180044428  mov     rcx, rsi; hEvent
0x18004442b  call    cs:__imp_ResetEvent
0x180044431  xor     r9d, r9d; pfnCallback
0x180044434  lea     r8d, [r9+4]; flags
0x180044438  lea     rdx, ?isUpdatingSingleton@StorageSenseHandlers@SystemSettings@@3VCIsUpdatingSingleton@12@A; pData
0x18004443f  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@AEBV?$shared_ptr@UCleanupListHandlerEvent@StorageSenseHandlers@SystemSettings@@@std@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x180044446  call    cs:__imp_SHCreateThread
0x18004444c  test    eax, eax
0x18004444e  jnz     short loc_180044458
0x180044450  mov     dil, 1
0x180044453  mov     byte ptr [rsp+58h+arg_0], dil
0x180044458  mov     r8b, 3
0x18004445b  mov     dl, 1
0x18004445d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180044464  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180044469  nop
0x18004446a  lea     rcx, [rsp+58h+arg_18]; this
0x18004446f  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180044474  lea     rsi, stru_18018A650
0x18004447b  mov     rcx, rsi; lpCriticalSection
0x18004447e  call    cs:__imp_EnterCriticalSection
0x180044484  mov     [rsp+58h+dwindex], rsi
0x180044489  mov     r8b, 3
0x18004448c  mov     dl, 1
0x18004448e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180044495  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004449a  nop
0x18004449b  lea     r8, [rsp+58h+arg_8]
0x1800444a0  lea     rdx, [rsp+58h+var_28]
0x1800444a5  lea     rcx, qword_18018A5D8
0x1800444ac  call    ??$emplace@AEBQEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback * const &)
0x1800444b1  nop
0x1800444b2  jmp     short loc_1800444B9
0x1800444b4  mov     dil, byte ptr [rsp+58h+arg_0]
0x1800444b9  lock dec cs:dword_18018A648
0x1800444c0  mov     r8b, 3
0x1800444c3  mov     dl, 1
0x1800444c5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x1800444cc  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800444d1  nop
0x1800444d2  lea     rcx, [rsp+58h+dwindex]; this
0x1800444d7  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800444dc  test    dil, dil
0x1800444df  jz      short loc_1800444ED
0x1800444e1  lea     rcx, ?isUpdatingSingleton@StorageSenseHandlers@SystemSettings@@3VCIsUpdatingSingleton@12@A; SystemSettings::StorageSenseHandlers::CIsUpdatingSingleton SystemSettings::StorageSenseHandlers::isUpdatingSingleton
0x1800444e8  call    ?_Initialization@?$CSingletonHelper@PEAUAppListChangeNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::_Initialization(void)
0x1800444ed  add     rsp, 48h
0x1800444f1  pop     rdi
0x1800444f2  pop     rsi
0x1800444f3  retn
```
