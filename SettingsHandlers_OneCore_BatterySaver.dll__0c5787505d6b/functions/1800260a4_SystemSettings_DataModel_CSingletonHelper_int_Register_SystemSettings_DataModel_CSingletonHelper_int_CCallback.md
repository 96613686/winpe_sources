# SystemSettings::DataModel::CSingletonHelper<int>::Register(SystemSettings::DataModel::CSingletonHelper<int>::CCallback *)

- ea: `0x1800260a4`
- end: `0x18002626e`
- name: `?Register@?$CSingletonHelper@H@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `458`
- prototype: `__int64 __fastcall(void *pData)`
- caller_count: `8`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800190d8`
- `0x180033b04`
- `0x180033be0`
- `0x1800365b0`
- `0x180036630`
- `0x18003ce80`
- `0x18003dde0`
- `0x1800452dc`

## callees

- `0x180011a54`
- `0x180012c58`
- `0x18001314c`
- `0x1800260a4`
- `0x180026bf0`
- `0x18002adc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002616a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002616a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800260cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800261e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800260cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800261e3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180026191`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180026191`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180026125`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180026125`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x1800261a8`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x1800261a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SystemSettings::DataModel::CSingletonHelper<int>::Register(char *pData, __int64 a2)
{
  char *v2; // rdi
  char v3; // r14
  char *v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  volatile signed __int32 *v7; // r15
  __int64 v8; // rdx
  __int64 v9; // r8
  HANDLE EventW; // rbx
  __int64 v11; // r8
  __int64 v12; // rdx
  const char *v13; // r9
  __int64 v14; // rdx
  __int64 v15; // r8
  _QWORD v16[2]; // [rsp+30h] [rbp-48h] BYREF
  volatile signed __int32 *v17; // [rsp+40h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  __int64 v21; // [rsp+88h] [rbp+10h] BYREF
  char v22; // [rsp+90h] [rbp+18h]
  char *dwindex; // [rsp+98h] [rbp+20h] BYREF

  v21 = a2;
  v2 = pData;
  v3 = 0;
  v22 = 0;
  v4 = pData + 112;
  EnterCriticalSection((LPCRITICAL_SECTION)(pData + 112));
  v16[0] = v4;
  v7 = (volatile signed __int32 *)(v2 + 152);
  v17 = (volatile signed __int32 *)(v2 + 152);
  _InterlockedIncrement((volatile signed __int32 *)v2 + 38);
  if ( v2[208] && *((_QWORD *)v2 + 25) )
  {
    LODWORD(dwindex) = 0;
    CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, (LPHANDLE)v2 + 25, (LPDWORD)&dwindex);
  }
  LOBYTE(v6) = 3;
  LOBYTE(v5) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v5,
    v6);
  if ( !v2[106] && !v2[104] )
  {
    if ( (v2[104] = 1, !*((_DWORD *)v2 + 2))
      || (EventW = (HANDLE)*((_QWORD *)v2 + 2)) == 0
      && (EventW = CreateEventW(0, 1, 0, 0),
          CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(v2 + 16),
          (*((_QWORD *)v2 + 2) = EventW) == 0)
      || (*((_DWORD *)v2 + 56) = -2147483638,
          ResetEvent(EventW),
          !SHCreateThread(
             SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::s_InitializationThread,
             v2,
             4u,
             0)) )
    {
      v3 = 1;
      v22 = 1;
    }
  }
  LOBYTE(v9) = 3;
  LOBYTE(v8) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v8,
    v9);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)v16);
  EnterCriticalSection((LPCRITICAL_SECTION)v2 + 4);
  dwindex = v2 + 160;
  LOBYTE(v11) = 3;
  LOBYTE(v12) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v12,
    v11);
  try
  {
    std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback * const &>(
      (float *)v2 + 10,
      (__int64)v16,
      (unsigned __int8 *)&v21);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x4A5,
      (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingHandlersBaseCore.h",
      v13);
    v2 = pData;
    v3 = v22;
    v7 = v17;
  }
  _InterlockedDecrement(v7);
  LOBYTE(v15) = 3;
  LOBYTE(v14) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v14,
    v15);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&dwindex);
  if ( v3 )
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::_Initialization(v2);
}

