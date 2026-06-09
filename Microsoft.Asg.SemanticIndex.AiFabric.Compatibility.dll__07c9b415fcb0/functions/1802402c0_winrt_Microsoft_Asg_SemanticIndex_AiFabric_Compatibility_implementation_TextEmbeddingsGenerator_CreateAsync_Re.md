# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::CreateAsync$_ResumeCoro$1

- ea: `0x1802402c0`
- end: `0x18024083c`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::CreateAsync$_ResumeCoro$1`
- size: `1404`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180060a50`
- `0x1802402b0`

## callees

- `0x180003bd0`
- `0x18000d230`
- `0x18000d4b0`
- `0x18001b1f0`
- `0x18001b3c0`
- `0x18001bc40`
- `0x18001d420`
- `0x18001fd80`
- `0x180020e60`
- `0x180047120`
- `0x180047520`
- `0x1800475c0`
- `0x180060b80`
- `0x180064e00`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f97e0`
- `0x180206a58`
- `0x1802402c0`
- `0x180242120`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1802403bb`
- `KERNEL32!CloseHandle` at `0x1802404cf`
- `KERNEL32!CloseHandle` at `0x1802404ed`
- `KERNEL32!CloseHandle` at `0x180240602`
- `KERNEL32!CloseHandle` at `0x180240774`
- `KERNEL32!CloseHandle` at `0x1802403bb`
- `KERNEL32!CloseHandle` at `0x1802404cf`
- `KERNEL32!CloseHandle` at `0x1802404ed`
- `KERNEL32!CloseHandle` at `0x180240602`
- `KERNEL32!CloseHandle` at `0x180240774`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1802404b7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1802404b7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180240479`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180240479`

## string_xrefs

- `0x180240358`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x180240509`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x1802406d6`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\TextEmbeddingsGenerator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::CreateAsync__ResumeCoro_1(
        _WORD *a1)
{
  __int64 v2; // rcx
  void *v3; // rcx
  __int64 v4; // rcx
  void *v5; // rdi
  _WORD *v6; // rdi
  void *v7; // r14
  unsigned int v8; // r8d
  const char *v9; // r9
  wil::details::in1diag3 *v10; // rcx
  void *v11; // rcx
  volatile __int64 *v12; // rdi
  void *v13; // rcx
  char v14; // r14
  volatile __int64 *v15; // rdi
  _QWORD *v16; // r14
  __int64 *v17; // rdi
  __int64 v18; // rax
  _WORD *v19; // r14
  void *v20; // rcx
  _BYTE pExceptionObject[24]; // [rsp+38h] [rbp-E0h] BYREF
  _BYTE v22[24]; // [rsp+50h] [rbp-C8h] BYREF
  _BYTE v23[24]; // [rsp+68h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+80h] [rbp-98h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  switch ( a1[82] )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_66;
    case 2:
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      winrt::make<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IndexVectorSpaceIds &>(
        a1 + 88,
        a1 + 66);
      ImpersonationHelper::GetThreadImpersonationToken(a1 + 92);
      *((_BYTE *)a1 + 192) = 0;
      if ( *((_DWORD *)a1 + 28) == 2 )
      {
        *((_DWORD *)a1 + 78) = 5672;
        *((_QWORD *)a1 + 40) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generate"
                               "d Files\\winrt\\Windows.Foundation.h";
        *((_QWORD *)a1 + 41) = 0;
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)pExceptionObject,
          (const struct winrt::impl::slim_source_location *)(a1 + 156));
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      a1[82] = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v2, a1);
      return;
    case 4:
      v4 = *((_QWORD *)a1 + 22);
      *((_QWORD *)a1 + 25) = v4;
      if ( v4 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
      v5 = (void *)*((_QWORD *)a1 + 23);
      if ( v5 )
      {
        ImpersonationHelper::GetThreadImpersonationToken(a1 + 168);
        v7 = (void *)*((_QWORD *)a1 + 42);
        *((_QWORD *)a1 + 42) = 0;
        *((_QWORD *)a1 + 43) = v7;
        if ( !ImpersonateLoggedOnUser(v5) )
          wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x1C, v8, v9);
        v6 = a1 + 104;
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::CreateAsync_::_2_::_lambda_1_::operator()(
          a1 + 100,
          a1 + 104);
        if ( v7 != (void *)-1LL )
        {
          if ( !SetThreadToken(0, v7) )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(v10);
          if ( v7 )
            CloseHandle(v7);
        }
        v11 = (void *)*((_QWORD *)a1 + 42);
        if ( v11 && v11 != (void *)-1LL )
          CloseHandle(v11);
      }
      else
      {
        v6 = a1 + 104;
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::CreateAsync_::_2_::_lambda_1_::operator()(
          a1 + 100,
          a1 + 104);
      }
      if ( *((_DWORD *)a1 + 28) == 2 )
      {
        *((_DWORD *)a1 + 88) = 5672;
        *((_QWORD *)a1 + 45) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generate"
                               "d Files\\winrt\\Windows.Foundation.h";
        *((_QWORD *)a1 + 46) = 0;
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)v22,
          (const struct winrt::impl::slim_source_location *)(a1 + 176));
        throw (winrt::hresult_canceled *)v22;
      }
      *((_QWORD *)a1 + 27) = 0;
      *((_QWORD *)a1 + 28) = v6;
      *((_QWORD *)a1 + 29) = 0;
      *((_BYTE *)a1 + 240) = 1;
      a1[82] = 6;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>(
                              (_QWORD *)a1 + 27,
                              (__int64)a1) )
        return;
      goto LABEL_44;
    case 5:
      v3 = (void *)*((_QWORD *)a1 + 23);
      if ( v3 && v3 != (void *)-1LL )
        CloseHandle(v3);
      if ( *((_QWORD *)a1 + 22) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 88);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      goto LABEL_66;
    case 6:
