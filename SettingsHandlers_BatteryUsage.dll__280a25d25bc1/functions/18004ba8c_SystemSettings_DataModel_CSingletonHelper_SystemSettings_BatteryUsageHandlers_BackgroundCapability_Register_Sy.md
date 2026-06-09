# SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BackgroundCapability>::Register(SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BackgroundCapability>::CCallback *)

- ea: `0x18004ba8c`
- end: `0x18004bc48`
- name: `?Register@?$CSingletonHelper@W4BackgroundCapability@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `444`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004a18c`
- `0x18004c9b0`

## callees

- `0x18000d690`
- `0x18000fa10`
- `0x180010030`
- `0x1800103d0`
- `0x1800112c0`
- `0x18004ba8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004bb51`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004bb51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004baae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004bbd2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004baae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004bbd2`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18004bb7f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18004bb7f`
- `SHCORE!SHCreateThread` at `0x18004bb9a`
- `SHCORE!SHCreateThread` at `0x18004bb9a`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18004baf9`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18004baf9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BackgroundCapability>::Register(
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
  EnterCriticalSection(&stru_180079FF0);
  v18 = &stru_180079FF0;
  _InterlockedIncrement(&dword_18007A018);
  if ( byte_18007A050 && pHandles )
  {
    LODWORD(dwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &pHandles, (LPDWORD)&dwindex);
  }
  LOBYTE(v4) = 3;
  LOBYTE(v3) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v3,
    v4);
  if ( !byte_180079FEA && !(_BYTE)word_180079FE8 )
  {
    if ( (LOBYTE(word_180079FE8) = 1, !dword_180079F88)
      || (EventW = hEvent) == 0
      && (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&hEvent),
          (hEvent = EventW) == 0)
      || (dword_18007A060 = -2147483638,
          ResetEvent(EventW),
          !SHCreateThread(
             SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BackgroundCapability>::s_InitializationThread,
             &SystemSettings::BatteryUsageHandlers::g_BackgroundCapabilitySingleton,
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
  EnterCriticalSection(&stru_18007A020);
  dwindex = &stru_18007A020;
  LOBYTE(v8) = 3;
  LOBYTE(v9) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v9,
    v8);
  try
  {
    std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback * const &>(
      (float *)qword_180079FA8,
      (__int64)v13,
      (unsigned __int8 *)&v16);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x4A5,
      (unsigned int)"OneCoreUap\\Internal\\Shell\\inc\\SettingHandlersBaseCore.h",
      v10);
    v2 = v15;
  }
  _InterlockedDecrement(&dword_18007A018);
  LOBYTE(v12) = 3;
  LOBYTE(v11) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v11,
    v12);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&dwindex);
  if ( v2 )
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::_Initialization(&SystemSettings::BatteryUsageHandlers::g_BackgroundCapabilitySingleton);
}

```

## disassembly

