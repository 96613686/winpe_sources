# SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::BreakdownCollectionFilter>::Register(SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::BreakdownCollectionFilter>::CCallback *)

- ea: `0x180059cb4`
- end: `0x180059e70`
- name: `?Register@?$CSingletonHelper@W4BreakdownCollectionFilter@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004f0a8`

## callees

- `0x18001f53c`
- `0x180027bc8`
- `0x1800323d0`
- `0x180032cd0`
- `0x180034afc`
- `0x180059cb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059cd6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059dfa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059cd6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059dfa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180059d79`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180059d79`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180059da7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180059da7`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180059d21`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180059d21`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180059dc2`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180059dc2`

## pseudocode

```c
void __fastcall SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::StorageSenseHandlers::BreakdownCollectionFilter>::Register(
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
  EnterCriticalSection(&stru_18018A7E0);
  v15 = &stru_18018A7E0;
  _InterlockedIncrement(&dword_18018A808);
  if ( byte_18018A840 && qword_18018A838 )
  {
    LODWORD(dwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &qword_18018A838, (LPDWORD)&dwindex);
  }
  LOBYTE(v4) = 3;
  LOBYTE(v3) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v3,
    v4);
  if ( !byte_18018A7DA && !(_BYTE)word_18018A7D8 )
  {
    if ( (LOBYTE(word_18018A7D8) = 1, !dword_18018A778)
      || (EventW = qword_18018A780) == 0
      && (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&qword_18018A780),
          (qword_18018A780 = EventW) == 0)
      || (dword_18018A850 = -2147483638,
          ResetEvent(EventW),
          !SHCreateThread(
             SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::s_InitializationThread,
             &SystemSettings::StorageSenseHandlers::breakdownFilterSingleton,
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
  EnterCriticalSection(&stru_18018A810);
  dwindex = &stru_18018A810;
  LOBYTE(v8) = 3;
  LOBYTE(v9) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v9,
    v8);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback * const &>(
    (float *)&qword_18018A798,
    (__int64)v12,
    (unsigned __int8 *)&v13);
  _InterlockedDecrement(&dword_18018A808);
  LOBYTE(v10) = 3;
  LOBYTE(v11) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v11,
    v10);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&dwindex);
  if ( v2 )
    SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::_Initialization(&SystemSettings::StorageSenseHandlers::breakdownFilterSingleton);
}

```

## disassembly

