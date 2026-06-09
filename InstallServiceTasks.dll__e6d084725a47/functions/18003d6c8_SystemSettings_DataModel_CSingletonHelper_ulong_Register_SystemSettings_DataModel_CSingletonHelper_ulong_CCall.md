# SystemSettings::DataModel::CSingletonHelper<ulong>::Register(SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *)

- ea: `0x18003d6c8`
- end: `0x18003d892`
- name: `?Register@?$CSingletonHelper@K@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `458`
- prototype: `__int64 __fastcall(void *pData)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003b378`

## callees

- `0x18003af10`
- `0x18003d418`
- `0x18003d6c8`
- `0x18003d900`
- `0x18003ddac`
- `0x18003eb40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003d7b5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003d7b5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003d78e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003d78e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d6f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d807`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d6f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d807`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18003d749`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18003d749`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18003d7cc`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18003d7cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SystemSettings::DataModel::CSingletonHelper<unsigned long>::Register(char *pData, __int64 a2)
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
          !SHCreateThread(SystemSettings::DataModel::CSingletonHelper<unsigned long>::s_InitializationThread, v2, 4u, 0)) )
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
    std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<unsigned long>::CCallback * const &>(
      (float *)v2 + 10,
      (__int64)v16,
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
0x18003d6c8  mov     [rsp+arg_8], rdx
0x18003d6cd  mov     [rsp+arg_0], rcx
0x18003d6d2  push    rbx
0x18003d6d3  push    rdi
0x18003d6d4  push    r12
0x18003d6d6  push    r14
0x18003d6d8  push    r15
0x18003d6da  sub     rsp, 50h
0x18003d6de  mov     rdi, rcx
0x18003d6e1  xor     r14b, r14b
0x18003d6e4  mov     [rsp+78h+arg_10], r14b
0x18003d6ec  lea     rbx, [rcx+70h]
0x18003d6f0  mov     rcx, rbx; lpCriticalSection
0x18003d6f3  call    cs:__imp_EnterCriticalSection
0x18003d6f9  mov     [rsp+78h+var_48], rbx
0x18003d6fe  lea     r15, [rdi+98h]
0x18003d705  mov     [rsp+78h+var_38], r15
0x18003d70a  lock inc dword ptr [r15]
0x18003d70e  cmp     [rdi+0D0h], r14b
0x18003d715  jz      short loc_18003D74F
0x18003d717  lea     r9, [rdi+0C8h]; pHandles
0x18003d71e  cmp     qword ptr [r9], 0
0x18003d722  jz      short loc_18003D74F
0x18003d724  mov     dword ptr [rsp+78h+dwindex], 0
0x18003d72f  lea     rax, [rsp+78h+dwindex]
0x18003d737  mov     [rsp+78h+lpdwindex], rax; lpdwindex
0x18003d73c  mov     r8d, 1; cHandles
0x18003d742  or      edx, 0FFFFFFFFh; dwTimeout
0x18003d745  lea     ecx, [r8+7]; dwFlags
0x18003d749  call    cs:__imp_CoWaitForMultipleHandles
0x18003d74f  mov     r8b, 3
0x18003d752  mov     dl, 1
0x18003d754  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18003d75b  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003d760  cmp     byte ptr [rdi+6Ah], 0
0x18003d764  jnz     short loc_18003D7E1
0x18003d766  cmp     byte ptr [rdi+68h], 0
0x18003d76a  jnz     short loc_18003D7E1
0x18003d76c  mov     byte ptr [rdi+68h], 1
0x18003d770  cmp     dword ptr [rdi+8], 0
0x18003d774  jz      short loc_18003D7D6
0x18003d776  lea     r12, [rdi+10h]
0x18003d77a  mov     rbx, [r12]
0x18003d77e  test    rbx, rbx
0x18003d781  jnz     short loc_18003D7A8
0x18003d783  xor     r9d, r9d; lpName
0x18003d786  xor     r8d, r8d; bInitialState
0x18003d789  lea     edx, [rbx+1]; bManualReset
0x18003d78c  xor     ecx, ecx; lpEventAttributes
0x18003d78e  call    cs:__imp_CreateEventW
0x18003d794  mov     rbx, rax
0x18003d797  mov     rcx, r12
0x18003d79a  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18003d79f  mov     [r12], rbx
0x18003d7a3  test    rbx, rbx
0x18003d7a6  jz      short loc_18003D7D6
0x18003d7a8  mov     dword ptr [rdi+0E0h], 8000000Ah
0x18003d7b2  mov     rcx, rbx; hEvent
0x18003d7b5  call    cs:__imp_ResetEvent
0x18003d7bb  xor     r9d, r9d; pfnCallback
0x18003d7be  lea     r8d, [r9+4]; flags
0x18003d7c2  mov     rdx, rdi; pData
0x18003d7c5  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@K@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x18003d7cc  call    cs:__imp_SHCreateThread
0x18003d7d2  test    eax, eax
0x18003d7d4  jnz     short loc_18003D7E1
0x18003d7d6  mov     r14b, 1
0x18003d7d9  mov     [rsp+78h+arg_10], r14b
0x18003d7e1  mov     r8b, 3
0x18003d7e4  mov     dl, 1
0x18003d7e6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18003d7ed  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003d7f2  nop
0x18003d7f3  lea     rcx, [rsp+78h+var_48]; this
0x18003d7f8  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18003d7fd  lea     rbx, [rdi+0A0h]
0x18003d804  mov     rcx, rbx; lpCriticalSection
0x18003d807  call    cs:__imp_EnterCriticalSection
0x18003d80d  mov     [rsp+78h+dwindex], rbx
0x18003d815  mov     r8b, 3
0x18003d818  mov     dl, 1
0x18003d81a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18003d821  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003d826  nop
0x18003d827  lea     rcx, [rdi+28h]
0x18003d82b  lea     r8, [rsp+78h+arg_8]
0x18003d833  lea     rdx, [rsp+78h+var_48]
0x18003d838  call    ??$emplace@AEBQEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@K@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<ulong>::CCallback * const &)
0x18003d83d  nop
0x18003d83e  jmp     short loc_18003D855
0x18003d840  mov     rdi, [rsp+78h+arg_0]
0x18003d848  mov     r14b, [rsp+78h+arg_10]
0x18003d850  mov     r15, [rsp+78h+var_38]
0x18003d855  lock dec dword ptr [r15]
0x18003d859  mov     r8b, 3
0x18003d85c  mov     dl, 1
0x18003d85e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18003d865  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003d86a  nop
0x18003d86b  lea     rcx, [rsp+78h+dwindex]; this
0x18003d873  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18003d878  test    r14b, r14b
0x18003d87b  jz      short loc_18003D885
0x18003d87d  mov     rcx, rdi
0x18003d880  call    ?_Initialization@?$CSingletonHelper@K@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<ulong>::_Initialization(void)
0x18003d885  add     rsp, 50h
0x18003d889  pop     r15
0x18003d88b  pop     r14
0x18003d88d  pop     r12
0x18003d88f  pop     rdi
0x18003d890  pop     rbx
0x18003d891  retn
```
