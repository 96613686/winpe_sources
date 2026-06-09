# SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::StorSvcHandlerNotification>::Register(SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::StorSvcHandlerNotification>::CCallback *)

- ea: `0x180059af0`
- end: `0x180059cac`
- name: `?Register@?$CSingletonHelper@UStorSvcHandlerNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `444`
- prototype: ``
- caller_count: `14`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004f030`
- `0x18004f0a8`
- `0x180050fb8`
- `0x180051084`
- `0x1800511fc`
- `0x180051368`
- `0x180051544`
- `0x18005162c`
- `0x180054810`
- `0x18007d2f8`
- `0x18008251c`
- `0x180082680`
- `0x180082fec`
- `0x180084a98`

## callees

- `0x18001f53c`
- `0x180027bc8`
- `0x1800323d0`
- `0x180032cd0`
- `0x180034afc`
- `0x180059af0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059b12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059c36`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059b12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059c36`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180059bb5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180059bb5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180059be3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180059be3`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180059b5d`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180059b5d`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180059bfe`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180059bfe`

## pseudocode

```c
void __fastcall SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::StorSvcHandlerNotification>::Register(
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
  EnterCriticalSection(&stru_18018AE50);
  v15 = &stru_18018AE50;
  _InterlockedIncrement(&dword_18018AE78);
  if ( byte_18018AEB0 && qword_18018AEA8 )
  {
    LODWORD(dwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &qword_18018AEA8, (LPDWORD)&dwindex);
  }
  LOBYTE(v4) = 3;
  LOBYTE(v3) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v3,
    v4);
  if ( !byte_18018AE4A && !(_BYTE)word_18018AE48 )
  {
    if ( (LOBYTE(word_18018AE48) = 1, !dword_18018ADE8)
      || (EventW = qword_18018ADF0) == 0
      && (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&qword_18018ADF0),
          (qword_18018ADF0 = EventW) == 0)
      || (dword_18018AEC0 = -2147483638,
          ResetEvent(EventW),
          !SHCreateThread(
             SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::s_InitializationThread,
             &SystemSettings::StorageSenseHandlers::g_storSvcHandler,
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
  EnterCriticalSection(&stru_18018AE80);
  dwindex = &stru_18018AE80;
  LOBYTE(v8) = 3;
  LOBYTE(v9) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v9,
    v8);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback * const &>(
    (float *)&qword_18018AE08,
    (__int64)v12,
    (unsigned __int8 *)&v13);
  _InterlockedDecrement(&dword_18018AE78);
  LOBYTE(v10) = 3;
  LOBYTE(v11) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v11,
    v10);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&dwindex);
  if ( v2 )
    SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::_Initialization(&SystemSettings::StorageSenseHandlers::g_storSvcHandler);
}

```

## disassembly

