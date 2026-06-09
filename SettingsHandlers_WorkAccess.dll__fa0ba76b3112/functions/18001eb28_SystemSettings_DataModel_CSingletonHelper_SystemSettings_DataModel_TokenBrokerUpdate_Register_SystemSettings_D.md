# SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::TokenBrokerUpdate>::Register(SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::TokenBrokerUpdate>::CCallback *)

- ea: `0x18001eb28`
- end: `0x18001ed09`
- name: `?Register@?$CSingletonHelper@W4TokenBrokerUpdate@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `481`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001a690`

## callees

- `0x180014d48`
- `0x180019ed4`
- `0x18001eb28`
- `0x18001ed10`
- `0x18001f070`
- `0x1800207dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001eb4a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ec8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001eb4a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ec8c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001ec2d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001ec2d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ebf9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ebf9`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18001ec4e`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18001ec4e`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001eb9b`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001eb9b`

## pseudocode

```c
void __fastcall SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::TokenBrokerUpdate>::Register(
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
  EnterCriticalSection(&CriticalSection);
  v15 = &CriticalSection;
  _InterlockedIncrement(&dword_18006C048);
  if ( byte_18006C080 && qword_18006C078 )
  {
    LODWORD(dwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &qword_18006C078, (LPDWORD)&dwindex);
  }
  LOBYTE(v4) = 3;
  LOBYTE(v3) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v3,
    v4);
  if ( !byte_18006C01A && !(_BYTE)word_18006C018 )
  {
    if ( (LOBYTE(word_18006C018) = 1, !dword_18006BFB8)
      || (EventW = qword_18006BFC0) == 0
      && (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&qword_18006BFC0),
          (qword_18006BFC0 = EventW) == 0)
      || (dword_18006C090 = -2147483638,
          ResetEvent(EventW),
          !SHCreateThread(
             SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::s_InitializationThread,
             &SystemSettings::DataModel::g_TokenBrokerSingleton,
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
  EnterCriticalSection(&stru_18006C050);
  dwindex = &stru_18006C050;
  LOBYTE(v8) = 3;
  LOBYTE(v9) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v9,
    v8);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback * const &>(
    qword_18006BFD8,
    v12,
    &v13);
  _InterlockedDecrement(&dword_18006C048);
  LOBYTE(v10) = 3;
  LOBYTE(v11) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v11,
    v10);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&dwindex);
  if ( v2 )
    SystemSettings::DataModel::CSingletonHelper<unsigned long>::_Initialization(&SystemSettings::DataModel::g_TokenBrokerSingleton);
}

```

## disassembly

