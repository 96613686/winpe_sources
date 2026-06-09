# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateModelAccessorHelper$_ResumeCoro$1_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory_std::shared_ptr_asg::SemanticPipelines::ITextModelAccessor__winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextModelWrapper_

- ea: `0x18023ef80`
- end: `0x18023f4b0`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateModelAccessorHelper$_ResumeCoro$1_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory_std::shared_ptr_asg::SemanticPipelines::ITextModelAccessor__winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextModelWrapper_`
- size: `1328`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180059cf0`
- `0x18023ea40`

## callees

- `0x180003bd0`
- `0x18000d4b0`
- `0x18000e5a0`
- `0x18001b3c0`
- `0x180047120`
- `0x1800475c0`
- `0x180059b60`
- `0x18005b9e0`
- `0x18005c030`
- `0x18005c5c0`
- `0x18005d850`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180206a58`
- `0x18023ef80`
- `0x180242120`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18023f03e`
- `KERNEL32!CloseHandle` at `0x18023f12b`
- `KERNEL32!CloseHandle` at `0x18023f149`
- `KERNEL32!CloseHandle` at `0x18023f213`
- `KERNEL32!CloseHandle` at `0x18023f432`
- `KERNEL32!CloseHandle` at `0x18023f03e`
- `KERNEL32!CloseHandle` at `0x18023f12b`
- `KERNEL32!CloseHandle` at `0x18023f149`
- `KERNEL32!CloseHandle` at `0x18023f213`
- `KERNEL32!CloseHandle` at `0x18023f432`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18023f113`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18023f113`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18023f0d2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18023f0d2`

## string_xrefs

- `0x18023f2bb`: `Factory failed to create a model; no error was reported.`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateModelAccessorHelper__ResumeCoro_1_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory_std::shared_ptr_asg::SemanticPipelines::ITextModelAccessor__winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextModelWrapper_(
        __int64 a1)
{
  __int64 *v2; // rcx
  __int64 v3; // rax
  void *v4; // rcx
  __int64 v5; // rcx
  void *v6; // rbx
  __int64 v7; // rbx
  void *v8; // r14
  unsigned int v9; // r8d
  const char *v10; // r9
  wil::details::in1diag3 *v11; // rcx
  void *v12; // rcx
  volatile __int64 *v13; // rbx
  void *v14; // rcx
  volatile __int64 *v15; // rbx
  __int64 v16; // r13
  char *v17; // r15
  _QWORD *v18; // r12
  __int64 v19; // rbx
  volatile signed __int32 *v20; // rsi
  void *v21; // rcx
  _BYTE pExceptionObject[80]; // [rsp+78h] [rbp-170h] BYREF
  char *v23; // [rsp+C8h] [rbp-120h]
  __int64 v24; // [rsp+D8h] [rbp-110h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  switch ( *(_WORD *)(a1 + 48) )
  {
    case 0xFFFF:
    case 3:
      goto LABEL_58;
    case 2:
      *(_DWORD *)(a1 + 480) = 0;
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      ImpersonationHelper::GetThreadImpersonationToken(a1 + 56);
      v2 = *(__int64 **)(a1 + 40);
      v3 = *v2;
      *v2 = 0;
      *(_QWORD *)(a1 + 64) = v3;
      *(_BYTE *)(a1 + 72) = 0;
      *(_BYTE *)(a1 + 80) = *((_BYTE *)v2 + 16);
      *(_BYTE *)(a1 + 88) = 0;
      *(_WORD *)(a1 + 48) = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v2, a1);
      return;
    case 4:
      v5 = *(_QWORD *)(a1 + 24);
      *(_QWORD *)(a1 + 96) = v5;
      if ( v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
      v6 = *(void **)(a1 + 56);
      if ( v6 )
      {
        ImpersonationHelper::GetThreadImpersonationToken(a1 + 464);
        v8 = *(void **)(a1 + 464);
        *(_QWORD *)(a1 + 464) = 0;
        *(_QWORD *)(a1 + 472) = v8;
        if ( !ImpersonateLoggedOnUser(v6) )
          wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x1C, v9, v10);
        v7 = a1 + 104;
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateModelAccessorHelper_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory_std::shared_ptr_asg::SemanticPipelines::ITextModelAccessor__winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextModelWrapper__::_3_::_lambda_1_::operator()(
          a1 + 96,
          a1 + 104);
        *(_DWORD *)(a1 + 480) = 1;
        if ( v8 != (void *)-1LL )
        {
          if ( !SetThreadToken(0, v8) )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(v11);
          if ( v8 )
            CloseHandle(v8);
        }
        v12 = *(void **)(a1 + 464);
        if ( v12 && v12 != (void *)-1LL )
          CloseHandle(v12);
      }
      else
      {
        v7 = a1 + 104;
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateModelAccessorHelper_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory_std::shared_ptr_asg::SemanticPipelines::ITextModelAccessor__winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextModelWrapper__::_3_::_lambda_1_::operator()(
          a1 + 96,
          a1 + 104);
        *(_DWORD *)(a1 + 480) = 1;
      }
      *(_QWORD *)(a1 + 112) = 0;
      *(_QWORD *)(a1 + 120) = v7;
      *(_QWORD *)(a1 + 128) = 0;
      *(_BYTE *)(a1 + 136) = 1;
      *(_WORD *)(a1 + 48) = 6;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,1>::await_suspend<std::coroutine_traits<winrt::fire_and_forget,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory,std::optional<asg::SemanticRegistry::EmbeddingQuantizationParameters> const &,std::promise<std::shared_ptr<asg::SemanticPipelines::ITextModelAccessor>> &&>::promise_type>() )
        return;
      goto LABEL_36;
    case 5:
      std::promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>::~promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>(a1 + 64);
      v4 = *(void **)(a1 + 56);
      if ( v4 && v4 != (void *)-1LL )
        CloseHandle(v4);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      goto LABEL_58;
    case 6:
LABEL_36:
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,1>::await_resume(
        a1 + 112,
        a1 + 144);
      v15 = *(volatile __int64 **)(a1 + 112);
      if ( v15 )
      {
        v24 = *(_QWORD *)(a1 + 112);
        while ( _InterlockedExchange64(v15, 0) == 1 )
          Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 104) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 104);
      if ( *(_QWORD *)(a1 + 96) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 96);
      if ( !*(_QWORD *)(a1 + 144) )
      {
        std::runtime_error::runtime_error(
          (std::runtime_error *)pExceptionObject,
          "Factory failed to create a model; no error was reported.");
        throw (std::runtime_error *)pExceptionObject;
      }
      v16 = *(_QWORD *)(a1 + 32);
      v17 = (char *)operator new(0x30u);
      *((_DWORD *)v17 + 2) = 1;
      *((_DWORD *)v17 + 3) = 1;
      *(_QWORD *)v17 = &std::_Ref_count_obj2<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextModelWrapper>::`vftable';
      v18 = v17 + 16;
      v19 = *(_QWORD *)(a1 + 144);
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
      *v18 = &winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextModelWrapper::`vftable';
      *((_QWORD *)v17 + 3) = v19;
      *((_QWORD *)v17 + 4) = *(_QWORD *)v16;
      *((_DWORD *)v17 + 10) = *(_DWORD *)(v16 + 8);
      *(_DWORD *)(a1 + 480) = 3;
      v23 = v17 + 16;
      *(_QWORD *)(a1 + 168) = v18;
      *(_QWORD *)(a1 + 176) = v17;
      *(_QWORD *)(a1 + 152) = 0;
      *(_QWORD *)(a1 + 160) = 0;
      std::promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>::set_value(a1 + 64);
      v20 = *(volatile signed __int32 **)(a1 + 176);
      if ( v20 )
      {
        if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
          if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
        }
      }
      if ( *(_QWORD *)(a1 + 144) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 144);
      std::promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>::~promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>(a1 + 64);
      v21 = *(void **)(a1 + 56);
      if ( v21 && v21 != (void *)-1LL )
        CloseHandle(v21);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      goto LABEL_58;
    case 7:
      v13 = *(volatile __int64 **)(a1 + 112);
      if ( v13 )
      {
        v24 = *(_QWORD *)(a1 + 112);
        while ( _InterlockedExchange64(v13, 0) == 1 )
          Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 104) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 104);
      if ( *(_QWORD *)(a1 + 96) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 96);
      std::promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>::~promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>(a1 + 64);
      v14 = *(void **)(a1 + 56);
      if ( v14 && v14 != (void *)-1LL )
        CloseHandle(v14);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
LABEL_58:
      if ( *(_QWORD *)(a1 + 24) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 24);
      if ( *(_WORD *)(a1 + 50) )
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
0x18023ef80  mov     [rsp+Block], rcx
0x18023ef85  push    rbx
0x18023ef86  push    rsi
0x18023ef87  push    rdi
0x18023ef88  push    r12
0x18023ef8a  push    r13
0x18023ef8c  push    r14
0x18023ef8e  push    r15
0x18023ef90  sub     rsp, 1B0h
0x18023ef97  mov     rdi, [rsp+1E8h+Block]
0x18023ef9f  movzx   eax, word ptr [rdi+30h]
0x18023efa3  mov     [rsp+1E8h+var_1C0], ax
0x18023efa8  inc     ax; switch 9 cases
0x18023efab  cmp     ax, 8
0x18023efaf  ja      def_18023EFCA; jumptable 000000018023EFCA default case, cases 0,1
0x18023efb5  movsx   rax, ax
0x18023efb9  lea     rdx, cs:180000000h
0x18023efc0  mov     ecx, ds:(jpt_18023EFCA - 180000000h)[rdx+rax*4]
0x18023efc7  add     rcx, rdx
0x18023efca  jmp     rcx; switch jump
0x18023efcc  jmp     loc_18023F450; jumptable 000000018023EFCA case 3
0x18023efd1  xor     esi, esi; jumptable 000000018023EFCA case 2
0x18023efd3  mov     [rdi+1E0h], esi
0x18023efd9  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18023efe0  lea     rcx, [rdi+38h]
0x18023efe4  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x18023efe9  nop
0x18023efea  mov     rcx, [rdi+28h]
0x18023efee  mov     rax, [rcx]
0x18023eff1  mov     [rcx], rsi
0x18023eff4  mov     [rdi+40h], rax
0x18023eff8  mov     [rdi+48h], sil
0x18023effc  movzx   eax, byte ptr [rcx+10h]
0x18023f000  mov     [rdi+50h], al
0x18023f003  mov     [rdi+58h], sil
0x18023f007  mov     eax, 4
0x18023f00c  mov     [rdi+30h], ax
0x18023f010  mov     rdx, rdi
0x18023f013  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x18023f018  jmp     loc_18023F476
0x18023f01d  lea     rcx, [rdi+40h]; jumptable 000000018023EFCA case 5
0x18023f021  call    ??1?$promise@V?$shared_ptr@UIImageModelAccessor@SemanticPipelines@asg@@@std@@@std@@QEAA@XZ; std::promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>::~promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>(void)
0x18023f026  nop
0x18023f027  mov     rcx, [rdi+38h]; hObject
0x18023f02b  test    rcx, rcx
0x18023f02e  jz      short loc_18023F045
0x18023f030  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18023f034  jz      short loc_18023F045
0x18023f036  mov     [rsp+1E8h+arg_10], rcx
0x18023f03e  call    cs:__imp_CloseHandle
0x18023f044  nop
0x18023f045  mov     ebx, 0FFFFFFFFh
0x18023f04a  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ebx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18023f052  sub     ebx, 1
0x18023f055  jz      short loc_18023F061
0x18023f057  test    ebx, ebx
0x18023f059  jns     short loc_18023F061
0x18023f05b  call    abort
0x18023f061  jmp     loc_18023F450; jumptable 000000018023EFCA case -1
0x18023f066  mov     rcx, [rdi+18h]; jumptable 000000018023EFCA case 4
0x18023f06a  mov     [rdi+60h], rcx
0x18023f06e  test    rcx, rcx
0x18023f071  jz      short loc_18023F081
0x18023f073  mov     rax, [rcx]
0x18023f076  mov     rax, [rax+8]
0x18023f07a  call    cs:__guard_dispatch_icall_fptr
0x18023f080  nop
0x18023f081  mov     rbx, [rdi+38h]
0x18023f085  test    rbx, rbx
0x18023f088  jnz     short loc_18023F0AB
0x18023f08a  lea     rbx, [rdi+68h]
0x18023f08e  mov     rdx, rbx
0x18023f091  lea     rcx, [rdi+60h]
0x18023f095  call    _winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__CreateModelAccessorHelper_winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__ITextEmbeddingsModelFactory_std__shared_ptr_asg__SemanticPipelines__ITextModelAccessor__winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__ITextEmbeddingsModel_winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__TextModelWrapper_____3____lambda_1___operator__
0x18023f09a  mov     dword ptr [rdi+1E0h], 1
0x18023f0a4  xor     esi, esi
0x18023f0a6  jmp     loc_18023F150
0x18023f0ab  lea     rcx, [rdi+1D0h]
0x18023f0b2  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x18023f0b7  nop
0x18023f0b8  mov     r14, [rdi+1D0h]
0x18023f0bf  xor     esi, esi
0x18023f0c1  mov     [rdi+1D0h], rsi
0x18023f0c8  mov     [rdi+1D8h], r14
0x18023f0cf  mov     rcx, rbx; hToken
0x18023f0d2  call    cs:__imp_ImpersonateLoggedOnUser
0x18023f0d8  mov     rcx, [rsp+1E8h]; this
0x18023f0e0  test    eax, eax
0x18023f0e2  jnz     short loc_18023F0EE
0x18023f0e4  mov     edx, 1Ch; void *
0x18023f0e9  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18023f0ee  lea     rbx, [rdi+68h]
0x18023f0f2  mov     rdx, rbx
0x18023f0f5  lea     rcx, [rdi+60h]
0x18023f0f9  call    _winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__CreateModelAccessorHelper_winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__ITextEmbeddingsModelFactory_std__shared_ptr_asg__SemanticPipelines__ITextModelAccessor__winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__ITextEmbeddingsModel_winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__TextModelWrapper_____3____lambda_1___operator__
0x18023f0fe  mov     dword ptr [rdi+1E0h], 1
0x18023f108  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18023f10c  jz      short loc_18023F132
0x18023f10e  mov     rdx, r14; Token
0x18023f111  xor     ecx, ecx; Thread
0x18023f113  call    cs:__imp_SetThreadToken
0x18023f119  test    eax, eax
0x18023f11b  jnz     short loc_18023F123
0x18023f11d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18023f123  test    r14, r14
0x18023f126  jz      short loc_18023F132
0x18023f128  mov     rcx, r14; hObject
0x18023f12b  call    cs:__imp_CloseHandle
0x18023f131  nop
0x18023f132  mov     rcx, [rdi+1D0h]; hObject
0x18023f139  test    rcx, rcx
0x18023f13c  jz      short loc_18023F150
0x18023f13e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18023f142  jz      short loc_18023F150
0x18023f144  mov     [rsp+1E8h+var_180], rcx
0x18023f149  call    cs:__imp_CloseHandle
0x18023f14f  nop
0x18023f150  lea     rcx, [rdi+70h]
0x18023f154  mov     [rcx], rsi
0x18023f157  mov     [rdi+78h], rbx
0x18023f15b  mov     qword ptr [rdi+80h], 0
0x18023f166  mov     byte ptr [rdi+88h], 1
0x18023f16d  mov     eax, 6
0x18023f172  mov     [rdi+30h], ax
0x18023f176  mov     rdx, rdi
0x18023f179  call    ??$await_suspend@Upromise_type@?$coroutine_traits@Ufire_and_forget@winrt@@UITextEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@AEBV?$optional@UEmbeddingQuantizationParameters@SemanticRegistry@asg@@@std@@$$QEAV?$promise@V?$shared_ptr@UITextModelAccessor@SemanticPipelines@asg@@@std@@@std@@@std@@@?$await_adapter@U?$IAsyncOperation@UITextEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@Ufire_and_forget@winrt@@UITextEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@AEBV?$optional@UEmbeddingQuantizationParameters@SemanticRegistry@asg@@@std@@$$QEAV?$promise@V?$shared_ptr@UITextModelAccessor@SemanticPipelines@asg@@@std@@@std@@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,1>::await_suspend<std::coroutine_traits<winrt::fire_and_forget,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory,std::optional<asg::SemanticRegistry::EmbeddingQuantizationParameters> const &,std::promise<std::shared_ptr<asg::SemanticPipelines::ITextModelAccessor>> &&>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::fire_and_forget,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory,std::optional<asg::SemanticRegistry::EmbeddingQuantizationParameters> const &,std::promise<std::shared_ptr<asg::SemanticPipelines::ITextModelAccessor>> &&>::promise_type>)
0x18023f17e  test    al, al
0x18023f180  jz      loc_18023F23D
0x18023f186  jmp     loc_18023F476
0x18023f18b  mov     rbx, [rdi+70h]; jumptable 000000018023EFCA case 7
0x18023f18f  test    rbx, rbx
0x18023f192  jz      short loc_18023F1C1
0x18023f194  mov     [rsp+1E8h+var_110], rbx
0x18023f19c  xor     esi, esi
0x18023f19e  mov     eax, esi
0x18023f1a0  xchg    rax, [rbx]
0x18023f1a3  cmp     rax, 1
0x18023f1a7  jnz     short loc_18023F1C1
0x18023f1a9  nop     dword ptr [rax+00000000h]
0x18023f1b0  call    _Thrd_yield
0x18023f1b5  mov     rax, rsi
0x18023f1b8  xchg    rax, [rbx]
0x18023f1bb  cmp     rax, 1
0x18023f1bf  jz      short loc_18023F1B0
0x18023f1c1  lea     rcx, [rdi+68h]
0x18023f1c5  mov     rax, [rcx]
0x18023f1c8  mov     [rsp+1E8h+arg_18], rax
0x18023f1d0  test    rax, rax
0x18023f1d3  jz      short loc_18023F1DB
0x18023f1d5  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023f1da  nop
0x18023f1db  lea     rcx, [rdi+60h]
0x18023f1df  mov     rax, [rcx]
0x18023f1e2  mov     [rsp+1E8h+var_1B8], rax
0x18023f1e7  test    rax, rax
0x18023f1ea  jz      short loc_18023F1F2
0x18023f1ec  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023f1f1  nop
0x18023f1f2  lea     rcx, [rdi+40h]
0x18023f1f6  call    ??1?$promise@V?$shared_ptr@UIImageModelAccessor@SemanticPipelines@asg@@@std@@@std@@QEAA@XZ; std::promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>::~promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>(void)
0x18023f1fb  nop
0x18023f1fc  mov     rcx, [rdi+38h]; hObject
0x18023f200  test    rcx, rcx
0x18023f203  jz      short loc_18023F21A
0x18023f205  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18023f209  jz      short loc_18023F21A
0x18023f20b  mov     [rsp+1E8h+arg_10], rcx
0x18023f213  call    cs:__imp_CloseHandle
0x18023f219  nop
0x18023f21a  mov     ebx, 0FFFFFFFFh
0x18023f21f  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ebx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18023f227  sub     ebx, 1
0x18023f22a  jz      short loc_18023F236
0x18023f22c  test    ebx, ebx
0x18023f22e  jns     short loc_18023F236
0x18023f230  call    abort
0x18023f236  jmp     loc_18023F450; jumptable 000000018023EFCA case -1
0x18023f23b  xor     esi, esi; jumptable 000000018023EFCA case 6
0x18023f23d  lea     rdx, [rdi+90h]
0x18023f244  lea     rcx, [rdi+70h]
0x18023f248  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@UITextEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,1>::await_resume(void)
0x18023f24d  nop
0x18023f24e  mov     rbx, [rdi+70h]
0x18023f252  test    rbx, rbx
0x18023f255  jz      short loc_18023F281
0x18023f257  mov     [rsp+1E8h+var_110], rbx
0x18023f25f  mov     rax, rsi
0x18023f262  xchg    rax, [rbx]
0x18023f265  cmp     rax, 1
0x18023f269  jnz     short loc_18023F281
0x18023f26b  nop     dword ptr [rax+rax+00h]
0x18023f270  call    _Thrd_yield
0x18023f275  mov     rax, rsi
0x18023f278  xchg    rax, [rbx]
0x18023f27b  cmp     rax, 1
0x18023f27f  jz      short loc_18023F270
0x18023f281  lea     rcx, [rdi+68h]
0x18023f285  mov     rax, [rcx]
0x18023f288  mov     [rsp+1E8h+arg_18], rax
0x18023f290  test    rax, rax
0x18023f293  jz      short loc_18023F29B
0x18023f295  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023f29a  nop
0x18023f29b  lea     rcx, [rdi+60h]
0x18023f29f  mov     rax, [rcx]
0x18023f2a2  mov     [rsp+1E8h+var_1B8], rax
0x18023f2a7  test    rax, rax
0x18023f2aa  jz      short loc_18023F2B1
0x18023f2ac  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023f2b1  cmp     qword ptr [rdi+90h], 0
0x18023f2b9  jnz     short loc_18023F2DD
0x18023f2bb  lea     rdx, aFactoryFailedT; "Factory failed to create a model; no er"...
0x18023f2c2  lea     rcx, [rsp+1E8h+pExceptionObject]; this
0x18023f2c7  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18023f2cc  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18023f2d3  lea     rcx, [rsp+1E8h+pExceptionObject]; pExceptionObject
0x18023f2d8  call    _CxxThrowException
0x18023f2dd  mov     r13, [rdi+20h]
0x18023f2e1  mov     ecx, 30h ; '0'; Size
0x18023f2e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18023f2eb  mov     r15, rax
0x18023f2ee  mov     dword ptr [rax+8], 1
0x18023f2f5  mov     dword ptr [rax+0Ch], 1
0x18023f2fc  lea     rax, ??_7?$_Ref_count_obj2@UTextModelWrapper@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@6B@; const std::_Ref_count_obj2<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextModelWrapper>::`vftable'
0x18023f303  mov     [r15], rax
0x18023f306  lea     r12, [r15+10h]
0x18023f30a  mov     rbx, [rdi+90h]
0x18023f311  test    rbx, rbx
0x18023f314  jz      short loc_18023F32B
0x18023f316  mov     [rsp+1E8h+var_1B0], rbx
0x18023f31b  mov     rax, [rbx]
0x18023f31e  mov     rcx, rbx
0x18023f321  mov     rax, [rax+8]
0x18023f325  call    cs:__guard_dispatch_icall_fptr
0x18023f32b  lea     rax, ??_7TextModelWrapper@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@6B@; const winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextModelWrapper::`vftable'
0x18023f332  mov     [r12], rax
0x18023f336  mov     [r12+8], rbx
0x18023f33b  movsd   xmm0, qword ptr [r13+0]
0x18023f341  movsd   qword ptr [r12+10h], xmm0
0x18023f348  mov     eax, [r13+8]
0x18023f34c  mov     [r12+18h], eax
0x18023f351  mov     dword ptr [rdi+1E0h], 3
0x18023f35b  lea     rdx, [rdi+0A8h]
0x18023f362  mov     [rsp+1E8h+var_120], r12
0x18023f36a  mov     [rdx], r12
0x18023f36d  mov     [rdi+0B0h], r15
0x18023f374  mov     [rdi+98h], rsi
0x18023f37b  mov     [rdi+0A0h], rsi
0x18023f382  lea     rcx, [rdi+40h]
0x18023f386  call    ?set_value@?$promise@V?$shared_ptr@UIImageModelAccessor@SemanticPipelines@asg@@@std@@@std@@QEAAX$$QEAV?$shared_ptr@UIImageModelAccessor@SemanticPipelines@asg@@@2@@Z; std::promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>::set_value(std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor> &&)
0x18023f38b  nop
0x18023f38c  mov     rsi, [rdi+0B0h]
0x18023f393  mov     ebx, 0FFFFFFFFh
0x18023f398  test    rsi, rsi
0x18023f39b  jz      short loc_18023F3E4
0x18023f39d  mov     [rsp+1E8h+var_188], rsi
0x18023f3a2  mov     eax, ebx
0x18023f3a4  lock xadd [rsi+8], eax
0x18023f3a9  cmp     eax, 1
0x18023f3ac  jnz     short loc_18023F3E4
0x18023f3ae  mov     rax, [rsi]
0x18023f3b1  mov     rcx, rsi
0x18023f3b4  mov     rax, [rax]
0x18023f3b7  call    cs:__guard_dispatch_icall_fptr
0x18023f3bd  mov     [rsp+1E8h+var_188], rsi
0x18023f3c2  mov     eax, ebx
0x18023f3c4  lock xadd [rsi+0Ch], eax
0x18023f3c9  cmp     eax, 1
0x18023f3cc  jnz     short loc_18023F3E4
0x18023f3ce  mov     rax, [rsi]
0x18023f3d1  mov     [rsp+1E8h+var_188], rsi
0x18023f3d6  mov     rcx, rsi
0x18023f3d9  mov     rax, [rax+8]
0x18023f3dd  call    cs:__guard_dispatch_icall_fptr
0x18023f3e3  nop
0x18023f3e4  mov     rax, [rdi+90h]
0x18023f3eb  mov     [rsp+1E8h+var_1B0], rax
0x18023f3f0  test    rax, rax
0x18023f3f3  jz      short loc_18023F402
0x18023f3f5  lea     rcx, [rdi+90h]
0x18023f3fc  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023f401  nop
0x18023f402  jmp     short loc_18023F411
0x18023f404  mov     rdi, [rsp+1E8h+Block]
0x18023f40c  mov     ebx, 0FFFFFFFFh
0x18023f411  lea     rcx, [rdi+40h]
0x18023f415  call    ??1?$promise@V?$shared_ptr@UIImageModelAccessor@SemanticPipelines@asg@@@std@@@std@@QEAA@XZ; std::promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>::~promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>(void)
0x18023f41a  nop
0x18023f41b  mov     rcx, [rdi+38h]; hObject
0x18023f41f  test    rcx, rcx
0x18023f422  jz      short loc_18023F439
0x18023f424  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18023f428  jz      short loc_18023F439
0x18023f42a  mov     [rsp+1E8h+arg_10], rcx
0x18023f432  call    cs:__imp_CloseHandle
0x18023f438  nop
0x18023f439  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ebx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18023f441  sub     ebx, 1
0x18023f444  jz      short loc_18023F450; jumptable 000000018023EFCA case -1
0x18023f446  test    ebx, ebx
  ... truncated ...
```