```asm
0x180059af0  mov     [rsp+arg_8], rdx
0x180059af5  mov     [rsp+arg_0], rcx
0x180059afa  push    rsi
0x180059afb  push    rdi
0x180059afc  sub     rsp, 48h
0x180059b00  xor     dil, dil
0x180059b03  mov     byte ptr [rsp+58h+arg_0], dil
0x180059b08  lea     rsi, stru_18018AE50
0x180059b0f  mov     rcx, rsi; lpCriticalSection
0x180059b12  call    cs:__imp_EnterCriticalSection
0x180059b18  mov     [rsp+58h+arg_18], rsi
0x180059b1d  lock inc cs:dword_18018AE78
0x180059b24  cmp     cs:byte_18018AEB0, dil
0x180059b2b  jz      short loc_180059B63
0x180059b2d  cmp     cs:qword_18018AEA8, 0
0x180059b35  jz      short loc_180059B63
0x180059b37  mov     dword ptr [rsp+58h+dwindex], 0
0x180059b3f  lea     rax, [rsp+58h+dwindex]
0x180059b44  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x180059b49  lea     r9, qword_18018AEA8; pHandles
0x180059b50  mov     r8d, 1; cHandles
0x180059b56  or      edx, 0FFFFFFFFh; dwTimeout
0x180059b59  lea     ecx, [r8+7]; dwFlags
0x180059b5d  call    cs:__imp_CoWaitForMultipleHandles
0x180059b63  mov     r8b, 3
0x180059b66  mov     dl, 1
0x180059b68  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180059b6f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180059b74  cmp     cs:byte_18018AE4A, 0
0x180059b7b  jnz     loc_180059C10
0x180059b81  cmp     byte ptr cs:word_18018AE48, 0
0x180059b88  jnz     loc_180059C10
0x180059b8e  mov     byte ptr cs:word_18018AE48, 1
0x180059b95  cmp     cs:dword_18018ADE8, 0
0x180059b9c  jz      short loc_180059C08
0x180059b9e  mov     rsi, cs:qword_18018ADF0
0x180059ba5  test    rsi, rsi
0x180059ba8  jnz     short loc_180059BD6
0x180059baa  xor     r9d, r9d; lpName
0x180059bad  xor     r8d, r8d; bInitialState
0x180059bb0  lea     edx, [rsi+1]; bManualReset
0x180059bb3  xor     ecx, ecx; lpEventAttributes
0x180059bb5  call    cs:__imp_CreateEventW
0x180059bbb  mov     rsi, rax
0x180059bbe  lea     rcx, qword_18018ADF0
0x180059bc5  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180059bca  mov     cs:qword_18018ADF0, rsi
0x180059bd1  test    rsi, rsi
0x180059bd4  jz      short loc_180059C08
0x180059bd6  mov     cs:dword_18018AEC0, 8000000Ah
0x180059be0  mov     rcx, rsi; hEvent
0x180059be3  call    cs:__imp_ResetEvent
0x180059be9  xor     r9d, r9d; pfnCallback
0x180059bec  lea     r8d, [r9+4]; flags
0x180059bf0  lea     rdx, ?g_storSvcHandler@StorageSenseHandlers@SystemSettings@@3VCStorSvcHandler@12@A; pData
0x180059bf7  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@AEBV?$shared_ptr@UCleanupListHandlerEvent@StorageSenseHandlers@SystemSettings@@@std@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x180059bfe  call    cs:__imp_SHCreateThread
0x180059c04  test    eax, eax
0x180059c06  jnz     short loc_180059C10
0x180059c08  mov     dil, 1
0x180059c0b  mov     byte ptr [rsp+58h+arg_0], dil
0x180059c10  mov     r8b, 3
0x180059c13  mov     dl, 1
0x180059c15  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180059c1c  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180059c21  nop
0x180059c22  lea     rcx, [rsp+58h+arg_18]; this
0x180059c27  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180059c2c  lea     rsi, stru_18018AE80
0x180059c33  mov     rcx, rsi; lpCriticalSection
0x180059c36  call    cs:__imp_EnterCriticalSection
0x180059c3c  mov     [rsp+58h+dwindex], rsi
0x180059c41  mov     r8b, 3
0x180059c44  mov     dl, 1
0x180059c46  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180059c4d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180059c52  nop
0x180059c53  lea     r8, [rsp+58h+arg_8]
0x180059c58  lea     rdx, [rsp+58h+var_28]
0x180059c5d  lea     rcx, qword_18018AE08
0x180059c64  call    ??$emplace@AEBQEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback * const &)
0x180059c69  nop
0x180059c6a  jmp     short loc_180059C71
0x180059c6c  mov     dil, byte ptr [rsp+58h+arg_0]
0x180059c71  lock dec cs:dword_18018AE78
0x180059c78  mov     r8b, 3
0x180059c7b  mov     dl, 1
0x180059c7d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180059c84  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180059c89  nop
0x180059c8a  lea     rcx, [rsp+58h+dwindex]; this
0x180059c8f  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180059c94  test    dil, dil
0x180059c97  jz      short loc_180059CA5
0x180059c99  lea     rcx, ?g_storSvcHandler@StorageSenseHandlers@SystemSettings@@3VCStorSvcHandler@12@A; SystemSettings::StorageSenseHandlers::CStorSvcHandler SystemSettings::StorageSenseHandlers::g_storSvcHandler
0x180059ca0  call    ?_Initialization@?$CSingletonHelper@PEAUAppListChangeNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::_Initialization(void)
0x180059ca5  add     rsp, 48h
0x180059ca9  pop     rdi
0x180059caa  pop     rsi
0x180059cab  retn
```
