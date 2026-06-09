# UsageAndQualityInsights::Database::ServiceUsageDatabase::IncrementServiceUsage(UsageAndQualityInsights::Database::ServiceUsageKind)

- ea: `0x18002b6a8`
- end: `0x18002b96d`
- name: `?IncrementServiceUsage@ServiceUsageDatabase@Database@UsageAndQualityInsights@@QEAAXW4ServiceUsageKind@23@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c060`

## callees

- `0x180003fdc`
- `0x180008320`
- `0x180013c48`
- `0x1800149fc`
- `0x180016dcc`
- `0x180018e64`
- `0x18002b054`
- `0x18002b258`
- `0x18002b2b0`
- `0x18002b6a8`
- `0x18002be8c`
- `0x18004ec60`
- `0x18004fe0c`
- `0x18004fee0`
- `0x18009b670`
- `0x1800c0e30`
- `0x1800c3160`
- `0x1800c4690`
- `0x1800c6d20`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x18002b7c9`
- `msvcp_win!_Xtime_get_ticks` at `0x18002b7c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b8b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b8b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b88d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b88d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b76c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b76c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b6fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b7a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b901`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b6fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b7a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b901`

## string_xrefs

- `0x18002b811`: `INSERT INTO ServiceUsageHistory (Kind, Timestamp) VALUES (?, ?);`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall UsageAndQualityInsights::Database::ServiceUsageDatabase::IncrementServiceUsage(_QWORD *a1)
{
  __int64 *v2; // rax
  __int64 v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 *Local; // rax
  __int64 v8; // rsi
  LPVOID v9; // rbx
  _DWORD *v10; // rsi
  struct _RTL_CRITICAL_SECTION *v11; // r14
  struct _RTL_CRITICAL_SECTION *v12; // rbx
  struct sqlite3 *v13; // rdx
  __int64 v14; // rax
  _QWORD *v15; // rdx
  void **v16; // [rsp+40h] [rbp-D8h] BYREF
  _QWORD v17[2]; // [rsp+48h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+58h] [rbp-C0h]
  DWORD CurrentThreadId; // [rsp+60h] [rbp-B8h]
  __int64 v20; // [rsp+68h] [rbp-B0h]
  char v21; // [rsp+70h] [rbp-A8h]
  LPVOID v22; // [rsp+78h] [rbp-A0h]
  const std::exception *v23; // [rsp+80h] [rbp-98h] BYREF
  _BYTE v24[32]; // [rsp+88h] [rbp-90h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+A8h] [rbp-70h] BYREF
  _BYTE v26[80]; // [rsp+C8h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+130h] [rbp+18h] BYREF

  v2 = tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIIncrementServiceUsageTest,_tip_UQIIncrementServiceUsageTest>,>(&pv);
  v3 = *v2;
  *v2 = 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 68, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(v4);
    CoTaskMemFree(v4);
  }
  tip2::details::shared_data<0,0,0>::start(v3 + 8, v24);
  v16 = &tip2::test_watcher<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::`vftable';
  v17[0] = 0;
  v17[1] = &v16;
  v18 = 0;
  CurrentThreadId = 0;
  v20 = 0;
  v21 = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(v5) = 1;
    Local = (__int64 *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                         v6,
                         v5);
    v17[0] = Local;
    if ( Local )
    {
      v18 = *Local;
      *Local = (__int64)v17;
      CurrentThreadId = GetCurrentThreadId();
    }
  }
  else
  {
    v17[0] = 0;
  }
  v22 = (LPVOID)v3;
  if ( v3 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 272));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 272), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>((struct _RTL_CRITICAL_SECTION *)v3);
      CoTaskMemFree((LPVOID)v3);
    }
  }
  try
  {
    UsageAndQualityInsights::Database::UQIDatabase::BeginTransaction();
    pv = 0;
    v8 = _Xtime_get_ticks() / 10000;
    sqlite3LockAndPrepare(
      a1[4],
      (unsigned int)"INSERT INTO ServiceUsageHistory (Kind, Timestamp) VALUES (?, ?);",
      -1,
      128,
      0,
      (__int64)&pv,
      0);
    v9 = pv;
    sqlite3_bind_int64(pv, 1, 1);
    sqlite3_bind_int64(v9, 2, v8);
    sqlite3_step(v9);
    if ( v9 )
    {
      if ( (unsigned int)sqlite3_finalize(v9) )
      {
        v13 = (struct sqlite3 *)sqlite3_db_handle(v9);
        sqlite3_error::sqlite3_error((sqlite3_error *)v24, v13);
        sqlite3_error::sqlite3_error(pExceptionObject, v24);
        throw (sqlite3_error *)pExceptionObject;
      }
      pv = 0;
    }
    Transaction::Commit((Transaction *)v26);
    v10 = v22;
    v11 = (struct _RTL_CRITICAL_SECTION *)((char *)v22 + 200);
    EnterCriticalSection((LPCRITICAL_SECTION)v22 + 5);
    v10[18] |= 0x300u;
    if ( *((_QWORD *)v10 + 31) )
      tip2::details::shared_data<0,0,0>::complete_helper(v10 + 2, 2);
    if ( v11 )
      LeaveCriticalSection(v11);
    Transaction::~Transaction((Transaction *)v26);
    v12 = (struct _RTL_CRITICAL_SECTION *)v22;
    if ( v22 && _InterlockedExchangeAdd((volatile signed __int32 *)v22 + 68, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(v12);
      CoTaskMemFree(v12);
    }
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v17);
  }
  catch ( const std::exception *v23 )
  {
    v14 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v23 + 8LL))(v23);
    v15 = a1 + 5;
    if ( a1[8] > 7u )
      v15 = (_QWORD *)*v15;
    UsageAndQualityInsightsCoreLogging::TraceLoggingError(
      "IncrementServiceUsage failed for: %ws, exception: %s",
      v15,
      v14);
    return;
  }
  catch ( ... )
  {
    UsageAndQualityInsightsCoreLogging::TraceLoggingError("IncrementServiceUsage failed for: %ws, unknown exception");
  }
}

```

