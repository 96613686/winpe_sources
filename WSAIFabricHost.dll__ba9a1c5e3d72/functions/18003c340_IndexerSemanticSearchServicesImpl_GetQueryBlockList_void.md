# IndexerSemanticSearchServicesImpl::GetQueryBlockList(void)

- ea: `0x18003c340`
- end: `0x18003c610`
- name: `?GetQueryBlockList@IndexerSemanticSearchServicesImpl@@AEAA?AUQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@XZ`
- size: `720`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003f5d0`
- `0x1800403b0`

## callees

- `0x180007f72`
- `0x18000c478`
- `0x180013d94`
- `0x1800187b0`
- `0x180018fa0`
- `0x18001a464`
- `0x18001fd14`
- `0x18002f924`
- `0x180030410`
- `0x1800318c4`
- `0x180031bac`
- `0x1800326e8`
- `0x180032ac4`
- `0x180032c94`
- `0x180032ca0`
- `0x180034ee8`
- `0x18003c340`
- `0x18004dea8`
- `0x18004ff60`
- `0x1800501c0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003c3db`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003c3db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c582`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c582`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003c378`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003c378`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003c3a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003c3bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003c3a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003c3bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c517`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c517`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c45d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c4ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c45d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c4ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c553`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c553`

## string_xrefs

- `0x18003c42c`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x18003c5cf`: `QueryBlockList::CreateAsync timed out`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 *__fastcall IndexerSemanticSearchServicesImpl::GetQueryBlockList(__int64 a1, __int64 *a2)
{
  RTL_SRWLOCK *v4; // rbx
  __int64 *v5; // rdi
  __int64 v6; // rcx
  RTL_SRWLOCK *v7; // r14
  __int64 v8; // rax
  const wchar_t *v9; // r9
  struct _RTL_CRITICAL_SECTION *v10; // rbx
  __int64 *v11; // rbx
  __int64 v12; // rcx
  _DWORD *v13; // rbx
  struct _RTL_CRITICAL_SECTION *v14; // rsi
  struct _RTL_CRITICAL_SECTION *v15; // rbx
  __int64 v16; // rcx
  __int64 v18; // rax
  __int64 v19; // rbx
  unsigned int *v20; // rax
  _BYTE v21[8]; // [rsp+30h] [rbp-59h] BYREF
  _BYTE v22[48]; // [rsp+38h] [rbp-51h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-21h]
  _BYTE pExceptionObject[24]; // [rsp+70h] [rbp-19h] BYREF
  _BYTE v25[32]; // [rsp+88h] [rbp-1h] BYREF
  _BYTE v26[56]; // [rsp+A8h] [rbp+1Fh] BYREF
  struct _RTL_CRITICAL_SECTION *v27; // [rsp+F0h] [rbp+67h] BYREF
  __int64 v28; // [rsp+100h] [rbp+77h] BYREF
  __int64 v29; // [rsp+108h] [rbp+7Fh] BYREF

  LODWORD(v27) = 4;
  v4 = *(RTL_SRWLOCK **)std::unordered_map<enum AIFabric_Component,std::unique_ptr<wil::srwlock>>::operator[](
                          a1 + 32,
                          &v27);
  AcquireSRWLockShared(v4);
  v5 = (__int64 *)(a1 + 128);
  v6 = *(_QWORD *)(a1 + 128);
  if ( v6 )
  {
    *a2 = v6;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    if ( v4 )
      ReleaseSRWLockShared(v4);
  }
  else
  {
    if ( v4 )
      ReleaseSRWLockShared(v4);
    LODWORD(v27) = 4;
    v7 = *(RTL_SRWLOCK **)std::unordered_map<enum AIFabric_Component,std::unique_ptr<wil::srwlock>>::operator[](
                            a1 + 32,
                            &v27);
    AcquireSRWLockExclusive(v7);
    if ( !*v5 )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 152) + 24LL))(*(_QWORD *)(a1 + 152), &v29);
      winrt::impl::consume_Windows_Foundation_IAsyncAction<winrt::Windows::Foundation::IAsyncAction>::get(v8);
      if ( v29 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v29);
      SearchIndexerTrace::Verbose(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
        (const wchar_t *)0x32F,
        (unsigned int)L"Query Block List Available",
        v9);
      tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>((__int64)v21);
      v10 = (struct _RTL_CRITICAL_SECTION *)pv;
      v27 = (struct _RTL_CRITICAL_SECTION *)pv;
      if ( pv )
        _InterlockedIncrement((volatile signed __int32 *)pv + 72);
      EnterCriticalSection(v10 + 5);
      ++LODWORD(v10[6].DebugInfo);
      LODWORD(v10[6].SpinCount) = 32;
      tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v27);
      winrt::Microsoft::Windows::SemanticSearch::QueryBlockList::CreateAsync();
      if ( !(unsigned int)winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList>>(
                            &v28,
                            0x1D4C0u) )
      {
        v18 = tip2::test_watcher<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::operator->(
                v21,
                &v27);
        *(_BYTE *)(std::unique_ptr<wil::srwlock>::operator->(v18) + 276) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v27);
        v19 = winrt::impl::slim_source_location::current(v26);
        winrt::param::hstring::hstring((winrt::param::hstring *)v25, L"QueryBlockList::CreateAsync timed out");
        v20 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v27, -2147023436);
        winrt::hresult_error::hresult_error(pExceptionObject, *v20, v25, v19);
        throw (winrt::hresult_error *)pExceptionObject;
      }
      v11 = (__int64 *)winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList>,winrt::Microsoft::Windows::SemanticSearch::QueryBlockList>::get(
                         &v28,
                         &v27);
      if ( v5 != v11 )
      {
        if ( *v5 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 128);
        v12 = *v11;
        *v11 = 0;
        *v5 = v12;
      }
      if ( v27 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v27);
      v13 = pv;
      v14 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
      EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
      v13[18] |= 0x300u;
      if ( *((_QWORD *)v13 + 31) )
        tip2::details::shared_data<0,0,0>::complete_helper(v13 + 2, 2);
      if ( v14 )
        LeaveCriticalSection(v14);
      if ( v28 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v28);
      v15 = (struct _RTL_CRITICAL_SECTION *)pv;
      if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v15);
        CoTaskMemFree(v15);
      }
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v22);
    }
    v16 = *v5;
    *a2 = *v5;
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
    if ( v7 )
      ReleaseSRWLockExclusive(v7);
  }
  return a2;
}

