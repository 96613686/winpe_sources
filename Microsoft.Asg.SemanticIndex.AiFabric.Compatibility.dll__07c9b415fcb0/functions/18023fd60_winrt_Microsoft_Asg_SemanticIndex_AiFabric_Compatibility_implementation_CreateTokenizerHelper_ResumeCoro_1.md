# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateTokenizerHelper$_ResumeCoro$1

- ea: `0x18023fd60`
- end: `0x1802402ac`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateTokenizerHelper$_ResumeCoro$1`
- size: `1356`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180059eb0`
- `0x18023fd50`

## callees

- `0x180003bd0`
- `0x18000d4b0`
- `0x18000e5a0`
- `0x18001b3c0`
- `0x180047120`
- `0x1800475c0`
- `0x180059a40`
- `0x180059b60`
- `0x18005b9d0`
- `0x18005c030`
- `0x18005c5c0`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180206a58`
- `0x18023fd60`
- `0x180242120`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18023fe1a`
- `KERNEL32!CloseHandle` at `0x18023ff07`
- `KERNEL32!CloseHandle` at `0x18023ff25`
- `KERNEL32!CloseHandle` at `0x18023ffe5`
- `KERNEL32!CloseHandle` at `0x18024022e`
- `KERNEL32!CloseHandle` at `0x18023fe1a`
- `KERNEL32!CloseHandle` at `0x18023ff07`
- `KERNEL32!CloseHandle` at `0x18023ff25`
- `KERNEL32!CloseHandle` at `0x18023ffe5`
- `KERNEL32!CloseHandle` at `0x18024022e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18023feef`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18023feef`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18023feae`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18023feae`

## string_xrefs

- `0x18024008b`: `Factory failed to create a tokenizer; no error was reported.`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateTokenizerHelper__ResumeCoro_1(
        __int64 a1)
{
  __int64 *v2; // rcx
  __int64 v3; // rax
  void *v4; // rcx
  __int64 v5; // rcx
  void *v6; // rsi
  __int64 v7; // rsi
  void *v8; // r14
  unsigned int v9; // r8d
  const char *v10; // r9
  wil::details::in1diag3 *v11; // rcx
  void *v12; // rcx
  volatile __int64 *v13; // rsi
  void *v14; // rcx
  volatile __int64 *v15; // rsi
  char *v16; // rsi
  _QWORD *v17; // r14
  __int64 v18; // rbx
  volatile signed __int32 *v19; // r14
  void *v20; // rcx
  _BYTE pExceptionObject[80]; // [rsp+78h] [rbp-170h] BYREF
  char *v22; // [rsp+C8h] [rbp-120h]
  __int64 v23; // [rsp+D8h] [rbp-110h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  switch ( *(_WORD *)(a1 + 40) )
  {
    case 0xFFFF:
    case 3:
      goto LABEL_64;
    case 2:
      *(_DWORD *)(a1 + 472) = 0;
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      ImpersonationHelper::GetThreadImpersonationToken(a1 + 48);
      v2 = *(__int64 **)(a1 + 32);
      v3 = *v2;
      *v2 = 0;
      *(_QWORD *)(a1 + 56) = v3;
      *(_BYTE *)(a1 + 64) = 0;
      *(_BYTE *)(a1 + 72) = *((_BYTE *)v2 + 16);
      *(_BYTE *)(a1 + 80) = 0;
      *(_WORD *)(a1 + 40) = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v2, a1);
      return;
    case 4:
      v5 = *(_QWORD *)(a1 + 24);
      *(_QWORD *)(a1 + 88) = v5;
      if ( v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
      v6 = *(void **)(a1 + 48);
      if ( v6 )
      {
        ImpersonationHelper::GetThreadImpersonationToken(a1 + 456);
        v8 = *(void **)(a1 + 456);
        *(_QWORD *)(a1 + 456) = 0;
        *(_QWORD *)(a1 + 464) = v8;
        if ( !ImpersonateLoggedOnUser(v6) )
          wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x1C, v9, v10);
        v7 = a1 + 96;
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateTokenizerHelper_::_3_::_lambda_1_::operator()(
          a1 + 88,
          a1 + 96);
        *(_DWORD *)(a1 + 472) = 1;
        if ( v8 != (void *)-1LL )
        {
          if ( !SetThreadToken(0, v8) )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(v11);
          if ( v8 )
            CloseHandle(v8);
        }
        v12 = *(void **)(a1 + 456);
        if ( v12 && v12 != (void *)-1LL )
          CloseHandle(v12);
      }
      else
      {
        v7 = a1 + 96;
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateTokenizerHelper_::_3_::_lambda_1_::operator()(
          a1 + 88,
          a1 + 96);
        *(_DWORD *)(a1 + 472) = 1;
      }
      *(_QWORD *)(a1 + 104) = 0;
      *(_QWORD *)(a1 + 112) = v7;
      *(_QWORD *)(a1 + 120) = 0;
      *(_BYTE *)(a1 + 128) = 1;
      *(_WORD *)(a1 + 40) = 6;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextTokenizer>,1>::await_suspend<std::coroutine_traits<winrt::fire_and_forget,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory,std::promise<std::shared_ptr<asg::SemanticRegistry::ITokenizer>> &&>::promise_type>() )
        return;
      goto LABEL_36;
    case 5:
      std::promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>::~promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>(a1 + 56);
      v4 = *(void **)(a1 + 48);
      if ( v4 && v4 != (void *)-1LL )
        CloseHandle(v4);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      goto LABEL_64;
    case 6:
LABEL_36:
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,1>::await_resume(
        a1 + 104,
        a1 + 136);
      v15 = *(volatile __int64 **)(a1 + 104);
      if ( v15 )
      {
        v23 = *(_QWORD *)(a1 + 104);
        while ( _InterlockedExchange64(v15, 0) == 1 )
          Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 96) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 96);
      if ( *(_QWORD *)(a1 + 88) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 88);
      if ( !*(_QWORD *)(a1 + 136) )
      {
        std::runtime_error::runtime_error(
          (std::runtime_error *)pExceptionObject,
          "Factory failed to create a tokenizer; no error was reported.");
        throw (std::runtime_error *)pExceptionObject;
      }
      v16 = (char *)operator new(0x20u);
      *((_DWORD *)v16 + 2) = 1;
      *((_DWORD *)v16 + 3) = 1;
      *(_QWORD *)v16 = &std::_Ref_count_obj2<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextTokenizerWrapper>::`vftable';
      v17 = v16 + 16;
      v18 = *(_QWORD *)(a1 + 136);
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
      *v17 = &winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextTokenizerWrapper::`vftable';
      *((_QWORD *)v16 + 3) = v18;
      *(_DWORD *)(a1 + 472) = 3;
      *(_QWORD *)(a1 + 144) = v17;
      *(_QWORD *)(a1 + 152) = v16;
      if ( v16 )
        _InterlockedIncrement((volatile signed __int32 *)v16 + 2);
      v22 = v16 + 16;
      *(_QWORD *)(a1 + 160) = v17;
      *(_QWORD *)(a1 + 168) = v16;
      std::promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>::set_value(a1 + 56);
      v19 = *(volatile signed __int32 **)(a1 + 168);
      if ( v19 )
      {
        if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
          if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
        }
      }
      if ( v16 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v16 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(void *))v16)(v16);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v16 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(char *))(*(_QWORD *)v16 + 8LL))(v16);
        }
      }
      if ( *(_QWORD *)(a1 + 136) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 136);
      std::promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>::~promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>(a1 + 56);
      v20 = *(void **)(a1 + 48);
      if ( v20 && v20 != (void *)-1LL )
        CloseHandle(v20);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      goto LABEL_64;
    case 7:
      v13 = *(volatile __int64 **)(a1 + 104);
      if ( v13 )
      {
        v23 = *(_QWORD *)(a1 + 104);
        while ( _InterlockedExchange64(v13, 0) == 1 )
          Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 96) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 96);
      if ( *(_QWORD *)(a1 + 88) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 88);
      std::promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>::~promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>(a1 + 56);
      v14 = *(void **)(a1 + 48);
      if ( v14 && v14 != (void *)-1LL )
        CloseHandle(v14);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
LABEL_64:
      if ( *(_QWORD *)(a1 + 24) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 24);
      if ( *(_WORD *)(a1 + 42) )
        operator delete((void *)a1);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x18023fd60  mov     [rsp+Block], rcx
0x18023fd65  push    rbx
0x18023fd66  push    rsi
0x18023fd67  push    rdi
0x18023fd68  push    r12
0x18023fd6a  push    r14
0x18023fd6c  push    r15
0x18023fd6e  sub     rsp, 1B8h
0x18023fd75  mov     rdi, [rsp+1E8h+Block]
0x18023fd7d  movzx   eax, word ptr [rdi+28h]
0x18023fd81  mov     [rsp+1E8h+var_1C0], ax
0x18023fd86  inc     ax; switch 9 cases
0x18023fd89  cmp     ax, 8
0x18023fd8d  ja      def_18023FDA8; jumptable 000000018023FDA8 default case, cases 0,1
0x18023fd93  movsx   rax, ax
0x18023fd97  lea     rdx, cs:180000000h
0x18023fd9e  mov     ecx, ds:(jpt_18023FDA8 - 180000000h)[rdx+rax*4]
0x18023fda5  add     rcx, rdx
0x18023fda8  jmp     rcx; switch jump
0x18023fdaa  jmp     loc_180240250; jumptable 000000018023FDA8 case 3
0x18023fdaf  xor     ebx, ebx; jumptable 000000018023FDA8 case 2
0x18023fdb1  mov     [rdi+1D8h], ebx
0x18023fdb7  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18023fdbe  lea     rcx, [rdi+30h]
0x18023fdc2  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x18023fdc7  nop
0x18023fdc8  mov     rcx, [rdi+20h]
0x18023fdcc  mov     rax, [rcx]
0x18023fdcf  mov     [rcx], rbx
0x18023fdd2  mov     [rdi+38h], rax
0x18023fdd6  mov     [rdi+40h], bl
0x18023fdd9  movzx   eax, byte ptr [rcx+10h]
0x18023fddd  mov     [rdi+48h], al
0x18023fde0  mov     [rdi+50h], bl
0x18023fde3  mov     eax, 4
0x18023fde8  mov     [rdi+28h], ax
0x18023fdec  mov     rdx, rdi
0x18023fdef  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x18023fdf4  jmp     loc_180240276
0x18023fdf9  lea     rcx, [rdi+38h]; jumptable 000000018023FDA8 case 5
0x18023fdfd  call    ??1?$promise@V?$shared_ptr@UIImageModelAccessor@SemanticPipelines@asg@@@std@@@std@@QEAA@XZ; std::promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>::~promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>(void)
0x18023fe02  nop
0x18023fe03  mov     rcx, [rdi+30h]; hObject
0x18023fe07  test    rcx, rcx
0x18023fe0a  jz      short loc_18023FE21
0x18023fe0c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18023fe10  jz      short loc_18023FE21
0x18023fe12  mov     [rsp+1E8h+arg_10], rcx
0x18023fe1a  call    cs:__imp_CloseHandle
0x18023fe20  nop
0x18023fe21  mov     ebx, 0FFFFFFFFh
0x18023fe26  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ebx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18023fe2e  sub     ebx, 1
0x18023fe31  jz      short loc_18023FE3D
0x18023fe33  test    ebx, ebx
0x18023fe35  jns     short loc_18023FE3D
0x18023fe37  call    abort
0x18023fe3d  jmp     loc_180240250; jumptable 000000018023FDA8 case -1
0x18023fe42  mov     rcx, [rdi+18h]; jumptable 000000018023FDA8 case 4
0x18023fe46  mov     [rdi+58h], rcx
0x18023fe4a  test    rcx, rcx
0x18023fe4d  jz      short loc_18023FE5D
0x18023fe4f  mov     rax, [rcx]
0x18023fe52  mov     rax, [rax+8]
0x18023fe56  call    cs:__guard_dispatch_icall_fptr
0x18023fe5c  nop
0x18023fe5d  mov     rsi, [rdi+30h]
0x18023fe61  test    rsi, rsi
0x18023fe64  jnz     short loc_18023FE87
0x18023fe66  lea     rsi, [rdi+60h]
0x18023fe6a  mov     rdx, rsi
0x18023fe6d  lea     rcx, [rdi+58h]
0x18023fe71  call    _winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__CreateTokenizerHelper____3____lambda_1___operator__
0x18023fe76  mov     dword ptr [rdi+1D8h], 1
0x18023fe80  xor     ebx, ebx
0x18023fe82  jmp     loc_18023FF2C
0x18023fe87  lea     rcx, [rdi+1C8h]
0x18023fe8e  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x18023fe93  nop
0x18023fe94  mov     r14, [rdi+1C8h]
0x18023fe9b  xor     ebx, ebx
0x18023fe9d  mov     [rdi+1C8h], rbx
0x18023fea4  mov     [rdi+1D0h], r14
0x18023feab  mov     rcx, rsi; hToken
0x18023feae  call    cs:__imp_ImpersonateLoggedOnUser
0x18023feb4  mov     rcx, [rsp+1E8h]; this
0x18023febc  test    eax, eax
0x18023febe  jnz     short loc_18023FECA
0x18023fec0  mov     edx, 1Ch; void *
0x18023fec5  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18023feca  lea     rsi, [rdi+60h]
0x18023fece  mov     rdx, rsi
0x18023fed1  lea     rcx, [rdi+58h]
0x18023fed5  call    _winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__CreateTokenizerHelper____3____lambda_1___operator__
0x18023feda  mov     dword ptr [rdi+1D8h], 1
0x18023fee4  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18023fee8  jz      short loc_18023FF0E
0x18023feea  mov     rdx, r14; Token
0x18023feed  xor     ecx, ecx; Thread
0x18023feef  call    cs:__imp_SetThreadToken
0x18023fef5  test    eax, eax
0x18023fef7  jnz     short loc_18023FEFF
0x18023fef9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18023feff  test    r14, r14
0x18023ff02  jz      short loc_18023FF0E
0x18023ff04  mov     rcx, r14; hObject
0x18023ff07  call    cs:__imp_CloseHandle
0x18023ff0d  nop
0x18023ff0e  mov     rcx, [rdi+1C8h]; hObject
0x18023ff15  test    rcx, rcx
0x18023ff18  jz      short loc_18023FF2C
0x18023ff1a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18023ff1e  jz      short loc_18023FF2C
0x18023ff20  mov     [rsp+1E8h+var_180], rcx
0x18023ff25  call    cs:__imp_CloseHandle
0x18023ff2b  nop
0x18023ff2c  lea     rcx, [rdi+68h]
0x18023ff30  mov     [rcx], rbx
0x18023ff33  mov     [rdi+70h], rsi
0x18023ff37  mov     qword ptr [rdi+78h], 0
0x18023ff3f  mov     byte ptr [rdi+80h], 1
0x18023ff46  mov     eax, 6
0x18023ff4b  mov     [rdi+28h], ax
0x18023ff4f  mov     rdx, rdi
0x18023ff52  call    ??$await_suspend@Upromise_type@?$coroutine_traits@Ufire_and_forget@winrt@@UITextEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@$$QEAV?$promise@V?$shared_ptr@VITokenizer@SemanticRegistry@asg@@@std@@@std@@@std@@@?$await_adapter@U?$IAsyncOperation@UITextTokenizer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@Ufire_and_forget@winrt@@UITextEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@$$QEAV?$promise@V?$shared_ptr@VITokenizer@SemanticRegistry@asg@@@std@@@std@@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextTokenizer>,1>::await_suspend<std::coroutine_traits<winrt::fire_and_forget,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory,std::promise<std::shared_ptr<asg::SemanticRegistry::ITokenizer>> &&>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::fire_and_forget,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory,std::promise<std::shared_ptr<asg::SemanticRegistry::ITokenizer>> &&>::promise_type>)
0x18023ff57  test    al, al
0x18023ff59  jz      loc_18024000F
0x18023ff5f  jmp     loc_180240276
0x18023ff64  mov     rsi, [rdi+68h]; jumptable 000000018023FDA8 case 7
0x18023ff68  test    rsi, rsi
0x18023ff6b  jz      short loc_18023FF93
0x18023ff6d  mov     [rsp+1E8h+var_110], rsi
0x18023ff75  xor     ebx, ebx
0x18023ff77  mov     eax, ebx
0x18023ff79  xchg    rax, [rsi]
0x18023ff7c  cmp     rax, 1
0x18023ff80  jnz     short loc_18023FF93
0x18023ff82  call    _Thrd_yield
0x18023ff87  mov     rax, rbx
0x18023ff8a  xchg    rax, [rsi]
0x18023ff8d  cmp     rax, 1
0x18023ff91  jz      short loc_18023FF82
0x18023ff93  lea     rcx, [rdi+60h]
0x18023ff97  mov     rax, [rcx]
0x18023ff9a  mov     [rsp+1E8h+arg_18], rax
0x18023ffa2  test    rax, rax
0x18023ffa5  jz      short loc_18023FFAD
0x18023ffa7  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023ffac  nop
0x18023ffad  lea     rcx, [rdi+58h]
0x18023ffb1  mov     rax, [rcx]
0x18023ffb4  mov     [rsp+1E8h+var_1B8], rax
0x18023ffb9  test    rax, rax
0x18023ffbc  jz      short loc_18023FFC4
0x18023ffbe  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023ffc3  nop
0x18023ffc4  lea     rcx, [rdi+38h]
0x18023ffc8  call    ??1?$promise@V?$shared_ptr@UIImageModelAccessor@SemanticPipelines@asg@@@std@@@std@@QEAA@XZ; std::promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>::~promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>(void)
0x18023ffcd  nop
0x18023ffce  mov     rcx, [rdi+30h]; hObject
0x18023ffd2  test    rcx, rcx
0x18023ffd5  jz      short loc_18023FFEC
0x18023ffd7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18023ffdb  jz      short loc_18023FFEC
0x18023ffdd  mov     [rsp+1E8h+arg_10], rcx
0x18023ffe5  call    cs:__imp_CloseHandle
0x18023ffeb  nop
0x18023ffec  mov     ebx, 0FFFFFFFFh
0x18023fff1  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ebx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18023fff9  sub     ebx, 1
0x18023fffc  jz      short loc_180240008
0x18023fffe  test    ebx, ebx
0x180240000  jns     short loc_180240008
0x180240002  call    abort
0x180240008  jmp     loc_180240250; jumptable 000000018023FDA8 case -1
0x18024000d  xor     ebx, ebx; jumptable 000000018023FDA8 case 6
0x18024000f  lea     rdx, [rdi+88h]
0x180240016  lea     rcx, [rdi+68h]
0x18024001a  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@UITextEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,1>::await_resume(void)
0x18024001f  nop
0x180240020  mov     rsi, [rdi+68h]
0x180240024  test    rsi, rsi
0x180240027  jz      short loc_180240051
0x180240029  mov     [rsp+1E8h+var_110], rsi
0x180240031  mov     rax, rbx
0x180240034  xchg    rax, [rsi]
0x180240037  cmp     rax, 1
0x18024003b  jnz     short loc_180240051
0x18024003d  nop     dword ptr [rax]
0x180240040  call    _Thrd_yield
0x180240045  mov     rax, rbx
0x180240048  xchg    rax, [rsi]
0x18024004b  cmp     rax, 1
0x18024004f  jz      short loc_180240040
0x180240051  lea     rcx, [rdi+60h]
0x180240055  mov     rax, [rcx]
0x180240058  mov     [rsp+1E8h+arg_18], rax
0x180240060  test    rax, rax
0x180240063  jz      short loc_18024006B
0x180240065  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18024006a  nop
0x18024006b  lea     rcx, [rdi+58h]
0x18024006f  mov     rax, [rcx]
0x180240072  mov     [rsp+1E8h+var_1B8], rax
0x180240077  test    rax, rax
0x18024007a  jz      short loc_180240081
0x18024007c  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180240081  cmp     qword ptr [rdi+88h], 0
0x180240089  jnz     short loc_1802400AD
0x18024008b  lea     rdx, aFactoryFailedT_0; "Factory failed to create a tokenizer; n"...
0x180240092  lea     rcx, [rsp+1E8h+pExceptionObject]; this
0x180240097  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18024009c  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1802400a3  lea     rcx, [rsp+1E8h+pExceptionObject]; pExceptionObject
0x1802400a8  call    _CxxThrowException
0x1802400ad  mov     ecx, 20h ; ' '; Size
0x1802400b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802400b7  mov     rsi, rax
0x1802400ba  mov     dword ptr [rax+8], 1
0x1802400c1  mov     dword ptr [rax+0Ch], 1
0x1802400c8  lea     rax, ??_7?$_Ref_count_obj2@UTextTokenizerWrapper@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@6B@; const std::_Ref_count_obj2<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextTokenizerWrapper>::`vftable'
0x1802400cf  mov     [rsi], rax
0x1802400d2  lea     r14, [rsi+10h]
0x1802400d6  mov     rbx, [rdi+88h]
0x1802400dd  test    rbx, rbx
0x1802400e0  jz      short loc_1802400F7
0x1802400e2  mov     [rsp+1E8h+var_1B0], rbx
0x1802400e7  mov     rax, [rbx]
0x1802400ea  mov     rcx, rbx
0x1802400ed  mov     rax, [rax+8]
0x1802400f1  call    cs:__guard_dispatch_icall_fptr
0x1802400f7  lea     rax, ??_7TextTokenizerWrapper@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@6B@; const winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextTokenizerWrapper::`vftable'
0x1802400fe  mov     [r14], rax
0x180240101  mov     [r14+8], rbx
0x180240105  mov     dword ptr [rdi+1D8h], 3
0x18024010f  mov     [rdi+90h], r14
0x180240116  mov     [rdi+98h], rsi
0x18024011d  test    rsi, rsi
0x180240120  jz      short loc_180240126
0x180240122  lock inc dword ptr [rsi+8]
0x180240126  lea     rdx, [rdi+0A0h]
0x18024012d  mov     [rsp+1E8h+var_120], r14
0x180240135  mov     [rdx], r14
0x180240138  mov     [rdi+0A8h], rsi
0x18024013f  lea     rcx, [rdi+38h]
0x180240143  call    ?set_value@?$promise@V?$shared_ptr@UIImageModelAccessor@SemanticPipelines@asg@@@std@@@std@@QEAAX$$QEAV?$shared_ptr@UIImageModelAccessor@SemanticPipelines@asg@@@2@@Z; std::promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>::set_value(std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor> &&)
0x180240148  nop
0x180240149  mov     r14, [rdi+0A8h]
0x180240150  mov     ebx, 0FFFFFFFFh
0x180240155  test    r14, r14
0x180240158  jz      short loc_1802401A3
0x18024015a  mov     [rsp+1E8h+var_188], r14
0x18024015f  mov     eax, ebx
0x180240161  lock xadd [r14+8], eax
0x180240167  cmp     eax, 1
0x18024016a  jnz     short loc_1802401A3
0x18024016c  mov     rax, [r14]
0x18024016f  mov     rcx, r14
0x180240172  mov     rax, [rax]
0x180240175  call    cs:__guard_dispatch_icall_fptr
0x18024017b  mov     [rsp+1E8h+var_188], r14
0x180240180  mov     eax, ebx
0x180240182  lock xadd [r14+0Ch], eax
0x180240188  cmp     eax, 1
0x18024018b  jnz     short loc_1802401A3
0x18024018d  mov     rax, [r14]
0x180240190  mov     [rsp+1E8h+var_188], r14
0x180240195  mov     rcx, r14
0x180240198  mov     rax, [rax+8]
0x18024019c  call    cs:__guard_dispatch_icall_fptr
0x1802401a2  nop
0x1802401a3  test    rsi, rsi
0x1802401a6  jz      short loc_1802401E0
0x1802401a8  mov     eax, ebx
0x1802401aa  lock xadd [rsi+8], eax
0x1802401af  cmp     eax, 1
0x1802401b2  jnz     short loc_1802401E0
0x1802401b4  mov     rax, [rsi]
0x1802401b7  mov     rcx, rsi
0x1802401ba  mov     rax, [rax]
0x1802401bd  call    cs:__guard_dispatch_icall_fptr
0x1802401c3  mov     eax, ebx
0x1802401c5  lock xadd [rsi+0Ch], eax
0x1802401ca  cmp     eax, 1
0x1802401cd  jnz     short loc_1802401E0
0x1802401cf  mov     rax, [rsi]
0x1802401d2  mov     rcx, rsi
0x1802401d5  mov     rax, [rax+8]
0x1802401d9  call    cs:__guard_dispatch_icall_fptr
0x1802401df  nop
0x1802401e0  mov     rax, [rdi+88h]
0x1802401e7  mov     [rsp+1E8h+var_1B0], rax
0x1802401ec  test    rax, rax
0x1802401ef  jz      short loc_1802401FE
0x1802401f1  lea     rcx, [rdi+88h]
0x1802401f8  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802401fd  nop
0x1802401fe  jmp     short loc_18024020D
0x180240200  mov     rdi, [rsp+1E8h+Block]
0x180240208  mov     ebx, 0FFFFFFFFh
  ... truncated ...
```
