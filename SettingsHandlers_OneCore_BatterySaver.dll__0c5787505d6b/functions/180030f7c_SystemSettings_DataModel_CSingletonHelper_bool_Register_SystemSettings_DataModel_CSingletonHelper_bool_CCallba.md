# SystemSettings::DataModel::CSingletonHelper<bool>::Register(SystemSettings::DataModel::CSingletonHelper<bool>::CCallback *)

- ea: `0x180030f7c`
- end: `0x180031138`
- name: `?Register@?$CSingletonHelper@_N@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `444`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800305f4`
- `0x180030f30`

## callees

- `0x180012c58`
- `0x18001314c`
- `0x180017c6c`
- `0x180026bf0`
- `0x18002adc8`
- `0x180030f7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180031041`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180031041`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030f9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800310c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030f9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800310c2`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003106f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003106f`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180030fe9`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180030fe9`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18003108a`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18003108a`

## pseudocode

```c
void __fastcall SystemSettings::DataModel::CSingletonHelper<bool>::Register(__int64 a1, __int64 a2)
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
  EnterCriticalSection(&stru_180065AB0);
  v15 = &stru_180065AB0;
  _InterlockedIncrement(&dword_180065AD8);
  if ( byte_180065B10 && qword_180065B08 )
  {
    LODWORD(dwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &qword_180065B08, (LPDWORD)&dwindex);
  }
  LOBYTE(v4) = 3;
  LOBYTE(v3) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v3,
    v4);
  if ( !byte_180065AAA && !(_BYTE)word_180065AA8 )
  {
    if ( (LOBYTE(word_180065AA8) = 1, !dword_180065A48)
      || (EventW = qword_180065A50) == 0
      && (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&qword_180065A50),
          (qword_180065A50 = EventW) == 0)
      || (dword_180065B20 = -2147483638,
          ResetEvent(EventW),
          !SHCreateThread(
             SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::s_InitializationThread,
             &SystemSettings::BatterySaverOneCoreDataModel::g_CBatteryPercentageToggleSingleton,
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
  EnterCriticalSection(&stru_180065AE0);
  dwindex = &stru_180065AE0;
  LOBYTE(v8) = 3;
  LOBYTE(v9) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v9,
    v8);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback * const &>(
    (float *)&qword_180065A68,
    (__int64)v12,
    (unsigned __int8 *)&v13);
  _InterlockedDecrement(&dword_180065AD8);
  LOBYTE(v10) = 3;
  LOBYTE(v11) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v11,
    v10);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&dwindex);
  if ( v2 )
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::_Initialization(&SystemSettings::BatterySaverOneCoreDataModel::g_CBatteryPercentageToggleSingleton);
}

