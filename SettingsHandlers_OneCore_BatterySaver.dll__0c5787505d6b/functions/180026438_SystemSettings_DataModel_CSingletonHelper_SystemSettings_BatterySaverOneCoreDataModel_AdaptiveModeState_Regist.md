# SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::Register(SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *)

- ea: `0x180026438`
- end: `0x1800265f4`
- name: `?Register@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `444`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019784`
- `0x180024d90`
- `0x18003b87c`
- `0x18003c090`

## callees

- `0x180012c58`
- `0x18001314c`
- `0x180017c6c`
- `0x180026438`
- `0x180026bf0`
- `0x18002adc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800264fd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800264fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002645a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002657e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002645a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002657e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002652b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002652b`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800264a5`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800264a5`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180026546`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180026546`

## pseudocode

```c
void __fastcall SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::Register(
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
  EnterCriticalSection(&stru_1800667A0);
  v15 = &stru_1800667A0;
  _InterlockedIncrement(&dword_1800667C8);
  if ( byte_180066800 && qword_1800667F8 )
  {
    LODWORD(dwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &qword_1800667F8, (LPDWORD)&dwindex);
  }
  LOBYTE(v4) = 3;
  LOBYTE(v3) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v3,
    v4);
  if ( !byte_18006679A && !(_BYTE)word_180066798 )
  {
    if ( (LOBYTE(word_180066798) = 1, !dword_180066738)
      || (EventW = qword_180066740) == 0
      && (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&qword_180066740),
          (qword_180066740 = EventW) == 0)
      || (dword_180066810 = -2147483638,
          ResetEvent(EventW),
          !SHCreateThread(
             SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::s_InitializationThread,
             &SystemSettings::BatterySaverOneCoreDataModel::g_AdaptiveModeSingleton,
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
  EnterCriticalSection(&stru_1800667D0);
  dwindex = &stru_1800667D0;
  LOBYTE(v8) = 3;
  LOBYTE(v9) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v9,
    v8);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback * const &>(
    (float *)qword_180066758,
    (__int64)v12,
    (unsigned __int8 *)&v13);
  _InterlockedDecrement(&dword_1800667C8);
  LOBYTE(v10) = 3;
  LOBYTE(v11) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v11,
    v10);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&dwindex);
  if ( v2 )
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::_Initialization(&SystemSettings::BatterySaverOneCoreDataModel::g_AdaptiveModeSingleton);
}

```

## disassembly

