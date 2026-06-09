# SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::Register(SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *)

- ea: `0x18001d6d4`
- end: `0x18001d8c9`
- name: `?Register@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@QEAAXPEAVCCallback@123@@Z`
- size: `501`
- prototype: `__int64 __fastcall(void *pData)`
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180010efc`
- `0x180011008`
- `0x18001127c`
- `0x180011378`
- `0x180011544`
- `0x180011648`
- `0x18001d8d0`

## callees

- `0x18001d6d4`
- `0x18001e840`
- `0x180021acc`
- `0x180023260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001d7da`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001d7da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d820`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d8a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d820`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d8a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d6ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d838`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d6ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d838`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001d79f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001d79f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d7be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d7be`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001d755`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001d755`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18001d7f1`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18001d7f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::Register(
        char *pData,
        __int64 a2)
{
  char *v2; // rbx
  char v3; // si
  struct _RTL_CRITICAL_SECTION *v4; // r12
  __int64 v5; // rdx
  __int64 v6; // r8
  volatile signed __int32 *v7; // r15
  __int64 v8; // rdx
  __int64 v9; // r8
  HANDLE EventW; // r14
  char *v11; // rcx
  struct _RTL_CRITICAL_SECTION *v12; // r14
  __int64 v13; // r8
  __int64 v14; // rdx
  const char *v15; // r9
  __int64 v16; // rdx
  __int64 v17; // r8
  volatile signed __int32 *v18; // [rsp+30h] [rbp-48h]
  _BYTE v20[56]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  __int64 v24; // [rsp+88h] [rbp+10h] BYREF
  char v25; // [rsp+90h] [rbp+18h]
  struct _RTL_CRITICAL_SECTION *dwindex; // [rsp+98h] [rbp+20h] BYREF

  v24 = a2;
  v2 = pData;
  v3 = 0;
  v25 = 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)(pData + 112);
  EnterCriticalSection((LPCRITICAL_SECTION)(pData + 112));
  v7 = (volatile signed __int32 *)(v2 + 152);
  v18 = (volatile signed __int32 *)(v2 + 152);
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
    v2[104] = 1;
    if ( !*((_DWORD *)v2 + 2) )
      goto LABEL_12;
    EventW = (HANDLE)*((_QWORD *)v2 + 2);
    if ( !EventW )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      v11 = (char *)*((_QWORD *)v2 + 2);
      *((_QWORD *)v2 + 2) = 0;
      if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v11);
      *((_QWORD *)v2 + 2) = EventW;
      if ( !EventW )
        goto LABEL_12;
    }
    *((_DWORD *)v2 + 56) = -2147483638;
    ResetEvent(EventW);
    if ( !SHCreateThread(
            SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::s_InitializationThread,
            v2,
            4u,
            0) )
    {
LABEL_12:
      v3 = 1;
      v25 = 1;
    }
  }
  LOBYTE(v9) = 3;
  LOBYTE(v8) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v8,
    v9);
  if ( v4 )
    LeaveCriticalSection(v4);
  v12 = (struct _RTL_CRITICAL_SECTION *)(v2 + 160);
  dwindex = (struct _RTL_CRITICAL_SECTION *)(v2 + 160);
  EnterCriticalSection((LPCRITICAL_SECTION)v2 + 4);
  LOBYTE(v13) = 3;
  LOBYTE(v14) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v14,
    v13);
  try
  {
    std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,0>>::insert(
      v2 + 40,
      v20,
      &v24);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x4A5, v17, v15);
    v2 = pData;
    v3 = v25;
    v7 = v18;
    v12 = dwindex;
  }
  _InterlockedDecrement(v7);
  LOBYTE(v17) = 3;
  LOBYTE(v16) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl'::`2'::impl,
    v16,
    v17);
  if ( v12 )
    LeaveCriticalSection(v12);
  if ( v3 )
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::_Initialization(v2);
}