```

## disassembly

```asm
0x18003c340  mov     [rsp-8+arg_8], rbx
0x18003c345  push    rbp
0x18003c346  push    rsi
0x18003c347  push    rdi
0x18003c348  push    r14
0x18003c34a  push    r15
0x18003c34c  lea     rbp, [rsp-37h]
0x18003c351  sub     rsp, 0C0h
0x18003c358  mov     r15, rdx
0x18003c35b  mov     rsi, rcx
0x18003c35e  mov     dword ptr [rbp+57h+arg_0], 4
0x18003c365  lea     rdx, [rbp+57h+arg_0]
0x18003c369  add     rcx, 20h ; ' '
0x18003c36d  call    ??A?$unordered_map@W4AIFabric_Component@@V?$unique_ptr@Vsrwlock@wil@@U?$default_delete@Vsrwlock@wil@@@std@@@std@@U?$hash@W4AIFabric_Component@@@3@U?$equal_to@W4AIFabric_Component@@@3@V?$allocator@U?$pair@$$CBW4AIFabric_Component@@V?$unique_ptr@Vsrwlock@wil@@U?$default_delete@Vsrwlock@wil@@@std@@@std@@@std@@@3@@std@@QEAAAEAV?$unique_ptr@Vsrwlock@wil@@U?$default_delete@Vsrwlock@wil@@@std@@@1@$$QEAW4AIFabric_Component@@@Z; std::unordered_map<AIFabric_Component,std::unique_ptr<wil::srwlock>>::operator[](AIFabric_Component &&)
0x18003c372  mov     rbx, [rax]
0x18003c375  mov     rcx, rbx; SRWLock
0x18003c378  call    cs:__imp_AcquireSRWLockShared
0x18003c37e  lea     rdi, [rsi+80h]
0x18003c385  mov     rcx, [rdi]
0x18003c388  test    rcx, rcx
0x18003c38b  jz      short loc_18003C3B3
0x18003c38d  mov     [r15], rcx
0x18003c390  mov     rax, [rcx]
0x18003c393  mov     rax, [rax+8]
0x18003c397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c39c  test    rbx, rbx
0x18003c39f  jz      loc_18003C588
0x18003c3a5  mov     rcx, rbx; SRWLock
0x18003c3a8  call    cs:__imp_ReleaseSRWLockShared
0x18003c3ae  jmp     loc_18003C588
0x18003c3b3  test    rbx, rbx
0x18003c3b6  jz      short loc_18003C3C1
0x18003c3b8  mov     rcx, rbx; SRWLock
0x18003c3bb  call    cs:__imp_ReleaseSRWLockShared
0x18003c3c1  mov     dword ptr [rbp+57h+arg_0], 4
0x18003c3c8  lea     rdx, [rbp+57h+arg_0]
0x18003c3cc  lea     rcx, [rsi+20h]
0x18003c3d0  call    ??A?$unordered_map@W4AIFabric_Component@@V?$unique_ptr@Vsrwlock@wil@@U?$default_delete@Vsrwlock@wil@@@std@@@std@@U?$hash@W4AIFabric_Component@@@3@U?$equal_to@W4AIFabric_Component@@@3@V?$allocator@U?$pair@$$CBW4AIFabric_Component@@V?$unique_ptr@Vsrwlock@wil@@U?$default_delete@Vsrwlock@wil@@@std@@@std@@@std@@@3@@std@@QEAAAEAV?$unique_ptr@Vsrwlock@wil@@U?$default_delete@Vsrwlock@wil@@@std@@@1@$$QEAW4AIFabric_Component@@@Z; std::unordered_map<AIFabric_Component,std::unique_ptr<wil::srwlock>>::operator[](AIFabric_Component &&)
0x18003c3d5  mov     r14, [rax]
0x18003c3d8  mov     rcx, r14; SRWLock
0x18003c3db  call    cs:__imp_AcquireSRWLockExclusive
0x18003c3e1  mov     [rbp+57h+var_B8], r14
0x18003c3e5  cmp     qword ptr [rdi], 0
0x18003c3e9  jnz     loc_18003C562
0x18003c3ef  mov     rcx, [rsi+98h]
0x18003c3f6  mov     rax, [rcx]
0x18003c3f9  lea     rdx, [rbp+57h+arg_18]
0x18003c3fd  mov     rax, [rax+18h]
0x18003c401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c406  nop
0x18003c407  mov     rcx, rax
0x18003c40a  call    ?get@?$consume_Windows_Foundation_IAsyncAction@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncAction<winrt::Windows::Foundation::IAsyncAction>::get(void)
0x18003c40f  nop
0x18003c410  cmp     [rbp+57h+arg_18], 0
0x18003c415  jz      short loc_18003C420
0x18003c417  lea     rcx, [rbp+57h+arg_18]
0x18003c41b  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003c420  lea     r8, aQueryBlockList; "Query Block List Available"
0x18003c427  mov     edx, 32Fh; wchar_t *
0x18003c42c  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x18003c433  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x18003c438  lea     rcx, [rbp+57h+var_B0]
0x18003c43c  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18003c441  nop
0x18003c442  mov     rbx, [rbp+57h+pv]
0x18003c446  mov     [rbp+57h+arg_0], rbx
0x18003c44a  test    rbx, rbx
0x18003c44d  jz      short loc_18003C456
0x18003c44f  lock inc dword ptr [rbx+120h]
0x18003c456  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18003c45d  call    cs:__imp_EnterCriticalSection
0x18003c463  inc     dword ptr [rbx+0F0h]
0x18003c469  mov     dword ptr [rbx+110h], 20h ; ' '
0x18003c473  lea     rcx, [rbp+57h+arg_0]
0x18003c477  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x18003c47c  lea     rcx, [rbp+57h+arg_10]
0x18003c480  call    ?CreateAsync@QueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@SA@XZ; winrt::Microsoft::Windows::SemanticSearch::QueryBlockList::CreateAsync(void)
0x18003c485  nop
0x18003c486  mov     edx, 1D4C0h
0x18003c48b  lea     rcx, [rbp+57h+arg_10]
0x18003c48f  call    ??$wait_for_completed@U?$IAsyncOperation@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@1@I@Z
0x18003c494  lea     rdx, [rbp+57h+arg_0]
0x18003c498  test    eax, eax
0x18003c49a  jz      loc_18003C5A2
0x18003c4a0  lea     rcx, [rbp+57h+arg_10]
0x18003c4a4  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@UQueryBlockList@SemanticSearch@3Microsoft@4@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList>,winrt::Microsoft::Windows::SemanticSearch::QueryBlockList>::get(void)
0x18003c4a9  mov     rbx, rax
0x18003c4ac  cmp     rdi, rax
0x18003c4af  jz      short loc_18003C4CC
0x18003c4b1  cmp     qword ptr [rdi], 0
0x18003c4b5  jz      short loc_18003C4BF
0x18003c4b7  mov     rcx, rdi
0x18003c4ba  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003c4bf  mov     rcx, [rbx]
0x18003c4c2  mov     qword ptr [rbx], 0
0x18003c4c9  mov     [rdi], rcx
0x18003c4cc  cmp     [rbp+57h+arg_0], 0
0x18003c4d1  jz      short loc_18003C4DC
0x18003c4d3  lea     rcx, [rbp+57h+arg_0]
0x18003c4d7  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003c4dc  mov     rbx, [rbp+57h+pv]
0x18003c4e0  lea     rsi, [rbx+0C8h]
0x18003c4e7  mov     rcx, rsi; lpCriticalSection
0x18003c4ea  call    cs:__imp_EnterCriticalSection
0x18003c4f0  or      dword ptr [rbx+48h], 300h
0x18003c4f7  cmp     qword ptr [rbx+0F8h], 0
0x18003c4ff  jz      short loc_18003C50F
0x18003c501  mov     edx, 2
0x18003c506  lea     rcx, [rbx+8]
0x18003c50a  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18003c50f  test    rsi, rsi
0x18003c512  jz      short loc_18003C51E
0x18003c514  mov     rcx, rsi; lpCriticalSection
0x18003c517  call    cs:__imp_LeaveCriticalSection
0x18003c51d  nop
0x18003c51e  cmp     [rbp+57h+arg_10], 0
0x18003c523  jz      short loc_18003C52F
0x18003c525  lea     rcx, [rbp+57h+arg_10]
0x18003c529  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003c52e  nop
0x18003c52f  mov     rbx, [rbp+57h+pv]
0x18003c533  test    rbx, rbx
0x18003c536  jz      short loc_18003C559
0x18003c538  or      eax, 0FFFFFFFFh
0x18003c53b  lock xadd [rbx+120h], eax
0x18003c543  cmp     eax, 1
0x18003c546  jnz     short loc_18003C559
0x18003c548  mov     rcx, rbx
0x18003c54b  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x18003c550  mov     rcx, rbx; pv
0x18003c553  call    cs:__imp_CoTaskMemFree
0x18003c559  lea     rcx, [rbp+57h+var_A8]; this
0x18003c55d  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18003c562  mov     rcx, [rdi]
0x18003c565  mov     [r15], rcx
0x18003c568  test    rcx, rcx
0x18003c56b  jz      short loc_18003C57A
0x18003c56d  mov     rax, [rcx]
0x18003c570  mov     rax, [rax+8]
0x18003c574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c579  nop
0x18003c57a  test    r14, r14
0x18003c57d  jz      short loc_18003C588
0x18003c57f  mov     rcx, r14; SRWLock
0x18003c582  call    cs:__imp_ReleaseSRWLockExclusive
0x18003c588  mov     rax, r15
0x18003c58b  mov     rbx, [rsp+0E0h+arg_8]
0x18003c593  add     rsp, 0C0h
0x18003c59a  pop     r15
0x18003c59c  pop     r14
0x18003c59e  pop     rdi
0x18003c59f  pop     rsi
0x18003c5a0  pop     rbp
0x18003c5a1  retn
0x18003c5a2  lea     rcx, [rbp+57h+var_B0]
0x18003c5a6  call    ??C?$test_watcher@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@1@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::operator->(void)
0x18003c5ab  mov     rcx, rax
0x18003c5ae  call    ??C?$unique_ptr@Vsrwlock@wil@@U?$default_delete@Vsrwlock@wil@@@std@@@std@@QEBAPEAVsrwlock@wil@@XZ; std::unique_ptr<wil::srwlock>::operator->(void)
0x18003c5b3  mov     byte ptr [rax+114h], 1
0x18003c5ba  lea     rcx, [rbp+57h+arg_0]
0x18003c5be  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x18003c5c3  lea     rcx, [rbp+57h+var_38]
0x18003c5c7  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18003c5cc  mov     rbx, rax
0x18003c5cf  lea     rdx, aQueryblocklist; "QueryBlockList::CreateAsync timed out"
0x18003c5d6  lea     rcx, [rbp+57h+var_58]; this
0x18003c5da  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18003c5df  mov     edx, 800705B4h; int
0x18003c5e4  lea     rcx, [rbp+57h+arg_0]; this
0x18003c5e8  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18003c5ed  mov     r9, rbx
0x18003c5f0  lea     r8, [rbp+57h+var_58]
0x18003c5f4  mov     edx, [rax]
0x18003c5f6  lea     rcx, [rbp+57h+pExceptionObject]
0x18003c5fa  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18003c5ff  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18003c606  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003c60a  call    _CxxThrowException_0
```
