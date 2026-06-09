# SystemSettings::DataModel::CSingletonHelper<ulong>::Register(SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *)

- ea: `0x18001e940`
- end: `0x18001eb21`
- name: `?Register@?$CSingletonHelper@K@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `481`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001a690`
- `0x18003b240`

## callees

- `0x180014d48`
- `0x180019ed4`
- `0x18001e940`
- `0x18001ed10`
- `0x18001f070`
- `0x1800207dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e962`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001eaa4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e962`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001eaa4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001ea45`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001ea45`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ea11`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ea11`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18001ea66`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18001ea66`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001e9b3`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001e9b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SystemSettings::DataModel::CSingletonHelper<unsigned long>::Register(__int64 a1, __int64 a2)
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
  EnterCriticalSection(&stru_18006C180);
  v18 = &stru_18006C180;
  _InterlockedIncrement(&dword_18006C1A8);
  if ( byte_18006C1E0 && pHandles )
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
  if ( !byte_18006C17A && !(_BYTE)word_18006C178 )
  {
    if ( (LOBYTE(word_18006C178) = 1, !dword_18006C118)
      || (EventW = hEvent) == 0
      && (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&hEvent),
          (hEvent = EventW) == 0)
      || (dword_18006C1F0 = -2147483638,
          ResetEvent(EventW),
          !SHCreateThread(
             SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::s_InitializationThread,
             &SystemSettings::WorkAccess::g_WorkAccessSingleton,
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
  EnterCriticalSection(&stru_18006C1B0);
  dwindex = &stru_18006C1B0;
  LOBYTE(v8) = 3;
  LOBYTE(v9) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v9,
    v8);
  try
  {
    std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback * const &>(
      &qword_18006C138,
      v13,
      &v16);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x4A5,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
      v10);
    v2 = v15;
  }
  _InterlockedDecrement(&dword_18006C1A8);
  LOBYTE(v12) = 3;
  LOBYTE(v11) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v11,
    v12);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&dwindex);
  if ( v2 )
    SystemSettings::DataModel::CSingletonHelper<unsigned long>::_Initialization(&SystemSettings::WorkAccess::g_WorkAccessSingleton);
}

