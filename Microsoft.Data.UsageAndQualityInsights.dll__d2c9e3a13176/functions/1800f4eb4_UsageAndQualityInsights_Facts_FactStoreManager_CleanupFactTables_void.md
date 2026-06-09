# UsageAndQualityInsights::Facts::FactStoreManager::CleanupFactTables(void)

- ea: `0x1800f4eb4`
- end: `0x1800f5187`
- name: `?CleanupFactTables@FactStoreManager@Facts@UsageAndQualityInsights@@QEAAXXZ`
- size: `723`
- prototype: `void __fastcall(UsageAndQualityInsights::Facts::FactStoreManager *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001c060`

## callees

- `0x1800033d0`
- `0x1800033f4`
- `0x180008320`
- `0x180013c48`
- `0x1800149fc`
- `0x180016648`
- `0x180016998`
- `0x180016a6c`
- `0x180016dcc`
- `0x180018e64`
- `0x18001ba58`
- `0x18004a66c`
- `0x18004c634`
- `0x1800e6dcc`
- `0x1800eaecc`
- `0x1800f4988`
- `0x1800f4eb4`
- `0x1800f5308`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f50fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f50fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f50cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f50cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f4f7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f4f7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f4f16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f4fb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f5155`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f4f16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f4fb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f5155`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall UsageAndQualityInsights::Facts::FactStoreManager::CleanupFactTables(
        UsageAndQualityInsights::Facts::FactStoreManager *this)
{
  __int64 *v2; // rax
  __int64 v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 *Local; // rax
  _BYTE *ServiceObj; // rax
  __int64 v9; // rbx
  __int64 v10; // rax
  volatile signed __int32 *v11; // rbx
  __int64 v12; // rcx
  __int64 *v13; // rbx
  __int64 v14; // rdi
  __int64 **v15; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  _DWORD *v18; // rbx
  struct _RTL_CRITICAL_SECTION *v19; // rdi
  struct _RTL_CRITICAL_SECTION *v20; // rbx
  LPVOID pv[3]; // [rsp+28h] [rbp-A1h] BYREF
  void **v22; // [rsp+40h] [rbp-89h] BYREF
  _QWORD v23[2]; // [rsp+48h] [rbp-81h] BYREF
  __int64 v24; // [rsp+58h] [rbp-71h]
  DWORD CurrentThreadId; // [rsp+60h] [rbp-69h]
  __int64 v26; // [rsp+68h] [rbp-61h]
  char v27; // [rsp+70h] [rbp-59h]
  LPVOID v28; // [rsp+78h] [rbp-51h]
  _BYTE v29[24]; // [rsp+80h] [rbp-49h] BYREF
  _BYTE v30[24]; // [rsp+98h] [rbp-31h] BYREF
  _BYTE v31[16]; // [rsp+B0h] [rbp-19h] BYREF
  _BYTE v32[32]; // [rsp+C0h] [rbp-9h] BYREF

  v2 = tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQICleanupOldFactsTipTest,_tip_UQICleanupOldFactsTipTest>,>(pv);
  v3 = *v2;
  *v2 = 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)pv[0];
  if ( pv[0] && _InterlockedExchangeAdd((volatile signed __int32 *)pv[0] + 68, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(v4);
    CoTaskMemFree(v4);
  }
  tip2::details::shared_data<0,0,0>::start(v3 + 8, pv);
  v22 = &tip2::test_watcher<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::`vftable';
  v23[0] = 0;
  v23[1] = &v22;
  v24 = 0;
  CurrentThreadId = 0;
  v26 = 0;
  v27 = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(v5) = 1;
    Local = (__int64 *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                         v6,
                         v5);
    v23[0] = Local;
    if ( Local )
    {
      v24 = *Local;
      *Local = (__int64)v23;
      CurrentThreadId = GetCurrentThreadId();
    }
  }
  else
  {
    v23[0] = 0;
  }
  v28 = (LPVOID)v3;
  if ( v3 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 272));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 272), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>((struct _RTL_CRITICAL_SECTION *)v3);
      CoTaskMemFree((LPVOID)v3);
    }
  }
  ServiceObj = (_BYTE *)GetServiceObj(v31);
  if ( !ServiceObj[8] )
    std::_Throw_bad_optional_access();
  v9 = *(_QWORD *)ServiceObj;
  v10 = *(_QWORD *)(*(_QWORD *)ServiceObj + 48LL);
  if ( v10 )
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
  pv[0] = *(LPVOID *)(v9 + 40);
  v11 = *(volatile signed __int32 **)(v9 + 48);
  pv[1] = (LPVOID)v11;
  UsageAndQualityInsights::Configuration::ConfigStore::GetCurrentConfig(pv[0], v29);
  if ( v11 )
  {
    if ( !_InterlockedDecrement(v11 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( !_InterlockedDecrement(v11 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  UsageAndQualityInsights::Facts::FactStoreManager::GetFactStoreIdentifiers(v12, v30);
  UsageAndQualityInsights::Configuration::CompiledUQIConfig::GetMaxExpirationDateBySourceAndEvent(v29, v32);
  v13 = (__int64 *)**((_QWORD **)this + 5);
  while ( !*((_BYTE *)v13 + 25) )
  {
    v14 = v13[8];
    UsageAndQualityInsightsCoreLogging::TraceLoggingInfo("FactStore::CleanupFactTables");
    UsageAndQualityInsights::Database::FactStoreDatabase::RemoveExpiredEvents(*(_QWORD *)(v14 + 16), v32);
    v15 = (__int64 **)v13[2];
    if ( *((_BYTE *)v15 + 25) )
    {
      for ( i = (__int64 *)v13[1]; !*((_BYTE *)i + 25) && v13 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v13 = i;
      v13 = i;
    }
    else
    {
      v13 = (__int64 *)v13[2];
      for ( j = *v15; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v13 = j;
    }
  }
  v18 = v28;
  v19 = (struct _RTL_CRITICAL_SECTION *)((char *)v28 + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)v28 + 5);
  v18[18] |= 0x300u;
  if ( *((_QWORD *)v18 + 31) )
    tip2::details::shared_data<0,0,0>::complete_helper(v18 + 2, 2);
  if ( v19 )
    LeaveCriticalSection(v19);
  `eh vector destructor iterator'(
    v32,
    0x10u,
    2u,
    std::map<std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~map<std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>);
  std::vector<std::wstring>::_Tidy(v30);
  std::vector<UsageAndQualityInsights::Configuration::UQIConfig>::_Tidy(v29);
  v20 = (struct _RTL_CRITICAL_SECTION *)v28;
  if ( v28 && _InterlockedExchangeAdd((volatile signed __int32 *)v28 + 68, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(v20);
    CoTaskMemFree(v20);
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v23);
}

