# DependencyManager::EnsureSemanticImageSearchModelsReadyAsync$_ResumeCoro$1

- ea: `0x18001b430`
- end: `0x18001bcb4`
- name: `DependencyManager::EnsureSemanticImageSearchModelsReadyAsync$_ResumeCoro$1`
- size: `2180`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001b410`
- `0x18001bcc0`

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
- `0x18001b430`
- `0x18001dc68`
- `0x18001dd84`
- `0x18001de54`
- `0x180074e4c`
- `0x180075748`
- `0x1800758e4`
- `0x180075dd0`
- `0x180077448`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001bc42`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001bc42`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b63c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b82a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b8b7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b936`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001bafc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001bb85`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b63c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b82a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b8b7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b936`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001bafc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001bb85`
- `msvcp_win!_Thrd_yield` at `0x18001b5fa`
- `msvcp_win!_Thrd_yield` at `0x18001b686`
- `msvcp_win!_Thrd_yield` at `0x18001b7eb`
- `msvcp_win!_Thrd_yield` at `0x18001b874`
- `msvcp_win!_Thrd_yield` at `0x18001b8f4`
- `msvcp_win!_Thrd_yield` at `0x18001b980`
- `msvcp_win!_Thrd_yield` at `0x18001babd`
- `msvcp_win!_Thrd_yield` at `0x18001bb46`
- `msvcp_win!_Thrd_yield` at `0x18001b5fa`
- `msvcp_win!_Thrd_yield` at `0x18001b686`
- `msvcp_win!_Thrd_yield` at `0x18001b7eb`
- `msvcp_win!_Thrd_yield` at `0x18001b874`
- `msvcp_win!_Thrd_yield` at `0x18001b8f4`
- `msvcp_win!_Thrd_yield` at `0x18001b980`
- `msvcp_win!_Thrd_yield` at `0x18001babd`
- `msvcp_win!_Thrd_yield` at `0x18001bb46`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001bc01`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001bc01`

## string_xrefs

- `0x18001b64e`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18001b83c`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18001b8cd`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18001b948`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18001bb0e`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18001bb97`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall DependencyManager::EnsureSemanticImageSearchModelsReadyAsync__ResumeCoro_1(__int64 a1)
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
  void (__fastcall **v11)(__int64); // r14
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
  __int64 SemanticImageSearchModelsAvailableAsync; // rax
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
      goto LABEL_97;
    case 2:
      if ( !*(_QWORD *)(a1 + 136) )
      {
        if ( !ModelPackageManager::IsDefaultImageTextQueryGeneratorAvailable()
          || !ModelPackageManager::IsDefaultImageEmbeddingsGeneratorAvailable() )
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
LABEL_23:
          winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_resume(a1 + 176);
          v10 = *(volatile __int64 **)(a1 + 176);
          if ( v10 )
          {
            while ( _InterlockedExchange64(v10, 0) == 1 )
              _Thrd_yield();
          }
          if ( *(_QWORD *)(a1 + 168) )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 168);
          v11 = (void (__fastcall **)(__int64))operator new(0x220u);
          *(_QWORD *)(a1 + 376) = v11;
          v11[1] = (void (__fastcall *)(__int64))ModelPackageManager::MakeDefaultSemanticImageSearchModelsAvailableAsync__DestroyCoro_2;
          *v11 = ModelPackageManager::MakeDefaultSemanticImageSearchModelsAvailableAsync__ResumeCoro_1;
          *((_DWORD *)v11 + 31) = 65538;
          memset_0(v11 + 2, 0, 0x68u);
          std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::hstring,enum winrt::Windows::Indexer::SemanticSearch::SemanticIndexCreationDisposition>::promise_type::promise_type((__int64)(v11 + 2));
          *(_QWORD *)(a1 + 208) = v11 + 4;
          if ( v11 != (void (__fastcall **)(__int64))-32LL )
            (*((void (__fastcall **)(_QWORD *))v11[4] + 1))(v11 + 4);
          *((_BYTE *)v11 + 120) = 0;
          ModelPackageManager::MakeDefaultSemanticImageSearchModelsAvailableAsync__ResumeCoro_1((__int64)v11);
          if ( *(_DWORD *)(a1 + 112) == 2 )
          {
            v12 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 960);
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
LABEL_44:
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
        goto LABEL_96;
      }
      if ( (unsigned __int8)ModelPackageManager::AreSemanticImageSearchModelsAvailable(
                              a1 + 136,
                              *(unsigned int *)(a1 + 144)) )
        goto LABEL_96;
      *(_QWORD *)(a1 + 248) = 0;
      v5 = Indexer::MakeAvailableAsyncWaiter::WaitAsync(a1 + 248, a1 + 256);
      if ( *(_DWORD *)(a1 + 112) == 2 )
      {
        v6 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 984);
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
LABEL_62:
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
        goto LABEL_69;
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
LABEL_69:
          v25 = 0;
        }
      }
      else
      {
        _InterlockedIncrement((volatile signed __int32 *)v25 + 6);
      }
      *(_QWORD *)(a1 + 296) = v25;
      SemanticImageSearchModelsAvailableAsync = ModelPackageManager::MakeSemanticImageSearchModelsAvailableAsync(
                                                  a1 + 304,
                                                  a1 + 296,
                                                  v24);
      if ( *(_DWORD *)(a1 + 112) == 2 )
      {
        v29 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 1008);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v42, v29);
        throw (winrt::hresult_canceled *)v42;
      }
      *(_QWORD *)(a1 + 312) = 0;
      *(_QWORD *)(a1 + 320) = SemanticImageSearchModelsAvailableAsync;
      *(_QWORD *)(a1 + 328) = 0;
      *(_BYTE *)(a1 + 336) = 1;
      *v2 = 10;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticSearchServicesImpl &,winrt::Windows::Indexer::SemanticSearch::SemanticIndexStoreOptions>::promise_type>(
                              (__int64 *)(a1 + 312),
                              a1) )
        return;
