# UsageAndQualityInsights::Database::FactStoreDatabase::CreateTableIfNotExists(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180046cf0`
- end: `0x180047172`
- name: `?CreateTableIfNotExists@FactStoreDatabase@Database@UsageAndQualityInsights@@QEAA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0@Z`
- size: `1154`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004aec4`

## callees

- `0x180003fdc`
- `0x180008320`
- `0x1800107b0`
- `0x1800149fc`
- `0x180016dcc`
- `0x180018e64`
- `0x18001c3d0`
- `0x18002b258`
- `0x18002b2b0`
- `0x18002be8c`
- `0x180041690`
- `0x18004368c`
- `0x180043764`
- `0x180046cf0`
- `0x18004de34`
- `0x18004dff0`
- `0x1800c1ee0`
- `0x1800c3160`
- `0x1800c3f90`
- `0x1800c4690`
- `0x1800c4750`
- `0x1800c6d20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046e96`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046ecc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046f03`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046ffd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004702d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047063`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047099`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046e96`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046ecc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046f03`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046ffd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004702d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047063`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047099`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046dbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046dbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046d58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046df8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047119`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046d58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046df8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047119`

## string_xrefs

- `0x180046d12`: `CreateTableIfNotExists`
- `0x180046fd6`: `Failed to create table '%s': %s (sqlcode: %d)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
char __fastcall UsageAndQualityInsights::Database::FactStoreDatabase::CreateTableIfNotExists(
        __int64 a1,
        void **a2,
        _QWORD *a3)
{
  __int64 *v6; // rax
  __int64 v7; // rdi
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  char v11; // bl
  __int64 *Local; // rax
  _BYTE *v13; // rcx
  __int64 v14; // rax
  struct _RTL_CRITICAL_SECTION *v15; // rdi
  struct _RTL_CRITICAL_SECTION *v16; // rdi
  struct _RTL_CRITICAL_SECTION *v17; // rdi
  struct _RTL_CRITICAL_SECTION *v18; // rdi
  int v19; // eax
  int v20; // esi
  LPVOID v21; // r15
  const char *v22; // r8
  struct _RTL_CRITICAL_SECTION *v23; // rdi
  struct _RTL_CRITICAL_SECTION *v24; // rdi
  struct _RTL_CRITICAL_SECTION *v25; // rdi
  struct _RTL_CRITICAL_SECTION *v26; // rdi
  struct sqlite3 *v28; // rax
  struct sqlite3_stmt *v29; // [rsp+30h] [rbp-79h] BYREF
  void **v30; // [rsp+40h] [rbp-69h] BYREF
  _QWORD v31[2]; // [rsp+48h] [rbp-61h] BYREF
  __int64 v32; // [rsp+58h] [rbp-51h]
  DWORD CurrentThreadId; // [rsp+60h] [rbp-49h]
  __int64 v34; // [rsp+68h] [rbp-41h]
  char v35; // [rsp+70h] [rbp-39h]
  LPVOID v36; // [rsp+78h] [rbp-31h]
  LPVOID pv; // [rsp+80h] [rbp-29h] BYREF
  __int64 v38; // [rsp+88h] [rbp-21h]
  _BYTE pExceptionObject[96]; // [rsp+A0h] [rbp-9h] BYREF
  LPVOID v40; // [rsp+128h] [rbp+7Fh] BYREF

  UsageAndQualityInsightsTraceLogging::TraceLoggingInfo("CreateTableIfNotExists");
  v6 = tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>,>(&pv);
  v7 = *v6;
  *v6 = 0;
  v8 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>::~merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>(v8);
    CoTaskMemFree(v8);
  }
  tip2::details::shared_data<0,0,0>::start(v7 + 8, &pv);
  v30 = &tip2::test_watcher<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::`vftable';
  v31[0] = 0;
  v31[1] = &v30;
  v32 = 0;
  CurrentThreadId = 0;
  v34 = 0;
  v35 = 0;
  v11 = 1;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(v9) = 1;
    Local = (__int64 *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                         v10,
                         v9);
    v31[0] = Local;
    if ( Local )
    {
      v32 = *Local;
      *Local = (__int64)v31;
      CurrentThreadId = GetCurrentThreadId();
    }
  }
  else
  {
    v31[0] = 0;
  }
  v36 = (LPVOID)v7;
  if ( v7 )
  {
    _InterlockedAdd((volatile signed __int32 *)(v7 + 280), 1u);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 280), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>::~merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>((struct _RTL_CRITICAL_SECTION *)v7);
      CoTaskMemFree((LPVOID)v7);
    }
  }
  pv = "SELECT COUNT(name) FROM sqlite_master WHERE type='table' AND name=?;";
  v38 = 68;
  sqlite3_prepare_v2_entire_cpp(&v29, *(_QWORD *)(a1 + 32), &pv);
  if ( (unsigned __int64)a2[3] <= 0xF )
    v13 = a2;
  else
    v13 = *a2;
  v14 = -1;
  do
    ++v14;
  while ( v13[v14] );
  pv = v13;
  v38 = v14;
  sqlite3_bind_text_cpp(v29, 1, &pv);
  if ( (unsigned int)sqlite3_step(v29) == 100 && (int)sqlite3_column_int(v29, 0) > 0 )
  {
    v15 = (struct _RTL_CRITICAL_SECTION *)v36;
    v40 = v36;
    if ( v36 )
      _InterlockedAdd((volatile signed __int32 *)v36 + 70, 1u);
    EnterCriticalSection(v15 + 5);
    ++LODWORD(v15[6].DebugInfo);
    LOBYTE(v15[6].SpinCount) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>((__int64 *)&v40);
    v16 = (struct _RTL_CRITICAL_SECTION *)v36;
    v40 = v36;
    if ( v36 )
      _InterlockedAdd((volatile signed __int32 *)v36 + 70, 1u);
    EnterCriticalSection(v16 + 5);
    ++LODWORD(v16[6].DebugInfo);
    HIDWORD(v16[6].SpinCount) = 0;
    tip2::test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>((__int64 *)&v40);
    v17 = (struct _RTL_CRITICAL_SECTION *)v36;
    v40 = v36;
    if ( v36 )
      _InterlockedAdd((volatile signed __int32 *)v36 + 70, 1u);
    EnterCriticalSection(v17 + 5);
    ++LODWORD(v17[6].DebugInfo);
    LODWORD(v17[1].SpinCount) |= 0xB00u;
    if ( *(_QWORD *)&v17[6].LockCount )
      tip2::details::shared_data<0,0,0>::complete_helper(&v17->LockCount, 10);
    tip2::test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>((__int64 *)&v40);
    if ( v29 )
      unique_sqlite3_stmt::release_or_terminate(v29);
    v18 = (struct _RTL_CRITICAL_SECTION *)v36;
    if ( v36 )
    {
LABEL_61:
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v36 + 70, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>::~merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>(v18);
        CoTaskMemFree(v18);
      }
    }
  }
  else
  {
    if ( v29 )
    {
      if ( (unsigned int)sqlite3_finalize() )
      {
        v28 = (struct sqlite3 *)sqlite3_db_handle(v29);
        sqlite3_error::sqlite3_error((sqlite3_error *)&pv, v28);
        sqlite3_error::sqlite3_error(pExceptionObject, &pv);
        throw (sqlite3_error *)pExceptionObject;
      }
      v29 = 0;
    }
    v40 = 0;
    if ( a3[3] > 0xFu )
      a3 = (_QWORD *)*a3;
    v19 = sqlite3_exec(*(_QWORD *)(a1 + 32), (_DWORD)a3, 0, 0, (__int64)&v40);
    v20 = v19;
    v21 = v40;
    if ( v19 == 101 || !v19 )
    {
      v24 = (struct _RTL_CRITICAL_SECTION *)v36;
      v40 = v36;
      if ( v36 )
        _InterlockedAdd((volatile signed __int32 *)v36 + 70, 1u);
      EnterCriticalSection(v24 + 5);
      ++LODWORD(v24[6].DebugInfo);
      LOBYTE(v24[6].SpinCount) = 1;
    }
    else
    {
      v22 = "unknown error";
      if ( v40 )
        v22 = (const char *)v40;
      if ( (unsigned __int64)a2[3] > 0xF )
        a2 = (void **)*a2;
      UsageAndQualityInsightsCoreLogging::TraceLoggingError(
        "Failed to create table '%s': %s (sqlcode: %d)",
        (const char *)a2,
        v22,
        v19);
      v23 = (struct _RTL_CRITICAL_SECTION *)v36;
      v40 = v36;
      if ( v36 )
        _InterlockedAdd((volatile signed __int32 *)v36 + 70, 1u);
      EnterCriticalSection(v23 + 5);
      ++LODWORD(v23[6].DebugInfo);
      LOBYTE(v23[6].SpinCount) = 0;
    }
    tip2::test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>((__int64 *)&v40);
    v25 = (struct _RTL_CRITICAL_SECTION *)v36;
    v40 = v36;
    if ( v36 )
      _InterlockedAdd((volatile signed __int32 *)v36 + 70, 1u);
    EnterCriticalSection(v25 + 5);
    ++LODWORD(v25[6].DebugInfo);
    HIDWORD(v25[6].SpinCount) = v20;
    tip2::test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>((__int64 *)&v40);
    v26 = (struct _RTL_CRITICAL_SECTION *)v36;
    v40 = v36;
    if ( v36 )
      _InterlockedAdd((volatile signed __int32 *)v36 + 70, 1u);
    EnterCriticalSection(v26 + 5);
    ++LODWORD(v26[6].DebugInfo);
    LODWORD(v26[1].SpinCount) |= 0xB00u;
    if ( *(_QWORD *)&v26[6].LockCount )
      tip2::details::shared_data<0,0,0>::complete_helper(&v26->LockCount, 10);
    tip2::test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>((__int64 *)&v40);
    if ( v20 && v20 != 101 )
      v11 = 0;
    if ( v21 )
      sqlite3_free(v21);
    if ( v29 )
      unique_sqlite3_stmt::release_or_terminate(v29);
    v18 = (struct _RTL_CRITICAL_SECTION *)v36;
    if ( v36 )
      goto LABEL_61;
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v31);
  return v11;
}

