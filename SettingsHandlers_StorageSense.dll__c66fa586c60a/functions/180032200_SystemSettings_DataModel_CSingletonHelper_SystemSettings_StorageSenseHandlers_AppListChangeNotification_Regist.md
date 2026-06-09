# SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::Register(SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::CCallback *)

- ea: `0x180032200`
- end: `0x1800323ca`
- name: `?Register@?$CSingletonHelper@PEAUAppListChangeNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `458`
- prototype: `__int64 __fastcall(void *pData)`
- caller_count: `26`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180028940`
- `0x180028af4`
- `0x18003a378`
- `0x18003a614`
- `0x18003df40`
- `0x180060994`
- `0x180060c60`
- `0x1800610a4`
- `0x180061180`
- `0x180061328`
- `0x180070a24`
- `0x180070f50`
- `0x18007113c`
- `0x18007cd04`
- `0x18007cdbc`
- `0x18007cf24`
- `0x18007d00c`
- `0x18007d0d4`
- `0x18007d1d8`
- `0x18007d2f8`
- `0x180087590`
- `0x1800893f8`
- `0x1800895d0`
- `0x180094600`
- `0x1800bb298`
- `0x1800c8c28`

## callees

- `0x18001f53c`
- `0x180027bc8`
- `0x180032200`
- `0x1800323d0`
- `0x180032cd0`
- `0x180034afc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003222b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003233f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003222b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003233f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800322c6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800322c6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800322ed`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800322ed`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180032281`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180032281`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180032304`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180032304`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::Register(
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
             SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::s_InitializationThread,
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
    std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback * const &>(
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
    SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::_Initialization(v2);
}

```

## disassembly

```asm
0x180032200  mov     [rsp+arg_8], rdx
0x180032205  mov     [rsp+arg_0], rcx
0x18003220a  push    rbx
0x18003220b  push    rdi
0x18003220c  push    r12
0x18003220e  push    r14
0x180032210  push    r15
0x180032212  sub     rsp, 50h
0x180032216  mov     rdi, rcx
0x180032219  xor     r14b, r14b
0x18003221c  mov     [rsp+78h+arg_10], r14b
0x180032224  lea     rbx, [rcx+70h]
0x180032228  mov     rcx, rbx; lpCriticalSection
0x18003222b  call    cs:__imp_EnterCriticalSection
0x180032231  mov     [rsp+78h+var_48], rbx
0x180032236  lea     r15, [rdi+98h]
0x18003223d  mov     [rsp+78h+var_38], r15
0x180032242  lock inc dword ptr [r15]
0x180032246  cmp     [rdi+0D0h], r14b
0x18003224d  jz      short loc_180032287
0x18003224f  lea     r9, [rdi+0C8h]; pHandles
0x180032256  cmp     qword ptr [r9], 0
0x18003225a  jz      short loc_180032287
0x18003225c  mov     dword ptr [rsp+78h+dwindex], 0
0x180032267  lea     rax, [rsp+78h+dwindex]
0x18003226f  mov     [rsp+78h+lpdwindex], rax; lpdwindex
0x180032274  mov     r8d, 1; cHandles
0x18003227a  or      edx, 0FFFFFFFFh; dwTimeout
0x18003227d  lea     ecx, [r8+7]; dwFlags
0x180032281  call    cs:__imp_CoWaitForMultipleHandles
0x180032287  mov     r8b, 3
0x18003228a  mov     dl, 1
0x18003228c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180032293  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180032298  cmp     byte ptr [rdi+6Ah], 0
0x18003229c  jnz     short loc_180032319
0x18003229e  cmp     byte ptr [rdi+68h], 0
0x1800322a2  jnz     short loc_180032319
0x1800322a4  mov     byte ptr [rdi+68h], 1
0x1800322a8  cmp     dword ptr [rdi+8], 0
0x1800322ac  jz      short loc_18003230E
0x1800322ae  lea     r12, [rdi+10h]
0x1800322b2  mov     rbx, [r12]
0x1800322b6  test    rbx, rbx
0x1800322b9  jnz     short loc_1800322E0
0x1800322bb  xor     r9d, r9d; lpName
0x1800322be  xor     r8d, r8d; bInitialState
0x1800322c1  lea     edx, [rbx+1]; bManualReset
0x1800322c4  xor     ecx, ecx; lpEventAttributes
0x1800322c6  call    cs:__imp_CreateEventW
0x1800322cc  mov     rbx, rax
0x1800322cf  mov     rcx, r12
0x1800322d2  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x1800322d7  mov     [r12], rbx
0x1800322db  test    rbx, rbx
0x1800322de  jz      short loc_18003230E
0x1800322e0  mov     dword ptr [rdi+0E0h], 8000000Ah
0x1800322ea  mov     rcx, rbx; hEvent
0x1800322ed  call    cs:__imp_ResetEvent
0x1800322f3  xor     r9d, r9d; pfnCallback
0x1800322f6  lea     r8d, [r9+4]; flags
0x1800322fa  mov     rdx, rdi; pData
0x1800322fd  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@AEBV?$shared_ptr@UCleanupListHandlerEvent@StorageSenseHandlers@SystemSettings@@@std@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x180032304  call    cs:__imp_SHCreateThread
0x18003230a  test    eax, eax
0x18003230c  jnz     short loc_180032319
0x18003230e  mov     r14b, 1
0x180032311  mov     [rsp+78h+arg_10], r14b
0x180032319  mov     r8b, 3
0x18003231c  mov     dl, 1
0x18003231e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180032325  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003232a  nop
0x18003232b  lea     rcx, [rsp+78h+var_48]; this
0x180032330  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180032335  lea     rbx, [rdi+0A0h]
0x18003233c  mov     rcx, rbx; lpCriticalSection
0x18003233f  call    cs:__imp_EnterCriticalSection
0x180032345  mov     [rsp+78h+dwindex], rbx
0x18003234d  mov     r8b, 3
0x180032350  mov     dl, 1
0x180032352  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x180032359  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003235e  nop
0x18003235f  lea     rcx, [rdi+28h]
0x180032363  lea     r8, [rsp+78h+arg_8]
0x18003236b  lea     rdx, [rsp+78h+var_48]
0x180032370  call    ??$emplace@AEBQEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@PEAUAppEnumNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppEnumNotification *>::CCallback * const &)
0x180032375  nop
0x180032376  jmp     short loc_18003238D
0x180032378  mov     rdi, [rsp+78h+arg_0]
0x180032380  mov     r14b, [rsp+78h+arg_10]
0x180032388  mov     r15, [rsp+78h+var_38]
0x18003238d  lock dec dword ptr [r15]
0x180032391  mov     r8b, 3
0x180032394  mov     dl, 1
0x180032396  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18003239d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800323a2  nop
0x1800323a3  lea     rcx, [rsp+78h+dwindex]; this
0x1800323ab  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800323b0  test    r14b, r14b
0x1800323b3  jz      short loc_1800323BD
0x1800323b5  mov     rcx, rdi
0x1800323b8  call    ?_Initialization@?$CSingletonHelper@PEAUAppListChangeNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppListChangeNotification *>::_Initialization(void)
0x1800323bd  add     rsp, 50h
0x1800323c1  pop     r15
0x1800323c3  pop     r14
0x1800323c5  pop     r12
0x1800323c7  pop     rdi
0x1800323c8  pop     rbx
0x1800323c9  retn
```
