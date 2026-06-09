# SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_POWER_MODE_STATE>::Register(SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_POWER_MODE_STATE>::CCallback *)

- ea: `0x18003dfac`
- end: `0x18003e168`
- name: `?Register@?$CSingletonHelper@U_POWER_MODE_STATE@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `444`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003ce80`
- `0x18003dde0`

## callees

- `0x180011a54`
- `0x180012c58`
- `0x18001314c`
- `0x180026bf0`
- `0x18002adc8`
- `0x18003dfac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003e071`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003e071`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003dfce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e0f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003dfce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e0f2`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003e09f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003e09f`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18003e019`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18003e019`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18003e0ba`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18003e0ba`

## pseudocode

```c
void __fastcall SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_POWER_MODE_STATE>::Register(
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
  EnterCriticalSection(&stru_180065EA0);
  v15 = &stru_180065EA0;
  _InterlockedIncrement(&dword_180065EC8);
  if ( byte_180065F00 && qword_180065EF8 )
  {
    LODWORD(dwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &qword_180065EF8, (LPDWORD)&dwindex);
  }
  LOBYTE(v4) = 3;
  LOBYTE(v3) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v3,
    v4);
  if ( !byte_180065E9A && !(_BYTE)word_180065E98 )
  {
    if ( (LOBYTE(word_180065E98) = 1, !dword_180065E38)
      || (EventW = qword_180065E40) == 0
      && (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&qword_180065E40),
          (qword_180065E40 = EventW) == 0)
      || (dword_180065F10 = -2147483638,
          ResetEvent(EventW),
          !SHCreateThread(
             SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::s_InitializationThread,
             &SystemSettings::BatterySaverOneCoreDataModel::g_CPowerModeSingleton,
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
  EnterCriticalSection(&stru_180065ED0);
  dwindex = &stru_180065ED0;
  LOBYTE(v8) = 3;
  LOBYTE(v9) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v9,
    v8);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback * const &>(
    (float *)qword_180065E58,
    (__int64)v12,
    (unsigned __int8 *)&v13);
  _InterlockedDecrement(&dword_180065EC8);
  LOBYTE(v10) = 3;
  LOBYTE(v11) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v11,
    v10);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&dwindex);
  if ( v2 )
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::_Initialization(&SystemSettings::BatterySaverOneCoreDataModel::g_CPowerModeSingleton);
}