LABEL_44:
      v14 = winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(a1 + 108);
      v15 = (volatile __int64 *)*((_QWORD *)a1 + 27);
      if ( v15 )
      {
        v24 = *((_QWORD *)a1 + 27);
        while ( _InterlockedExchange64(v15, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 26) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 104);
      if ( *((_QWORD *)a1 + 25) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 100);
      if ( !v14 )
      {
        *((_DWORD *)a1 + 62) = 52;
        *((_QWORD *)a1 + 32) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\TextEmbeddingsGenerator.cpp";
        *((_QWORD *)a1 + 33) = 0;
        winrt::param::hstring::hstring((winrt::param::hstring *)(a1 + 136), L"Failed to load text embedding model");
        winrt::hresult_access_denied::hresult_access_denied(
          (winrt::hresult_access_denied *)v23,
          (const struct winrt::param::hstring *)(a1 + 136),
          (const struct winrt::impl::slim_source_location *)(a1 + 124));
        throw (winrt::hresult_access_denied *)v23;
      }
      v16 = a1 + 60;
      v17 = (__int64 *)(a1 + 88);
      if ( a1 + 60 == a1 + 88 )
      {
        v19 = a1 + 88;
      }
      else
      {
        if ( *v16 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 60);
        v18 = *v17;
        *v17 = 0;
        *v16 = v18;
        v19 = a1 + 88;
      }
      v20 = (void *)*((_QWORD *)a1 + 23);
      if ( v20 && v20 != (void *)-1LL )
        CloseHandle(v20);
      if ( *v17 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v19);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      *((_QWORD *)a1 + 38) = a1 + 8;
      a1[82] = 0;
      *(_QWORD *)a1 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryEmbeddings const &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticQueryOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,void>::final_suspend_awaiter::await_suspend(a1 + 152) )
        goto LABEL_66;
      return;
    case 7:
      v12 = (volatile __int64 *)*((_QWORD *)a1 + 27);
      if ( v12 )
      {
        v24 = *((_QWORD *)a1 + 27);
        while ( _InterlockedExchange64(v12, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 26) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 104);
      if ( *((_QWORD *)a1 + 25) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 100);
      v13 = (void *)*((_QWORD *)a1 + 23);
      if ( v13 && v13 != (void *)-1LL )
        CloseHandle(v13);
      if ( *((_QWORD *)a1 + 22) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 88);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
LABEL_66:
      std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type::~promise_type(a1 + 8);
      if ( a1[83] )
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
0x1802402c0  mov     [rsp+Block], rcx
0x1802402c5  push    rbx
0x1802402c6  push    rsi
0x1802402c7  push    rdi
0x1802402c8  push    r12
0x1802402ca  push    r14
0x1802402cc  push    r15
0x1802402ce  sub     rsp, 0E8h
0x1802402d5  mov     rbx, [rsp+118h+Block]
0x1802402dd  movzx   eax, word ptr [rbx+0A4h]
0x1802402e4  mov     [rsp+118h+var_F8], ax
0x1802402e9  inc     ax; switch 9 cases
0x1802402ec  cmp     ax, 8
0x1802402f0  ja      def_18024030B; jumptable 000000018024030B default case, case 0
0x1802402f6  movsx   rax, ax
0x1802402fa  lea     rdx, cs:180000000h
0x180240301  mov     ecx, ds:(jpt_18024030B - 180000000h)[rdx+rax*4]
0x180240308  add     rcx, rdx
0x18024030b  jmp     rcx; switch jump
0x18024030d  jmp     loc_1802407E0; jumptable 000000018024030B case 3
0x180240312  xor     esi, esi; jumptable 000000018024030B case 2
0x180240314  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18024031b  lea     rdx, [rbx+84h]
0x180240322  lea     rcx, [rbx+0B0h]
0x180240329  call    ??$make@UTextEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAUIndexVectorSpaceIds@345678@@winrt@@YA?A_PAEAUIndexVectorSpaceIds@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@0@@Z
0x18024032e  nop
0x18024032f  lea     rcx, [rbx+0B8h]
0x180240336  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x18024033b  nop
0x18024033c  mov     [rbx+0C0h], sil
0x180240343  mov     eax, [rbx+70h]
0x180240346  cmp     eax, 2
0x180240349  jnz     short loc_180240388
0x18024034b  lea     rdx, [rbx+138h]; struct winrt::impl::slim_source_location *
0x180240352  mov     dword ptr [rdx], 1628h
0x180240358  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18024035f  mov     [rbx+140h], rax
0x180240366  mov     [rbx+148h], rsi
0x18024036d  lea     rcx, [rsp+118h+pExceptionObject]; this
0x180240372  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180240377  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18024037e  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x180240383  call    _CxxThrowException
0x180240388  mov     eax, 4
0x18024038d  mov     [rbx+0A4h], ax
0x180240394  mov     rdx, rbx
0x180240397  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x18024039c  jmp     loc_180240803
0x1802403a1  mov     rcx, [rbx+0B8h]; jumptable 000000018024030B case 5
0x1802403a8  test    rcx, rcx
0x1802403ab  jz      short loc_1802403C2
0x1802403ad  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1802403b1  jz      short loc_1802403C2
0x1802403b3  mov     [rsp+118h+arg_10], rcx
0x1802403bb  call    cs:__imp_CloseHandle
0x1802403c1  nop
0x1802403c2  lea     rcx, [rbx+0B0h]
0x1802403c9  mov     rax, [rcx]
0x1802403cc  mov     [rsp+118h+arg_8], rax
0x1802403d4  test    rax, rax
0x1802403d7  jz      short loc_1802403DF
0x1802403d9  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802403de  nop
0x1802403df  mov     eax, 0FFFFFFFFh
0x1802403e4  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1802403ec  sub     eax, 1
0x1802403ef  jz      short loc_1802403FB
0x1802403f1  test    eax, eax
0x1802403f3  jns     short loc_1802403FB
0x1802403f5  call    abort
0x1802403fb  jmp     loc_1802407E0; jumptable 000000018024030B cases -1,1
0x180240400  mov     rcx, [rbx+0B0h]; jumptable 000000018024030B case 4
0x180240407  mov     [rbx+0C8h], rcx
0x18024040e  test    rcx, rcx
0x180240411  jz      short loc_180240429
0x180240413  mov     [rsp+118h+arg_8], rcx
0x18024041b  mov     rax, [rcx]
0x18024041e  mov     rax, [rax+8]
0x180240422  call    cs:__guard_dispatch_icall_fptr
0x180240428  nop
0x180240429  mov     rdi, [rbx+0B8h]
0x180240430  test    rdi, rdi
0x180240433  jnz     short loc_180240452
0x180240435  lea     rdi, [rbx+0D0h]
0x18024043c  mov     rdx, rdi
0x18024043f  lea     rcx, [rbx+0C8h]
0x180240446  call    _winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__TextEmbeddingsGenerator__CreateAsync____2____lambda_1___operator__
0x18024044b  xor     esi, esi
0x18024044d  jmp     loc_1802404F4
0x180240452  lea     rcx, [rbx+150h]
0x180240459  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x18024045e  nop
0x18024045f  mov     r14, [rbx+150h]
0x180240466  xor     esi, esi
0x180240468  mov     [rbx+150h], rsi
0x18024046f  mov     [rbx+158h], r14
0x180240476  mov     rcx, rdi; hToken
0x180240479  call    cs:__imp_ImpersonateLoggedOnUser
0x18024047f  mov     rcx, [rsp+118h]; this
0x180240487  test    eax, eax
0x180240489  jnz     short loc_180240495
0x18024048b  mov     edx, 1Ch; void *
0x180240490  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180240495  lea     rdi, [rbx+0D0h]
0x18024049c  mov     rdx, rdi
0x18024049f  lea     rcx, [rbx+0C8h]
0x1802404a6  call    _winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__TextEmbeddingsGenerator__CreateAsync____2____lambda_1___operator__
0x1802404ab  nop
0x1802404ac  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1802404b0  jz      short loc_1802404D6
0x1802404b2  mov     rdx, r14; Token
0x1802404b5  xor     ecx, ecx; Thread
0x1802404b7  call    cs:__imp_SetThreadToken
0x1802404bd  test    eax, eax
0x1802404bf  jnz     short loc_1802404C7
0x1802404c1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1802404c7  test    r14, r14
0x1802404ca  jz      short loc_1802404D6
0x1802404cc  mov     rcx, r14; hObject
0x1802404cf  call    cs:__imp_CloseHandle
0x1802404d5  nop
0x1802404d6  mov     rcx, [rbx+150h]; hObject
0x1802404dd  test    rcx, rcx
0x1802404e0  jz      short loc_1802404F4
0x1802404e2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1802404e6  jz      short loc_1802404F4
0x1802404e8  mov     [rsp+118h+var_E8], rcx
0x1802404ed  call    cs:__imp_CloseHandle
0x1802404f3  nop
0x1802404f4  mov     eax, [rbx+70h]
0x1802404f7  cmp     eax, 2
0x1802404fa  jnz     short loc_180240539
0x1802404fc  lea     rdx, [rbx+160h]; struct winrt::impl::slim_source_location *
0x180240503  mov     dword ptr [rdx], 1628h
0x180240509  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180240510  mov     [rbx+168h], rax
0x180240517  mov     [rbx+170h], rsi
0x18024051e  lea     rcx, [rsp+118h+var_C8]; this
0x180240523  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180240528  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18024052f  lea     rcx, [rsp+118h+var_C8]; pExceptionObject
0x180240534  call    _CxxThrowException
0x180240539  lea     rcx, [rbx+0D8h]
0x180240540  mov     [rcx], rsi
0x180240543  mov     [rbx+0E0h], rdi
0x18024054a  mov     qword ptr [rbx+0E8h], 0
0x180240555  mov     byte ptr [rbx+0F0h], 1
0x18024055c  mov     eax, 6
0x180240561  mov     [rbx+0A4h], ax
0x180240568  mov     rdx, rbx
0x18024056b  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>)
0x180240570  test    al, al
0x180240572  jz      loc_180240649
0x180240578  jmp     loc_180240803
0x18024057d  mov     rdi, [rbx+0D8h]; jumptable 000000018024030B case 7
0x180240584  test    rdi, rdi
0x180240587  jz      short loc_1802405B1
0x180240589  mov     [rsp+118h+var_98], rdi
0x180240591  xor     esi, esi
0x180240593  mov     eax, esi
0x180240595  xchg    rax, [rdi]
0x180240598  cmp     rax, 1
0x18024059c  jnz     short loc_1802405B1
0x18024059e  xchg    ax, ax
0x1802405a0  call    _Thrd_yield
0x1802405a5  mov     rax, rsi
0x1802405a8  xchg    rax, [rdi]
0x1802405ab  cmp     rax, 1
0x1802405af  jz      short loc_1802405A0
0x1802405b1  lea     rcx, [rbx+0D0h]
0x1802405b8  mov     rax, [rcx]
0x1802405bb  mov     [rsp+118h+arg_18], rax
0x1802405c3  test    rax, rax
0x1802405c6  jz      short loc_1802405CE
0x1802405c8  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802405cd  nop
0x1802405ce  lea     rcx, [rbx+0C8h]
0x1802405d5  mov     rax, [rcx]
0x1802405d8  mov     [rsp+118h+var_F0], rax
0x1802405dd  test    rax, rax
0x1802405e0  jz      short loc_1802405E8
0x1802405e2  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802405e7  nop
0x1802405e8  mov     rcx, [rbx+0B8h]; hObject
0x1802405ef  test    rcx, rcx
0x1802405f2  jz      short loc_180240609
0x1802405f4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1802405f8  jz      short loc_180240609
0x1802405fa  mov     [rsp+118h+arg_10], rcx
0x180240602  call    cs:__imp_CloseHandle
0x180240608  nop
0x180240609  lea     rcx, [rbx+0B0h]
0x180240610  mov     rax, [rcx]
0x180240613  mov     [rsp+118h+arg_8], rax
0x18024061b  test    rax, rax
0x18024061e  jz      short loc_180240626
0x180240620  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180240625  nop
0x180240626  mov     eax, 0FFFFFFFFh
0x18024062b  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180240633  sub     eax, 1
0x180240636  jz      short loc_180240642
0x180240638  test    eax, eax
0x18024063a  jns     short loc_180240642
0x18024063c  call    abort
0x180240642  jmp     loc_1802407E0; jumptable 000000018024030B cases -1,1
0x180240647  xor     esi, esi; jumptable 000000018024030B case 6
0x180240649  lea     rcx, [rbx+0D8h]
0x180240650  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(void)
0x180240655  movzx   r14d, al
0x180240659  mov     rdi, [rbx+0D8h]
0x180240660  test    rdi, rdi
0x180240663  jz      short loc_180240691
0x180240665  mov     [rsp+118h+var_98], rdi
0x18024066d  mov     rcx, rsi
0x180240670  xchg    rcx, [rdi]
0x180240673  cmp     rcx, 1
0x180240677  jnz     short loc_180240691
0x180240679  nop     dword ptr [rax+00000000h]
0x180240680  call    _Thrd_yield
0x180240685  mov     rax, rsi
0x180240688  xchg    rax, [rdi]
0x18024068b  cmp     rax, 1
0x18024068f  jz      short loc_180240680
0x180240691  lea     rcx, [rbx+0D0h]
0x180240698  mov     rax, [rcx]
0x18024069b  mov     [rsp+118h+arg_18], rax
0x1802406a3  test    rax, rax
0x1802406a6  jz      short loc_1802406AE
0x1802406a8  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802406ad  nop
0x1802406ae  lea     rcx, [rbx+0C8h]
0x1802406b5  mov     rax, [rcx]
0x1802406b8  mov     [rsp+118h+var_F0], rax
0x1802406bd  test    rax, rax
0x1802406c0  jz      short loc_1802406C7
0x1802406c2  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802406c7  test    r14b, r14b
0x1802406ca  jnz     short loc_180240727
0x1802406cc  mov     dword ptr [rbx+0F8h], 34h ; '4'
0x1802406d6  lea     rax, aCW1SSrcSemanti_1; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x1802406dd  mov     [rbx+100h], rax
0x1802406e4  mov     [rbx+108h], rsi
0x1802406eb  lea     rdx, aFailedToLoadTe; "Failed to load text embedding model"
0x1802406f2  lea     rcx, [rbx+110h]; this
0x1802406f9  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x1802406fe  lea     r8, [rbx+0F8h]; struct winrt::impl::slim_source_location *
0x180240705  lea     rdx, [rbx+110h]; struct winrt::param::hstring *
0x18024070c  lea     rcx, [rsp+118h+var_B0]; this
0x180240711  call    ??0hresult_access_denied@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180240716  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x18024071d  lea     rcx, [rsp+118h+var_B0]; pExceptionObject
0x180240722  call    _CxxThrowException
0x180240727  lea     r14, [rbx+78h]
0x18024072b  lea     rdi, [rbx+0B0h]
0x180240732  cmp     r14, rdi
0x180240735  jz      short loc_180240757
0x180240737  cmp     qword ptr [r14], 0
0x18024073b  jz      short loc_180240745
0x18024073d  mov     rcx, r14
0x180240740  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180240745  mov     rax, [rdi]
0x180240748  mov     [rdi], rsi
0x18024074b  mov     [r14], rax
0x18024074e  lea     r14, [rbx+0B0h]
0x180240755  jmp     short loc_18024075A
0x180240757  mov     r14, rdi
0x18024075a  mov     rcx, [rbx+0B8h]; hObject
0x180240761  test    rcx, rcx
0x180240764  jz      short loc_18024077B
0x180240766  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18024076a  jz      short loc_18024077B
0x18024076c  mov     [rsp+118h+arg_10], rcx
0x180240774  call    cs:__imp_CloseHandle
0x18024077a  nop
0x18024077b  mov     rax, [rdi]
0x18024077e  mov     [rsp+118h+arg_8], rax
0x180240786  test    rax, rax
0x180240789  jz      short loc_180240794
0x18024078b  mov     rcx, r14
0x18024078e  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180240793  nop
0x180240794  mov     eax, 0FFFFFFFFh
0x180240799  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1802407a1  sub     eax, 1
0x1802407a4  jz      short loc_1802407B0
0x1802407a6  test    eax, eax
0x1802407a8  jns     short loc_1802407B0
0x1802407aa  call    abort
0x1802407b0  jmp     short loc_1802407BC
0x1802407b2  xor     esi, esi
0x1802407b4  mov     rbx, [rsp+118h+Block]
0x1802407bc  lea     rax, [rbx+10h]
0x1802407c0  lea     rcx, [rbx+130h]
0x1802407c7  mov     [rcx], rax
0x1802407ca  xor     eax, eax
0x1802407cc  mov     [rbx+0A4h], ax
0x1802407d3  mov     [rbx], rsi
0x1802407d6  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@AEBUQueryEmbeddings@789Asg@Microsoft@4@USemanticQueryOptions@789Asg@Microsoft@4@@std@@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryEmbeddings const &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticQueryOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x1802407db  test    al, al
  ... truncated ...
```
