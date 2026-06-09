# SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::Register(SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::CCallback *)

- ea: `0x1800267c0`
- end: `0x18002697c`
- name: `?Register@?$CSingletonHelper@W4BatterySaverInfoType@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `444`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019340`
- `0x180024be0`
- `0x18002cc40`
- `0x18002f4d0`
- `0x18002fad4`
- `0x180030300`

## callees

- `0x180011a54`
- `0x180012c58`
- `0x18001314c`
- `0x1800267c0`
- `0x180026bf0`
- `0x18002adc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180026885`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180026885`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800267e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026906`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800267e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026906`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800268b3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800268b3`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18002682d`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18002682d`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x1800268ce`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x1800268ce`

## pseudocode

```c
void __fastcall SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverInfoType>::Register(
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
  EnterCriticalSection(&stru_1800656B0);
  v15 = &stru_1800656B0;
  _InterlockedIncrement(&dword_1800656D8);
  if ( byte_180065710 && qword_180065708 )
  {
    LODWORD(dwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &qword_180065708, (LPDWORD)&dwindex);
  }
  LOBYTE(v4) = 3;
  LOBYTE(v3) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v3,
    v4);
  if ( !byte_1800656AA && !(_BYTE)word_1800656A8 )
  {
    if ( (LOBYTE(word_1800656A8) = 1, !dword_180065648)
      || (EventW = qword_180065650) == 0
      && (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&qword_180065650),
          (qword_180065650 = EventW) == 0)
      || (dword_180065720 = -2147483638,
          ResetEvent(EventW),
          !SHCreateThread(
             SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::s_InitializationThread,
             &SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverBatteryInfoSingleton,
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
  EnterCriticalSection(&stru_1800656E0);
  dwindex = &stru_1800656E0;
  LOBYTE(v8) = 3;
  LOBYTE(v9) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v9,
    v8);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback * const &>(
    (float *)qword_180065668,
    (__int64)v12,
    (unsigned __int8 *)&v13);
  _InterlockedDecrement(&dword_1800656D8);
  LOBYTE(v10) = 3;
  LOBYTE(v11) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v11,
    v10);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&dwindex);
  if ( v2 )
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::_Initialization(&SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverBatteryInfoSingleton);
}

```

## disassembly

```asm
0x1800267c0  mov     [rsp+arg_8], rdx
0x1800267c5  mov     [rsp+arg_0], rcx
0x1800267ca  push    rsi
0x1800267cb  push    rdi
0x1800267cc  sub     rsp, 48h
0x1800267d0  xor     dil, dil
0x1800267d3  mov     byte ptr [rsp+58h+arg_0], dil
0x1800267d8  lea     rsi, stru_1800656B0
0x1800267df  mov     rcx, rsi; lpCriticalSection
0x1800267e2  call    cs:__imp_EnterCriticalSection
0x1800267e8  mov     [rsp+58h+arg_18], rsi
0x1800267ed  lock inc cs:dword_1800656D8
0x1800267f4  cmp     cs:byte_180065710, dil
0x1800267fb  jz      short loc_180026833
0x1800267fd  cmp     cs:qword_180065708, 0
0x180026805  jz      short loc_180026833
0x180026807  mov     dword ptr [rsp+58h+dwindex], 0
0x18002680f  lea     rax, [rsp+58h+dwindex]
0x180026814  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x180026819  lea     r9, qword_180065708; pHandles
0x180026820  mov     r8d, 1; cHandles
0x180026826  or      edx, 0FFFFFFFFh; dwTimeout
0x180026829  lea     ecx, [r8+7]; dwFlags
0x18002682d  call    cs:__imp_CoWaitForMultipleHandles
0x180026833  mov     r8b, 3
0x180026836  mov     dl, 1
0x180026838  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18002683f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180026844  cmp     cs:byte_1800656AA, 0
0x18002684b  jnz     loc_1800268E0
0x180026851  cmp     byte ptr cs:word_1800656A8, 0
0x180026858  jnz     loc_1800268E0
0x18002685e  mov     byte ptr cs:word_1800656A8, 1
0x180026865  cmp     cs:dword_180065648, 0
0x18002686c  jz      short loc_1800268D8
0x18002686e  mov     rsi, cs:qword_180065650
0x180026875  test    rsi, rsi
0x180026878  jnz     short loc_1800268A6
0x18002687a  xor     r9d, r9d; lpName
0x18002687d  xor     r8d, r8d; bInitialState
0x180026880  lea     edx, [rsi+1]; bManualReset
0x180026883  xor     ecx, ecx; lpEventAttributes
0x180026885  call    cs:__imp_CreateEventW
0x18002688b  mov     rsi, rax
0x18002688e  lea     rcx, qword_180065650
0x180026895  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18002689a  mov     cs:qword_180065650, rsi
0x1800268a1  test    rsi, rsi
0x1800268a4  jz      short loc_1800268D8
0x1800268a6  mov     cs:dword_180065720, 8000000Ah
0x1800268b0  mov     rcx, rsi; hEvent
0x1800268b3  call    cs:__imp_ResetEvent
0x1800268b9  xor     r9d, r9d; pfnCallback
0x1800268bc  lea     r8d, [r9+4]; flags
0x1800268c0  lea     rdx, ?g_CBatterySaverBatteryInfoSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCBatterySaverBatteryInfoSingleton@12@A; pData
0x1800268c7  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@W4BatterySaverCallbackSetting@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x1800268ce  call    cs:__imp_SHCreateThread
0x1800268d4  test    eax, eax
0x1800268d6  jnz     short loc_1800268E0
0x1800268d8  mov     dil, 1
0x1800268db  mov     byte ptr [rsp+58h+arg_0], dil
0x1800268e0  mov     r8b, 3
0x1800268e3  mov     dl, 1
0x1800268e5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x1800268ec  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800268f1  nop
0x1800268f2  lea     rcx, [rsp+58h+arg_18]; this
0x1800268f7  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800268fc  lea     rsi, stru_1800656E0
0x180026903  mov     rcx, rsi; lpCriticalSection
0x180026906  call    cs:__imp_EnterCriticalSection
0x18002690c  mov     [rsp+58h+dwindex], rsi
0x180026911  mov     r8b, 3
0x180026914  mov     dl, 1
0x180026916  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18002691d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180026922  nop
0x180026923  lea     r8, [rsp+58h+arg_8]
0x180026928  lea     rdx, [rsp+58h+var_28]
0x18002692d  lea     rcx, qword_180065668
0x180026934  call    ??$emplace@AEBQEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback * const &)
0x180026939  nop
0x18002693a  jmp     short loc_180026941
0x18002693c  mov     dil, byte ptr [rsp+58h+arg_0]
0x180026941  lock dec cs:dword_1800656D8
0x180026948  mov     r8b, 3
0x18002694b  mov     dl, 1
0x18002694d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180026954  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180026959  nop
0x18002695a  lea     rcx, [rsp+58h+dwindex]; this
0x18002695f  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180026964  test    dil, dil
0x180026967  jz      short loc_180026975
0x180026969  lea     rcx, ?g_CBatterySaverBatteryInfoSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCBatterySaverBatteryInfoSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverBatteryInfoSingleton SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverBatteryInfoSingleton
0x180026970  call    ?_Initialization@?$CSingletonHelper@W4_BATTERY_STATE@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::_Initialization(void)
0x180026975  add     rsp, 48h
0x180026979  pop     rdi
0x18002697a  pop     rsi
0x18002697b  retn
```
