# ModelPackageManager::MakeSemanticTextSearchModelsAvailableAsync$_ResumeCoro$1

- ea: `0x180077570`
- end: `0x180077af0`
- name: `ModelPackageManager::MakeSemanticTextSearchModelsAvailableAsync$_ResumeCoro$1`
- size: `1408`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180077550`
- `0x180077af8`

## callees

- `0x180005140`
- `0x1800058cb`
- `0x18000591f`
- `0x180007f72`
- `0x180008f84`
- `0x18000c478`
- `0x180014688`
- `0x180018fa0`
- `0x180019c3c`
- `0x18001a420`
- `0x18001de54`
- `0x18002f8ec`
- `0x1800318c4`
- `0x180031bac`
- `0x18003d008`
- `0x18004ba10`
- `0x18004dd6c`
- `0x18004dea8`
- `0x18004eb70`
- `0x18005266c`
- `0x180073ce8`
- `0x180073d20`
- `0x1800748a4`
- `0x180075068`
- `0x180077570`
- `0x1800783b8`
- `0x1800785a8`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180077a98`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180077a98`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007799f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007799f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077689`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077972`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077689`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077972`
- `msvcp_win!_Thrd_yield` at `0x1800777eb`
- `msvcp_win!_Thrd_yield` at `0x1800778a0`
- `msvcp_win!_Thrd_yield` at `0x1800777eb`
- `msvcp_win!_Thrd_yield` at `0x1800778a0`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180077a59`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180077a59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077848`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800779d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077848`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800779d4`

## string_xrefs

- `0x180077617`: `onecoreuap\base\appmodel\Search\common\AIFabricHostHelper\include\Utils.h`
- `0x18007792c`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\modelpackagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall ModelPackageManager::MakeSemanticTextSearchModelsAvailableAsync__ResumeCoro_1(_WORD *a1)
{
  _WORD *v2; // r12
  _WORD *v3; // r14
  int v4; // ecx
  int v5; // ecx
  const char *v6; // r9
  __int64 v7; // r8
  _QWORD *v8; // r15
  __int64 *v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rcx
  int v12; // eax
  _WORD *v13; // r14
  const struct winrt::impl::slim_source_location *v14; // rax
  volatile __int64 *v15; // rbx
  struct _RTL_CRITICAL_SECTION *v16; // r14
  volatile __int64 *v17; // r14
  const char *v18; // rdx
  const char *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned __int16 v22; // ax
  __int64 v23; // r8
  unsigned int v24; // eax
  __int64 v25; // r14
  struct _RTL_CRITICAL_SECTION *v26; // r14
  volatile signed __int32 *v27; // r14
  int v28; // ebx
  HANDLE ProcessHeap; // rax
  const char *v30; // [rsp+28h] [rbp-E0h]
  _BYTE pExceptionObject[24]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+70h] [rbp-98h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v2 = a1 + 72;
  switch ( a1[72] )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_53;
    case 2:
      v3 = a1 + 64;
      v4 = *((_DWORD *)a1 + 34);
      if ( v4 )
      {
        v5 = v4 - 1;
        if ( v5 )
        {
          if ( v5 != 1 )
          {
            v6 = (const char *)(unsigned int)wil::verify_hresult(2147549183LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x20,
              (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\AIFabricHostHelper\\include\\Utils.h",
              v6,
              (int)"Unexpected disposition.",
              v30);
          }
          v7 = 2;
        }
        else
        {
          v7 = 1;
        }
      }
      else
      {
        v7 = 0;
      }
      v8 = a1 + 76;
      Utils::GetSemanticTextIndexStoreOptions(a1 + 76, a1 + 64, v7);
      tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>(a1 + 80);
      v9 = (__int64 *)tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::ensure_data(a1 + 80);
      v10 = *v9;
      *((_QWORD *)a1 + 21) = *v9;
      if ( v10 )
        _InterlockedIncrement((volatile signed __int32 *)(v10 + 288));
      *((_QWORD *)a1 + 46) = v3;
      EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 200));
      ++*(_DWORD *)(v10 + 240);
      *(_DWORD *)(v10 + 272) = 18;
      tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(a1 + 84);
      *((_QWORD *)a1 + 37) = v8;
      *((_QWORD *)a1 + 38) = &qword_1800AF6D8;
      _InterlockedAdd64(&qword_1800AF6D8, 1u);
      v11 = winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>;
      if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics> )
      {
        *((_QWORD *)a1 + 42) = 0;
        *((_DWORD *)a1 + 86) = 0;
        *((_QWORD *)a1 + 44) = 0;
        *((_QWORD *)a1 + 45) = 0;
        v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, _WORD *))(*(_QWORD *)v11 + 56LL))(v11, *v8, a1 + 168);
        if ( v12 < 0 )
          winrt::throw_hresult((unsigned int)v12, a1 + 172);
        v13 = a1 + 88;
        *((_QWORD *)a1 + 22) = *((_QWORD *)a1 + 42);
        _InterlockedAdd64(&qword_1800AF6D8, 0xFFFFFFFFFFFFFFFFuLL);
      }
      else
      {
        _InterlockedAdd64(&qword_1800AF6D8, 0xFFFFFFFFFFFFFFFFuLL);
        v13 = a1 + 88;
        winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>::call<_lambda_27cdfc14008dc8e0d07cbd9d97e1b928_ &>(
          0,
          (_QWORD *)a1 + 22,
          (_QWORD **)a1 + 37);
      }
      if ( *((_DWORD *)a1 + 28) == 2 )
      {
        v14 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 156);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject, v14);
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *((_QWORD *)a1 + 23) = 0;
      *((_QWORD *)a1 + 24) = v13;
      *((_QWORD *)a1 + 25) = 0;
      *((_BYTE *)a1 + 208) = 1;
      *v2 = 4;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,>::promise_type>(
                              a1 + 92,
                              a1) )
        return;
      goto LABEL_32;
    case 4:
LABEL_32:
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_resume(
        a1 + 92,
        a1 + 108);
      v17 = (volatile __int64 *)*((_QWORD *)a1 + 23);
      if ( v17 )
      {
        v32 = *((_QWORD *)a1 + 23);
        while ( _InterlockedExchange64(v17, 0) == 1 )
          _Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 22) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 88);
      if ( !(unsigned __int8)ModelPackageManager::AreSemanticTextSearchModelsAvailable(
                               *((_QWORD *)a1 + 46),
                               *((unsigned int *)a1 + 34)) )
      {
        ModelPackageManager::ThrowIfPackageDeploymentFailed((const struct winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult *)(a1 + 108));
        v19 = tip2::details::reason_string(
                (tip2::details *)"AIFabricAPIsPerfTest::reason::PolarisSearchModelsAreNotAvailable",
                v18);
        v22 = tip2::details::validate_reason<enum _tip_AIFabricAPIsPerfTest::reason,2>(v21, v20, v19);
        tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::complete_and_fail(
          a1 + 80,
          v22,
          v23);
        v24 = wil::verify_hresult(2147549183LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x63,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\modelpackagemanager.cpp",
          (const char *)v24,
          (int)"MakeAvailableAsync succeeded but models are still not available",
          v30);
      }
      if ( *((_QWORD *)a1 + 27) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 108);
      v25 = *((_QWORD *)a1 + 20);
      if ( v25 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(v25 + 200));
        *(_DWORD *)(v25 + 72) |= 0x300u;
        if ( *(_QWORD *)(v25 + 248) )
          tip2::details::shared_data<0,0,0>::complete_helper(v25 + 8, 2);
        if ( v25 != -200 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v25 + 200));
      }
      v26 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)a1 + 20);
      if ( v26 && _InterlockedExchangeAdd(&v26[7].LockCount, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v26);
        CoTaskMemFree(v26);
      }
      if ( *((_QWORD *)a1 + 19) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 76);
      *((_QWORD *)a1 + 36) = a1 + 8;
      *v2 = 0;
      *(_QWORD *)a1 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticStore &,enum winrt::Windows::Indexer::SemanticSearch::ModelKind>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend() )
        goto LABEL_53;
      return;
    case 5:
      v15 = (volatile __int64 *)*((_QWORD *)a1 + 23);
      if ( v15 )
      {
        v32 = *((_QWORD *)a1 + 23);
        while ( _InterlockedExchange64(v15, 0) == 1 )
          _Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 22) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 88);
      v16 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)a1 + 20);
      if ( v16 && _InterlockedExchangeAdd(&v16[7].LockCount, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v16);
        CoTaskMemFree(v16);
      }
      if ( *((_QWORD *)a1 + 19) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 76);
LABEL_53:
      if ( *((_QWORD *)a1 + 13) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 52);
      if ( *((_QWORD *)a1 + 12) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 48);
      __ExceptionPtrDestroy(a1 + 36);
      winrt::impl::root_implements<IndexerSemanticSearchServicesImpl,IIndexerSemanticSearchServices,winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices,winrt::non_agile>::~root_implements<IndexerSemanticSearchServicesImpl,IIndexerSemanticSearchServices,winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices,winrt::non_agile>(a1 + 8);
      v27 = (volatile signed __int32 *)*((_QWORD *)a1 + 16);
      if ( v27 )
      {
        v28 = _InterlockedDecrement(v27 + 6);
        if ( v28 )
        {
          if ( v28 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v27);
        }
        *((_QWORD *)a1 + 16) = 0;
      }
      if ( a1[73] )
        operator delete(a1, 0x180u);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x180077570  mov     [rsp+arg_0], rcx
0x180077575  push    rbx
0x180077576  push    rsi
0x180077577  push    rdi
0x180077578  push    r12
0x18007757a  push    r13
0x18007757c  push    r14
0x18007757e  push    r15
0x180077580  sub     rsp, 0D0h
0x180077587  mov     rsi, [rsp+108h+arg_0]
0x18007758f  lea     r12, [rsi+90h]
0x180077596  movzx   eax, word ptr [r12]
0x18007759b  mov     [rsp+108h+var_D8], ax
0x1800775a0  mov     r13d, 1
0x1800775a6  add     ax, r13w
0x1800775aa  cmp     ax, 6; switch 7 cases
0x1800775ae  ja      def_1800775CE; jumptable 00000001800775CE default case, case 1
0x1800775b4  mov     [rsp+108h+var_C8], r12
0x1800775b9  movsx   rax, ax
0x1800775bd  lea     rdx, __ImageBase
0x1800775c4  mov     ecx, ds:(jpt_1800775CE - 180000000h)[rdx+rax*4]
0x1800775cb  add     rcx, rdx
0x1800775ce  jmp     rcx; switch jump
0x1800775d0  xor     edi, edi; jumptable 00000001800775CE case 4
0x1800775d2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800775d6  jmp     loc_180077A39
0x1800775db  xor     edi, edi; jumptable 00000001800775CE case 3
0x1800775dd  lea     r14, [rsi+80h]
0x1800775e4  mov     ecx, [r14+8]
0x1800775e8  test    ecx, ecx
0x1800775ea  jz      short loc_180077633
0x1800775ec  sub     ecx, 1
0x1800775ef  jz      short loc_18007762E
0x1800775f1  cmp     ecx, 1
0x1800775f4  jz      short loc_180077626
0x1800775f6  mov     ecx, 8000FFFFh
0x1800775fb  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x180077600  mov     r9d, eax; char *
0x180077603  mov     rcx, [rsp+108h]; this
0x18007760b  lea     rax, aUnexpectedDisp; "Unexpected disposition."
0x180077612  mov     qword ptr [rsp+108h+var_E8], rax; int
0x180077617  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18007761e  lea     edx, [rdi+20h]; void *
0x180077621  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180077626  mov     r8d, 2
0x18007762c  jmp     short loc_180077636
0x18007762e  mov     r8d, r13d
0x180077631  jmp     short loc_180077636
0x180077633  mov     r8d, edi
0x180077636  lea     r15, [rsi+98h]
0x18007763d  mov     rdx, r14
0x180077640  mov     rcx, r15
0x180077643  call    ?GetSemanticTextIndexStoreOptions@Utils@@YA?AUSemanticTextIndexStoreOptions@SemanticSearch@Windows@Microsoft@winrt@@AEBUhstring@6@W4IndexCreationDisposition@3456@@Z; Utils::GetSemanticTextIndexStoreOptions(winrt::hstring const &,winrt::Microsoft::Windows::SemanticSearch::IndexCreationDisposition)
0x180077648  nop
0x180077649  lea     rbx, [rsi+0A0h]
0x180077650  mov     rcx, rbx
0x180077653  call    ??$start@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>(void)
0x180077658  nop
0x180077659  mov     rcx, rbx
0x18007765c  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::ensure_data(void)
0x180077661  mov     rbx, [rax]
0x180077664  lea     r13, [rsi+0A8h]
0x18007766b  mov     [r13+0], rbx
0x18007766f  test    rbx, rbx
0x180077672  jz      short loc_18007767B
0x180077674  lock inc dword ptr [rbx+120h]
0x18007767b  mov     [rsi+170h], r14
0x180077682  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180077689  call    cs:__imp_EnterCriticalSection
0x18007768f  inc     dword ptr [rbx+0F0h]
0x180077695  mov     dword ptr [rbx+110h], 12h
0x18007769f  mov     rcx, r13
0x1800776a2  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x1800776a7  nop
0x1800776a8  lea     r8, [rsi+128h]
0x1800776af  mov     [r8], r15
0x1800776b2  lea     rax, qword_1800AF6D8
0x1800776b9  mov     [rsi+130h], rax
0x1800776c0  mov     r13d, 1
0x1800776c6  lock add cs:qword_1800AF6D8, r13
0x1800776ce  mov     rcx, cs:??$factory_cache_entry_v@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticTextIndexStoreStatics@2345@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticTextIndexStoreStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>
0x1800776d5  test    rcx, rcx
0x1800776d8  jz      short loc_180077749
0x1800776da  lea     r13, [rsi+150h]
0x1800776e1  mov     [r13+0], rdi
0x1800776e5  lea     rbx, [rsi+158h]
0x1800776ec  mov     [rbx], edi
0x1800776ee  mov     [rsi+160h], rdi
0x1800776f5  mov     [rsi+168h], rdi
0x1800776fc  mov     rax, [rcx]
0x1800776ff  mov     rdx, [r15]
0x180077702  mov     [rsp+108h+arg_18], rdx
0x18007770a  mov     r8, r13
0x18007770d  mov     rax, [rax+38h]
0x180077711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077716  test    eax, eax
0x180077718  jns     short loc_180077724
0x18007771a  mov     rdx, rbx
0x18007771d  mov     ecx, eax
0x18007771f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180077724  lea     r14, [rsi+0B0h]
0x18007772b  mov     rax, [r13+0]
0x18007772f  mov     [rsp+108h+var_C0], rax
0x180077734  mov     [r14], rax
0x180077737  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007773b  lock add cs:qword_1800AF6D8, rbx
0x180077743  lea     r13d, [rbx+2]
0x180077747  jmp     short loc_180077765
0x180077749  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007774d  lock add cs:qword_1800AF6D8, rbx
0x180077755  lea     r14, [rsi+0B0h]
0x18007775c  mov     rdx, r14
0x18007775f  call    ??$call@AEAV_lambda_27cdfc14008dc8e0d07cbd9d97e1b928_@@@?$factory_cache_entry@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticTextIndexStoreStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_27cdfc14008dc8e0d07cbd9d97e1b928_@@@Z
0x180077764  nop
0x180077765  mov     eax, [rsi+70h]
0x180077768  nop
0x180077769  cmp     eax, 2
0x18007776c  jnz     short loc_180077798
0x18007776e  lea     rcx, [rsi+138h]
0x180077775  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18007777a  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18007777d  lea     rcx, [rsp+108h+pExceptionObject]; this
0x180077782  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180077787  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18007778e  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180077793  call    _CxxThrowException_0
0x180077798  lea     rcx, [rsi+0B8h]
0x18007779f  mov     [rcx], rdi
0x1800777a2  mov     [rsi+0C0h], r14
0x1800777a9  mov     [rsi+0C8h], rdi
0x1800777b0  mov     [rsi+0D0h], r13b
0x1800777b7  mov     eax, 4
0x1800777bc  mov     [r12], ax
0x1800777c1  mov     rdx, rsi
0x1800777c4  call    ??$await_suspend@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@$$V@std@@@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@$$V@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,>::promise_type>)
0x1800777c9  test    al, al
0x1800777cb  jz      loc_180077877
0x1800777d1  jmp     loc_180077ABF
0x1800777d6  mov     rbx, [rsi+0B8h]; jumptable 00000001800775CE case 6
0x1800777dd  xor     edi, edi
0x1800777df  test    rbx, rbx
0x1800777e2  jz      short loc_1800777FC
0x1800777e4  mov     [rsp+108h+var_98], rbx
0x1800777e9  jmp     short loc_1800777F1
0x1800777eb  call    cs:__imp__Thrd_yield
0x1800777f1  mov     rax, rdi
0x1800777f4  xchg    rax, [rbx]
0x1800777f7  cmp     rax, r13
0x1800777fa  jz      short loc_1800777EB
0x1800777fc  lea     rcx, [rsi+0B0h]
0x180077803  mov     rax, [rcx]
0x180077806  mov     [rsp+108h+var_D0], rax
0x18007780b  test    rax, rax
0x18007780e  jz      short loc_180077816
0x180077810  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180077815  nop
0x180077816  mov     r14, [rsi+0A0h]
0x18007781d  mov     [rsp+108h+arg_10], r14
0x180077825  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180077829  test    r14, r14
0x18007782c  jz      short loc_18007784F
0x18007782e  mov     eax, ebx
0x180077830  lock xadd [r14+120h], eax
0x180077839  add     eax, ebx
0x18007783b  jnz     short loc_18007784F
0x18007783d  mov     rcx, r14
0x180077840  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180077845  mov     rcx, r14; pv
0x180077848  call    cs:__imp_CoTaskMemFree
0x18007784e  nop
0x18007784f  lea     rcx, [rsi+98h]
0x180077856  mov     rax, [rcx]
0x180077859  mov     [rsp+108h+arg_18], rax
0x180077861  test    rax, rax
0x180077864  jz      short loc_18007786C
0x180077866  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18007786b  nop
0x18007786c  jmp     loc_180077A39
0x180077871  xor     edi, edi; jumptable 00000001800775CE case 5
0x180077873  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180077877  lea     r15, [rsi+0D8h]
0x18007787e  lea     r14, [rsi+0B8h]
0x180077885  mov     rdx, r15
0x180077888  mov     rcx, r14
0x18007788b  call    ?await_resume@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_resume(void)
0x180077890  nop
0x180077891  mov     r14, [r14]
0x180077894  test    r14, r14
0x180077897  jz      short loc_1800778B1
0x180077899  mov     [rsp+108h+var_98], r14
0x18007789e  jmp     short loc_1800778A6
0x1800778a0  call    cs:__imp__Thrd_yield
0x1800778a6  mov     rax, rdi
0x1800778a9  xchg    rax, [r14]
0x1800778ac  cmp     rax, r13
0x1800778af  jz      short loc_1800778A0
0x1800778b1  lea     rcx, [rsi+0B0h]
0x1800778b8  mov     rax, [rcx]
0x1800778bb  mov     [rsp+108h+var_D0], rax
0x1800778c0  test    rax, rax
0x1800778c3  jz      short loc_1800778CA
0x1800778c5  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x1800778ca  mov     edx, [rsi+88h]
0x1800778d0  mov     rcx, [rsi+170h]
0x1800778d7  call    ?AreSemanticTextSearchModelsAvailable@ModelPackageManager@@SA_NAEBUhstring@winrt@@W4SemanticIndexCreationDisposition@SemanticSearch@Indexer@Windows@3@@Z; ModelPackageManager::AreSemanticTextSearchModelsAvailable(winrt::hstring const &,winrt::Windows::Indexer::SemanticSearch::SemanticIndexCreationDisposition)
0x1800778dc  test    al, al
0x1800778de  jnz     short loc_18007793E
0x1800778e0  mov     rcx, r15; struct winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult *
0x1800778e3  call    ?ThrowIfPackageDeploymentFailed@ModelPackageManager@@CAXAEBUPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@Z; ModelPackageManager::ThrowIfPackageDeploymentFailed(winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult const &)
0x1800778e8  lea     rcx, aAifabricapispe_2; "AIFabricAPIsPerfTest::reason::PolarisSe"...
0x1800778ef  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800778f4  mov     r8, rax
0x1800778f7  call    ??$validate_reason@W4reason@_tip_AIFabricAPIsPerfTest@@$01@details@tip2@@YAGXZ; tip2::details::validate_reason<_tip_AIFabricAPIsPerfTest::reason,2>(void)
0x1800778fc  movzx   edx, ax
0x1800778ff  lea     rcx, [rsi+0A0h]
0x180077906  call    ?complete_and_fail@?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::complete_and_fail(ushort,char const *)
0x18007790b  mov     ecx, 8000FFFFh
0x180077910  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x180077915  mov     r9d, eax; char *
0x180077918  mov     rcx, [rsp+108h]; this
0x180077920  lea     rax, aMakeavailablea_1; "MakeAvailableAsync succeeded but models"...
0x180077927  mov     qword ptr [rsp+108h+var_E8], rax; int
0x18007792c  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\search\\com"...
0x180077933  mov     edx, 63h ; 'c'; void *
0x180077938  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18007793e  mov     rax, [r15]
0x180077941  mov     [rsp+108h+var_B8], rax
0x180077946  test    rax, rax
0x180077949  jz      short loc_180077954
0x18007794b  mov     rcx, r15
0x18007794e  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180077953  nop
0x180077954  mov     r14, [rsi+0A0h]
0x18007795b  test    r14, r14
0x18007795e  jz      short loc_1800779A6
0x180077960  mov     [rsp+108h+arg_10], r14
0x180077968  lea     r15, [r14+0C8h]
0x18007796f  mov     rcx, r15; lpCriticalSection
0x180077972  call    cs:__imp_EnterCriticalSection
0x180077978  or      dword ptr [r14+48h], 300h
0x180077980  cmp     [r14+0F8h], rdi
0x180077987  jz      short loc_180077997
0x180077989  mov     edx, 2
0x18007798e  lea     rcx, [r14+8]
0x180077992  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180077997  test    r15, r15
0x18007799a  jz      short loc_1800779A6
0x18007799c  mov     rcx, r15; lpCriticalSection
0x18007799f  call    cs:__imp_LeaveCriticalSection
0x1800779a5  nop
0x1800779a6  mov     r14, [rsi+0A0h]
0x1800779ad  mov     [rsp+108h+arg_10], r14
0x1800779b5  test    r14, r14
0x1800779b8  jz      short loc_1800779DB
0x1800779ba  mov     eax, ebx
0x1800779bc  lock xadd [r14+120h], eax
0x1800779c5  add     eax, ebx
0x1800779c7  jnz     short loc_1800779DB
0x1800779c9  mov     rcx, r14
0x1800779cc  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x1800779d1  mov     rcx, r14; pv
0x1800779d4  call    cs:__imp_CoTaskMemFree
0x1800779da  nop
0x1800779db  lea     rcx, [rsi+98h]
0x1800779e2  mov     rax, [rcx]
0x1800779e5  mov     [rsp+108h+arg_18], rax
0x1800779ed  test    rax, rax
0x1800779f0  jz      short loc_1800779F8
0x1800779f2  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x1800779f7  nop
0x1800779f8  jmp     short loc_180077A0D
0x1800779fa  xor     edi, edi
0x1800779fc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180077a00  mov     rsi, [rsp+108h+arg_0]
0x180077a08  mov     r12, [rsp+108h+var_C8]
0x180077a0d  lea     rax, [rsi+10h]
0x180077a11  lea     rcx, [rsi+120h]
0x180077a18  mov     [rcx], rax
0x180077a1b  xor     eax, eax
0x180077a1d  mov     [r12], ax
0x180077a22  mov     [rsi], rdi
0x180077a25  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUIndexerSemanticStore@@W4ModelKind@SemanticSearch@Indexer@34@@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticStore &,winrt::Windows::Indexer::SemanticSearch::ModelKind>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x180077a2a  test    al, al
0x180077a2c  jz      short loc_180077A39
0x180077a2e  jmp     loc_180077ABF
0x180077a33  xor     edi, edi; jumptable 00000001800775CE cases 0,2
0x180077a35  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180077a39  lea     rcx, [rsi+68h]
0x180077a3d  cmp     [rcx], rdi
0x180077a40  jz      short loc_180077A47
0x180077a42  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180077a47  lea     rcx, [rsi+60h]
0x180077a4b  cmp     [rcx], rdi
0x180077a4e  jz      short loc_180077A55
0x180077a50  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180077a55  lea     rcx, [rsi+48h]
0x180077a59  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180077a5f  lea     rcx, [rsi+10h]
0x180077a63  call    ??1?$root_implements@UIndexerSemanticSearchServicesImpl@@UIIndexerSemanticSearchServices@@UISemanticSearchServices@SemanticSearch@Indexer@Windows@winrt@@Unon_agile@7@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<IndexerSemanticSearchServicesImpl,IIndexerSemanticSearchServices,winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices,winrt::non_agile>::~root_implements<IndexerSemanticSearchServicesImpl,IIndexerSemanticSearchServices,winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices,winrt::non_agile>(void)
0x180077a68  mov     r14, [rsi+80h]
  ... truncated ...
```
