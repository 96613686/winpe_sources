# SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::BackgroundPermission>::Register(SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::BackgroundPermission>::CCallback *)

- ea: `0x1800cbc00`
- end: `0x1800cbdbc`
- name: `?Register@?$CSingletonHelper@W4BackgroundPermission@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c8918`

## callees

- `0x18001f53c`
- `0x180027bc8`
- `0x1800323d0`
- `0x180032cd0`
- `0x180034afc`
- `0x1800cbc00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cbc22`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cbd46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cbc22`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cbd46`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800cbcc5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800cbcc5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800cbcf3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800cbcf3`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800cbc6d`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800cbc6d`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x1800cbd0e`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x1800cbd0e`

## pseudocode

```c
void __fastcall SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::StorageSenseHandlers::BackgroundPermission>::Register(
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
  EnterCriticalSection(&stru_18018B170);
  v15 = &stru_18018B170;
  _InterlockedIncrement(&dword_18018B198);
  if ( byte_18018B1D0 && qword_18018B1C8 )
  {
    LODWORD(dwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &qword_18018B1C8, (LPDWORD)&dwindex);
  }
  LOBYTE(v4) = 3;
  LOBYTE(v3) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v3,
    v4);
  if ( !byte_18018B16A && !(_BYTE)word_18018B168 )
  {
    if ( (LOBYTE(word_18018B168) = 1, !dword_18018B108)
      || (EventW = qword_18018B110) == 0
      && (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&qword_18018B110),
          (qword_18018B110 = EventW) == 0)
      || (dword_18018B1E0 = -2147483638,
          ResetEvent(EventW),
          !SHCreateThread(
             SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::s_InitializationThread,
             &SystemSettings::StorageSenseHandlers::g_backgroundPermissionSingleton,
             4u,
             0)) )
    {
      v2 = 1;
    }
  }
  LOBYTE(v6) = 3;
  LOBYTE(v5) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v5,
    v6);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v15);
  EnterCriticalSection(&stru_18018B1A0);
  dwindex = &stru_18018B1A0;
  LOBYTE(v8) = 3;
  LOBYTE(v9) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v9,
    v8);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback * const &>(
    (float *)&qword_18018B128,
    (__int64)v12,
    (unsigned __int8 *)&v13);
  _InterlockedDecrement(&dword_18018B198);
  LOBYTE(v10) = 3;
  LOBYTE(v11) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v11,
    v10);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&dwindex);
  if ( v2 )
    SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::_Initialization(&SystemSettings::StorageSenseHandlers::g_backgroundPermissionSingleton);
}

