# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::CreateTextQueryEmbeddingsGeneratorForOptionsAsync$_ResumeCoro$1

- ea: `0x18022ffa0`
- end: `0x1802305ec`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::CreateTextQueryEmbeddingsGeneratorForOptionsAsync$_ResumeCoro$1`
- size: `1612`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001d110`
- `0x18022ff90`

## callees

- `0x180003bd0`
- `0x180003fb0`
- `0x180004510`
- `0x18000d230`
- `0x18000d4b0`
- `0x18001b1f0`
- `0x18001b3c0`
- `0x18001bc40`
- `0x18001d250`
- `0x18001fd80`
- `0x180020e60`
- `0x180047120`
- `0x180047520`
- `0x1800475c0`
- `0x180060f20`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180206a58`
- `0x18022ffa0`
- `0x180242120`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180230086`
- `KERNEL32!CloseHandle` at `0x180230241`
- `KERNEL32!CloseHandle` at `0x18023025f`
- `KERNEL32!CloseHandle` at `0x1802303a2`
- `KERNEL32!CloseHandle` at `0x18023052e`
- `KERNEL32!CloseHandle` at `0x180230086`
- `KERNEL32!CloseHandle` at `0x180230241`
- `KERNEL32!CloseHandle` at `0x18023025f`
- `KERNEL32!CloseHandle` at `0x1802303a2`
- `KERNEL32!CloseHandle` at `0x18023052e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180230229`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180230229`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1802301eb`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1802301eb`

## string_xrefs

- `0x180230023`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18023027b`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18023046f`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticImageIndexStore.cpp`

## pseudocode

