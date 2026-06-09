# UsageAndQualityInsights::Database::UQIDatabaseManager::GetOrCreateDatabaseImpl(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,UsageAndQualityInsights::Database::UQIDatabaseType)

- ea: `0x1800366f4`
- end: `0x180036abd`
- name: `?GetOrCreateDatabaseImpl@UQIDatabaseManager@Database@UsageAndQualityInsights@@AEAA?AV?$shared_ptr@VUQIDatabase@Database@UsageAndQualityInsights@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@W4UQIDatabaseType@23@@Z`
- size: `969`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180036ac4`
- `0x180036c7c`

## callees

- `0x180005e7c`
- `0x1800107b0`
- `0x180013c48`
- `0x180016628`
- `0x180016dcc`
- `0x180018e64`
- `0x18001a8f4`
- `0x18002c4a0`
- `0x180030d30`
- `0x18003459c`
- `0x1800346b0`
- `0x1800347c4`
- `0x1800366f4`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036a18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036a50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036a18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036a50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036745`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800369ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036745`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800369ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003678a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036a40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003678a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036a40`

## string_xrefs

- `0x180036a93`: `onecore\base\usageandqualityinsights\service\lib\database\databasemanager.cpp`
- `0x180036aab`: `onecore\base\usageandqualityinsights\service\lib\database\databasemanager.cpp`
- `0x180036875`: `GetOrCreateUserDatabase From Cache Identifier: %ws`
- `0x1800369cc`: `GetOrCreateUserDatabase No Cache Identifier: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall UsageAndQualityInsights::Database::UQIDatabaseManager::GetOrCreateDatabaseImpl(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        int a4)
{
  __int64 *v8; // rax
  __int64 v9; // r14
  void *v10; // rdi
  _QWORD *v11; // rdx
  __int64 v12; // r9
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rcx
  volatile signed __int32 *v18; // rdi
  __int64 *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rdx
  volatile signed __int32 *v22; // rdi
  volatile signed __int32 *v23; // rdi
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rcx
  volatile signed __int32 *v27; // rdi
  unsigned int v29; // eax
  int v30; // [rsp+20h] [rbp-40h]
  char *v31; // [rsp+28h] [rbp-38h]
  LPVOID pv; // [rsp+38h] [rbp-28h] BYREF
  volatile signed __int32 *v33; // [rsp+40h] [rbp-20h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-18h]
  __int64 v35; // [rsp+50h] [rbp-10h]
  __int64 v36; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  if ( (unsigned int)(a4 - 1) > 1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12,
      (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\database\\databasemanager.cpp",
      (const char *)0x80070005LL,
      v30);
  lpCriticalSection = (LPCRITICAL_SECTION)(a1 + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  v35 = a1 + 64;
  v8 = (__int64 *)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>,>(&pv);
  v9 = *v8;
  *v8 = 0;
  v36 = v9;
  v10 = pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 68, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(v10);
    CoTaskMemFree(v10);
  }
  tip2::details::shared_data<0,0,0>::start(v9 + 8, &pv);
  *a2 = 0;
  a2[1] = 0;
  if ( a3[3] <= 7u )
    v11 = a3;
  else
    v11 = (_QWORD *)*a3;
  v12 = 0xCBF29CE484222325uLL;
  v13 = 0;
  v14 = 2LL * a3[2];
  if ( v14 )
  {
    do
      v12 = 0x100000001B3LL * (*((unsigned __int8 *)v11 + v13++) ^ (unsigned __int64)v12);
    while ( v13 < v14 );
  }
  v15 = *(_QWORD *)(std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
                      a1,
                      &pv,
                      a3,
                      v12)
                  + 8);
  if ( !v15 || v15 == *(_QWORD *)(a1 + 8) )
  {
    if ( a4 == 1 )
    {
      v19 = (__int64 *)std::make_shared<UsageAndQualityInsights::Database::FactStoreDatabase,std::wstring const &>(
                         &pv,
                         a3);
    }
    else
    {
      if ( a4 != 2 )
      {
        v29 = wil::verify_hresult<long>(2147942487LL);
        LODWORD(v31) = a4;
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x5B,
          (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\database\\databasemanager.cpp",
          (const char *)v29,
          (int)"Unexpected UQIDatabaseType: %d",
          v31,
          1);
      }
      v19 = (__int64 *)std::make_shared<UsageAndQualityInsights::Database::ServiceUsageDatabase,std::wstring const &>(
                         &pv,
                         a3);
    }
    v20 = *v19;
    v21 = v19[1];
    *v19 = 0;
    v19[1] = 0;
    *a2 = v20;
    v22 = (volatile signed __int32 *)a2[1];
    a2[1] = v21;
    if ( v22 )
    {
      if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
        if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
      }
    }
    v23 = v33;
    if ( v33 )
    {
      if ( _InterlockedExchangeAdd(v33 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
        if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
      }
    }
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 8LL))(*a2);
    v24 = *(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<UsageAndQualityInsights::Database::UQIDatabase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<UsageAndQualityInsights::Database::UQIDatabase>>>,0>>::_Try_emplace<std::wstring const &,>(
                       a1,
                       &pv,
                       a3);
    v25 = a2[1];
    if ( v25 )
      _InterlockedIncrement((volatile signed __int32 *)(v25 + 8));
    v26 = a2[1];
    *(_QWORD *)(v24 + 48) = *a2;
    v27 = *(volatile signed __int32 **)(v24 + 56);
    *(_QWORD *)(v24 + 56) = v26;
    if ( v27 )
    {
      if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
        if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
      }
    }
    if ( a3[3] > 7u )
      a3 = (_QWORD *)*a3;
    UsageAndQualityInsightsTraceLogging::TraceLoggingInfo("GetOrCreateUserDatabase No Cache Identifier: %ws", a3);
  }
  else
  {
    v16 = *(_QWORD *)(v15 + 56);
    if ( v16 )
      _InterlockedIncrement((volatile signed __int32 *)(v16 + 8));
    v17 = *(_QWORD *)(v15 + 56);
    *a2 = *(_QWORD *)(v15 + 48);
    v18 = (volatile signed __int32 *)a2[1];
    a2[1] = v17;
    if ( v18 )
    {
      if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    if ( a3[3] > 7u )
      a3 = (_QWORD *)*a3;
    UsageAndQualityInsightsTraceLogging::TraceLoggingInfo("GetOrCreateUserDatabase From Cache Identifier: %ws", a3);
  }
  if ( v9 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 200));
    *(_DWORD *)(v9 + 72) |= 0x300u;
    if ( *(_QWORD *)(v9 + 248) )
      tip2::details::shared_data<0,0,0>::complete_helper(v9 + 8, 2);
    if ( v9 != -200 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 200));
  }
  if ( v9 && _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 272), 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(v9);
    CoTaskMemFree((LPVOID)v9);
  }
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  return a2;
}

```