```asm
0x180026438  mov     [rsp+arg_8], rdx
0x18002643d  mov     [rsp+arg_0], rcx
0x180026442  push    rsi
0x180026443  push    rdi
0x180026444  sub     rsp, 48h
0x180026448  xor     dil, dil
0x18002644b  mov     byte ptr [rsp+58h+arg_0], dil
0x180026450  lea     rsi, stru_1800667A0
0x180026457  mov     rcx, rsi; lpCriticalSection
0x18002645a  call    cs:__imp_EnterCriticalSection
0x180026460  mov     [rsp+58h+arg_18], rsi
0x180026465  lock inc cs:dword_1800667C8
0x18002646c  cmp     cs:byte_180066800, dil
0x180026473  jz      short loc_1800264AB
0x180026475  cmp     cs:qword_1800667F8, 0
0x18002647d  jz      short loc_1800264AB
0x18002647f  mov     dword ptr [rsp+58h+dwindex], 0
0x180026487  lea     rax, [rsp+58h+dwindex]
0x18002648c  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x180026491  lea     r9, qword_1800667F8; pHandles
0x180026498  mov     r8d, 1; cHandles
0x18002649e  or      edx, 0FFFFFFFFh; dwTimeout
0x1800264a1  lea     ecx, [r8+7]; dwFlags
0x1800264a5  call    cs:__imp_CoWaitForMultipleHandles
0x1800264ab  mov     r8b, 3
0x1800264ae  mov     dl, 1
0x1800264b0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x1800264b7  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800264bc  cmp     cs:byte_18006679A, 0
0x1800264c3  jnz     loc_180026558
0x1800264c9  cmp     byte ptr cs:word_180066798, 0
0x1800264d0  jnz     loc_180026558
0x1800264d6  mov     byte ptr cs:word_180066798, 1
0x1800264dd  cmp     cs:dword_180066738, 0
0x1800264e4  jz      short loc_180026550
0x1800264e6  mov     rsi, cs:qword_180066740
0x1800264ed  test    rsi, rsi
0x1800264f0  jnz     short loc_18002651E
0x1800264f2  xor     r9d, r9d; lpName
0x1800264f5  xor     r8d, r8d; bInitialState
0x1800264f8  lea     edx, [rsi+1]; bManualReset
0x1800264fb  xor     ecx, ecx; lpEventAttributes
0x1800264fd  call    cs:__imp_CreateEventW
0x180026503  mov     rsi, rax
0x180026506  lea     rcx, qword_180066740
0x18002650d  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180026512  mov     cs:qword_180066740, rsi
0x180026519  test    rsi, rsi
0x18002651c  jz      short loc_180026550
0x18002651e  mov     cs:dword_180066810, 8000000Ah
0x180026528  mov     rcx, rsi; hEvent
0x18002652b  call    cs:__imp_ResetEvent
0x180026531  xor     r9d, r9d; pfnCallback
0x180026534  lea     r8d, [r9+4]; flags
0x180026538  lea     rdx, ?g_AdaptiveModeSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VAdaptiveModeSingleton@12@A; pData
0x18002653f  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@W4BatterySaverCallbackSetting@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x180026546  call    cs:__imp_SHCreateThread
0x18002654c  test    eax, eax
0x18002654e  jnz     short loc_180026558
0x180026550  mov     dil, 1
0x180026553  mov     byte ptr [rsp+58h+arg_0], dil
0x180026558  mov     r8b, 3
0x18002655b  mov     dl, 1
0x18002655d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180026564  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180026569  nop
0x18002656a  lea     rcx, [rsp+58h+arg_18]; this
0x18002656f  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180026574  lea     rsi, stru_1800667D0
0x18002657b  mov     rcx, rsi; lpCriticalSection
0x18002657e  call    cs:__imp_EnterCriticalSection
0x180026584  mov     [rsp+58h+dwindex], rsi
0x180026589  mov     r8b, 3
0x18002658c  mov     dl, 1
0x18002658e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180026595  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002659a  nop
0x18002659b  lea     r8, [rsp+58h+arg_8]
0x1800265a0  lea     rdx, [rsp+58h+var_28]
0x1800265a5  lea     rcx, qword_180066758
0x1800265ac  call    ??$emplace@AEBQEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback * const &)
0x1800265b1  nop
0x1800265b2  jmp     short loc_1800265B9
0x1800265b4  mov     dil, byte ptr [rsp+58h+arg_0]
0x1800265b9  lock dec cs:dword_1800667C8
0x1800265c0  mov     r8b, 3
0x1800265c3  mov     dl, 1
0x1800265c5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x1800265cc  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800265d1  nop
0x1800265d2  lea     rcx, [rsp+58h+dwindex]; this
0x1800265d7  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800265dc  test    dil, dil
0x1800265df  jz      short loc_1800265ED
0x1800265e1  lea     rcx, ?g_AdaptiveModeSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VAdaptiveModeSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeSingleton SystemSettings::BatterySaverOneCoreDataModel::g_AdaptiveModeSingleton
0x1800265e8  call    ?_Initialization@?$CSingletonHelper@W4_BATTERY_STATE@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::_Initialization(void)
0x1800265ed  add     rsp, 48h
0x1800265f1  pop     rdi
0x1800265f2  pop     rsi
0x1800265f3  retn
```