```

## disassembly

```asm
0x18001d6d4  mov     [rsp+arg_8], rdx
0x18001d6d9  mov     [rsp+arg_0], rcx
0x18001d6de  push    rbx
0x18001d6df  push    rsi
0x18001d6e0  push    r12
0x18001d6e2  push    r14
0x18001d6e4  push    r15
0x18001d6e6  sub     rsp, 50h
0x18001d6ea  mov     rbx, rcx
0x18001d6ed  xor     sil, sil
0x18001d6f0  mov     [rsp+78h+arg_10], sil
0x18001d6f8  lea     r12, [rcx+70h]
0x18001d6fc  mov     rcx, r12; lpCriticalSection
0x18001d6ff  call    cs:__imp_EnterCriticalSection
0x18001d705  mov     [rsp+78h+var_40], r12
0x18001d70a  lea     r15, [rbx+98h]
0x18001d711  mov     [rsp+78h+var_48], r15
0x18001d716  lock inc dword ptr [r15]
0x18001d71a  cmp     [rbx+0D0h], sil
0x18001d721  jz      short loc_18001D75B
0x18001d723  lea     r9, [rbx+0C8h]; pHandles
0x18001d72a  cmp     qword ptr [r9], 0
0x18001d72e  jz      short loc_18001D75B
0x18001d730  mov     dword ptr [rsp+78h+dwindex], 0
0x18001d73b  lea     rax, [rsp+78h+dwindex]
0x18001d743  mov     [rsp+78h+lpdwindex], rax; lpdwindex
0x18001d748  mov     r8d, 1; cHandles
0x18001d74e  or      edx, 0FFFFFFFFh; dwTimeout
0x18001d751  lea     ecx, [r8+7]; dwFlags
0x18001d755  call    cs:__imp_CoWaitForMultipleHandles
0x18001d75b  mov     r8b, 3
0x18001d75e  mov     dl, 1
0x18001d760  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001d767  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001d76c  cmp     byte ptr [rbx+6Ah], 0
0x18001d770  jnz     loc_18001D806
0x18001d776  cmp     byte ptr [rbx+68h], 0
0x18001d77a  jnz     loc_18001D806
0x18001d780  mov     byte ptr [rbx+68h], 1
0x18001d784  cmp     dword ptr [rbx+8], 0
0x18001d788  jz      short loc_18001D7FB
0x18001d78a  mov     r14, [rbx+10h]
0x18001d78e  test    r14, r14
0x18001d791  jnz     short loc_18001D7CD
0x18001d793  xor     r9d, r9d; lpName
0x18001d796  xor     r8d, r8d; bInitialState
0x18001d799  lea     edx, [r14+1]; bManualReset
0x18001d79d  xor     ecx, ecx; lpEventAttributes
0x18001d79f  call    cs:__imp_CreateEventW
0x18001d7a5  mov     r14, rax
0x18001d7a8  mov     rcx, [rbx+10h]; hObject
0x18001d7ac  mov     qword ptr [rbx+10h], 0
0x18001d7b4  lea     rax, [rcx-1]
0x18001d7b8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001d7bc  ja      short loc_18001D7C4
0x18001d7be  call    cs:__imp_CloseHandle
0x18001d7c4  mov     [rbx+10h], r14
0x18001d7c8  test    r14, r14
0x18001d7cb  jz      short loc_18001D7FB
0x18001d7cd  mov     dword ptr [rbx+0E0h], 8000000Ah
0x18001d7d7  mov     rcx, r14; hEvent
0x18001d7da  call    cs:__imp_ResetEvent
0x18001d7e0  xor     r9d, r9d; pfnCallback
0x18001d7e3  lea     r8d, [r9+4]; flags
0x18001d7e7  mov     rdx, rbx; pData
0x18001d7ea  lea     rcx, ?s_InitializationThread@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; pfnThreadProc
0x18001d7f1  call    cs:__imp_SHCreateThread
0x18001d7f7  test    eax, eax
0x18001d7f9  jnz     short loc_18001D806
0x18001d7fb  mov     sil, 1
0x18001d7fe  mov     [rsp+78h+arg_10], sil
0x18001d806  mov     r8b, 3
0x18001d809  mov     dl, 1
0x18001d80b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001d812  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001d817  nop
0x18001d818  test    r12, r12
0x18001d81b  jz      short loc_18001D826
0x18001d81d  mov     rcx, r12; lpCriticalSection
0x18001d820  call    cs:__imp_LeaveCriticalSection
0x18001d826  lea     r14, [rbx+0A0h]
0x18001d82d  mov     [rsp+78h+dwindex], r14
0x18001d835  mov     rcx, r14; lpCriticalSection
0x18001d838  call    cs:__imp_EnterCriticalSection
0x18001d83e  mov     [rsp+78h+var_40], r14
0x18001d843  mov     r8b, 3
0x18001d846  mov     dl, 1
0x18001d848  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001d84f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001d854  nop
0x18001d855  lea     rcx, [rbx+28h]
0x18001d859  lea     r8, [rsp+78h+arg_8]
0x18001d861  lea     rdx, [rsp+78h+var_38]
0x18001d866  call    ?insert@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@2@AEBQEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,0>>::insert(SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback * const &)
0x18001d86b  nop
0x18001d86c  jmp     short loc_18001D88B
0x18001d86e  mov     rbx, [rsp+78h+arg_0]
0x18001d876  mov     sil, [rsp+78h+arg_10]
0x18001d87e  mov     r15, [rsp+78h+var_48]
0x18001d883  mov     r14, [rsp+78h+dwindex]
0x18001d88b  lock dec dword ptr [r15]
0x18001d88f  mov     r8b, 3
0x18001d892  mov     dl, 1
0x18001d894  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton> `wil::Feature<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetImpl(void)'::`2'::impl
0x18001d89b  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001d8a0  nop
0x18001d8a1  test    r14, r14
0x18001d8a4  jz      short loc_18001D8AF
0x18001d8a6  mov     rcx, r14; lpCriticalSection
0x18001d8a9  call    cs:__imp_LeaveCriticalSection
0x18001d8af  test    sil, sil
0x18001d8b2  jz      short loc_18001D8BC
0x18001d8b4  mov     rcx, rbx
0x18001d8b7  call    ?_Initialization@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@AEAAXXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::_Initialization(void)
0x18001d8bc  add     rsp, 50h
0x18001d8c0  pop     r15
0x18001d8c2  pop     r14
0x18001d8c4  pop     r12
0x18001d8c6  pop     rsi
0x18001d8c7  pop     rbx
0x18001d8c8  retn
```