```

## disassembly

```asm
0x18003dfac  mov     [rsp+arg_8], rdx
0x18003dfb1  mov     [rsp+arg_0], rcx
0x18003dfb6  push    rsi
0x18003dfb7  push    rdi
0x18003dfb8  sub     rsp, 48h
0x18003dfbc  xor     dil, dil
0x18003dfbf  mov     byte ptr [rsp+58h+arg_0], dil
0x18003dfc4  lea     rsi, stru_180065EA0
0x18003dfcb  mov     rcx, rsi; lpCriticalSection
0x18003dfce  call    cs:__imp_EnterCriticalSection
0x18003dfd4  mov     [rsp+58h+arg_18], rsi
0x18003dfd9  lock inc cs:dword_180065EC8
0x18003dfe0  cmp     cs:byte_180065F00, dil
0x18003dfe7  jz      short loc_18003E01F
0x18003dfe9  cmp     cs:qword_180065EF8, 0
0x18003dff1  jz      short loc_18003E01F
0x18003dff3  mov     dword ptr [rsp+58h+dwindex], 0
0x18003dffb  lea     rax, [rsp+58h+dwindex]
0x18003e000  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x18003e005  lea     r9, qword_180065EF8; pHandles
0x18003e00c  mov     r8d, 1; cHandles
0x18003e012  or      edx, 0FFFFFFFFh; dwTimeout
0x18003e015  lea     ecx, [r8+7]; dwFlags
0x18003e019  call    cs:__imp_CoWaitForMultipleHandles
0x18003e01f  mov     r8b, 3
0x18003e022  mov     dl, 1
0x18003e024  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18003e02b  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003e030  cmp     cs:byte_180065E9A, 0
0x18003e037  jnz     loc_18003E0CC
0x18003e03d  cmp     byte ptr cs:word_180065E98, 0
0x18003e044  jnz     loc_18003E0CC
0x18003e04a  mov     byte ptr cs:word_180065E98, 1
0x18003e051  cmp     cs:dword_180065E38, 0
0x18003e058  jz      short loc_18003E0C4
0x18003e05a  mov     rsi, cs:qword_180065E40
0x18003e061  test    rsi, rsi
0x18003e064  jnz     short loc_18003E092
0x18003e066  xor     r9d, r9d; lpName
0x18003e069  xor     r8d, r8d; bInitialState
0x18003e06c  lea     edx, [rsi+1]; bManualReset
0x18003e06f  xor     ecx, ecx; lpEventAttributes
0x18003e071  call    cs:__imp_CreateEventW
0x18003e077  mov     rsi, rax
0x18003e07a  lea     rcx, qword_180065E40
0x18003e081  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18003e086  mov     cs:qword_180065E40, rsi
0x18003e08d  test    rsi, rsi
0x18003e090  jz      short loc_18003E0C4
0x18003e092  mov     cs:dword_180065F10, 8000000Ah
0x18003e09c  mov     rcx, rsi; hEvent
0x18003e09f  call    cs:__imp_ResetEvent
0x18003e0a5  xor     r9d, r9d; pfnCallback
0x18003e0a8  lea     r8d, [r9+4]; flags
0x18003e0ac  lea     rdx, ?g_CPowerModeSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCPowerModeSingleton@12@A; pData
0x18003e0b3  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@W4BatterySaverCallbackSetting@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x18003e0ba  call    cs:__imp_SHCreateThread
0x18003e0c0  test    eax, eax
0x18003e0c2  jnz     short loc_18003E0CC
0x18003e0c4  mov     dil, 1
0x18003e0c7  mov     byte ptr [rsp+58h+arg_0], dil
0x18003e0cc  mov     r8b, 3
0x18003e0cf  mov     dl, 1
0x18003e0d1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18003e0d8  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003e0dd  nop
0x18003e0de  lea     rcx, [rsp+58h+arg_18]; this
0x18003e0e3  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18003e0e8  lea     rsi, stru_180065ED0
0x18003e0ef  mov     rcx, rsi; lpCriticalSection
0x18003e0f2  call    cs:__imp_EnterCriticalSection
0x18003e0f8  mov     [rsp+58h+dwindex], rsi
0x18003e0fd  mov     r8b, 3
0x18003e100  mov     dl, 1
0x18003e102  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18003e109  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003e10e  nop
0x18003e10f  lea     r8, [rsp+58h+arg_8]
0x18003e114  lea     rdx, [rsp+58h+var_28]
0x18003e119  lea     rcx, qword_180065E58
0x18003e120  call    ??$emplace@AEBQEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback * const &)
0x18003e125  nop
0x18003e126  jmp     short loc_18003E12D
0x18003e128  mov     dil, byte ptr [rsp+58h+arg_0]
0x18003e12d  lock dec cs:dword_180065EC8
0x18003e134  mov     r8b, 3
0x18003e137  mov     dl, 1
0x18003e139  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18003e140  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003e145  nop
0x18003e146  lea     rcx, [rsp+58h+dwindex]; this
0x18003e14b  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18003e150  test    dil, dil
0x18003e153  jz      short loc_18003E161
0x18003e155  lea     rcx, ?g_CPowerModeSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCPowerModeSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CPowerModeSingleton SystemSettings::BatterySaverOneCoreDataModel::g_CPowerModeSingleton
0x18003e15c  call    ?_Initialization@?$CSingletonHelper@W4_BATTERY_STATE@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::_Initialization(void)
0x18003e161  add     rsp, 48h
0x18003e165  pop     rdi
0x18003e166  pop     rsi
0x18003e167  retn
```
