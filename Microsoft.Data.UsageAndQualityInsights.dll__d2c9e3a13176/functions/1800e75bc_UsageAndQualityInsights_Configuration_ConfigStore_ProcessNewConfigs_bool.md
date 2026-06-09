# UsageAndQualityInsights::Configuration::ConfigStore::ProcessNewConfigs(bool)

- ea: `0x1800e75bc`
- end: `0x1800e7a4a`
- name: `?ProcessNewConfigs@ConfigStore@Configuration@UsageAndQualityInsights@@QEAAX_N@Z`
- size: `1166`
- prototype: `void __fastcall(RTL_SRWLOCK *this, char)`
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800e4154`
- `0x1800e5324`

## callees

- `0x1800033d0`
- `0x180003870`
- `0x180008320`
- `0x18000c844`
- `0x18000d9d4`
- `0x18000eee0`
- `0x1800107b0`
- `0x180013c48`
- `0x180013e44`
- `0x1800149fc`
- `0x180016998`
- `0x180016dcc`
- `0x180018e64`
- `0x180037c7c`
- `0x180039768`
- `0x1800e4b00`
- `0x1800e4f78`
- `0x1800e5204`
- `0x1800e65d4`
- `0x1800e6bb8`
- `0x1800e733c`
- `0x1800e75bc`
- `0x1800e7a50`
- `0x1800ec2ac`
- `0x1800f2104`
- `0x1800f3500`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e7853`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e7853`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e78b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e78b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e7809`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e7949`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e7809`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e7949`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e78ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e78ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e78c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e78c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e76a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e76a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e763b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e76e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e79e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e763b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e76e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e79e6`

## string_xrefs

