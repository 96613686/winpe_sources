# SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::Register(SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::CCallback *)

- ea: `0x180026984`
- end: `0x180026b40`
- name: `?Register@?$CSingletonHelper@W4_BATTERY_STATE@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `444`
- prototype: ``
- caller_count: `20`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019284`
- `0x1800195a0`
- `0x180019630`
- `0x180019784`
- `0x180019a64`
- `0x180024b60`
- `0x180024c50`
- `0x180024cb0`
- `0x180024d90`
- `0x180024e40`
- `0x18002cc40`
- `0x18002f4d0`
- `0x18003abe0`
- `0x18003b0a8`
- `0x18003b340`
- `0x18003b87c`
- `0x18003c090`
- `0x18003ce80`
- `0x18003dde0`
- `0x180046914`

## callees

- `0x180011a54`
- `0x180012c58`
- `0x18001314c`
- `0x180026984`
- `0x180026bf0`
- `0x18002adc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180026a49`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180026a49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800269a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026aca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800269a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026aca`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180026a77`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180026a77`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800269f1`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800269f1`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180026a92`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180026a92`

## pseudocode

```c
void __fastcall SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::Register(
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
  EnterCriticalSection(&stru_1800662C0);
  v15 = &stru_1800662C0;
  _InterlockedIncrement(&dword_1800662E8);
  if ( byte_180066320 && qword_180066318 )
  {
    LODWORD(dwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &qword_180066318, (LPDWORD)&dwindex);
  }
  LOBYTE(v4) = 3;
  LOBYTE(v3) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v3,
    v4);
  if ( !byte_1800662BA && !(_BYTE)word_1800662B8 )
  {
    if ( (LOBYTE(word_1800662B8) = 1, !dword_180066258)
      || (EventW = pHandles) == 0
      && (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&pHandles),
          (pHandles = EventW) == 0)
      || (dword_180066330 = -2147483638,
          ResetEvent(EventW),
          !SHCreateThread(
             SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::s_InitializationThread,
             &SystemSettings::BatterySaverOneCoreDataModel::g_CBatteryStateSingleton,
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
  EnterCriticalSection(&stru_1800662F0);
  dwindex = &stru_1800662F0;
  LOBYTE(v8) = 3;
  LOBYTE(v9) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v9,
    v8);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback * const &>(
    (float *)qword_180066278,
    (__int64)v12,
    (unsigned __int8 *)&v13);
  _InterlockedDecrement(&dword_1800662E8);
  LOBYTE(v10) = 3;
  LOBYTE(v11) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v11,
    v10);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&dwindex);
  if ( v2 )
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::_Initialization(&SystemSettings::BatterySaverOneCoreDataModel::g_CBatteryStateSingleton);
}

