# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateModelAccessorHelper$_ResumeCoro$1_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory_std::shared_ptr_asg::SemanticPipelines::IImageModelAccessor__winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModel_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageModelWrapper_

- ea: `0x18023ea50`
- end: `0x18023ef80`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateModelAccessorHelper$_ResumeCoro$1_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory_std::shared_ptr_asg::SemanticPipelines::IImageModelAccessor__winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModel_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageModelWrapper_`
- size: `1328`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005a060`
- `0x18023ea30`

## callees

- `0x180003bd0`
- `0x18000d4b0`
- `0x18000e5a0`
- `0x18001b3c0`
- `0x180047120`
- `0x1800475c0`
- `0x180059b60`
- `0x18005bb00`
- `0x18005c030`
- `0x18005c5c0`
- `0x18005d890`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180206a58`
- `0x18023ea50`
- `0x180242120`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18023eb0e`
- `KERNEL32!CloseHandle` at `0x18023ebfb`
- `KERNEL32!CloseHandle` at `0x18023ec19`
- `KERNEL32!CloseHandle` at `0x18023ece3`
- `KERNEL32!CloseHandle` at `0x18023ef02`
- `KERNEL32!CloseHandle` at `0x18023eb0e`
- `KERNEL32!CloseHandle` at `0x18023ebfb`
- `KERNEL32!CloseHandle` at `0x18023ec19`
- `KERNEL32!CloseHandle` at `0x18023ece3`
- `KERNEL32!CloseHandle` at `0x18023ef02`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18023ebe3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18023ebe3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18023eba2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18023eba2`

## string_xrefs

- `0x18023ed8b`: `Factory failed to create a model; no error was reported.`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateModelAccessorHelper__ResumeCoro_1_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory_std::shared_ptr_asg::SemanticPipelines::IImageModelAccessor__winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModel_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageModelWrapper_(
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
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateModelAccessorHelper_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory_std::shared_ptr_asg::SemanticPipelines::IImageModelAccessor__winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModel_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageModelWrapper__::_3_::_lambda_1_::operator()(
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
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CreateModelAccessorHelper_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory_std::shared_ptr_asg::SemanticPipelines::IImageModelAccessor__winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModel_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageModelWrapper__::_3_::_lambda_1_::operator()(
          a1 + 96,
          a1 + 104);
        *(_DWORD *)(a1 + 480) = 1;
      }
      *(_QWORD *)(a1 + 112) = 0;
      *(_QWORD *)(a1 + 120) = v7;
      *(_QWORD *)(a1 + 128) = 0;
      *(_BYTE *)(a1 + 136) = 1;
      *(_WORD *)(a1 + 48) = 6;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModel>,1>::await_suspend<std::coroutine_traits<winrt::fire_and_forget,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory,std::optional<asg::SemanticRegistry::EmbeddingQuantizationParameters> const &,std::promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>> &&>::promise_type>() )
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
      *(_QWORD *)v17 = &std::_Ref_count_obj2<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageModelWrapper>::`vftable';
      v18 = v17 + 16;
      v19 = *(_QWORD *)(a1 + 144);
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
      *v18 = &winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageModelWrapper::`vftable';
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
0x18023ea50  mov     [rsp+Block], rcx
0x18023ea55  push    rbx
0x18023ea56  push    rsi
0x18023ea57  push    rdi
0x18023ea58  push    r12
0x18023ea5a  push    r13
0x18023ea5c  push    r14
0x18023ea5e  push    r15
0x18023ea60  sub     rsp, 1B0h
0x18023ea67  mov     rdi, [rsp+1E8h+Block]
0x18023ea6f  movzx   eax, word ptr [rdi+30h]
0x18023ea73  mov     [rsp+1E8h+var_1C0], ax
0x18023ea78  inc     ax; switch 9 cases
0x18023ea7b  cmp     ax, 8
0x18023ea7f  ja      def_18023EA9A; jumptable 000000018023EA9A default case, cases 0,1
0x18023ea85  movsx   rax, ax
0x18023ea89  lea     rdx, cs:180000000h
0x18023ea90  mov     ecx, ds:(jpt_18023EA9A - 180000000h)[rdx+rax*4]
0x18023ea97  add     rcx, rdx
0x18023ea9a  jmp     rcx; switch jump
0x18023ea9c  jmp     loc_18023EF20; jumptable 000000018023EA9A case 3
0x18023eaa1  xor     esi, esi; jumptable 000000018023EA9A case 2
0x18023eaa3  mov     [rdi+1E0h], esi
0x18023eaa9  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18023eab0  lea     rcx, [rdi+38h]
0x18023eab4  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x18023eab9  nop
0x18023eaba  mov     rcx, [rdi+28h]
0x18023eabe  mov     rax, [rcx]
0x18023eac1  mov     [rcx], rsi
0x18023eac4  mov     [rdi+40h], rax
0x18023eac8  mov     [rdi+48h], sil
0x18023eacc  movzx   eax, byte ptr [rcx+10h]
0x18023ead0  mov     [rdi+50h], al
0x18023ead3  mov     [rdi+58h], sil
0x18023ead7  mov     eax, 4
0x18023eadc  mov     [rdi+30h], ax
0x18023eae0  mov     rdx, rdi
0x18023eae3  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x18023eae8  jmp     loc_18023EF46
0x18023eaed  lea     rcx, [rdi+40h]; jumptable 000000018023EA9A case 5
0x18023eaf1  call    ??1?$promise@V?$shared_ptr@UIImageModelAccessor@SemanticPipelines@asg@@@std@@@std@@QEAA@XZ; std::promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>::~promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>(void)
0x18023eaf6  nop
0x18023eaf7  mov     rcx, [rdi+38h]; hObject
0x18023eafb  test    rcx, rcx
0x18023eafe  jz      short loc_18023EB15
0x18023eb00  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18023eb04  jz      short loc_18023EB15
0x18023eb06  mov     [rsp+1E8h+arg_10], rcx
0x18023eb0e  call    cs:__imp_CloseHandle
0x18023eb14  nop
0x18023eb15  mov     ebx, 0FFFFFFFFh
0x18023eb1a  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ebx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18023eb22  sub     ebx, 1
0x18023eb25  jz      short loc_18023EB31
0x18023eb27  test    ebx, ebx
0x18023eb29  jns     short loc_18023EB31
0x18023eb2b  call    abort
0x18023eb31  jmp     loc_18023EF20; jumptable 000000018023EA9A case -1
0x18023eb36  mov     rcx, [rdi+18h]; jumptable 000000018023EA9A case 4
0x18023eb3a  mov     [rdi+60h], rcx
0x18023eb3e  test    rcx, rcx
0x18023eb41  jz      short loc_18023EB51
0x18023eb43  mov     rax, [rcx]
0x18023eb46  mov     rax, [rax+8]
0x18023eb4a  call    cs:__guard_dispatch_icall_fptr
0x18023eb50  nop
0x18023eb51  mov     rbx, [rdi+38h]
0x18023eb55  test    rbx, rbx
0x18023eb58  jnz     short loc_18023EB7B
0x18023eb5a  lea     rbx, [rdi+68h]
0x18023eb5e  mov     rdx, rbx
0x18023eb61  lea     rcx, [rdi+60h]
0x18023eb65  call    _winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__CreateModelAccessorHelper_winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__IImageEmbeddingsModelFactory_std__shared_ptr_asg__SemanticPipelines__IImageModelAccessor__winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__IImageEmbeddingsModel_winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__ImageModelWrapper_____3____lambda_1___operator__
0x18023eb6a  mov     dword ptr [rdi+1E0h], 1
0x18023eb74  xor     esi, esi
0x18023eb76  jmp     loc_18023EC20
0x18023eb7b  lea     rcx, [rdi+1D0h]
0x18023eb82  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x18023eb87  nop
0x18023eb88  mov     r14, [rdi+1D0h]
0x18023eb8f  xor     esi, esi
0x18023eb91  mov     [rdi+1D0h], rsi
0x18023eb98  mov     [rdi+1D8h], r14
0x18023eb9f  mov     rcx, rbx; hToken
0x18023eba2  call    cs:__imp_ImpersonateLoggedOnUser
0x18023eba8  mov     rcx, [rsp+1E8h]; this
0x18023ebb0  test    eax, eax
0x18023ebb2  jnz     short loc_18023EBBE
0x18023ebb4  mov     edx, 1Ch; void *
0x18023ebb9  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18023ebbe  lea     rbx, [rdi+68h]
0x18023ebc2  mov     rdx, rbx
0x18023ebc5  lea     rcx, [rdi+60h]
0x18023ebc9  call    _winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__CreateModelAccessorHelper_winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__IImageEmbeddingsModelFactory_std__shared_ptr_asg__SemanticPipelines__IImageModelAccessor__winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__IImageEmbeddingsModel_winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__ImageModelWrapper_____3____lambda_1___operator__
0x18023ebce  mov     dword ptr [rdi+1E0h], 1
0x18023ebd8  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18023ebdc  jz      short loc_18023EC02
0x18023ebde  mov     rdx, r14; Token
0x18023ebe1  xor     ecx, ecx; Thread
0x18023ebe3  call    cs:__imp_SetThreadToken
0x18023ebe9  test    eax, eax
0x18023ebeb  jnz     short loc_18023EBF3
0x18023ebed  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18023ebf3  test    r14, r14
0x18023ebf6  jz      short loc_18023EC02
0x18023ebf8  mov     rcx, r14; hObject
0x18023ebfb  call    cs:__imp_CloseHandle
0x18023ec01  nop
0x18023ec02  mov     rcx, [rdi+1D0h]; hObject
0x18023ec09  test    rcx, rcx
0x18023ec0c  jz      short loc_18023EC20
0x18023ec0e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18023ec12  jz      short loc_18023EC20
0x18023ec14  mov     [rsp+1E8h+var_180], rcx
0x18023ec19  call    cs:__imp_CloseHandle
0x18023ec1f  nop
0x18023ec20  lea     rcx, [rdi+70h]
0x18023ec24  mov     [rcx], rsi
0x18023ec27  mov     [rdi+78h], rbx
0x18023ec2b  mov     qword ptr [rdi+80h], 0
0x18023ec36  mov     byte ptr [rdi+88h], 1
0x18023ec3d  mov     eax, 6
0x18023ec42  mov     [rdi+30h], ax
0x18023ec46  mov     rdx, rdi
0x18023ec49  call    ??$await_suspend@Upromise_type@?$coroutine_traits@Ufire_and_forget@winrt@@UIImageEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@AEBV?$optional@UEmbeddingQuantizationParameters@SemanticRegistry@asg@@@std@@$$QEAV?$promise@V?$shared_ptr@UIImageModelAccessor@SemanticPipelines@asg@@@std@@@std@@@std@@@?$await_adapter@U?$IAsyncOperation@UIImageEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@Ufire_and_forget@winrt@@UIImageEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@AEBV?$optional@UEmbeddingQuantizationParameters@SemanticRegistry@asg@@@std@@$$QEAV?$promise@V?$shared_ptr@UIImageModelAccessor@SemanticPipelines@asg@@@std@@@std@@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModel>,1>::await_suspend<std::coroutine_traits<winrt::fire_and_forget,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory,std::optional<asg::SemanticRegistry::EmbeddingQuantizationParameters> const &,std::promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>> &&>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::fire_and_forget,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory,std::optional<asg::SemanticRegistry::EmbeddingQuantizationParameters> const &,std::promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>> &&>::promise_type>)
0x18023ec4e  test    al, al
0x18023ec50  jz      loc_18023ED0D
0x18023ec56  jmp     loc_18023EF46
0x18023ec5b  mov     rbx, [rdi+70h]; jumptable 000000018023EA9A case 7
0x18023ec5f  test    rbx, rbx
0x18023ec62  jz      short loc_18023EC91
0x18023ec64  mov     [rsp+1E8h+var_110], rbx
0x18023ec6c  xor     esi, esi
0x18023ec6e  mov     eax, esi
0x18023ec70  xchg    rax, [rbx]
0x18023ec73  cmp     rax, 1
0x18023ec77  jnz     short loc_18023EC91
0x18023ec79  nop     dword ptr [rax+00000000h]
0x18023ec80  call    _Thrd_yield
0x18023ec85  mov     rax, rsi
0x18023ec88  xchg    rax, [rbx]
0x18023ec8b  cmp     rax, 1
0x18023ec8f  jz      short loc_18023EC80
0x18023ec91  lea     rcx, [rdi+68h]
0x18023ec95  mov     rax, [rcx]
0x18023ec98  mov     [rsp+1E8h+arg_18], rax
0x18023eca0  test    rax, rax
0x18023eca3  jz      short loc_18023ECAB
0x18023eca5  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023ecaa  nop
0x18023ecab  lea     rcx, [rdi+60h]
0x18023ecaf  mov     rax, [rcx]
0x18023ecb2  mov     [rsp+1E8h+var_1B8], rax
0x18023ecb7  test    rax, rax
0x18023ecba  jz      short loc_18023ECC2
0x18023ecbc  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023ecc1  nop
0x18023ecc2  lea     rcx, [rdi+40h]
0x18023ecc6  call    ??1?$promise@V?$shared_ptr@UIImageModelAccessor@SemanticPipelines@asg@@@std@@@std@@QEAA@XZ; std::promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>::~promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>(void)
0x18023eccb  nop
0x18023eccc  mov     rcx, [rdi+38h]; hObject
0x18023ecd0  test    rcx, rcx
0x18023ecd3  jz      short loc_18023ECEA
0x18023ecd5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18023ecd9  jz      short loc_18023ECEA
0x18023ecdb  mov     [rsp+1E8h+arg_10], rcx
0x18023ece3  call    cs:__imp_CloseHandle
0x18023ece9  nop
0x18023ecea  mov     ebx, 0FFFFFFFFh
0x18023ecef  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ebx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18023ecf7  sub     ebx, 1
0x18023ecfa  jz      short loc_18023ED06
0x18023ecfc  test    ebx, ebx
0x18023ecfe  jns     short loc_18023ED06
0x18023ed00  call    abort
0x18023ed06  jmp     loc_18023EF20; jumptable 000000018023EA9A case -1
0x18023ed0b  xor     esi, esi; jumptable 000000018023EA9A case 6
0x18023ed0d  lea     rdx, [rdi+90h]
0x18023ed14  lea     rcx, [rdi+70h]
0x18023ed18  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@UITextEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,1>::await_resume(void)
0x18023ed1d  nop
0x18023ed1e  mov     rbx, [rdi+70h]
0x18023ed22  test    rbx, rbx
0x18023ed25  jz      short loc_18023ED51
0x18023ed27  mov     [rsp+1E8h+var_110], rbx
0x18023ed2f  mov     rax, rsi
0x18023ed32  xchg    rax, [rbx]
0x18023ed35  cmp     rax, 1
0x18023ed39  jnz     short loc_18023ED51
0x18023ed3b  nop     dword ptr [rax+rax+00h]
0x18023ed40  call    _Thrd_yield
0x18023ed45  mov     rax, rsi
0x18023ed48  xchg    rax, [rbx]
0x18023ed4b  cmp     rax, 1
0x18023ed4f  jz      short loc_18023ED40
0x18023ed51  lea     rcx, [rdi+68h]
0x18023ed55  mov     rax, [rcx]
0x18023ed58  mov     [rsp+1E8h+arg_18], rax
0x18023ed60  test    rax, rax
0x18023ed63  jz      short loc_18023ED6B
0x18023ed65  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023ed6a  nop
0x18023ed6b  lea     rcx, [rdi+60h]
0x18023ed6f  mov     rax, [rcx]
0x18023ed72  mov     [rsp+1E8h+var_1B8], rax
0x18023ed77  test    rax, rax
0x18023ed7a  jz      short loc_18023ED81
0x18023ed7c  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023ed81  cmp     qword ptr [rdi+90h], 0
0x18023ed89  jnz     short loc_18023EDAD
0x18023ed8b  lea     rdx, aFactoryFailedT; "Factory failed to create a model; no er"...
0x18023ed92  lea     rcx, [rsp+1E8h+pExceptionObject]; this
0x18023ed97  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18023ed9c  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18023eda3  lea     rcx, [rsp+1E8h+pExceptionObject]; pExceptionObject
0x18023eda8  call    _CxxThrowException
0x18023edad  mov     r13, [rdi+20h]
0x18023edb1  mov     ecx, 30h ; '0'; Size
0x18023edb6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18023edbb  mov     r15, rax
0x18023edbe  mov     dword ptr [rax+8], 1
0x18023edc5  mov     dword ptr [rax+0Ch], 1
0x18023edcc  lea     rax, ??_7?$_Ref_count_obj2@UImageModelWrapper@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@6B@; const std::_Ref_count_obj2<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageModelWrapper>::`vftable'
0x18023edd3  mov     [r15], rax
0x18023edd6  lea     r12, [r15+10h]
0x18023edda  mov     rbx, [rdi+90h]
0x18023ede1  test    rbx, rbx
0x18023ede4  jz      short loc_18023EDFB
0x18023ede6  mov     [rsp+1E8h+var_1B0], rbx
0x18023edeb  mov     rax, [rbx]
0x18023edee  mov     rcx, rbx
0x18023edf1  mov     rax, [rax+8]
0x18023edf5  call    cs:__guard_dispatch_icall_fptr
0x18023edfb  lea     rax, ??_7ImageModelWrapper@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@6B@; const winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageModelWrapper::`vftable'
0x18023ee02  mov     [r12], rax
0x18023ee06  mov     [r12+8], rbx
0x18023ee0b  movsd   xmm0, qword ptr [r13+0]
0x18023ee11  movsd   qword ptr [r12+10h], xmm0
0x18023ee18  mov     eax, [r13+8]
0x18023ee1c  mov     [r12+18h], eax
0x18023ee21  mov     dword ptr [rdi+1E0h], 3
0x18023ee2b  lea     rdx, [rdi+0A8h]
0x18023ee32  mov     [rsp+1E8h+var_120], r12
0x18023ee3a  mov     [rdx], r12
0x18023ee3d  mov     [rdi+0B0h], r15
0x18023ee44  mov     [rdi+98h], rsi
0x18023ee4b  mov     [rdi+0A0h], rsi
0x18023ee52  lea     rcx, [rdi+40h]
0x18023ee56  call    ?set_value@?$promise@V?$shared_ptr@UIImageModelAccessor@SemanticPipelines@asg@@@std@@@std@@QEAAX$$QEAV?$shared_ptr@UIImageModelAccessor@SemanticPipelines@asg@@@2@@Z; std::promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>::set_value(std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor> &&)
0x18023ee5b  nop
0x18023ee5c  mov     rsi, [rdi+0B0h]
0x18023ee63  mov     ebx, 0FFFFFFFFh
0x18023ee68  test    rsi, rsi
0x18023ee6b  jz      short loc_18023EEB4
0x18023ee6d  mov     [rsp+1E8h+var_188], rsi
0x18023ee72  mov     eax, ebx
0x18023ee74  lock xadd [rsi+8], eax
0x18023ee79  cmp     eax, 1
0x18023ee7c  jnz     short loc_18023EEB4
0x18023ee7e  mov     rax, [rsi]
0x18023ee81  mov     rcx, rsi
0x18023ee84  mov     rax, [rax]
0x18023ee87  call    cs:__guard_dispatch_icall_fptr
0x18023ee8d  mov     [rsp+1E8h+var_188], rsi
0x18023ee92  mov     eax, ebx
0x18023ee94  lock xadd [rsi+0Ch], eax
0x18023ee99  cmp     eax, 1
0x18023ee9c  jnz     short loc_18023EEB4
0x18023ee9e  mov     rax, [rsi]
0x18023eea1  mov     [rsp+1E8h+var_188], rsi
0x18023eea6  mov     rcx, rsi
0x18023eea9  mov     rax, [rax+8]
0x18023eead  call    cs:__guard_dispatch_icall_fptr
0x18023eeb3  nop
0x18023eeb4  mov     rax, [rdi+90h]
0x18023eebb  mov     [rsp+1E8h+var_1B0], rax
0x18023eec0  test    rax, rax
0x18023eec3  jz      short loc_18023EED2
0x18023eec5  lea     rcx, [rdi+90h]
0x18023eecc  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023eed1  nop
0x18023eed2  jmp     short loc_18023EEE1
0x18023eed4  mov     rdi, [rsp+1E8h+Block]
0x18023eedc  mov     ebx, 0FFFFFFFFh
0x18023eee1  lea     rcx, [rdi+40h]
0x18023eee5  call    ??1?$promise@V?$shared_ptr@UIImageModelAccessor@SemanticPipelines@asg@@@std@@@std@@QEAA@XZ; std::promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>::~promise<std::shared_ptr<asg::SemanticPipelines::IImageModelAccessor>>(void)
0x18023eeea  nop
0x18023eeeb  mov     rcx, [rdi+38h]; hObject
0x18023eeef  test    rcx, rcx
0x18023eef2  jz      short loc_18023EF09
0x18023eef4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18023eef8  jz      short loc_18023EF09
0x18023eefa  mov     [rsp+1E8h+arg_10], rcx
0x18023ef02  call    cs:__imp_CloseHandle
0x18023ef08  nop
0x18023ef09  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ebx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18023ef11  sub     ebx, 1
0x18023ef14  jz      short loc_18023EF20; jumptable 000000018023EA9A case -1
0x18023ef16  test    ebx, ebx
  ... truncated ...
```