- `0x1800e75f6`: `ProcessNewConfigs`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall UsageAndQualityInsights::Configuration::ConfigStore::ProcessNewConfigs(RTL_SRWLOCK *this, char a2)
{
  volatile signed __int32 **v4; // rax
  volatile signed __int32 *v5; // rbx
  void *v6; // rsi
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 *Local; // rax
  RTL_SRWLOCK *v10; // rdx
  PVOID Ptr; // r8
  char v12; // bl
  struct std::error_code *v13; // r8
  bool v14; // al
  UsageAndQualityInsights::Configuration::ConfigStore *v15; // rcx
  const struct std::filesystem::path *v16; // r9
  RTL_SRWLOCK *v17; // rdx
  PVOID v18; // r8
  struct std::error_code *v19; // r8
  bool v20; // al
  const struct std::filesystem::path *v21; // r9
  char v22; // si
  struct _RTL_CRITICAL_SECTION *v23; // rbx
  DWORD LastError; // ebx
  __int64 v25; // rax
  UsageAndQualityInsights::Configuration::ConfigStore *v26; // rcx
  struct _RTL_CRITICAL_SECTION *v27; // rbx
  void *v28; // rbx
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  void ***v30; // [rsp+28h] [rbp-D8h]
  __int64 v31; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v32; // [rsp+38h] [rbp-C8h] BYREF
  void *v33[2]; // [rsp+40h] [rbp-C0h] BYREF
  void **v34; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v35[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+68h] [rbp-98h]
  DWORD CurrentThreadId; // [rsp+70h] [rbp-90h]
  __int64 v38; // [rsp+78h] [rbp-88h]
  char v39; // [rsp+80h] [rbp-80h]
  LPVOID v40; // [rsp+88h] [rbp-78h]
  __int128 v41; // [rsp+90h] [rbp-70h] BYREF
  void *v42; // [rsp+A0h] [rbp-60h]
  _BYTE v43[24]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v44; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v45; // [rsp+D0h] [rbp-30h]
  __int64 v46; // [rsp+D8h] [rbp-28h]
  __int128 v47; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v48; // [rsp+F0h] [rbp-10h]
  __int64 v49; // [rsp+F8h] [rbp-8h]

  LODWORD(v31) = 0;
  UsageAndQualityInsightsTraceLogging::TraceLoggingInfo("ProcessNewConfigs");
  v4 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIConfigsProcessingTipTest,_tip_UQIConfigsProcessingTipTest>,>(&pv);
  v5 = *v4;
  *v4 = 0;
  v6 = pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 68, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(v6);
    CoTaskMemFree(v6);
  }
  tip2::details::shared_data<0,0,0>::start(v5 + 2, &pv);
  v34 = &tip2::test_watcher<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::`vftable';
  v35[0] = 0;
  v35[1] = &v34;
  v36 = 0;
  CurrentThreadId = 0;
  v38 = 0;
  v39 = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(v7) = 1;
    Local = (__int64 *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                         v8,
                         v7);
    v35[0] = Local;
    if ( Local )
    {
      v36 = *Local;
      *Local = (__int64)v35;
      CurrentThreadId = GetCurrentThreadId();
    }
  }
  else
  {
    v35[0] = 0;
  }
  v40 = (LPVOID)v5;
  if ( v5 )
  {
    _InterlockedIncrement(v5 + 68);
    if ( _InterlockedExchangeAdd(v5 + 68, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(v5);
      CoTaskMemFree((LPVOID)v5);
    }
  }
  v10 = this + 13;
  Ptr = this[15].Ptr;
  if ( this[16].Ptr > (PVOID)7 )
    v10 = (RTL_SRWLOCK *)v10->Ptr;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v47, v10, Ptr);
  v12 = 13;
  LODWORD(v31) = 13;
  LODWORD(pv) = 0;
  v30 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  v14 = std::filesystem::exists((std::filesystem *)&v47, (const struct std::filesystem::path *)&pv, v13);
  if ( (_DWORD)pv )
    std::filesystem::_Throw_fs_error(
      (std::filesystem *)"exists",
      (const char *)&pv,
      (const struct std::error_code *)&v47,
      v16);
  if ( !v14 )
    goto LABEL_22;
  v17 = this + 17;
  v18 = this[19].Ptr;
  if ( this[20].Ptr > (PVOID)7 )
    v17 = (RTL_SRWLOCK *)v17->Ptr;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v44, v17, v18);
  v12 = 63;
  LODWORD(v31) = 63;
  LODWORD(pv) = 0;
  v30 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  v20 = std::filesystem::exists((std::filesystem *)&v44, (const struct std::filesystem::path *)&pv, v19);
  if ( (_DWORD)pv )
    std::filesystem::_Throw_fs_error(
      (std::filesystem *)"exists",
      (const char *)&pv,
      (const struct std::error_code *)&v44,
      v21);
  if ( !v20
    || a2
    && UsageAndQualityInsights::Configuration::ConfigStore::AreNewConfigsAvailable((UsageAndQualityInsights::Configuration::ConfigStore *)this) )
  {
LABEL_22:
    v22 = 0;
  }
  else
  {
    v22 = 1;
  }
  if ( (v12 & 2) != 0 )
  {
    v12 &= ~2u;
    std::wstring::~wstring(&v44);
  }
  if ( (v12 & 1) != 0 )
    std::wstring::~wstring(&v47);
  if ( v22 )
  {
    UsageAndQualityInsights::Configuration::ConfigStore::EnableMetricGroup(v15);
    v23 = (struct _RTL_CRITICAL_SECTION *)v40;
    pv = v40;
    if ( v40 )
      _InterlockedIncrement((volatile signed __int32 *)v40 + 68);
    EnterCriticalSection(v23 + 5);
    ++LODWORD(v23[6].DebugInfo);
    LODWORD(v23[1].SpinCount) |= 0xB00u;
    if ( *(_QWORD *)&v23[6].LockCount )
      tip2::details::shared_data<0,0,0>::complete_helper(&v23->LockCount, 10);
    tip2::test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>(&pv);
  }
  else
  {
    UsageAndQualityInsights::Configuration::ConfigStore::LoadPartnerConfigs(v43, &this[5]);
    AcquireSRWLockExclusive(this);
    pv = this;
    std::vector<UsageAndQualityInsights::Configuration::UQIConfig>::vector<UsageAndQualityInsights::Configuration::UQIConfig>(
      &v41,
      v43);
    if ( &this[21] != (RTL_SRWLOCK *)&v41 )
    {
      std::vector<UsageAndQualityInsights::Configuration::UQIConfig>::_Tidy(&this[21]);
      *(_OWORD *)&this[21].Ptr = v41;
      this[23].Ptr = v42;
      v41 = 0;
      v42 = 0;
    }
    std::vector<UsageAndQualityInsights::Configuration::UQIConfig>::_Tidy(&v41);
    if ( this )
    {
      LastError = GetLastError();
      ReleaseSRWLockExclusive(this);
      SetLastError(LastError);
    }
    pv = 0;
    UsageAndQualityInsights::Configuration::MetricEventConfigFromUQIConfigArray(v33, v43);
    UsageAndQualityInsights::Configuration::MetricEventConfigToUtcSideloadConfig(&v32, v33);
    UsageAndQualityInsights::Configuration::ConfigStore::StoreJsonToPath(&v32, &this[17]);
    v25 = UsageAndQualityInsights::Configuration::CompiledUQIConfig::ToJson(&this[21], &v31);
    UsageAndQualityInsights::Configuration::ConfigStore::StoreJsonToPath(v25, &this[13]);
    if ( v31 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v31);
    UsageAndQualityInsights::Configuration::ConfigStore::EnableMetricGroup(v26);
    v27 = (struct _RTL_CRITICAL_SECTION *)v40;
    pv = v40;
    if ( v40 )
      _InterlockedIncrement((volatile signed __int32 *)v40 + 68);
    EnterCriticalSection(v27 + 5);
    ++LODWORD(v27[6].DebugInfo);
    LODWORD(v27[1].SpinCount) |= 0xB00u;
    if ( *(_QWORD *)&v27[6].LockCount )
      tip2::details::shared_data<0,0,0>::complete_helper(&v27->LockCount, 10);
    tip2::test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>(&pv);
    if ( v32 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v32);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::MetricEventConfigEntry>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::MetricEventConfigEntry>,void *>>>(
      v33,
      v33,
      *((_QWORD *)v33[0] + 1));
    operator delete(v33[0], 0xD8u);
    std::vector<UsageAndQualityInsights::Configuration::UQIConfig>::_Tidy(v43);
  }
  v28 = v40;
  if ( v40 && _InterlockedExchangeAdd((volatile signed __int32 *)v40 + 68, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(v28);
    CoTaskMemFree(v28);
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v35);
}

```