```

## disassembly

```asm
0x180046cf0  push    rbp
0x180046cf2  push    rbx
0x180046cf3  push    rsi
0x180046cf4  push    rdi
0x180046cf5  push    r12
0x180046cf7  push    r13
0x180046cf9  push    r14
0x180046cfb  push    r15
0x180046cfd  lea     rbp, [rsp-1Fh]
0x180046d02  sub     rsp, 0C8h
0x180046d09  mov     rsi, r8
0x180046d0c  mov     r14, rdx
0x180046d0f  mov     r15, rcx
0x180046d12  lea     rcx, aCreatetableifn; "CreateTableIfNotExists"
0x180046d19  call    ?TraceLoggingInfo@UsageAndQualityInsightsTraceLogging@@SAXPEBDZZ; UsageAndQualityInsightsTraceLogging::TraceLoggingInfo(char const *,...)
0x180046d1e  lea     rcx, [rbp+57h+pv]
0x180046d22  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_UQIAssertTableExistsTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_UQIAssertTableExistsTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>,>(void)
0x180046d27  mov     rdi, [rax]
0x180046d2a  xor     r12d, r12d
0x180046d2d  mov     [rax], r12
0x180046d30  or      r13, 0FFFFFFFFFFFFFFFFh
0x180046d34  mov     rbx, [rbp+57h+pv]
0x180046d38  test    rbx, rbx
0x180046d3b  jz      short loc_180046D5E
0x180046d3d  mov     eax, r13d
0x180046d40  lock xadd [rbx+118h], eax
0x180046d48  add     eax, r13d
0x180046d4b  jnz     short loc_180046D5E
0x180046d4d  mov     rcx, rbx
0x180046d50  call    ??1?$merged_data@U_tip_UQIAssertTableExistsTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>::~merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>(void)
0x180046d55  mov     rcx, rbx; pv
0x180046d58  call    cs:__imp_CoTaskMemFree
0x180046d5e  lea     rcx, [rdi+8]
0x180046d62  lea     rdx, [rbp+57h+pv]
0x180046d66  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x180046d6b  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::`vftable'
0x180046d72  mov     [rbp+57h+var_C0], rax
0x180046d76  mov     [rbp+57h+var_B8], r12
0x180046d7a  lea     rax, [rbp+57h+var_C0]
0x180046d7e  mov     [rbp+57h+var_B0], rax
0x180046d82  mov     [rbp+57h+var_A8], r12
0x180046d86  mov     [rbp+57h+var_A0], r12d
0x180046d8a  mov     [rbp+57h+var_98], r12
0x180046d8e  mov     [rbp+57h+var_90], r12b
0x180046d92  mov     ebx, 1
0x180046d97  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r12; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180046d9e  jz      short loc_180046DC9
0x180046da0  mov     dl, bl
0x180046da2  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180046da7  mov     [rbp+57h+var_B8], rax
0x180046dab  test    rax, rax
0x180046dae  jz      short loc_180046DCD
0x180046db0  mov     rcx, [rax]
0x180046db3  mov     [rbp+57h+var_A8], rcx
0x180046db7  lea     rcx, [rbp+57h+var_B8]
0x180046dbb  mov     [rax], rcx
0x180046dbe  call    cs:__imp_GetCurrentThreadId
0x180046dc4  mov     [rbp+57h+var_A0], eax
0x180046dc7  jmp     short loc_180046DCD
0x180046dc9  mov     [rbp+57h+var_B8], r12
0x180046dcd  mov     [rbp+57h+var_88], rdi
0x180046dd1  test    rdi, rdi
0x180046dd4  jz      short loc_180046DFF
0x180046dd6  lock add [rdi+118h], ebx
0x180046ddd  mov     eax, r13d
0x180046de0  lock xadd [rdi+118h], eax
0x180046de8  add     eax, r13d
0x180046deb  jnz     short loc_180046DFF
0x180046ded  mov     rcx, rdi
0x180046df0  call    ??1?$merged_data@U_tip_UQIAssertTableExistsTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>::~merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>(void)
0x180046df5  mov     rcx, rdi; pv
0x180046df8  call    cs:__imp_CoTaskMemFree
0x180046dfe  nop
0x180046dff  lea     rax, aSelectCountNam; "SELECT COUNT(name) FROM sqlite_master W"...
0x180046e06  mov     [rbp+57h+pv], rax
0x180046e0a  mov     [rbp+57h+var_78], 44h ; 'D'
0x180046e12  lea     r8, [rbp+57h+pv]
0x180046e16  mov     rdx, [r15+20h]
0x180046e1a  lea     rcx, [rbp+57h+var_D0]
0x180046e1e  call    ?sqlite3_prepare_v2_entire_cpp@@YA?AUunique_sqlite3_stmt@@PEAUsqlite3@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z; sqlite3_prepare_v2_entire_cpp(sqlite3 *,std::string_view)
0x180046e23  nop
0x180046e24  cmp     qword ptr [r14+18h], 0Fh
0x180046e29  jbe     short loc_180046E30
0x180046e2b  mov     rcx, [r14]
0x180046e2e  jmp     short loc_180046E33
0x180046e30  mov     rcx, r14
0x180046e33  mov     rax, r13
0x180046e36  inc     rax
0x180046e39  cmp     [rcx+rax], r12b
0x180046e3d  jnz     short loc_180046E36
0x180046e3f  mov     [rbp+57h+pv], rcx
0x180046e43  mov     [rbp+57h+var_78], rax
0x180046e47  lea     r8, [rbp+57h+pv]
0x180046e4b  mov     edx, ebx
0x180046e4d  mov     rcx, [rbp+57h+var_D0]
0x180046e51  call    ?sqlite3_bind_text_cpp@@YAXPEAUsqlite3_stmt@@HV?$basic_string_view@DU?$char_traits@D@std@@@std@@Q6AXPEAX@_E@Z; sqlite3_bind_text_cpp(sqlite3_stmt *,int,std::string_view,void (*const)(void *),...)
0x180046e56  mov     rcx, [rbp+57h+var_D0]
0x180046e5a  call    sqlite3_step
0x180046e5f  cmp     eax, 64h ; 'd'
0x180046e62  jnz     loc_180046F66
0x180046e68  xor     edx, edx
0x180046e6a  mov     rcx, [rbp+57h+var_D0]
0x180046e6e  call    sqlite3_column_int
0x180046e73  test    eax, eax
0x180046e75  jle     loc_180046F66
0x180046e7b  mov     rdi, [rbp+57h+var_88]
0x180046e7f  mov     [rbp+57h+arg_18], rdi
0x180046e83  test    rdi, rdi
0x180046e86  jz      short loc_180046E8F
0x180046e88  lock add [rdi+118h], ebx
0x180046e8f  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x180046e96  call    cs:__imp_EnterCriticalSection
0x180046e9c  add     [rdi+0F0h], ebx
0x180046ea2  mov     [rdi+110h], bl
0x180046ea8  lea     rcx, [rbp+57h+arg_18]
0x180046eac  call    ??1?$test_data_control@V?$merged_data@U_tip_UQIAssertTableExistsTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>(void)
0x180046eb1  mov     rdi, [rbp+57h+var_88]
0x180046eb5  mov     [rbp+57h+arg_18], rdi
0x180046eb9  test    rdi, rdi
0x180046ebc  jz      short loc_180046EC5
0x180046ebe  lock add [rdi+118h], ebx
0x180046ec5  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x180046ecc  call    cs:__imp_EnterCriticalSection
0x180046ed2  add     [rdi+0F0h], ebx
0x180046ed8  mov     [rdi+114h], r12d
0x180046edf  lea     rcx, [rbp+57h+arg_18]
0x180046ee3  call    ??1?$test_data_control@V?$merged_data@U_tip_UQIAssertTableExistsTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>(void)
0x180046ee8  mov     rdi, [rbp+57h+var_88]
0x180046eec  mov     [rbp+57h+arg_18], rdi
0x180046ef0  test    rdi, rdi
0x180046ef3  jz      short loc_180046EFC
0x180046ef5  lock add [rdi+118h], ebx
0x180046efc  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x180046f03  call    cs:__imp_EnterCriticalSection
0x180046f09  add     [rdi+0F0h], ebx
0x180046f0f  or      dword ptr [rdi+48h], 0B00h
0x180046f16  cmp     [rdi+0F8h], r12
0x180046f1d  jz      short loc_180046F2D
0x180046f1f  mov     edx, 0Ah
0x180046f24  lea     rcx, [rdi+8]
0x180046f28  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180046f2d  lea     rcx, [rbp+57h+arg_18]
0x180046f31  call    ??1?$test_data_control@V?$merged_data@U_tip_UQIAssertTableExistsTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>(void)
0x180046f36  nop
0x180046f37  mov     rcx, [rbp+57h+var_D0]; struct sqlite3_stmt *
0x180046f3b  test    rcx, rcx
0x180046f3e  jz      short loc_180046F46
0x180046f40  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x180046f45  nop
0x180046f46  mov     rdi, [rbp+57h+var_88]
0x180046f4a  test    rdi, rdi
0x180046f4d  jz      loc_18004711F
0x180046f53  mov     edx, r13d
0x180046f56  lock xadd [rdi+118h], edx
0x180046f5e  add     edx, r13d
0x180046f61  jmp     loc_18004710C
0x180046f66  mov     rcx, [rbp+57h+var_D0]
0x180046f6a  test    rcx, rcx
0x180046f6d  jz      short loc_180046F80
0x180046f6f  call    sqlite3_finalize
0x180046f74  test    eax, eax
0x180046f76  jnz     loc_18004713E
0x180046f7c  mov     [rbp+57h+var_D0], r12
0x180046f80  mov     [rbp+57h+arg_18], r12
0x180046f84  cmp     qword ptr [rsi+18h], 0Fh
0x180046f89  jbe     short loc_180046F8E
0x180046f8b  mov     rsi, [rsi]
0x180046f8e  lea     rax, [rbp+57h+arg_18]
0x180046f92  mov     [rsp+100h+var_E0], rax
0x180046f97  xor     r9d, r9d
0x180046f9a  xor     r8d, r8d
0x180046f9d  mov     rdx, rsi
0x180046fa0  mov     rcx, [r15+20h]
0x180046fa4  call    sqlite3_exec
0x180046fa9  mov     esi, eax
0x180046fab  mov     r15, [rbp+57h+arg_18]
0x180046faf  cmp     eax, 65h ; 'e'
0x180046fb2  jz      short loc_180047012
0x180046fb4  test    eax, eax
0x180046fb6  jz      short loc_180047012
0x180046fb8  lea     r8, aUnknownError; "unknown error"
0x180046fbf  test    r15, r15
0x180046fc2  cmovnz  r8, r15
0x180046fc6  cmp     qword ptr [r14+18h], 0Fh
0x180046fcb  jbe     short loc_180046FD0
0x180046fcd  mov     r14, [r14]
0x180046fd0  mov     r9d, esi
0x180046fd3  mov     rdx, r14
0x180046fd6  lea     rcx, aFailedToCreate; "Failed to create table '%s': %s (sqlcod"...
0x180046fdd  call    ?TraceLoggingError@UsageAndQualityInsightsCoreLogging@@SAXPEBDZZ; UsageAndQualityInsightsCoreLogging::TraceLoggingError(char const *,...)
0x180046fe2  mov     rdi, [rbp+57h+var_88]
0x180046fe6  mov     [rbp+57h+arg_18], rdi
0x180046fea  test    rdi, rdi
0x180046fed  jz      short loc_180046FF6
0x180046fef  lock add [rdi+118h], ebx
0x180046ff6  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x180046ffd  call    cs:__imp_EnterCriticalSection
0x180047003  add     [rdi+0F0h], ebx
0x180047009  mov     [rdi+110h], r12b
0x180047010  jmp     short loc_18004703F
0x180047012  mov     rdi, [rbp+57h+var_88]
0x180047016  mov     [rbp+57h+arg_18], rdi
0x18004701a  test    rdi, rdi
0x18004701d  jz      short loc_180047026
0x18004701f  lock add [rdi+118h], ebx
0x180047026  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x18004702d  call    cs:__imp_EnterCriticalSection
0x180047033  add     [rdi+0F0h], ebx
0x180047039  mov     [rdi+110h], bl
0x18004703f  lea     rcx, [rbp+57h+arg_18]
0x180047043  call    ??1?$test_data_control@V?$merged_data@U_tip_UQIAssertTableExistsTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>(void)
0x180047048  mov     rdi, [rbp+57h+var_88]
0x18004704c  mov     [rbp+57h+arg_18], rdi
0x180047050  test    rdi, rdi
0x180047053  jz      short loc_18004705C
0x180047055  lock add [rdi+118h], ebx
0x18004705c  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x180047063  call    cs:__imp_EnterCriticalSection
0x180047069  add     [rdi+0F0h], ebx
0x18004706f  mov     [rdi+114h], esi
0x180047075  lea     rcx, [rbp+57h+arg_18]
0x180047079  call    ??1?$test_data_control@V?$merged_data@U_tip_UQIAssertTableExistsTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>(void)
0x18004707e  mov     rdi, [rbp+57h+var_88]
0x180047082  mov     [rbp+57h+arg_18], rdi
0x180047086  test    rdi, rdi
0x180047089  jz      short loc_180047092
0x18004708b  lock add [rdi+118h], ebx
0x180047092  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x180047099  call    cs:__imp_EnterCriticalSection
0x18004709f  add     [rdi+0F0h], ebx
0x1800470a5  or      dword ptr [rdi+48h], 0B00h
0x1800470ac  cmp     [rdi+0F8h], r12
0x1800470b3  jz      short loc_1800470C3
0x1800470b5  mov     edx, 0Ah
0x1800470ba  lea     rcx, [rdi+8]
0x1800470be  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x1800470c3  lea     rcx, [rbp+57h+arg_18]
0x1800470c7  call    ??1?$test_data_control@V?$merged_data@U_tip_UQIAssertTableExistsTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>>(void)
0x1800470cc  test    esi, esi
0x1800470ce  jz      short loc_1800470D8
0x1800470d0  cmp     esi, 65h ; 'e'
0x1800470d3  jz      short loc_1800470D8
0x1800470d5  mov     bl, r12b
0x1800470d8  test    r15, r15
0x1800470db  jz      short loc_1800470E6
0x1800470dd  mov     rcx, r15
0x1800470e0  call    sqlite3_free
0x1800470e5  nop
0x1800470e6  mov     rcx, [rbp+57h+var_D0]; struct sqlite3_stmt *
0x1800470ea  test    rcx, rcx
0x1800470ed  jz      short loc_1800470F5
0x1800470ef  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x1800470f4  nop
0x1800470f5  mov     rdi, [rbp+57h+var_88]
0x1800470f9  test    rdi, rdi
0x1800470fc  jz      short loc_18004711F
0x1800470fe  mov     eax, r13d
0x180047101  lock xadd [rdi+118h], eax
0x180047109  add     eax, r13d
0x18004710c  jnz     short loc_18004711F
0x18004710e  mov     rcx, rdi
0x180047111  call    ??1?$merged_data@U_tip_UQIAssertTableExistsTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>::~merged_data<_tip_UQIAssertTableExistsTipTest,_tip_UQIAssertTableExistsTipTest>(void)
0x180047116  mov     rcx, rdi; pv
0x180047119  call    cs:__imp_CoTaskMemFree
0x18004711f  lea     rcx, [rbp+57h+var_B8]; this
0x180047123  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180047128  mov     al, bl
0x18004712a  add     rsp, 0C8h
0x180047131  pop     r15
0x180047133  pop     r14
0x180047135  pop     r13
0x180047137  pop     r12
0x180047139  pop     rdi
0x18004713a  pop     rsi
0x18004713b  pop     rbx
0x18004713c  pop     rbp
0x18004713d  retn
0x18004713e  mov     rcx, [rbp+57h+var_D0]
0x180047142  call    sqlite3_db_handle
0x180047147  mov     rdx, rax; struct sqlite3 *
0x18004714a  lea     rcx, [rbp+57h+pv]; this
0x18004714e  call    ??0sqlite3_error@@QEAA@PEAUsqlite3@@@Z; sqlite3_error::sqlite3_error(sqlite3 *)
0x180047153  nop
0x180047154  lea     rdx, [rbp+57h+pv]
0x180047158  lea     rcx, [rbp+57h+pExceptionObject]
0x18004715c  call    ??0sqlite3_error@@QEAA@$$QEAU0@@Z; sqlite3_error::sqlite3_error(sqlite3_error &&)
0x180047161  lea     rdx, _TI2?AUsqlite3_error@@; pThrowInfo
0x180047168  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004716c  call    _CxxThrowException_0
```