```

## disassembly

```asm
0x18001e940  mov     [rsp+arg_8], rdx
0x18001e945  mov     [rsp+arg_0], rcx
0x18001e94a  push    rsi
0x18001e94b  push    rdi
0x18001e94c  sub     rsp, 48h
0x18001e950  xor     dil, dil
0x18001e953  mov     byte ptr [rsp+58h+arg_0], dil
0x18001e958  lea     rsi, stru_18006C180
0x18001e95f  mov     rcx, rsi; lpCriticalSection
0x18001e962  call    cs:__imp_EnterCriticalSection
0x18001e969  nop     dword ptr [rax+rax+00h]
0x18001e96e  mov     [rsp+58h+arg_18], rsi
0x18001e973  lock inc cs:dword_18006C1A8
0x18001e97a  cmp     cs:byte_18006C1E0, dil
0x18001e981  jz      short loc_18001E9BF
0x18001e983  cmp     cs:pHandles, 0
0x18001e98b  jz      short loc_18001E9BF
0x18001e98d  mov     dword ptr [rsp+58h+dwindex], 0
0x18001e995  lea     rax, [rsp+58h+dwindex]
0x18001e99a  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x18001e99f  lea     r9, pHandles; pHandles
0x18001e9a6  mov     r8d, 1; cHandles
0x18001e9ac  or      edx, 0FFFFFFFFh; dwTimeout
0x18001e9af  lea     ecx, [r8+7]; dwFlags
0x18001e9b3  call    cs:__imp_CoWaitForMultipleHandles
0x18001e9ba  nop     dword ptr [rax+rax+00h]
0x18001e9bf  mov     r8b, 3
0x18001e9c2  mov     dl, 1
0x18001e9c4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001e9cb  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001e9d0  cmp     cs:byte_18006C17A, 0
0x18001e9d7  jnz     loc_18001EA7E
0x18001e9dd  cmp     byte ptr cs:word_18006C178, 0
0x18001e9e4  jnz     loc_18001EA7E
0x18001e9ea  mov     byte ptr cs:word_18006C178, 1
0x18001e9f1  cmp     cs:dword_18006C118, 0
0x18001e9f8  jz      short loc_18001EA76
0x18001e9fa  mov     rsi, cs:hEvent
0x18001ea01  test    rsi, rsi
0x18001ea04  jnz     short loc_18001EA38
0x18001ea06  xor     r9d, r9d; lpName
0x18001ea09  xor     r8d, r8d; bInitialState
0x18001ea0c  lea     edx, [rsi+1]; bManualReset
0x18001ea0f  xor     ecx, ecx; lpEventAttributes
0x18001ea11  call    cs:__imp_CreateEventW
0x18001ea18  nop     dword ptr [rax+rax+00h]
0x18001ea1d  mov     rsi, rax
0x18001ea20  lea     rcx, hEvent
0x18001ea27  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18001ea2c  mov     cs:hEvent, rsi
0x18001ea33  test    rsi, rsi
0x18001ea36  jz      short loc_18001EA76
0x18001ea38  mov     cs:dword_18006C1F0, 8000000Ah
0x18001ea42  mov     rcx, rsi; hEvent
0x18001ea45  call    cs:__imp_ResetEvent
0x18001ea4c  nop     dword ptr [rax+rax+00h]
0x18001ea51  xor     r9d, r9d; pfnCallback
0x18001ea54  lea     r8d, [r9+4]; flags
0x18001ea58  lea     rdx, ?g_WorkAccessSingleton@WorkAccess@SystemSettings@@3VCWorkAccessSingleton@12@A; pData
0x18001ea5f  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x18001ea66  call    cs:__imp_SHCreateThread
0x18001ea6d  nop     dword ptr [rax+rax+00h]
0x18001ea72  test    eax, eax
0x18001ea74  jnz     short loc_18001EA7E
0x18001ea76  mov     dil, 1
0x18001ea79  mov     byte ptr [rsp+58h+arg_0], dil
0x18001ea7e  mov     r8b, 3
0x18001ea81  mov     dl, 1
0x18001ea83  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001ea8a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001ea8f  nop
0x18001ea90  lea     rcx, [rsp+58h+arg_18]; this
0x18001ea95  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18001ea9a  lea     rsi, stru_18006C1B0
0x18001eaa1  mov     rcx, rsi; lpCriticalSection
0x18001eaa4  call    cs:__imp_EnterCriticalSection
0x18001eaab  nop     dword ptr [rax+rax+00h]
0x18001eab0  mov     [rsp+58h+dwindex], rsi
0x18001eab5  mov     r8b, 3
0x18001eab8  mov     dl, 1
0x18001eaba  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001eac1  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001eac6  nop
0x18001eac7  lea     r8, [rsp+58h+arg_8]
0x18001eacc  lea     rdx, [rsp+58h+var_28]
0x18001ead1  lea     rcx, qword_18006C138
0x18001ead8  call    ??$emplace@AEBQEAVCCallback@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback * const &)
0x18001eadd  nop
0x18001eade  jmp     short loc_18001EAE5
0x18001eae0  mov     dil, byte ptr [rsp+58h+arg_0]
0x18001eae5  lock dec cs:dword_18006C1A8
0x18001eaec  mov     r8b, 3
0x18001eaef  mov     dl, 1
0x18001eaf1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001eaf8  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001eafd  nop
0x18001eafe  lea     rcx, [rsp+58h+dwindex]; this
0x18001eb03  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18001eb08  test    dil, dil
0x18001eb0b  jz      short loc_18001EB19
0x18001eb0d  lea     rcx, ?g_WorkAccessSingleton@WorkAccess@SystemSettings@@3VCWorkAccessSingleton@12@A; SystemSettings::WorkAccess::CWorkAccessSingleton SystemSettings::WorkAccess::g_WorkAccessSingleton
0x18001eb14  call    ?_Initialization@?$CSingletonHelper@K@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<ulong>::_Initialization(void)
0x18001eb19  add     rsp, 48h
0x18001eb1d  pop     rdi
0x18001eb1e  pop     rsi
0x18001eb1f  retn
```
