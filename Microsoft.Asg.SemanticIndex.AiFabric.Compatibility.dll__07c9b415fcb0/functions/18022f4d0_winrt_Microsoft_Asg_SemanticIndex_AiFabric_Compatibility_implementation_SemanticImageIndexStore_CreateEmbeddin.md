# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::CreateEmbeddingsGeneratorForOptionsAsync$_ResumeCoro$1

- ea: `0x18022f4d0`
- end: `0x18022fb1c`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::CreateEmbeddingsGeneratorForOptionsAsync$_ResumeCoro$1`
- size: `1612`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001c7a0`
- `0x18022f4c0`

## callees

- `0x180003bd0`
- `0x180003fb0`
- `0x180004510`
- `0x18000d230`
- `0x18000d4b0`
- `0x18001b1f0`
- `0x18001b3c0`
- `0x18001bc40`
- `0x18001c8e0`
- `0x18001fd80`
- `0x180020e60`
- `0x180047120`
- `0x180047520`
- `0x1800475c0`
- `0x18006cd50`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180206a58`
- `0x18022f4d0`
- `0x180242120`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18022f5b6`
- `KERNEL32!CloseHandle` at `0x18022f771`
- `KERNEL32!CloseHandle` at `0x18022f78f`
- `KERNEL32!CloseHandle` at `0x18022f8d2`
- `KERNEL32!CloseHandle` at `0x18022fa5e`
- `KERNEL32!CloseHandle` at `0x18022f5b6`
- `KERNEL32!CloseHandle` at `0x18022f771`
- `KERNEL32!CloseHandle` at `0x18022f78f`
- `KERNEL32!CloseHandle` at `0x18022f8d2`
- `KERNEL32!CloseHandle` at `0x18022fa5e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18022f759`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18022f759`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18022f71b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18022f71b`

## string_xrefs

