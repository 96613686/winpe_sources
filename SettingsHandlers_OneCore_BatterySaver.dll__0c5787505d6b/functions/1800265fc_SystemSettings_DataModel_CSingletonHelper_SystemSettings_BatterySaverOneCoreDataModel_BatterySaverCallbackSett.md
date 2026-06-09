# SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::Register(SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::CCallback *)

- ea: `0x1800265fc`
- end: `0x1800267b8`
- name: `?Register@?$CSingletonHelper@W4BatterySaverCallbackSetting@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `444`
- prototype: ``
- caller_count: `12`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019284`
- `0x180019630`
- `0x1800196ec`
- `0x180019784`
- `0x180019a64`
- `0x180024b60`
- `0x180024cb0`
- `0x180024d40`
- `0x180024d90`
- `0x180024e40`
- `0x18003abe0`
- `0x180046914`

## callees

- `0x180011a54`
- `0x180012c58`
- `0x18001314c`
- `0x1800265fc`
- `0x180026bf0`
- `0x18002adc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800266c1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800266c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002661e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026742`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002661e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026742`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800266ef`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800266ef`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180026669`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180026669`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18002670a`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18002670a`

## pseudocode

```c
void __fastcall SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::Register(
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
  EnterCriticalSection(&stru_1800655B0);
  v15 = &stru_1800655B0;
  _InterlockedIncrement(&dword_1800655D8);
  if ( byte_180065610 && qword_180065608 )
  {
    LODWORD(dwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &qword_180065608, (LPDWORD)&dwindex);
  }
  LOBYTE(v4) = 3;
  LOBYTE(v3) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v3,
    v4);
  if ( !byte_1800655AA && !(_BYTE)word_1800655A8 )
  {
    if ( (LOBYTE(word_1800655A8) = 1, !dword_180065548)
      || (EventW = qword_180065550) == 0
      && (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&qword_180065550),
          (qword_180065550 = EventW) == 0)
      || (dword_180065620 = -2147483638,
          ResetEvent(EventW),
          !SHCreateThread(
             SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::s_InitializationThread,
             &SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverSettingsSingleton,
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
  EnterCriticalSection(&stru_1800655E0);
  dwindex = &stru_1800655E0;
  LOBYTE(v8) = 3;
  LOBYTE(v9) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v9,
    v8);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback * const &>(
    (float *)&qword_180065568,
    (__int64)v12,
    (unsigned __int8 *)&v13);
  _InterlockedDecrement(&dword_1800655D8);
  LOBYTE(v10) = 3;
  LOBYTE(v11) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v11,
    v10);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&dwindex);
  if ( v2 )
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::_Initialization(&SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverSettingsSingleton);
}

