# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::MakeAvailableAsync$_ResumeCoro$1

- ea: `0x18023c450`
- end: `0x18023cb1c`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::MakeAvailableAsync$_ResumeCoro$1`
- size: `1740`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004a8e0`
- `0x18023c440`

## callees

- `0x180003bd0`
- `0x18000d4b0`
- `0x180010dd0`
- `0x18001b3c0`
- `0x18001b680`
- `0x18001b830`
- `0x18001fd50`
- `0x180021690`
- `0x180032bf0`
- `0x180047120`
- `0x180047520`
- `0x1800475c0`
- `0x18004b040`
- `0x180078d56`
- `0x180078d5c`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f97e0`
- `0x180206a58`
- `0x18023c450`
- `0x180242120`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18023c54b`
- `KERNEL32!CloseHandle` at `0x18023c709`
- `KERNEL32!CloseHandle` at `0x18023c727`
- `KERNEL32!CloseHandle` at `0x18023c833`
- `KERNEL32!CloseHandle` at `0x18023ca4d`
- `KERNEL32!CloseHandle` at `0x18023c54b`
- `KERNEL32!CloseHandle` at `0x18023c709`
- `KERNEL32!CloseHandle` at `0x18023c727`
- `KERNEL32!CloseHandle` at `0x18023c833`
- `KERNEL32!CloseHandle` at `0x18023ca4d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18023c6f1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18023c6f1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18023c697`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18023c697`

## string_xrefs

- `0x18023c4e8`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18023c743`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18023c8f5`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Windows.Management.Deployment.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::MakeAvailableAsync__ResumeCoro_1(
        _WORD *a1)
{
  __int64 v2; // rcx
  void *v3; // rcx
  RTL_SRWLOCK *v4; // rbx
  PVOID Ptr; // rcx
  __int64 v6; // rbx
  void *v7; // r12
  _WORD *v8; // rbx
  void *v9; // r14
  unsigned int v10; // r8d
  const char *v11; // r9
  wil::details::in1diag3 *v12; // rcx
  void *v13; // rcx
  volatile __int64 *v14; // rbx
  void *v15; // rcx
  __int64 *v16; // r14
  volatile __int64 *v17; // rbx
  int v18; // ebx
  __int64 v19; // rcx
  int v20; // eax
  RTL_SRWLOCK *v21; // rbx
  __int64 v22; // r13
  __int64 v23; // rcx
  _QWORD *v24; // rbx
  __int64 v25; // rax
  void *v26; // rcx
  _BYTE pExceptionObject[24]; // [rsp+48h] [rbp-E0h] BYREF
  _BYTE v28[24]; // [rsp+60h] [rbp-C8h] BYREF
  __int128 v29; // [rsp+78h] [rbp-B0h]
  __int64 v30; // [rsp+88h] [rbp-A0h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  switch ( a1[76] )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_74;
    case 2:
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      ImpersonationHelper::GetThreadImpersonationToken(a1 + 80);
      *((_QWORD *)a1 + 36) = a1 + 8;
      *((_QWORD *)a1 + 60) = a1 + 8;
      *((_BYTE *)a1 + 168) = 0;
      v2 = *((unsigned int *)a1 + 28);
      if ( (_DWORD)v2 == 2 )
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
      a1[76] = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v2, a1);
      return;
    case 4:
      v4 = (RTL_SRWLOCK *)*((_QWORD *)a1 + 36);
      *((_QWORD *)a1 + 22) = v4;
      *((_QWORD *)a1 + 23) = v4;
      *((_DWORD *)a1 + 48) = 1;
      *((_QWORD *)a1 + 25) = 0;
      *((_QWORD *)a1 + 52) = v4 + 9;
      WINRT_IMPL_AcquireSRWLockExclusive(v4 + 9);
      Ptr = v4[14].Ptr;
      *((_QWORD *)a1 + 49) = Ptr;
      if ( Ptr )
      {
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 8LL))(Ptr);
        ReleaseSRWLockExclusive_0(v4 + 9);
        winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(
          a1 + 196,
          v4,
          a1 + 96);
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 196);
      }
      else
      {
        ReleaseSRWLockExclusive_0(v4 + 9);
      }
      v6 = *((_QWORD *)a1 + 18);
      *((_QWORD *)a1 + 64) = v6;
      *((_QWORD *)a1 + 26) = v6;
      if ( v6 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
      v7 = (void *)*((_QWORD *)a1 + 20);
      if ( v7 )
      {
        ImpersonationHelper::GetThreadImpersonationToken(a1 + 168);
        v9 = (void *)*((_QWORD *)a1 + 42);
        *((_QWORD *)a1 + 42) = 0;
        *((_QWORD *)a1 + 43) = v9;
        if ( !ImpersonateLoggedOnUser(v7) )
          wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x1C, v10, v11);
        *((_QWORD *)a1 + 48) = v6;
        if ( v6 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
        v8 = a1 + 108;
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::MakeEmbeddingsGeneratorAvailableForOptionsAsync(
          a1 + 108,
          a1 + 192);
        if ( v9 != (void *)-1LL )
        {
          if ( !SetThreadToken(0, v9) )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(v12);
          if ( v9 )
            CloseHandle(v9);
        }
        v13 = (void *)*((_QWORD *)a1 + 42);
        if ( v13 && v13 != (void *)-1LL )
          CloseHandle(v13);
      }
      else
      {
        *((_QWORD *)a1 + 44) = v6;
        if ( v6 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
        v8 = a1 + 108;
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::MakeEmbeddingsGeneratorAvailableForOptionsAsync(
          a1 + 108,
          a1 + 176);
      }
      if ( *((_DWORD *)a1 + 28) == 2 )
      {
        *((_DWORD *)a1 + 90) = 5672;
        *((_QWORD *)a1 + 46) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generate"
                               "d Files\\winrt\\Windows.Foundation.h";
        *((_QWORD *)a1 + 47) = 0;
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)v28,
          (const struct winrt::impl::slim_source_location *)(a1 + 180));
        throw (winrt::hresult_canceled *)v28;
      }
      *((_QWORD *)a1 + 28) = 0;
      *((_QWORD *)a1 + 29) = v8;
      *((_QWORD *)a1 + 30) = 0;
      *((_BYTE *)a1 + 248) = 1;
      a1[76] = 8;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type>(
                              (_QWORD *)a1 + 28,
                              (__int64)a1) )
        return;
      goto LABEL_47;
    case 5:
      v3 = (void *)*((_QWORD *)a1 + 20);
      if ( v3 && v3 != (void *)-1LL )
        CloseHandle(v3);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      goto LABEL_74;
    case 8:
LABEL_47:
      v16 = (__int64 *)(a1 + 128);
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_resume(
        a1 + 112,
        a1 + 128);
      v17 = (volatile __int64 *)*((_QWORD *)a1 + 28);
      if ( v17 )
      {
        v30 = *((_QWORD *)a1 + 28);
        while ( _InterlockedExchange64(v17, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 27) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 108);
      if ( *((_QWORD *)a1 + 64) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 104);
      v18 = 2;
      v19 = *v16;
      if ( *v16 )
      {
        *((_DWORD *)a1 + 108) = 0;
        *((_DWORD *)a1 + 110) = 1440;
        *((_QWORD *)a1 + 56) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generate"
                               "d Files\\winrt\\Microsoft.Windows.Management.Deployment.h";
        *((_QWORD *)a1 + 57) = 0;
        v20 = (*(__int64 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v19 + 48LL))(v19, a1 + 216);
        if ( v20 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v20, a1 + 220);
        }
        if ( *((_DWORD *)a1 + 108) != 1 )
          v18 = 3;
      }
      *((_DWORD *)a1 + 66) = v18;
      *((_QWORD *)a1 + 34) = 0x3FF0000000000000LL;
      v29 = *(_OWORD *)(a1 + 132);
      *((_OWORD *)a1 + 12) = v29;
      v21 = (RTL_SRWLOCK *)*((_QWORD *)a1 + 52);
      WINRT_IMPL_AcquireSRWLockExclusive(v21);
      v22 = *((_QWORD *)a1 + 23);
      v23 = *(_QWORD *)(v22 + 112);
      *((_QWORD *)a1 + 51) = v23;
      if ( v23 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
        ReleaseSRWLockExclusive_0(v21);
        winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(
          a1 + 204,
          v22,
          a1 + 96);
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 204);
      }
      else
      {
        ReleaseSRWLockExclusive_0(v21);
      }
      WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)a1 + 11);
      v24 = a1 + 60;
      if ( a1 + 60 != (_WORD *)v16 )
      {
        if ( *v24 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 60);
        v25 = *v16;
        *v16 = 0;
        *v24 = v25;
      }
      ReleaseSRWLockExclusive_0((PSRWLOCK)a1 + 11);
      if ( *v16 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 128);
      v26 = (void *)*((_QWORD *)a1 + 20);
      if ( v26 && v26 != (void *)-1LL )
        CloseHandle(v26);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      *((_QWORD *)a1 + 38) = *((_QWORD *)a1 + 60);
      a1[76] = 0;
      *(_QWORD *)a1 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::final_suspend_awaiter::await_suspend() )
        goto LABEL_74;
      return;
    case 9:
      v14 = (volatile __int64 *)*((_QWORD *)a1 + 28);
      if ( v14 )
      {
        v30 = *((_QWORD *)a1 + 28);
        while ( _InterlockedExchange64(v14, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 27) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 108);
      if ( *((_QWORD *)a1 + 64) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 104);
      v15 = (void *)*((_QWORD *)a1 + 20);
      if ( v15 && v15 != (void *)-1LL )
        CloseHandle(v15);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
LABEL_74:
      std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type::~promise_type(a1 + 8);
      if ( *((_QWORD *)a1 + 18) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 72);
      if ( a1[77] )
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
0x18023c450  mov     [rsp+Block], rcx
0x18023c455  push    rbx
0x18023c456  push    rsi
0x18023c457  push    rdi
0x18023c458  push    r12
0x18023c45a  push    r13
0x18023c45c  push    r14
0x18023c45e  push    r15
0x18023c460  sub     rsp, 0F0h
0x18023c467  mov     rdi, [rsp+128h+Block]
0x18023c46f  movzx   eax, word ptr [rdi+98h]
0x18023c476  mov     [rsp+128h+var_108], ax
0x18023c47b  inc     ax; switch 11 cases
0x18023c47e  cmp     ax, 0Ah
0x18023c482  ja      def_18023C49D; jumptable 000000018023C49D default case, cases 0,6,7
0x18023c488  movsx   rax, ax
0x18023c48c  lea     rdx, cs:180000000h
0x18023c493  mov     ecx, ds:(jpt_18023C49D - 180000000h)[rdx+rax*4]
0x18023c49a  add     rcx, rdx
0x18023c49d  jmp     rcx; switch jump
0x18023c49f  jmp     loc_18023CAA6; jumptable 000000018023C49D case 3
0x18023c4a4  xor     esi, esi; jumptable 000000018023C49D case 2
0x18023c4a6  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18023c4ad  lea     rcx, [rdi+0A0h]
0x18023c4b4  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x18023c4b9  nop
0x18023c4ba  lea     rax, [rdi+10h]
0x18023c4be  mov     [rdi+120h], rax
0x18023c4c5  mov     [rdi+1E0h], rax
0x18023c4cc  mov     [rdi+0A8h], sil
0x18023c4d3  mov     ecx, [rax+60h]
0x18023c4d6  cmp     ecx, 2
0x18023c4d9  jnz     short loc_18023C518
0x18023c4db  lea     rdx, [rdi+138h]; struct winrt::impl::slim_source_location *
0x18023c4e2  mov     dword ptr [rdx], 1628h
0x18023c4e8  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18023c4ef  mov     [rdi+140h], rax
0x18023c4f6  mov     [rdi+148h], rsi
0x18023c4fd  lea     rcx, [rsp+128h+pExceptionObject]; this
0x18023c502  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18023c507  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18023c50e  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x18023c513  call    _CxxThrowException
0x18023c518  mov     eax, 4
0x18023c51d  mov     [rdi+98h], ax
0x18023c524  mov     rdx, rdi
0x18023c527  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x18023c52c  jmp     loc_18023CADB
0x18023c531  mov     rcx, [rdi+0A0h]; jumptable 000000018023C49D case 5
0x18023c538  test    rcx, rcx
0x18023c53b  jz      short loc_18023C552
0x18023c53d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18023c541  jz      short loc_18023C552
0x18023c543  mov     [rsp+128h+arg_10], rcx
0x18023c54b  call    cs:__imp_CloseHandle
0x18023c551  nop
0x18023c552  mov     eax, 0FFFFFFFFh
0x18023c557  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18023c55f  sub     eax, 1
0x18023c562  jz      short loc_18023C56E
0x18023c564  test    eax, eax
0x18023c566  jns     short loc_18023C56E
0x18023c568  call    abort
0x18023c56e  jmp     loc_18023CAA6; jumptable 000000018023C49D cases -1,1
0x18023c573  mov     rbx, [rdi+120h]; jumptable 000000018023C49D case 4
0x18023c57a  mov     [rdi+0B0h], rbx
0x18023c581  mov     [rdi+0B8h], rbx
0x18023c588  mov     dword ptr [rdi+0C0h], 1
0x18023c592  xor     esi, esi
0x18023c594  mov     [rdi+0C8h], rsi
0x18023c59b  lea     r14, [rbx+48h]
0x18023c59f  mov     [rdi+1A0h], r14
0x18023c5a6  mov     rcx, r14; SRWLock
0x18023c5a9  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18023c5ae  mov     rcx, [rbx+70h]
0x18023c5b2  mov     [rdi+188h], rcx
0x18023c5b9  test    rcx, rcx
0x18023c5bc  jz      short loc_18023C5FC
0x18023c5be  mov     [rsp+128h+var_F8], rcx
0x18023c5c3  mov     rax, [rcx]
0x18023c5c6  mov     rax, [rax+8]
0x18023c5ca  call    cs:__guard_dispatch_icall_fptr
0x18023c5d0  mov     rcx, r14; SRWLock
0x18023c5d3  call    ReleaseSRWLockExclusive_0
0x18023c5d8  lea     r8, [rdi+0C0h]
0x18023c5df  mov     rdx, rbx
0x18023c5e2  lea     rcx, [rdi+188h]
0x18023c5e9  call    ??$invoke@U?$AsyncOperationProgressHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@UPackageDeploymentProgress@Deployment@Management@3Microsoft@4@@impl@winrt@@YA_NAEBU?$AsyncOperationProgressHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@1@AEBUpromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@AEBUPackageDeploymentProgress@Deployment@Management@4Microsoft@1@@Z; winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> const &,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type const &,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress const &)
0x18023c5ee  lea     rcx, [rdi+188h]
0x18023c5f5  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023c5fa  jmp     short loc_18023C604
0x18023c5fc  mov     rcx, r14; SRWLock
0x18023c5ff  call    ReleaseSRWLockExclusive_0
0x18023c604  mov     rbx, [rdi+90h]
0x18023c60b  mov     [rdi+200h], rbx
0x18023c612  mov     [rdi+0D0h], rbx
0x18023c619  test    rbx, rbx
0x18023c61c  jz      short loc_18023C62F
0x18023c61e  mov     rax, [rbx]
0x18023c621  mov     rcx, rbx
0x18023c624  mov     rax, [rax+8]
0x18023c628  call    cs:__guard_dispatch_icall_fptr
0x18023c62e  nop
0x18023c62f  mov     r12, [rdi+0A0h]
0x18023c636  test    r12, r12
0x18023c639  jnz     short loc_18023C672
0x18023c63b  mov     [rdi+160h], rbx
0x18023c642  test    rbx, rbx
0x18023c645  jz      short loc_18023C657
0x18023c647  mov     rax, [rbx]
0x18023c64a  mov     rcx, rbx
0x18023c64d  mov     rax, [rax+8]
0x18023c651  call    cs:__guard_dispatch_icall_fptr
0x18023c657  lea     rbx, [rdi+0D8h]
0x18023c65e  lea     rdx, [rdi+160h]
0x18023c665  mov     rcx, rbx
0x18023c668  call    ?MakeEmbeddingsGeneratorAvailableForOptionsAsync@SemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@8@USemanticTextIndexStoreOptions@345678@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::MakeEmbeddingsGeneratorAvailableForOptionsAsync(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions)
0x18023c66d  jmp     loc_18023C72E
0x18023c672  lea     rcx, [rdi+150h]
0x18023c679  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x18023c67e  nop
0x18023c67f  mov     r14, [rdi+150h]
0x18023c686  mov     [rdi+150h], rsi
0x18023c68d  mov     [rdi+158h], r14
0x18023c694  mov     rcx, r12; hToken
0x18023c697  call    cs:__imp_ImpersonateLoggedOnUser
0x18023c69d  mov     rcx, [rsp+128h]; this
0x18023c6a5  test    eax, eax
0x18023c6a7  jnz     short loc_18023C6B3
0x18023c6a9  mov     edx, 1Ch; void *
0x18023c6ae  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18023c6b3  mov     [rdi+180h], rbx
0x18023c6ba  test    rbx, rbx
0x18023c6bd  jz      short loc_18023C6CF
0x18023c6bf  mov     rax, [rbx]
0x18023c6c2  mov     rcx, rbx
0x18023c6c5  mov     rax, [rax+8]
0x18023c6c9  call    cs:__guard_dispatch_icall_fptr
0x18023c6cf  lea     rbx, [rdi+0D8h]
0x18023c6d6  lea     rdx, [rdi+180h]
0x18023c6dd  mov     rcx, rbx
0x18023c6e0  call    ?MakeEmbeddingsGeneratorAvailableForOptionsAsync@SemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@8@USemanticTextIndexStoreOptions@345678@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::MakeEmbeddingsGeneratorAvailableForOptionsAsync(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions)
0x18023c6e5  nop
0x18023c6e6  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18023c6ea  jz      short loc_18023C710
0x18023c6ec  mov     rdx, r14; Token
0x18023c6ef  xor     ecx, ecx; Thread
0x18023c6f1  call    cs:__imp_SetThreadToken
0x18023c6f7  test    eax, eax
0x18023c6f9  jnz     short loc_18023C701
0x18023c6fb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18023c701  test    r14, r14
0x18023c704  jz      short loc_18023C710
0x18023c706  mov     rcx, r14; hObject
0x18023c709  call    cs:__imp_CloseHandle
0x18023c70f  nop
0x18023c710  mov     rcx, [rdi+150h]; hObject
0x18023c717  test    rcx, rcx
0x18023c71a  jz      short loc_18023C72E
0x18023c71c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18023c720  jz      short loc_18023C72E
0x18023c722  mov     [rsp+128h+var_F0], rcx
0x18023c727  call    cs:__imp_CloseHandle
0x18023c72d  nop
0x18023c72e  mov     eax, [rdi+70h]
0x18023c731  cmp     eax, 2
0x18023c734  jnz     short loc_18023C773
0x18023c736  lea     rdx, [rdi+168h]; struct winrt::impl::slim_source_location *
0x18023c73d  mov     dword ptr [rdx], 1628h
0x18023c743  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18023c74a  mov     [rdi+170h], rax
0x18023c751  mov     [rdi+178h], rsi
0x18023c758  lea     rcx, [rsp+128h+var_C8]; this
0x18023c75d  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18023c762  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18023c769  lea     rcx, [rsp+128h+var_C8]; pExceptionObject
0x18023c76e  call    _CxxThrowException
0x18023c773  lea     rcx, [rdi+0E0h]
0x18023c77a  mov     [rcx], rsi
0x18023c77d  mov     [rdi+0E8h], rbx
0x18023c784  mov     [rdi+0F0h], rsi
0x18023c78b  mov     byte ptr [rdi+0F8h], 1
0x18023c792  mov     eax, 8
0x18023c797  mov     [rdi+98h], ax
0x18023c79e  mov     rdx, rdi
0x18023c7a1  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type>)
0x18023c7a6  test    al, al
0x18023c7a8  jz      loc_18023C85D
0x18023c7ae  jmp     loc_18023CADB
0x18023c7b3  mov     rbx, [rdi+0E0h]; jumptable 000000018023C49D case 9
0x18023c7ba  test    rbx, rbx
0x18023c7bd  jz      short loc_18023C7E5
0x18023c7bf  mov     [rsp+128h+var_A0], rbx
0x18023c7c7  xor     esi, esi
0x18023c7c9  mov     eax, esi
0x18023c7cb  xchg    rax, [rbx]
0x18023c7ce  cmp     rax, 1
0x18023c7d2  jnz     short loc_18023C7E5
0x18023c7d4  call    _Thrd_yield
0x18023c7d9  mov     rax, rsi
0x18023c7dc  xchg    rax, [rbx]
0x18023c7df  cmp     rax, 1
0x18023c7e3  jz      short loc_18023C7D4
0x18023c7e5  lea     rcx, [rdi+0D8h]
0x18023c7ec  mov     rax, [rcx]
0x18023c7ef  mov     [rsp+128h+arg_18], rax
0x18023c7f7  test    rax, rax
0x18023c7fa  jz      short loc_18023C802
0x18023c7fc  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023c801  nop
0x18023c802  cmp     qword ptr [rdi+200h], 0
0x18023c80a  jz      short loc_18023C819
0x18023c80c  lea     rcx, [rdi+0D0h]
0x18023c813  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023c818  nop
0x18023c819  mov     rcx, [rdi+0A0h]; hObject
0x18023c820  test    rcx, rcx
0x18023c823  jz      short loc_18023C83A
0x18023c825  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18023c829  jz      short loc_18023C83A
0x18023c82b  mov     [rsp+128h+arg_10], rcx
0x18023c833  call    cs:__imp_CloseHandle
0x18023c839  nop
0x18023c83a  mov     eax, 0FFFFFFFFh
0x18023c83f  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18023c847  sub     eax, 1
0x18023c84a  jz      short loc_18023C856
0x18023c84c  test    eax, eax
0x18023c84e  jns     short loc_18023C856
0x18023c850  call    abort
0x18023c856  jmp     loc_18023CAA6; jumptable 000000018023C49D cases -1,1
0x18023c85b  xor     esi, esi; jumptable 000000018023C49D case 8
0x18023c85d  lea     r14, [rdi+100h]
0x18023c864  mov     rdx, r14
0x18023c867  lea     rcx, [rdi+0E0h]
0x18023c86e  call    ?await_resume@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_resume(void)
0x18023c873  nop
0x18023c874  mov     rbx, [rdi+0E0h]
0x18023c87b  test    rbx, rbx
0x18023c87e  jz      short loc_18023C8A5
0x18023c880  mov     [rsp+128h+var_A0], rbx
0x18023c888  mov     rax, rsi
0x18023c88b  xchg    rax, [rbx]
0x18023c88e  cmp     rax, 1
0x18023c892  jnz     short loc_18023C8A5
0x18023c894  call    _Thrd_yield
0x18023c899  mov     rax, rsi
0x18023c89c  xchg    rax, [rbx]
0x18023c89f  cmp     rax, 1
0x18023c8a3  jz      short loc_18023C894
0x18023c8a5  lea     rcx, [rdi+0D8h]
0x18023c8ac  mov     rax, [rcx]
0x18023c8af  mov     [rsp+128h+arg_18], rax
0x18023c8b7  test    rax, rax
0x18023c8ba  jz      short loc_18023C8C2
0x18023c8bc  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023c8c1  nop
0x18023c8c2  cmp     qword ptr [rdi+200h], 0
0x18023c8ca  jz      short loc_18023C8D8
0x18023c8cc  lea     rcx, [rdi+0D0h]
0x18023c8d3  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023c8d8  mov     ebx, 2
0x18023c8dd  mov     rcx, [r14]
0x18023c8e0  test    rcx, rcx
0x18023c8e3  jz      short loc_18023C950
0x18023c8e5  mov     [rdi+1B0h], esi
0x18023c8eb  mov     dword ptr [rdi+1B8h], 5A0h
0x18023c8f5  lea     rax, aCW1SX64Release_14; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18023c8fc  mov     [rdi+1C0h], rax
0x18023c903  mov     [rdi+1C8h], rsi
0x18023c90a  mov     [rsp+128h+var_100], rcx
0x18023c90f  mov     rax, [rcx]
0x18023c912  lea     rdx, [rdi+1B0h]
0x18023c919  mov     rax, [rax+30h]
0x18023c91d  call    cs:__guard_dispatch_icall_fptr
0x18023c923  test    eax, eax
0x18023c925  jns     short loc_18023C938
0x18023c927  lfence
0x18023c92a  lea     rdx, [rdi+1B8h]
0x18023c931  mov     ecx, eax
0x18023c933  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18023c938  mov     eax, [rdi+1B0h]
0x18023c93e  mov     [rsp+128h+arg_8], eax
0x18023c945  mov     ecx, 3
0x18023c94a  cmp     eax, 1
0x18023c94d  cmovnz  ebx, ecx
0x18023c950  mov     [rdi+108h], ebx
0x18023c956  mov     rax, 3FF0000000000000h
0x18023c960  mov     [rdi+110h], rax
0x18023c967  movups  xmm0, xmmword ptr [rdi+108h]
0x18023c96e  movups  [rsp+128h+var_B0], xmm0
0x18023c973  movups  xmmword ptr [rdi+0C0h], xmm0
0x18023c97a  mov     rbx, [rdi+1A0h]
0x18023c981  mov     rcx, rbx; SRWLock
0x18023c984  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18023c989  mov     r13, [rdi+0B8h]
0x18023c990  mov     rcx, [r13+70h]
0x18023c994  mov     [rdi+198h], rcx
0x18023c99b  test    rcx, rcx
0x18023c99e  jz      short loc_18023C9DE
  ... truncated ...
```
