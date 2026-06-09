# ModelPackageManager::MakeQueryBlockListAvailableAsync$_ResumeCoro$1

- ea: `0x180076a40`
- end: `0x180076e94`
- name: `ModelPackageManager::MakeQueryBlockListAvailableAsync$_ResumeCoro$1`
- size: `1108`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001aeb0`
- `0x180076a30`

## callees

- `0x180005140`
- `0x180007f72`
- `0x180008f84`
- `0x18000c478`
- `0x180014688`
- `0x180018fa0`
- `0x180019c3c`
- `0x18001a420`
- `0x18001de54`
- `0x18002d750`
- `0x18002f8ec`
- `0x1800318c4`
- `0x180031bac`
- `0x18004ba10`
- `0x18004dd6c`
- `0x18004dea8`
- `0x18004eb70`
- `0x18005266c`
- `0x180073ce8`
- `0x1800748c8`
- `0x180075a80`
- `0x180076a40`
- `0x1800783b8`
- `0x1800785a8`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076dae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076dae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076adc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076d82`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076adc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076d82`
- `msvcp_win!_Thrd_yield` at `0x180076c26`
- `msvcp_win!_Thrd_yield` at `0x180076cba`
- `msvcp_win!_Thrd_yield` at `0x180076c26`
- `msvcp_win!_Thrd_yield` at `0x180076cba`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180076e40`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180076e40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076c83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076de4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076c83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076de4`

## string_xrefs

- `0x180076d3c`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\modelpackagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall ModelPackageManager::MakeQueryBlockListAvailableAsync__ResumeCoro_1(_WORD *a1)
{
  _WORD *v2; // r15
  __int64 *v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rcx
  int v6; // eax
  _WORD *v7; // rbx
  const struct winrt::impl::slim_source_location *v8; // rax
  volatile __int64 *v9; // rbx
  struct _RTL_CRITICAL_SECTION *v10; // rbx
  volatile __int64 *v11; // rbx
  const char *v12; // rdx
  const char *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned __int16 v16; // ax
  __int64 v17; // r8
  unsigned int v18; // eax
  __int64 v19; // rbx
  struct _RTL_CRITICAL_SECTION *v20; // rbx
  const char *v21; // [rsp+28h] [rbp-D0h]
  _BYTE pExceptionObject[24]; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+68h] [rbp-90h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v2 = a1 + 62;
  switch ( a1[62] )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_42;
    case 2:
      tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>(a1 + 64);
      v3 = (__int64 *)tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::ensure_data(a1 + 64);
      v4 = *v3;
      *((_QWORD *)a1 + 17) = *v3;
      if ( v4 )
        _InterlockedAdd((volatile signed __int32 *)(v4 + 288), 1u);
      EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 200));
      ++*(_DWORD *)(v4 + 240);
      *(_DWORD *)(v4 + 272) = 22;
      tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(a1 + 68);
      *((_QWORD *)a1 + 33) = &qword_1800AF638;
      _InterlockedAdd64(&qword_1800AF638, 1u);
      v5 = winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>;
      if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics> )
      {
        *((_QWORD *)a1 + 35) = 0;
        *((_DWORD *)a1 + 72) = 0;
        *((_QWORD *)a1 + 37) = 0;
        *((_QWORD *)a1 + 38) = 0;
        v6 = (*(__int64 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v5 + 56LL))(v5, a1 + 140);
        if ( v6 < 0 )
          winrt::throw_hresult((unsigned int)v6, a1 + 144);
        v7 = a1 + 72;
        *((_QWORD *)a1 + 18) = *((_QWORD *)a1 + 35);
        _InterlockedDecrement64(&qword_1800AF638);
      }
      else
      {
        _InterlockedDecrement64(&qword_1800AF638);
        *((_QWORD *)a1 + 34) = _lambda_05cb80ee2c167c13088eab7ae81a7071_::_lambda_invoker_cdecl_;
        v7 = a1 + 72;
        winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>::call<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> (*)(winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics const &)>(
          0,
          (__int64)(a1 + 72),
          (void (__fastcall **)(__int64, __int64 *))a1 + 34);
      }
      if ( *((_DWORD *)a1 + 28) == 2 )
      {
        v8 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 156);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject, v8);
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *((_QWORD *)a1 + 19) = 0;
      *((_QWORD *)a1 + 20) = v7;
      *((_QWORD *)a1 + 21) = 0;
      *((_BYTE *)a1 + 176) = 1;
      *v2 = 4;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,>::promise_type>(
                              a1 + 76,
                              a1) )
        return;
      goto LABEL_23;
    case 4:
LABEL_23:
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_resume(
        a1 + 76,
        a1 + 92);
      v11 = (volatile __int64 *)*((_QWORD *)a1 + 19);
      if ( v11 )
      {
        v23 = *((_QWORD *)a1 + 19);
        while ( _InterlockedExchange64(v11, 0) == 1 )
          _Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 18) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 72);
      if ( !ModelPackageManager::IsQueryBlockListAvailable() )
      {
        ModelPackageManager::ThrowIfPackageDeploymentFailed((const struct winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult *)(a1 + 92));
        v13 = tip2::details::reason_string(
                (tip2::details *)"AIFabricAPIsPerfTest::reason::QueryBlockListNotAvailable",
                v12);
        v16 = tip2::details::validate_reason<enum _tip_AIFabricAPIsPerfTest::reason,5>(v15, v14, v13);
        tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::complete_and_fail(
          a1 + 64,
          v16,
          v17);
        v18 = wil::verify_hresult(2147549183LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x115,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\modelpackagemanager.cpp",
          (const char *)v18,
          (int)"MakeAvailableAsync succeeded but query block list is not available",
          v21);
      }
      if ( *((_QWORD *)a1 + 23) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 92);
      v19 = *((_QWORD *)a1 + 16);
      if ( v19 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(v19 + 200));
        *(_DWORD *)(v19 + 72) |= 0x300u;
        if ( *(_QWORD *)(v19 + 248) )
          tip2::details::shared_data<0,0,0>::complete_helper(v19 + 8, 2);
        if ( v19 != -200 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 200));
      }
      v20 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)a1 + 16);
      if ( v20 && _InterlockedExchangeAdd(&v20[7].LockCount, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v20);
        CoTaskMemFree(v20);
      }
      *((_QWORD *)a1 + 32) = a1 + 8;
      *v2 = 0;
      *(_QWORD *)a1 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticStore &,enum winrt::Windows::Indexer::SemanticSearch::ModelKind>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend() )
        goto LABEL_42;
      return;
    case 5:
      v9 = (volatile __int64 *)*((_QWORD *)a1 + 19);
      if ( v9 )
      {
        v23 = *((_QWORD *)a1 + 19);
        while ( _InterlockedExchange64(v9, 0) == 1 )
          _Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 18) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 72);
      v10 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)a1 + 16);
      if ( v10 && _InterlockedExchangeAdd(&v10[7].LockCount, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v10);
        CoTaskMemFree(v10);
      }
LABEL_42:
      if ( *((_QWORD *)a1 + 13) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 52);
      if ( *((_QWORD *)a1 + 12) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 48);
      __ExceptionPtrDestroy(a1 + 36);
      winrt::impl::root_implements<IndexerSemanticSearchServicesImpl,IIndexerSemanticSearchServices,winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices,winrt::non_agile>::~root_implements<IndexerSemanticSearchServicesImpl,IIndexerSemanticSearchServices,winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices,winrt::non_agile>(a1 + 8);
      if ( a1[63] )
        operator delete(a1, 0x150u);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x180076a40  mov     [rsp+arg_0], rcx
0x180076a45  push    rbx
0x180076a46  push    rsi
0x180076a47  push    rdi
0x180076a48  push    r12
0x180076a4a  push    r14
0x180076a4c  push    r15
0x180076a4e  sub     rsp, 0C8h
0x180076a55  mov     rsi, [rsp+0F8h+arg_0]
0x180076a5d  lea     r15, [rsi+7Ch]
0x180076a61  movzx   eax, word ptr [r15]
0x180076a65  mov     [rsp+0F8h+var_C8], ax
0x180076a6a  mov     r12d, 1
0x180076a70  add     ax, r12w
0x180076a74  cmp     ax, 6; switch 7 cases
0x180076a78  ja      def_180076A98; jumptable 0000000180076A98 default case, case 1
0x180076a7e  mov     [rsp+0F8h+var_C0], r15
0x180076a83  movsx   rax, ax
0x180076a87  lea     rdx, __ImageBase
0x180076a8e  mov     ecx, ds:(jpt_180076A98 - 180000000h)[rdx+rax*4]
0x180076a95  add     rcx, rdx
0x180076a98  jmp     rcx; switch jump
0x180076a9a  xor     edi, edi; jumptable 0000000180076A98 case 4
0x180076a9c  jmp     loc_180076E20
0x180076aa1  xor     edi, edi; jumptable 0000000180076A98 case 3
0x180076aa3  lea     rbx, [rsi+80h]
0x180076aaa  mov     rcx, rbx
0x180076aad  call    ??$start@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>(void)
0x180076ab2  nop
0x180076ab3  mov     rcx, rbx
0x180076ab6  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::ensure_data(void)
0x180076abb  mov     rbx, [rax]
0x180076abe  lea     r14, [rsi+88h]
0x180076ac5  mov     [r14], rbx
0x180076ac8  test    rbx, rbx
0x180076acb  jz      short loc_180076AD5
0x180076acd  lock add [rbx+120h], r12d
0x180076ad5  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180076adc  call    cs:__imp_EnterCriticalSection
0x180076ae2  add     [rbx+0F0h], r12d
0x180076ae9  mov     dword ptr [rbx+110h], 16h
0x180076af3  mov     rcx, r14
0x180076af6  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180076afb  nop
0x180076afc  lea     rax, qword_1800AF638
0x180076b03  mov     [rsi+108h], rax
0x180076b0a  lock add cs:qword_1800AF638, r12
0x180076b12  mov     rcx, cs:??$factory_cache_entry_v@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@UIQueryBlockListStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@UIQueryBlockListStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::IQueryBlockListStatics>
0x180076b19  test    rcx, rcx
0x180076b1c  jz      short loc_180076B78
0x180076b1e  lea     r14, [rsi+118h]
0x180076b25  mov     [r14], rdi
0x180076b28  lea     rbx, [rsi+120h]
0x180076b2f  mov     [rbx], edi
0x180076b31  mov     [rsi+128h], rdi
0x180076b38  mov     [rsi+130h], rdi
0x180076b3f  mov     rax, [rcx]
0x180076b42  mov     rdx, r14
0x180076b45  mov     rax, [rax+38h]
0x180076b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076b4e  test    eax, eax
0x180076b50  jns     short loc_180076B5C
0x180076b52  mov     rdx, rbx
0x180076b55  mov     ecx, eax
0x180076b57  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180076b5c  lea     rbx, [rsi+90h]
0x180076b63  mov     rax, [r14]
0x180076b66  mov     [rsp+0F8h+var_B8], rax
0x180076b6b  mov     [rbx], rax
0x180076b6e  lock dec cs:qword_1800AF638
0x180076b76  jmp     short loc_180076BA1
0x180076b78  lock dec cs:qword_1800AF638
0x180076b80  lea     r8, [rsi+110h]
0x180076b87  lea     rax, ?_lambda_invoker_cdecl_@_lambda_05cb80ee2c167c13088eab7ae81a7071_@@CA@AEBUITextRecognizerStatics@Vision@Windows@Microsoft@winrt@@@Z; _lambda_05cb80ee2c167c13088eab7ae81a7071_::_lambda_invoker_cdecl_(winrt::Microsoft::Windows::Vision::ITextRecognizerStatics const &)
0x180076b8e  mov     [r8], rax
0x180076b91  lea     rbx, [rsi+90h]
0x180076b98  mov     rdx, rbx
0x180076b9b  call    ??$call@P6A?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@AEBUIQueryBlockListStatics@SemanticSearch@3Microsoft@4@@Z@?$factory_cache_entry@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@UIQueryBlockListStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@2@AEBUIQueryBlockListStatics@SemanticSearch@5Microsoft@2@@Z@Z
0x180076ba0  nop
0x180076ba1  mov     eax, [rsi+70h]
0x180076ba4  nop
0x180076ba5  cmp     eax, 2
0x180076ba8  jnz     short loc_180076BD4
0x180076baa  lea     rcx, [rsi+138h]
0x180076bb1  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180076bb6  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180076bb9  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x180076bbe  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180076bc3  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180076bca  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180076bcf  call    _CxxThrowException_0
0x180076bd4  lea     rcx, [rsi+98h]
0x180076bdb  mov     [rcx], rdi
0x180076bde  mov     [rsi+0A0h], rbx
0x180076be5  mov     [rsi+0A8h], rdi
0x180076bec  mov     [rsi+0B0h], r12b
0x180076bf3  mov     eax, 4
0x180076bf8  mov     [r15], ax
0x180076bfc  mov     rdx, rsi
0x180076bff  call    ??$await_suspend@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@$$V@std@@@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@$$V@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,>::promise_type>)
0x180076c04  test    al, al
0x180076c06  jz      loc_180076C91
0x180076c0c  jmp     loc_180076E65
0x180076c11  mov     rbx, [rsi+98h]; jumptable 0000000180076A98 case 6
0x180076c18  xor     edi, edi
0x180076c1a  test    rbx, rbx
0x180076c1d  jz      short loc_180076C37
0x180076c1f  mov     [rsp+0F8h+var_90], rbx
0x180076c24  jmp     short loc_180076C2C
0x180076c26  call    cs:__imp__Thrd_yield
0x180076c2c  mov     rax, rdi
0x180076c2f  xchg    rax, [rbx]
0x180076c32  cmp     rax, r12
0x180076c35  jz      short loc_180076C26
0x180076c37  lea     rcx, [rsi+90h]
0x180076c3e  mov     rax, [rcx]
0x180076c41  mov     [rsp+0F8h+arg_18], rax
0x180076c49  test    rax, rax
0x180076c4c  jz      short loc_180076C54
0x180076c4e  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180076c53  nop
0x180076c54  mov     rbx, [rsi+80h]
0x180076c5b  mov     [rsp+0F8h+arg_10], rbx
0x180076c63  test    rbx, rbx
0x180076c66  jz      short loc_180076C8A
0x180076c68  or      eax, 0FFFFFFFFh
0x180076c6b  lock xadd [rbx+120h], eax
0x180076c73  cmp     eax, 1
0x180076c76  jnz     short loc_180076C8A
0x180076c78  mov     rcx, rbx
0x180076c7b  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180076c80  mov     rcx, rbx; pv
0x180076c83  call    cs:__imp_CoTaskMemFree
0x180076c89  nop
0x180076c8a  jmp     loc_180076E20
0x180076c8f  xor     edi, edi; jumptable 0000000180076A98 case 5
0x180076c91  lea     r14, [rsi+0B8h]
0x180076c98  lea     rbx, [rsi+98h]
0x180076c9f  mov     rdx, r14
0x180076ca2  mov     rcx, rbx
0x180076ca5  call    ?await_resume@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_resume(void)
0x180076caa  nop
0x180076cab  mov     rbx, [rbx]
0x180076cae  test    rbx, rbx
0x180076cb1  jz      short loc_180076CCB
0x180076cb3  mov     [rsp+0F8h+var_90], rbx
0x180076cb8  jmp     short loc_180076CC0
0x180076cba  call    cs:__imp__Thrd_yield
0x180076cc0  mov     rax, rdi
0x180076cc3  xchg    rax, [rbx]
0x180076cc6  cmp     rax, r12
0x180076cc9  jz      short loc_180076CBA
0x180076ccb  lea     rcx, [rsi+90h]
0x180076cd2  mov     rax, [rcx]
0x180076cd5  mov     [rsp+0F8h+arg_18], rax
0x180076cdd  test    rax, rax
0x180076ce0  jz      short loc_180076CE7
0x180076ce2  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180076ce7  call    ?IsQueryBlockListAvailable@ModelPackageManager@@SA_NXZ; ModelPackageManager::IsQueryBlockListAvailable(void)
0x180076cec  test    al, al
0x180076cee  jnz     short loc_180076D4E
0x180076cf0  mov     rcx, r14; struct winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult *
0x180076cf3  call    ?ThrowIfPackageDeploymentFailed@ModelPackageManager@@CAXAEBUPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@Z; ModelPackageManager::ThrowIfPackageDeploymentFailed(winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult const &)
0x180076cf8  lea     rcx, aAifabricapispe; "AIFabricAPIsPerfTest::reason::QueryBloc"...
0x180076cff  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180076d04  mov     r8, rax
0x180076d07  call    ??$validate_reason@W4reason@_tip_AIFabricAPIsPerfTest@@$04@details@tip2@@YAGXZ; tip2::details::validate_reason<_tip_AIFabricAPIsPerfTest::reason,5>(void)
0x180076d0c  movzx   edx, ax
0x180076d0f  lea     rcx, [rsi+80h]
0x180076d16  call    ?complete_and_fail@?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::complete_and_fail(ushort,char const *)
0x180076d1b  mov     ecx, 8000FFFFh
0x180076d20  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x180076d25  mov     r9d, eax; char *
0x180076d28  mov     rcx, [rsp+0F8h]; this
0x180076d30  lea     rax, aMakeavailablea_2; "MakeAvailableAsync succeeded but query "...
0x180076d37  mov     qword ptr [rsp+0F8h+var_D8], rax; int
0x180076d3c  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\search\\com"...
0x180076d43  mov     edx, 115h; void *
0x180076d48  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180076d4e  mov     rax, [r14]
0x180076d51  mov     [rsp+0F8h+var_B0], rax
0x180076d56  test    rax, rax
0x180076d59  jz      short loc_180076D64
0x180076d5b  mov     rcx, r14
0x180076d5e  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180076d63  nop
0x180076d64  mov     rbx, [rsi+80h]
0x180076d6b  test    rbx, rbx
0x180076d6e  jz      short loc_180076DB5
0x180076d70  mov     [rsp+0F8h+arg_10], rbx
0x180076d78  lea     r14, [rbx+0C8h]
0x180076d7f  mov     rcx, r14; lpCriticalSection
0x180076d82  call    cs:__imp_EnterCriticalSection
0x180076d88  or      dword ptr [rbx+48h], 300h
0x180076d8f  cmp     [rbx+0F8h], rdi
0x180076d96  jz      short loc_180076DA6
0x180076d98  mov     edx, 2
0x180076d9d  lea     rcx, [rbx+8]
0x180076da1  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180076da6  test    r14, r14
0x180076da9  jz      short loc_180076DB5
0x180076dab  mov     rcx, r14; lpCriticalSection
0x180076dae  call    cs:__imp_LeaveCriticalSection
0x180076db4  nop
0x180076db5  mov     rbx, [rsi+80h]
0x180076dbc  mov     [rsp+0F8h+arg_10], rbx
0x180076dc4  test    rbx, rbx
0x180076dc7  jz      short loc_180076DEB
0x180076dc9  or      eax, 0FFFFFFFFh
0x180076dcc  lock xadd [rbx+120h], eax
0x180076dd4  cmp     eax, 1
0x180076dd7  jnz     short loc_180076DEB
0x180076dd9  mov     rcx, rbx
0x180076ddc  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180076de1  mov     rcx, rbx; pv
0x180076de4  call    cs:__imp_CoTaskMemFree
0x180076dea  nop
0x180076deb  jmp     short loc_180076DFC
0x180076ded  xor     edi, edi
0x180076def  mov     rsi, [rsp+0F8h+arg_0]
0x180076df7  mov     r15, [rsp+0F8h+var_C0]
0x180076dfc  lea     rax, [rsi+10h]
0x180076e00  lea     rcx, [rsi+100h]
0x180076e07  mov     [rcx], rax
0x180076e0a  xor     eax, eax
0x180076e0c  mov     [r15], ax
0x180076e10  mov     [rsi], rdi
0x180076e13  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUIndexerSemanticStore@@W4ModelKind@SemanticSearch@Indexer@34@@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticStore &,winrt::Windows::Indexer::SemanticSearch::ModelKind>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x180076e18  test    al, al
0x180076e1a  jz      short loc_180076E20
0x180076e1c  jmp     short loc_180076E65
0x180076e1e  xor     edi, edi; jumptable 0000000180076A98 cases 0,2
0x180076e20  lea     rcx, [rsi+68h]
0x180076e24  cmp     [rcx], rdi
0x180076e27  jz      short loc_180076E2E
0x180076e29  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180076e2e  lea     rcx, [rsi+60h]
0x180076e32  cmp     [rcx], rdi
0x180076e35  jz      short loc_180076E3C
0x180076e37  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180076e3c  lea     rcx, [rsi+48h]
0x180076e40  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180076e46  lea     rcx, [rsi+10h]
0x180076e4a  call    ??1?$root_implements@UIndexerSemanticSearchServicesImpl@@UIIndexerSemanticSearchServices@@UISemanticSearchServices@SemanticSearch@Indexer@Windows@winrt@@Unon_agile@7@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<IndexerSemanticSearchServicesImpl,IIndexerSemanticSearchServices,winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices,winrt::non_agile>::~root_implements<IndexerSemanticSearchServicesImpl,IIndexerSemanticSearchServices,winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices,winrt::non_agile>(void)
0x180076e4f  cmp     [rsi+7Eh], di
0x180076e53  jz      short loc_180076E65
0x180076e55  mov     edx, 150h; unsigned __int64
0x180076e5a  mov     rcx, rsi; void *
0x180076e5d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180076e62  jmp     short loc_180076E65
0x180076e64  int     3; Trap to Debugger
0x180076e65  add     rsp, 0C8h
0x180076e6c  pop     r15
0x180076e6e  pop     r14
0x180076e70  pop     r12
0x180076e72  pop     rdi
0x180076e73  pop     rsi
0x180076e74  pop     rbx
0x180076e75  retn
```