```

## disassembly

```asm
0x1800265fc  mov     [rsp+arg_8], rdx
0x180026601  mov     [rsp+arg_0], rcx
0x180026606  push    rsi
0x180026607  push    rdi
0x180026608  sub     rsp, 48h
0x18002660c  xor     dil, dil
0x18002660f  mov     byte ptr [rsp+58h+arg_0], dil
0x180026614  lea     rsi, stru_1800655B0
0x18002661b  mov     rcx, rsi; lpCriticalSection
0x18002661e  call    cs:__imp_EnterCriticalSection
0x180026624  mov     [rsp+58h+arg_18], rsi
0x180026629  lock inc cs:dword_1800655D8
0x180026630  cmp     cs:byte_180065610, dil
0x180026637  jz      short loc_18002666F
0x180026639  cmp     cs:qword_180065608, 0
0x180026641  jz      short loc_18002666F
0x180026643  mov     dword ptr [rsp+58h+dwindex], 0
0x18002664b  lea     rax, [rsp+58h+dwindex]
0x180026650  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x180026655  lea     r9, qword_180065608; pHandles
0x18002665c  mov     r8d, 1; cHandles
0x180026662  or      edx, 0FFFFFFFFh; dwTimeout
0x180026665  lea     ecx, [r8+7]; dwFlags
0x180026669  call    cs:__imp_CoWaitForMultipleHandles
0x18002666f  mov     r8b, 3
0x180026672  mov     dl, 1
0x180026674  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18002667b  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180026680  cmp     cs:byte_1800655AA, 0
0x180026687  jnz     loc_18002671C
0x18002668d  cmp     byte ptr cs:word_1800655A8, 0
0x180026694  jnz     loc_18002671C
0x18002669a  mov     byte ptr cs:word_1800655A8, 1
0x1800266a1  cmp     cs:dword_180065548, 0
0x1800266a8  jz      short loc_180026714
0x1800266aa  mov     rsi, cs:qword_180065550
0x1800266b1  test    rsi, rsi
0x1800266b4  jnz     short loc_1800266E2
0x1800266b6  xor     r9d, r9d; lpName
0x1800266b9  xor     r8d, r8d; bInitialState
0x1800266bc  lea     edx, [rsi+1]; bManualReset
0x1800266bf  xor     ecx, ecx; lpEventAttributes
0x1800266c1  call    cs:__imp_CreateEventW
0x1800266c7  mov     rsi, rax
0x1800266ca  lea     rcx, qword_180065550
0x1800266d1  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x1800266d6  mov     cs:qword_180065550, rsi
0x1800266dd  test    rsi, rsi
0x1800266e0  jz      short loc_180026714
0x1800266e2  mov     cs:dword_180065620, 8000000Ah
0x1800266ec  mov     rcx, rsi; hEvent
0x1800266ef  call    cs:__imp_ResetEvent
0x1800266f5  xor     r9d, r9d; pfnCallback
0x1800266f8  lea     r8d, [r9+4]; flags
0x1800266fc  lea     rdx, ?g_CBatterySaverSettingsSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCBatterySaverSettingsSingleton@12@A; pData
0x180026703  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@W4BatterySaverCallbackSetting@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x18002670a  call    cs:__imp_SHCreateThread
0x180026710  test    eax, eax
0x180026712  jnz     short loc_18002671C
0x180026714  mov     dil, 1
0x180026717  mov     byte ptr [rsp+58h+arg_0], dil
0x18002671c  mov     r8b, 3
0x18002671f  mov     dl, 1
0x180026721  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180026728  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002672d  nop
0x18002672e  lea     rcx, [rsp+58h+arg_18]; this
0x180026733  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180026738  lea     rsi, stru_1800655E0
0x18002673f  mov     rcx, rsi; lpCriticalSection
0x180026742  call    cs:__imp_EnterCriticalSection
0x180026748  mov     [rsp+58h+dwindex], rsi
0x18002674d  mov     r8b, 3
0x180026750  mov     dl, 1
0x180026752  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180026759  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002675e  nop
0x18002675f  lea     r8, [rsp+58h+arg_8]
0x180026764  lea     rdx, [rsp+58h+var_28]
0x180026769  lea     rcx, qword_180065568
0x180026770  call    ??$emplace@AEBQEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback * const &)
0x180026775  nop
0x180026776  jmp     short loc_18002677D
0x180026778  mov     dil, byte ptr [rsp+58h+arg_0]
0x18002677d  lock dec cs:dword_1800655D8
0x180026784  mov     r8b, 3
0x180026787  mov     dl, 1
0x180026789  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180026790  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180026795  nop
0x180026796  lea     rcx, [rsp+58h+dwindex]; this
0x18002679b  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800267a0  test    dil, dil
0x1800267a3  jz      short loc_1800267B1
0x1800267a5  lea     rcx, ?g_CBatterySaverSettingsSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCBatterySaverSettingsSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverSettingsSingleton SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverSettingsSingleton
0x1800267ac  call    ?_Initialization@?$CSingletonHelper@W4_BATTERY_STATE@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::_Initialization(void)
0x1800267b1  add     rsp, 48h
0x1800267b5  pop     rdi
0x1800267b6  pop     rsi
0x1800267b7  retn
```
