# SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::Register(SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *)

- ea: `0x180036c94`
- end: `0x180036e50`
- name: `?Register@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `444`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180033be0`
- `0x180036630`

## callees

- `0x180012c58`
- `0x18001314c`
- `0x180017c6c`
- `0x180026bf0`
- `0x18002adc8`
- `0x180036c94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180036d59`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180036d59`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036cb6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036dda`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036cb6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036dda`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180036d87`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180036d87`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180036d01`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180036d01`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180036da2`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180036da2`

## pseudocode

```c
void __fastcall SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::Register(
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
  EnterCriticalSection(&stru_180065C90);
  v15 = &stru_180065C90;
  _InterlockedIncrement(&dword_180065CB8);
  if ( byte_180065CF0 && qword_180065CE8 )
  {
    LODWORD(dwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &qword_180065CE8, (LPDWORD)&dwindex);
  }
  LOBYTE(v4) = 3;
  LOBYTE(v3) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v3,
    v4);
  if ( !byte_180065C8A && !(_BYTE)word_180065C88 )
  {
    if ( (LOBYTE(word_180065C88) = 1, !dword_180065C28)
      || (EventW = qword_180065C30) == 0
      && (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&qword_180065C30),
          (qword_180065C30 = EventW) == 0)
      || (dword_180065D00 = -2147483638,
          ResetEvent(EventW),
          !SHCreateThread(
             SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::s_InitializationThread,
             &SystemSettings::BatterySaverOneCoreDataModel::g_CRenewableChargingStatusSingleton,
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
  EnterCriticalSection(&stru_180065CC0);
  dwindex = &stru_180065CC0;
  LOBYTE(v8) = 3;
  LOBYTE(v9) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v9,
    v8);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback * const &>(
    (float *)qword_180065C48,
    (__int64)v12,
    (unsigned __int8 *)&v13);
  _InterlockedDecrement(&dword_180065CB8);
  LOBYTE(v10) = 3;
  LOBYTE(v11) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v11,
    v10);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&dwindex);
  if ( v2 )
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::_Initialization(&SystemSettings::BatterySaverOneCoreDataModel::g_CRenewableChargingStatusSingleton);
}

```

## disassembly

```asm
0x180036c94  mov     [rsp+arg_8], rdx
0x180036c99  mov     [rsp+arg_0], rcx
0x180036c9e  push    rsi
0x180036c9f  push    rdi
0x180036ca0  sub     rsp, 48h
0x180036ca4  xor     dil, dil
0x180036ca7  mov     byte ptr [rsp+58h+arg_0], dil
0x180036cac  lea     rsi, stru_180065C90
0x180036cb3  mov     rcx, rsi; lpCriticalSection
0x180036cb6  call    cs:__imp_EnterCriticalSection
0x180036cbc  mov     [rsp+58h+arg_18], rsi
0x180036cc1  lock inc cs:dword_180065CB8
0x180036cc8  cmp     cs:byte_180065CF0, dil
0x180036ccf  jz      short loc_180036D07
0x180036cd1  cmp     cs:qword_180065CE8, 0
0x180036cd9  jz      short loc_180036D07
0x180036cdb  mov     dword ptr [rsp+58h+dwindex], 0
0x180036ce3  lea     rax, [rsp+58h+dwindex]
0x180036ce8  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x180036ced  lea     r9, qword_180065CE8; pHandles
0x180036cf4  mov     r8d, 1; cHandles
0x180036cfa  or      edx, 0FFFFFFFFh; dwTimeout
0x180036cfd  lea     ecx, [r8+7]; dwFlags
0x180036d01  call    cs:__imp_CoWaitForMultipleHandles
0x180036d07  mov     r8b, 3
0x180036d0a  mov     dl, 1
0x180036d0c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180036d13  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180036d18  cmp     cs:byte_180065C8A, 0
0x180036d1f  jnz     loc_180036DB4
0x180036d25  cmp     byte ptr cs:word_180065C88, 0
0x180036d2c  jnz     loc_180036DB4
0x180036d32  mov     byte ptr cs:word_180065C88, 1
0x180036d39  cmp     cs:dword_180065C28, 0
0x180036d40  jz      short loc_180036DAC
0x180036d42  mov     rsi, cs:qword_180065C30
0x180036d49  test    rsi, rsi
0x180036d4c  jnz     short loc_180036D7A
0x180036d4e  xor     r9d, r9d; lpName
0x180036d51  xor     r8d, r8d; bInitialState
0x180036d54  lea     edx, [rsi+1]; bManualReset
0x180036d57  xor     ecx, ecx; lpEventAttributes
0x180036d59  call    cs:__imp_CreateEventW
0x180036d5f  mov     rsi, rax
0x180036d62  lea     rcx, qword_180065C30
0x180036d69  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180036d6e  mov     cs:qword_180065C30, rsi
0x180036d75  test    rsi, rsi
0x180036d78  jz      short loc_180036DAC
0x180036d7a  mov     cs:dword_180065D00, 8000000Ah
0x180036d84  mov     rcx, rsi; hEvent
0x180036d87  call    cs:__imp_ResetEvent
0x180036d8d  xor     r9d, r9d; pfnCallback
0x180036d90  lea     r8d, [r9+4]; flags
0x180036d94  lea     rdx, ?g_CRenewableChargingStatusSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCRenewableChargingStatusSingleton@12@A; pData
0x180036d9b  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@W4BatterySaverCallbackSetting@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x180036da2  call    cs:__imp_SHCreateThread
0x180036da8  test    eax, eax
0x180036daa  jnz     short loc_180036DB4
0x180036dac  mov     dil, 1
0x180036daf  mov     byte ptr [rsp+58h+arg_0], dil
0x180036db4  mov     r8b, 3
0x180036db7  mov     dl, 1
0x180036db9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180036dc0  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180036dc5  nop
0x180036dc6  lea     rcx, [rsp+58h+arg_18]; this
0x180036dcb  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180036dd0  lea     rsi, stru_180065CC0
0x180036dd7  mov     rcx, rsi; lpCriticalSection
0x180036dda  call    cs:__imp_EnterCriticalSection
0x180036de0  mov     [rsp+58h+dwindex], rsi
0x180036de5  mov     r8b, 3
0x180036de8  mov     dl, 1
0x180036dea  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180036df1  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180036df6  nop
0x180036df7  lea     r8, [rsp+58h+arg_8]
0x180036dfc  lea     rdx, [rsp+58h+var_28]
0x180036e01  lea     rcx, qword_180065C48
0x180036e08  call    ??$emplace@AEBQEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback * const &)
0x180036e0d  nop
0x180036e0e  jmp     short loc_180036E15
0x180036e10  mov     dil, byte ptr [rsp+58h+arg_0]
0x180036e15  lock dec cs:dword_180065CB8
0x180036e1c  mov     r8b, 3
0x180036e1f  mov     dl, 1
0x180036e21  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180036e28  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180036e2d  nop
0x180036e2e  lea     rcx, [rsp+58h+dwindex]; this
0x180036e33  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180036e38  test    dil, dil
0x180036e3b  jz      short loc_180036E49
0x180036e3d  lea     rcx, ?g_CRenewableChargingStatusSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCRenewableChargingStatusSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CRenewableChargingStatusSingleton SystemSettings::BatterySaverOneCoreDataModel::g_CRenewableChargingStatusSingleton
0x180036e44  call    ?_Initialization@?$CSingletonHelper@W4_BATTERY_STATE@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::_Initialization(void)
0x180036e49  add     rsp, 48h
0x180036e4d  pop     rdi
0x180036e4e  pop     rsi
0x180036e4f  retn
```