## disassembly

```asm
0x1800366f4  mov     [rsp-38h+arg_0], rbx
0x1800366f9  mov     [rsp-38h+arg_8], rdx
0x1800366fe  push    rbp
0x1800366ff  push    rsi
0x180036700  push    rdi
0x180036701  push    r12
0x180036703  push    r13
0x180036705  push    r14
0x180036707  push    r15
0x180036709  mov     rbp, rsp
0x18003670c  sub     rsp, 60h
0x180036710  mov     r15d, r9d
0x180036713  mov     rbx, r8
0x180036716  mov     rsi, rdx
0x180036719  mov     r12, rcx
0x18003671c  mov     [rbp+var_30], 0
0x180036723  lea     eax, [r9-1]
0x180036727  cmp     eax, 1
0x18003672a  setnbe  al
0x18003672d  mov     rcx, [rbp+38h]; this
0x180036731  test    al, al
0x180036733  jnz     loc_180036AA5
0x180036739  lea     rdi, [r12+40h]
0x18003673e  mov     [rbp+lpCriticalSection], rdi
0x180036742  mov     rcx, rdi; lpCriticalSection
0x180036745  call    cs:__imp_EnterCriticalSection
0x18003674b  mov     [rbp+var_10], rdi
0x18003674f  lea     rcx, [rbp+pv]
0x180036753  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>,>(void)
0x180036758  mov     r14, [rax]
0x18003675b  mov     qword ptr [rax], 0
0x180036762  mov     [rbp+var_8], r14
0x180036766  mov     rdi, [rbp+pv]
0x18003676a  test    rdi, rdi
0x18003676d  jz      short loc_180036790
0x18003676f  or      eax, 0FFFFFFFFh
0x180036772  lock xadd [rdi+110h], eax
0x18003677a  cmp     eax, 1
0x18003677d  jnz     short loc_180036790
0x18003677f  mov     rcx, rdi
0x180036782  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x180036787  mov     rcx, rdi; pv
0x18003678a  call    cs:__imp_CoTaskMemFree
0x180036790  lea     rdx, [rbp+pv]
0x180036794  lea     rcx, [r14+8]
0x180036798  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18003679d  nop
0x18003679e  xor     edi, edi
0x1800367a0  mov     [rsi], rdi
0x1800367a3  mov     [rsi+8], rdi
0x1800367a7  mov     [rbp+var_30], 1
0x1800367ae  mov     r8, [rbx+10h]
0x1800367b2  cmp     qword ptr [rbx+18h], 7
0x1800367b7  jbe     short loc_1800367BE
0x1800367b9  mov     rdx, [rbx]
0x1800367bc  jmp     short loc_1800367C1
0x1800367be  mov     rdx, rbx
0x1800367c1  mov     r9, 0CBF29CE484222325h
0x1800367cb  mov     rcx, rdi
0x1800367ce  add     r8, r8
0x1800367d1  jz      short loc_1800367F0
0x1800367d3  movzx   eax, byte ptr [rdx+rcx]
0x1800367d7  xor     r9, rax
0x1800367da  mov     r10, 100000001B3h
0x1800367e4  imul    r9, r10
0x1800367e8  inc     rcx
0x1800367eb  cmp     rcx, r8
0x1800367ee  jb      short loc_1800367D3
0x1800367f0  mov     r8, rbx
0x1800367f3  lea     rdx, [rbp+pv]
0x1800367f7  mov     rcx, r12
0x1800367fa  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x1800367ff  mov     rax, [rax+8]
0x180036803  test    rax, rax
0x180036806  jz      short loc_180036881
0x180036808  cmp     rax, [r12+8]
0x18003680d  jz      short loc_180036881
0x18003680f  mov     rcx, [rax+38h]
0x180036813  test    rcx, rcx
0x180036816  jz      short loc_18003681C
0x180036818  lock inc dword ptr [rcx+8]
0x18003681c  mov     rcx, [rax+38h]
0x180036820  mov     rax, [rax+30h]
0x180036824  mov     [rsi], rax
0x180036827  mov     rdi, [rsi+8]
0x18003682b  mov     [rsi+8], rcx
0x18003682f  test    rdi, rdi
0x180036832  jz      short loc_18003686B
0x180036834  or      eax, 0FFFFFFFFh
0x180036837  lock xadd [rdi+8], eax
0x18003683c  cmp     eax, 1
0x18003683f  jnz     short loc_18003686B
0x180036841  mov     rax, [rdi]
0x180036844  mov     rcx, rdi
0x180036847  mov     rax, [rax]
0x18003684a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003684f  or      eax, 0FFFFFFFFh
0x180036852  lock xadd [rdi+0Ch], eax
0x180036857  cmp     eax, 1
0x18003685a  jnz     short loc_18003686B
0x18003685c  mov     rax, [rdi]
0x18003685f  mov     rcx, rdi
0x180036862  mov     rax, [rax+8]
0x180036866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003686b  cmp     qword ptr [rbx+18h], 7
0x180036870  jbe     short loc_180036875
0x180036872  mov     rbx, [rbx]
0x180036875  lea     rcx, aGetorcreateuse_0; "GetOrCreateUserDatabase From Cache Iden"...
0x18003687c  jmp     loc_1800369D3
0x180036881  mov     ecx, r15d
0x180036884  sub     ecx, 1
0x180036887  jz      short loc_1800368A0
0x180036889  cmp     ecx, 1
0x18003688c  jnz     loc_180036A71
0x180036892  mov     rdx, rbx
0x180036895  lea     rcx, [rbp+pv]
0x180036899  call    ??$make_shared@VServiceUsageDatabase@Database@UsageAndQualityInsights@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@YA?AV?$shared_ptr@VServiceUsageDatabase@Database@UsageAndQualityInsights@@@0@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::make_shared<UsageAndQualityInsights::Database::ServiceUsageDatabase,std::wstring const &>(std::wstring const &)
0x18003689e  jmp     short loc_1800368AC
0x1800368a0  mov     rdx, rbx
0x1800368a3  lea     rcx, [rbp+pv]
0x1800368a7  call    ??$make_shared@VFactStoreDatabase@Database@UsageAndQualityInsights@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@YA?AV?$shared_ptr@VFactStoreDatabase@Database@UsageAndQualityInsights@@@0@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::make_shared<UsageAndQualityInsights::Database::FactStoreDatabase,std::wstring const &>(std::wstring const &)
0x1800368ac  mov     rcx, [rax]
0x1800368af  mov     rdx, [rax+8]
0x1800368b3  mov     [rax], rdi
0x1800368b6  mov     [rax+8], rdi
0x1800368ba  mov     [rsi], rcx
0x1800368bd  or      r15d, 0FFFFFFFFh
0x1800368c1  mov     rdi, [rsi+8]
0x1800368c5  test    rdi, rdi
0x1800368c8  mov     [rsi+8], rdx
0x1800368cc  jz      short loc_180036905
0x1800368ce  mov     eax, r15d
0x1800368d1  lock xadd [rdi+8], eax
0x1800368d6  add     eax, r15d
0x1800368d9  jnz     short loc_180036905
0x1800368db  mov     rax, [rdi]
0x1800368de  mov     rcx, rdi
0x1800368e1  mov     rax, [rax]
0x1800368e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368e9  mov     eax, r15d
0x1800368ec  lock xadd [rdi+0Ch], eax
0x1800368f1  add     eax, r15d
0x1800368f4  jnz     short loc_180036905
0x1800368f6  mov     rax, [rdi]
0x1800368f9  mov     rcx, rdi
0x1800368fc  mov     rax, [rax+8]
0x180036900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036905  mov     rdi, [rbp+var_20]
0x180036909  test    rdi, rdi
0x18003690c  jz      short loc_180036945
0x18003690e  mov     eax, r15d
0x180036911  lock xadd [rdi+8], eax
0x180036916  add     eax, r15d
0x180036919  jnz     short loc_180036945
0x18003691b  mov     rax, [rdi]
0x18003691e  mov     rcx, rdi
0x180036921  mov     rax, [rax]
0x180036924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036929  mov     eax, r15d
0x18003692c  lock xadd [rdi+0Ch], eax
0x180036931  add     eax, r15d
0x180036934  jnz     short loc_180036945
0x180036936  mov     rax, [rdi]
0x180036939  mov     rcx, rdi
0x18003693c  mov     rax, [rax+8]
0x180036940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036945  mov     rcx, [rsi]
0x180036948  mov     rax, [rcx]
0x18003694b  mov     rax, [rax+8]
0x18003694f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036954  mov     r8, rbx
0x180036957  lea     rdx, [rbp+pv]
0x18003695b  mov     rcx, r12
0x18003695e  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VUQIDatabase@Database@UsageAndQualityInsights@@@2@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VUQIDatabase@Database@UsageAndQualityInsights@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VUQIDatabase@Database@UsageAndQualityInsights@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<UsageAndQualityInsights::Database::UQIDatabase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<UsageAndQualityInsights::Database::UQIDatabase>>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180036963  mov     rdx, [rax]
0x180036966  mov     rax, [rsi+8]
0x18003696a  test    rax, rax
0x18003696d  jz      short loc_180036973
0x18003696f  lock inc dword ptr [rax+8]
0x180036973  mov     rcx, [rsi+8]
0x180036977  mov     rax, [rsi]
0x18003697a  mov     [rdx+30h], rax
0x18003697e  mov     rdi, [rdx+38h]
0x180036982  mov     [rdx+38h], rcx
0x180036986  test    rdi, rdi
0x180036989  jz      short loc_1800369C2
0x18003698b  or      eax, 0FFFFFFFFh
0x18003698e  lock xadd [rdi+8], eax
0x180036993  cmp     eax, 1
0x180036996  jnz     short loc_1800369C2
0x180036998  mov     rax, [rdi]
0x18003699b  mov     rcx, rdi
0x18003699e  mov     rax, [rax]
0x1800369a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800369a6  or      eax, 0FFFFFFFFh
0x1800369a9  lock xadd [rdi+0Ch], eax
0x1800369ae  cmp     eax, 1
0x1800369b1  jnz     short loc_1800369C2
0x1800369b3  mov     rax, [rdi]
0x1800369b6  mov     rcx, rdi
0x1800369b9  mov     rax, [rax+8]
0x1800369bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800369c2  cmp     qword ptr [rbx+18h], 7
0x1800369c7  jbe     short loc_1800369CC
0x1800369c9  mov     rbx, [rbx]
0x1800369cc  lea     rcx, aGetorcreateuse; "GetOrCreateUserDatabase No Cache Identi"...
0x1800369d3  mov     rdx, rbx
0x1800369d6  call    ?TraceLoggingInfo@UsageAndQualityInsightsTraceLogging@@SAXPEBDZZ; UsageAndQualityInsightsTraceLogging::TraceLoggingInfo(char const *,...)
0x1800369db  test    r14, r14
0x1800369de  jz      short loc_180036A1F
0x1800369e0  lea     rbx, [r14+0C8h]
0x1800369e7  mov     rcx, rbx; lpCriticalSection
0x1800369ea  call    cs:__imp_EnterCriticalSection
0x1800369f0  or      dword ptr [r14+48h], 300h
0x1800369f8  cmp     qword ptr [r14+0F8h], 0
0x180036a00  jz      short loc_180036A10
0x180036a02  mov     edx, 2
0x180036a07  lea     rcx, [r14+8]
0x180036a0b  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180036a10  test    rbx, rbx
0x180036a13  jz      short loc_180036A1F
0x180036a15  mov     rcx, rbx; lpCriticalSection
0x180036a18  call    cs:__imp_LeaveCriticalSection
0x180036a1e  nop
0x180036a1f  test    r14, r14
0x180036a22  jz      short loc_180036A47
0x180036a24  or      eax, 0FFFFFFFFh
0x180036a27  lock xadd [r14+110h], eax
0x180036a30  cmp     eax, 1
0x180036a33  jnz     short loc_180036A47
0x180036a35  mov     rcx, r14
0x180036a38  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x180036a3d  mov     rcx, r14; pv
0x180036a40  call    cs:__imp_CoTaskMemFree
0x180036a46  nop
0x180036a47  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180036a4b  test    rcx, rcx
0x180036a4e  jz      short loc_180036A56
0x180036a50  call    cs:__imp_LeaveCriticalSection
0x180036a56  mov     rax, rsi
0x180036a59  mov     rbx, [rsp+60h+arg_0]
0x180036a61  add     rsp, 60h
0x180036a65  pop     r15
0x180036a67  pop     r14
0x180036a69  pop     r13
0x180036a6b  pop     r12
0x180036a6d  pop     rdi
0x180036a6e  pop     rsi
0x180036a6f  pop     rbp
0x180036a70  retn
0x180036a71  mov     ecx, 80070057h
0x180036a76  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180036a7b  mov     r9d, eax; char *
0x180036a7e  mov     rcx, [rbp+38h]; this
0x180036a82  mov     dword ptr [rsp+60h+var_38], r15d; char *
0x180036a87  lea     rax, aUnexpectedUqid; "Unexpected UQIDatabaseType: %d"
0x180036a8e  mov     qword ptr [rsp+60h+var_40], rax; int
0x180036a93  lea     r8, aOnecoreBaseUsa_18; "onecore\\base\\usageandqualityinsights"...
0x180036a9a  mov     edx, 5Bh ; '['; void *
0x180036a9f  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180036aa5  mov     r9d, 80070005h; char *
0x180036aab  lea     r8, aOnecoreBaseUsa_18; "onecore\\base\\usageandqualityinsights"...
0x180036ab2  mov     edx, 12h; void *
0x180036ab7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
