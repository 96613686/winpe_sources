# SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::TotalVisibleAppNotification *>::Register(SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::TotalVisibleAppNotification *>::CCallback *)

- ea: `0x1800444fc`
- end: `0x1800446b8`
- name: `?Register@?$CSingletonHelper@PEAUTotalVisibleAppNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
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
- `0x1800444fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004451e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044642`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004451e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044642`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800445c1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800445c1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800445ef`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800445ef`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180044569`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180044569`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18004460a`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18004460a`

## pseudocode

```c
void __fastcall SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::TotalVisibleAppNotification *>::Register(
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
  __int64 v10; // r8
  __int64 v11; // rdx
  _BYTE v12[40]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v13; // [rsp+68h] [rbp+10h] BYREF
  struct _RTL_CRITICAL_SECTION *dwindex; // [rsp+70h] [rbp+18h] BYREF
  struct _RTL_CRITICAL_SECTION *v15; // [rsp+78h] [rbp+20h] BYREF

  v13 = a2;
  v2 = 0;
  EnterCriticalSection(&stru_18018A530);
  v15 = &stru_18018A530;
  _InterlockedIncrement(&dword_18018A558);
  if ( byte_18018A590 && qword_18018A588 )
  {
    LODWORD(dwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &qword_18018A588, (LPDWORD)&dwindex);
  }
  LOBYTE(v4) = 3;
  LOBYTE(v3) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v3,
    v4);
  if ( !byte_18018A52A && !(_BYTE)word_18018A528 )
  {
    if ( (LOBYTE(word_18018A528) = 1, !dword_18018A4C8)
      || (EventW = qword_18018A4D0) == 0
      && (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&qword_18018A4D0),
          (qword_18018A4D0 = EventW) == 0)
      || (dword_18018A5A0 = -2147483638,
          ResetEvent(EventW),
          !SHCreateThread(
             SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::s_InitializationThread,
             &SystemSettings::StorageSenseHandlers::totalAppsVisibleSingleton,
             4u,
             0)) )
    {
      v2 = 1;
    }
  }
  LOBYTE(v6) = 3;
  LOBYTE(v5) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v5,
    v6);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v15);
  EnterCriticalSection(&stru_18018A560);
  dwindex = &stru_18018A560;
  LOBYTE(v8) = 3;
  LOBYTE(v9) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v9,
    v8);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback * const &>(
    &unk_18018A4E8,
    v12,
    &v13);
  _InterlockedDecrement(&dword_18018A558);
  LOBYTE(v10) = 3;
  LOBYTE(v11) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v11,
    v10);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&dwindex);
  if ( v2 )
    SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::_Initialization(&SystemSettings::StorageSenseHandlers::totalAppsVisibleSingleton);
}

```

## disassembly

