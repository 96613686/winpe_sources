# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::CreateAsync$_ResumeCoro$1

- ea: `0x1802411f0`
- end: `0x18024176c`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::CreateAsync$_ResumeCoro$1`
- size: `1404`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18006cb00`
- `0x1802411e0`

## callees

- `0x180003bd0`
- `0x18000d230`
- `0x18000d4b0`
- `0x18001b1f0`
- `0x18001b3c0`
- `0x18001bc40`
- `0x18001d370`
- `0x18001fd80`
- `0x180020e60`
- `0x180047120`
- `0x180047520`
- `0x1800475c0`
- `0x180064e00`
- `0x18006cc30`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f97e0`
- `0x180206a58`
- `0x1802411f0`
- `0x180242120`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1802412eb`
- `KERNEL32!CloseHandle` at `0x1802413ff`
- `KERNEL32!CloseHandle` at `0x18024141d`
- `KERNEL32!CloseHandle` at `0x180241532`
- `KERNEL32!CloseHandle` at `0x1802416a4`
- `KERNEL32!CloseHandle` at `0x1802412eb`
- `KERNEL32!CloseHandle` at `0x1802413ff`
- `KERNEL32!CloseHandle` at `0x18024141d`
- `KERNEL32!CloseHandle` at `0x180241532`
- `KERNEL32!CloseHandle` at `0x1802416a4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1802413e7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1802413e7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1802413a9`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1802413a9`

## string_xrefs

- `0x180241288`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x180241439`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x180241606`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\ImageEmbeddingsGenerator.cpp`

## pseudocode