```

## disassembly

```asm
0x180026984  mov     [rsp+arg_8], rdx
0x180026989  mov     [rsp+arg_0], rcx
0x18002698e  push    rsi
0x18002698f  push    rdi
0x180026990  sub     rsp, 48h
0x180026994  xor     dil, dil
0x180026997  mov     byte ptr [rsp+58h+arg_0], dil
0x18002699c  lea     rsi, stru_1800662C0
0x1800269a3  mov     rcx, rsi; lpCriticalSection
0x1800269a6  call    cs:__imp_EnterCriticalSection
0x1800269ac  mov     [rsp+58h+arg_18], rsi
0x1800269b1  lock inc cs:dword_1800662E8
0x1800269b8  cmp     cs:byte_180066320, dil
0x1800269bf  jz      short loc_1800269F7
0x1800269c1  cmp     cs:qword_180066318, 0
0x1800269c9  jz      short loc_1800269F7
0x1800269cb  mov     dword ptr [rsp+58h+dwindex], 0
0x1800269d3  lea     rax, [rsp+58h+dwindex]
0x1800269d8  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x1800269dd  lea     r9, qword_180066318; pHandles
0x1800269e4  mov     r8d, 1; cHandles
0x1800269ea  or      edx, 0FFFFFFFFh; dwTimeout
0x1800269ed  lea     ecx, [r8+7]; dwFlags
0x1800269f1  call    cs:__imp_CoWaitForMultipleHandles
0x1800269f7  mov     r8b, 3
0x1800269fa  mov     dl, 1
0x1800269fc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180026a03  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180026a08  cmp     cs:byte_1800662BA, 0
0x180026a0f  jnz     loc_180026AA4
0x180026a15  cmp     byte ptr cs:word_1800662B8, 0
0x180026a1c  jnz     loc_180026AA4
0x180026a22  mov     byte ptr cs:word_1800662B8, 1
0x180026a29  cmp     cs:dword_180066258, 0
0x180026a30  jz      short loc_180026A9C
0x180026a32  mov     rsi, cs:pHandles
0x180026a39  test    rsi, rsi
0x180026a3c  jnz     short loc_180026A6A
0x180026a3e  xor     r9d, r9d; lpName
0x180026a41  xor     r8d, r8d; bInitialState
0x180026a44  lea     edx, [rsi+1]; bManualReset
0x180026a47  xor     ecx, ecx; lpEventAttributes
0x180026a49  call    cs:__imp_CreateEventW
0x180026a4f  mov     rsi, rax
0x180026a52  lea     rcx, pHandles
0x180026a59  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180026a5e  mov     cs:pHandles, rsi
0x180026a65  test    rsi, rsi
0x180026a68  jz      short loc_180026A9C
0x180026a6a  mov     cs:dword_180066330, 8000000Ah
0x180026a74  mov     rcx, rsi; hEvent
0x180026a77  call    cs:__imp_ResetEvent
0x180026a7d  xor     r9d, r9d; pfnCallback
0x180026a80  lea     r8d, [r9+4]; flags
0x180026a84  lea     rdx, ?g_CBatteryStateSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCBatteryStateSingleton@12@A; pData
0x180026a8b  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@W4BatterySaverCallbackSetting@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x180026a92  call    cs:__imp_SHCreateThread
0x180026a98  test    eax, eax
0x180026a9a  jnz     short loc_180026AA4
0x180026a9c  mov     dil, 1
0x180026a9f  mov     byte ptr [rsp+58h+arg_0], dil
0x180026aa4  mov     r8b, 3
0x180026aa7  mov     dl, 1
0x180026aa9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180026ab0  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180026ab5  nop
0x180026ab6  lea     rcx, [rsp+58h+arg_18]; this
0x180026abb  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180026ac0  lea     rsi, stru_1800662F0
0x180026ac7  mov     rcx, rsi; lpCriticalSection
0x180026aca  call    cs:__imp_EnterCriticalSection
0x180026ad0  mov     [rsp+58h+dwindex], rsi
0x180026ad5  mov     r8b, 3
0x180026ad8  mov     dl, 1
0x180026ada  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180026ae1  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180026ae6  nop
0x180026ae7  lea     r8, [rsp+58h+arg_8]
0x180026aec  lea     rdx, [rsp+58h+var_28]
0x180026af1  lea     rcx, qword_180066278
0x180026af8  call    ??$emplace@AEBQEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback * const &)
0x180026afd  nop
0x180026afe  jmp     short loc_180026B05
0x180026b00  mov     dil, byte ptr [rsp+58h+arg_0]
0x180026b05  lock dec cs:dword_1800662E8
0x180026b0c  mov     r8b, 3
0x180026b0f  mov     dl, 1
0x180026b11  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180026b18  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180026b1d  nop
0x180026b1e  lea     rcx, [rsp+58h+dwindex]; this
0x180026b23  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180026b28  test    dil, dil
0x180026b2b  jz      short loc_180026B39
0x180026b2d  lea     rcx, ?g_CBatteryStateSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCBatteryStateSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CBatteryStateSingleton SystemSettings::BatterySaverOneCoreDataModel::g_CBatteryStateSingleton
0x180026b34  call    ?_Initialization@?$CSingletonHelper@W4_BATTERY_STATE@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::_Initialization(void)
0x180026b39  add     rsp, 48h
0x180026b3d  pop     rdi
0x180026b3e  pop     rsi
0x180026b3f  retn
```