```

## disassembly

```asm
0x1800f4eb4  push    rbp
0x1800f4eb6  push    rbx
0x1800f4eb7  push    rsi
0x1800f4eb8  push    rdi
0x1800f4eb9  push    r14
0x1800f4ebb  push    r15
0x1800f4ebd  lea     rbp, [rsp-2Fh]
0x1800f4ec2  sub     rsp, 0F8h
0x1800f4ec9  mov     rax, cs:__security_cookie
0x1800f4ed0  xor     rax, rsp
0x1800f4ed3  mov     [rbp+57h+var_40], rax
0x1800f4ed7  mov     rsi, rcx
0x1800f4eda  lea     rcx, [rsp+120h+pv]
0x1800f4edf  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_UQICleanupOldFactsTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_UQICleanupOldFactsTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQICleanupOldFactsTipTest,_tip_UQICleanupOldFactsTipTest>,>(void)
0x1800f4ee4  mov     rbx, [rax]
0x1800f4ee7  xor     r14d, r14d
0x1800f4eea  mov     [rax], r14
0x1800f4eed  or      r15d, 0FFFFFFFFh
0x1800f4ef1  mov     rdi, [rsp+120h+pv]
0x1800f4ef6  test    rdi, rdi
0x1800f4ef9  jz      short loc_1800F4F1C
0x1800f4efb  mov     eax, r15d
0x1800f4efe  lock xadd [rdi+110h], eax
0x1800f4f06  add     eax, r15d
0x1800f4f09  jnz     short loc_1800F4F1C
0x1800f4f0b  mov     rcx, rdi
0x1800f4f0e  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x1800f4f13  mov     rcx, rdi; pv
0x1800f4f16  call    cs:__imp_CoTaskMemFree
0x1800f4f1c  lea     rcx, [rbx+8]
0x1800f4f20  lea     rdx, [rsp+120h+pv]
0x1800f4f25  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x1800f4f2a  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::`vftable'
0x1800f4f31  mov     [rsp+120h+var_E0], rax
0x1800f4f36  mov     [rsp+120h+var_D8], r14
0x1800f4f3b  lea     rax, [rsp+120h+var_E0]
0x1800f4f40  mov     [rbp+57h+var_D0], rax
0x1800f4f44  mov     [rbp+57h+var_C8], r14
0x1800f4f48  mov     [rbp+57h+var_C0], r14d
0x1800f4f4c  mov     [rbp+57h+var_B8], r14
0x1800f4f50  mov     [rbp+57h+var_B0], r14b
0x1800f4f54  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r14; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800f4f5b  jz      short loc_1800F4F88
0x1800f4f5d  mov     dl, 1
0x1800f4f5f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800f4f64  mov     [rsp+120h+var_D8], rax
0x1800f4f69  test    rax, rax
0x1800f4f6c  jz      short loc_1800F4F8D
0x1800f4f6e  mov     rcx, [rax]
0x1800f4f71  mov     [rbp+57h+var_C8], rcx
0x1800f4f75  lea     rcx, [rsp+120h+var_D8]
0x1800f4f7a  mov     [rax], rcx
0x1800f4f7d  call    cs:__imp_GetCurrentThreadId
0x1800f4f83  mov     [rbp+57h+var_C0], eax
0x1800f4f86  jmp     short loc_1800F4F8D
0x1800f4f88  mov     [rsp+120h+var_D8], r14
0x1800f4f8d  mov     [rbp+57h+var_A8], rbx
0x1800f4f91  test    rbx, rbx
0x1800f4f94  jz      short loc_1800F4FBF
0x1800f4f96  lock inc dword ptr [rbx+110h]
0x1800f4f9d  mov     eax, r15d
0x1800f4fa0  lock xadd [rbx+110h], eax
0x1800f4fa8  add     eax, r15d
0x1800f4fab  jnz     short loc_1800F4FBF
0x1800f4fad  mov     rcx, rbx
0x1800f4fb0  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x1800f4fb5  mov     rcx, rbx; pv
0x1800f4fb8  call    cs:__imp_CoTaskMemFree
0x1800f4fbe  nop
0x1800f4fbf  lea     rcx, [rbp+57h+var_70]
0x1800f4fc3  call    ?GetServiceObj@@YA?AV?$optional@V?$reference_wrapper@VUQIService@@@std@@@std@@XZ; GetServiceObj(void)
0x1800f4fc8  cmp     [rax+8], r14b
0x1800f4fcc  jz      loc_1800F5181
0x1800f4fd2  mov     rbx, [rax]
0x1800f4fd5  mov     rax, [rbx+30h]
0x1800f4fd9  test    rax, rax
0x1800f4fdc  jz      short loc_1800F4FE2
0x1800f4fde  lock inc dword ptr [rax+8]
0x1800f4fe2  mov     rcx, [rbx+28h]
0x1800f4fe6  mov     [rsp+120h+pv], rcx
0x1800f4feb  mov     rbx, [rbx+30h]
0x1800f4fef  mov     [rsp+120h+var_F0], rbx
0x1800f4ff4  lea     rdx, [rbp+57h+var_A0]
0x1800f4ff8  call    ?GetCurrentConfig@ConfigStore@Configuration@UsageAndQualityInsights@@QEBA?AVCompiledUQIConfig@23@XZ; UsageAndQualityInsights::Configuration::ConfigStore::GetCurrentConfig(void)
0x1800f4ffd  nop
0x1800f4ffe  test    rbx, rbx
0x1800f5001  jz      short loc_1800F503A
0x1800f5003  mov     eax, r15d
0x1800f5006  lock xadd [rbx+8], eax
0x1800f500b  add     eax, r15d
0x1800f500e  jnz     short loc_1800F503A
0x1800f5010  mov     rax, [rbx]
0x1800f5013  mov     rcx, rbx
0x1800f5016  mov     rax, [rax]
0x1800f5019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f501e  mov     eax, r15d
0x1800f5021  lock xadd [rbx+0Ch], eax
0x1800f5026  add     eax, r15d
0x1800f5029  jnz     short loc_1800F503A
0x1800f502b  mov     rax, [rbx]
0x1800f502e  mov     rcx, rbx
0x1800f5031  mov     rax, [rax+8]
0x1800f5035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f503a  lea     rdx, [rbp+57h+var_88]
0x1800f503e  call    ?GetFactStoreIdentifiers@FactStoreManager@Facts@UsageAndQualityInsights@@AEAA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@W4Scope@23@_N@Z; UsageAndQualityInsights::Facts::FactStoreManager::GetFactStoreIdentifiers(UsageAndQualityInsights::Facts::Scope,bool)
0x1800f5043  nop
0x1800f5044  lea     rdx, [rbp+57h+var_60]
0x1800f5048  lea     rcx, [rbp+57h+var_A0]
0x1800f504c  call    ?GetMaxExpirationDateBySourceAndEvent@CompiledUQIConfig@Configuration@UsageAndQualityInsights@@QEBA?AV?$array@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@@std@@@2@@std@@$01@std@@XZ; UsageAndQualityInsights::Configuration::CompiledUQIConfig::GetMaxExpirationDateBySourceAndEvent(void)
0x1800f5051  nop
0x1800f5052  mov     rbx, [rsi+28h]
0x1800f5056  mov     rbx, [rbx]
0x1800f5059  cmp     [rbx+19h], r14b
0x1800f505d  jnz     short loc_1800F50C1
0x1800f505f  mov     rdi, [rbx+40h]
0x1800f5063  lea     rcx, aFactstoreClean; "FactStore::CleanupFactTables"
0x1800f506a  call    ?TraceLoggingInfo@UsageAndQualityInsightsCoreLogging@@SAXPEBDZZ; UsageAndQualityInsightsCoreLogging::TraceLoggingInfo(char const *,...)
0x1800f506f  lea     rdx, [rbp+57h+var_60]
0x1800f5073  mov     rcx, [rdi+10h]
0x1800f5077  call    ?RemoveExpiredEvents@FactStoreDatabase@Database@UsageAndQualityInsights@@QEAAXAEBV?$array@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@@std@@@2@@std@@$01@std@@@Z; UsageAndQualityInsights::Database::FactStoreDatabase::RemoveExpiredEvents(std::array<std::map<std::wstring,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>,2> const &)
0x1800f507c  mov     rcx, [rbx+10h]
0x1800f5080  cmp     [rcx+19h], r14b
0x1800f5084  jz      short loc_1800F50A4
0x1800f5086  mov     rax, [rbx+8]
0x1800f508a  jmp     short loc_1800F5099
0x1800f508c  cmp     rbx, [rax+10h]
0x1800f5090  jnz     short loc_1800F509F
0x1800f5092  mov     rbx, rax
0x1800f5095  mov     rax, [rax+8]
0x1800f5099  cmp     [rax+19h], r14b
0x1800f509d  jz      short loc_1800F508C
0x1800f509f  mov     rbx, rax
0x1800f50a2  jmp     short loc_1800F5059
0x1800f50a4  mov     rbx, rcx
0x1800f50a7  mov     rcx, [rcx]
0x1800f50aa  cmp     [rcx+19h], r14b
0x1800f50ae  jnz     short loc_1800F5059
0x1800f50b0  mov     rbx, rcx
0x1800f50b3  mov     rax, [rcx]
0x1800f50b6  mov     rcx, rax
0x1800f50b9  cmp     [rax+19h], r14b
0x1800f50bd  jz      short loc_1800F50B0
0x1800f50bf  jmp     short loc_1800F5059
0x1800f50c1  mov     rbx, [rbp+57h+var_A8]
0x1800f50c5  lea     rdi, [rbx+0C8h]
0x1800f50cc  mov     rcx, rdi; lpCriticalSection
0x1800f50cf  call    cs:__imp_EnterCriticalSection
0x1800f50d5  or      dword ptr [rbx+48h], 300h
0x1800f50dc  mov     esi, 2
0x1800f50e1  cmp     [rbx+0F8h], r14
0x1800f50e8  jz      short loc_1800F50F5
0x1800f50ea  mov     edx, esi
0x1800f50ec  lea     rcx, [rbx+8]
0x1800f50f0  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x1800f50f5  test    rdi, rdi
0x1800f50f8  jz      short loc_1800F5104
0x1800f50fa  mov     rcx, rdi; lpCriticalSection
0x1800f50fd  call    cs:__imp_LeaveCriticalSection
0x1800f5103  nop
0x1800f5104  lea     r9, ??1?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@2@@std@@@2@@std@@QEAA@XZ; void (*)(void *)
0x1800f510b  mov     r8, rsi; unsigned __int64
0x1800f510e  mov     edx, 10h; unsigned __int64
0x1800f5113  lea     rcx, [rbp+57h+var_60]; void *
0x1800f5117  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800f511c  nop
0x1800f511d  lea     rcx, [rbp+57h+var_88]
0x1800f5121  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800f5126  nop
0x1800f5127  lea     rcx, [rbp+57h+var_A0]
0x1800f512b  call    ?_Tidy@?$vector@UUQIConfig@Configuration@UsageAndQualityInsights@@V?$allocator@UUQIConfig@Configuration@UsageAndQualityInsights@@@std@@@std@@AEAAXXZ; std::vector<UsageAndQualityInsights::Configuration::UQIConfig>::_Tidy(void)
0x1800f5130  nop
0x1800f5131  mov     rbx, [rbp+57h+var_A8]
0x1800f5135  test    rbx, rbx
0x1800f5138  jz      short loc_1800F515B
0x1800f513a  mov     eax, r15d
0x1800f513d  lock xadd [rbx+110h], eax
0x1800f5145  add     eax, r15d
0x1800f5148  jnz     short loc_1800F515B
0x1800f514a  mov     rcx, rbx
0x1800f514d  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x1800f5152  mov     rcx, rbx; pv
0x1800f5155  call    cs:__imp_CoTaskMemFree
0x1800f515b  lea     rcx, [rsp+120h+var_D8]; this
0x1800f5160  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800f5165  mov     rcx, [rbp+57h+var_40]
0x1800f5169  xor     rcx, rsp; StackCookie
0x1800f516c  call    __security_check_cookie
0x1800f5171  add     rsp, 0F8h
0x1800f5178  pop     r15
0x1800f517a  pop     r14
0x1800f517c  pop     rdi
0x1800f517d  pop     rsi
0x1800f517e  pop     rbx
0x1800f517f  pop     rbp
0x1800f5180  retn
0x1800f5181  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
```