```asm
0x180059cb4  mov     [rsp+arg_8], rdx
0x180059cb9  mov     [rsp+arg_0], rcx
0x180059cbe  push    rsi
0x180059cbf  push    rdi
0x180059cc0  sub     rsp, 48h
0x180059cc4  xor     dil, dil
0x180059cc7  mov     byte ptr [rsp+58h+arg_0], dil
0x180059ccc  lea     rsi, stru_18018A7E0
0x180059cd3  mov     rcx, rsi; lpCriticalSection
0x180059cd6  call    cs:__imp_EnterCriticalSection
0x180059cdc  mov     [rsp+58h+arg_18], rsi
0x180059ce1  lock inc cs:dword_18018A808
0x180059ce8  cmp     cs:byte_18018A840, dil
0x180059cef  jz      short loc_180059D27
0x180059cf1  cmp     cs:qword_18018A838, 0
0x180059cf9  jz      short loc_180059D27
0x180059cfb  mov     dword ptr [rsp+58h+dwindex], 0
0x180059d03  lea     rax, [rsp+58h+dwindex]
0x180059d08  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x180059d0d  lea     r9, qword_18018A838; pHandles
0x180059d14  mov     r8d, 1; cHandles
0x180059d1a  or      edx, 0FFFFFFFFh; dwTimeout
0x180059d1d  lea     ecx, [r8+7]; dwFlags
0x180059d21  call    cs:__imp_CoWaitForMultipleHandles
0x180059d27  mov     r8b, 3
0x180059d2a  mov     dl, 1
0x180059d2c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180059d33  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180059d38  cmp     cs:byte_18018A7DA, 0
0x180059d3f  jnz     loc_180059DD4
0x180059d45  cmp     byte ptr cs:word_18018A7D8, 0
0x180059d4c  jnz     loc_180059DD4
0x180059d52  mov     byte ptr cs:word_18018A7D8, 1
0x180059d59  cmp     cs:dword_18018A778, 0
0x180059d60  jz      short loc_180059DCC
0x180059d62  mov     rsi, cs:qword_18018A780
0x180059d69  test    rsi, rsi
0x180059d6c  jnz     short loc_180059D9A
0x180059d6e  xor     r9d, r9d; lpName
0x180059d71  xor     r8d, r8d; bInitialState
0x180059d74  lea     edx, [rsi+1]; bManualReset
0x180059d77  xor     ecx, ecx; lpEventAttributes
0x180059d79  call    cs:__imp_CreateEventW
0x180059d7f  mov     rsi, rax
0x180059d82  lea     rcx, qword_18018A780
0x180059d89  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180059d8e  mov     cs:qword_18018A780, rsi
0x180059d95  test    rsi, rsi
0x180059d98  jz      short loc_180059DCC
0x180059d9a  mov     cs:dword_18018A850, 8000000Ah
0x180059da4  mov     rcx, rsi; hEvent
0x180059da7  call    cs:__imp_ResetEvent
0x180059dad  xor     r9d, r9d; pfnCallback
0x180059db0  lea     r8d, [r9+4]; flags
0x180059db4  lea     rdx, ?breakdownFilterSingleton@StorageSenseHandlers@SystemSettings@@3VCBreakdownCollectionFilterSingleton@12@A; pData
0x180059dbb  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@AEBV?$shared_ptr@UCleanupListHandlerEvent@StorageSenseHandlers@SystemSettings@@@std@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x180059dc2  call    cs:__imp_SHCreateThread
0x180059dc8  test    eax, eax
0x180059dca  jnz     short loc_180059DD4
0x180059dcc  mov     dil, 1
0x180059dcf  mov     byte ptr [rsp+58h+arg_0], dil
0x180059dd4  mov     r8b, 3
0x180059dd7  mov     dl, 1
0x180059dd9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180059de0  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180059de5  nop
0x180059de6  lea     rcx, [rsp+58h+arg_18]; this
0x180059deb  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180059df0  lea     rsi, stru_18018A810
0x180059df7  mov     rcx, rsi; lpCriticalSection
0x180059dfa  call    cs:__imp_EnterCriticalSection
0x180059e00  mov     [rsp+58h+dwindex], rsi
0x180059e05  mov     r8b, 3
0x180059e08  mov     dl, 1
0x180059e0a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180059e11  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180059e16  nop
0x180059e17  lea     r8, [rsp+58h+arg_8]
0x180059e1c  lea     rdx, [rsp+58h+var_28]
0x180059e21  lea     rcx, qword_18018A798
0x180059e28  call    ??$emplace@AEBQEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback * const &)
0x180059e2d  nop
0x180059e2e  jmp     short loc_180059E35
0x180059e30  mov     dil, byte ptr [rsp+58h+arg_0]
0x180059e35  lock dec cs:dword_18018A808
0x180059e3c  mov     r8b, 3
0x180059e3f  mov     dl, 1
0x180059e41  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180059e48  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180059e4d  nop
0x180059e4e  lea     rcx, [rsp+58h+dwindex]; this
0x180059e53  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180059e58  test    dil, dil
0x180059e5b  jz      short loc_180059E69
0x180059e5d  lea     rcx, ?breakdownFilterSingleton@StorageSenseHandlers@SystemSettings@@3VCBreakdownCollectionFilterSingleton@12@A; SystemSettings::StorageSenseHandlers::CBreakdownCollectionFilterSingleton SystemSettings::StorageSenseHandlers::breakdownFilterSingleton
0x180059e64  call    ?_Initialization@?$CSingletonHelper@PEAUAppListChangeNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::_Initialization(void)
0x180059e69  add     rsp, 48h
0x180059e6d  pop     rdi
0x180059e6e  pop     rsi
0x180059e6f  retn
```