```asm
0x1800444fc  mov     [rsp+arg_8], rdx
0x180044501  mov     [rsp+arg_0], rcx
0x180044506  push    rsi
0x180044507  push    rdi
0x180044508  sub     rsp, 48h
0x18004450c  xor     dil, dil
0x18004450f  mov     byte ptr [rsp+58h+arg_0], dil
0x180044514  lea     rsi, stru_18018A530
0x18004451b  mov     rcx, rsi; lpCriticalSection
0x18004451e  call    cs:__imp_EnterCriticalSection
0x180044524  mov     [rsp+58h+arg_18], rsi
0x180044529  lock inc cs:dword_18018A558
0x180044530  cmp     cs:byte_18018A590, dil
0x180044537  jz      short loc_18004456F
0x180044539  cmp     cs:qword_18018A588, 0
0x180044541  jz      short loc_18004456F
0x180044543  mov     dword ptr [rsp+58h+dwindex], 0
0x18004454b  lea     rax, [rsp+58h+dwindex]
0x180044550  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x180044555  lea     r9, qword_18018A588; pHandles
0x18004455c  mov     r8d, 1; cHandles
0x180044562  or      edx, 0FFFFFFFFh; dwTimeout
0x180044565  lea     ecx, [r8+7]; dwFlags
0x180044569  call    cs:__imp_CoWaitForMultipleHandles
0x18004456f  mov     r8b, 3
0x180044572  mov     dl, 1
0x180044574  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18004457b  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180044580  cmp     cs:byte_18018A52A, 0
0x180044587  jnz     loc_18004461C
0x18004458d  cmp     byte ptr cs:word_18018A528, 0
0x180044594  jnz     loc_18004461C
0x18004459a  mov     byte ptr cs:word_18018A528, 1
0x1800445a1  cmp     cs:dword_18018A4C8, 0
0x1800445a8  jz      short loc_180044614
0x1800445aa  mov     rsi, cs:qword_18018A4D0
0x1800445b1  test    rsi, rsi
0x1800445b4  jnz     short loc_1800445E2
0x1800445b6  xor     r9d, r9d; lpName
0x1800445b9  xor     r8d, r8d; bInitialState
0x1800445bc  lea     edx, [rsi+1]; bManualReset
0x1800445bf  xor     ecx, ecx; lpEventAttributes
0x1800445c1  call    cs:__imp_CreateEventW
0x1800445c7  mov     rsi, rax
0x1800445ca  lea     rcx, qword_18018A4D0
0x1800445d1  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x1800445d6  mov     cs:qword_18018A4D0, rsi
0x1800445dd  test    rsi, rsi
0x1800445e0  jz      short loc_180044614
0x1800445e2  mov     cs:dword_18018A5A0, 8000000Ah
0x1800445ec  mov     rcx, rsi; hEvent
0x1800445ef  call    cs:__imp_ResetEvent
0x1800445f5  xor     r9d, r9d; pfnCallback
0x1800445f8  lea     r8d, [r9+4]; flags
0x1800445fc  lea     rdx, ?totalAppsVisibleSingleton@StorageSenseHandlers@SystemSettings@@3VCTotalAppsVisibleSingleton@12@A; pData
0x180044603  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@AEBV?$shared_ptr@UCleanupListHandlerEvent@StorageSenseHandlers@SystemSettings@@@std@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x18004460a  call    cs:__imp_SHCreateThread
0x180044610  test    eax, eax
0x180044612  jnz     short loc_18004461C
0x180044614  mov     dil, 1
0x180044617  mov     byte ptr [rsp+58h+arg_0], dil
0x18004461c  mov     r8b, 3
0x18004461f  mov     dl, 1
0x180044621  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180044628  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004462d  nop
0x18004462e  lea     rcx, [rsp+58h+arg_18]; this
0x180044633  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180044638  lea     rsi, stru_18018A560
0x18004463f  mov     rcx, rsi; lpCriticalSection
0x180044642  call    cs:__imp_EnterCriticalSection
0x180044648  mov     [rsp+58h+dwindex], rsi
0x18004464d  mov     r8b, 3
0x180044650  mov     dl, 1
0x180044652  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180044659  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004465e  nop
0x18004465f  lea     r8, [rsp+58h+arg_8]
0x180044664  lea     rdx, [rsp+58h+var_28]
0x180044669  lea     rcx, unk_18018A4E8
0x180044670  call    ??$emplace@AEBQEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback * const &)
0x180044675  nop
0x180044676  jmp     short loc_18004467D
0x180044678  mov     dil, byte ptr [rsp+58h+arg_0]
0x18004467d  lock dec cs:dword_18018A558
0x180044684  mov     r8b, 3
0x180044687  mov     dl, 1
0x180044689  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180044690  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180044695  nop
0x180044696  lea     rcx, [rsp+58h+dwindex]; this
0x18004469b  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800446a0  test    dil, dil
0x1800446a3  jz      short loc_1800446B1
0x1800446a5  lea     rcx, ?totalAppsVisibleSingleton@StorageSenseHandlers@SystemSettings@@3VCTotalAppsVisibleSingleton@12@A; SystemSettings::StorageSenseHandlers::CTotalAppsVisibleSingleton SystemSettings::StorageSenseHandlers::totalAppsVisibleSingleton
0x1800446ac  call    ?_Initialization@?$CSingletonHelper@PEAUAppListChangeNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::_Initialization(void)
0x1800446b1  add     rsp, 48h
0x1800446b5  pop     rdi
0x1800446b6  pop     rsi
0x1800446b7  retn
```
