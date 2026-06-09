# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::CreateEmbeddingsGeneratorForOptionsAsync$_ResumeCoro$1

- ea: `0x180239c10`
- end: `0x18023a25c`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::CreateEmbeddingsGeneratorForOptionsAsync$_ResumeCoro$1`
- size: `1612`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18004b260`
- `0x180239c00`

## callees

- `0x180003bd0`
- `0x180003fb0`
- `0x180004510`
- `0x18000d230`
- `0x18000d4b0`
- `0x18001b1f0`
- `0x18001b3c0`
- `0x18001bc40`
- `0x18001fd80`
- `0x180020e60`
- `0x180047120`
- `0x180047520`
- `0x1800475c0`
- `0x18004b3a0`
- `0x180060ca0`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180206a58`
- `0x180239c10`
- `0x180242120`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180239cf6`
- `KERNEL32!CloseHandle` at `0x180239eb1`
- `KERNEL32!CloseHandle` at `0x180239ecf`
- `KERNEL32!CloseHandle` at `0x18023a012`
- `KERNEL32!CloseHandle` at `0x18023a19e`
- `KERNEL32!CloseHandle` at `0x180239cf6`
- `KERNEL32!CloseHandle` at `0x180239eb1`
- `KERNEL32!CloseHandle` at `0x180239ecf`
- `KERNEL32!CloseHandle` at `0x18023a012`
- `KERNEL32!CloseHandle` at `0x18023a19e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180239e99`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180239e99`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180239e5b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180239e5b`

## string_xrefs

