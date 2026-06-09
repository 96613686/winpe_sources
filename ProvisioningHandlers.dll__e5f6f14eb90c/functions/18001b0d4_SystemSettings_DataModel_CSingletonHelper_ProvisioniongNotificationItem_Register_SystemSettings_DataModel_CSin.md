# SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::Register(SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *)

- ea: `0x18001b0d4`
- end: `0x18001b2bc`
- name: `?Register@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `488`
- prototype: ``
- caller_count: `9`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f6fc`
- `0x18000f830`
- `0x18000f978`
- `0x18000fa20`
- `0x18000fad0`
- `0x18000fb6c`
- `0x18000fcac`
- `0x18000fd5c`
- `0x18000fe34`

## callees

- `0x18000df60`
- `0x180019c10`
- `0x18001b0d4`
- `0x18001b330`
- `0x18001c3f0`
- `0x18001f288`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001b1d9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001b1d9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b1a5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b1a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b0f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b238`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b0f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b238`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001b147`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001b147`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18001b1fa`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18001b1fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::Register(
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
  __int64 v10; // r9
  const char *v11; // r9
  __int64 v12; // rdx
  __int64 v13; // r8
  _BYTE v14[40]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  char v16; // [rsp+60h] [rbp+8h]
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF
  struct _RTL_CRITICAL_SECTION *dwindex; // [rsp+70h] [rbp+18h] BYREF
  struct _RTL_CRITICAL_SECTION *v19; // [rsp+78h] [rbp+20h] BYREF

  v17 = a2;
  v2 = 0;
  v16 = 0;
  EnterCriticalSection(&CriticalSection);
  v19 = &CriticalSection;
  _InterlockedIncrement(&dword_18003EEC8);
  if ( byte_18003EF00 && pHandles )
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
  if ( !byte_18003EE9A && !(_BYTE)word_18003EE98 )
  {
    if ( (LOBYTE(word_18003EE98) = 1, !dword_18003EE38)
      || (EventW = hEvent) == 0
      && (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&hEvent),
          (hEvent = EventW) == 0)
      || (dword_18003EF10 = -2147483638,
          ResetEvent(EventW),
          !SHCreateThread(
             SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::s_InitializationThread,
             &g_CProvisioningSingleton,
             4u,
             0)) )
    {
      v2 = 1;
      v16 = 1;
    }
  }
  LOBYTE(v6) = 3;
  LOBYTE(v5) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v5,
    v6);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v19);
  EnterCriticalSection(&stru_18003EED0);
  dwindex = &stru_18003EED0;
  LOBYTE(v8) = 3;
  LOBYTE(v9) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v9,
    v8);
  try
  {
    LOBYTE(v10) = byte_18003EE28;
    std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>,0>>::_Insert<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback * const &,std::_Nil>(
      &qword_18003EE58,
      v14,
      &v17,
      v10);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x4A5,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
      v11);
    v2 = v16;
  }
  _InterlockedDecrement(&dword_18003EEC8);
  LOBYTE(v13) = 3;
  LOBYTE(v12) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v12,
    v13);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&dwindex);
  if ( v2 )
    SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::_Initialization(&g_CProvisioningSingleton);
}

```

## disassembly

