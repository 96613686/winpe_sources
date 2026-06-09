# SystemSettings::DataModel::CSingletonHelper<uint>::Register(SystemSettings::DataModel::CSingletonHelper<uint>::CCallback *)

- ea: `0x180026274`
- end: `0x180026430`
- name: `?Register@?$CSingletonHelper@I@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `444`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800191f4`
- `0x18002cc40`
- `0x18002f4d0`

## callees

- `0x180011a54`
- `0x180012c58`
- `0x18001314c`
- `0x180026274`
- `0x180026bf0`
- `0x18002adc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180026339`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180026339`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026296`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800263ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026296`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800263ba`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180026367`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180026367`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800262e1`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800262e1`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180026382`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180026382`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SystemSettings::DataModel::CSingletonHelper<unsigned int>::Register(__int64 a1, __int64 a2)
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
  EnterCriticalSection(&CriticalSection);
  v18 = &CriticalSection;
  _InterlockedIncrement(&dword_180065918);
  if ( byte_180065950 && qword_180065948 )
  {
    LODWORD(dwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &qword_180065948, (LPDWORD)&dwindex);
  }
  LOBYTE(v4) = 3;
  LOBYTE(v3) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v3,
    v4);
  if ( !byte_1800658EA && !(_BYTE)word_1800658E8 )
  {
    if ( (LOBYTE(word_1800658E8) = 1, !dword_180065888)
      || (EventW = hEvent) == 0
      && (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&hEvent),
          (hEvent = EventW) == 0)
      || (dword_180065960 = -2147483638,
          ResetEvent(EventW),
          !SHCreateThread(
             SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::s_InitializationThread,
             &SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverMultipleBatterySingleton,
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
  EnterCriticalSection(&stru_180065920);
  dwindex = &stru_180065920;
  LOBYTE(v8) = 3;
  LOBYTE(v9) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v9,
    v8);
  try
  {
    std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback * const &>(
      (float *)qword_1800658A8,
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
  _InterlockedDecrement(&dword_180065918);
  LOBYTE(v12) = 3;
  LOBYTE(v11) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v11,
    v12);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&dwindex);
  if ( v2 )
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::_Initialization(&SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverMultipleBatterySingleton);
}

```

## disassembly

```asm
0x180026274  mov     [rsp+arg_8], rdx
0x180026279  mov     [rsp+arg_0], rcx
0x18002627e  push    rsi
0x18002627f  push    rdi
0x180026280  sub     rsp, 48h
0x180026284  xor     dil, dil
0x180026287  mov     byte ptr [rsp+58h+arg_0], dil
0x18002628c  lea     rsi, CriticalSection
0x180026293  mov     rcx, rsi; lpCriticalSection
0x180026296  call    cs:__imp_EnterCriticalSection
0x18002629c  mov     [rsp+58h+arg_18], rsi
0x1800262a1  lock inc cs:dword_180065918
0x1800262a8  cmp     cs:byte_180065950, dil
0x1800262af  jz      short loc_1800262E7
0x1800262b1  cmp     cs:qword_180065948, 0
0x1800262b9  jz      short loc_1800262E7
0x1800262bb  mov     dword ptr [rsp+58h+dwindex], 0
0x1800262c3  lea     rax, [rsp+58h+dwindex]
0x1800262c8  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x1800262cd  lea     r9, qword_180065948; pHandles
0x1800262d4  mov     r8d, 1; cHandles
0x1800262da  or      edx, 0FFFFFFFFh; dwTimeout
0x1800262dd  lea     ecx, [r8+7]; dwFlags
0x1800262e1  call    cs:__imp_CoWaitForMultipleHandles
0x1800262e7  mov     r8b, 3
0x1800262ea  mov     dl, 1
0x1800262ec  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x1800262f3  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800262f8  cmp     cs:byte_1800658EA, 0
0x1800262ff  jnz     loc_180026394
0x180026305  cmp     byte ptr cs:word_1800658E8, 0
0x18002630c  jnz     loc_180026394
0x180026312  mov     byte ptr cs:word_1800658E8, 1
0x180026319  cmp     cs:dword_180065888, 0
0x180026320  jz      short loc_18002638C
0x180026322  mov     rsi, cs:hEvent
0x180026329  test    rsi, rsi
0x18002632c  jnz     short loc_18002635A
0x18002632e  xor     r9d, r9d; lpName
0x180026331  xor     r8d, r8d; bInitialState
0x180026334  lea     edx, [rsi+1]; bManualReset
0x180026337  xor     ecx, ecx; lpEventAttributes
0x180026339  call    cs:__imp_CreateEventW
0x18002633f  mov     rsi, rax
0x180026342  lea     rcx, hEvent
0x180026349  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18002634e  mov     cs:hEvent, rsi
0x180026355  test    rsi, rsi
0x180026358  jz      short loc_18002638C
0x18002635a  mov     cs:dword_180065960, 8000000Ah
0x180026364  mov     rcx, rsi; hEvent
0x180026367  call    cs:__imp_ResetEvent
0x18002636d  xor     r9d, r9d; pfnCallback
0x180026370  lea     r8d, [r9+4]; flags
0x180026374  lea     rdx, ?g_CBatterySaverMultipleBatterySingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCBatterySaverMultipleBatterySingleton@12@A; pData
0x18002637b  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@W4BatterySaverCallbackSetting@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x180026382  call    cs:__imp_SHCreateThread
0x180026388  test    eax, eax
0x18002638a  jnz     short loc_180026394
0x18002638c  mov     dil, 1
0x18002638f  mov     byte ptr [rsp+58h+arg_0], dil
0x180026394  mov     r8b, 3
0x180026397  mov     dl, 1
0x180026399  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x1800263a0  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800263a5  nop
0x1800263a6  lea     rcx, [rsp+58h+arg_18]; this
0x1800263ab  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800263b0  lea     rsi, stru_180065920
0x1800263b7  mov     rcx, rsi; lpCriticalSection
0x1800263ba  call    cs:__imp_EnterCriticalSection
0x1800263c0  mov     [rsp+58h+dwindex], rsi
0x1800263c5  mov     r8b, 3
0x1800263c8  mov     dl, 1
0x1800263ca  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x1800263d1  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800263d6  nop
0x1800263d7  lea     r8, [rsp+58h+arg_8]
0x1800263dc  lea     rdx, [rsp+58h+var_28]
0x1800263e1  lea     rcx, qword_1800658A8
0x1800263e8  call    ??$emplace@AEBQEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback * const &)
0x1800263ed  nop
0x1800263ee  jmp     short loc_1800263F5
0x1800263f0  mov     dil, byte ptr [rsp+58h+arg_0]
0x1800263f5  lock dec cs:dword_180065918
0x1800263fc  mov     r8b, 3
0x1800263ff  mov     dl, 1
0x180026401  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180026408  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002640d  nop
0x18002640e  lea     rcx, [rsp+58h+dwindex]; this
0x180026413  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180026418  test    dil, dil
0x18002641b  jz      short loc_180026429
0x18002641d  lea     rcx, ?g_CBatterySaverMultipleBatterySingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCBatterySaverMultipleBatterySingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverMultipleBatterySingleton SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverMultipleBatterySingleton
0x180026424  call    ?_Initialization@?$CSingletonHelper@W4_BATTERY_STATE@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::_Initialization(void)
0x180026429  add     rsp, 48h
0x18002642d  pop     rdi
0x18002642e  pop     rsi
0x18002642f  retn
```