```c
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::CreateTextQueryEmbeddingsGeneratorForOptionsAsync__ResumeCoro_1(
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
      goto LABEL_77;
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
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TextEmbeddingsGenerator(v4);
      *v4 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::`vftable';
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
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::CreateTextQueryEmbeddingsGeneratorForOptionsAsync_::_2_::_lambda_1_::operator()(
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
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::CreateTextQueryEmbeddingsGeneratorForOptionsAsync_::_2_::_lambda_1_::operator()(
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
      goto LABEL_54;
    case 5:
      v3 = (void *)*((_QWORD *)a1 + 19);
      if ( v3 && v3 != (void *)-1LL )
        CloseHandle(v3);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      goto LABEL_77;
    case 6:
LABEL_54:
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
        *((_DWORD *)a1 + 58) = 564;
        *((_QWORD *)a1 + 30) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticImageIndexStore.cpp";
        *((_QWORD *)a1 + 31) = 0;
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)(a1 + 128),
          L"Failed to load text query embedding model - migration of underlying index may be required");
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
        goto LABEL_77;
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
LABEL_77:
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
0x18022ffa0  mov     [rsp+Block], rcx
0x18022ffa5  push    rbx
0x18022ffa6  push    rsi
0x18022ffa7  push    rdi
0x18022ffa8  push    r12
0x18022ffaa  push    r14
0x18022ffac  push    r15
0x18022ffae  sub     rsp, 118h
0x18022ffb5  mov     rsi, [rsp+148h+Block]
0x18022ffbd  movzx   eax, word ptr [rsi+90h]
0x18022ffc4  mov     [rsp+148h+var_128], ax
0x18022ffc9  inc     ax; switch 9 cases
0x18022ffcc  cmp     ax, 8
0x18022ffd0  ja      def_18022FFEB; jumptable 000000018022FFEB default case, case 0
0x18022ffd6  movsx   rax, ax
0x18022ffda  lea     rdx, cs:180000000h
0x18022ffe1  mov     ecx, ds:(jpt_18022FFEB - 180000000h)[rdx+rax*4]
0x18022ffe8  add     rcx, rdx
0x18022ffeb  jmp     rcx; switch jump
0x18022ffed  jmp     loc_180230580; jumptable 000000018022FFEB case 3
0x18022fff2  xor     ebx, ebx; jumptable 000000018022FFEB case 2
0x18022fff4  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18022fffb  lea     rcx, [rsi+98h]
0x180230002  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x180230007  nop
0x180230008  mov     [rsi+0A0h], bl
0x18023000e  mov     eax, [rsi+70h]
0x180230011  cmp     eax, 2
0x180230014  jnz     short loc_180230053
0x180230016  lea     rdx, [rsi+130h]; struct winrt::impl::slim_source_location *
0x18023001d  mov     dword ptr [rdx], 1628h
0x180230023  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18023002a  mov     [rsi+138h], rax
0x180230031  mov     [rsi+140h], rbx
0x180230038  lea     rcx, [rsp+148h+pExceptionObject]; this
0x18023003d  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180230042  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180230049  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x18023004e  call    _CxxThrowException
0x180230053  mov     eax, 4
0x180230058  mov     [rsi+90h], ax
0x18023005f  mov     rdx, rsi
0x180230062  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x180230067  jmp     loc_1802305B5
0x18023006c  mov     rcx, [rsi+98h]; jumptable 000000018022FFEB case 5
0x180230073  test    rcx, rcx
0x180230076  jz      short loc_18023008D
0x180230078  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18023007c  jz      short loc_18023008D
0x18023007e  mov     [rsp+148h+arg_8], rcx
0x180230086  call    cs:__imp_CloseHandle
0x18023008c  nop
0x18023008d  mov     eax, 0FFFFFFFFh
0x180230092  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18023009a  sub     eax, 1
0x18023009d  jz      short loc_1802300A9
0x18023009f  test    eax, eax
0x1802300a1  jns     short loc_1802300A9
0x1802300a3  call    abort
0x1802300a9  jmp     loc_180230580; jumptable 000000018022FFEB cases -1,1
0x1802300ae  mov     ecx, 1B8h; jumptable 000000018022FFEB case 4
0x1802300b3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802300b8  mov     r14, rax
0x1802300bb  mov     [rsi+150h], rax
0x1802300c2  movups  xmm0, cs:?VectorSpaceId@CompliantFlorenceD3@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@2UGuid@asg@@B; asg::Guid const winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::CompliantFlorenceD3::VectorSpaceId
0x1802300c9  movups  [rsp+148h+var_120], xmm0
0x1802300ce  lea     rdi, [rsi+168h]
0x1802300d5  mov     rcx, [rsi+88h]
0x1802300dc  mov     [rdi], rcx
0x1802300df  test    rcx, rcx
0x1802300e2  jz      short loc_1802300F6
0x1802300e4  mov     rax, [rcx]
0x1802300e7  mov     rax, [rax+8]
0x1802300eb  call    cs:__guard_dispatch_icall_fptr
0x1802300f1  movups  xmm0, [rsp+148h+var_120]
0x1802300f6  mov     [rsi+160h], rdi
0x1802300fd  lea     rdx, [rsi+170h]
0x180230104  mov     rax, [rdi]
0x180230107  xor     ebx, ebx
0x180230109  mov     [rdi], rbx
0x18023010c  mov     [rdx], rax
0x18023010f  lea     r8, [rsi+180h]
0x180230116  movaps  xmmword ptr [r8], xmm0
0x18023011a  mov     rcx, r14
0x18023011d  call    ??0TextEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@USemanticImageIndexStoreOptions@234567@Uguid@7@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TextEmbeddingsGenerator(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions,winrt::guid)
0x180230122  lea     rax, ??_7?$heap_implements@UTextEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::`vftable'
0x180230129  mov     [r14], rax
0x18023012c  mov     rax, [rdi]
0x18023012f  mov     [rsp+148h+arg_18], rax
0x180230137  test    rax, rax
0x18023013a  jz      short loc_180230145
0x18023013c  mov     rcx, rdi
0x18023013f  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180230144  nop
0x180230145  lea     rax, [r14+10h]
0x180230149  test    r14, r14
0x18023014c  cmovz   rax, rbx
0x180230150  mov     [rsi+158h], rax
0x180230157  mov     [rsi+0A8h], rax
0x18023015e  mov     rcx, [rsi+158h]
0x180230165  mov     [rsi+0B0h], rcx
0x18023016c  test    rcx, rcx
0x18023016f  jz      short loc_18023017E
0x180230171  mov     rax, [rcx]
0x180230174  mov     rax, [rax+8]
0x180230178  call    cs:__guard_dispatch_icall_fptr
0x18023017e  mov     rcx, [rsi+88h]
0x180230185  mov     [rsi+0B8h], rcx
0x18023018c  test    rcx, rcx
0x18023018f  jz      short loc_18023019F
0x180230191  mov     rax, [rcx]
0x180230194  mov     rax, [rax+8]
0x180230198  call    cs:__guard_dispatch_icall_fptr
0x18023019e  nop
0x18023019f  mov     rdi, [rsi+98h]
0x1802301a6  test    rdi, rdi
0x1802301a9  jnz     short loc_1802301C6
0x1802301ab  lea     rdi, [rsi+0C0h]
0x1802301b2  mov     rdx, rdi
0x1802301b5  lea     rcx, [rsi+0B0h]
0x1802301bc  call    _winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__SemanticImageIndexStore__CreateTextQueryEmbeddingsGeneratorForOptionsAsync____2____lambda_1___operator__
0x1802301c1  jmp     loc_180230266
0x1802301c6  lea     rcx, [rsi+148h]
0x1802301cd  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x1802301d2  nop
0x1802301d3  mov     r14, [rsi+148h]
0x1802301da  mov     [rsi+148h], rbx
0x1802301e1  mov     [rsi+190h], r14
0x1802301e8  mov     rcx, rdi; hToken
0x1802301eb  call    cs:__imp_ImpersonateLoggedOnUser
0x1802301f1  mov     rcx, [rsp+148h]; this
0x1802301f9  test    eax, eax
0x1802301fb  jnz     short loc_180230207
0x1802301fd  mov     edx, 1Ch; void *
0x180230202  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180230207  lea     rdi, [rsi+0C0h]
0x18023020e  mov     rdx, rdi
0x180230211  lea     rcx, [rsi+0B0h]
0x180230218  call    _winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__SemanticImageIndexStore__CreateTextQueryEmbeddingsGeneratorForOptionsAsync____2____lambda_1___operator__
0x18023021d  nop
0x18023021e  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180230222  jz      short loc_180230248
0x180230224  mov     rdx, r14; Token
0x180230227  xor     ecx, ecx; Thread
0x180230229  call    cs:__imp_SetThreadToken
0x18023022f  test    eax, eax
0x180230231  jnz     short loc_180230239
0x180230233  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180230239  test    r14, r14
0x18023023c  jz      short loc_180230248
0x18023023e  mov     rcx, r14; hObject
0x180230241  call    cs:__imp_CloseHandle
0x180230247  nop
0x180230248  mov     rcx, [rsi+148h]; hObject
0x18023024f  test    rcx, rcx
0x180230252  jz      short loc_180230266
0x180230254  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180230258  jz      short loc_180230266
0x18023025a  mov     [rsp+148h+var_110], rcx
0x18023025f  call    cs:__imp_CloseHandle
0x180230265  nop
0x180230266  mov     eax, [rsi+70h]
0x180230269  cmp     eax, 2
0x18023026c  jnz     short loc_1802302AB
0x18023026e  lea     rdx, [rsi+198h]; struct winrt::impl::slim_source_location *
0x180230275  mov     dword ptr [rdx], 1628h
0x18023027b  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180230282  mov     [rsi+1A0h], rax
0x180230289  mov     [rsi+1A8h], rbx
0x180230290  lea     rcx, [rsp+148h+var_E8]; this
0x180230295  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18023029a  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x1802302a1  lea     rcx, [rsp+148h+var_E8]; pExceptionObject
0x1802302a6  call    _CxxThrowException
0x1802302ab  lea     rcx, [rsi+0C8h]
0x1802302b2  mov     [rcx], rbx
0x1802302b5  mov     [rsi+0D0h], rdi
0x1802302bc  mov     [rsi+0D8h], rbx
0x1802302c3  mov     byte ptr [rsi+0E0h], 1
0x1802302ca  mov     eax, 6
0x1802302cf  mov     [rsi+90h], ax
0x1802302d6  mov     rdx, rsi
0x1802302d9  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>)
0x1802302de  test    al, al
0x1802302e0  jz      loc_1802303CC
0x1802302e6  jmp     loc_1802305B5
0x1802302eb  mov     rdi, [rsi+0C8h]; jumptable 000000018022FFEB case 7
0x1802302f2  test    rdi, rdi
0x1802302f5  jz      short loc_180230321
0x1802302f7  mov     [rsp+148h+var_B8], rdi
0x1802302ff  xor     ebx, ebx
0x180230301  mov     eax, ebx
0x180230303  xchg    rax, [rdi]
0x180230306  cmp     rax, 1
0x18023030a  jnz     short loc_180230321
0x18023030c  nop     dword ptr [rax+00h]
0x180230310  call    _Thrd_yield
0x180230315  mov     rax, rbx
0x180230318  xchg    rax, [rdi]
0x18023031b  cmp     rax, 1
0x18023031f  jz      short loc_180230310
0x180230321  lea     rcx, [rsi+0C0h]
0x180230328  mov     rax, [rcx]
0x18023032b  mov     [rsp+148h+arg_10], rax
0x180230333  test    rax, rax
0x180230336  jz      short loc_18023033E
0x180230338  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023033d  nop
0x18023033e  lea     rcx, [rsi+0B8h]
0x180230345  mov     rax, [rcx]
0x180230348  mov     qword ptr [rsp+148h+var_120+8], rax
0x18023034d  test    rax, rax
0x180230350  jz      short loc_180230357
0x180230352  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180230357  lea     rcx, [rsi+0B0h]
0x18023035e  mov     rax, [rcx]
0x180230361  mov     qword ptr [rsp+148h+var_120], rax
0x180230366  test    rax, rax
0x180230369  jz      short loc_180230371
0x18023036b  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180230370  nop
0x180230371  cmp     qword ptr [rsi+158h], 0
0x180230379  jz      short loc_180230388
0x18023037b  lea     rcx, [rsi+0A8h]
0x180230382  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180230387  nop
0x180230388  mov     rcx, [rsi+98h]; hObject
0x18023038f  test    rcx, rcx
0x180230392  jz      short loc_1802303A9
0x180230394  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180230398  jz      short loc_1802303A9
0x18023039a  mov     [rsp+148h+arg_8], rcx
0x1802303a2  call    cs:__imp_CloseHandle
0x1802303a8  nop
0x1802303a9  mov     eax, 0FFFFFFFFh
0x1802303ae  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1802303b6  sub     eax, 1
0x1802303b9  jz      short loc_1802303C5
0x1802303bb  test    eax, eax
0x1802303bd  jns     short loc_1802303C5
0x1802303bf  call    abort
0x1802303c5  jmp     loc_180230580; jumptable 000000018022FFEB cases -1,1
0x1802303ca  xor     ebx, ebx; jumptable 000000018022FFEB case 6
0x1802303cc  lea     rcx, [rsi+0C8h]
0x1802303d3  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(void)
0x1802303d8  movzx   r14d, al
0x1802303dc  mov     rdi, [rsi+0C8h]
0x1802303e3  test    rdi, rdi
0x1802303e6  jz      short loc_180230411
0x1802303e8  mov     [rsp+148h+var_B8], rdi
0x1802303f0  mov     rcx, rbx
0x1802303f3  xchg    rcx, [rdi]
0x1802303f6  cmp     rcx, 1
0x1802303fa  jnz     short loc_180230411
0x1802303fc  nop     dword ptr [rax+00h]
0x180230400  call    _Thrd_yield
0x180230405  mov     rax, rbx
0x180230408  xchg    rax, [rdi]
0x18023040b  cmp     rax, 1
0x18023040f  jz      short loc_180230400
0x180230411  lea     rcx, [rsi+0C0h]
0x180230418  mov     rax, [rcx]
0x18023041b  mov     [rsp+148h+arg_10], rax
0x180230423  test    rax, rax
0x180230426  jz      short loc_18023042E
0x180230428  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023042d  nop
0x18023042e  lea     rcx, [rsi+0B8h]
0x180230435  mov     rax, [rcx]
0x180230438  mov     qword ptr [rsp+148h+var_120+8], rax
0x18023043d  test    rax, rax
0x180230440  jz      short loc_180230447
0x180230442  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180230447  lea     rcx, [rsi+0B0h]
0x18023044e  mov     rax, [rcx]
0x180230451  mov     qword ptr [rsp+148h+var_120], rax
0x180230456  test    rax, rax
0x180230459  jz      short loc_180230460
0x18023045b  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180230460  test    r14b, r14b
0x180230463  jnz     short loc_1802304D3
0x180230465  mov     dword ptr [rsi+0E8h], 234h
0x18023046f  lea     rax, aCW1SSrcSemanti_43; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180230476  mov     [rsi+0F0h], rax
0x18023047d  mov     [rsi+0F8h], rbx
0x180230484  lea     rdx, aFailedToLoadTe_1; "Failed to load text query embedding mod"...
0x18023048b  lea     rcx, [rsi+100h]; this
0x180230492  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180230497  lea     rcx, [rsi+120h]; this
0x18023049e  mov     edx, 83EBAD1Dh; int
0x1802304a3  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x1802304a8  lea     r9, [rsi+0E8h]
0x1802304af  lea     r8, [rsi+100h]
0x1802304b6  mov     edx, [rax]
0x1802304b8  lea     rcx, [rsp+148h+var_D0]
0x1802304bd  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x1802304c2  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x1802304c9  lea     rcx, [rsp+148h+var_D0]; pExceptionObject
0x1802304ce  call    _CxxThrowException
0x1802304d3  lea     r14, [rsi+78h]
  ... truncated ...
```
