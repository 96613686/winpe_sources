# ModelPackageManager::MakeDefaultSemanticTextSearchModelsAvailableAsync$_ResumeCoro$1

- ea: `0x1800765d0`
- end: `0x180076a28`
- name: `ModelPackageManager::MakeDefaultSemanticTextSearchModelsAvailableAsync$_ResumeCoro$1`
- size: `1112`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001bde0`
- `0x1800765c0`

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
- `0x18002d874`
- `0x18002f8ec`
- `0x1800318c4`
- `0x180031bac`
- `0x18004ba10`
- `0x18004dd6c`
- `0x18004dea8`
- `0x18004eb70`
- `0x18005266c`
- `0x180073ce8`
- `0x1800748a4`
- `0x180074cb0`
- `0x1800765d0`
- `0x1800783b8`
- `0x1800785a8`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076929`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180076929`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007666d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800768fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007666d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800768fd`
- `msvcp_win!_Thrd_yield` at `0x1800767b8`
- `msvcp_win!_Thrd_yield` at `0x18007684c`
- `msvcp_win!_Thrd_yield` at `0x1800767b8`
- `msvcp_win!_Thrd_yield` at `0x18007684c`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800769d2`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800769d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076815`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076975`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076815`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076975`

## string_xrefs

- `0x1800768ce`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\modelpackagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall ModelPackageManager::MakeDefaultSemanticTextSearchModelsAvailableAsync__ResumeCoro_1(_WORD *a1)
{
  _WORD *v2; // r12
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
      *(_DWORD *)(v4 + 272) = 37;
      tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(a1 + 68);
      *((_QWORD *)a1 + 33) = &qword_1800AF6D8;
      _InterlockedAdd64(&qword_1800AF6D8, 1u);
      v5 = winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>;
      if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics> )
      {
        *((_QWORD *)a1 + 35) = 0;
        *((_DWORD *)a1 + 72) = 0;
        *((_QWORD *)a1 + 37) = 0;
        *((_QWORD *)a1 + 38) = 0;
        v6 = (*(__int64 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v5 + 80LL))(v5, a1 + 140);
        if ( v6 < 0 )
          winrt::throw_hresult((unsigned int)v6, a1 + 144);
        v7 = a1 + 72;
        *((_QWORD *)a1 + 18) = *((_QWORD *)a1 + 35);
        _InterlockedDecrement64(&qword_1800AF6D8);
      }
      else
      {
        _InterlockedDecrement64(&qword_1800AF6D8);
        *((_QWORD *)a1 + 34) = _lambda_42c5ad22edcc3d8e44a36b4fb3cdc9f0_::_lambda_invoker_cdecl_;
        v7 = a1 + 72;
        winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>::call<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> (*)(winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics const &)>(
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
      if ( !ModelPackageManager::AreDefaultTextSearchModelsAvailable() )
      {
        ModelPackageManager::ThrowIfPackageDeploymentFailed((const struct winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult *)(a1 + 92));
        v13 = tip2::details::reason_string(
                (tip2::details *)"AIFabricAPIsPerfTest::reason::PolarisSearchModelsAreNotAvailable",
                v12);
        v16 = tip2::details::validate_reason<enum _tip_AIFabricAPIsPerfTest::reason,2>(v15, v14, v13);
        tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::complete_and_fail(
          a1 + 64,
          v16,
          v17);
        v18 = wil::verify_hresult(2147549183LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0xE1,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\modelpackagemanager.cpp",
          (const char *)v18,
          (int)"MakeAvailableAsync succeeded but models are still not available",
          v21);
      }
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
      if ( *((_QWORD *)a1 + 23) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 92);
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
0x1800765d0  mov     [rsp+arg_0], rcx
0x1800765d5  push    rbx
0x1800765d6  push    rsi
0x1800765d7  push    rdi
0x1800765d8  push    r12
0x1800765da  push    r14
0x1800765dc  push    r15
0x1800765de  sub     rsp, 0C8h
0x1800765e5  mov     rsi, [rsp+0F8h+arg_0]
0x1800765ed  lea     r12, [rsi+7Ch]
0x1800765f1  movzx   eax, word ptr [r12]
0x1800765f6  mov     [rsp+0F8h+var_C8], ax
0x1800765fb  mov     r15d, 1
0x180076601  add     ax, r15w
0x180076605  cmp     ax, 6; switch 7 cases
0x180076609  ja      def_180076629; jumptable 0000000180076629 default case, case 1
0x18007660f  mov     [rsp+0F8h+var_C0], r12
0x180076614  movsx   rax, ax
0x180076618  lea     rdx, __ImageBase
0x18007661f  mov     ecx, ds:(jpt_180076629 - 180000000h)[rdx+rax*4]
0x180076626  add     rcx, rdx
0x180076629  jmp     rcx; switch jump
0x18007662b  xor     edi, edi; jumptable 0000000180076629 case 4
0x18007662d  jmp     loc_1800769B2
0x180076632  xor     edi, edi; jumptable 0000000180076629 case 3
0x180076634  lea     rbx, [rsi+80h]
0x18007663b  mov     rcx, rbx
0x18007663e  call    ??$start@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>(void)
0x180076643  nop
0x180076644  mov     rcx, rbx
0x180076647  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::ensure_data(void)
0x18007664c  mov     rbx, [rax]
0x18007664f  lea     r14, [rsi+88h]
0x180076656  mov     [r14], rbx
0x180076659  test    rbx, rbx
0x18007665c  jz      short loc_180076666
0x18007665e  lock add [rbx+120h], r15d
0x180076666  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18007666d  call    cs:__imp_EnterCriticalSection
0x180076673  add     [rbx+0F0h], r15d
0x18007667a  mov     dword ptr [rbx+110h], 25h ; '%'
0x180076684  mov     rcx, r14
0x180076687  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x18007668c  nop
0x18007668d  lea     rax, qword_1800AF6D8
0x180076694  mov     [rsi+108h], rax
0x18007669b  lock add cs:qword_1800AF6D8, r15
0x1800766a3  mov     rcx, cs:??$factory_cache_entry_v@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticTextIndexStoreStatics@2345@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticTextIndexStoreStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>
0x1800766aa  test    rcx, rcx
0x1800766ad  jz      short loc_180076709
0x1800766af  lea     r14, [rsi+118h]
0x1800766b6  mov     [r14], rdi
0x1800766b9  lea     rbx, [rsi+120h]
0x1800766c0  mov     [rbx], edi
0x1800766c2  mov     [rsi+128h], rdi
0x1800766c9  mov     [rsi+130h], rdi
0x1800766d0  mov     rax, [rcx]
0x1800766d3  mov     rdx, r14
0x1800766d6  mov     rax, [rax+50h]
0x1800766da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800766df  test    eax, eax
0x1800766e1  jns     short loc_1800766ED
0x1800766e3  mov     rdx, rbx
0x1800766e6  mov     ecx, eax
0x1800766e8  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800766ed  lea     rbx, [rsi+90h]
0x1800766f4  mov     rax, [r14]
0x1800766f7  mov     [rsp+0F8h+var_B8], rax
0x1800766fc  mov     [rbx], rax
0x1800766ff  lock dec cs:qword_1800AF6D8
0x180076707  jmp     short loc_180076732
0x180076709  lock dec cs:qword_1800AF6D8
0x180076711  lea     r8, [rsi+110h]
0x180076718  lea     rax, ?_lambda_invoker_cdecl_@_lambda_42c5ad22edcc3d8e44a36b4fb3cdc9f0_@@CA@AEBUISemanticImageIndexStoreStatics@SemanticSearch@Windows@Microsoft@winrt@@@Z; _lambda_42c5ad22edcc3d8e44a36b4fb3cdc9f0_::_lambda_invoker_cdecl_(winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics const &)
0x18007671f  mov     [r8], rax
0x180076722  lea     rbx, [rsi+90h]
0x180076729  mov     rdx, rbx
0x18007672c  call    ??$call@P6A?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@AEBUISemanticTextIndexStoreStatics@SemanticSearch@3Microsoft@4@@Z@?$factory_cache_entry@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticTextIndexStoreStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@2@AEBUISemanticTextIndexStoreStatics@SemanticSearch@5Microsoft@2@@Z@Z
0x180076731  nop
0x180076732  mov     eax, [rsi+70h]
0x180076735  nop
0x180076736  cmp     eax, 2
0x180076739  jnz     short loc_180076765
0x18007673b  lea     rcx, [rsi+138h]
0x180076742  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180076747  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18007674a  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x18007674f  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180076754  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18007675b  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180076760  call    _CxxThrowException_0
0x180076765  lea     rcx, [rsi+98h]
0x18007676c  mov     [rcx], rdi
0x18007676f  mov     [rsi+0A0h], rbx
0x180076776  mov     [rsi+0A8h], rdi
0x18007677d  mov     [rsi+0B0h], r15b
0x180076784  mov     eax, 4
0x180076789  mov     [r12], ax
0x18007678e  mov     rdx, rsi
0x180076791  call    ??$await_suspend@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@$$V@std@@@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@$$V@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,>::promise_type>)
0x180076796  test    al, al
0x180076798  jz      loc_180076823
0x18007679e  jmp     loc_1800769F7
0x1800767a3  mov     rbx, [rsi+98h]; jumptable 0000000180076629 case 6
0x1800767aa  xor     edi, edi
0x1800767ac  test    rbx, rbx
0x1800767af  jz      short loc_1800767C9
0x1800767b1  mov     [rsp+0F8h+var_90], rbx
0x1800767b6  jmp     short loc_1800767BE
0x1800767b8  call    cs:__imp__Thrd_yield
0x1800767be  mov     rax, rdi
0x1800767c1  xchg    rax, [rbx]
0x1800767c4  cmp     rax, r15
0x1800767c7  jz      short loc_1800767B8
0x1800767c9  lea     rcx, [rsi+90h]
0x1800767d0  mov     rax, [rcx]
0x1800767d3  mov     [rsp+0F8h+arg_18], rax
0x1800767db  test    rax, rax
0x1800767de  jz      short loc_1800767E6
0x1800767e0  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x1800767e5  nop
0x1800767e6  mov     rbx, [rsi+80h]
0x1800767ed  mov     [rsp+0F8h+arg_10], rbx
0x1800767f5  test    rbx, rbx
0x1800767f8  jz      short loc_18007681C
0x1800767fa  or      eax, 0FFFFFFFFh
0x1800767fd  lock xadd [rbx+120h], eax
0x180076805  cmp     eax, 1
0x180076808  jnz     short loc_18007681C
0x18007680a  mov     rcx, rbx
0x18007680d  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180076812  mov     rcx, rbx; pv
0x180076815  call    cs:__imp_CoTaskMemFree
0x18007681b  nop
0x18007681c  jmp     loc_1800769B2
0x180076821  xor     edi, edi; jumptable 0000000180076629 case 5
0x180076823  lea     r14, [rsi+0B8h]
0x18007682a  lea     rbx, [rsi+98h]
0x180076831  mov     rdx, r14
0x180076834  mov     rcx, rbx
0x180076837  call    ?await_resume@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_resume(void)
0x18007683c  nop
0x18007683d  mov     rbx, [rbx]
0x180076840  test    rbx, rbx
0x180076843  jz      short loc_18007685D
0x180076845  mov     [rsp+0F8h+var_90], rbx
0x18007684a  jmp     short loc_180076852
0x18007684c  call    cs:__imp__Thrd_yield
0x180076852  mov     rax, rdi
0x180076855  xchg    rax, [rbx]
0x180076858  cmp     rax, r15
0x18007685b  jz      short loc_18007684C
0x18007685d  lea     rcx, [rsi+90h]
0x180076864  mov     rax, [rcx]
0x180076867  mov     [rsp+0F8h+arg_18], rax
0x18007686f  test    rax, rax
0x180076872  jz      short loc_180076879
0x180076874  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180076879  call    ?AreDefaultTextSearchModelsAvailable@ModelPackageManager@@SA_NXZ; ModelPackageManager::AreDefaultTextSearchModelsAvailable(void)
0x18007687e  test    al, al
0x180076880  jnz     short loc_1800768DF
0x180076882  mov     rcx, r14; struct winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult *
0x180076885  call    ?ThrowIfPackageDeploymentFailed@ModelPackageManager@@CAXAEBUPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@Z; ModelPackageManager::ThrowIfPackageDeploymentFailed(winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult const &)
0x18007688a  lea     rcx, aAifabricapispe_2; "AIFabricAPIsPerfTest::reason::PolarisSe"...
0x180076891  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180076896  mov     r8, rax
0x180076899  call    ??$validate_reason@W4reason@_tip_AIFabricAPIsPerfTest@@$01@details@tip2@@YAGXZ; tip2::details::validate_reason<_tip_AIFabricAPIsPerfTest::reason,2>(void)
0x18007689e  movzx   edx, ax
0x1800768a1  lea     rcx, [rsi+80h]
0x1800768a8  call    ?complete_and_fail@?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::complete_and_fail(ushort,char const *)
0x1800768ad  mov     ecx, 8000FFFFh
0x1800768b2  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x1800768b7  mov     r9d, eax; char *
0x1800768ba  mov     rcx, [rsp+0F8h]; this
0x1800768c2  lea     rax, aMakeavailablea_1; "MakeAvailableAsync succeeded but models"...
0x1800768c9  mov     qword ptr [rsp+0F8h+var_D8], rax; int
0x1800768ce  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800768d5  mov     edx, 0E1h; void *
0x1800768da  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800768df  mov     rbx, [rsi+80h]
0x1800768e6  test    rbx, rbx
0x1800768e9  jz      short loc_180076930
0x1800768eb  mov     [rsp+0F8h+arg_10], rbx
0x1800768f3  lea     r15, [rbx+0C8h]
0x1800768fa  mov     rcx, r15; lpCriticalSection
0x1800768fd  call    cs:__imp_EnterCriticalSection
0x180076903  or      dword ptr [rbx+48h], 300h
0x18007690a  cmp     [rbx+0F8h], rdi
0x180076911  jz      short loc_180076921
0x180076913  mov     edx, 2
0x180076918  lea     rcx, [rbx+8]
0x18007691c  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180076921  test    r15, r15
0x180076924  jz      short loc_180076930
0x180076926  mov     rcx, r15; lpCriticalSection
0x180076929  call    cs:__imp_LeaveCriticalSection
0x18007692f  nop
0x180076930  mov     rax, [r14]
0x180076933  mov     [rsp+0F8h+var_B0], rax
0x180076938  test    rax, rax
0x18007693b  jz      short loc_180076946
0x18007693d  mov     rcx, r14
0x180076940  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180076945  nop
0x180076946  mov     rbx, [rsi+80h]
0x18007694d  mov     [rsp+0F8h+arg_10], rbx
0x180076955  test    rbx, rbx
0x180076958  jz      short loc_18007697C
0x18007695a  or      eax, 0FFFFFFFFh
0x18007695d  lock xadd [rbx+120h], eax
0x180076965  cmp     eax, 1
0x180076968  jnz     short loc_18007697C
0x18007696a  mov     rcx, rbx
0x18007696d  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180076972  mov     rcx, rbx; pv
0x180076975  call    cs:__imp_CoTaskMemFree
0x18007697b  nop
0x18007697c  jmp     short loc_18007698D
0x18007697e  xor     edi, edi
0x180076980  mov     rsi, [rsp+0F8h+arg_0]
0x180076988  mov     r12, [rsp+0F8h+var_C0]
0x18007698d  lea     rax, [rsi+10h]
0x180076991  lea     rcx, [rsi+100h]
0x180076998  mov     [rcx], rax
0x18007699b  xor     eax, eax
0x18007699d  mov     [r12], ax
0x1800769a2  mov     [rsi], rdi
0x1800769a5  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUIndexerSemanticStore@@W4ModelKind@SemanticSearch@Indexer@34@@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticStore &,winrt::Windows::Indexer::SemanticSearch::ModelKind>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x1800769aa  test    al, al
0x1800769ac  jz      short loc_1800769B2
0x1800769ae  jmp     short loc_1800769F7
0x1800769b0  xor     edi, edi; jumptable 0000000180076629 cases 0,2
0x1800769b2  lea     rcx, [rsi+68h]
0x1800769b6  cmp     [rcx], rdi
0x1800769b9  jz      short loc_1800769C0
0x1800769bb  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x1800769c0  lea     rcx, [rsi+60h]
0x1800769c4  cmp     [rcx], rdi
0x1800769c7  jz      short loc_1800769CE
0x1800769c9  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x1800769ce  lea     rcx, [rsi+48h]
0x1800769d2  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800769d8  lea     rcx, [rsi+10h]
0x1800769dc  call    ??1?$root_implements@UIndexerSemanticSearchServicesImpl@@UIIndexerSemanticSearchServices@@UISemanticSearchServices@SemanticSearch@Indexer@Windows@winrt@@Unon_agile@7@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<IndexerSemanticSearchServicesImpl,IIndexerSemanticSearchServices,winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices,winrt::non_agile>::~root_implements<IndexerSemanticSearchServicesImpl,IIndexerSemanticSearchServices,winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices,winrt::non_agile>(void)
0x1800769e1  cmp     [rsi+7Eh], di
0x1800769e5  jz      short loc_1800769F7
0x1800769e7  mov     edx, 150h; unsigned __int64
0x1800769ec  mov     rcx, rsi; void *
0x1800769ef  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800769f4  jmp     short loc_1800769F7
0x1800769f6  int     3; Trap to Debugger
0x1800769f7  add     rsp, 0C8h
0x1800769fe  pop     r15
0x180076a00  pop     r14
0x180076a02  pop     r12
0x180076a04  pop     rdi
0x180076a05  pop     rsi
0x180076a06  pop     rbx
0x180076a07  retn
```