## disassembly

```asm
0x1800e75bc  mov     [rsp-8+arg_8], rbx
0x1800e75c1  mov     [rsp-8+arg_10], rsi
0x1800e75c6  push    rbp
0x1800e75c7  push    rdi
0x1800e75c8  push    r13
0x1800e75ca  push    r14
0x1800e75cc  push    r15
0x1800e75ce  lea     rbp, [rsp-10h]
0x1800e75d3  sub     rsp, 110h
0x1800e75da  mov     rax, cs:__security_cookie
0x1800e75e1  xor     rax, rsp
0x1800e75e4  mov     [rbp+30h+var_30], rax
0x1800e75e8  mov     r14b, dl
0x1800e75eb  mov     rdi, rcx
0x1800e75ee  xor     r15d, r15d
0x1800e75f1  mov     dword ptr [rsp+130h+var_100], r15d
0x1800e75f6  lea     rcx, aProcessnewconf; "ProcessNewConfigs"
0x1800e75fd  call    ?TraceLoggingInfo@UsageAndQualityInsightsTraceLogging@@SAXPEBDZZ; UsageAndQualityInsightsTraceLogging::TraceLoggingInfo(char const *,...)
0x1800e7602  lea     rcx, [rsp+130h+pv]
0x1800e7607  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_UQIConfigsProcessingTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_UQIConfigsProcessingTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIConfigsProcessingTipTest,_tip_UQIConfigsProcessingTipTest>,>(void)
0x1800e760c  mov     rbx, [rax]
0x1800e760f  mov     [rax], r15
0x1800e7612  or      r13d, 0FFFFFFFFh
0x1800e7616  mov     rsi, [rsp+130h+pv]
0x1800e761b  test    rsi, rsi
0x1800e761e  jz      short loc_1800E7641
0x1800e7620  mov     eax, r13d
0x1800e7623  lock xadd [rsi+110h], eax
0x1800e762b  add     eax, r13d
0x1800e762e  jnz     short loc_1800E7641
0x1800e7630  mov     rcx, rsi
0x1800e7633  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x1800e7638  mov     rcx, rsi; pv
0x1800e763b  call    cs:__imp_CoTaskMemFree
0x1800e7641  lea     rcx, [rbx+8]
0x1800e7645  lea     rdx, [rsp+130h+pv]
0x1800e764a  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x1800e764f  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::`vftable'
0x1800e7656  mov     [rsp+130h+var_E0], rax
0x1800e765b  mov     [rsp+130h+var_D8], r15
0x1800e7660  lea     rax, [rsp+130h+var_E0]
0x1800e7665  mov     [rsp+130h+var_D0], rax
0x1800e766a  mov     [rsp+130h+var_C8], r15
0x1800e766f  mov     [rsp+130h+var_C0], r15d
0x1800e7674  mov     [rsp+130h+var_B8], r15
0x1800e7679  mov     [rbp+30h+var_B0], r15b
0x1800e767d  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r15; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800e7684  jz      short loc_1800E76B3
0x1800e7686  mov     dl, 1
0x1800e7688  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800e768d  mov     [rsp+130h+var_D8], rax
0x1800e7692  test    rax, rax
0x1800e7695  jz      short loc_1800E76B8
0x1800e7697  mov     rcx, [rax]
0x1800e769a  mov     [rsp+130h+var_C8], rcx
0x1800e769f  lea     rcx, [rsp+130h+var_D8]
0x1800e76a4  mov     [rax], rcx
0x1800e76a7  call    cs:__imp_GetCurrentThreadId
0x1800e76ad  mov     [rsp+130h+var_C0], eax
0x1800e76b1  jmp     short loc_1800E76B8
0x1800e76b3  mov     [rsp+130h+var_D8], r15
0x1800e76b8  mov     [rbp+30h+var_A8], rbx
0x1800e76bc  test    rbx, rbx
0x1800e76bf  jz      short loc_1800E76EA
0x1800e76c1  lock inc dword ptr [rbx+110h]
0x1800e76c8  mov     eax, r13d
0x1800e76cb  lock xadd [rbx+110h], eax
0x1800e76d3  add     eax, r13d
0x1800e76d6  jnz     short loc_1800E76EA
0x1800e76d8  mov     rcx, rbx
0x1800e76db  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x1800e76e0  mov     rcx, rbx; pv
0x1800e76e3  call    cs:__imp_CoTaskMemFree
0x1800e76e9  nop
0x1800e76ea  lea     rdx, [rdi+68h]
0x1800e76ee  mov     r8, [rdx+10h]
0x1800e76f2  cmp     qword ptr [rdx+18h], 7
0x1800e76f7  jbe     short loc_1800E76FC
0x1800e76f9  mov     rdx, [rdx]
0x1800e76fc  xorps   xmm0, xmm0
0x1800e76ff  movups  [rbp+30h+var_50], xmm0
0x1800e7703  mov     [rbp+30h+var_40], r15
0x1800e7707  mov     [rbp+30h+var_38], r15
0x1800e770b  lea     rcx, [rbp+30h+var_50]
0x1800e770f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800e7714  nop
0x1800e7715  mov     ebx, 0Dh
0x1800e771a  mov     dword ptr [rsp+130h+var_100], ebx
0x1800e771e  mov     dword ptr [rsp+130h+pv], r15d
0x1800e7723  lea     rsi, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x1800e772a  mov     [rsp+130h+var_108], rsi
0x1800e772f  lea     rdx, [rsp+130h+pv]; struct std::filesystem::path *
0x1800e7734  lea     rcx, [rbp+30h+var_50]; this
0x1800e7738  call    ?exists@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::exists(std::filesystem::path const &,std::error_code &)
0x1800e773d  cmp     dword ptr [rsp+130h+pv], r15d
0x1800e7742  jnz     loc_1800E7A34
0x1800e7748  test    al, al
0x1800e774a  jz      short loc_1800E77C0
0x1800e774c  lea     rdx, [rdi+88h]
0x1800e7753  mov     r8, [rdx+10h]
0x1800e7757  cmp     qword ptr [rdx+18h], 7
0x1800e775c  jbe     short loc_1800E7761
0x1800e775e  mov     rdx, [rdx]
0x1800e7761  xorps   xmm0, xmm0
0x1800e7764  movups  [rbp+30h+var_70], xmm0
0x1800e7768  mov     [rbp+30h+var_60], r15
0x1800e776c  mov     [rbp+30h+var_58], r15
0x1800e7770  lea     rcx, [rbp+30h+var_70]
0x1800e7774  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800e7779  nop
0x1800e777a  mov     ebx, 3Fh ; '?'
0x1800e777f  mov     dword ptr [rsp+130h+var_100], ebx
0x1800e7783  mov     dword ptr [rsp+130h+pv], r15d
0x1800e7788  mov     [rsp+130h+var_108], rsi
0x1800e778d  lea     rdx, [rsp+130h+pv]; struct std::filesystem::path *
0x1800e7792  lea     rcx, [rbp+30h+var_70]; this
0x1800e7796  call    ?exists@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::exists(std::filesystem::path const &,std::error_code &)
0x1800e779b  cmp     dword ptr [rsp+130h+pv], r15d
0x1800e77a0  jnz     loc_1800E7A1E
0x1800e77a6  test    al, al
0x1800e77a8  jz      short loc_1800E77C0
0x1800e77aa  test    r14b, r14b
0x1800e77ad  jz      short loc_1800E77BB
0x1800e77af  mov     rcx, rdi; this
0x1800e77b2  call    ?AreNewConfigsAvailable@ConfigStore@Configuration@UsageAndQualityInsights@@QEBA_NXZ; UsageAndQualityInsights::Configuration::ConfigStore::AreNewConfigsAvailable(void)
0x1800e77b7  test    al, al
0x1800e77b9  jnz     short loc_1800E77C0
0x1800e77bb  mov     sil, 1
0x1800e77be  jmp     short loc_1800E77C3
0x1800e77c0  mov     sil, r15b
0x1800e77c3  test    bl, 2
0x1800e77c6  jz      short loc_1800E77D5
0x1800e77c8  and     ebx, 0FFFFFFFDh
0x1800e77cb  lea     rcx, [rbp+30h+var_70]; void *
0x1800e77cf  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e77d4  nop
0x1800e77d5  test    bl, 1
0x1800e77d8  jz      short loc_1800E77E3
0x1800e77da  lea     rcx, [rbp+30h+var_50]; void *
0x1800e77de  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e77e3  test    sil, sil
0x1800e77e6  jz      short loc_1800E7842
0x1800e77e8  call    ?EnableMetricGroup@ConfigStore@Configuration@UsageAndQualityInsights@@AEAAXXZ; UsageAndQualityInsights::Configuration::ConfigStore::EnableMetricGroup(void)
0x1800e77ed  mov     rbx, [rbp+30h+var_A8]
0x1800e77f1  mov     [rsp+130h+pv], rbx
0x1800e77f6  test    rbx, rbx
0x1800e77f9  jz      short loc_1800E7802
0x1800e77fb  lock inc dword ptr [rbx+110h]
0x1800e7802  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800e7809  call    cs:__imp_EnterCriticalSection
0x1800e780f  inc     dword ptr [rbx+0F0h]
0x1800e7815  or      dword ptr [rbx+48h], 0B00h
0x1800e781c  cmp     [rbx+0F8h], r15
0x1800e7823  jz      short loc_1800E7833
0x1800e7825  mov     edx, 0Ah
0x1800e782a  lea     rcx, [rbx+8]
0x1800e782e  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x1800e7833  lea     rcx, [rsp+130h+pv]
0x1800e7838  call    ??1?$test_data_control@V?$merged_data@U_tip_UQISaveFactsToFactStoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>(void)
0x1800e783d  jmp     loc_1800E79C2
0x1800e7842  lea     rdx, [rdi+28h]
0x1800e7846  lea     rcx, [rbp+30h+var_88]
0x1800e784a  call    ?LoadPartnerConfigs@ConfigStore@Configuration@UsageAndQualityInsights@@CA?AV?$vector@UUQIConfig@Configuration@UsageAndQualityInsights@@V?$allocator@UUQIConfig@Configuration@UsageAndQualityInsights@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; UsageAndQualityInsights::Configuration::ConfigStore::LoadPartnerConfigs(std::wstring const &)
0x1800e784f  nop
0x1800e7850  mov     rcx, rdi; SRWLock
0x1800e7853  call    cs:__imp_AcquireSRWLockExclusive
0x1800e7859  mov     [rsp+130h+pv], rdi
0x1800e785e  lea     rdx, [rbp+30h+var_88]
0x1800e7862  lea     rcx, [rbp+30h+var_A0]
0x1800e7866  call    ??0?$vector@UUQIConfig@Configuration@UsageAndQualityInsights@@V?$allocator@UUQIConfig@Configuration@UsageAndQualityInsights@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<UsageAndQualityInsights::Configuration::UQIConfig>::vector<UsageAndQualityInsights::Configuration::UQIConfig>(std::vector<UsageAndQualityInsights::Configuration::UQIConfig> const &)
0x1800e786b  lea     rsi, [rdi+0A8h]
0x1800e7872  lea     rax, [rbp+30h+var_A0]
0x1800e7876  cmp     rsi, rax
0x1800e7879  jz      short loc_1800E78A0
0x1800e787b  mov     rcx, rsi
0x1800e787e  call    ?_Tidy@?$vector@UUQIConfig@Configuration@UsageAndQualityInsights@@V?$allocator@UUQIConfig@Configuration@UsageAndQualityInsights@@@std@@@std@@AEAAXXZ; std::vector<UsageAndQualityInsights::Configuration::UQIConfig>::_Tidy(void)
0x1800e7883  movups  xmm0, [rbp+30h+var_A0]
0x1800e7887  movups  xmmword ptr [rsi], xmm0
0x1800e788a  movsd   xmm1, [rbp+30h+var_90]
0x1800e788f  movsd   qword ptr [rsi+10h], xmm1
0x1800e7894  xorps   xmm0, xmm0
0x1800e7897  movdqu  [rbp+30h+var_A0], xmm0
0x1800e789c  mov     [rbp+30h+var_90], r15
0x1800e78a0  lea     rcx, [rbp+30h+var_A0]
0x1800e78a4  call    ?_Tidy@?$vector@UUQIConfig@Configuration@UsageAndQualityInsights@@V?$allocator@UUQIConfig@Configuration@UsageAndQualityInsights@@@std@@@std@@AEAAXXZ; std::vector<UsageAndQualityInsights::Configuration::UQIConfig>::_Tidy(void)
0x1800e78a9  test    rdi, rdi
0x1800e78ac  jz      short loc_1800E78C7
0x1800e78ae  call    cs:__imp_GetLastError
0x1800e78b4  mov     ebx, eax
0x1800e78b6  mov     rcx, rdi; SRWLock
0x1800e78b9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800e78bf  mov     ecx, ebx; dwErrCode
0x1800e78c1  call    cs:__imp_SetLastError
0x1800e78c7  mov     [rsp+130h+pv], r15
0x1800e78cc  lea     rdx, [rbp+30h+var_88]
0x1800e78d0  lea     rcx, [rsp+130h+var_F0]
0x1800e78d5  call    ?MetricEventConfigFromUQIConfigArray@Configuration@UsageAndQualityInsights@@YA?AUMetricEventConfig@12@AEBV?$vector@UUQIConfig@Configuration@UsageAndQualityInsights@@V?$allocator@UUQIConfig@Configuration@UsageAndQualityInsights@@@std@@@std@@@Z; UsageAndQualityInsights::Configuration::MetricEventConfigFromUQIConfigArray(std::vector<UsageAndQualityInsights::Configuration::UQIConfig> const &)
0x1800e78da  nop
0x1800e78db  lea     rdx, [rsp+130h+var_F0]
0x1800e78e0  lea     rcx, [rsp+130h+var_F8]
0x1800e78e5  call    ?MetricEventConfigToUtcSideloadConfig@Configuration@UsageAndQualityInsights@@YA?AUJsonObject@Json@Data@Windows@winrt@@AEBUMetricEventConfig@12@@Z; UsageAndQualityInsights::Configuration::MetricEventConfigToUtcSideloadConfig(UsageAndQualityInsights::Configuration::MetricEventConfig const &)
0x1800e78ea  nop
0x1800e78eb  lea     rdx, [rdi+88h]
0x1800e78f2  lea     rcx, [rsp+130h+var_F8]
0x1800e78f7  call    ?StoreJsonToPath@ConfigStore@Configuration@UsageAndQualityInsights@@CAXAEBUJsonObject@Json@Data@Windows@winrt@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UsageAndQualityInsights::Configuration::ConfigStore::StoreJsonToPath(winrt::Windows::Data::Json::JsonObject const &,std::wstring const &)
0x1800e78fc  lea     rdx, [rsp+130h+var_100]
0x1800e7901  mov     rcx, rsi
0x1800e7904  call    ?ToJson@CompiledUQIConfig@Configuration@UsageAndQualityInsights@@QEBA?AUJsonObject@Json@Data@Windows@winrt@@XZ; UsageAndQualityInsights::Configuration::CompiledUQIConfig::ToJson(void)
0x1800e7909  nop
0x1800e790a  lea     rdx, [rdi+68h]
0x1800e790e  mov     rcx, rax
0x1800e7911  call    ?StoreJsonToPath@ConfigStore@Configuration@UsageAndQualityInsights@@CAXAEBUJsonObject@Json@Data@Windows@winrt@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UsageAndQualityInsights::Configuration::ConfigStore::StoreJsonToPath(winrt::Windows::Data::Json::JsonObject const &,std::wstring const &)
0x1800e7916  nop
0x1800e7917  cmp     [rsp+130h+var_100], r15
0x1800e791c  jz      short loc_1800E7928
0x1800e791e  lea     rcx, [rsp+130h+var_100]
0x1800e7923  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800e7928  call    ?EnableMetricGroup@ConfigStore@Configuration@UsageAndQualityInsights@@AEAAXXZ; UsageAndQualityInsights::Configuration::ConfigStore::EnableMetricGroup(void)
0x1800e792d  mov     rbx, [rbp+30h+var_A8]
0x1800e7931  mov     [rsp+130h+pv], rbx
0x1800e7936  test    rbx, rbx
0x1800e7939  jz      short loc_1800E7942
0x1800e793b  lock inc dword ptr [rbx+110h]
0x1800e7942  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800e7949  call    cs:__imp_EnterCriticalSection
0x1800e794f  inc     dword ptr [rbx+0F0h]
0x1800e7955  or      dword ptr [rbx+48h], 0B00h
0x1800e795c  cmp     [rbx+0F8h], r15
0x1800e7963  jz      short loc_1800E7973
0x1800e7965  mov     edx, 0Ah
0x1800e796a  lea     rcx, [rbx+8]
0x1800e796e  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x1800e7973  lea     rcx, [rsp+130h+pv]
0x1800e7978  call    ??1?$test_data_control@V?$merged_data@U_tip_UQISaveFactsToFactStoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>(void)
0x1800e797d  nop
0x1800e797e  cmp     [rsp+130h+var_F8], r15
0x1800e7983  jz      short loc_1800E7990
0x1800e7985  lea     rcx, [rsp+130h+var_F8]
0x1800e798a  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800e798f  nop
0x1800e7990  mov     r8, [rsp+130h+var_F0]
0x1800e7995  mov     r8, [r8+8]
0x1800e7999  lea     rdx, [rsp+130h+var_F0]
0x1800e799e  lea     rcx, [rsp+130h+var_F0]
0x1800e79a3  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMetricEventConfigEntry@Configuration@UsageAndQualityInsights@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::MetricEventConfigEntry>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::MetricEventConfigEntry>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::MetricEventConfigEntry>,void *>> &,std::_Tree_node<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::MetricEventConfigEntry>,void *> *)
0x1800e79a8  mov     edx, 0D8h; unsigned __int64
0x1800e79ad  mov     rcx, [rsp+130h+var_F0]; void *
0x1800e79b2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e79b7  nop
0x1800e79b8  lea     rcx, [rbp+30h+var_88]
0x1800e79bc  call    ?_Tidy@?$vector@UUQIConfig@Configuration@UsageAndQualityInsights@@V?$allocator@UUQIConfig@Configuration@UsageAndQualityInsights@@@std@@@std@@AEAAXXZ; std::vector<UsageAndQualityInsights::Configuration::UQIConfig>::_Tidy(void)
0x1800e79c1  nop
0x1800e79c2  mov     rbx, [rbp+30h+var_A8]
0x1800e79c6  test    rbx, rbx
0x1800e79c9  jz      short loc_1800E79EC
0x1800e79cb  mov     eax, r13d
0x1800e79ce  lock xadd [rbx+110h], eax
0x1800e79d6  add     eax, r13d
0x1800e79d9  jnz     short loc_1800E79EC
0x1800e79db  mov     rcx, rbx
0x1800e79de  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x1800e79e3  mov     rcx, rbx; pv
0x1800e79e6  call    cs:__imp_CoTaskMemFree
0x1800e79ec  lea     rcx, [rsp+130h+var_D8]; this
0x1800e79f1  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800e79f6  mov     rcx, [rbp+30h+var_30]
0x1800e79fa  xor     rcx, rsp; StackCookie
0x1800e79fd  call    __security_check_cookie
0x1800e7a02  lea     r11, [rsp+130h+var_20]
0x1800e7a0a  mov     rbx, [r11+38h]
0x1800e7a0e  mov     rsi, [r11+40h]
0x1800e7a12  mov     rsp, r11
0x1800e7a15  pop     r15
0x1800e7a17  pop     r14
0x1800e7a19  pop     r13
0x1800e7a1b  pop     rdi
0x1800e7a1c  pop     rbp
0x1800e7a1d  retn
0x1800e7a1e  lea     r8, [rbp+30h+var_70]; struct std::error_code *
0x1800e7a22  lea     rdx, [rsp+130h+pv]; char *
0x1800e7a27  lea     rcx, aExists; "exists"
0x1800e7a2e  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
0x1800e7a34  lea     r8, [rbp+30h+var_50]; struct std::error_code *
0x1800e7a38  lea     rdx, [rsp+130h+pv]; char *
0x1800e7a3d  lea     rcx, aExists; "exists"
0x1800e7a44  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
```
