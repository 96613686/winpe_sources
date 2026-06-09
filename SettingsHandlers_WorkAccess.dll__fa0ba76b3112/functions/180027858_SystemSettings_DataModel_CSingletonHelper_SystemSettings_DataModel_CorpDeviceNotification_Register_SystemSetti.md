# SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::Register(SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *)

- ea: `0x180027858`
- end: `0x180027a4f`
- name: `?Register@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `503`
- prototype: `__int64 __fastcall(void *pData)`
- caller_count: `11`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180023378`
- `0x18002dff8`
- `0x18002e1dc`
- `0x18002e280`
- `0x18002e324`
- `0x18002e3c4`
- `0x18002e464`
- `0x18002e534`
- `0x18002e5d8`
- `0x18003b240`
- `0x18003b310`

## callees

- `0x180014d48`
- `0x180019ed4`
- `0x18001ed10`
- `0x18001f070`
- `0x1800207dc`
- `0x180027858`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027883`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800279bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027883`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800279bd`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002795f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002795f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180027932`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180027932`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18002797c`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18002797c`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800278df`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800278df`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::Register(
        char *pData,
        __int64 a2)
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
             SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::s_InitializationThread,
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
    std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback * const &>(
      v2 + 40,
      v16,
      &v21);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x4A5,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
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
    SystemSettings::DataModel::CSingletonHelper<unsigned long>::_Initialization(v2);
}

```

## disassembly

```asm
0x180027858  mov     [rsp+arg_8], rdx
0x18002785d  mov     [rsp+arg_0], rcx
0x180027862  push    rbx
0x180027863  push    rdi
0x180027864  push    r12
0x180027866  push    r14
0x180027868  push    r15
0x18002786a  sub     rsp, 50h
0x18002786e  mov     rdi, rcx
0x180027871  xor     r14b, r14b
0x180027874  mov     [rsp+78h+arg_10], r14b
0x18002787c  lea     rbx, [rcx+70h]
0x180027880  mov     rcx, rbx; lpCriticalSection
0x180027883  call    cs:__imp_EnterCriticalSection
0x18002788a  nop     dword ptr [rax+rax+00h]
0x18002788f  mov     [rsp+78h+var_48], rbx
0x180027894  lea     r15, [rdi+98h]
0x18002789b  mov     [rsp+78h+var_38], r15
0x1800278a0  lock inc dword ptr [r15]
0x1800278a4  cmp     [rdi+0D0h], r14b
0x1800278ab  jz      short loc_1800278EB
0x1800278ad  lea     r9, [rdi+0C8h]; pHandles
0x1800278b4  cmp     qword ptr [r9], 0
0x1800278b8  jz      short loc_1800278EB
0x1800278ba  mov     dword ptr [rsp+78h+dwindex], 0
0x1800278c5  lea     rax, [rsp+78h+dwindex]
0x1800278cd  mov     [rsp+78h+lpdwindex], rax; lpdwindex
0x1800278d2  mov     r8d, 1; cHandles
0x1800278d8  or      edx, 0FFFFFFFFh; dwTimeout
0x1800278db  lea     ecx, [r8+7]; dwFlags
0x1800278df  call    cs:__imp_CoWaitForMultipleHandles
0x1800278e6  nop     dword ptr [rax+rax+00h]
0x1800278eb  mov     r8b, 3
0x1800278ee  mov     dl, 1
0x1800278f0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x1800278f7  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800278fc  cmp     byte ptr [rdi+6Ah], 0
0x180027900  jnz     loc_180027997
0x180027906  cmp     byte ptr [rdi+68h], 0
0x18002790a  jnz     loc_180027997
0x180027910  mov     byte ptr [rdi+68h], 1
0x180027914  cmp     dword ptr [rdi+8], 0
0x180027918  jz      short loc_18002798C
0x18002791a  lea     r12, [rdi+10h]
0x18002791e  mov     rbx, [r12]
0x180027922  test    rbx, rbx
0x180027925  jnz     short loc_180027952
0x180027927  xor     r9d, r9d; lpName
0x18002792a  xor     r8d, r8d; bInitialState
0x18002792d  lea     edx, [rbx+1]; bManualReset
0x180027930  xor     ecx, ecx; lpEventAttributes
0x180027932  call    cs:__imp_CreateEventW
0x180027939  nop     dword ptr [rax+rax+00h]
0x18002793e  mov     rbx, rax
0x180027941  mov     rcx, r12
0x180027944  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180027949  mov     [r12], rbx
0x18002794d  test    rbx, rbx
0x180027950  jz      short loc_18002798C
0x180027952  mov     dword ptr [rdi+0E0h], 8000000Ah
0x18002795c  mov     rcx, rbx; hEvent
0x18002795f  call    cs:__imp_ResetEvent
0x180027966  nop     dword ptr [rax+rax+00h]
0x18002796b  xor     r9d, r9d; pfnCallback
0x18002796e  lea     r8d, [r9+4]; flags
0x180027972  mov     rdx, rdi; pData
0x180027975  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x18002797c  call    cs:__imp_SHCreateThread
0x180027983  nop     dword ptr [rax+rax+00h]
0x180027988  test    eax, eax
0x18002798a  jnz     short loc_180027997
0x18002798c  mov     r14b, 1
0x18002798f  mov     [rsp+78h+arg_10], r14b
0x180027997  mov     r8b, 3
0x18002799a  mov     dl, 1
0x18002799c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x1800279a3  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800279a8  nop
0x1800279a9  lea     rcx, [rsp+78h+var_48]; this
0x1800279ae  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800279b3  lea     rbx, [rdi+0A0h]
0x1800279ba  mov     rcx, rbx; lpCriticalSection
0x1800279bd  call    cs:__imp_EnterCriticalSection
0x1800279c4  nop     dword ptr [rax+rax+00h]
0x1800279c9  mov     [rsp+78h+dwindex], rbx
0x1800279d1  mov     r8b, 3
0x1800279d4  mov     dl, 1
0x1800279d6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x1800279dd  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800279e2  nop
0x1800279e3  lea     rcx, [rdi+28h]
0x1800279e7  lea     r8, [rsp+78h+arg_8]
0x1800279ef  lea     rdx, [rsp+78h+var_48]
0x1800279f4  call    ??$emplace@AEBQEAVCCallback@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@UCorpDeviceNotification@DataModel@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::CorpDeviceNotification>::CCallback * const &)
0x1800279f9  nop
0x1800279fa  jmp     short loc_180027A11
0x1800279fc  mov     rdi, [rsp+78h+arg_0]
0x180027a04  mov     r14b, [rsp+78h+arg_10]
0x180027a0c  mov     r15, [rsp+78h+var_38]
0x180027a11  lock dec dword ptr [r15]
0x180027a15  mov     r8b, 3
0x180027a18  mov     dl, 1
0x180027a1a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180027a21  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180027a26  nop
0x180027a27  lea     rcx, [rsp+78h+dwindex]; this
0x180027a2f  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180027a34  test    r14b, r14b
0x180027a37  jz      short loc_180027A41
0x180027a39  mov     rcx, rdi
0x180027a3c  call    ?_Initialization@?$CSingletonHelper@K@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<ulong>::_Initialization(void)
0x180027a41  add     rsp, 50h
0x180027a45  pop     r15
0x180027a47  pop     r14
0x180027a49  pop     r12
0x180027a4b  pop     rdi
0x180027a4c  pop     rbx
0x180027a4d  retn
```