- `0x18022f553`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18022f7ab`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18022f99f`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticImageIndexStore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::CreateEmbeddingsGeneratorForOptionsAsync__ResumeCoro_1(
        _WORD *a1)
{
  __int64 v2; // rcx
  void *v3; // rcx
  _QWORD *v4; // r14
  __int128 v5; // xmm0
  __int64 *v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rax
  _QWORD *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  void *v12; // rdi
  _WORD *v13; // rdi
  void *v14; // r14
  unsigned int v15; // r8d
  const char *v16; // r9
  wil::details::in1diag3 *v17; // rcx
  void *v18; // rcx
  volatile __int64 *v19; // rdi
  void *v20; // rcx
  char v21; // r14
  volatile __int64 *v22; // rdi
  unsigned int *v23; // rax
  _QWORD *v24; // r14
  _QWORD *v25; // rdi
  void *v26; // rcx
  _BYTE pExceptionObject[24]; // [rsp+48h] [rbp-100h] BYREF
  _BYTE v28[24]; // [rsp+60h] [rbp-E8h] BYREF
  _BYTE v29[24]; // [rsp+78h] [rbp-D0h] BYREF
  __int64 v30; // [rsp+90h] [rbp-B8h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  switch ( a1[72] )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_75;
    case 2:
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      ImpersonationHelper::GetThreadImpersonationToken(a1 + 76);
      *((_BYTE *)a1 + 160) = 0;
      if ( *((_DWORD *)a1 + 28) == 2 )
      {
        *((_DWORD *)a1 + 76) = 5672;
        *((_QWORD *)a1 + 39) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generate"
                               "d Files\\winrt\\Windows.Foundation.h";
        *((_QWORD *)a1 + 40) = 0;
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)pExceptionObject,
          (const struct winrt::impl::slim_source_location *)(a1 + 152));
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      a1[72] = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v2, a1);
      return;
    case 4:
      v4 = operator new(0x1B8u);
      *((_QWORD *)a1 + 42) = v4;
      v5 = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::CompliantFlorenceD3::VectorSpaceId;
      v6 = (__int64 *)(a1 + 180);
      v7 = *((_QWORD *)a1 + 17);
      *((_QWORD *)a1 + 45) = v7;
      if ( v7 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
        v5 = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::CompliantFlorenceD3::VectorSpaceId;
      }
      *((_QWORD *)a1 + 44) = v6;
      v8 = *v6;
      *v6 = 0;
      *((_QWORD *)a1 + 46) = v8;
      *((_OWORD *)a1 + 24) = v5;
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::ImageEmbeddingsGenerator(v4);
      *v4 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator>::`vftable';
      if ( *v6 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 180);
      v9 = v4 + 2;
      if ( !v4 )
        v9 = 0;
      *((_QWORD *)a1 + 43) = v9;
      *((_QWORD *)a1 + 21) = v9;
      v10 = *((_QWORD *)a1 + 43);
      *((_QWORD *)a1 + 22) = v10;
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
      v11 = *((_QWORD *)a1 + 17);
      *((_QWORD *)a1 + 23) = v11;
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
      v12 = (void *)*((_QWORD *)a1 + 19);
      if ( v12 )
      {
        ImpersonationHelper::GetThreadImpersonationToken(a1 + 164);
        v14 = (void *)*((_QWORD *)a1 + 41);
        *((_QWORD *)a1 + 41) = 0;
        *((_QWORD *)a1 + 50) = v14;
        if ( !ImpersonateLoggedOnUser(v12) )
          wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x1C, v15, v16);
        v13 = a1 + 96;
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::CreateEmbeddingsGeneratorForOptionsAsync_::_2_::_lambda_1_::operator()(
          a1 + 88,
          a1 + 96);
        if ( v14 != (void *)-1LL )
        {
          if ( !SetThreadToken(0, v14) )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
          if ( v14 )
            CloseHandle(v14);
        }
        v18 = (void *)*((_QWORD *)a1 + 41);
        if ( v18 && v18 != (void *)-1LL )
          CloseHandle(v18);
      }
      else
      {
        v13 = a1 + 96;
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::CreateEmbeddingsGeneratorForOptionsAsync_::_2_::_lambda_1_::operator()(
          a1 + 88,
          a1 + 96);
      }
      if ( *((_DWORD *)a1 + 28) == 2 )
      {
        *((_DWORD *)a1 + 102) = 5672;
        *((_QWORD *)a1 + 52) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generate"
                               "d Files\\winrt\\Windows.Foundation.h";
        *((_QWORD *)a1 + 53) = 0;
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)v28,
          (const struct winrt::impl::slim_source_location *)(a1 + 204));
        throw (winrt::hresult_canceled *)v28;
      }
      *((_QWORD *)a1 + 25) = 0;
      *((_QWORD *)a1 + 26) = v13;
      *((_QWORD *)a1 + 27) = 0;
      *((_BYTE *)a1 + 224) = 1;
      a1[72] = 6;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>(
                              (_QWORD *)a1 + 25,
                              (__int64)a1) )
        return;
      goto LABEL_52;
    case 5:
      v3 = (void *)*((_QWORD *)a1 + 19);
      if ( v3 && v3 != (void *)-1LL )
        CloseHandle(v3);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      goto LABEL_75;
    case 6:
LABEL_52:
      v21 = winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(a1 + 100);
      v22 = (volatile __int64 *)*((_QWORD *)a1 + 25);
      if ( v22 )
      {
        v30 = *((_QWORD *)a1 + 25);
        while ( _InterlockedExchange64(v22, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 24) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 96);
      if ( *((_QWORD *)a1 + 23) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 92);
      if ( *((_QWORD *)a1 + 22) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 88);
      if ( !v21 )
      {
        *((_DWORD *)a1 + 58) = 387;
        *((_QWORD *)a1 + 30) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticImageIndexStore.cpp";
        *((_QWORD *)a1 + 31) = 0;
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)(a1 + 128),
          L"Failed to load image embedding model - migration of underlying index may be required");
        v23 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(a1 + 144), -2081706723);
        winrt::hresult_error::hresult_error(v29, *v23, a1 + 128, a1 + 116);
        throw (winrt::hresult_error *)v29;
      }
      v24 = a1 + 60;
      v25 = a1 + 84;
      if ( a1 + 60 != a1 + 84 )
      {
        if ( *v24 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 60);
        *v25 = 0;
        *v24 = *((_QWORD *)a1 + 43);
      }
      if ( *v25 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 84);
      v26 = (void *)*((_QWORD *)a1 + 19);
      if ( v26 && v26 != (void *)-1LL )
        CloseHandle(v26);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      *((_QWORD *)a1 + 37) = a1 + 8;
      a1[72] = 0;
      *(_QWORD *)a1 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryEmbeddings const &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticQueryOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,void>::final_suspend_awaiter::await_suspend(a1 + 148) )
        goto LABEL_75;
      return;
    case 7:
      v19 = (volatile __int64 *)*((_QWORD *)a1 + 25);
      if ( v19 )
      {
        v30 = *((_QWORD *)a1 + 25);
        while ( _InterlockedExchange64(v19, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 24) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 96);
      if ( *((_QWORD *)a1 + 23) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 92);
      if ( *((_QWORD *)a1 + 22) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 88);
      if ( *((_QWORD *)a1 + 43) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 84);
      v20 = (void *)*((_QWORD *)a1 + 19);
      if ( v20 && v20 != (void *)-1LL )
        CloseHandle(v20);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
LABEL_75:
      std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type::~promise_type(a1 + 8);
      if ( *((_QWORD *)a1 + 17) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 68);
      if ( a1[73] )
        operator delete(a1);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x18022f4d0  mov     [rsp+Block], rcx
0x18022f4d5  push    rbx
0x18022f4d6  push    rsi
0x18022f4d7  push    rdi
0x18022f4d8  push    r12
0x18022f4da  push    r14
0x18022f4dc  push    r15
0x18022f4de  sub     rsp, 118h
0x18022f4e5  mov     rsi, [rsp+148h+Block]
0x18022f4ed  movzx   eax, word ptr [rsi+90h]
0x18022f4f4  mov     [rsp+148h+var_128], ax
0x18022f4f9  inc     ax; switch 9 cases
0x18022f4fc  cmp     ax, 8
0x18022f500  ja      def_18022F51B; jumptable 000000018022F51B default case, case 0
0x18022f506  movsx   rax, ax
0x18022f50a  lea     rdx, cs:180000000h
0x18022f511  mov     ecx, ds:(jpt_18022F51B - 180000000h)[rdx+rax*4]
0x18022f518  add     rcx, rdx
0x18022f51b  jmp     rcx; switch jump
0x18022f51d  jmp     loc_18022FAB0; jumptable 000000018022F51B case 3
0x18022f522  xor     ebx, ebx; jumptable 000000018022F51B case 2
0x18022f524  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18022f52b  lea     rcx, [rsi+98h]
0x18022f532  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x18022f537  nop
0x18022f538  mov     [rsi+0A0h], bl
0x18022f53e  mov     eax, [rsi+70h]
0x18022f541  cmp     eax, 2
0x18022f544  jnz     short loc_18022F583
0x18022f546  lea     rdx, [rsi+130h]; struct winrt::impl::slim_source_location *
0x18022f54d  mov     dword ptr [rdx], 1628h
0x18022f553  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18022f55a  mov     [rsi+138h], rax
0x18022f561  mov     [rsi+140h], rbx
0x18022f568  lea     rcx, [rsp+148h+pExceptionObject]; this
0x18022f56d  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18022f572  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18022f579  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x18022f57e  call    _CxxThrowException
0x18022f583  mov     eax, 4
0x18022f588  mov     [rsi+90h], ax
0x18022f58f  mov     rdx, rsi
0x18022f592  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x18022f597  jmp     loc_18022FAE5
0x18022f59c  mov     rcx, [rsi+98h]; jumptable 000000018022F51B case 5
0x18022f5a3  test    rcx, rcx
0x18022f5a6  jz      short loc_18022F5BD
0x18022f5a8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18022f5ac  jz      short loc_18022F5BD
0x18022f5ae  mov     [rsp+148h+arg_8], rcx
0x18022f5b6  call    cs:__imp_CloseHandle
0x18022f5bc  nop
0x18022f5bd  mov     eax, 0FFFFFFFFh
0x18022f5c2  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18022f5ca  sub     eax, 1
0x18022f5cd  jz      short loc_18022F5D9
0x18022f5cf  test    eax, eax
0x18022f5d1  jns     short loc_18022F5D9
0x18022f5d3  call    abort
0x18022f5d9  jmp     loc_18022FAB0; jumptable 000000018022F51B cases -1,1
0x18022f5de  mov     ecx, 1B8h; jumptable 000000018022F51B case 4
0x18022f5e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18022f5e8  mov     r14, rax
0x18022f5eb  mov     [rsi+150h], rax
0x18022f5f2  movups  xmm0, cs:?VectorSpaceId@CompliantFlorenceD3@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@2UGuid@asg@@B; asg::Guid const winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::CompliantFlorenceD3::VectorSpaceId
0x18022f5f9  movups  [rsp+148h+var_120], xmm0
0x18022f5fe  lea     rdi, [rsi+168h]
0x18022f605  mov     rcx, [rsi+88h]
0x18022f60c  mov     [rdi], rcx
0x18022f60f  test    rcx, rcx
0x18022f612  jz      short loc_18022F626
0x18022f614  mov     rax, [rcx]
0x18022f617  mov     rax, [rax+8]
0x18022f61b  call    cs:__guard_dispatch_icall_fptr
0x18022f621  movups  xmm0, [rsp+148h+var_120]
0x18022f626  mov     [rsi+160h], rdi
0x18022f62d  lea     rdx, [rsi+170h]
0x18022f634  mov     rax, [rdi]
0x18022f637  xor     ebx, ebx
0x18022f639  mov     [rdi], rbx
0x18022f63c  mov     [rdx], rax
0x18022f63f  lea     r8, [rsi+180h]
0x18022f646  movaps  xmmword ptr [r8], xmm0
0x18022f64a  mov     rcx, r14
0x18022f64d  call    ??0ImageEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@USemanticImageIndexStoreOptions@234567@Uguid@7@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::ImageEmbeddingsGenerator(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions,winrt::guid)
0x18022f652  lea     rax, ??_7?$heap_implements@UImageEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator>::`vftable'
0x18022f659  mov     [r14], rax
0x18022f65c  mov     rax, [rdi]
0x18022f65f  mov     [rsp+148h+arg_18], rax
0x18022f667  test    rax, rax
0x18022f66a  jz      short loc_18022F675
0x18022f66c  mov     rcx, rdi
0x18022f66f  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022f674  nop
0x18022f675  lea     rax, [r14+10h]
0x18022f679  test    r14, r14
0x18022f67c  cmovz   rax, rbx
0x18022f680  mov     [rsi+158h], rax
0x18022f687  mov     [rsi+0A8h], rax
0x18022f68e  mov     rcx, [rsi+158h]
0x18022f695  mov     [rsi+0B0h], rcx
0x18022f69c  test    rcx, rcx
0x18022f69f  jz      short loc_18022F6AE
0x18022f6a1  mov     rax, [rcx]
0x18022f6a4  mov     rax, [rax+8]
0x18022f6a8  call    cs:__guard_dispatch_icall_fptr
0x18022f6ae  mov     rcx, [rsi+88h]
0x18022f6b5  mov     [rsi+0B8h], rcx
0x18022f6bc  test    rcx, rcx
0x18022f6bf  jz      short loc_18022F6CF
0x18022f6c1  mov     rax, [rcx]
0x18022f6c4  mov     rax, [rax+8]
0x18022f6c8  call    cs:__guard_dispatch_icall_fptr
0x18022f6ce  nop
0x18022f6cf  mov     rdi, [rsi+98h]
0x18022f6d6  test    rdi, rdi
0x18022f6d9  jnz     short loc_18022F6F6
0x18022f6db  lea     rdi, [rsi+0C0h]
0x18022f6e2  mov     rdx, rdi
0x18022f6e5  lea     rcx, [rsi+0B0h]
0x18022f6ec  call    _winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__SemanticImageIndexStore__CreateEmbeddingsGeneratorForOptionsAsync____2____lambda_1___operator__
0x18022f6f1  jmp     loc_18022F796
0x18022f6f6  lea     rcx, [rsi+148h]
0x18022f6fd  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x18022f702  nop
0x18022f703  mov     r14, [rsi+148h]
0x18022f70a  mov     [rsi+148h], rbx
0x18022f711  mov     [rsi+190h], r14
0x18022f718  mov     rcx, rdi; hToken
0x18022f71b  call    cs:__imp_ImpersonateLoggedOnUser
0x18022f721  mov     rcx, [rsp+148h]; this
0x18022f729  test    eax, eax
0x18022f72b  jnz     short loc_18022F737
0x18022f72d  mov     edx, 1Ch; void *
0x18022f732  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18022f737  lea     rdi, [rsi+0C0h]
0x18022f73e  mov     rdx, rdi
0x18022f741  lea     rcx, [rsi+0B0h]
0x18022f748  call    _winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__SemanticImageIndexStore__CreateEmbeddingsGeneratorForOptionsAsync____2____lambda_1___operator__
0x18022f74d  nop
0x18022f74e  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18022f752  jz      short loc_18022F778
0x18022f754  mov     rdx, r14; Token
0x18022f757  xor     ecx, ecx; Thread
0x18022f759  call    cs:__imp_SetThreadToken
0x18022f75f  test    eax, eax
0x18022f761  jnz     short loc_18022F769
0x18022f763  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18022f769  test    r14, r14
0x18022f76c  jz      short loc_18022F778
0x18022f76e  mov     rcx, r14; hObject
0x18022f771  call    cs:__imp_CloseHandle
0x18022f777  nop
0x18022f778  mov     rcx, [rsi+148h]; hObject
0x18022f77f  test    rcx, rcx
0x18022f782  jz      short loc_18022F796
0x18022f784  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18022f788  jz      short loc_18022F796
0x18022f78a  mov     [rsp+148h+var_110], rcx
0x18022f78f  call    cs:__imp_CloseHandle
0x18022f795  nop
0x18022f796  mov     eax, [rsi+70h]
0x18022f799  cmp     eax, 2
0x18022f79c  jnz     short loc_18022F7DB
0x18022f79e  lea     rdx, [rsi+198h]; struct winrt::impl::slim_source_location *
0x18022f7a5  mov     dword ptr [rdx], 1628h
0x18022f7ab  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18022f7b2  mov     [rsi+1A0h], rax
0x18022f7b9  mov     [rsi+1A8h], rbx
0x18022f7c0  lea     rcx, [rsp+148h+var_E8]; this
0x18022f7c5  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18022f7ca  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18022f7d1  lea     rcx, [rsp+148h+var_E8]; pExceptionObject
0x18022f7d6  call    _CxxThrowException
0x18022f7db  lea     rcx, [rsi+0C8h]
0x18022f7e2  mov     [rcx], rbx
0x18022f7e5  mov     [rsi+0D0h], rdi
0x18022f7ec  mov     [rsi+0D8h], rbx
0x18022f7f3  mov     byte ptr [rsi+0E0h], 1
0x18022f7fa  mov     eax, 6
0x18022f7ff  mov     [rsi+90h], ax
0x18022f806  mov     rdx, rsi
0x18022f809  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>)
0x18022f80e  test    al, al
0x18022f810  jz      loc_18022F8FC
0x18022f816  jmp     loc_18022FAE5
0x18022f81b  mov     rdi, [rsi+0C8h]; jumptable 000000018022F51B case 7
0x18022f822  test    rdi, rdi
0x18022f825  jz      short loc_18022F851
0x18022f827  mov     [rsp+148h+var_B8], rdi
0x18022f82f  xor     ebx, ebx
0x18022f831  mov     eax, ebx
0x18022f833  xchg    rax, [rdi]
0x18022f836  cmp     rax, 1
0x18022f83a  jnz     short loc_18022F851
0x18022f83c  nop     dword ptr [rax+00h]
0x18022f840  call    _Thrd_yield
0x18022f845  mov     rax, rbx
0x18022f848  xchg    rax, [rdi]
0x18022f84b  cmp     rax, 1
0x18022f84f  jz      short loc_18022F840
0x18022f851  lea     rcx, [rsi+0C0h]
0x18022f858  mov     rax, [rcx]
0x18022f85b  mov     [rsp+148h+arg_10], rax
0x18022f863  test    rax, rax
0x18022f866  jz      short loc_18022F86E
0x18022f868  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022f86d  nop
0x18022f86e  lea     rcx, [rsi+0B8h]
0x18022f875  mov     rax, [rcx]
0x18022f878  mov     qword ptr [rsp+148h+var_120+8], rax
0x18022f87d  test    rax, rax
0x18022f880  jz      short loc_18022F887
0x18022f882  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022f887  lea     rcx, [rsi+0B0h]
0x18022f88e  mov     rax, [rcx]
0x18022f891  mov     qword ptr [rsp+148h+var_120], rax
0x18022f896  test    rax, rax
0x18022f899  jz      short loc_18022F8A1
0x18022f89b  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022f8a0  nop
0x18022f8a1  cmp     qword ptr [rsi+158h], 0
0x18022f8a9  jz      short loc_18022F8B8
0x18022f8ab  lea     rcx, [rsi+0A8h]
0x18022f8b2  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022f8b7  nop
0x18022f8b8  mov     rcx, [rsi+98h]; hObject
0x18022f8bf  test    rcx, rcx
0x18022f8c2  jz      short loc_18022F8D9
0x18022f8c4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18022f8c8  jz      short loc_18022F8D9
0x18022f8ca  mov     [rsp+148h+arg_8], rcx
0x18022f8d2  call    cs:__imp_CloseHandle
0x18022f8d8  nop
0x18022f8d9  mov     eax, 0FFFFFFFFh
0x18022f8de  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18022f8e6  sub     eax, 1
0x18022f8e9  jz      short loc_18022F8F5
0x18022f8eb  test    eax, eax
0x18022f8ed  jns     short loc_18022F8F5
0x18022f8ef  call    abort
0x18022f8f5  jmp     loc_18022FAB0; jumptable 000000018022F51B cases -1,1
0x18022f8fa  xor     ebx, ebx; jumptable 000000018022F51B case 6
0x18022f8fc  lea     rcx, [rsi+0C8h]
0x18022f903  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(void)
0x18022f908  movzx   r14d, al
0x18022f90c  mov     rdi, [rsi+0C8h]
0x18022f913  test    rdi, rdi
0x18022f916  jz      short loc_18022F941
0x18022f918  mov     [rsp+148h+var_B8], rdi
0x18022f920  mov     rcx, rbx
0x18022f923  xchg    rcx, [rdi]
0x18022f926  cmp     rcx, 1
0x18022f92a  jnz     short loc_18022F941
0x18022f92c  nop     dword ptr [rax+00h]
0x18022f930  call    _Thrd_yield
0x18022f935  mov     rax, rbx
0x18022f938  xchg    rax, [rdi]
0x18022f93b  cmp     rax, 1
0x18022f93f  jz      short loc_18022F930
0x18022f941  lea     rcx, [rsi+0C0h]
0x18022f948  mov     rax, [rcx]
0x18022f94b  mov     [rsp+148h+arg_10], rax
0x18022f953  test    rax, rax
0x18022f956  jz      short loc_18022F95E
0x18022f958  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022f95d  nop
0x18022f95e  lea     rcx, [rsi+0B8h]
0x18022f965  mov     rax, [rcx]
0x18022f968  mov     qword ptr [rsp+148h+var_120+8], rax
0x18022f96d  test    rax, rax
0x18022f970  jz      short loc_18022F977
0x18022f972  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022f977  lea     rcx, [rsi+0B0h]
0x18022f97e  mov     rax, [rcx]
0x18022f981  mov     qword ptr [rsp+148h+var_120], rax
0x18022f986  test    rax, rax
0x18022f989  jz      short loc_18022F990
0x18022f98b  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022f990  test    r14b, r14b
0x18022f993  jnz     short loc_18022FA03
0x18022f995  mov     dword ptr [rsi+0E8h], 183h
0x18022f99f  lea     rax, aCW1SSrcSemanti_43; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18022f9a6  mov     [rsi+0F0h], rax
0x18022f9ad  mov     [rsi+0F8h], rbx
0x18022f9b4  lea     rdx, aFailedToLoadIm; "Failed to load image embedding model - "...
0x18022f9bb  lea     rcx, [rsi+100h]; this
0x18022f9c2  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18022f9c7  lea     rcx, [rsi+120h]; this
0x18022f9ce  mov     edx, 83EBAD1Dh; int
0x18022f9d3  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18022f9d8  lea     r9, [rsi+0E8h]
0x18022f9df  lea     r8, [rsi+100h]
0x18022f9e6  mov     edx, [rax]
0x18022f9e8  lea     rcx, [rsp+148h+var_D0]
0x18022f9ed  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18022f9f2  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18022f9f9  lea     rcx, [rsp+148h+var_D0]; pExceptionObject
0x18022f9fe  call    _CxxThrowException
0x18022fa03  lea     r14, [rsi+78h]
  ... truncated ...
```
