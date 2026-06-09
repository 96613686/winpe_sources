# ModelPackageManager::MakeSemanticImageSearchModelsAvailableAsync$_ResumeCoro$1

- ea: `0x180076ec0`
- end: `0x180077440`
- name: `ModelPackageManager::MakeSemanticImageSearchModelsAvailableAsync$_ResumeCoro$1`
- size: `1408`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180076ea0`
- `0x180077448`

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
- `0x18003cf0c`
- `0x18004ba10`
- `0x18004dd6c`
- `0x18004dea8`
- `0x18004eb70`
- `0x18005266c`
- `0x180073ce8`
- `0x180073eb4`
- `0x1800748bc`
- `0x180074e4c`
- `0x180076ec0`
- `0x1800783b8`
- `0x1800785a8`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800773e8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800773e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800772ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800772ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076fd9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800772c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076fd9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800772c2`
- `msvcp_win!_Thrd_yield` at `0x18007713b`
- `msvcp_win!_Thrd_yield` at `0x1800771f0`
- `msvcp_win!_Thrd_yield` at `0x18007713b`
- `msvcp_win!_Thrd_yield` at `0x1800771f0`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800773a9`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800773a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077198`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077324`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077198`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077324`

## string_xrefs

- `0x180076f67`: `onecoreuap\base\appmodel\Search\common\AIFabricHostHelper\include\Utils.h`
- `0x18007727c`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\modelpackagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall ModelPackageManager::MakeSemanticImageSearchModelsAvailableAsync__ResumeCoro_1(_WORD *a1)
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
      Utils::GetSemanticImageIndexStoreOptions(a1 + 76, a1 + 64, v7);
      tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>(a1 + 80);
      v9 = (__int64 *)tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::ensure_data(a1 + 80);
      v10 = *v9;
      *((_QWORD *)a1 + 21) = *v9;
      if ( v10 )
        _InterlockedIncrement((volatile signed __int32 *)(v10 + 288));
      *((_QWORD *)a1 + 46) = v3;
      EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 200));
      ++*(_DWORD *)(v10 + 240);
      *(_DWORD *)(v10 + 272) = 19;
      tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(a1 + 84);
      *((_QWORD *)a1 + 37) = v8;
      *((_QWORD *)a1 + 38) = &qword_1800AF658;
      _InterlockedAdd64(&qword_1800AF658, 1u);
      v11 = winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>;
      if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics> )
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
        _InterlockedAdd64(&qword_1800AF658, 0xFFFFFFFFFFFFFFFFuLL);
      }
      else
      {
        _InterlockedAdd64(&qword_1800AF658, 0xFFFFFFFFFFFFFFFFuLL);
        v13 = a1 + 88;
        winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>::call<_lambda_3a963aefb97e81b874c95be865cbc733_ &>(
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
      if ( !(unsigned __int8)ModelPackageManager::AreSemanticImageSearchModelsAvailable(
                               *((_QWORD *)a1 + 46),
                               *((unsigned int *)a1 + 34)) )
      {
        ModelPackageManager::ThrowIfPackageDeploymentFailed((const struct winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult *)(a1 + 108));
        v19 = tip2::details::reason_string(
                (tip2::details *)"AIFabricAPIsPerfTest::reason::ImageSearchModelNotAvailable",
                v18);
        v22 = tip2::details::validate_reason<enum _tip_AIFabricAPIsPerfTest::reason,4>(v21, v20, v19);
        tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::complete_and_fail(
          a1 + 80,
          v22,
          v23);
        v24 = wil::verify_hresult(2147549183LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x89,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\modelpackagemanager.cpp",
          (const char *)v24,
          (int)"MakeAvailableAsync succeeded but image models are still not available",
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
0x180076ec0  mov     [rsp+arg_0], rcx
0x180076ec5  push    rbx
0x180076ec6  push    rsi
0x180076ec7  push    rdi
0x180076ec8  push    r12
0x180076eca  push    r13
0x180076ecc  push    r14
0x180076ece  push    r15
0x180076ed0  sub     rsp, 0D0h
0x180076ed7  mov     rsi, [rsp+108h+arg_0]
0x180076edf  lea     r12, [rsi+90h]
0x180076ee6  movzx   eax, word ptr [r12]
0x180076eeb  mov     [rsp+108h+var_D8], ax
0x180076ef0  mov     r13d, 1
0x180076ef6  add     ax, r13w
0x180076efa  cmp     ax, 6; switch 7 cases
0x180076efe  ja      def_180076F1E; jumptable 0000000180076F1E default case, case 1
0x180076f04  mov     [rsp+108h+var_C8], r12
0x180076f09  movsx   rax, ax
0x180076f0d  lea     rdx, __ImageBase
0x180076f14  mov     ecx, ds:(jpt_180076F1E - 180000000h)[rdx+rax*4]
0x180076f1b  add     rcx, rdx
0x180076f1e  jmp     rcx; switch jump
0x180076f20  xor     edi, edi; jumptable 0000000180076F1E case 4
0x180076f22  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180076f26  jmp     loc_180077389
0x180076f2b  xor     edi, edi; jumptable 0000000180076F1E case 3
0x180076f2d  lea     r14, [rsi+80h]
0x180076f34  mov     ecx, [r14+8]
0x180076f38  test    ecx, ecx
0x180076f3a  jz      short loc_180076F83
0x180076f3c  sub     ecx, 1
0x180076f3f  jz      short loc_180076F7E
0x180076f41  cmp     ecx, 1
0x180076f44  jz      short loc_180076F76
0x180076f46  mov     ecx, 8000FFFFh
0x180076f4b  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x180076f50  mov     r9d, eax; char *
0x180076f53  mov     rcx, [rsp+108h]; this
0x180076f5b  lea     rax, aUnexpectedDisp; "Unexpected disposition."
0x180076f62  mov     qword ptr [rsp+108h+var_E8], rax; int
0x180076f67  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180076f6e  lea     edx, [rdi+20h]; void *
0x180076f71  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180076f76  mov     r8d, 2
0x180076f7c  jmp     short loc_180076F86
0x180076f7e  mov     r8d, r13d
0x180076f81  jmp     short loc_180076F86
0x180076f83  mov     r8d, edi
0x180076f86  lea     r15, [rsi+98h]
0x180076f8d  mov     rdx, r14
0x180076f90  mov     rcx, r15
0x180076f93  call    ?GetSemanticImageIndexStoreOptions@Utils@@YA?AUSemanticImageIndexStoreOptions@SemanticSearch@Windows@Microsoft@winrt@@AEBUhstring@6@W4IndexCreationDisposition@3456@@Z; Utils::GetSemanticImageIndexStoreOptions(winrt::hstring const &,winrt::Microsoft::Windows::SemanticSearch::IndexCreationDisposition)
0x180076f98  nop
0x180076f99  lea     rbx, [rsi+0A0h]
0x180076fa0  mov     rcx, rbx
0x180076fa3  call    ??$start@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>(void)
0x180076fa8  nop
0x180076fa9  mov     rcx, rbx
0x180076fac  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::ensure_data(void)
0x180076fb1  mov     rbx, [rax]
0x180076fb4  lea     r13, [rsi+0A8h]
0x180076fbb  mov     [r13+0], rbx
0x180076fbf  test    rbx, rbx
0x180076fc2  jz      short loc_180076FCB
0x180076fc4  lock inc dword ptr [rbx+120h]
0x180076fcb  mov     [rsi+170h], r14
0x180076fd2  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180076fd9  call    cs:__imp_EnterCriticalSection
0x180076fdf  inc     dword ptr [rbx+0F0h]
0x180076fe5  mov     dword ptr [rbx+110h], 13h
0x180076fef  mov     rcx, r13
0x180076ff2  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180076ff7  nop
0x180076ff8  lea     r8, [rsi+128h]
0x180076fff  mov     [r8], r15
0x180077002  lea     rax, qword_1800AF658
0x180077009  mov     [rsi+130h], rax
0x180077010  mov     r13d, 1
0x180077016  lock add cs:qword_1800AF658, r13
0x18007701e  mov     rcx, cs:??$factory_cache_entry_v@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticImageIndexStoreStatics@2345@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticImageIndexStoreStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>
0x180077025  test    rcx, rcx
0x180077028  jz      short loc_180077099
0x18007702a  lea     r13, [rsi+150h]
0x180077031  mov     [r13+0], rdi
0x180077035  lea     rbx, [rsi+158h]
0x18007703c  mov     [rbx], edi
0x18007703e  mov     [rsi+160h], rdi
0x180077045  mov     [rsi+168h], rdi
0x18007704c  mov     rax, [rcx]
0x18007704f  mov     rdx, [r15]
0x180077052  mov     [rsp+108h+arg_18], rdx
0x18007705a  mov     r8, r13
0x18007705d  mov     rax, [rax+38h]
0x180077061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077066  test    eax, eax
0x180077068  jns     short loc_180077074
0x18007706a  mov     rdx, rbx
0x18007706d  mov     ecx, eax
0x18007706f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180077074  lea     r14, [rsi+0B0h]
0x18007707b  mov     rax, [r13+0]
0x18007707f  mov     [rsp+108h+var_C0], rax
0x180077084  mov     [r14], rax
0x180077087  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007708b  lock add cs:qword_1800AF658, rbx
0x180077093  lea     r13d, [rbx+2]
0x180077097  jmp     short loc_1800770B5
0x180077099  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007709d  lock add cs:qword_1800AF658, rbx
0x1800770a5  lea     r14, [rsi+0B0h]
0x1800770ac  mov     rdx, r14
0x1800770af  call    ??$call@AEAV_lambda_3a963aefb97e81b874c95be865cbc733_@@@?$factory_cache_entry@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticImageIndexStoreStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_3a963aefb97e81b874c95be865cbc733_@@@Z
0x1800770b4  nop
0x1800770b5  mov     eax, [rsi+70h]
0x1800770b8  nop
0x1800770b9  cmp     eax, 2
0x1800770bc  jnz     short loc_1800770E8
0x1800770be  lea     rcx, [rsi+138h]
0x1800770c5  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800770ca  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800770cd  lea     rcx, [rsp+108h+pExceptionObject]; this
0x1800770d2  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x1800770d7  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x1800770de  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x1800770e3  call    _CxxThrowException_0
0x1800770e8  lea     rcx, [rsi+0B8h]
0x1800770ef  mov     [rcx], rdi
0x1800770f2  mov     [rsi+0C0h], r14
0x1800770f9  mov     [rsi+0C8h], rdi
0x180077100  mov     [rsi+0D0h], r13b
0x180077107  mov     eax, 4
0x18007710c  mov     [r12], ax
0x180077111  mov     rdx, rsi
0x180077114  call    ??$await_suspend@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@$$V@std@@@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@$$V@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,>::promise_type>)
0x180077119  test    al, al
0x18007711b  jz      loc_1800771C7
0x180077121  jmp     loc_18007740F
0x180077126  mov     rbx, [rsi+0B8h]; jumptable 0000000180076F1E case 6
0x18007712d  xor     edi, edi
0x18007712f  test    rbx, rbx
0x180077132  jz      short loc_18007714C
0x180077134  mov     [rsp+108h+var_98], rbx
0x180077139  jmp     short loc_180077141
0x18007713b  call    cs:__imp__Thrd_yield
0x180077141  mov     rax, rdi
0x180077144  xchg    rax, [rbx]
0x180077147  cmp     rax, r13
0x18007714a  jz      short loc_18007713B
0x18007714c  lea     rcx, [rsi+0B0h]
0x180077153  mov     rax, [rcx]
0x180077156  mov     [rsp+108h+var_D0], rax
0x18007715b  test    rax, rax
0x18007715e  jz      short loc_180077166
0x180077160  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180077165  nop
0x180077166  mov     r14, [rsi+0A0h]
0x18007716d  mov     [rsp+108h+arg_10], r14
0x180077175  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180077179  test    r14, r14
0x18007717c  jz      short loc_18007719F
0x18007717e  mov     eax, ebx
0x180077180  lock xadd [r14+120h], eax
0x180077189  add     eax, ebx
0x18007718b  jnz     short loc_18007719F
0x18007718d  mov     rcx, r14
0x180077190  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180077195  mov     rcx, r14; pv
0x180077198  call    cs:__imp_CoTaskMemFree
0x18007719e  nop
0x18007719f  lea     rcx, [rsi+98h]
0x1800771a6  mov     rax, [rcx]
0x1800771a9  mov     [rsp+108h+arg_18], rax
0x1800771b1  test    rax, rax
0x1800771b4  jz      short loc_1800771BC
0x1800771b6  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x1800771bb  nop
0x1800771bc  jmp     loc_180077389
0x1800771c1  xor     edi, edi; jumptable 0000000180076F1E case 5
0x1800771c3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800771c7  lea     r15, [rsi+0D8h]
0x1800771ce  lea     r14, [rsi+0B8h]
0x1800771d5  mov     rdx, r15
0x1800771d8  mov     rcx, r14
0x1800771db  call    ?await_resume@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_resume(void)
0x1800771e0  nop
0x1800771e1  mov     r14, [r14]
0x1800771e4  test    r14, r14
0x1800771e7  jz      short loc_180077201
0x1800771e9  mov     [rsp+108h+var_98], r14
0x1800771ee  jmp     short loc_1800771F6
0x1800771f0  call    cs:__imp__Thrd_yield
0x1800771f6  mov     rax, rdi
0x1800771f9  xchg    rax, [r14]
0x1800771fc  cmp     rax, r13
0x1800771ff  jz      short loc_1800771F0
0x180077201  lea     rcx, [rsi+0B0h]
0x180077208  mov     rax, [rcx]
0x18007720b  mov     [rsp+108h+var_D0], rax
0x180077210  test    rax, rax
0x180077213  jz      short loc_18007721A
0x180077215  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18007721a  mov     edx, [rsi+88h]
0x180077220  mov     rcx, [rsi+170h]
0x180077227  call    ?AreSemanticImageSearchModelsAvailable@ModelPackageManager@@SA_NAEBUhstring@winrt@@W4SemanticIndexCreationDisposition@SemanticSearch@Indexer@Windows@3@@Z; ModelPackageManager::AreSemanticImageSearchModelsAvailable(winrt::hstring const &,winrt::Windows::Indexer::SemanticSearch::SemanticIndexCreationDisposition)
0x18007722c  test    al, al
0x18007722e  jnz     short loc_18007728E
0x180077230  mov     rcx, r15; struct winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult *
0x180077233  call    ?ThrowIfPackageDeploymentFailed@ModelPackageManager@@CAXAEBUPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@Z; ModelPackageManager::ThrowIfPackageDeploymentFailed(winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult const &)
0x180077238  lea     rcx, aAifabricapispe_0; "AIFabricAPIsPerfTest::reason::ImageSear"...
0x18007723f  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180077244  mov     r8, rax
0x180077247  call    ??$validate_reason@W4reason@_tip_AIFabricAPIsPerfTest@@$03@details@tip2@@YAGXZ; tip2::details::validate_reason<_tip_AIFabricAPIsPerfTest::reason,4>(void)
0x18007724c  movzx   edx, ax
0x18007724f  lea     rcx, [rsi+0A0h]
0x180077256  call    ?complete_and_fail@?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::complete_and_fail(ushort,char const *)
0x18007725b  mov     ecx, 8000FFFFh
0x180077260  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x180077265  mov     r9d, eax; char *
0x180077268  mov     rcx, [rsp+108h]; this
0x180077270  lea     rax, aMakeavailablea; "MakeAvailableAsync succeeded but image "...
0x180077277  mov     qword ptr [rsp+108h+var_E8], rax; int
0x18007727c  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\search\\com"...
0x180077283  mov     edx, 89h; void *
0x180077288  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18007728e  mov     rax, [r15]
0x180077291  mov     [rsp+108h+var_B8], rax
0x180077296  test    rax, rax
0x180077299  jz      short loc_1800772A4
0x18007729b  mov     rcx, r15
0x18007729e  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x1800772a3  nop
0x1800772a4  mov     r14, [rsi+0A0h]
0x1800772ab  test    r14, r14
0x1800772ae  jz      short loc_1800772F6
0x1800772b0  mov     [rsp+108h+arg_10], r14
0x1800772b8  lea     r15, [r14+0C8h]
0x1800772bf  mov     rcx, r15; lpCriticalSection
0x1800772c2  call    cs:__imp_EnterCriticalSection
0x1800772c8  or      dword ptr [r14+48h], 300h
0x1800772d0  cmp     [r14+0F8h], rdi
0x1800772d7  jz      short loc_1800772E7
0x1800772d9  mov     edx, 2
0x1800772de  lea     rcx, [r14+8]
0x1800772e2  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x1800772e7  test    r15, r15
0x1800772ea  jz      short loc_1800772F6
0x1800772ec  mov     rcx, r15; lpCriticalSection
0x1800772ef  call    cs:__imp_LeaveCriticalSection
0x1800772f5  nop
0x1800772f6  mov     r14, [rsi+0A0h]
0x1800772fd  mov     [rsp+108h+arg_10], r14
0x180077305  test    r14, r14
0x180077308  jz      short loc_18007732B
0x18007730a  mov     eax, ebx
0x18007730c  lock xadd [r14+120h], eax
0x180077315  add     eax, ebx
0x180077317  jnz     short loc_18007732B
0x180077319  mov     rcx, r14
0x18007731c  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180077321  mov     rcx, r14; pv
0x180077324  call    cs:__imp_CoTaskMemFree
0x18007732a  nop
0x18007732b  lea     rcx, [rsi+98h]
0x180077332  mov     rax, [rcx]
0x180077335  mov     [rsp+108h+arg_18], rax
0x18007733d  test    rax, rax
0x180077340  jz      short loc_180077348
0x180077342  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180077347  nop
0x180077348  jmp     short loc_18007735D
0x18007734a  xor     edi, edi
0x18007734c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180077350  mov     rsi, [rsp+108h+arg_0]
0x180077358  mov     r12, [rsp+108h+var_C8]
0x18007735d  lea     rax, [rsi+10h]
0x180077361  lea     rcx, [rsi+120h]
0x180077368  mov     [rcx], rax
0x18007736b  xor     eax, eax
0x18007736d  mov     [r12], ax
0x180077372  mov     [rsi], rdi
0x180077375  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUIndexerSemanticStore@@W4ModelKind@SemanticSearch@Indexer@34@@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticStore &,winrt::Windows::Indexer::SemanticSearch::ModelKind>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x18007737a  test    al, al
0x18007737c  jz      short loc_180077389
0x18007737e  jmp     loc_18007740F
0x180077383  xor     edi, edi; jumptable 0000000180076F1E cases 0,2
0x180077385  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180077389  lea     rcx, [rsi+68h]
0x18007738d  cmp     [rcx], rdi
0x180077390  jz      short loc_180077397
0x180077392  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180077397  lea     rcx, [rsi+60h]
0x18007739b  cmp     [rcx], rdi
0x18007739e  jz      short loc_1800773A5
0x1800773a0  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x1800773a5  lea     rcx, [rsi+48h]
0x1800773a9  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800773af  lea     rcx, [rsi+10h]
0x1800773b3  call    ??1?$root_implements@UIndexerSemanticSearchServicesImpl@@UIIndexerSemanticSearchServices@@UISemanticSearchServices@SemanticSearch@Indexer@Windows@winrt@@Unon_agile@7@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<IndexerSemanticSearchServicesImpl,IIndexerSemanticSearchServices,winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices,winrt::non_agile>::~root_implements<IndexerSemanticSearchServicesImpl,IIndexerSemanticSearchServices,winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices,winrt::non_agile>(void)
0x1800773b8  mov     r14, [rsi+80h]
  ... truncated ...
```