LABEL_87:
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
LABEL_96:
      *(_QWORD *)(a1 + 344) = a1 + 16;
      *v2 = 0;
      *(_QWORD *)a1 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticStore &,enum winrt::Windows::Indexer::SemanticSearch::ModelKind>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend() )
      {
LABEL_97:
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
          operator delete((void *)a1, 0x410u);
      }
      return;
    case 4:
      goto LABEL_23;
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
      goto LABEL_97;
    case 6:
      goto LABEL_44;
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
      goto LABEL_97;
    case 8:
      goto LABEL_62;
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
      goto LABEL_97;
    case 0xA:
      goto LABEL_87;
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
      goto LABEL_97;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x18001b430  mov     [rsp+arg_0], rcx
0x18001b435  push    rbx
0x18001b436  push    rsi
0x18001b437  push    rdi
0x18001b438  push    r12
0x18001b43a  push    r13
0x18001b43c  push    r14
0x18001b43e  push    r15
0x18001b440  sub     rsp, 1A0h
0x18001b447  mov     rsi, [rsp+1D8h+arg_0]
0x18001b44f  lea     r15, [rsi+98h]
0x18001b456  movzx   eax, word ptr [r15]
0x18001b45a  mov     [rsp+1D8h+var_1B0], ax
0x18001b45f  mov     r13d, 1
0x18001b465  add     ax, r13w
0x18001b469  cmp     ax, 0Ch; switch 13 cases
0x18001b46d  ja      def_18001B48D; jumptable 000000018001B48D default case, case 1
0x18001b473  mov     [rsp+1D8h+var_1A8], r15
0x18001b478  movsx   rax, ax
0x18001b47c  lea     rdx, __ImageBase
0x18001b483  mov     ecx, ds:(jpt_18001B48D - 180000000h)[rdx+rax*4]
0x18001b48a  add     rcx, rdx
0x18001b48d  jmp     rcx; switch jump
0x18001b48f  xor     edi, edi; jumptable 000000018001B48D case 4
0x18001b491  jmp     loc_18001BBE1
0x18001b496  lea     rcx, [rsi+88h]; jumptable 000000018001B48D case 3
0x18001b49d  xor     edi, edi
0x18001b49f  cmp     [rcx], rdi
0x18001b4a2  jnz     loc_18001B545
0x18001b4a8  call    ?IsDefaultImageTextQueryGeneratorAvailable@ModelPackageManager@@CA_NXZ; ModelPackageManager::IsDefaultImageTextQueryGeneratorAvailable(void)
0x18001b4ad  test    al, al
0x18001b4af  jz      short loc_18001B4BE
0x18001b4b1  call    ?IsDefaultImageEmbeddingsGeneratorAvailable@ModelPackageManager@@CA_NXZ; ModelPackageManager::IsDefaultImageEmbeddingsGeneratorAvailable(void)
0x18001b4b6  test    al, al
0x18001b4b8  jnz     loc_18001BBA9
0x18001b4be  lea     rcx, [rsi+0A0h]
0x18001b4c5  mov     [rcx], rdi
0x18001b4c8  lea     rdx, [rsi+0A8h]
0x18001b4cf  call    ?WaitAsync@MakeAvailableAsyncWaiter@Indexer@@QEAA?AUIAsyncAction@Foundation@Windows@winrt@@XZ; Indexer::MakeAvailableAsyncWaiter::WaitAsync(void)
0x18001b4d4  nop
0x18001b4d5  mov     ecx, [rsi+70h]
0x18001b4d8  nop
0x18001b4d9  cmp     ecx, 2
0x18001b4dc  jnz     short loc_18001B508
0x18001b4de  lea     rcx, [rsi+160h]
0x18001b4e5  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001b4ea  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001b4ed  lea     rcx, [rsp+1D8h+pExceptionObject]; this
0x18001b4f2  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18001b4f7  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18001b4fe  lea     rcx, [rsp+1D8h+pExceptionObject]; pExceptionObject
0x18001b503  call    _CxxThrowException_0
0x18001b508  lea     rcx, [rsi+0B0h]
0x18001b50f  mov     [rcx], rdi
0x18001b512  mov     [rsi+0B8h], rax
0x18001b519  mov     [rsi+0C0h], rdi
0x18001b520  mov     [rsi+0C8h], r13b
0x18001b527  mov     eax, 4
0x18001b52c  mov     [r15], ax
0x18001b530  mov     rdx, rsi
0x18001b533  call    ??$await_suspend@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUIndexerSemanticSearchServicesImpl@@USemanticIndexStoreOptions@SemanticSearch@Indexer@34@@std@@@?$await_adapter@UIAsyncAction@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUIndexerSemanticSearchServicesImpl@@USemanticIndexStoreOptions@SemanticSearch@Indexer@34@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticSearchServicesImpl &,winrt::Windows::Indexer::SemanticSearch::SemanticIndexStoreOptions>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticSearchServicesImpl &,winrt::Windows::Indexer::SemanticSearch::SemanticIndexStoreOptions>::promise_type>)
0x18001b538  test    al, al
0x18001b53a  jz      loc_18001B667
0x18001b540  jmp     loc_18001BC69
0x18001b545  mov     edx, [rsi+90h]
0x18001b54b  call    ?AreSemanticImageSearchModelsAvailable@ModelPackageManager@@SA_NAEBUhstring@winrt@@W4SemanticIndexCreationDisposition@SemanticSearch@Indexer@Windows@3@@Z; ModelPackageManager::AreSemanticImageSearchModelsAvailable(winrt::hstring const &,winrt::Windows::Indexer::SemanticSearch::SemanticIndexCreationDisposition)
0x18001b550  test    al, al
0x18001b552  jnz     loc_18001BBA9
0x18001b558  lea     rcx, [rsi+0F8h]
0x18001b55f  mov     [rcx], rdi
0x18001b562  lea     rdx, [rsi+100h]
0x18001b569  call    ?WaitAsync@MakeAvailableAsyncWaiter@Indexer@@QEAA?AUIAsyncAction@Foundation@Windows@winrt@@XZ; Indexer::MakeAvailableAsyncWaiter::WaitAsync(void)
0x18001b56e  nop
0x18001b56f  mov     ecx, [rsi+70h]
0x18001b572  nop
0x18001b573  cmp     ecx, 2
0x18001b576  jnz     short loc_18001B5A8
0x18001b578  lea     rcx, [rsi+3D8h]
0x18001b57f  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001b584  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001b587  lea     rcx, [rsp+1D8h+var_148]; this
0x18001b58f  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18001b594  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18001b59b  lea     rcx, [rsp+1D8h+var_148]; pExceptionObject
0x18001b5a3  call    _CxxThrowException_0
0x18001b5a8  lea     rcx, [rsi+108h]
0x18001b5af  mov     [rcx], rdi
0x18001b5b2  mov     [rsi+110h], rax
0x18001b5b9  mov     [rsi+118h], rdi
0x18001b5c0  mov     [rsi+120h], r13b
0x18001b5c7  mov     eax, 8
0x18001b5cc  mov     [r15], ax
0x18001b5d0  mov     rdx, rsi
0x18001b5d3  call    ??$await_suspend@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUIndexerSemanticSearchServicesImpl@@USemanticIndexStoreOptions@SemanticSearch@Indexer@34@@std@@@?$await_adapter@UIAsyncAction@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUIndexerSemanticSearchServicesImpl@@USemanticIndexStoreOptions@SemanticSearch@Indexer@34@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticSearchServicesImpl &,winrt::Windows::Indexer::SemanticSearch::SemanticIndexStoreOptions>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticSearchServicesImpl &,winrt::Windows::Indexer::SemanticSearch::SemanticIndexStoreOptions>::promise_type>)
0x18001b5d8  test    al, al
0x18001b5da  jz      loc_18001B961
0x18001b5e0  jmp     loc_18001BC69
0x18001b5e5  mov     rbx, [rsi+0B0h]; jumptable 000000018001B48D case 6
0x18001b5ec  xor     edi, edi
0x18001b5ee  test    rbx, rbx
0x18001b5f1  jz      short loc_18001B60B
0x18001b5f3  mov     [rsp+1D8h+var_1A0], rbx
0x18001b5f8  jmp     short loc_18001B600
0x18001b5fa  call    cs:__imp__Thrd_yield
0x18001b600  mov     rax, rdi
0x18001b603  xchg    rax, [rbx]
0x18001b606  cmp     rax, r13
0x18001b609  jz      short loc_18001B5FA
0x18001b60b  lea     rcx, [rsi+0A8h]
0x18001b612  mov     rax, [rcx]
0x18001b615  mov     [rsp+1D8h+arg_18], rax
0x18001b61d  test    rax, rax
0x18001b620  jz      short loc_18001B628
0x18001b622  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18001b627  nop
0x18001b628  mov     rcx, [rsi+0A0h]; hEvent
0x18001b62f  mov     [rsp+1D8h+arg_10], rcx
0x18001b637  test    rcx, rcx
0x18001b63a  jz      short loc_18001B660
0x18001b63c  call    cs:__imp_SetEvent
0x18001b642  mov     rcx, [rsp+1D8h]; this
0x18001b64a  test    eax, eax
0x18001b64c  jnz     short loc_18001B660
0x18001b64e  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001b655  mov     edx, 0A01h; void *
0x18001b65a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001b660  jmp     loc_18001BBE1
0x18001b665  xor     edi, edi; jumptable 000000018001B48D case 5
0x18001b667  lea     rbx, [rsi+0B0h]
0x18001b66e  mov     rcx, rbx
0x18001b671  call    ?await_resume@?$await_adapter@UIAsyncAction@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_resume(void)
0x18001b676  nop
0x18001b677  mov     rbx, [rbx]
0x18001b67a  test    rbx, rbx
0x18001b67d  jz      short loc_18001B697
0x18001b67f  mov     [rsp+1D8h+var_1A0], rbx
0x18001b684  jmp     short loc_18001B68C
0x18001b686  call    cs:__imp__Thrd_yield
0x18001b68c  mov     rax, rdi
0x18001b68f  xchg    rax, [rbx]
0x18001b692  cmp     rax, r13
0x18001b695  jz      short loc_18001B686
0x18001b697  lea     rcx, [rsi+0A8h]
0x18001b69e  mov     rax, [rcx]
0x18001b6a1  mov     [rsp+1D8h+arg_18], rax
0x18001b6a9  test    rax, rax
0x18001b6ac  jz      short loc_18001B6B3
0x18001b6ae  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18001b6b3  mov     ecx, 220h; Size
0x18001b6b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b6bd  mov     r14, rax
0x18001b6c0  mov     [rsi+178h], rax
0x18001b6c7  mov     [rsp+1D8h+arg_8], rax
0x18001b6cf  lea     rax, ModelPackageManager__MakeDefaultSemanticImageSearchModelsAvailableAsync$_DestroyCoro$2
0x18001b6d6  mov     [r14+8], rax
0x18001b6da  mov     [rsp+1D8h+arg_8], r14
0x18001b6e2  lea     rax, ModelPackageManager__MakeDefaultSemanticImageSearchModelsAvailableAsync$_ResumeCoro$1
0x18001b6e9  mov     [r14], rax
0x18001b6ec  mov     [rsp+1D8h+arg_8], r14
0x18001b6f4  mov     dword ptr [r14+7Ch], 10002h
0x18001b6fc  mov     [rsp+1D8h+arg_8], r14
0x18001b704  xor     edx, edx; Val
0x18001b706  lea     r8d, [rdx+68h]; Size
0x18001b70a  lea     rcx, [r14+10h]; void *
0x18001b70e  call    memset_0
0x18001b713  lea     rcx, [r14+10h]
0x18001b717  call    ??0promise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@Uhstring@4@W4SemanticIndexCreationDisposition@SemanticSearch@Indexer@34@@std@@QEAA@XZ; std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::hstring,winrt::Windows::Indexer::SemanticSearch::SemanticIndexCreationDisposition>::promise_type::promise_type(void)
0x18001b71c  nop
0x18001b71d  lea     rcx, [r14+20h]
0x18001b721  lea     rbx, [rsi+0D0h]
0x18001b728  mov     [rbx], rcx
0x18001b72b  test    rcx, rcx
0x18001b72e  jz      short loc_18001B73D
0x18001b730  mov     rax, [rcx]
0x18001b733  mov     rax, [rax+8]
0x18001b737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b73c  nop
0x18001b73d  mov     [rsp+1D8h+arg_8], r14
0x18001b745  xor     eax, eax
0x18001b747  mov     [r14+78h], al
0x18001b74b  mov     [rsp+1D8h+arg_8], r14
0x18001b753  mov     rcx, r14
0x18001b756  call    ModelPackageManager__MakeDefaultSemanticImageSearchModelsAvailableAsync$_ResumeCoro$1
0x18001b75b  nop
0x18001b75c  mov     eax, [rsi+70h]
0x18001b75f  nop
0x18001b760  cmp     eax, 2
0x18001b763  jnz     short loc_18001B795
0x18001b765  lea     rcx, [rsi+3C0h]
0x18001b76c  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001b771  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001b774  lea     rcx, [rsp+1D8h+var_130]; this
0x18001b77c  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18001b781  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18001b788  lea     rcx, [rsp+1D8h+var_130]; pExceptionObject
0x18001b790  call    _CxxThrowException_0
0x18001b795  lea     rcx, [rsi+0D8h]
0x18001b79c  mov     [rcx], rdi
0x18001b79f  mov     [rsi+0E0h], rbx
0x18001b7a6  mov     qword ptr [rsi+0E8h], 0
0x18001b7b1  mov     [rsi+0F0h], r13b
0x18001b7b8  mov     eax, 6
0x18001b7bd  mov     [r15], ax
0x18001b7c1  mov     rdx, rsi
0x18001b7c4  call    ??$await_suspend@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUIndexerSemanticSearchServicesImpl@@USemanticIndexStoreOptions@SemanticSearch@Indexer@34@@std@@@?$await_adapter@UIAsyncAction@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUIndexerSemanticSearchServicesImpl@@USemanticIndexStoreOptions@SemanticSearch@Indexer@34@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticSearchServicesImpl &,winrt::Windows::Indexer::SemanticSearch::SemanticIndexStoreOptions>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticSearchServicesImpl &,winrt::Windows::Indexer::SemanticSearch::SemanticIndexStoreOptions>::promise_type>)
0x18001b7c9  test    al, al
0x18001b7cb  jz      loc_18001B855
0x18001b7d1  jmp     loc_18001BC69
0x18001b7d6  mov     rbx, [rsi+0D8h]; jumptable 000000018001B48D case 8
0x18001b7dd  xor     edi, edi
0x18001b7df  test    rbx, rbx
0x18001b7e2  jz      short loc_18001B7FC
0x18001b7e4  mov     [rsp+1D8h+var_180], rbx
0x18001b7e9  jmp     short loc_18001B7F1
0x18001b7eb  call    cs:__imp__Thrd_yield
0x18001b7f1  mov     rax, rdi
0x18001b7f4  xchg    rax, [rbx]
0x18001b7f7  cmp     rax, r13
0x18001b7fa  jz      short loc_18001B7EB
0x18001b7fc  lea     rcx, [rsi+0D0h]
0x18001b803  mov     rax, [rcx]
0x18001b806  mov     [rsp+1D8h+var_1B8], rax
0x18001b80b  test    rax, rax
0x18001b80e  jz      short loc_18001B816
0x18001b810  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18001b815  nop
0x18001b816  mov     rcx, [rsi+0A0h]; hEvent
0x18001b81d  mov     [rsp+1D8h+arg_10], rcx
0x18001b825  test    rcx, rcx
0x18001b828  jz      short loc_18001B84E
0x18001b82a  call    cs:__imp_SetEvent
0x18001b830  mov     rcx, [rsp+1D8h]; this
0x18001b838  test    eax, eax
0x18001b83a  jnz     short loc_18001B84E
0x18001b83c  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001b843  mov     edx, 0A01h; void *
0x18001b848  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001b84e  jmp     loc_18001BBE1
0x18001b853  xor     edi, edi; jumptable 000000018001B48D case 7
0x18001b855  lea     rbx, [rsi+0D8h]
0x18001b85c  mov     rcx, rbx
0x18001b85f  call    ?await_resume@?$await_adapter@UIAsyncAction@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_resume(void)
0x18001b864  nop
0x18001b865  mov     rbx, [rbx]
0x18001b868  test    rbx, rbx
0x18001b86b  jz      short loc_18001B885
0x18001b86d  mov     [rsp+1D8h+var_180], rbx
0x18001b872  jmp     short loc_18001B87A
0x18001b874  call    cs:__imp__Thrd_yield
0x18001b87a  mov     rax, rdi
0x18001b87d  xchg    rax, [rbx]
0x18001b880  cmp     rax, r13
0x18001b883  jz      short loc_18001B874
0x18001b885  lea     rcx, [rsi+0D0h]
0x18001b88c  mov     rax, [rcx]
0x18001b88f  mov     [rsp+1D8h+var_1B8], rax
0x18001b894  test    rax, rax
0x18001b897  jz      short loc_18001B89F
0x18001b899  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18001b89e  nop
0x18001b89f  mov     rcx, [rsi+0A0h]; hEvent
0x18001b8a6  mov     [rsp+1D8h+arg_10], rcx
0x18001b8ae  test    rcx, rcx
0x18001b8b1  jz      loc_18001BBA9
0x18001b8b7  call    cs:__imp_SetEvent
0x18001b8bd  mov     rcx, [rsp+1D8h]; this
0x18001b8c5  test    eax, eax
0x18001b8c7  jnz     loc_18001BBA9
0x18001b8cd  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001b8d4  mov     edx, 0A01h; void *
0x18001b8d9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001b8df  mov     rbx, [rsi+108h]; jumptable 000000018001B48D case 10
0x18001b8e6  xor     edi, edi
0x18001b8e8  test    rbx, rbx
0x18001b8eb  jz      short loc_18001B905
0x18001b8ed  mov     [rsp+1D8h+var_180], rbx
0x18001b8f2  jmp     short loc_18001B8FA
0x18001b8f4  call    cs:__imp__Thrd_yield
0x18001b8fa  mov     rax, rdi
0x18001b8fd  xchg    rax, [rbx]
0x18001b900  cmp     rax, r13
0x18001b903  jz      short loc_18001B8F4
0x18001b905  lea     rcx, [rsi+100h]
0x18001b90c  mov     rax, [rcx]
0x18001b90f  mov     [rsp+1D8h+arg_18], rax
0x18001b917  test    rax, rax
0x18001b91a  jz      short loc_18001B922
0x18001b91c  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18001b921  nop
0x18001b922  mov     rcx, [rsi+0F8h]; hEvent
0x18001b929  mov     [rsp+1D8h+arg_10], rcx
0x18001b931  test    rcx, rcx
0x18001b934  jz      short loc_18001B95A
0x18001b936  call    cs:__imp_SetEvent
0x18001b93c  mov     rcx, [rsp+1D8h]; this
0x18001b944  test    eax, eax
0x18001b946  jnz     short loc_18001B95A
0x18001b948  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001b94f  mov     edx, 0A01h; void *
0x18001b954  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
  ... truncated ...
```