```asm
0x18001eb28  mov     [rsp+arg_8], rdx
0x18001eb2d  mov     [rsp+arg_0], rcx
0x18001eb32  push    rsi
0x18001eb33  push    rdi
0x18001eb34  sub     rsp, 48h
0x18001eb38  xor     dil, dil
0x18001eb3b  mov     byte ptr [rsp+58h+arg_0], dil
0x18001eb40  lea     rsi, CriticalSection
0x18001eb47  mov     rcx, rsi; lpCriticalSection
0x18001eb4a  call    cs:__imp_EnterCriticalSection
0x18001eb51  nop     dword ptr [rax+rax+00h]
0x18001eb56  mov     [rsp+58h+arg_18], rsi
0x18001eb5b  lock inc cs:dword_18006C048
0x18001eb62  cmp     cs:byte_18006C080, dil
0x18001eb69  jz      short loc_18001EBA7
0x18001eb6b  cmp     cs:qword_18006C078, 0
0x18001eb73  jz      short loc_18001EBA7
0x18001eb75  mov     dword ptr [rsp+58h+dwindex], 0
0x18001eb7d  lea     rax, [rsp+58h+dwindex]
0x18001eb82  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x18001eb87  lea     r9, qword_18006C078; pHandles
0x18001eb8e  mov     r8d, 1; cHandles
0x18001eb94  or      edx, 0FFFFFFFFh; dwTimeout
0x18001eb97  lea     ecx, [r8+7]; dwFlags
0x18001eb9b  call    cs:__imp_CoWaitForMultipleHandles
0x18001eba2  nop     dword ptr [rax+rax+00h]
0x18001eba7  mov     r8b, 3
0x18001ebaa  mov     dl, 1
0x18001ebac  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001ebb3  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001ebb8  cmp     cs:byte_18006C01A, 0
0x18001ebbf  jnz     loc_18001EC66
0x18001ebc5  cmp     byte ptr cs:word_18006C018, 0
0x18001ebcc  jnz     loc_18001EC66
0x18001ebd2  mov     byte ptr cs:word_18006C018, 1
0x18001ebd9  cmp     cs:dword_18006BFB8, 0
0x18001ebe0  jz      short loc_18001EC5E
0x18001ebe2  mov     rsi, cs:qword_18006BFC0
0x18001ebe9  test    rsi, rsi
0x18001ebec  jnz     short loc_18001EC20
0x18001ebee  xor     r9d, r9d; lpName
0x18001ebf1  xor     r8d, r8d; bInitialState
0x18001ebf4  lea     edx, [rsi+1]; bManualReset
0x18001ebf7  xor     ecx, ecx; lpEventAttributes
0x18001ebf9  call    cs:__imp_CreateEventW
0x18001ec00  nop     dword ptr [rax+rax+00h]
0x18001ec05  mov     rsi, rax
0x18001ec08  lea     rcx, qword_18006BFC0
0x18001ec0f  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18001ec14  mov     cs:qword_18006BFC0, rsi
0x18001ec1b  test    rsi, rsi
0x18001ec1e  jz      short loc_18001EC5E
0x18001ec20  mov     cs:dword_18006C090, 8000000Ah
0x18001ec2a  mov     rcx, rsi; hEvent
0x18001ec2d  call    cs:__imp_ResetEvent
0x18001ec34  nop     dword ptr [rax+rax+00h]
0x18001ec39  xor     r9d, r9d; pfnCallback
0x18001ec3c  lea     r8d, [r9+4]; flags
0x18001ec40  lea     rdx, ?g_TokenBrokerSingleton@DataModel@SystemSettings@@3VTokenBrokerSingleton@12@A; pData
0x18001ec47  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x18001ec4e  call    cs:__imp_SHCreateThread
0x18001ec55  nop     dword ptr [rax+rax+00h]
0x18001ec5a  test    eax, eax
0x18001ec5c  jnz     short loc_18001EC66
0x18001ec5e  mov     dil, 1
0x18001ec61  mov     byte ptr [rsp+58h+arg_0], dil
0x18001ec66  mov     r8b, 3
0x18001ec69  mov     dl, 1
0x18001ec6b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001ec72  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001ec77  nop
0x18001ec78  lea     rcx, [rsp+58h+arg_18]; this
0x18001ec7d  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18001ec82  lea     rsi, stru_18006C050
0x18001ec89  mov     rcx, rsi; lpCriticalSection
0x18001ec8c  call    cs:__imp_EnterCriticalSection
0x18001ec93  nop     dword ptr [rax+rax+00h]
0x18001ec98  mov     [rsp+58h+dwindex], rsi
0x18001ec9d  mov     r8b, 3
0x18001eca0  mov     dl, 1
0x18001eca2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001eca9  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001ecae  nop
0x18001ecaf  lea     r8, [rsp+58h+arg_8]
0x18001ecb4  lea     rdx, [rsp+58h+var_28]
0x18001ecb9  lea     rcx, qword_18006BFD8
0x18001ecc0  call    ??$emplace@AEBQEAVCCallback@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback * const &)
0x18001ecc5  nop
0x18001ecc6  jmp     short loc_18001ECCD
0x18001ecc8  mov     dil, byte ptr [rsp+58h+arg_0]
0x18001eccd  lock dec cs:dword_18006C048
0x18001ecd4  mov     r8b, 3
0x18001ecd7  mov     dl, 1
0x18001ecd9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001ece0  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001ece5  nop
0x18001ece6  lea     rcx, [rsp+58h+dwindex]; this
0x18001eceb  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18001ecf0  test    dil, dil
0x18001ecf3  jz      short loc_18001ED01
0x18001ecf5  lea     rcx, ?g_TokenBrokerSingleton@DataModel@SystemSettings@@3VTokenBrokerSingleton@12@A; SystemSettings::DataModel::TokenBrokerSingleton SystemSettings::DataModel::g_TokenBrokerSingleton
0x18001ecfc  call    ?_Initialization@?$CSingletonHelper@K@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<ulong>::_Initialization(void)
0x18001ed01  add     rsp, 48h
0x18001ed05  pop     rdi
0x18001ed06  pop     rsi
0x18001ed07  retn
```
