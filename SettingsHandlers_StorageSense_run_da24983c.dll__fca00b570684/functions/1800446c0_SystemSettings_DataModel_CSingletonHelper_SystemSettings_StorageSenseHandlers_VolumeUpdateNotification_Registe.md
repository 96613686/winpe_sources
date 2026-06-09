# SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::VolumeUpdateNotification>::Register(SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::VolumeUpdateNotification>::CCallback *)

- ea: `0x1800446c0`
- end: `0x18004487c`
- name: `?Register@?$CSingletonHelper@W4VolumeUpdateNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `444`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003a120`
- `0x18003a788`
- `0x18004f030`
- `0x18007ab90`
- `0x18008251c`
- `0x180082680`

## callees

- `0x18001f53c`
- `0x180027bc8`
- `0x1800323d0`
- `0x180032cd0`
- `0x180034afc`
- `0x1800446c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800446e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044806`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800446e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044806`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180044785`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180044785`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800447b3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800447b3`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18004472d`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18004472d`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x1800447ce`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x1800447ce`

## pseudocode

```c
void __fastcall SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::StorageSenseHandlers::VolumeUpdateNotification>::Register(
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
  EnterCriticalSection(&stru_18018AC20);
  v15 = &stru_18018AC20;
  _InterlockedIncrement(&dword_18018AC48);
  if ( byte_18018AC80 && qword_18018AC78 )
  {
    LODWORD(dwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &qword_18018AC78, (LPDWORD)&dwindex);
  }
  LOBYTE(v4) = 3;
  LOBYTE(v3) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v3,
    v4);
  if ( !byte_18018AC1A && !(_BYTE)word_18018AC18 )
  {
    if ( (LOBYTE(word_18018AC18) = 1, !dword_18018ABB8)
      || (EventW = qword_18018ABC0) == 0
      && (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&qword_18018ABC0),
          (qword_18018ABC0 = EventW) == 0)
      || (dword_18018AC90 = -2147483638,
          ResetEvent(EventW),
          !SHCreateThread(
             SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::s_InitializationThread,
             &SystemSettings::StorageSenseHandlers::g_storageSenseVolumeManager,
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
  EnterCriticalSection(&stru_18018AC50);
  dwindex = &stru_18018AC50;
  LOBYTE(v8) = 3;
  LOBYTE(v9) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v9,
    v8);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback * const &>(
    &unk_18018ABD8,
    v12,
    &v13);
  _InterlockedDecrement(&dword_18018AC48);
  LOBYTE(v10) = 3;
  LOBYTE(v11) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v11,
    v10);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&dwindex);
  if ( v2 )
    SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::_Initialization(&SystemSettings::StorageSenseHandlers::g_storageSenseVolumeManager);
}

```

## disassembly

