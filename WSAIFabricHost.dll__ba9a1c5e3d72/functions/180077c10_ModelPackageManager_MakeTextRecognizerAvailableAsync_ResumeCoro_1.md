# ModelPackageManager::MakeTextRecognizerAvailableAsync$_ResumeCoro$1

- ea: `0x180077c10`
- end: `0x180078064`
- name: `ModelPackageManager::MakeTextRecognizerAvailableAsync$_ResumeCoro$1`
- size: `1108`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001c780`
- `0x180077c00`

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
- `0x18002d998`
- `0x18002f8ec`
- `0x1800318c4`
- `0x180031bac`
- `0x18004ba10`
- `0x18004dd6c`
- `0x18004dea8`
- `0x18004eb70`
- `0x18005266c`
- `0x180073ce8`
- `0x1800748b0`
- `0x180075c1c`
- `0x180077c10`
- `0x1800783b8`
- `0x1800785a8`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077f7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077f7e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077cac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077f52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077cac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077f52`
- `msvcp_win!_Thrd_yield` at `0x180077df6`
- `msvcp_win!_Thrd_yield` at `0x180077e8a`
- `msvcp_win!_Thrd_yield` at `0x180077df6`
- `msvcp_win!_Thrd_yield` at `0x180077e8a`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180078010`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180078010`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077e53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077fb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077e53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077fb4`

## string_xrefs

- `0x180077f0c`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\modelpackagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall ModelPackageManager::MakeTextRecognizerAvailableAsync__ResumeCoro_1(_WORD *a1)
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
      *(_DWORD *)(v4 + 272) = 25;
      tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(a1 + 68);
      *((_QWORD *)a1 + 33) = &qword_1800AF898;
      _InterlockedAdd64(&qword_1800AF898, 1u);
      v5 = winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics>;
      if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics> )
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
        _InterlockedDecrement64(&qword_1800AF898);
      }
      else
      {
        _InterlockedDecrement64(&qword_1800AF898);
        *((_QWORD *)a1 + 34) = _lambda_05cb80ee2c167c13088eab7ae81a7071_::_lambda_invoker_cdecl_;
        v7 = a1 + 72;
        winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics>::call<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::Vision::TextRecognizer> (*)(winrt::Microsoft::Windows::Vision::ITextRecognizerStatics const &)>(
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
      if ( !ModelPackageManager::IsTextRecognizerAvailable() )
      {
        ModelPackageManager::ThrowIfPackageDeploymentFailed((const struct winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult *)(a1 + 92));
        v13 = tip2::details::reason_string(
                (tip2::details *)"AIFabricAPIsPerfTest::reason::TextRecognizerNotAvailable",
                v12);
        v16 = tip2::details::validate_reason<enum _tip_AIFabricAPIsPerfTest::reason,3>(v15, v14, v13);
        tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::complete_and_fail(
          a1 + 64,
          v16,
          v17);
        v18 = wil::verify_hresult(2147549183LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0xFB,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\modelpackagemanager.cpp",
          (const char *)v18,
          (int)"MakeAvailableAsync succeeded but text recognizer is still not available",
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
0x180077c10  mov     [rsp+arg_0], rcx
0x180077c15  push    rbx
0x180077c16  push    rsi
0x180077c17  push    rdi
0x180077c18  push    r12
0x180077c1a  push    r14
0x180077c1c  push    r15
0x180077c1e  sub     rsp, 0C8h
0x180077c25  mov     rsi, [rsp+0F8h+arg_0]
0x180077c2d  lea     r15, [rsi+7Ch]
0x180077c31  movzx   eax, word ptr [r15]
0x180077c35  mov     [rsp+0F8h+var_C8], ax
0x180077c3a  mov     r12d, 1
0x180077c40  add     ax, r12w
0x180077c44  cmp     ax, 6; switch 7 cases
0x180077c48  ja      def_180077C68; jumptable 0000000180077C68 default case, case 1
0x180077c4e  mov     [rsp+0F8h+var_C0], r15
0x180077c53  movsx   rax, ax
0x180077c57  lea     rdx, __ImageBase
0x180077c5e  mov     ecx, ds:(jpt_180077C68 - 180000000h)[rdx+rax*4]
0x180077c65  add     rcx, rdx
0x180077c68  jmp     rcx; switch jump
0x180077c6a  xor     edi, edi; jumptable 0000000180077C68 case 4
0x180077c6c  jmp     loc_180077FF0
0x180077c71  xor     edi, edi; jumptable 0000000180077C68 case 3
0x180077c73  lea     rbx, [rsi+80h]
0x180077c7a  mov     rcx, rbx
0x180077c7d  call    ??$start@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>(void)
0x180077c82  nop
0x180077c83  mov     rcx, rbx
0x180077c86  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::ensure_data(void)
0x180077c8b  mov     rbx, [rax]
0x180077c8e  lea     r14, [rsi+88h]
0x180077c95  mov     [r14], rbx
0x180077c98  test    rbx, rbx
0x180077c9b  jz      short loc_180077CA5
0x180077c9d  lock add [rbx+120h], r12d
0x180077ca5  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180077cac  call    cs:__imp_EnterCriticalSection
0x180077cb2  add     [rbx+0F0h], r12d
0x180077cb9  mov     dword ptr [rbx+110h], 19h
0x180077cc3  mov     rcx, r14
0x180077cc6  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180077ccb  nop
0x180077ccc  lea     rax, qword_1800AF898
0x180077cd3  mov     [rsi+108h], rax
0x180077cda  lock add cs:qword_1800AF898, r12
0x180077ce2  mov     rcx, cs:??$factory_cache_entry_v@UTextRecognizer@Vision@Windows@Microsoft@winrt@@UITextRecognizerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UTextRecognizer@Vision@Windows@Microsoft@winrt@@UITextRecognizerStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics>
0x180077ce9  test    rcx, rcx
0x180077cec  jz      short loc_180077D48
0x180077cee  lea     r14, [rsi+118h]
0x180077cf5  mov     [r14], rdi
0x180077cf8  lea     rbx, [rsi+120h]
0x180077cff  mov     [rbx], edi
0x180077d01  mov     [rsi+128h], rdi
0x180077d08  mov     [rsi+130h], rdi
0x180077d0f  mov     rax, [rcx]
0x180077d12  mov     rdx, r14
0x180077d15  mov     rax, [rax+38h]
0x180077d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077d1e  test    eax, eax
0x180077d20  jns     short loc_180077D2C
0x180077d22  mov     rdx, rbx
0x180077d25  mov     ecx, eax
0x180077d27  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180077d2c  lea     rbx, [rsi+90h]
0x180077d33  mov     rax, [r14]
0x180077d36  mov     [rsp+0F8h+var_B8], rax
0x180077d3b  mov     [rbx], rax
0x180077d3e  lock dec cs:qword_1800AF898
0x180077d46  jmp     short loc_180077D71
0x180077d48  lock dec cs:qword_1800AF898
0x180077d50  lea     r8, [rsi+110h]
0x180077d57  lea     rax, ?_lambda_invoker_cdecl_@_lambda_05cb80ee2c167c13088eab7ae81a7071_@@CA@AEBUITextRecognizerStatics@Vision@Windows@Microsoft@winrt@@@Z; _lambda_05cb80ee2c167c13088eab7ae81a7071_::_lambda_invoker_cdecl_(winrt::Microsoft::Windows::Vision::ITextRecognizerStatics const &)
0x180077d5e  mov     [r8], rax
0x180077d61  lea     rbx, [rsi+90h]
0x180077d68  mov     rdx, rbx
0x180077d6b  call    ??$call@P6A?AU?$IAsyncOperation@UTextRecognizer@Vision@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEBUITextRecognizerStatics@Vision@3Microsoft@4@@Z@?$factory_cache_entry@UTextRecognizer@Vision@Windows@Microsoft@winrt@@UITextRecognizerStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AU?$IAsyncOperation@UTextRecognizer@Vision@Windows@Microsoft@winrt@@@Foundation@Windows@2@AEBUITextRecognizerStatics@Vision@5Microsoft@2@@Z@Z
0x180077d70  nop
0x180077d71  mov     eax, [rsi+70h]
0x180077d74  nop
0x180077d75  cmp     eax, 2
0x180077d78  jnz     short loc_180077DA4
0x180077d7a  lea     rcx, [rsi+138h]
0x180077d81  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180077d86  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180077d89  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x180077d8e  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180077d93  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180077d9a  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180077d9f  call    _CxxThrowException_0
0x180077da4  lea     rcx, [rsi+98h]
0x180077dab  mov     [rcx], rdi
0x180077dae  mov     [rsi+0A0h], rbx
0x180077db5  mov     [rsi+0A8h], rdi
0x180077dbc  mov     [rsi+0B0h], r12b
0x180077dc3  mov     eax, 4
0x180077dc8  mov     [r15], ax
0x180077dcc  mov     rdx, rsi
0x180077dcf  call    ??$await_suspend@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@$$V@std@@@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@$$V@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,>::promise_type>)
0x180077dd4  test    al, al
0x180077dd6  jz      loc_180077E61
0x180077ddc  jmp     loc_180078035
0x180077de1  mov     rbx, [rsi+98h]; jumptable 0000000180077C68 case 6
0x180077de8  xor     edi, edi
0x180077dea  test    rbx, rbx
0x180077ded  jz      short loc_180077E07
0x180077def  mov     [rsp+0F8h+var_90], rbx
0x180077df4  jmp     short loc_180077DFC
0x180077df6  call    cs:__imp__Thrd_yield
0x180077dfc  mov     rax, rdi
0x180077dff  xchg    rax, [rbx]
0x180077e02  cmp     rax, r12
0x180077e05  jz      short loc_180077DF6
0x180077e07  lea     rcx, [rsi+90h]
0x180077e0e  mov     rax, [rcx]
0x180077e11  mov     [rsp+0F8h+arg_18], rax
0x180077e19  test    rax, rax
0x180077e1c  jz      short loc_180077E24
0x180077e1e  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180077e23  nop
0x180077e24  mov     rbx, [rsi+80h]
0x180077e2b  mov     [rsp+0F8h+arg_10], rbx
0x180077e33  test    rbx, rbx
0x180077e36  jz      short loc_180077E5A
0x180077e38  or      eax, 0FFFFFFFFh
0x180077e3b  lock xadd [rbx+120h], eax
0x180077e43  cmp     eax, 1
0x180077e46  jnz     short loc_180077E5A
0x180077e48  mov     rcx, rbx
0x180077e4b  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180077e50  mov     rcx, rbx; pv
0x180077e53  call    cs:__imp_CoTaskMemFree
0x180077e59  nop
0x180077e5a  jmp     loc_180077FF0
0x180077e5f  xor     edi, edi; jumptable 0000000180077C68 case 5
0x180077e61  lea     r14, [rsi+0B8h]
0x180077e68  lea     rbx, [rsi+98h]
0x180077e6f  mov     rdx, r14
0x180077e72  mov     rcx, rbx
0x180077e75  call    ?await_resume@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_resume(void)
0x180077e7a  nop
0x180077e7b  mov     rbx, [rbx]
0x180077e7e  test    rbx, rbx
0x180077e81  jz      short loc_180077E9B
0x180077e83  mov     [rsp+0F8h+var_90], rbx
0x180077e88  jmp     short loc_180077E90
0x180077e8a  call    cs:__imp__Thrd_yield
0x180077e90  mov     rax, rdi
0x180077e93  xchg    rax, [rbx]
0x180077e96  cmp     rax, r12
0x180077e99  jz      short loc_180077E8A
0x180077e9b  lea     rcx, [rsi+90h]
0x180077ea2  mov     rax, [rcx]
0x180077ea5  mov     [rsp+0F8h+arg_18], rax
0x180077ead  test    rax, rax
0x180077eb0  jz      short loc_180077EB7
0x180077eb2  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180077eb7  call    ?IsTextRecognizerAvailable@ModelPackageManager@@SA_NXZ; ModelPackageManager::IsTextRecognizerAvailable(void)
0x180077ebc  test    al, al
0x180077ebe  jnz     short loc_180077F1E
0x180077ec0  mov     rcx, r14; struct winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult *
0x180077ec3  call    ?ThrowIfPackageDeploymentFailed@ModelPackageManager@@CAXAEBUPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@Z; ModelPackageManager::ThrowIfPackageDeploymentFailed(winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult const &)
0x180077ec8  lea     rcx, aAifabricapispe_1; "AIFabricAPIsPerfTest::reason::TextRecog"...
0x180077ecf  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180077ed4  mov     r8, rax
0x180077ed7  call    ??$validate_reason@W4reason@_tip_AIFabricAPIsPerfTest@@$02@details@tip2@@YAGXZ; tip2::details::validate_reason<_tip_AIFabricAPIsPerfTest::reason,3>(void)
0x180077edc  movzx   edx, ax
0x180077edf  lea     rcx, [rsi+80h]
0x180077ee6  call    ?complete_and_fail@?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::complete_and_fail(ushort,char const *)
0x180077eeb  mov     ecx, 8000FFFFh
0x180077ef0  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x180077ef5  mov     r9d, eax; char *
0x180077ef8  mov     rcx, [rsp+0F8h]; this
0x180077f00  lea     rax, aMakeavailablea_0; "MakeAvailableAsync succeeded but text r"...
0x180077f07  mov     qword ptr [rsp+0F8h+var_D8], rax; int
0x180077f0c  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\search\\com"...
0x180077f13  mov     edx, 0FBh; void *
0x180077f18  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180077f1e  mov     rax, [r14]
0x180077f21  mov     [rsp+0F8h+var_B0], rax
0x180077f26  test    rax, rax
0x180077f29  jz      short loc_180077F34
0x180077f2b  mov     rcx, r14
0x180077f2e  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180077f33  nop
0x180077f34  mov     rbx, [rsi+80h]
0x180077f3b  test    rbx, rbx
0x180077f3e  jz      short loc_180077F85
0x180077f40  mov     [rsp+0F8h+arg_10], rbx
0x180077f48  lea     r14, [rbx+0C8h]
0x180077f4f  mov     rcx, r14; lpCriticalSection
0x180077f52  call    cs:__imp_EnterCriticalSection
0x180077f58  or      dword ptr [rbx+48h], 300h
0x180077f5f  cmp     [rbx+0F8h], rdi
0x180077f66  jz      short loc_180077F76
0x180077f68  mov     edx, 2
0x180077f6d  lea     rcx, [rbx+8]
0x180077f71  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180077f76  test    r14, r14
0x180077f79  jz      short loc_180077F85
0x180077f7b  mov     rcx, r14; lpCriticalSection
0x180077f7e  call    cs:__imp_LeaveCriticalSection
0x180077f84  nop
0x180077f85  mov     rbx, [rsi+80h]
0x180077f8c  mov     [rsp+0F8h+arg_10], rbx
0x180077f94  test    rbx, rbx
0x180077f97  jz      short loc_180077FBB
0x180077f99  or      eax, 0FFFFFFFFh
0x180077f9c  lock xadd [rbx+120h], eax
0x180077fa4  cmp     eax, 1
0x180077fa7  jnz     short loc_180077FBB
0x180077fa9  mov     rcx, rbx
0x180077fac  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180077fb1  mov     rcx, rbx; pv
0x180077fb4  call    cs:__imp_CoTaskMemFree
0x180077fba  nop
0x180077fbb  jmp     short loc_180077FCC
0x180077fbd  xor     edi, edi
0x180077fbf  mov     rsi, [rsp+0F8h+arg_0]
0x180077fc7  mov     r15, [rsp+0F8h+var_C0]
0x180077fcc  lea     rax, [rsi+10h]
0x180077fd0  lea     rcx, [rsi+100h]
0x180077fd7  mov     [rcx], rax
0x180077fda  xor     eax, eax
0x180077fdc  mov     [r15], ax
0x180077fe0  mov     [rsi], rdi
0x180077fe3  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUIndexerSemanticStore@@W4ModelKind@SemanticSearch@Indexer@34@@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticStore &,winrt::Windows::Indexer::SemanticSearch::ModelKind>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x180077fe8  test    al, al
0x180077fea  jz      short loc_180077FF0
0x180077fec  jmp     short loc_180078035
0x180077fee  xor     edi, edi; jumptable 0000000180077C68 cases 0,2
0x180077ff0  lea     rcx, [rsi+68h]
0x180077ff4  cmp     [rcx], rdi
0x180077ff7  jz      short loc_180077FFE
0x180077ff9  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180077ffe  lea     rcx, [rsi+60h]
0x180078002  cmp     [rcx], rdi
0x180078005  jz      short loc_18007800C
0x180078007  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18007800c  lea     rcx, [rsi+48h]
0x180078010  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180078016  lea     rcx, [rsi+10h]
0x18007801a  call    ??1?$root_implements@UIndexerSemanticSearchServicesImpl@@UIIndexerSemanticSearchServices@@UISemanticSearchServices@SemanticSearch@Indexer@Windows@winrt@@Unon_agile@7@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<IndexerSemanticSearchServicesImpl,IIndexerSemanticSearchServices,winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices,winrt::non_agile>::~root_implements<IndexerSemanticSearchServicesImpl,IIndexerSemanticSearchServices,winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices,winrt::non_agile>(void)
0x18007801f  cmp     [rsi+7Eh], di
0x180078023  jz      short loc_180078035
0x180078025  mov     edx, 150h; unsigned __int64
0x18007802a  mov     rcx, rsi; void *
0x18007802d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180078032  jmp     short loc_180078035
0x180078034  int     3; Trap to Debugger
0x180078035  add     rsp, 0C8h
0x18007803c  pop     r15
0x18007803e  pop     r14
0x180078040  pop     r12
0x180078042  pop     rdi
0x180078043  pop     rsi
0x180078044  pop     rbx
0x180078045  retn
```