```

## disassembly

```asm
0x180030f7c  mov     [rsp+arg_8], rdx
0x180030f81  mov     [rsp+arg_0], rcx
0x180030f86  push    rsi
0x180030f87  push    rdi
0x180030f88  sub     rsp, 48h
0x180030f8c  xor     dil, dil
0x180030f8f  mov     byte ptr [rsp+58h+arg_0], dil
0x180030f94  lea     rsi, stru_180065AB0
0x180030f9b  mov     rcx, rsi; lpCriticalSection
0x180030f9e  call    cs:__imp_EnterCriticalSection
0x180030fa4  mov     [rsp+58h+arg_18], rsi
0x180030fa9  lock inc cs:dword_180065AD8
0x180030fb0  cmp     cs:byte_180065B10, dil
0x180030fb7  jz      short loc_180030FEF
0x180030fb9  cmp     cs:qword_180065B08, 0
0x180030fc1  jz      short loc_180030FEF
0x180030fc3  mov     dword ptr [rsp+58h+dwindex], 0
0x180030fcb  lea     rax, [rsp+58h+dwindex]
0x180030fd0  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x180030fd5  lea     r9, qword_180065B08; pHandles
0x180030fdc  mov     r8d, 1; cHandles
0x180030fe2  or      edx, 0FFFFFFFFh; dwTimeout
0x180030fe5  lea     ecx, [r8+7]; dwFlags
0x180030fe9  call    cs:__imp_CoWaitForMultipleHandles
0x180030fef  mov     r8b, 3
0x180030ff2  mov     dl, 1
0x180030ff4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180030ffb  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180031000  cmp     cs:byte_180065AAA, 0
0x180031007  jnz     loc_18003109C
0x18003100d  cmp     byte ptr cs:word_180065AA8, 0
0x180031014  jnz     loc_18003109C
0x18003101a  mov     byte ptr cs:word_180065AA8, 1
0x180031021  cmp     cs:dword_180065A48, 0
0x180031028  jz      short loc_180031094
0x18003102a  mov     rsi, cs:qword_180065A50
0x180031031  test    rsi, rsi
0x180031034  jnz     short loc_180031062
0x180031036  xor     r9d, r9d; lpName
0x180031039  xor     r8d, r8d; bInitialState
0x18003103c  lea     edx, [rsi+1]; bManualReset
0x18003103f  xor     ecx, ecx; lpEventAttributes
0x180031041  call    cs:__imp_CreateEventW
0x180031047  mov     rsi, rax
0x18003104a  lea     rcx, qword_180065A50
0x180031051  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180031056  mov     cs:qword_180065A50, rsi
0x18003105d  test    rsi, rsi
0x180031060  jz      short loc_180031094
0x180031062  mov     cs:dword_180065B20, 8000000Ah
0x18003106c  mov     rcx, rsi; hEvent
0x18003106f  call    cs:__imp_ResetEvent
0x180031075  xor     r9d, r9d; pfnCallback
0x180031078  lea     r8d, [r9+4]; flags
0x18003107c  lea     rdx, ?g_CBatteryPercentageToggleSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCBatteryPercentageToggleSingleton@12@A; pData
0x180031083  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@W4BatterySaverCallbackSetting@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x18003108a  call    cs:__imp_SHCreateThread
0x180031090  test    eax, eax
0x180031092  jnz     short loc_18003109C
0x180031094  mov     dil, 1
0x180031097  mov     byte ptr [rsp+58h+arg_0], dil
0x18003109c  mov     r8b, 3
0x18003109f  mov     dl, 1
0x1800310a1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x1800310a8  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800310ad  nop
0x1800310ae  lea     rcx, [rsp+58h+arg_18]; this
0x1800310b3  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800310b8  lea     rsi, stru_180065AE0
0x1800310bf  mov     rcx, rsi; lpCriticalSection
0x1800310c2  call    cs:__imp_EnterCriticalSection
0x1800310c8  mov     [rsp+58h+dwindex], rsi
0x1800310cd  mov     r8b, 3
0x1800310d0  mov     dl, 1
0x1800310d2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x1800310d9  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800310de  nop
0x1800310df  lea     r8, [rsp+58h+arg_8]
0x1800310e4  lea     rdx, [rsp+58h+var_28]
0x1800310e9  lea     rcx, qword_180065A68
0x1800310f0  call    ??$emplace@AEBQEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback * const &)
0x1800310f5  nop
0x1800310f6  jmp     short loc_1800310FD
0x1800310f8  mov     dil, byte ptr [rsp+58h+arg_0]
0x1800310fd  lock dec cs:dword_180065AD8
0x180031104  mov     r8b, 3
0x180031107  mov     dl, 1
0x180031109  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180031110  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180031115  nop
0x180031116  lea     rcx, [rsp+58h+dwindex]; this
0x18003111b  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180031120  test    dil, dil
0x180031123  jz      short loc_180031131
0x180031125  lea     rcx, ?g_CBatteryPercentageToggleSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCBatteryPercentageToggleSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CBatteryPercentageToggleSingleton SystemSettings::BatterySaverOneCoreDataModel::g_CBatteryPercentageToggleSingleton
0x18003112c  call    ?_Initialization@?$CSingletonHelper@W4_BATTERY_STATE@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::_Initialization(void)
0x180031131  add     rsp, 48h
0x180031135  pop     rdi
0x180031136  pop     rsi
0x180031137  retn
```