```

## disassembly

```asm
0x1800260a4  mov     [rsp+arg_8], rdx
0x1800260a9  mov     [rsp+arg_0], rcx
0x1800260ae  push    rbx
0x1800260af  push    rdi
0x1800260b0  push    r12
0x1800260b2  push    r14
0x1800260b4  push    r15
0x1800260b6  sub     rsp, 50h
0x1800260ba  mov     rdi, rcx
0x1800260bd  xor     r14b, r14b
0x1800260c0  mov     [rsp+78h+arg_10], r14b
0x1800260c8  lea     rbx, [rcx+70h]
0x1800260cc  mov     rcx, rbx; lpCriticalSection
0x1800260cf  call    cs:__imp_EnterCriticalSection
0x1800260d5  mov     [rsp+78h+var_48], rbx
0x1800260da  lea     r15, [rdi+98h]
0x1800260e1  mov     [rsp+78h+var_38], r15
0x1800260e6  lock inc dword ptr [r15]
0x1800260ea  cmp     [rdi+0D0h], r14b
0x1800260f1  jz      short loc_18002612B
0x1800260f3  lea     r9, [rdi+0C8h]; pHandles
0x1800260fa  cmp     qword ptr [r9], 0
0x1800260fe  jz      short loc_18002612B
0x180026100  mov     dword ptr [rsp+78h+dwindex], 0
0x18002610b  lea     rax, [rsp+78h+dwindex]
0x180026113  mov     [rsp+78h+lpdwindex], rax; lpdwindex
0x180026118  mov     r8d, 1; cHandles
0x18002611e  or      edx, 0FFFFFFFFh; dwTimeout
0x180026121  lea     ecx, [r8+7]; dwFlags
0x180026125  call    cs:__imp_CoWaitForMultipleHandles
0x18002612b  mov     r8b, 3
0x18002612e  mov     dl, 1
0x180026130  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180026137  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002613c  cmp     byte ptr [rdi+6Ah], 0
0x180026140  jnz     short loc_1800261BD
0x180026142  cmp     byte ptr [rdi+68h], 0
0x180026146  jnz     short loc_1800261BD
0x180026148  mov     byte ptr [rdi+68h], 1
0x18002614c  cmp     dword ptr [rdi+8], 0
0x180026150  jz      short loc_1800261B2
0x180026152  lea     r12, [rdi+10h]
0x180026156  mov     rbx, [r12]
0x18002615a  test    rbx, rbx
0x18002615d  jnz     short loc_180026184
0x18002615f  xor     r9d, r9d; lpName
0x180026162  xor     r8d, r8d; bInitialState
0x180026165  lea     edx, [rbx+1]; bManualReset
0x180026168  xor     ecx, ecx; lpEventAttributes
0x18002616a  call    cs:__imp_CreateEventW
0x180026170  mov     rbx, rax
0x180026173  mov     rcx, r12
0x180026176  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18002617b  mov     [r12], rbx
0x18002617f  test    rbx, rbx
0x180026182  jz      short loc_1800261B2
0x180026184  mov     dword ptr [rdi+0E0h], 8000000Ah
0x18002618e  mov     rcx, rbx; hEvent
0x180026191  call    cs:__imp_ResetEvent
0x180026197  xor     r9d, r9d; pfnCallback
0x18002619a  lea     r8d, [r9+4]; flags
0x18002619e  mov     rdx, rdi; pData
0x1800261a1  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@W4BatterySaverCallbackSetting@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x1800261a8  call    cs:__imp_SHCreateThread
0x1800261ae  test    eax, eax
0x1800261b0  jnz     short loc_1800261BD
0x1800261b2  mov     r14b, 1
0x1800261b5  mov     [rsp+78h+arg_10], r14b
0x1800261bd  mov     r8b, 3
0x1800261c0  mov     dl, 1
0x1800261c2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x1800261c9  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800261ce  nop
0x1800261cf  lea     rcx, [rsp+78h+var_48]; this
0x1800261d4  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800261d9  lea     rbx, [rdi+0A0h]
0x1800261e0  mov     rcx, rbx; lpCriticalSection
0x1800261e3  call    cs:__imp_EnterCriticalSection
0x1800261e9  mov     [rsp+78h+dwindex], rbx
0x1800261f1  mov     r8b, 3
0x1800261f4  mov     dl, 1
0x1800261f6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x1800261fd  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180026202  nop
0x180026203  lea     rcx, [rdi+28h]
0x180026207  lea     r8, [rsp+78h+arg_8]
0x18002620f  lea     rdx, [rsp+78h+var_48]
0x180026214  call    ??$emplace@AEBQEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback * const &)
0x180026219  nop
0x18002621a  jmp     short loc_180026231
0x18002621c  mov     rdi, [rsp+78h+arg_0]
0x180026224  mov     r14b, [rsp+78h+arg_10]
0x18002622c  mov     r15, [rsp+78h+var_38]
0x180026231  lock dec dword ptr [r15]
0x180026235  mov     r8b, 3
0x180026238  mov     dl, 1
0x18002623a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180026241  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180026246  nop
0x180026247  lea     rcx, [rsp+78h+dwindex]; this
0x18002624f  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180026254  test    r14b, r14b
0x180026257  jz      short loc_180026261
0x180026259  mov     rcx, rdi
0x18002625c  call    ?_Initialization@?$CSingletonHelper@W4_BATTERY_STATE@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_BATTERY_STATE>::_Initialization(void)
0x180026261  add     rsp, 50h
0x180026265  pop     r15
0x180026267  pop     r14
0x180026269  pop     r12
0x18002626b  pop     rdi
0x18002626c  pop     rbx
0x18002626d  retn
```