```asm
0x1800446c0  mov     [rsp+arg_8], rdx
0x1800446c5  mov     [rsp+arg_0], rcx
0x1800446ca  push    rsi
0x1800446cb  push    rdi
0x1800446cc  sub     rsp, 48h
0x1800446d0  xor     dil, dil
0x1800446d3  mov     byte ptr [rsp+58h+arg_0], dil
0x1800446d8  lea     rsi, stru_18018AC20
0x1800446df  mov     rcx, rsi; lpCriticalSection
0x1800446e2  call    cs:__imp_EnterCriticalSection
0x1800446e8  mov     [rsp+58h+arg_18], rsi
0x1800446ed  lock inc cs:dword_18018AC48
0x1800446f4  cmp     cs:byte_18018AC80, dil
0x1800446fb  jz      short loc_180044733
0x1800446fd  cmp     cs:qword_18018AC78, 0
0x180044705  jz      short loc_180044733
0x180044707  mov     dword ptr [rsp+58h+dwindex], 0
0x18004470f  lea     rax, [rsp+58h+dwindex]
0x180044714  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x180044719  lea     r9, qword_18018AC78; pHandles
0x180044720  mov     r8d, 1; cHandles
0x180044726  or      edx, 0FFFFFFFFh; dwTimeout
0x180044729  lea     ecx, [r8+7]; dwFlags
0x18004472d  call    cs:__imp_CoWaitForMultipleHandles
0x180044733  mov     r8b, 3
0x180044736  mov     dl, 1
0x180044738  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18004473f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180044744  cmp     cs:byte_18018AC1A, 0
0x18004474b  jnz     loc_1800447E0
0x180044751  cmp     byte ptr cs:word_18018AC18, 0
0x180044758  jnz     loc_1800447E0
0x18004475e  mov     byte ptr cs:word_18018AC18, 1
0x180044765  cmp     cs:dword_18018ABB8, 0
0x18004476c  jz      short loc_1800447D8
0x18004476e  mov     rsi, cs:qword_18018ABC0
0x180044775  test    rsi, rsi
0x180044778  jnz     short loc_1800447A6
0x18004477a  xor     r9d, r9d; lpName
0x18004477d  xor     r8d, r8d; bInitialState
0x180044780  lea     edx, [rsi+1]; bManualReset
0x180044783  xor     ecx, ecx; lpEventAttributes
0x180044785  call    cs:__imp_CreateEventW
0x18004478b  mov     rsi, rax
0x18004478e  lea     rcx, qword_18018ABC0
0x180044795  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18004479a  mov     cs:qword_18018ABC0, rsi
0x1800447a1  test    rsi, rsi
0x1800447a4  jz      short loc_1800447D8
0x1800447a6  mov     cs:dword_18018AC90, 8000000Ah
0x1800447b0  mov     rcx, rsi; hEvent
0x1800447b3  call    cs:__imp_ResetEvent
0x1800447b9  xor     r9d, r9d; pfnCallback
0x1800447bc  lea     r8d, [r9+4]; flags
0x1800447c0  lea     rdx, ?g_storageSenseVolumeManager@StorageSenseHandlers@SystemSettings@@3VCRemovableMediaManager@12@A; pData
0x1800447c7  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@AEBV?$shared_ptr@UCleanupListHandlerEvent@StorageSenseHandlers@SystemSettings@@@std@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x1800447ce  call    cs:__imp_SHCreateThread
0x1800447d4  test    eax, eax
0x1800447d6  jnz     short loc_1800447E0
0x1800447d8  mov     dil, 1
0x1800447db  mov     byte ptr [rsp+58h+arg_0], dil
0x1800447e0  mov     r8b, 3
0x1800447e3  mov     dl, 1
0x1800447e5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x1800447ec  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800447f1  nop
0x1800447f2  lea     rcx, [rsp+58h+arg_18]; this
0x1800447f7  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800447fc  lea     rsi, stru_18018AC50
0x180044803  mov     rcx, rsi; lpCriticalSection
0x180044806  call    cs:__imp_EnterCriticalSection
0x18004480c  mov     [rsp+58h+dwindex], rsi
0x180044811  mov     r8b, 3
0x180044814  mov     dl, 1
0x180044816  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18004481d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180044822  nop
0x180044823  lea     r8, [rsp+58h+arg_8]
0x180044828  lea     rdx, [rsp+58h+var_28]
0x18004482d  lea     rcx, unk_18018ABD8
0x180044834  call    ??$emplace@AEBQEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback * const &)
0x180044839  nop
0x18004483a  jmp     short loc_180044841
0x18004483c  mov     dil, byte ptr [rsp+58h+arg_0]
0x180044841  lock dec cs:dword_18018AC48
0x180044848  mov     r8b, 3
0x18004484b  mov     dl, 1
0x18004484d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180044854  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180044859  nop
0x18004485a  lea     rcx, [rsp+58h+dwindex]; this
0x18004485f  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180044864  test    dil, dil
0x180044867  jz      short loc_180044875
0x180044869  lea     rcx, ?g_storageSenseVolumeManager@StorageSenseHandlers@SystemSettings@@3VCRemovableMediaManager@12@A; SystemSettings::StorageSenseHandlers::CRemovableMediaManager SystemSettings::StorageSenseHandlers::g_storageSenseVolumeManager
0x180044870  call    ?_Initialization@?$CSingletonHelper@PEAUAppListChangeNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::_Initialization(void)
0x180044875  add     rsp, 48h
0x180044879  pop     rdi
0x18004487a  pop     rsi
0x18004487b  retn
```
