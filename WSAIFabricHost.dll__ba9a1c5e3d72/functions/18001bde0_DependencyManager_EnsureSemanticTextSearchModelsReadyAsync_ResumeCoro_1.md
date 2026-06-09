# DependencyManager::EnsureSemanticTextSearchModelsReadyAsync$_ResumeCoro$1

- ea: `0x18001bde0`
- end: `0x18001c658`
- name: `DependencyManager::EnsureSemanticTextSearchModelsReadyAsync$_ResumeCoro$1`
- size: `2168`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001bdc0`
- `0x18001c660`

## callees

- `0x180005140`
- `0x180005758`
- `0x1800058cb`
- `0x18000591f`
- `0x180007ad0`
- `0x180007f72`
- `0x18000c018`
- `0x18000c350`
- `0x18000c478`
- `0x18000c634`
- `0x180014688`
- `0x180018fa0`
- `0x18001a0d4`
- `0x18001a420`
- `0x18001a6b4`
- `0x18001bde0`
- `0x18001dc68`
- `0x18001dd84`
- `0x18001de54`
- `0x180074cb0`
- `0x180075068`
- `0x1800765d0`
- `0x180077af8`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001c5e9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001c5e9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001bfe3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001c1d1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001c25e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001c2dd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001c4a3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001c52c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001bfe3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001c1d1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001c25e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001c2dd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001c4a3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001c52c`
- `msvcp_win!_Thrd_yield` at `0x18001bfa1`
- `msvcp_win!_Thrd_yield` at `0x18001c02d`
- `msvcp_win!_Thrd_yield` at `0x18001c192`
- `msvcp_win!_Thrd_yield` at `0x18001c21b`
- `msvcp_win!_Thrd_yield` at `0x18001c29b`
- `msvcp_win!_Thrd_yield` at `0x18001c327`
- `msvcp_win!_Thrd_yield` at `0x18001c464`
- `msvcp_win!_Thrd_yield` at `0x18001c4ed`
- `msvcp_win!_Thrd_yield` at `0x18001bfa1`
- `msvcp_win!_Thrd_yield` at `0x18001c02d`
- `msvcp_win!_Thrd_yield` at `0x18001c192`
- `msvcp_win!_Thrd_yield` at `0x18001c21b`
- `msvcp_win!_Thrd_yield` at `0x18001c29b`
- `msvcp_win!_Thrd_yield` at `0x18001c327`
- `msvcp_win!_Thrd_yield` at `0x18001c464`
- `msvcp_win!_Thrd_yield` at `0x18001c4ed`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001c5a8`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001c5a8`

## string_xrefs

