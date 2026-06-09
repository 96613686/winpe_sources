# SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::Register(SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback *)

- ea: `0x18000fdf4`
- end: `0x18000ffbe`
- name: `?Register@?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `458`
- prototype: `__int64 __fastcall(void *pData)`
- caller_count: `16`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000d9d8`
- `0x18001a5f8`
- `0x18001a658`
- `0x18001f918`
- `0x18001f9b0`
- `0x18001fb20`
- `0x180026690`
- `0x1800270dc`
- `0x180027730`
- `0x18002aae0`
- `0x180031ce0`
- `0x180034b10`
- `0x180037270`
- `0x1800375fc`
- `0x18004976c`
- `0x180049870`

## callees

- `0x18000d690`
- `0x18000fa10`
- `0x18000fdf4`
- `0x180010030`
- `0x1800103d0`
- `0x1800112c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000feba`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000feba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fe1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ff33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fe1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ff33`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000fee1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000fee1`
- `SHCORE!SHCreateThread` at `0x18000fef8`
- `SHCORE!SHCreateThread` at `0x18000fef8`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000fe75`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000fe75`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::Register(
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
             SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BackgroundCapability>::s_InitializationThread,
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
    std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback * const &>(
      (float *)v2 + 10,
      (__int64)v16,
      (unsigned __int8 *)&v21);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x4A5,
      (unsigned int)"OneCoreUap\\Internal\\Shell\\inc\\SettingHandlersBaseCore.h",
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
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::_Initialization(v2);
}

```

## disassembly

```asm
0x18000fdf4  mov     [rsp+arg_8], rdx
0x18000fdf9  mov     [rsp+arg_0], rcx
0x18000fdfe  push    rbx
0x18000fdff  push    rdi
0x18000fe00  push    r12
0x18000fe02  push    r14
0x18000fe04  push    r15
0x18000fe06  sub     rsp, 50h
0x18000fe0a  mov     rdi, rcx
0x18000fe0d  xor     r14b, r14b
0x18000fe10  mov     [rsp+78h+arg_10], r14b
0x18000fe18  lea     rbx, [rcx+70h]
0x18000fe1c  mov     rcx, rbx; lpCriticalSection
0x18000fe1f  call    cs:__imp_EnterCriticalSection
0x18000fe25  mov     [rsp+78h+var_48], rbx
0x18000fe2a  lea     r15, [rdi+98h]
0x18000fe31  mov     [rsp+78h+var_38], r15
0x18000fe36  lock inc dword ptr [r15]
0x18000fe3a  cmp     [rdi+0D0h], r14b
0x18000fe41  jz      short loc_18000FE7B
0x18000fe43  lea     r9, [rdi+0C8h]; pHandles
0x18000fe4a  cmp     qword ptr [r9], 0
0x18000fe4e  jz      short loc_18000FE7B
0x18000fe50  mov     dword ptr [rsp+78h+dwindex], 0
0x18000fe5b  lea     rax, [rsp+78h+dwindex]
0x18000fe63  mov     [rsp+78h+lpdwindex], rax; lpdwindex
0x18000fe68  mov     r8d, 1; cHandles
0x18000fe6e  or      edx, 0FFFFFFFFh; dwTimeout
0x18000fe71  lea     ecx, [r8+7]; dwFlags
0x18000fe75  call    cs:__imp_CoWaitForMultipleHandles
0x18000fe7b  mov     r8b, 3
0x18000fe7e  mov     dl, 1
0x18000fe80  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18000fe87  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000fe8c  cmp     byte ptr [rdi+6Ah], 0
0x18000fe90  jnz     short loc_18000FF0D
0x18000fe92  cmp     byte ptr [rdi+68h], 0
0x18000fe96  jnz     short loc_18000FF0D
0x18000fe98  mov     byte ptr [rdi+68h], 1
0x18000fe9c  cmp     dword ptr [rdi+8], 0
0x18000fea0  jz      short loc_18000FF02
0x18000fea2  lea     r12, [rdi+10h]
0x18000fea6  mov     rbx, [r12]
0x18000feaa  test    rbx, rbx
0x18000fead  jnz     short loc_18000FED4
0x18000feaf  xor     r9d, r9d; lpName
0x18000feb2  xor     r8d, r8d; bInitialState
0x18000feb5  lea     edx, [rbx+1]; bManualReset
0x18000feb8  xor     ecx, ecx; lpEventAttributes
0x18000feba  call    cs:__imp_CreateEventW
0x18000fec0  mov     rbx, rax
0x18000fec3  mov     rcx, r12
0x18000fec6  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18000fecb  mov     [r12], rbx
0x18000fecf  test    rbx, rbx
0x18000fed2  jz      short loc_18000FF02
0x18000fed4  mov     dword ptr [rdi+0E0h], 8000000Ah
0x18000fede  mov     rcx, rbx; hEvent
0x18000fee1  call    cs:__imp_ResetEvent
0x18000fee7  xor     r9d, r9d; pfnCallback
0x18000feea  lea     r8d, [r9+4]; flags
0x18000feee  mov     rdx, rdi; pData
0x18000fef1  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@W4BackgroundCapability@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x18000fef8  call    cs:__imp_SHCreateThread
0x18000fefe  test    eax, eax
0x18000ff00  jnz     short loc_18000FF0D
0x18000ff02  mov     r14b, 1
0x18000ff05  mov     [rsp+78h+arg_10], r14b
0x18000ff0d  mov     r8b, 3
0x18000ff10  mov     dl, 1
0x18000ff12  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18000ff19  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000ff1e  nop
0x18000ff1f  lea     rcx, [rsp+78h+var_48]; this
0x18000ff24  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18000ff29  lea     rbx, [rdi+0A0h]
0x18000ff30  mov     rcx, rbx; lpCriticalSection
0x18000ff33  call    cs:__imp_EnterCriticalSection
0x18000ff39  mov     [rsp+78h+dwindex], rbx
0x18000ff41  mov     r8b, 3
0x18000ff44  mov     dl, 1
0x18000ff46  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18000ff4d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000ff52  nop
0x18000ff53  lea     rcx, [rdi+28h]
0x18000ff57  lea     r8, [rsp+78h+arg_8]
0x18000ff5f  lea     rdx, [rsp+78h+var_48]
0x18000ff64  call    ??$emplace@AEBQEAVCCallback@?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::CCallback * const &)
0x18000ff69  nop
0x18000ff6a  jmp     short loc_18000FF81
0x18000ff6c  mov     rdi, [rsp+78h+arg_0]
0x18000ff74  mov     r14b, [rsp+78h+arg_10]
0x18000ff7c  mov     r15, [rsp+78h+var_38]
0x18000ff81  lock dec dword ptr [r15]
0x18000ff85  mov     r8b, 3
0x18000ff88  mov     dl, 1
0x18000ff8a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18000ff91  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000ff96  nop
0x18000ff97  lea     rcx, [rsp+78h+dwindex]; this
0x18000ff9f  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18000ffa4  test    r14b, r14b
0x18000ffa7  jz      short loc_18000FFB1
0x18000ffa9  mov     rcx, rdi
0x18000ffac  call    ?_Initialization@?$CSingletonHelper@W4BatteryUsageNotification@BatteryUsageHandlers@SystemSettings@@@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatteryUsageHandlers::BatteryUsageNotification>::_Initialization(void)
0x18000ffb1  add     rsp, 50h
0x18000ffb5  pop     r15
0x18000ffb7  pop     r14
0x18000ffb9  pop     r12
0x18000ffbb  pop     rdi
0x18000ffbc  pop     rbx
0x18000ffbd  retn
```
