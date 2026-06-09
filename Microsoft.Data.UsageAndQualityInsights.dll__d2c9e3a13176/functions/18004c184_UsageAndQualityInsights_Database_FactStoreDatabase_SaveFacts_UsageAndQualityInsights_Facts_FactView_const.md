# UsageAndQualityInsights::Database::FactStoreDatabase::SaveFacts(UsageAndQualityInsights::Facts::FactView const &)

- ea: `0x18004c184`
- end: `0x18004c3d5`
- name: `?SaveFacts@FactStoreDatabase@Database@UsageAndQualityInsights@@QEAAXAEBUFactView@Facts@3@@Z`
- size: `593`
- prototype: `void __fastcall(UsageAndQualityInsights::Database::FactStoreDatabase *__hidden this, const struct UsageAndQualityInsights::Facts::FactView *)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800f58d4`

## callees

- `0x1800033d0`
- `0x180008320`
- `0x1800107b0`
- `0x180013c48`
- `0x180013e44`
- `0x180013ff8`
- `0x1800149fc`
- `0x180016dcc`
- `0x180018e64`
- `0x18002b470`
- `0x18003ac7c`
- `0x180041758`
- `0x1800435fc`
- `0x180043ff0`
- `0x180047688`
- `0x180049250`
- `0x18004aec4`
- `0x18004c184`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c32b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c32b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c26b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c26b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c1f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c2aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c3a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c1f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c2aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c3a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall UsageAndQualityInsights::Database::FactStoreDatabase::SaveFacts(
        UsageAndQualityInsights::Database::FactStoreDatabase *this,
        const struct UsageAndQualityInsights::Facts::FactView *a2)
{
  __int64 *v4; // rax
  __int64 v5; // rbx
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 *Local; // rax
  _QWORD *v10; // rdi
  _QWORD *i; // rbx
  struct _RTL_CRITICAL_SECTION *v12; // rbx
  struct _RTL_CRITICAL_SECTION *v13; // rbx
  void **v14; // [rsp+30h] [rbp-89h] BYREF
  _QWORD v15[2]; // [rsp+38h] [rbp-81h] BYREF
  __int64 v16; // [rsp+48h] [rbp-71h]
  DWORD CurrentThreadId; // [rsp+50h] [rbp-69h]
  __int64 v18; // [rsp+58h] [rbp-61h]
  char v19; // [rsp+60h] [rbp-59h]
  LPVOID v20; // [rsp+68h] [rbp-51h]
  _BYTE v21[8]; // [rsp+70h] [rbp-49h] BYREF
  _QWORD *v22; // [rsp+78h] [rbp-41h] BYREF
  _BYTE v23[40]; // [rsp+88h] [rbp-31h] BYREF
  LPVOID pv[4]; // [rsp+B0h] [rbp-9h] BYREF
  char *v25[4]; // [rsp+D0h] [rbp+17h] BYREF

  UsageAndQualityInsightsTraceLogging::TraceLoggingInfo("SaveAllFacts");
  v4 = tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>,>(pv);
  v5 = *v4;
  *v4 = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)pv[0];
  if ( pv[0] && _InterlockedExchangeAdd((volatile signed __int32 *)pv[0] + 68, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(v6);
    CoTaskMemFree(v6);
  }
  tip2::details::shared_data<0,0,0>::start(v5 + 8, pv);
  v14 = &tip2::test_watcher<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::`vftable';
  v15[0] = 0;
  v15[1] = &v14;
  v16 = 0;
  CurrentThreadId = 0;
  v18 = 0;
  v19 = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(v7) = 1;
    Local = (__int64 *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                         v8,
                         v7);
    v15[0] = Local;
    if ( Local )
    {
      v16 = *Local;
      *Local = (__int64)v15;
      CurrentThreadId = GetCurrentThreadId();
    }
  }
  else
  {
    v15[0] = 0;
  }
  v20 = (LPVOID)v5;
  if ( v5 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 272));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 272), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>((struct _RTL_CRITICAL_SECTION *)v5);
      CoTaskMemFree((LPVOID)v5);
    }
  }
  UsageAndQualityInsights::Facts::FactView::SplitBy__UsageAndQualityInsights::Database::FactStoreDatabase::SaveFacts_::_2_::_lambda_1___(
    a2,
    v21);
  UsageAndQualityInsights::Database::FactStoreDatabase::EnsureOSInfoTableIsUpToDate(this);
  UsageAndQualityInsights::Database::FactStoreDatabase::GetLatestOsInfo(this, v25);
  v10 = v22;
  for ( i = (_QWORD *)*v22; i != v10; i = (_QWORD *)*i )
  {
    UsageAndQualityInsights::Database::FactTableName::operator std::string(i + 2, pv);
    UsageAndQualityInsights::Database::FactStoreDatabase::SaveFacts(this, i + 3, pv, v25);
    std::string::~string((char **)pv);
  }
  v12 = (struct _RTL_CRITICAL_SECTION *)v20;
  pv[0] = v20;
  if ( v20 )
    _InterlockedIncrement((volatile signed __int32 *)v20 + 68);
  EnterCriticalSection(v12 + 5);
  ++LODWORD(v12[6].DebugInfo);
  LODWORD(v12[1].SpinCount) |= 0xB00u;
  if ( *(_QWORD *)&v12[6].LockCount )
    tip2::details::shared_data<0,0,0>::complete_helper(&v12->LockCount, 10);
  tip2::test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>((__int64 *)pv);
  std::string::~string(v25);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<UsageAndQualityInsights::Database::FactTableName const,UsageAndQualityInsights::Facts::FactView>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<UsageAndQualityInsights::Database::FactTableName const,UsageAndQualityInsights::Facts::FactView>>>>>>(v23);
  std::list<std::pair<UsageAndQualityInsights::Database::FactTableName const,UsageAndQualityInsights::Facts::FactView>>::~list<std::pair<UsageAndQualityInsights::Database::FactTableName const,UsageAndQualityInsights::Facts::FactView>>(&v22);
  v13 = (struct _RTL_CRITICAL_SECTION *)v20;
  if ( v20 && _InterlockedExchangeAdd((volatile signed __int32 *)v20 + 68, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(v13);
    CoTaskMemFree(v13);
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v15);
}

```

## disassembly

```asm
0x18004c184  mov     [rsp-8+arg_10], rbx
0x18004c189  mov     [rsp-8+arg_18], rsi
0x18004c18e  push    rbp
0x18004c18f  push    rdi
0x18004c190  push    r14
0x18004c192  lea     rbp, [rsp-47h]
0x18004c197  sub     rsp, 100h
0x18004c19e  mov     rax, cs:__security_cookie
0x18004c1a5  xor     rax, rsp
0x18004c1a8  mov     [rbp+57h+var_20], rax
0x18004c1ac  mov     rsi, rdx
0x18004c1af  mov     r14, rcx
0x18004c1b2  lea     rcx, aSaveallfacts; "SaveAllFacts"
0x18004c1b9  call    ?TraceLoggingInfo@UsageAndQualityInsightsTraceLogging@@SAXPEBDZZ; UsageAndQualityInsightsTraceLogging::TraceLoggingInfo(char const *,...)
0x18004c1be  lea     rcx, [rbp+57h+pv]
0x18004c1c2  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_UQISaveFactsToFactStoreTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_UQISaveFactsToFactStoreTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>,>(void)
0x18004c1c7  mov     rbx, [rax]
0x18004c1ca  mov     qword ptr [rax], 0
0x18004c1d1  mov     rdi, [rbp+57h+pv]
0x18004c1d5  test    rdi, rdi
0x18004c1d8  jz      short loc_18004C1FB
0x18004c1da  or      eax, 0FFFFFFFFh
0x18004c1dd  lock xadd [rdi+110h], eax
0x18004c1e5  cmp     eax, 1
0x18004c1e8  jnz     short loc_18004C1FB
0x18004c1ea  mov     rcx, rdi
0x18004c1ed  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x18004c1f2  mov     rcx, rdi; pv
0x18004c1f5  call    cs:__imp_CoTaskMemFree
0x18004c1fb  lea     rcx, [rbx+8]
0x18004c1ff  lea     rdx, [rbp+57h+pv]
0x18004c203  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18004c208  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::`vftable'
0x18004c20f  mov     [rsp+110h+var_E0], rax
0x18004c214  mov     [rsp+110h+var_D8], 0
0x18004c21d  lea     rax, [rsp+110h+var_E0]
0x18004c222  mov     [rbp+57h+var_D0], rax
0x18004c226  mov     [rbp+57h+var_C8], 0
0x18004c22e  mov     [rbp+57h+var_C0], 0
0x18004c235  mov     [rbp+57h+var_B8], 0
0x18004c23d  mov     [rbp+57h+var_B0], 0
0x18004c241  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18004c249  jz      short loc_18004C276
0x18004c24b  mov     dl, 1
0x18004c24d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18004c252  mov     [rsp+110h+var_D8], rax
0x18004c257  test    rax, rax
0x18004c25a  jz      short loc_18004C27F
0x18004c25c  mov     rcx, [rax]
0x18004c25f  mov     [rbp+57h+var_C8], rcx
0x18004c263  lea     rcx, [rsp+110h+var_D8]
0x18004c268  mov     [rax], rcx
0x18004c26b  call    cs:__imp_GetCurrentThreadId
0x18004c271  mov     [rbp+57h+var_C0], eax
0x18004c274  jmp     short loc_18004C27F
0x18004c276  mov     [rsp+110h+var_D8], 0
0x18004c27f  mov     [rbp+57h+var_A8], rbx
0x18004c283  test    rbx, rbx
0x18004c286  jz      short loc_18004C2B1
0x18004c288  lock inc dword ptr [rbx+110h]
0x18004c28f  or      eax, 0FFFFFFFFh
0x18004c292  lock xadd [rbx+110h], eax
0x18004c29a  cmp     eax, 1
0x18004c29d  jnz     short loc_18004C2B1
0x18004c29f  mov     rcx, rbx
0x18004c2a2  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x18004c2a7  mov     rcx, rbx; pv
0x18004c2aa  call    cs:__imp_CoTaskMemFree
0x18004c2b0  nop
0x18004c2b1  lea     rdx, [rbp+57h+var_A0]
0x18004c2b5  mov     rcx, rsi
0x18004c2b8  call    UsageAndQualityInsights__Facts__FactView__SplitBy__UsageAndQualityInsights__Database__FactStoreDatabase__SaveFacts____2____lambda_1___
0x18004c2bd  nop
0x18004c2be  mov     rcx, r14; this
0x18004c2c1  call    ?EnsureOSInfoTableIsUpToDate@FactStoreDatabase@Database@UsageAndQualityInsights@@QEAAXXZ; UsageAndQualityInsights::Database::FactStoreDatabase::EnsureOSInfoTableIsUpToDate(void)
0x18004c2c6  lea     rdx, [rbp+57h+var_40]
0x18004c2ca  mov     rcx, r14
0x18004c2cd  call    ?GetLatestOsInfo@FactStoreDatabase@Database@UsageAndQualityInsights@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; UsageAndQualityInsights::Database::FactStoreDatabase::GetLatestOsInfo(void)
0x18004c2d2  nop
0x18004c2d3  mov     rdi, [rbp+57h+var_98]
0x18004c2d7  mov     rbx, [rdi]
0x18004c2da  cmp     rbx, rdi
0x18004c2dd  jz      short loc_18004C310
0x18004c2df  lea     rdx, [rbp+57h+pv]
0x18004c2e3  lea     rcx, [rbx+10h]
0x18004c2e7  call    ??BFactTableName@Database@UsageAndQualityInsights@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; UsageAndQualityInsights::Database::FactTableName::operator std::string(void)
0x18004c2ec  nop
0x18004c2ed  lea     rdx, [rbx+18h]
0x18004c2f1  lea     r9, [rbp+57h+var_40]
0x18004c2f5  lea     r8, [rbp+57h+pv]
0x18004c2f9  mov     rcx, r14
0x18004c2fc  call    ?SaveFacts@FactStoreDatabase@Database@UsageAndQualityInsights@@AEAAXAEBUFactView@Facts@3@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; UsageAndQualityInsights::Database::FactStoreDatabase::SaveFacts(UsageAndQualityInsights::Facts::FactView const &,std::string const &,std::string const &)
0x18004c301  nop
0x18004c302  lea     rcx, [rbp+57h+pv]; void *
0x18004c306  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004c30b  mov     rbx, [rbx]
0x18004c30e  jmp     short loc_18004C2DA
0x18004c310  mov     rbx, [rbp+57h+var_A8]
0x18004c314  mov     [rbp+57h+pv], rbx
0x18004c318  test    rbx, rbx
0x18004c31b  jz      short loc_18004C324
0x18004c31d  lock inc dword ptr [rbx+110h]
0x18004c324  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18004c32b  call    cs:__imp_EnterCriticalSection
0x18004c331  inc     dword ptr [rbx+0F0h]
0x18004c337  or      dword ptr [rbx+48h], 0B00h
0x18004c33e  cmp     qword ptr [rbx+0F8h], 0
0x18004c346  jz      short loc_18004C356
0x18004c348  mov     edx, 0Ah
0x18004c34d  lea     rcx, [rbx+8]
0x18004c351  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18004c356  lea     rcx, [rbp+57h+pv]
0x18004c35a  call    ??1?$test_data_control@V?$merged_data@U_tip_UQISaveFactsToFactStoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>(void)
0x18004c35f  nop
0x18004c360  lea     rcx, [rbp+57h+var_40]; void *
0x18004c364  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004c369  nop
0x18004c36a  lea     rcx, [rbp+57h+var_88]
0x18004c36e  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUFactTableName@Database@UsageAndQualityInsights@@UFactView@Facts@3@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<UsageAndQualityInsights::Database::FactTableName const,UsageAndQualityInsights::Facts::FactView>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<UsageAndQualityInsights::Database::FactTableName const,UsageAndQualityInsights::Facts::FactView>>>>>>(void)
0x18004c373  lea     rcx, [rbp+57h+var_98]
0x18004c377  call    ??1?$list@U?$pair@$$CBUFactTableName@Database@UsageAndQualityInsights@@UFactView@Facts@3@@std@@V?$allocator@U?$pair@$$CBUFactTableName@Database@UsageAndQualityInsights@@UFactView@Facts@3@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<UsageAndQualityInsights::Database::FactTableName const,UsageAndQualityInsights::Facts::FactView>>::~list<std::pair<UsageAndQualityInsights::Database::FactTableName const,UsageAndQualityInsights::Facts::FactView>>(void)
0x18004c37c  nop
0x18004c37d  mov     rbx, [rbp+57h+var_A8]
0x18004c381  test    rbx, rbx
0x18004c384  jz      short loc_18004C3A7
0x18004c386  or      eax, 0FFFFFFFFh
0x18004c389  lock xadd [rbx+110h], eax
0x18004c391  cmp     eax, 1
0x18004c394  jnz     short loc_18004C3A7
0x18004c396  mov     rcx, rbx
0x18004c399  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x18004c39e  mov     rcx, rbx; pv
0x18004c3a1  call    cs:__imp_CoTaskMemFree
0x18004c3a7  lea     rcx, [rsp+110h+var_D8]; this
0x18004c3ac  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18004c3b1  mov     rcx, [rbp+57h+var_20]
0x18004c3b5  xor     rcx, rsp; StackCookie
0x18004c3b8  call    __security_check_cookie
0x18004c3bd  lea     r11, [rsp+110h+var_10]
0x18004c3c5  mov     rbx, [r11+30h]
0x18004c3c9  mov     rsi, [r11+38h]
0x18004c3cd  mov     rsp, r11
0x18004c3d0  pop     r14
0x18004c3d2  pop     rdi
0x18004c3d3  pop     rbp
0x18004c3d4  retn
```