```

## disassembly

```asm
0x1800cbc00  mov     [rsp+arg_8], rdx
0x1800cbc05  mov     [rsp+arg_0], rcx
0x1800cbc0a  push    rsi
0x1800cbc0b  push    rdi
0x1800cbc0c  sub     rsp, 48h
0x1800cbc10  xor     dil, dil
0x1800cbc13  mov     byte ptr [rsp+58h+arg_0], dil
0x1800cbc18  lea     rsi, stru_18018B170
0x1800cbc1f  mov     rcx, rsi; lpCriticalSection
0x1800cbc22  call    cs:__imp_EnterCriticalSection
0x1800cbc28  mov     [rsp+58h+arg_18], rsi
0x1800cbc2d  lock inc cs:dword_18018B198
0x1800cbc34  cmp     cs:byte_18018B1D0, dil
0x1800cbc3b  jz      short loc_1800CBC73
0x1800cbc3d  cmp     cs:qword_18018B1C8, 0
0x1800cbc45  jz      short loc_1800CBC73
0x1800cbc47  mov     dword ptr [rsp+58h+dwindex], 0
0x1800cbc4f  lea     rax, [rsp+58h+dwindex]
0x1800cbc54  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x1800cbc59  lea     r9, qword_18018B1C8; pHandles
0x1800cbc60  mov     r8d, 1; cHandles
0x1800cbc66  or      edx, 0FFFFFFFFh; dwTimeout
0x1800cbc69  lea     ecx, [r8+7]; dwFlags
0x1800cbc6d  call    cs:__imp_CoWaitForMultipleHandles
0x1800cbc73  mov     r8b, 3
0x1800cbc76  mov     dl, 1
0x1800cbc78  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x1800cbc7f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800cbc84  cmp     cs:byte_18018B16A, 0
0x1800cbc8b  jnz     loc_1800CBD20
0x1800cbc91  cmp     byte ptr cs:word_18018B168, 0
0x1800cbc98  jnz     loc_1800CBD20
0x1800cbc9e  mov     byte ptr cs:word_18018B168, 1
0x1800cbca5  cmp     cs:dword_18018B108, 0
0x1800cbcac  jz      short loc_1800CBD18
0x1800cbcae  mov     rsi, cs:qword_18018B110
0x1800cbcb5  test    rsi, rsi
0x1800cbcb8  jnz     short loc_1800CBCE6
0x1800cbcba  xor     r9d, r9d; lpName
0x1800cbcbd  xor     r8d, r8d; bInitialState
0x1800cbcc0  lea     edx, [rsi+1]; bManualReset
0x1800cbcc3  xor     ecx, ecx; lpEventAttributes
0x1800cbcc5  call    cs:__imp_CreateEventW
0x1800cbccb  mov     rsi, rax
0x1800cbcce  lea     rcx, qword_18018B110
0x1800cbcd5  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x1800cbcda  mov     cs:qword_18018B110, rsi
0x1800cbce1  test    rsi, rsi
0x1800cbce4  jz      short loc_1800CBD18
0x1800cbce6  mov     cs:dword_18018B1E0, 8000000Ah
0x1800cbcf0  mov     rcx, rsi; hEvent
0x1800cbcf3  call    cs:__imp_ResetEvent
0x1800cbcf9  xor     r9d, r9d; pfnCallback
0x1800cbcfc  lea     r8d, [r9+4]; flags
0x1800cbd00  lea     rdx, ?g_backgroundPermissionSingleton@StorageSenseHandlers@SystemSettings@@3V?$CSingletonHelper@W4BackgroundPermission@StorageSenseHandlers@SystemSettings@@@DataModel@2@A; pData
0x1800cbd07  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@AEBV?$shared_ptr@UCleanupListHandlerEvent@StorageSenseHandlers@SystemSettings@@@std@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x1800cbd0e  call    cs:__imp_SHCreateThread
0x1800cbd14  test    eax, eax
0x1800cbd16  jnz     short loc_1800CBD20
0x1800cbd18  mov     dil, 1
0x1800cbd1b  mov     byte ptr [rsp+58h+arg_0], dil
0x1800cbd20  mov     r8b, 3
0x1800cbd23  mov     dl, 1
0x1800cbd25  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x1800cbd2c  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800cbd31  nop
0x1800cbd32  lea     rcx, [rsp+58h+arg_18]; this
0x1800cbd37  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800cbd3c  lea     rsi, stru_18018B1A0
0x1800cbd43  mov     rcx, rsi; lpCriticalSection
0x1800cbd46  call    cs:__imp_EnterCriticalSection
0x1800cbd4c  mov     [rsp+58h+dwindex], rsi
0x1800cbd51  mov     r8b, 3
0x1800cbd54  mov     dl, 1
0x1800cbd56  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x1800cbd5d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800cbd62  nop
0x1800cbd63  lea     r8, [rsp+58h+arg_8]
0x1800cbd68  lea     rdx, [rsp+58h+var_28]
0x1800cbd6d  lea     rcx, qword_18018B128
0x1800cbd74  call    ??$emplace@AEBQEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback * const &)
0x1800cbd79  nop
0x1800cbd7a  jmp     short loc_1800CBD81
0x1800cbd7c  mov     dil, byte ptr [rsp+58h+arg_0]
0x1800cbd81  lock dec cs:dword_18018B198
0x1800cbd88  mov     r8b, 3
0x1800cbd8b  mov     dl, 1
0x1800cbd8d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x1800cbd94  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800cbd99  nop
0x1800cbd9a  lea     rcx, [rsp+58h+dwindex]; this
0x1800cbd9f  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800cbda4  test    dil, dil
0x1800cbda7  jz      short loc_1800CBDB5
0x1800cbda9  lea     rcx, ?g_backgroundPermissionSingleton@StorageSenseHandlers@SystemSettings@@3V?$CSingletonHelper@W4BackgroundPermission@StorageSenseHandlers@SystemSettings@@@DataModel@2@A; SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::BackgroundPermission> SystemSettings::StorageSenseHandlers::g_backgroundPermissionSingleton
0x1800cbdb0  call    ?_Initialization@?$CSingletonHelper@PEAUAppListChangeNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::_Initialization(void)
0x1800cbdb5  add     rsp, 48h
0x1800cbdb9  pop     rdi
0x1800cbdba  pop     rsi
0x1800cbdbb  retn
```