## disassembly

```asm
0x18002b6a8  mov     rax, rsp
0x18002b6ab  mov     [rax+20h], rbx
0x18002b6af  mov     [rax+8], rcx
0x18002b6b3  push    rsi
0x18002b6b4  push    r14
0x18002b6b6  push    r15
0x18002b6b8  sub     rsp, 100h
0x18002b6bf  mov     r14, rcx
0x18002b6c2  lea     rcx, [rax+18h]
0x18002b6c6  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_UQIIncrementServiceUsageTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_UQIIncrementServiceUsageTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIIncrementServiceUsageTest,_tip_UQIIncrementServiceUsageTest>,>(void)
0x18002b6cb  mov     rbx, [rax]
0x18002b6ce  xor     r15d, r15d
0x18002b6d1  mov     [rax], r15
0x18002b6d4  mov     rsi, [rsp+118h+pv]
0x18002b6dc  test    rsi, rsi
0x18002b6df  jz      short loc_18002B702
0x18002b6e1  or      eax, 0FFFFFFFFh
0x18002b6e4  lock xadd [rsi+110h], eax
0x18002b6ec  cmp     eax, 1
0x18002b6ef  jnz     short loc_18002B702
0x18002b6f1  mov     rcx, rsi
0x18002b6f4  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x18002b6f9  mov     rcx, rsi; pv
0x18002b6fc  call    cs:__imp_CoTaskMemFree
0x18002b702  lea     rcx, [rbx+8]
0x18002b706  lea     rdx, [rsp+118h+var_90]
0x18002b70e  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18002b713  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::`vftable'
0x18002b71a  mov     [rsp+118h+var_D8], rax
0x18002b71f  mov     [rsp+118h+var_D0], r15
0x18002b724  lea     rax, [rsp+118h+var_D8]
0x18002b729  mov     [rsp+118h+var_C8], rax
0x18002b72e  mov     [rsp+118h+var_C0], r15
0x18002b733  mov     [rsp+118h+var_B8], r15d
0x18002b738  mov     [rsp+118h+var_B0], r15
0x18002b73d  mov     [rsp+118h+var_A8], r15b
0x18002b742  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r15; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18002b749  jz      short loc_18002B778
0x18002b74b  mov     dl, 1
0x18002b74d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18002b752  mov     [rsp+118h+var_D0], rax
0x18002b757  test    rax, rax
0x18002b75a  jz      short loc_18002B77D
0x18002b75c  mov     rcx, [rax]
0x18002b75f  mov     [rsp+118h+var_C0], rcx
0x18002b764  lea     rcx, [rsp+118h+var_D0]
0x18002b769  mov     [rax], rcx
0x18002b76c  call    cs:__imp_GetCurrentThreadId
0x18002b772  mov     [rsp+118h+var_B8], eax
0x18002b776  jmp     short loc_18002B77D
0x18002b778  mov     [rsp+118h+var_D0], r15
0x18002b77d  mov     [rsp+118h+var_A0], rbx
0x18002b782  test    rbx, rbx
0x18002b785  jz      short loc_18002B7B0
0x18002b787  lock inc dword ptr [rbx+110h]
0x18002b78e  or      eax, 0FFFFFFFFh
0x18002b791  lock xadd [rbx+110h], eax
0x18002b799  cmp     eax, 1
0x18002b79c  jnz     short loc_18002B7B0
0x18002b79e  mov     rcx, rbx
0x18002b7a1  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x18002b7a6  mov     rcx, rbx; pv
0x18002b7a9  call    cs:__imp_CoTaskMemFree
0x18002b7af  nop
0x18002b7b0  lea     rdx, [rsp+118h+var_50]
0x18002b7b8  mov     rcx, r14
0x18002b7bb  call    ?BeginTransaction@UQIDatabase@Database@UsageAndQualityInsights@@QEAA?AVTransaction@@W4TransactionLockType@@@Z; UsageAndQualityInsights::Database::UQIDatabase::BeginTransaction(TransactionLockType)
0x18002b7c0  nop
0x18002b7c1  mov     [rsp+118h+pv], r15
0x18002b7c9  call    cs:__imp__Xtime_get_ticks
0x18002b7cf  mov     rcx, rax
0x18002b7d2  mov     rax, 346DC5D63886594Bh
0x18002b7dc  imul    rcx
0x18002b7df  mov     rsi, rdx
0x18002b7e2  sar     rsi, 0Bh
0x18002b7e6  mov     rax, rsi
0x18002b7e9  shr     rax, 3Fh
0x18002b7ed  add     rsi, rax
0x18002b7f0  mov     [rsp+118h+var_E8], r15
0x18002b7f5  lea     rax, [rsp+118h+pv]
0x18002b7fd  mov     [rsp+118h+var_F0], rax
0x18002b802  mov     [rsp+118h+var_F8], r15
0x18002b807  mov     r9d, 80h
0x18002b80d  or      r8d, 0FFFFFFFFh
0x18002b811  lea     rdx, aInsertIntoServ; "INSERT INTO ServiceUsageHistory (Kind, "...
0x18002b818  mov     rcx, [r14+20h]
0x18002b81c  call    sqlite3LockAndPrepare
0x18002b821  mov     edx, 1
0x18002b826  mov     r8d, edx
0x18002b829  mov     rbx, [rsp+118h+pv]
0x18002b831  mov     rcx, rbx
0x18002b834  call    sqlite3_bind_int64
0x18002b839  mov     r8, rsi
0x18002b83c  mov     edx, 2
0x18002b841  mov     rcx, rbx
0x18002b844  call    sqlite3_bind_int64
0x18002b849  mov     rcx, rbx
0x18002b84c  call    sqlite3_step
0x18002b851  test    rbx, rbx
0x18002b854  jz      short loc_18002B871
0x18002b856  mov     rcx, rbx
0x18002b859  call    sqlite3_finalize
0x18002b85e  test    eax, eax
0x18002b860  jnz     loc_18002B929
0x18002b866  mov     rbx, r15
0x18002b869  mov     [rsp+118h+pv], rbx
0x18002b871  lea     rcx, [rsp+118h+var_50]; this
0x18002b879  call    ?Commit@Transaction@@QEAAXXZ; Transaction::Commit(void)
0x18002b87e  mov     rsi, [rsp+118h+var_A0]
0x18002b883  lea     r14, [rsi+0C8h]
0x18002b88a  mov     rcx, r14; lpCriticalSection
0x18002b88d  call    cs:__imp_EnterCriticalSection
0x18002b893  or      dword ptr [rsi+48h], 300h
0x18002b89a  cmp     [rsi+0F8h], r15
0x18002b8a1  jz      short loc_18002B8B1
0x18002b8a3  mov     edx, 2
0x18002b8a8  lea     rcx, [rsi+8]
0x18002b8ac  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18002b8b1  test    r14, r14
0x18002b8b4  jz      short loc_18002B8C0
0x18002b8b6  mov     rcx, r14; lpCriticalSection
0x18002b8b9  call    cs:__imp_LeaveCriticalSection
0x18002b8bf  nop
0x18002b8c0  test    rbx, rbx
0x18002b8c3  jz      short loc_18002B8CE
0x18002b8c5  mov     rcx, rbx; struct sqlite3_stmt *
0x18002b8c8  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x18002b8cd  nop
0x18002b8ce  lea     rcx, [rsp+118h+var_50]; this
0x18002b8d6  call    ??1Transaction@@QEAA@XZ; Transaction::~Transaction(void)
0x18002b8db  nop
0x18002b8dc  mov     rbx, [rsp+118h+var_A0]
0x18002b8e1  test    rbx, rbx
0x18002b8e4  jz      short loc_18002B907
0x18002b8e6  or      eax, 0FFFFFFFFh
0x18002b8e9  lock xadd [rbx+110h], eax
0x18002b8f1  cmp     eax, 1
0x18002b8f4  jnz     short loc_18002B907
0x18002b8f6  mov     rcx, rbx
0x18002b8f9  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x18002b8fe  mov     rcx, rbx; pv
0x18002b901  call    cs:__imp_CoTaskMemFree
0x18002b907  lea     rcx, [rsp+118h+var_D0]; this
0x18002b90c  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18002b911  nop
0x18002b912  mov     rbx, [rsp+118h+arg_18]
0x18002b91a  add     rsp, 100h
0x18002b921  pop     r15
0x18002b923  pop     r14
0x18002b925  pop     rsi
0x18002b926  retn
0x18002b927  jmp     short loc_18002B912
0x18002b929  mov     rcx, rbx
0x18002b92c  call    sqlite3_db_handle
0x18002b931  mov     rdx, rax; struct sqlite3 *
0x18002b934  lea     rcx, [rsp+118h+var_90]; this
0x18002b93c  call    ??0sqlite3_error@@QEAA@PEAUsqlite3@@@Z; sqlite3_error::sqlite3_error(sqlite3 *)
0x18002b941  nop
0x18002b942  lea     rdx, [rsp+118h+var_90]
0x18002b94a  lea     rcx, [rsp+118h+pExceptionObject]
0x18002b952  call    ??0sqlite3_error@@QEAA@$$QEAU0@@Z; sqlite3_error::sqlite3_error(sqlite3_error &&)
0x18002b957  lea     rdx, _TI2?AUsqlite3_error@@; pThrowInfo
0x18002b95e  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x18002b966  call    _CxxThrowException_0
```
