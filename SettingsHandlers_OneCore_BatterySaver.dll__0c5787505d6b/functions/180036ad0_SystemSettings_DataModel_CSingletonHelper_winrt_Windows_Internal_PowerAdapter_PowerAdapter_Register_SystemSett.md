# SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::Register(SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::CCallback *)

- ea: `0x180036ad0`
- end: `0x180036c8c`
- name: `?Register@?$CSingletonHelper@UPowerAdapter@1Internal@Windows@winrt@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `444`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180033b04`
- `0x1800365b0`

## callees

- `0x180012c58`
- `0x18001314c`
- `0x180017c6c`
- `0x180026bf0`
- `0x18002adc8`
- `0x180036ad0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180036b95`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180036b95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036af2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036c16`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036af2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036c16`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180036bc3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180036bc3`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180036b3d`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180036b3d`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180036bde`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180036bde`

## pseudocode

```c
void __fastcall SystemSettings::DataModel::CSingletonHelper<winrt::Windows::Internal::PowerAdapter::PowerAdapter>::Register(
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
  EnterCriticalSection(&stru_180065D80);
  v15 = &stru_180065D80;
  _InterlockedIncrement(&dword_180065DA8);
  if ( byte_180065DE0 && qword_180065DD8 )
  {
    LODWORD(dwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &qword_180065DD8, (LPDWORD)&dwindex);
  }
  LOBYTE(v4) = 3;
  LOBYTE(v3) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v3,
    v4);
  if ( !byte_180065D7A && !(_BYTE)word_180065D78 )
  {
    if ( (LOBYTE(word_180065D78) = 1, !dword_180065D18)
      || (EventW = qword_180065D20) == 0
      && (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&qword_180065D20),
          (qword_180065D20 = EventW) == 0)
      || (dword_180065DF0 = -2147483638,
          ResetEvent(EventW),
          !SHCreateThread(
             SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::s_InitializationThread,
             &SystemSettings::BatterySaverOneCoreDataModel::g_CRenewableChargingSupportSingleton,
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
  EnterCriticalSection(&stru_180065DB0);
  dwindex = &stru_180065DB0;
  LOBYTE(v8) = 3;
  LOBYTE(v9) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v9,
    v8);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback * const &>(
    (float *)&qword_180065D38,
    (__int64)v12,
    (unsigned __int8 *)&v13);
  _InterlockedDecrement(&dword_180065DA8);
  LOBYTE(v10) = 3;
  LOBYTE(v11) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v11,
    v10);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&dwindex);
  if ( v2 )
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::_Initialization(&SystemSettings::BatterySaverOneCoreDataModel::g_CRenewableChargingSupportSingleton);
}