```asm
0x18004ba8c  mov     [rsp+arg_8], rdx
0x18004ba91  mov     [rsp+arg_0], rcx
0x18004ba96  push    rsi
0x18004ba97  push    rdi
0x18004ba98  sub     rsp, 48h
0x18004ba9c  xor     dil, dil
0x18004ba9f  mov     byte ptr [rsp+58h+arg_0], dil
0x18004baa4  lea     rsi, stru_180079FF0
0x18004baab  mov     rcx, rsi; lpCriticalSection
0x18004baae  call    cs:__imp_EnterCriticalSection
0x18004bab4  mov     [rsp+58h+arg_18], rsi
0x18004bab9  lock inc cs:dword_18007A018
0x18004bac0  cmp     cs:byte_18007A050, dil
0x18004bac7  jz      short loc_18004BAFF
0x18004bac9  cmp     cs:pHandles, 0
0x18004bad1  jz      short loc_18004BAFF
0x18004bad3  mov     dword ptr [rsp+58h+dwindex], 0
0x18004badb  lea     rax, [rsp+58h+dwindex]
0x18004bae0  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x18004bae5  lea     r9, pHandles; pHandles
0x18004baec  mov     r8d, 1; cHandles
0x18004baf2  or      edx, 0FFFFFFFFh; dwTimeout
0x18004baf5  lea     ecx, [r8+7]; dwFlags
0x18004baf9  call    cs:__imp_CoWaitForMultipleHandles
0x18004baff  mov     r8b, 3
0x18004bb02  mov     dl, 1
0x18004bb04  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18004bb0b  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004bb10  cmp     cs:byte_180079FEA, 0
0x18004bb17  jnz     loc_18004BBAC
0x18004bb1d  cmp     byte ptr cs:word_180079FE8, 0
0x18004bb24  jnz     loc_18004BBAC
0x18004bb2a  mov     byte ptr cs:word_180079FE8, 1
0x18004bb31  cmp     cs:dword_180079F88, 0
0x18004bb38  jz      short loc_18004BBA4
0x18004bb3a  mov     rsi, cs:hEvent
0x18004bb41  test    rsi, rsi
0x18004bb44  jnz     short loc_18004BB72
0x18004bb46  xor     r9d, r9d; lpName
0x18004bb49  xor     r8d, r8d; bInitialState
0x18004bb4c  lea     edx, [rsi+1]; bManualReset
0x18004bb4f  xor     ecx, ecx; lpEventAttributes
0x18004bb51  call    cs:__imp_CreateEventW
0x18004bb57  mov     rsi, rax
0x18004bb5a  lea     rcx, hEvent
0x18004bb61  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18004bb66  mov     cs:hEvent, rsi
0x18004bb6d  test    rsi, rsi
0x18004bb70  jz      short loc_18004BBA4
0x18004bb72  mov     cs:dword_18007A060, 8000000Ah
0x18004bb7c  mov     rcx, rsi; hEvent
0x18004bb7f  call    cs:__imp_ResetEvent
0x18004bb85  xor     r9d, r9d; pfnCallback
0x18004bb88  lea     r8d, [r9+4]; flags
0x18004bb8c  lea     rdx, ?g_BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@3VBackgroundCapabilitySingleton@12@A; pData
0x18004bb93  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@W4BackgroundCapability@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x18004bb9a  call    cs:__imp_SHCreateThread
0x18004bba0  test    eax, eax
0x18004bba2  jnz     short loc_18004BBAC
0x18004bba4  mov     dil, 1
0x18004bba7  mov     byte ptr [rsp+58h+arg_0], dil
0x18004bbac  mov     r8b, 3
0x18004bbaf  mov     dl, 1
0x18004bbb1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18004bbb8  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004bbbd  nop
0x18004bbbe  lea     rcx, [rsp+58h+arg_18]; this
0x18004bbc3  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18004bbc8  lea     rsi, stru_18007A020
0x18004bbcf  mov     rcx, rsi; lpCriticalSection
0x18004bbd2  call    cs:__imp_EnterCriticalSection
0x18004bbd8  mov     [rsp+58h+dwindex], rsi
0x18004bbdd  mov     r8b, 3
0x18004bbe0  mov     dl, 1
0x18004bbe2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18004bbe9  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004bbee  nop
0x18004bbef  lea     r8, [rsp+58h+arg_8]
0x18004bbf4  lea     rdx, [rsp+58h+var_28]
0x18004bbf9  lea     rcx, qword_180079FA8
0x18004bc00  call    ??$emplace@AEBQEAVCCallback@?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback * const &)
0x18004bc05  nop
0x18004bc06  jmp     short loc_18004BC0D
0x18004bc08  mov     dil, byte ptr [rsp+58h+arg_0]
0x18004bc0d  lock dec cs:dword_18007A018
0x18004bc14  mov     r8b, 3
0x18004bc17  mov     dl, 1
0x18004bc19  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18004bc20  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004bc25  nop
0x18004bc26  lea     rcx, [rsp+58h+dwindex]; this
0x18004bc2b  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18004bc30  test    dil, dil
0x18004bc33  jz      short loc_18004BC41
0x18004bc35  lea     rcx, ?g_BackgroundCapabilitySingleton@BatteryUsageHandlers@SystemSettings@@3VBackgroundCapabilitySingleton@12@A; SystemSettings::BatteryUsageHandlers::BackgroundCapabilitySingleton SystemSettings::BatteryUsageHandlers::g_BackgroundCapabilitySingleton
0x18004bc3c  call    ?_Initialization@?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::_Initialization(void)
0x18004bc41  add     rsp, 48h
0x18004bc45  pop     rdi
0x18004bc46  pop     rsi
0x18004bc47  retn
```