```asm
0x18001b0d4  mov     [rsp+arg_8], rdx
0x18001b0d9  mov     [rsp+arg_0], rcx
0x18001b0de  push    rsi
0x18001b0df  push    rdi
0x18001b0e0  sub     rsp, 48h
0x18001b0e4  xor     dil, dil
0x18001b0e7  mov     byte ptr [rsp+58h+arg_0], dil
0x18001b0ec  lea     rsi, CriticalSection
0x18001b0f3  mov     rcx, rsi; lpCriticalSection
0x18001b0f6  call    cs:__imp_EnterCriticalSection
0x18001b0fd  nop     dword ptr [rax+rax+00h]
0x18001b102  mov     [rsp+58h+arg_18], rsi
0x18001b107  lock inc cs:dword_18003EEC8
0x18001b10e  cmp     cs:byte_18003EF00, dil
0x18001b115  jz      short loc_18001B153
0x18001b117  cmp     cs:pHandles, 0
0x18001b11f  jz      short loc_18001B153
0x18001b121  mov     dword ptr [rsp+58h+dwindex], 0
0x18001b129  lea     rax, [rsp+58h+dwindex]
0x18001b12e  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x18001b133  lea     r9, pHandles; pHandles
0x18001b13a  mov     r8d, 1; cHandles
0x18001b140  or      edx, 0FFFFFFFFh; dwTimeout
0x18001b143  lea     ecx, [r8+7]; dwFlags
0x18001b147  call    cs:__imp_CoWaitForMultipleHandles
0x18001b14e  nop     dword ptr [rax+rax+00h]
0x18001b153  mov     r8b, 3
0x18001b156  mov     dl, 1
0x18001b158  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001b15f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001b164  cmp     cs:byte_18003EE9A, 0
0x18001b16b  jnz     loc_18001B212
0x18001b171  cmp     byte ptr cs:word_18003EE98, 0
0x18001b178  jnz     loc_18001B212
0x18001b17e  mov     byte ptr cs:word_18003EE98, 1
0x18001b185  cmp     cs:dword_18003EE38, 0
0x18001b18c  jz      short loc_18001B20A
0x18001b18e  mov     rsi, cs:hEvent
0x18001b195  test    rsi, rsi
0x18001b198  jnz     short loc_18001B1CC
0x18001b19a  xor     r9d, r9d; lpName
0x18001b19d  xor     r8d, r8d; bInitialState
0x18001b1a0  lea     edx, [rsi+1]; bManualReset
0x18001b1a3  xor     ecx, ecx; lpEventAttributes
0x18001b1a5  call    cs:__imp_CreateEventW
0x18001b1ac  nop     dword ptr [rax+rax+00h]
0x18001b1b1  mov     rsi, rax
0x18001b1b4  lea     rcx, hEvent
0x18001b1bb  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18001b1c0  mov     cs:hEvent, rsi
0x18001b1c7  test    rsi, rsi
0x18001b1ca  jz      short loc_18001B20A
0x18001b1cc  mov     cs:dword_18003EF10, 8000000Ah
0x18001b1d6  mov     rcx, rsi; hEvent
0x18001b1d9  call    cs:__imp_ResetEvent
0x18001b1e0  nop     dword ptr [rax+rax+00h]
0x18001b1e5  xor     r9d, r9d; pfnCallback
0x18001b1e8  lea     r8d, [r9+4]; flags
0x18001b1ec  lea     rdx, ?g_CProvisioningSingleton@@3VCProvisioningSingleton@@A; pData
0x18001b1f3  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x18001b1fa  call    cs:__imp_SHCreateThread
0x18001b201  nop     dword ptr [rax+rax+00h]
0x18001b206  test    eax, eax
0x18001b208  jnz     short loc_18001B212
0x18001b20a  mov     dil, 1
0x18001b20d  mov     byte ptr [rsp+58h+arg_0], dil
0x18001b212  mov     r8b, 3
0x18001b215  mov     dl, 1
0x18001b217  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001b21e  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001b223  nop
0x18001b224  lea     rcx, [rsp+58h+arg_18]; this
0x18001b229  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18001b22e  lea     rsi, stru_18003EED0
0x18001b235  mov     rcx, rsi; lpCriticalSection
0x18001b238  call    cs:__imp_EnterCriticalSection
0x18001b23f  nop     dword ptr [rax+rax+00h]
0x18001b244  mov     [rsp+58h+dwindex], rsi
0x18001b249  mov     r8b, 3
0x18001b24c  mov     dl, 1
0x18001b24e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001b255  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001b25a  nop
0x18001b25b  mov     r9b, cs:byte_18003EE28
0x18001b262  lea     r8, [rsp+58h+arg_8]
0x18001b267  lea     rdx, [rsp+58h+var_28]
0x18001b26c  lea     rcx, qword_18003EE58
0x18001b273  call    ??$_Insert@AEBQEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@U_Nil@std@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@IEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@U_Nil@1@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>,0>>::_Insert<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback * const &,std::_Nil>(SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback * const &,std::_Nil)
0x18001b278  nop
0x18001b279  jmp     short loc_18001B280
0x18001b27b  mov     dil, byte ptr [rsp+58h+arg_0]
0x18001b280  lock dec cs:dword_18003EEC8
0x18001b287  mov     r8b, 3
0x18001b28a  mov     dl, 1
0x18001b28c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001b293  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001b298  nop
0x18001b299  lea     rcx, [rsp+58h+dwindex]; this
0x18001b29e  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18001b2a3  test    dil, dil
0x18001b2a6  jz      short loc_18001B2B4
0x18001b2a8  lea     rcx, ?g_CProvisioningSingleton@@3VCProvisioningSingleton@@A; CProvisioningSingleton g_CProvisioningSingleton
0x18001b2af  call    ?_Initialization@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::_Initialization(void)
0x18001b2b4  add     rsp, 48h
0x18001b2b8  pop     rdi
0x18001b2b9  pop     rsi
0x18001b2ba  retn
```