- `0x180239c93`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x180239eeb`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18023a0df`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticTextIndexStore.cpp`

## pseudocode

```c
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::CreateEmbeddingsGeneratorForOptionsAsync__ResumeCoro_1(
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
      v5 = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SpaceV6::VectorSpaceId;
      v6 = (__int64 *)(a1 + 180);
      v7 = *((_QWORD *)a1 + 17);
      *((_QWORD *)a1 + 45) = v7;
      if ( v7 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
        v5 = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SpaceV6::VectorSpaceId;
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
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::CreateEmbeddingsGeneratorForOptionsAsync_::_2_::_lambda_1_::operator()(
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
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::CreateEmbeddingsGeneratorForOptionsAsync_::_2_::_lambda_1_::operator()(
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
        *((_DWORD *)a1 + 58) = 255;
        *((_QWORD *)a1 + 30) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticTextIndexStore.cpp";
        *((_QWORD *)a1 + 31) = 0;
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)(a1 + 128),
          L"Failed to load text embedding model - migration of underlying index may be required");
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
0x180239c10  mov     [rsp+Block], rcx
0x180239c15  push    rbx
0x180239c16  push    rsi
0x180239c17  push    rdi
0x180239c18  push    r12
0x180239c1a  push    r14
0x180239c1c  push    r15
0x180239c1e  sub     rsp, 118h
0x180239c25  mov     rsi, [rsp+148h+Block]
0x180239c2d  movzx   eax, word ptr [rsi+90h]
0x180239c34  mov     [rsp+148h+var_128], ax
0x180239c39  inc     ax; switch 9 cases
0x180239c3c  cmp     ax, 8
0x180239c40  ja      def_180239C5B; jumptable 0000000180239C5B default case, case 0
0x180239c46  movsx   rax, ax
0x180239c4a  lea     rdx, cs:180000000h
0x180239c51  mov     ecx, ds:(jpt_180239C5B - 180000000h)[rdx+rax*4]
0x180239c58  add     rcx, rdx
0x180239c5b  jmp     rcx; switch jump
0x180239c5d  jmp     loc_18023A1F0; jumptable 0000000180239C5B case 3
0x180239c62  xor     ebx, ebx; jumptable 0000000180239C5B case 2
0x180239c64  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180239c6b  lea     rcx, [rsi+98h]
0x180239c72  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x180239c77  nop
0x180239c78  mov     [rsi+0A0h], bl
0x180239c7e  mov     eax, [rsi+70h]
0x180239c81  cmp     eax, 2
0x180239c84  jnz     short loc_180239CC3
0x180239c86  lea     rdx, [rsi+130h]; struct winrt::impl::slim_source_location *
0x180239c8d  mov     dword ptr [rdx], 1628h
0x180239c93  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180239c9a  mov     [rsi+138h], rax
0x180239ca1  mov     [rsi+140h], rbx
0x180239ca8  lea     rcx, [rsp+148h+pExceptionObject]; this
0x180239cad  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180239cb2  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180239cb9  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x180239cbe  call    _CxxThrowException
0x180239cc3  mov     eax, 4
0x180239cc8  mov     [rsi+90h], ax
0x180239ccf  mov     rdx, rsi
0x180239cd2  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x180239cd7  jmp     loc_18023A225
0x180239cdc  mov     rcx, [rsi+98h]; jumptable 0000000180239C5B case 5
0x180239ce3  test    rcx, rcx
0x180239ce6  jz      short loc_180239CFD
0x180239ce8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180239cec  jz      short loc_180239CFD
0x180239cee  mov     [rsp+148h+arg_8], rcx
0x180239cf6  call    cs:__imp_CloseHandle
0x180239cfc  nop
0x180239cfd  mov     eax, 0FFFFFFFFh
0x180239d02  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180239d0a  sub     eax, 1
0x180239d0d  jz      short loc_180239D19
0x180239d0f  test    eax, eax
0x180239d11  jns     short loc_180239D19
0x180239d13  call    abort
0x180239d19  jmp     loc_18023A1F0; jumptable 0000000180239C5B cases -1,1
0x180239d1e  mov     ecx, 1B8h; jumptable 0000000180239C5B case 4
0x180239d23  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180239d28  mov     r14, rax
0x180239d2b  mov     [rsi+150h], rax
0x180239d32  movups  xmm0, cs:?VectorSpaceId@SpaceV6@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@2UGuid@asg@@B; asg::Guid const winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SpaceV6::VectorSpaceId
0x180239d39  movups  [rsp+148h+var_120], xmm0
0x180239d3e  lea     rdi, [rsi+168h]
0x180239d45  mov     rcx, [rsi+88h]
0x180239d4c  mov     [rdi], rcx
0x180239d4f  test    rcx, rcx
0x180239d52  jz      short loc_180239D66
0x180239d54  mov     rax, [rcx]
0x180239d57  mov     rax, [rax+8]
0x180239d5b  call    cs:__guard_dispatch_icall_fptr
0x180239d61  movups  xmm0, [rsp+148h+var_120]
0x180239d66  mov     [rsi+160h], rdi
0x180239d6d  lea     rdx, [rsi+170h]
0x180239d74  mov     rax, [rdi]
0x180239d77  xor     ebx, ebx
0x180239d79  mov     [rdi], rbx
0x180239d7c  mov     [rdx], rax
0x180239d7f  lea     r8, [rsi+180h]
0x180239d86  movaps  xmmword ptr [r8], xmm0
0x180239d8a  mov     rcx, r14
0x180239d8d  call    ??0TextEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@USemanticTextIndexStoreOptions@234567@Uguid@7@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TextEmbeddingsGenerator(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions,winrt::guid)
0x180239d92  lea     rax, ??_7?$heap_implements@UTextEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::`vftable'
0x180239d99  mov     [r14], rax
0x180239d9c  mov     rax, [rdi]
0x180239d9f  mov     [rsp+148h+arg_18], rax
0x180239da7  test    rax, rax
0x180239daa  jz      short loc_180239DB5
0x180239dac  mov     rcx, rdi
0x180239daf  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180239db4  nop
0x180239db5  lea     rax, [r14+10h]
0x180239db9  test    r14, r14
0x180239dbc  cmovz   rax, rbx
0x180239dc0  mov     [rsi+158h], rax
0x180239dc7  mov     [rsi+0A8h], rax
0x180239dce  mov     rcx, [rsi+158h]
0x180239dd5  mov     [rsi+0B0h], rcx
0x180239ddc  test    rcx, rcx
0x180239ddf  jz      short loc_180239DEE
0x180239de1  mov     rax, [rcx]
0x180239de4  mov     rax, [rax+8]
0x180239de8  call    cs:__guard_dispatch_icall_fptr
0x180239dee  mov     rcx, [rsi+88h]
0x180239df5  mov     [rsi+0B8h], rcx
0x180239dfc  test    rcx, rcx
0x180239dff  jz      short loc_180239E0F
0x180239e01  mov     rax, [rcx]
0x180239e04  mov     rax, [rax+8]
0x180239e08  call    cs:__guard_dispatch_icall_fptr
0x180239e0e  nop
0x180239e0f  mov     rdi, [rsi+98h]
0x180239e16  test    rdi, rdi
0x180239e19  jnz     short loc_180239E36
0x180239e1b  lea     rdi, [rsi+0C0h]
0x180239e22  mov     rdx, rdi
0x180239e25  lea     rcx, [rsi+0B0h]
0x180239e2c  call    _winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__SemanticTextIndexStore__CreateEmbeddingsGeneratorForOptionsAsync____2____lambda_1___operator__
0x180239e31  jmp     loc_180239ED6
0x180239e36  lea     rcx, [rsi+148h]
0x180239e3d  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x180239e42  nop
0x180239e43  mov     r14, [rsi+148h]
0x180239e4a  mov     [rsi+148h], rbx
0x180239e51  mov     [rsi+190h], r14
0x180239e58  mov     rcx, rdi; hToken
0x180239e5b  call    cs:__imp_ImpersonateLoggedOnUser
0x180239e61  mov     rcx, [rsp+148h]; this
0x180239e69  test    eax, eax
0x180239e6b  jnz     short loc_180239E77
0x180239e6d  mov     edx, 1Ch; void *
0x180239e72  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180239e77  lea     rdi, [rsi+0C0h]
0x180239e7e  mov     rdx, rdi
0x180239e81  lea     rcx, [rsi+0B0h]
0x180239e88  call    _winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__SemanticTextIndexStore__CreateEmbeddingsGeneratorForOptionsAsync____2____lambda_1___operator__
0x180239e8d  nop
0x180239e8e  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180239e92  jz      short loc_180239EB8
0x180239e94  mov     rdx, r14; Token
0x180239e97  xor     ecx, ecx; Thread
0x180239e99  call    cs:__imp_SetThreadToken
0x180239e9f  test    eax, eax
0x180239ea1  jnz     short loc_180239EA9
0x180239ea3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180239ea9  test    r14, r14
0x180239eac  jz      short loc_180239EB8
0x180239eae  mov     rcx, r14; hObject
0x180239eb1  call    cs:__imp_CloseHandle
0x180239eb7  nop
0x180239eb8  mov     rcx, [rsi+148h]; hObject
0x180239ebf  test    rcx, rcx
0x180239ec2  jz      short loc_180239ED6
0x180239ec4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180239ec8  jz      short loc_180239ED6
0x180239eca  mov     [rsp+148h+var_110], rcx
0x180239ecf  call    cs:__imp_CloseHandle
0x180239ed5  nop
0x180239ed6  mov     eax, [rsi+70h]
0x180239ed9  cmp     eax, 2
0x180239edc  jnz     short loc_180239F1B
0x180239ede  lea     rdx, [rsi+198h]; struct winrt::impl::slim_source_location *
0x180239ee5  mov     dword ptr [rdx], 1628h
0x180239eeb  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180239ef2  mov     [rsi+1A0h], rax
0x180239ef9  mov     [rsi+1A8h], rbx
0x180239f00  lea     rcx, [rsp+148h+var_E8]; this
0x180239f05  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180239f0a  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180239f11  lea     rcx, [rsp+148h+var_E8]; pExceptionObject
0x180239f16  call    _CxxThrowException
0x180239f1b  lea     rcx, [rsi+0C8h]
0x180239f22  mov     [rcx], rbx
0x180239f25  mov     [rsi+0D0h], rdi
0x180239f2c  mov     [rsi+0D8h], rbx
0x180239f33  mov     byte ptr [rsi+0E0h], 1
0x180239f3a  mov     eax, 6
0x180239f3f  mov     [rsi+90h], ax
0x180239f46  mov     rdx, rsi
0x180239f49  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>)
0x180239f4e  test    al, al
0x180239f50  jz      loc_18023A03C
0x180239f56  jmp     loc_18023A225
0x180239f5b  mov     rdi, [rsi+0C8h]; jumptable 0000000180239C5B case 7
0x180239f62  test    rdi, rdi
0x180239f65  jz      short loc_180239F91
0x180239f67  mov     [rsp+148h+var_B8], rdi
0x180239f6f  xor     ebx, ebx
0x180239f71  mov     eax, ebx
0x180239f73  xchg    rax, [rdi]
0x180239f76  cmp     rax, 1
0x180239f7a  jnz     short loc_180239F91
0x180239f7c  nop     dword ptr [rax+00h]
0x180239f80  call    _Thrd_yield
0x180239f85  mov     rax, rbx
0x180239f88  xchg    rax, [rdi]
0x180239f8b  cmp     rax, 1
0x180239f8f  jz      short loc_180239F80
0x180239f91  lea     rcx, [rsi+0C0h]
0x180239f98  mov     rax, [rcx]
0x180239f9b  mov     [rsp+148h+arg_10], rax
0x180239fa3  test    rax, rax
0x180239fa6  jz      short loc_180239FAE
0x180239fa8  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180239fad  nop
0x180239fae  lea     rcx, [rsi+0B8h]
0x180239fb5  mov     rax, [rcx]
0x180239fb8  mov     qword ptr [rsp+148h+var_120+8], rax
0x180239fbd  test    rax, rax
0x180239fc0  jz      short loc_180239FC7
0x180239fc2  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180239fc7  lea     rcx, [rsi+0B0h]
0x180239fce  mov     rax, [rcx]
0x180239fd1  mov     qword ptr [rsp+148h+var_120], rax
0x180239fd6  test    rax, rax
0x180239fd9  jz      short loc_180239FE1
0x180239fdb  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180239fe0  nop
0x180239fe1  cmp     qword ptr [rsi+158h], 0
0x180239fe9  jz      short loc_180239FF8
0x180239feb  lea     rcx, [rsi+0A8h]
0x180239ff2  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180239ff7  nop
0x180239ff8  mov     rcx, [rsi+98h]; hObject
0x180239fff  test    rcx, rcx
0x18023a002  jz      short loc_18023A019
0x18023a004  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18023a008  jz      short loc_18023A019
0x18023a00a  mov     [rsp+148h+arg_8], rcx
0x18023a012  call    cs:__imp_CloseHandle
0x18023a018  nop
0x18023a019  mov     eax, 0FFFFFFFFh
0x18023a01e  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18023a026  sub     eax, 1
0x18023a029  jz      short loc_18023A035
0x18023a02b  test    eax, eax
0x18023a02d  jns     short loc_18023A035
0x18023a02f  call    abort
0x18023a035  jmp     loc_18023A1F0; jumptable 0000000180239C5B cases -1,1
0x18023a03a  xor     ebx, ebx; jumptable 0000000180239C5B case 6
0x18023a03c  lea     rcx, [rsi+0C8h]
0x18023a043  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(void)
0x18023a048  movzx   r14d, al
0x18023a04c  mov     rdi, [rsi+0C8h]
0x18023a053  test    rdi, rdi
0x18023a056  jz      short loc_18023A081
0x18023a058  mov     [rsp+148h+var_B8], rdi
0x18023a060  mov     rcx, rbx
0x18023a063  xchg    rcx, [rdi]
0x18023a066  cmp     rcx, 1
0x18023a06a  jnz     short loc_18023A081
0x18023a06c  nop     dword ptr [rax+00h]
0x18023a070  call    _Thrd_yield
0x18023a075  mov     rax, rbx
0x18023a078  xchg    rax, [rdi]
0x18023a07b  cmp     rax, 1
0x18023a07f  jz      short loc_18023A070
0x18023a081  lea     rcx, [rsi+0C0h]
0x18023a088  mov     rax, [rcx]
0x18023a08b  mov     [rsp+148h+arg_10], rax
0x18023a093  test    rax, rax
0x18023a096  jz      short loc_18023A09E
0x18023a098  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023a09d  nop
0x18023a09e  lea     rcx, [rsi+0B8h]
0x18023a0a5  mov     rax, [rcx]
0x18023a0a8  mov     qword ptr [rsp+148h+var_120+8], rax
0x18023a0ad  test    rax, rax
0x18023a0b0  jz      short loc_18023A0B7
0x18023a0b2  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023a0b7  lea     rcx, [rsi+0B0h]
0x18023a0be  mov     rax, [rcx]
0x18023a0c1  mov     qword ptr [rsp+148h+var_120], rax
0x18023a0c6  test    rax, rax
0x18023a0c9  jz      short loc_18023A0D0
0x18023a0cb  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023a0d0  test    r14b, r14b
0x18023a0d3  jnz     short loc_18023A143
0x18023a0d5  mov     dword ptr [rsi+0E8h], 0FFh
0x18023a0df  lea     rax, aCW1SSrcSemanti_28; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18023a0e6  mov     [rsi+0F0h], rax
0x18023a0ed  mov     [rsi+0F8h], rbx
0x18023a0f4  lea     rdx, aFailedToLoadTe_0; "Failed to load text embedding model - m"...
0x18023a0fb  lea     rcx, [rsi+100h]; this
0x18023a102  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18023a107  lea     rcx, [rsi+120h]; this
0x18023a10e  mov     edx, 83EBAD1Dh; int
0x18023a113  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18023a118  lea     r9, [rsi+0E8h]
0x18023a11f  lea     r8, [rsi+100h]
0x18023a126  mov     edx, [rax]
0x18023a128  lea     rcx, [rsp+148h+var_D0]
0x18023a12d  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18023a132  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18023a139  lea     rcx, [rsp+148h+var_D0]; pExceptionObject
0x18023a13e  call    _CxxThrowException
0x18023a143  lea     r14, [rsi+78h]
  ... truncated ...
```