```

## disassembly

```asm
0x180036ad0  mov     [rsp+arg_8], rdx
0x180036ad5  mov     [rsp+arg_0], rcx
0x180036ada  push    rsi
0x180036adb  push    rdi
0x180036adc  sub     rsp, 48h
0x180036ae0  xor     dil, dil
0x180036ae3  mov     byte ptr [rsp+58h+arg_0], dil
0x180036ae8  lea     rsi, stru_180065D80
0x180036aef  mov     rcx, rsi; lpCriticalSection
0x180036af2  call    cs:__imp_EnterCriticalSection
0x180036af8  mov     [rsp+58h+arg_18], rsi
0x180036afd  lock inc cs:dword_180065DA8
0x180036b04  cmp     cs:byte_180065DE0, dil
0x180036b0b  jz      short loc_180036B43
0x180036b0d  cmp     cs:qword_180065DD8, 0
0x180036b15  jz      short loc_180036B43
0x180036b17  mov     dword ptr [rsp+58h+dwindex], 0
0x180036b1f  lea     rax, [rsp+58h+dwindex]
0x180036b24  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x180036b29  lea     r9, qword_180065DD8; pHandles
0x180036b30  mov     r8d, 1; cHandles
0x180036b36  or      edx, 0FFFFFFFFh; dwTimeout
0x180036b39  lea     ecx, [r8+7]; dwFlags
0x180036b3d  call    cs:__imp_CoWaitForMultipleHandles
0x180036b43  mov     r8b, 3
0x180036b46  mov     dl, 1
0x180036b48  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180036b4f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180036b54  cmp     cs:byte_180065D7A, 0
0x180036b5b  jnz     loc_180036BF0
0x180036b61  cmp     byte ptr cs:word_180065D78, 0
0x180036b68  jnz     loc_180036BF0
0x180036b6e  mov     byte ptr cs:word_180065D78, 1
0x180036b75  cmp     cs:dword_180065D18, 0
0x180036b7c  jz      short loc_180036BE8
0x180036b7e  mov     rsi, cs:qword_180065D20
0x180036b85  test    rsi, rsi
0x180036b88  jnz     short loc_180036BB6
0x180036b8a  xor     r9d, r9d; lpName
0x180036b8d  xor     r8d, r8d; bInitialState
0x180036b90  lea     edx, [rsi+1]; bManualReset
0x180036b93  xor     ecx, ecx; lpEventAttributes
0x180036b95  call    cs:__imp_CreateEventW
0x180036b9b  mov     rsi, rax
0x180036b9e  lea     rcx, qword_180065D20
0x180036ba5  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180036baa  mov     cs:qword_180065D20, rsi
0x180036bb1  test    rsi, rsi
0x180036bb4  jz      short loc_180036BE8
0x180036bb6  mov     cs:dword_180065DF0, 8000000Ah
0x180036bc0  mov     rcx, rsi; hEvent
0x180036bc3  call    cs:__imp_ResetEvent
0x180036bc9  xor     r9d, r9d; pfnCallback
0x180036bcc  lea     r8d, [r9+4]; flags
0x180036bd0  lea     rdx, ?g_CRenewableChargingSupportSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCRenewableChargingSupportSingleton@12@A; pData
0x180036bd7  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@W4BatterySaverCallbackSetting@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x180036bde  call    cs:__imp_SHCreateThread
0x180036be4  test    eax, eax
0x180036be6  jnz     short loc_180036BF0
0x180036be8  mov     dil, 1
0x180036beb  mov     byte ptr [rsp+58h+arg_0], dil
0x180036bf0  mov     r8b, 3
0x180036bf3  mov     dl, 1
0x180036bf5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180036bfc  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180036c01  nop
0x180036c02  lea     rcx, [rsp+58h+arg_18]; this
0x180036c07  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180036c0c  lea     rsi, stru_180065DB0
0x180036c13  mov     rcx, rsi; lpCriticalSection
0x180036c16  call    cs:__imp_EnterCriticalSection
0x180036c1c  mov     [rsp+58h+dwindex], rsi
0x180036c21  mov     r8b, 3
0x180036c24  mov     dl, 1
0x180036c26  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180036c2d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180036c32  nop
0x180036c33  lea     r8, [rsp+58h+arg_8]
0x180036c38  lea     rdx, [rsp+58h+var_28]
0x180036c3d  lea     rcx, qword_180065D38
0x180036c44  call    ??$emplace@AEBQEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback * const &)
0x180036c49  nop
0x180036c4a  jmp     short loc_180036C51
0x180036c4c  mov     dil, byte ptr [rsp+58h+arg_0]
0x180036c51  lock dec cs:dword_180065DA8
0x180036c58  mov     r8b, 3
0x180036c5b  mov     dl, 1
0x180036c5d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180036c64  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180036c69  nop
0x180036c6a  lea     rcx, [rsp+58h+dwindex]; this
0x180036c6f  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180036c74  test    dil, dil
0x180036c77  jz      short loc_180036C85
0x180036c79  lea     rcx, ?g_CRenewableChargingSupportSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCRenewableChargingSupportSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CRenewableChargingSupportSingleton SystemSettings::BatterySaverOneCoreDataModel::g_CRenewableChargingSupportSingleton
0x180036c80  call    ?_Initialization@?$CSingletonHelper@W4_BATTERY_STATE@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::_Initialization(void)
0x180036c85  add     rsp, 48h
0x180036c89  pop     rdi
0x180036c8a  pop     rsi
0x180036c8b  retn
```
