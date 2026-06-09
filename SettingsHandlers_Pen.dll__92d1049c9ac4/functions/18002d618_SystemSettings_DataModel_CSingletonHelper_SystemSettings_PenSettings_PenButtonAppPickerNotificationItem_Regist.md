# SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::Register(SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::CCallback *)

- ea: `0x18002d618`
- end: `0x18002d7e2`
- name: `?Register@?$CSingletonHelper@AEAUPenButtonAppPickerNotificationItem@PenSettings@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `458`
- prototype: `__int64 __fastcall(void *pData)`
- caller_count: `19`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001f71c`
- `0x18001f7d0`
- `0x18001f95c`
- `0x18001fa00`
- `0x18001fb44`
- `0x18001fc28`
- `0x180033ab0`
- `0x180033bec`
- `0x180033c94`
- `0x180033d3c`
- `0x180033de4`
- `0x180033f40`
- `0x180033fe8`
- `0x180034080`
- `0x180034224`
- `0x180034310`
- `0x1800343a8`
- `0x18003448c`
- `0x18003484c`

## callees

- `0x18001620c`
- `0x18001e974`
- `0x18002d618`
- `0x18002d7e8`
- `0x18002e2b8`
- `0x180030e00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d643`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d757`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d643`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d757`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d6de`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d6de`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002d705`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002d705`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18002d699`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18002d699`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18002d71c`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18002d71c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenButtonAppPickerNotificationItem &>::Register(
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
             SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PenSettings::PenCommandsSyncArgs>::s_InitializationThread,
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
    std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PenSettings::PenSettingUpdate>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PenSettings::PenSettingUpdate>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PenSettings::PenSettingUpdate>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PenSettings::PenSettingUpdate>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PenSettings::PenSettingUpdate>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PenSettings::PenSettingUpdate>::CCallback * const &>(
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
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PenSettings::PenSettingUpdate>::_Initialization(v2);
}

```

## disassembly

```asm
0x18002d618  mov     [rsp+arg_8], rdx
0x18002d61d  mov     [rsp+arg_0], rcx
0x18002d622  push    rbx
0x18002d623  push    rdi
0x18002d624  push    r12
0x18002d626  push    r14
0x18002d628  push    r15
0x18002d62a  sub     rsp, 50h
0x18002d62e  mov     rdi, rcx
0x18002d631  xor     r14b, r14b
0x18002d634  mov     [rsp+78h+arg_10], r14b
0x18002d63c  lea     rbx, [rcx+70h]
0x18002d640  mov     rcx, rbx; lpCriticalSection
0x18002d643  call    cs:__imp_EnterCriticalSection
0x18002d649  mov     [rsp+78h+var_48], rbx
0x18002d64e  lea     r15, [rdi+98h]
0x18002d655  mov     [rsp+78h+var_38], r15
0x18002d65a  lock inc dword ptr [r15]
0x18002d65e  cmp     [rdi+0D0h], r14b
0x18002d665  jz      short loc_18002D69F
0x18002d667  lea     r9, [rdi+0C8h]; pHandles
0x18002d66e  cmp     qword ptr [r9], 0
0x18002d672  jz      short loc_18002D69F
0x18002d674  mov     dword ptr [rsp+78h+dwindex], 0
0x18002d67f  lea     rax, [rsp+78h+dwindex]
0x18002d687  mov     [rsp+78h+lpdwindex], rax; lpdwindex
0x18002d68c  mov     r8d, 1; cHandles
0x18002d692  or      edx, 0FFFFFFFFh; dwTimeout
0x18002d695  lea     ecx, [r8+7]; dwFlags
0x18002d699  call    cs:__imp_CoWaitForMultipleHandles
0x18002d69f  mov     r8b, 3
0x18002d6a2  mov     dl, 1
0x18002d6a4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18002d6ab  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002d6b0  cmp     byte ptr [rdi+6Ah], 0
0x18002d6b4  jnz     short loc_18002D731
0x18002d6b6  cmp     byte ptr [rdi+68h], 0
0x18002d6ba  jnz     short loc_18002D731
0x18002d6bc  mov     byte ptr [rdi+68h], 1
0x18002d6c0  cmp     dword ptr [rdi+8], 0
0x18002d6c4  jz      short loc_18002D726
0x18002d6c6  lea     r12, [rdi+10h]
0x18002d6ca  mov     rbx, [r12]
0x18002d6ce  test    rbx, rbx
0x18002d6d1  jnz     short loc_18002D6F8
0x18002d6d3  xor     r9d, r9d; lpName
0x18002d6d6  xor     r8d, r8d; bInitialState
0x18002d6d9  lea     edx, [rbx+1]; bManualReset
0x18002d6dc  xor     ecx, ecx; lpEventAttributes
0x18002d6de  call    cs:__imp_CreateEventW
0x18002d6e4  mov     rbx, rax
0x18002d6e7  mov     rcx, r12
0x18002d6ea  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18002d6ef  mov     [r12], rbx
0x18002d6f3  test    rbx, rbx
0x18002d6f6  jz      short loc_18002D726
0x18002d6f8  mov     dword ptr [rdi+0E0h], 8000000Ah
0x18002d702  mov     rcx, rbx; hEvent
0x18002d705  call    cs:__imp_ResetEvent
0x18002d70b  xor     r9d, r9d; pfnCallback
0x18002d70e  lea     r8d, [r9+4]; flags
0x18002d712  mov     rdx, rdi; pData
0x18002d715  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@W4PenCommandsSyncArgs@PenSettings@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x18002d71c  call    cs:__imp_SHCreateThread
0x18002d722  test    eax, eax
0x18002d724  jnz     short loc_18002D731
0x18002d726  mov     r14b, 1
0x18002d729  mov     [rsp+78h+arg_10], r14b
0x18002d731  mov     r8b, 3
0x18002d734  mov     dl, 1
0x18002d736  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18002d73d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002d742  nop
0x18002d743  lea     rcx, [rsp+78h+var_48]; this
0x18002d748  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18002d74d  lea     rbx, [rdi+0A0h]
0x18002d754  mov     rcx, rbx; lpCriticalSection
0x18002d757  call    cs:__imp_EnterCriticalSection
0x18002d75d  mov     [rsp+78h+dwindex], rbx
0x18002d765  mov     r8b, 3
0x18002d768  mov     dl, 1
0x18002d76a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18002d771  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002d776  nop
0x18002d777  lea     rcx, [rdi+28h]
0x18002d77b  lea     r8, [rsp+78h+arg_8]
0x18002d783  lea     rdx, [rsp+78h+var_48]
0x18002d788  call    ??$emplace@AEBQEAVCCallback@?$CSingletonHelper@W4PenSettingUpdate@PenSettings@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4PenSettingUpdate@PenSettings@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4PenSettingUpdate@PenSettings@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4PenSettingUpdate@PenSettings@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4PenSettingUpdate@PenSettings@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4PenSettingUpdate@PenSettings@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4PenSettingUpdate@PenSettings@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@W4PenSettingUpdate@PenSettings@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenSettingUpdate>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenSettingUpdate>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenSettingUpdate>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenSettingUpdate>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenSettingUpdate>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenSettingUpdate>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenSettingUpdate>::CCallback * const &)
0x18002d78d  nop
0x18002d78e  jmp     short loc_18002D7A5
0x18002d790  mov     rdi, [rsp+78h+arg_0]
0x18002d798  mov     r14b, [rsp+78h+arg_10]
0x18002d7a0  mov     r15, [rsp+78h+var_38]
0x18002d7a5  lock dec dword ptr [r15]
0x18002d7a9  mov     r8b, 3
0x18002d7ac  mov     dl, 1
0x18002d7ae  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18002d7b5  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002d7ba  nop
0x18002d7bb  lea     rcx, [rsp+78h+dwindex]; this
0x18002d7c3  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18002d7c8  test    r14b, r14b
0x18002d7cb  jz      short loc_18002D7D5
0x18002d7cd  mov     rcx, rdi
0x18002d7d0  call    ?_Initialization@?$CSingletonHelper@W4PenSettingUpdate@PenSettings@SystemSettings@@@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenSettingUpdate>::_Initialization(void)
0x18002d7d5  add     rsp, 50h
0x18002d7d9  pop     r15
0x18002d7db  pop     r14
0x18002d7dd  pop     r12
0x18002d7df  pop     rdi
0x18002d7e0  pop     rbx
0x18002d7e1  retn
```