- `0x18001bff5`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18001c1e3`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18001c274`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18001c2ef`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18001c4b5`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18001c53e`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall DependencyManager::EnsureSemanticTextSearchModelsReadyAsync__ResumeCoro_1(__int64 a1)
{
  _WORD *v2; // r15
  __int64 v3; // rax
  const struct winrt::impl::slim_source_location *v4; // rax
  __int64 v5; // rax
  const struct winrt::impl::slim_source_location *v6; // rax
  volatile __int64 *v7; // rbx
  void *v8; // rcx
  const char *v9; // r9
  volatile __int64 *v10; // rbx
  _QWORD *v11; // r14
  const struct winrt::impl::slim_source_location *v12; // rax
  volatile __int64 *v13; // rbx
  void *v14; // rcx
  const char *v15; // r9
  volatile __int64 *v16; // rbx
  void *v17; // rcx
  const char *v18; // r9
  volatile __int64 *v19; // rbx
  void *v20; // rcx
  const char *v21; // r9
  unsigned int v22; // edx
  volatile __int64 *v23; // rbx
  unsigned int v24; // eax
  struct winrt::impl::shared_hstring_header *v25; // rbx
  unsigned int v26; // r14d
  const void *v27; // r13
  __int64 SemanticTextSearchModelsAvailableAsync; // rax
  const struct winrt::impl::slim_source_location *v29; // rax
  volatile __int64 *v30; // rbx
  void *v31; // rcx
  const char *v32; // r9
  volatile __int64 *v33; // rbx
  void *v34; // rcx
  const char *v35; // r9
  volatile signed __int32 *v36; // rbx
  int v37; // eax
  HANDLE ProcessHeap; // rax
  _BYTE pExceptionObject[24]; // [rsp+78h] [rbp-160h] BYREF
  _BYTE v40[24]; // [rsp+90h] [rbp-148h] BYREF
  _BYTE v41[24]; // [rsp+A8h] [rbp-130h] BYREF
  _BYTE v42[280]; // [rsp+C0h] [rbp-118h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]
  unsigned int v44; // [rsp+1E8h] [rbp+10h]

  v2 = (_WORD *)(a1 + 152);
  switch ( *(_WORD *)(a1 + 152) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_96;
    case 2:
      if ( !*(_QWORD *)(a1 + 136) )
      {
        if ( !ModelPackageManager::AreDefaultTextSearchModelsAvailable() )
        {
          *(_QWORD *)(a1 + 160) = 0;
          v3 = Indexer::MakeAvailableAsyncWaiter::WaitAsync(a1 + 160, a1 + 168);
          if ( *(_DWORD *)(a1 + 112) == 2 )
          {
            v4 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 352);
            winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject, v4);
            throw (winrt::hresult_canceled *)pExceptionObject;
          }
          *(_QWORD *)(a1 + 176) = 0;
          *(_QWORD *)(a1 + 184) = v3;
          *(_QWORD *)(a1 + 192) = 0;
          *(_BYTE *)(a1 + 200) = 1;
          *v2 = 4;
          if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticSearchServicesImpl &,winrt::Windows::Indexer::SemanticSearch::SemanticIndexStoreOptions>::promise_type>(
                                  (__int64 *)(a1 + 176),
                                  a1) )
            return;
LABEL_22:
          winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_resume(a1 + 176);
          v10 = *(volatile __int64 **)(a1 + 176);
          if ( v10 )
          {
            while ( _InterlockedExchange64(v10, 0) == 1 )
              _Thrd_yield();
          }
          if ( *(_QWORD *)(a1 + 168) )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 168);
          v11 = operator new(0x150u);
          *(_QWORD *)(a1 + 376) = v11;
          v11[1] = ModelPackageManager::MakeDefaultSemanticTextSearchModelsAvailableAsync__DestroyCoro_2;
          *v11 = ModelPackageManager::MakeDefaultSemanticTextSearchModelsAvailableAsync__ResumeCoro_1;
          *((_DWORD *)v11 + 31) = 65538;
          memset_0(v11 + 2, 0, 0x68u);
          std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::hstring,enum winrt::Windows::Indexer::SemanticSearch::SemanticIndexCreationDisposition>::promise_type::promise_type((__int64)(v11 + 2));
          *(_QWORD *)(a1 + 208) = v11 + 4;
          if ( v11 != (_QWORD *)-32LL )
            (*(void (__fastcall **)(_QWORD *))(v11[4] + 8LL))(v11 + 4);
          *((_BYTE *)v11 + 120) = 0;
          ModelPackageManager::MakeDefaultSemanticTextSearchModelsAvailableAsync__ResumeCoro_1(v11);
          if ( *(_DWORD *)(a1 + 112) == 2 )
          {
            v12 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 752);
            winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v41, v12);
            throw (winrt::hresult_canceled *)v41;
          }
          *(_QWORD *)(a1 + 216) = 0;
          *(_QWORD *)(a1 + 224) = a1 + 208;
          *(_QWORD *)(a1 + 232) = 0;
          *(_BYTE *)(a1 + 240) = 1;
          *v2 = 6;
          if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticSearchServicesImpl &,winrt::Windows::Indexer::SemanticSearch::SemanticIndexStoreOptions>::promise_type>(
                                  (__int64 *)(a1 + 216),
                                  a1) )
            return;
LABEL_43:
          winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_resume(a1 + 216);
          v16 = *(volatile __int64 **)(a1 + 216);
          if ( v16 )
          {
            while ( _InterlockedExchange64(v16, 0) == 1 )
              _Thrd_yield();
          }
          if ( *(_QWORD *)(a1 + 208) )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 208);
          v17 = *(void **)(a1 + 160);
          if ( v17 && !SetEvent(v17) )
            wil::details::in1diag3::_FailFast_GetLastError(
              retaddr,
              (void *)0xA01,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
              v18);
        }
        goto LABEL_95;
      }
      if ( (unsigned __int8)ModelPackageManager::AreSemanticTextSearchModelsAvailable(
                              a1 + 136,
                              *(unsigned int *)(a1 + 144)) )
        goto LABEL_95;
      *(_QWORD *)(a1 + 248) = 0;
      v5 = Indexer::MakeAvailableAsyncWaiter::WaitAsync(a1 + 248, a1 + 256);
      if ( *(_DWORD *)(a1 + 112) == 2 )
      {
        v6 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 776);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v40, v6);
        throw (winrt::hresult_canceled *)v40;
      }
      *(_QWORD *)(a1 + 264) = 0;
      *(_QWORD *)(a1 + 272) = v5;
      *(_QWORD *)(a1 + 280) = 0;
      *(_BYTE *)(a1 + 288) = 1;
      *v2 = 8;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticSearchServicesImpl &,winrt::Windows::Indexer::SemanticSearch::SemanticIndexStoreOptions>::promise_type>(
                              (__int64 *)(a1 + 264),
                              a1) )
        return;
LABEL_61:
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_resume(a1 + 264);
      v23 = *(volatile __int64 **)(a1 + 264);
      if ( v23 )
      {
        while ( _InterlockedExchange64(v23, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 256) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 256);
      v24 = *(_DWORD *)(a1 + 144);
      v44 = v24;
      v25 = *(struct winrt::impl::shared_hstring_header **)(a1 + 136);
      if ( !v25 )
        goto LABEL_68;
      if ( (*(_DWORD *)v25 & 1) != 0 )
      {
        v26 = *((_DWORD *)v25 + 1);
        if ( v26 )
        {
          v27 = (const void *)*((_QWORD *)v25 + 2);
          v25 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v26, v22);
          memcpy_s((char *)v25 + 28, 2LL * v26, v27, 2LL * v26);
          v24 = v44;
        }
        else
        {
LABEL_68:
          v25 = 0;
        }
      }
      else
      {
        _InterlockedIncrement((volatile signed __int32 *)v25 + 6);
      }
      *(_QWORD *)(a1 + 296) = v25;
      SemanticTextSearchModelsAvailableAsync = ModelPackageManager::MakeSemanticTextSearchModelsAvailableAsync(
                                                 a1 + 304,
                                                 a1 + 296,
                                                 v24);
      if ( *(_DWORD *)(a1 + 112) == 2 )
      {
        v29 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 800);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v42, v29);
        throw (winrt::hresult_canceled *)v42;
      }
      *(_QWORD *)(a1 + 312) = 0;
      *(_QWORD *)(a1 + 320) = SemanticTextSearchModelsAvailableAsync;
      *(_QWORD *)(a1 + 328) = 0;
      *(_BYTE *)(a1 + 336) = 1;
      *v2 = 10;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticSearchServicesImpl &,winrt::Windows::Indexer::SemanticSearch::SemanticIndexStoreOptions>::promise_type>(
                              (__int64 *)(a1 + 312),
                              a1) )
        return;
LABEL_86:
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_resume(a1 + 312);
      v33 = *(volatile __int64 **)(a1 + 312);
      if ( v33 )
      {
        while ( _InterlockedExchange64(v33, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 304) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 304);
      v34 = *(void **)(a1 + 248);
      if ( v34 && !SetEvent(v34) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA01,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v35);
LABEL_95:
      *(_QWORD *)(a1 + 344) = a1 + 16;
      *v2 = 0;
      *(_QWORD *)a1 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticStore &,enum winrt::Windows::Indexer::SemanticSearch::ModelKind>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend() )
      {
LABEL_96:
        if ( *(_QWORD *)(a1 + 104) )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 104);
        if ( *(_QWORD *)(a1 + 96) )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 96);
        __ExceptionPtrDestroy((void *)(a1 + 72));
        winrt::impl::root_implements<IndexerSemanticSearchServicesImpl,IIndexerSemanticSearchServices,winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices,winrt::non_agile>::~root_implements<IndexerSemanticSearchServicesImpl,IIndexerSemanticSearchServices,winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices,winrt::non_agile>(a1 + 16);
        v36 = *(volatile signed __int32 **)(a1 + 136);
        if ( v36 )
        {
          v37 = _InterlockedDecrement(v36 + 6);
          if ( v37 )
          {
            if ( v37 < 0 )
              abort();
          }
          else
          {
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v36);
          }
          *(_QWORD *)(a1 + 136) = 0;
        }
        if ( *(_WORD *)(a1 + 154) )
          operator delete((void *)a1, 0x340u);
      }
      return;
    case 4:
      goto LABEL_22;
    case 5:
      v7 = *(volatile __int64 **)(a1 + 176);
      if ( v7 )
      {
        while ( _InterlockedExchange64(v7, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 168) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 168);
      v8 = *(void **)(a1 + 160);
      if ( v8 && !SetEvent(v8) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA01,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v9);
      goto LABEL_96;
    case 6:
      goto LABEL_43;
    case 7:
      v13 = *(volatile __int64 **)(a1 + 216);
      if ( v13 )
      {
        while ( _InterlockedExchange64(v13, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 208) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 208);
      v14 = *(void **)(a1 + 160);
      if ( v14 && !SetEvent(v14) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA01,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v15);
      goto LABEL_96;
    case 8:
      goto LABEL_61;
    case 9:
      v19 = *(volatile __int64 **)(a1 + 264);
      if ( v19 )
      {
        while ( _InterlockedExchange64(v19, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 256) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 256);
      v20 = *(void **)(a1 + 248);
      if ( v20 && !SetEvent(v20) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA01,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v21);
      goto LABEL_96;
    case 0xA:
      goto LABEL_86;
    case 0xB:
      v30 = *(volatile __int64 **)(a1 + 312);
      if ( v30 )
      {
        while ( _InterlockedExchange64(v30, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 304) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 304);
      v31 = *(void **)(a1 + 248);
      if ( v31 && !SetEvent(v31) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA01,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v32);
      goto LABEL_96;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x18001bde0  mov     [rsp+arg_0], rcx
0x18001bde5  push    rbx
0x18001bde6  push    rsi
0x18001bde7  push    rdi
0x18001bde8  push    r12
0x18001bdea  push    r13
0x18001bdec  push    r14
0x18001bdee  push    r15
0x18001bdf0  sub     rsp, 1A0h
0x18001bdf7  mov     rsi, [rsp+1D8h+arg_0]
0x18001bdff  lea     r15, [rsi+98h]
0x18001be06  movzx   eax, word ptr [r15]
0x18001be0a  mov     [rsp+1D8h+var_1B0], ax
0x18001be0f  mov     r13d, 1
0x18001be15  add     ax, r13w
0x18001be19  cmp     ax, 0Ch; switch 13 cases
0x18001be1d  ja      def_18001BE3D; jumptable 000000018001BE3D default case, case 1
0x18001be23  mov     [rsp+1D8h+var_1A8], r15
0x18001be28  movsx   rax, ax
0x18001be2c  lea     rdx, __ImageBase
0x18001be33  mov     ecx, ds:(jpt_18001BE3D - 180000000h)[rdx+rax*4]
0x18001be3a  add     rcx, rdx
0x18001be3d  jmp     rcx; switch jump
0x18001be3f  xor     edi, edi; jumptable 000000018001BE3D case 4
0x18001be41  jmp     loc_18001C588
0x18001be46  lea     rcx, [rsi+88h]; jumptable 000000018001BE3D case 3
0x18001be4d  xor     edi, edi
0x18001be4f  cmp     [rcx], rdi
0x18001be52  jnz     loc_18001BEEC
0x18001be58  call    ?AreDefaultTextSearchModelsAvailable@ModelPackageManager@@SA_NXZ; ModelPackageManager::AreDefaultTextSearchModelsAvailable(void)
0x18001be5d  test    al, al
0x18001be5f  jnz     loc_18001C550
0x18001be65  lea     rcx, [rsi+0A0h]
0x18001be6c  mov     [rcx], rdi
0x18001be6f  lea     rdx, [rsi+0A8h]
0x18001be76  call    ?WaitAsync@MakeAvailableAsyncWaiter@Indexer@@QEAA?AUIAsyncAction@Foundation@Windows@winrt@@XZ; Indexer::MakeAvailableAsyncWaiter::WaitAsync(void)
0x18001be7b  nop
0x18001be7c  mov     ecx, [rsi+70h]
0x18001be7f  nop
0x18001be80  cmp     ecx, 2
0x18001be83  jnz     short loc_18001BEAF
0x18001be85  lea     rcx, [rsi+160h]
0x18001be8c  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001be91  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001be94  lea     rcx, [rsp+1D8h+pExceptionObject]; this
0x18001be99  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18001be9e  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18001bea5  lea     rcx, [rsp+1D8h+pExceptionObject]; pExceptionObject
0x18001beaa  call    _CxxThrowException_0
0x18001beaf  lea     rcx, [rsi+0B0h]
0x18001beb6  mov     [rcx], rdi
0x18001beb9  mov     [rsi+0B8h], rax
0x18001bec0  mov     [rsi+0C0h], rdi
0x18001bec7  mov     [rsi+0C8h], r13b
0x18001bece  mov     eax, 4
0x18001bed3  mov     [r15], ax
0x18001bed7  mov     rdx, rsi
0x18001beda  call    ??$await_suspend@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUIndexerSemanticSearchServicesImpl@@USemanticIndexStoreOptions@SemanticSearch@Indexer@34@@std@@@?$await_adapter@UIAsyncAction@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUIndexerSemanticSearchServicesImpl@@USemanticIndexStoreOptions@SemanticSearch@Indexer@34@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticSearchServicesImpl &,winrt::Windows::Indexer::SemanticSearch::SemanticIndexStoreOptions>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticSearchServicesImpl &,winrt::Windows::Indexer::SemanticSearch::SemanticIndexStoreOptions>::promise_type>)
0x18001bedf  test    al, al
0x18001bee1  jz      loc_18001C00E
0x18001bee7  jmp     loc_18001C610
0x18001beec  mov     edx, [rsi+90h]
0x18001bef2  call    ?AreSemanticTextSearchModelsAvailable@ModelPackageManager@@SA_NAEBUhstring@winrt@@W4SemanticIndexCreationDisposition@SemanticSearch@Indexer@Windows@3@@Z; ModelPackageManager::AreSemanticTextSearchModelsAvailable(winrt::hstring const &,winrt::Windows::Indexer::SemanticSearch::SemanticIndexCreationDisposition)
0x18001bef7  test    al, al
0x18001bef9  jnz     loc_18001C550
0x18001beff  lea     rcx, [rsi+0F8h]
0x18001bf06  mov     [rcx], rdi
0x18001bf09  lea     rdx, [rsi+100h]
0x18001bf10  call    ?WaitAsync@MakeAvailableAsyncWaiter@Indexer@@QEAA?AUIAsyncAction@Foundation@Windows@winrt@@XZ; Indexer::MakeAvailableAsyncWaiter::WaitAsync(void)
0x18001bf15  nop
0x18001bf16  mov     ecx, [rsi+70h]
0x18001bf19  nop
0x18001bf1a  cmp     ecx, 2
0x18001bf1d  jnz     short loc_18001BF4F
0x18001bf1f  lea     rcx, [rsi+308h]
0x18001bf26  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001bf2b  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001bf2e  lea     rcx, [rsp+1D8h+var_148]; this
0x18001bf36  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18001bf3b  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18001bf42  lea     rcx, [rsp+1D8h+var_148]; pExceptionObject
0x18001bf4a  call    _CxxThrowException_0
0x18001bf4f  lea     rcx, [rsi+108h]
0x18001bf56  mov     [rcx], rdi
0x18001bf59  mov     [rsi+110h], rax
0x18001bf60  mov     [rsi+118h], rdi
0x18001bf67  mov     [rsi+120h], r13b
0x18001bf6e  mov     eax, 8
0x18001bf73  mov     [r15], ax
0x18001bf77  mov     rdx, rsi
0x18001bf7a  call    ??$await_suspend@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUIndexerSemanticSearchServicesImpl@@USemanticIndexStoreOptions@SemanticSearch@Indexer@34@@std@@@?$await_adapter@UIAsyncAction@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUIndexerSemanticSearchServicesImpl@@USemanticIndexStoreOptions@SemanticSearch@Indexer@34@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticSearchServicesImpl &,winrt::Windows::Indexer::SemanticSearch::SemanticIndexStoreOptions>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticSearchServicesImpl &,winrt::Windows::Indexer::SemanticSearch::SemanticIndexStoreOptions>::promise_type>)
0x18001bf7f  test    al, al
0x18001bf81  jz      loc_18001C308
0x18001bf87  jmp     loc_18001C610
0x18001bf8c  mov     rbx, [rsi+0B0h]; jumptable 000000018001BE3D case 6
0x18001bf93  xor     edi, edi
0x18001bf95  test    rbx, rbx
0x18001bf98  jz      short loc_18001BFB2
0x18001bf9a  mov     [rsp+1D8h+var_1A0], rbx
0x18001bf9f  jmp     short loc_18001BFA7
0x18001bfa1  call    cs:__imp__Thrd_yield
0x18001bfa7  mov     rax, rdi
0x18001bfaa  xchg    rax, [rbx]
0x18001bfad  cmp     rax, r13
0x18001bfb0  jz      short loc_18001BFA1
0x18001bfb2  lea     rcx, [rsi+0A8h]
0x18001bfb9  mov     rax, [rcx]
0x18001bfbc  mov     [rsp+1D8h+arg_18], rax
0x18001bfc4  test    rax, rax
0x18001bfc7  jz      short loc_18001BFCF
0x18001bfc9  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18001bfce  nop
0x18001bfcf  mov     rcx, [rsi+0A0h]; hEvent
0x18001bfd6  mov     [rsp+1D8h+arg_10], rcx
0x18001bfde  test    rcx, rcx
0x18001bfe1  jz      short loc_18001C007
0x18001bfe3  call    cs:__imp_SetEvent
0x18001bfe9  mov     rcx, [rsp+1D8h]; this
0x18001bff1  test    eax, eax
0x18001bff3  jnz     short loc_18001C007
0x18001bff5  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001bffc  mov     edx, 0A01h; void *
0x18001c001  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001c007  jmp     loc_18001C588
0x18001c00c  xor     edi, edi; jumptable 000000018001BE3D case 5
0x18001c00e  lea     rbx, [rsi+0B0h]
0x18001c015  mov     rcx, rbx
0x18001c018  call    ?await_resume@?$await_adapter@UIAsyncAction@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_resume(void)
0x18001c01d  nop
0x18001c01e  mov     rbx, [rbx]
0x18001c021  test    rbx, rbx
0x18001c024  jz      short loc_18001C03E
0x18001c026  mov     [rsp+1D8h+var_1A0], rbx
0x18001c02b  jmp     short loc_18001C033
0x18001c02d  call    cs:__imp__Thrd_yield
0x18001c033  mov     rax, rdi
0x18001c036  xchg    rax, [rbx]
0x18001c039  cmp     rax, r13
0x18001c03c  jz      short loc_18001C02D
0x18001c03e  lea     rcx, [rsi+0A8h]
0x18001c045  mov     rax, [rcx]
0x18001c048  mov     [rsp+1D8h+arg_18], rax
0x18001c050  test    rax, rax
0x18001c053  jz      short loc_18001C05A
0x18001c055  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18001c05a  mov     ecx, 150h; Size
0x18001c05f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c064  mov     r14, rax
0x18001c067  mov     [rsi+178h], rax
0x18001c06e  mov     [rsp+1D8h+arg_8], rax
0x18001c076  lea     rax, ModelPackageManager__MakeDefaultSemanticTextSearchModelsAvailableAsync$_DestroyCoro$2
0x18001c07d  mov     [r14+8], rax
0x18001c081  mov     [rsp+1D8h+arg_8], r14
0x18001c089  lea     rax, ModelPackageManager__MakeDefaultSemanticTextSearchModelsAvailableAsync$_ResumeCoro$1
0x18001c090  mov     [r14], rax
0x18001c093  mov     [rsp+1D8h+arg_8], r14
0x18001c09b  mov     dword ptr [r14+7Ch], 10002h
0x18001c0a3  mov     [rsp+1D8h+arg_8], r14
0x18001c0ab  xor     edx, edx; Val
0x18001c0ad  lea     r8d, [rdx+68h]; Size
0x18001c0b1  lea     rcx, [r14+10h]; void *
0x18001c0b5  call    memset_0
0x18001c0ba  lea     rcx, [r14+10h]
0x18001c0be  call    ??0promise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@Uhstring@4@W4SemanticIndexCreationDisposition@SemanticSearch@Indexer@34@@std@@QEAA@XZ; std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::hstring,winrt::Windows::Indexer::SemanticSearch::SemanticIndexCreationDisposition>::promise_type::promise_type(void)
0x18001c0c3  nop
0x18001c0c4  lea     rcx, [r14+20h]
0x18001c0c8  lea     rbx, [rsi+0D0h]
0x18001c0cf  mov     [rbx], rcx
0x18001c0d2  test    rcx, rcx
0x18001c0d5  jz      short loc_18001C0E4
0x18001c0d7  mov     rax, [rcx]
0x18001c0da  mov     rax, [rax+8]
0x18001c0de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0e3  nop
0x18001c0e4  mov     [rsp+1D8h+arg_8], r14
0x18001c0ec  xor     eax, eax
0x18001c0ee  mov     [r14+78h], al
0x18001c0f2  mov     [rsp+1D8h+arg_8], r14
0x18001c0fa  mov     rcx, r14
0x18001c0fd  call    ModelPackageManager__MakeDefaultSemanticTextSearchModelsAvailableAsync$_ResumeCoro$1
0x18001c102  nop
0x18001c103  mov     eax, [rsi+70h]
0x18001c106  nop
0x18001c107  cmp     eax, 2
0x18001c10a  jnz     short loc_18001C13C
0x18001c10c  lea     rcx, [rsi+2F0h]
0x18001c113  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001c118  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001c11b  lea     rcx, [rsp+1D8h+var_130]; this
0x18001c123  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18001c128  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18001c12f  lea     rcx, [rsp+1D8h+var_130]; pExceptionObject
0x18001c137  call    _CxxThrowException_0
0x18001c13c  lea     rcx, [rsi+0D8h]
0x18001c143  mov     [rcx], rdi
0x18001c146  mov     [rsi+0E0h], rbx
0x18001c14d  mov     qword ptr [rsi+0E8h], 0
0x18001c158  mov     [rsi+0F0h], r13b
0x18001c15f  mov     eax, 6
0x18001c164  mov     [r15], ax
0x18001c168  mov     rdx, rsi
0x18001c16b  call    ??$await_suspend@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUIndexerSemanticSearchServicesImpl@@USemanticIndexStoreOptions@SemanticSearch@Indexer@34@@std@@@?$await_adapter@UIAsyncAction@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUIndexerSemanticSearchServicesImpl@@USemanticIndexStoreOptions@SemanticSearch@Indexer@34@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticSearchServicesImpl &,winrt::Windows::Indexer::SemanticSearch::SemanticIndexStoreOptions>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticSearchServicesImpl &,winrt::Windows::Indexer::SemanticSearch::SemanticIndexStoreOptions>::promise_type>)
0x18001c170  test    al, al
0x18001c172  jz      loc_18001C1FC
0x18001c178  jmp     loc_18001C610
0x18001c17d  mov     rbx, [rsi+0D8h]; jumptable 000000018001BE3D case 8
0x18001c184  xor     edi, edi
0x18001c186  test    rbx, rbx
0x18001c189  jz      short loc_18001C1A3
0x18001c18b  mov     [rsp+1D8h+var_180], rbx
0x18001c190  jmp     short loc_18001C198
0x18001c192  call    cs:__imp__Thrd_yield
0x18001c198  mov     rax, rdi
0x18001c19b  xchg    rax, [rbx]
0x18001c19e  cmp     rax, r13
0x18001c1a1  jz      short loc_18001C192
0x18001c1a3  lea     rcx, [rsi+0D0h]
0x18001c1aa  mov     rax, [rcx]
0x18001c1ad  mov     [rsp+1D8h+var_1B8], rax
0x18001c1b2  test    rax, rax
0x18001c1b5  jz      short loc_18001C1BD
0x18001c1b7  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18001c1bc  nop
0x18001c1bd  mov     rcx, [rsi+0A0h]; hEvent
0x18001c1c4  mov     [rsp+1D8h+arg_10], rcx
0x18001c1cc  test    rcx, rcx
0x18001c1cf  jz      short loc_18001C1F5
0x18001c1d1  call    cs:__imp_SetEvent
0x18001c1d7  mov     rcx, [rsp+1D8h]; this
0x18001c1df  test    eax, eax
0x18001c1e1  jnz     short loc_18001C1F5
0x18001c1e3  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001c1ea  mov     edx, 0A01h; void *
0x18001c1ef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001c1f5  jmp     loc_18001C588
0x18001c1fa  xor     edi, edi; jumptable 000000018001BE3D case 7
0x18001c1fc  lea     rbx, [rsi+0D8h]
0x18001c203  mov     rcx, rbx
0x18001c206  call    ?await_resume@?$await_adapter@UIAsyncAction@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_resume(void)
0x18001c20b  nop
0x18001c20c  mov     rbx, [rbx]
0x18001c20f  test    rbx, rbx
0x18001c212  jz      short loc_18001C22C
0x18001c214  mov     [rsp+1D8h+var_180], rbx
0x18001c219  jmp     short loc_18001C221
0x18001c21b  call    cs:__imp__Thrd_yield
0x18001c221  mov     rax, rdi
0x18001c224  xchg    rax, [rbx]
0x18001c227  cmp     rax, r13
0x18001c22a  jz      short loc_18001C21B
0x18001c22c  lea     rcx, [rsi+0D0h]
0x18001c233  mov     rax, [rcx]
0x18001c236  mov     [rsp+1D8h+var_1B8], rax
0x18001c23b  test    rax, rax
0x18001c23e  jz      short loc_18001C246
0x18001c240  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18001c245  nop
0x18001c246  mov     rcx, [rsi+0A0h]; hEvent
0x18001c24d  mov     [rsp+1D8h+arg_10], rcx
0x18001c255  test    rcx, rcx
0x18001c258  jz      loc_18001C550
0x18001c25e  call    cs:__imp_SetEvent
0x18001c264  mov     rcx, [rsp+1D8h]; this
0x18001c26c  test    eax, eax
0x18001c26e  jnz     loc_18001C550
0x18001c274  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001c27b  mov     edx, 0A01h; void *
0x18001c280  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001c286  mov     rbx, [rsi+108h]; jumptable 000000018001BE3D case 10
0x18001c28d  xor     edi, edi
0x18001c28f  test    rbx, rbx
0x18001c292  jz      short loc_18001C2AC
0x18001c294  mov     [rsp+1D8h+var_180], rbx
0x18001c299  jmp     short loc_18001C2A1
0x18001c29b  call    cs:__imp__Thrd_yield
0x18001c2a1  mov     rax, rdi
0x18001c2a4  xchg    rax, [rbx]
0x18001c2a7  cmp     rax, r13
0x18001c2aa  jz      short loc_18001C29B
0x18001c2ac  lea     rcx, [rsi+100h]
0x18001c2b3  mov     rax, [rcx]
0x18001c2b6  mov     [rsp+1D8h+arg_18], rax
0x18001c2be  test    rax, rax
0x18001c2c1  jz      short loc_18001C2C9
0x18001c2c3  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18001c2c8  nop
0x18001c2c9  mov     rcx, [rsi+0F8h]; hEvent
0x18001c2d0  mov     [rsp+1D8h+arg_10], rcx
0x18001c2d8  test    rcx, rcx
0x18001c2db  jz      short loc_18001C301
0x18001c2dd  call    cs:__imp_SetEvent
0x18001c2e3  mov     rcx, [rsp+1D8h]; this
0x18001c2eb  test    eax, eax
0x18001c2ed  jnz     short loc_18001C301
0x18001c2ef  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001c2f6  mov     edx, 0A01h; void *
0x18001c2fb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001c301  jmp     loc_18001C588
0x18001c306  xor     edi, edi; jumptable 000000018001BE3D case 9
0x18001c308  lea     rbx, [rsi+108h]
  ... truncated ...
```