```c
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::CreateAsync__ResumeCoro_1(
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
      goto LABEL_68;
    case 2:
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      winrt::make<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IndexVectorSpaceIds &>(
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
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::CreateAsync_::_2_::_lambda_1_::operator()(
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
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::CreateAsync_::_2_::_lambda_1_::operator()(
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
      goto LABEL_46;
    case 5:
      v3 = (void *)*((_QWORD *)a1 + 23);
      if ( v3 && v3 != (void *)-1LL )
        CloseHandle(v3);
      if ( *((_QWORD *)a1 + 22) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 88);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      goto LABEL_68;
    case 6:
LABEL_46:
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
        *((_DWORD *)a1 + 62) = 47;
        *((_QWORD *)a1 + 32) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\ImageEmbeddingsGenerator.cpp";
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
        goto LABEL_68;
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
LABEL_68:
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
0x1802411f0  mov     [rsp+Block], rcx
0x1802411f5  push    rbx
0x1802411f6  push    rsi
0x1802411f7  push    rdi
0x1802411f8  push    r12
0x1802411fa  push    r14
0x1802411fc  push    r15
0x1802411fe  sub     rsp, 0E8h
0x180241205  mov     rbx, [rsp+118h+Block]
0x18024120d  movzx   eax, word ptr [rbx+0A4h]
0x180241214  mov     [rsp+118h+var_F8], ax
0x180241219  inc     ax; switch 9 cases
0x18024121c  cmp     ax, 8
0x180241220  ja      def_18024123B; jumptable 000000018024123B default case, case 0
0x180241226  movsx   rax, ax
0x18024122a  lea     rdx, cs:180000000h
0x180241231  mov     ecx, ds:(jpt_18024123B - 180000000h)[rdx+rax*4]
0x180241238  add     rcx, rdx
0x18024123b  jmp     rcx; switch jump
0x18024123d  jmp     loc_180241710; jumptable 000000018024123B case 3
0x180241242  xor     esi, esi; jumptable 000000018024123B case 2
0x180241244  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18024124b  lea     rdx, [rbx+84h]
0x180241252  lea     rcx, [rbx+0B0h]
0x180241259  call    ??$make@UImageEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAUIndexVectorSpaceIds@345678@@winrt@@YA?A_PAEAUIndexVectorSpaceIds@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@0@@Z
0x18024125e  nop
0x18024125f  lea     rcx, [rbx+0B8h]
0x180241266  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x18024126b  nop
0x18024126c  mov     [rbx+0C0h], sil
0x180241273  mov     eax, [rbx+70h]
0x180241276  cmp     eax, 2
0x180241279  jnz     short loc_1802412B8
0x18024127b  lea     rdx, [rbx+138h]; struct winrt::impl::slim_source_location *
0x180241282  mov     dword ptr [rdx], 1628h
0x180241288  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18024128f  mov     [rbx+140h], rax
0x180241296  mov     [rbx+148h], rsi
0x18024129d  lea     rcx, [rsp+118h+pExceptionObject]; this
0x1802412a2  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x1802412a7  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x1802412ae  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x1802412b3  call    _CxxThrowException
0x1802412b8  mov     eax, 4
0x1802412bd  mov     [rbx+0A4h], ax
0x1802412c4  mov     rdx, rbx
0x1802412c7  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x1802412cc  jmp     loc_180241733
0x1802412d1  mov     rcx, [rbx+0B8h]; jumptable 000000018024123B case 5
0x1802412d8  test    rcx, rcx
0x1802412db  jz      short loc_1802412F2
0x1802412dd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1802412e1  jz      short loc_1802412F2
0x1802412e3  mov     [rsp+118h+arg_10], rcx
0x1802412eb  call    cs:__imp_CloseHandle
0x1802412f1  nop
0x1802412f2  lea     rcx, [rbx+0B0h]
0x1802412f9  mov     rax, [rcx]
0x1802412fc  mov     [rsp+118h+arg_8], rax
0x180241304  test    rax, rax
0x180241307  jz      short loc_18024130F
0x180241309  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18024130e  nop
0x18024130f  mov     eax, 0FFFFFFFFh
0x180241314  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18024131c  sub     eax, 1
0x18024131f  jz      short loc_18024132B
0x180241321  test    eax, eax
0x180241323  jns     short loc_18024132B
0x180241325  call    abort
0x18024132b  jmp     loc_180241710; jumptable 000000018024123B cases -1,1
0x180241330  mov     rcx, [rbx+0B0h]; jumptable 000000018024123B case 4
0x180241337  mov     [rbx+0C8h], rcx
0x18024133e  test    rcx, rcx
0x180241341  jz      short loc_180241359
0x180241343  mov     [rsp+118h+arg_8], rcx
0x18024134b  mov     rax, [rcx]
0x18024134e  mov     rax, [rax+8]
0x180241352  call    cs:__guard_dispatch_icall_fptr
0x180241358  nop
0x180241359  mov     rdi, [rbx+0B8h]
0x180241360  test    rdi, rdi
0x180241363  jnz     short loc_180241382
0x180241365  lea     rdi, [rbx+0D0h]
0x18024136c  mov     rdx, rdi
0x18024136f  lea     rcx, [rbx+0C8h]
0x180241376  call    _winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__ImageEmbeddingsGenerator__CreateAsync____2____lambda_1___operator__
0x18024137b  xor     esi, esi
0x18024137d  jmp     loc_180241424
0x180241382  lea     rcx, [rbx+150h]
0x180241389  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x18024138e  nop
0x18024138f  mov     r14, [rbx+150h]
0x180241396  xor     esi, esi
0x180241398  mov     [rbx+150h], rsi
0x18024139f  mov     [rbx+158h], r14
0x1802413a6  mov     rcx, rdi; hToken
0x1802413a9  call    cs:__imp_ImpersonateLoggedOnUser
0x1802413af  mov     rcx, [rsp+118h]; this
0x1802413b7  test    eax, eax
0x1802413b9  jnz     short loc_1802413C5
0x1802413bb  mov     edx, 1Ch; void *
0x1802413c0  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1802413c5  lea     rdi, [rbx+0D0h]
0x1802413cc  mov     rdx, rdi
0x1802413cf  lea     rcx, [rbx+0C8h]
0x1802413d6  call    _winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__ImageEmbeddingsGenerator__CreateAsync____2____lambda_1___operator__
0x1802413db  nop
0x1802413dc  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1802413e0  jz      short loc_180241406
0x1802413e2  mov     rdx, r14; Token
0x1802413e5  xor     ecx, ecx; Thread
0x1802413e7  call    cs:__imp_SetThreadToken
0x1802413ed  test    eax, eax
0x1802413ef  jnz     short loc_1802413F7
0x1802413f1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1802413f7  test    r14, r14
0x1802413fa  jz      short loc_180241406
0x1802413fc  mov     rcx, r14; hObject
0x1802413ff  call    cs:__imp_CloseHandle
0x180241405  nop
0x180241406  mov     rcx, [rbx+150h]; hObject
0x18024140d  test    rcx, rcx
0x180241410  jz      short loc_180241424
0x180241412  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180241416  jz      short loc_180241424
0x180241418  mov     [rsp+118h+var_E8], rcx
0x18024141d  call    cs:__imp_CloseHandle
0x180241423  nop
0x180241424  mov     eax, [rbx+70h]
0x180241427  cmp     eax, 2
0x18024142a  jnz     short loc_180241469
0x18024142c  lea     rdx, [rbx+160h]; struct winrt::impl::slim_source_location *
0x180241433  mov     dword ptr [rdx], 1628h
0x180241439  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180241440  mov     [rbx+168h], rax
0x180241447  mov     [rbx+170h], rsi
0x18024144e  lea     rcx, [rsp+118h+var_C8]; this
0x180241453  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180241458  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18024145f  lea     rcx, [rsp+118h+var_C8]; pExceptionObject
0x180241464  call    _CxxThrowException
0x180241469  lea     rcx, [rbx+0D8h]
0x180241470  mov     [rcx], rsi
0x180241473  mov     [rbx+0E0h], rdi
0x18024147a  mov     qword ptr [rbx+0E8h], 0
0x180241485  mov     byte ptr [rbx+0F0h], 1
0x18024148c  mov     eax, 6
0x180241491  mov     [rbx+0A4h], ax
0x180241498  mov     rdx, rbx
0x18024149b  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>)
0x1802414a0  test    al, al
0x1802414a2  jz      loc_180241579
0x1802414a8  jmp     loc_180241733
0x1802414ad  mov     rdi, [rbx+0D8h]; jumptable 000000018024123B case 7
0x1802414b4  test    rdi, rdi
0x1802414b7  jz      short loc_1802414E1
0x1802414b9  mov     [rsp+118h+var_98], rdi
0x1802414c1  xor     esi, esi
0x1802414c3  mov     eax, esi
0x1802414c5  xchg    rax, [rdi]
0x1802414c8  cmp     rax, 1
0x1802414cc  jnz     short loc_1802414E1
0x1802414ce  xchg    ax, ax
0x1802414d0  call    _Thrd_yield
0x1802414d5  mov     rax, rsi
0x1802414d8  xchg    rax, [rdi]
0x1802414db  cmp     rax, 1
0x1802414df  jz      short loc_1802414D0
0x1802414e1  lea     rcx, [rbx+0D0h]
0x1802414e8  mov     rax, [rcx]
0x1802414eb  mov     [rsp+118h+arg_18], rax
0x1802414f3  test    rax, rax
0x1802414f6  jz      short loc_1802414FE
0x1802414f8  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802414fd  nop
0x1802414fe  lea     rcx, [rbx+0C8h]
0x180241505  mov     rax, [rcx]
0x180241508  mov     [rsp+118h+var_F0], rax
0x18024150d  test    rax, rax
0x180241510  jz      short loc_180241518
0x180241512  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180241517  nop
0x180241518  mov     rcx, [rbx+0B8h]; hObject
0x18024151f  test    rcx, rcx
0x180241522  jz      short loc_180241539
0x180241524  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180241528  jz      short loc_180241539
0x18024152a  mov     [rsp+118h+arg_10], rcx
0x180241532  call    cs:__imp_CloseHandle
0x180241538  nop
0x180241539  lea     rcx, [rbx+0B0h]
0x180241540  mov     rax, [rcx]
0x180241543  mov     [rsp+118h+arg_8], rax
0x18024154b  test    rax, rax
0x18024154e  jz      short loc_180241556
0x180241550  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180241555  nop
0x180241556  mov     eax, 0FFFFFFFFh
0x18024155b  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180241563  sub     eax, 1
0x180241566  jz      short loc_180241572
0x180241568  test    eax, eax
0x18024156a  jns     short loc_180241572
0x18024156c  call    abort
0x180241572  jmp     loc_180241710; jumptable 000000018024123B cases -1,1
0x180241577  xor     esi, esi; jumptable 000000018024123B case 6
0x180241579  lea     rcx, [rbx+0D8h]
0x180241580  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(void)
0x180241585  movzx   r14d, al
0x180241589  mov     rdi, [rbx+0D8h]
0x180241590  test    rdi, rdi
0x180241593  jz      short loc_1802415C1
0x180241595  mov     [rsp+118h+var_98], rdi
0x18024159d  mov     rcx, rsi
0x1802415a0  xchg    rcx, [rdi]
0x1802415a3  cmp     rcx, 1
0x1802415a7  jnz     short loc_1802415C1
0x1802415a9  nop     dword ptr [rax+00000000h]
0x1802415b0  call    _Thrd_yield
0x1802415b5  mov     rax, rsi
0x1802415b8  xchg    rax, [rdi]
0x1802415bb  cmp     rax, 1
0x1802415bf  jz      short loc_1802415B0
0x1802415c1  lea     rcx, [rbx+0D0h]
0x1802415c8  mov     rax, [rcx]
0x1802415cb  mov     [rsp+118h+arg_18], rax
0x1802415d3  test    rax, rax
0x1802415d6  jz      short loc_1802415DE
0x1802415d8  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802415dd  nop
0x1802415de  lea     rcx, [rbx+0C8h]
0x1802415e5  mov     rax, [rcx]
0x1802415e8  mov     [rsp+118h+var_F0], rax
0x1802415ed  test    rax, rax
0x1802415f0  jz      short loc_1802415F7
0x1802415f2  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802415f7  test    r14b, r14b
0x1802415fa  jnz     short loc_180241657
0x1802415fc  mov     dword ptr [rbx+0F8h], 2Fh ; '/'
0x180241606  lea     rax, aCW1SSrcSemanti_10; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18024160d  mov     [rbx+100h], rax
0x180241614  mov     [rbx+108h], rsi
0x18024161b  lea     rdx, aFailedToLoadTe; "Failed to load text embedding model"
0x180241622  lea     rcx, [rbx+110h]; this
0x180241629  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18024162e  lea     r8, [rbx+0F8h]; struct winrt::impl::slim_source_location *
0x180241635  lea     rdx, [rbx+110h]; struct winrt::param::hstring *
0x18024163c  lea     rcx, [rsp+118h+var_B0]; this
0x180241641  call    ??0hresult_access_denied@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180241646  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x18024164d  lea     rcx, [rsp+118h+var_B0]; pExceptionObject
0x180241652  call    _CxxThrowException
0x180241657  lea     r14, [rbx+78h]
0x18024165b  lea     rdi, [rbx+0B0h]
0x180241662  cmp     r14, rdi
0x180241665  jz      short loc_180241687
0x180241667  cmp     qword ptr [r14], 0
0x18024166b  jz      short loc_180241675
0x18024166d  mov     rcx, r14
0x180241670  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180241675  mov     rax, [rdi]
0x180241678  mov     [rdi], rsi
0x18024167b  mov     [r14], rax
0x18024167e  lea     r14, [rbx+0B0h]
0x180241685  jmp     short loc_18024168A
0x180241687  mov     r14, rdi
0x18024168a  mov     rcx, [rbx+0B8h]; hObject
0x180241691  test    rcx, rcx
0x180241694  jz      short loc_1802416AB
0x180241696  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18024169a  jz      short loc_1802416AB
0x18024169c  mov     [rsp+118h+arg_10], rcx
0x1802416a4  call    cs:__imp_CloseHandle
0x1802416aa  nop
0x1802416ab  mov     rax, [rdi]
0x1802416ae  mov     [rsp+118h+arg_8], rax
0x1802416b6  test    rax, rax
0x1802416b9  jz      short loc_1802416C4
0x1802416bb  mov     rcx, r14
0x1802416be  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802416c3  nop
0x1802416c4  mov     eax, 0FFFFFFFFh
0x1802416c9  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1802416d1  sub     eax, 1
0x1802416d4  jz      short loc_1802416E0
0x1802416d6  test    eax, eax
0x1802416d8  jns     short loc_1802416E0
0x1802416da  call    abort
0x1802416e0  jmp     short loc_1802416EC
0x1802416e2  xor     esi, esi
0x1802416e4  mov     rbx, [rsp+118h+Block]
0x1802416ec  lea     rax, [rbx+10h]
0x1802416f0  lea     rcx, [rbx+130h]
0x1802416f7  mov     [rcx], rax
0x1802416fa  xor     eax, eax
0x1802416fc  mov     [rbx+0A4h], ax
0x180241703  mov     [rbx], rsi
0x180241706  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@AEBUQueryEmbeddings@789Asg@Microsoft@4@USemanticQueryOptions@789Asg@Microsoft@4@@std@@U?$IAsyncOperation@UQueryResult@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryEmbeddings const &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticQueryOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x18024170b  test    al, al
  ... truncated ...
```
