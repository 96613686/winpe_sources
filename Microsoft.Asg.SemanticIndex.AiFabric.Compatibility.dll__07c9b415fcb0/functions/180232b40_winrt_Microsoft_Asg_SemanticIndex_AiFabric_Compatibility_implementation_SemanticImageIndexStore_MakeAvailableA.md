# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::MakeAvailableAsync$_ResumeCoro$1

- ea: `0x180232b40`
- end: `0x1802337c0`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::MakeAvailableAsync$_ResumeCoro$1`
- size: `3200`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001b5a0`
- `0x180232b30`

## callees

- `0x180003bd0`
- `0x18000d4b0`
- `0x180010dd0`
- `0x18001b3c0`
- `0x18001b680`
- `0x18001b830`
- `0x18001c560`
- `0x18001cb00`
- `0x18001fd50`
- `0x180021690`
- `0x180032bf0`
- `0x180047120`
- `0x180047520`
- `0x1800475c0`
- `0x180078d56`
- `0x180078d5c`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f97e0`
- `0x180206a58`
- `0x180232b40`
- `0x180242120`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180232c34`
- `KERNEL32!CloseHandle` at `0x180232df2`
- `KERNEL32!CloseHandle` at `0x180232e10`
- `KERNEL32!CloseHandle` at `0x180232f1f`
- `KERNEL32!CloseHandle` at `0x180233163`
- `KERNEL32!CloseHandle` at `0x180233181`
- `KERNEL32!CloseHandle` at `0x1802332ae`
- `KERNEL32!CloseHandle` at `0x180233519`
- `KERNEL32!CloseHandle` at `0x1802336ed`
- `KERNEL32!CloseHandle` at `0x180232c34`
- `KERNEL32!CloseHandle` at `0x180232df2`
- `KERNEL32!CloseHandle` at `0x180232e10`
- `KERNEL32!CloseHandle` at `0x180232f1f`
- `KERNEL32!CloseHandle` at `0x180233163`
- `KERNEL32!CloseHandle` at `0x180233181`
- `KERNEL32!CloseHandle` at `0x1802332ae`
- `KERNEL32!CloseHandle` at `0x180233519`
- `KERNEL32!CloseHandle` at `0x1802336ed`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180232dda`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18023314b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180232dda`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18023314b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180232d80`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1802330f1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180232d80`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1802330f1`

## string_xrefs

- `0x180232bd1`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x180232e2c`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18023319d`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x180233382`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Windows.Management.Deployment.h`
- `0x18023353f`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Windows.Management.Deployment.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::MakeAvailableAsync__ResumeCoro_1(
        __int64 a1)
{
  __int64 v2; // rcx
  void *v3; // rcx
  RTL_SRWLOCK *v4; // rbx
  PVOID Ptr; // rcx
  __int64 v6; // rbx
  void *v7; // r12
  __int64 v8; // rbx
  void *v9; // r14
  unsigned int v10; // r8d
  const char *v11; // r9
  wil::details::in1diag3 *v12; // rcx
  void *v13; // rcx
  volatile __int64 *v14; // rbx
  void *v15; // rcx
  volatile __int64 *v16; // rbx
  RTL_SRWLOCK *v17; // rbx
  __int64 v18; // r13
  __int64 v19; // rcx
  __int64 v20; // rbx
  void *v21; // r12
  __int64 v22; // rbx
  void *v23; // r14
  unsigned int v24; // r8d
  const char *v25; // r9
  wil::details::in1diag3 *v26; // rcx
  void *v27; // rcx
  volatile __int64 *v28; // rbx
  void *v29; // rcx
  volatile __int64 *v30; // rbx
  _QWORD *v31; // r14
  _QWORD *v32; // rbx
  int v33; // r13d
  __int64 *v34; // r15
  __int64 v35; // rcx
  int v36; // eax
  RTL_SRWLOCK *v37; // rbx
  __int64 v38; // rcx
  _QWORD *v39; // rbx
  __int64 v40; // rax
  void *v41; // rcx
  __int64 v42; // rcx
  _QWORD *v43; // r15
  int v44; // eax
  RTL_SRWLOCK *v45; // rbx
  __int64 v46; // rcx
  _QWORD *v47; // rbx
  __int64 v48; // rax
  _QWORD *v49; // rbx
  void *v50; // rcx
  _BYTE pExceptionObject[24]; // [rsp+78h] [rbp-150h] BYREF
  _BYTE v52[24]; // [rsp+90h] [rbp-138h] BYREF
  _BYTE v53[24]; // [rsp+A8h] [rbp-120h] BYREF
  __int128 v54; // [rsp+C0h] [rbp-108h]
  __int128 v55; // [rsp+D0h] [rbp-F8h]
  __int64 v56; // [rsp+E0h] [rbp-E8h]
  __int64 v57; // [rsp+100h] [rbp-C8h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  switch ( *(_WORD *)(a1 + 152) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_144;
    case 2:
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      ImpersonationHelper::GetThreadImpersonationToken(a1 + 160);
      *(_QWORD *)(a1 + 288) = a1 + 16;
      *(_BYTE *)(a1 + 168) = 0;
      v2 = *(unsigned int *)(a1 + 112);
      if ( (_DWORD)v2 == 2 )
      {
        *(_DWORD *)(a1 + 400) = 5672;
        *(_QWORD *)(a1 + 408) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generat"
                                "ed Files\\winrt\\Windows.Foundation.h";
        *(_QWORD *)(a1 + 416) = 0;
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)pExceptionObject,
          (const struct winrt::impl::slim_source_location *)(a1 + 400));
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *(_WORD *)(a1 + 152) = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v2, a1);
      return;
    case 4:
      v4 = *(RTL_SRWLOCK **)(a1 + 288);
      *(_QWORD *)(a1 + 176) = v4;
      *(_QWORD *)(a1 + 184) = v4;
      *(_DWORD *)(a1 + 192) = 1;
      *(_QWORD *)(a1 + 200) = 0;
      *(_QWORD *)(a1 + 464) = v4 + 9;
      WINRT_IMPL_AcquireSRWLockExclusive(v4 + 9);
      Ptr = v4[14].Ptr;
      *(_QWORD *)(a1 + 424) = Ptr;
      if ( Ptr )
      {
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 8LL))(Ptr);
        ReleaseSRWLockExclusive_0(v4 + 9);
        winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(
          a1 + 424,
          v4,
          a1 + 192);
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 424);
      }
      else
      {
        ReleaseSRWLockExclusive_0(v4 + 9);
      }
      v6 = *(_QWORD *)(a1 + 144);
      *(_QWORD *)(a1 + 704) = v6;
      *(_QWORD *)(a1 + 208) = v6;
      if ( v6 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
      v7 = *(void **)(a1 + 160);
      if ( v7 )
      {
        ImpersonationHelper::GetThreadImpersonationToken(a1 + 440);
        v9 = *(void **)(a1 + 440);
        *(_QWORD *)(a1 + 440) = 0;
        *(_QWORD *)(a1 + 432) = v9;
        if ( !ImpersonateLoggedOnUser(v7) )
          wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x1C, v10, v11);
        *(_QWORD *)(a1 + 504) = v6;
        if ( v6 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
        v8 = a1 + 216;
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::MakeEmbeddingsGeneratorAvailableForOptionsAsync(
          a1 + 216,
          a1 + 504);
        if ( v9 != (void *)-1LL )
        {
          if ( !SetThreadToken(0, v9) )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(v12);
          if ( v9 )
            CloseHandle(v9);
        }
        v13 = *(void **)(a1 + 440);
        if ( v13 && v13 != (void *)-1LL )
          CloseHandle(v13);
      }
      else
      {
        *(_QWORD *)(a1 + 448) = v6;
        if ( v6 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
        v8 = a1 + 216;
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::MakeEmbeddingsGeneratorAvailableForOptionsAsync(
          a1 + 216,
          a1 + 448);
      }
      if ( *(_DWORD *)(a1 + 112) == 2 )
      {
        *(_DWORD *)(a1 + 480) = 5672;
        *(_QWORD *)(a1 + 488) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generat"
                                "ed Files\\winrt\\Windows.Foundation.h";
        *(_QWORD *)(a1 + 496) = 0;
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)v52,
          (const struct winrt::impl::slim_source_location *)(a1 + 480));
        throw (winrt::hresult_canceled *)v52;
      }
      *(_QWORD *)(a1 + 224) = 0;
      *(_QWORD *)(a1 + 232) = v8;
      *(_QWORD *)(a1 + 240) = 0;
      *(_BYTE *)(a1 + 248) = 1;
      *(_WORD *)(a1 + 152) = 8;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type>(
                              (_QWORD *)(a1 + 224),
                              a1) )
        return;
      goto LABEL_47;
    case 5:
      v3 = *(void **)(a1 + 160);
      if ( v3 && v3 != (void *)-1LL )
        CloseHandle(v3);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      goto LABEL_144;
    case 8:
LABEL_47:
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_resume(
        a1 + 224,
        a1 + 256);
      v16 = *(volatile __int64 **)(a1 + 224);
      if ( v16 )
      {
        v56 = *(_QWORD *)(a1 + 224);
        while ( _InterlockedExchange64(v16, 0) == 1 )
          Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 216) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 216);
      if ( *(_QWORD *)(a1 + 704) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 208);
      *(_DWORD *)(a1 + 264) = 1;
      *(_QWORD *)(a1 + 272) = 0x3FE0000000000000LL;
      v54 = *(_OWORD *)(a1 + 264);
      *(_OWORD *)(a1 + 192) = v54;
      v17 = *(RTL_SRWLOCK **)(a1 + 464);
      WINRT_IMPL_AcquireSRWLockExclusive(v17);
      v18 = *(_QWORD *)(a1 + 184);
      v19 = *(_QWORD *)(v18 + 112);
      *(_QWORD *)(a1 + 568) = v19;
      if ( v19 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
        ReleaseSRWLockExclusive_0(v17);
        winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(
          a1 + 568,
          v18,
          a1 + 192);
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 568);
      }
      else
      {
        ReleaseSRWLockExclusive_0(v17);
      }
      v20 = *(_QWORD *)(a1 + 144);
      *(_QWORD *)(a1 + 688) = v20;
      *(_QWORD *)(a1 + 304) = v20;
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
      v21 = *(void **)(a1 + 160);
      if ( v21 )
      {
        ImpersonationHelper::GetThreadImpersonationToken(a1 + 520);
        v23 = *(void **)(a1 + 520);
        *(_QWORD *)(a1 + 520) = 0;
        *(_QWORD *)(a1 + 512) = v23;
        if ( !ImpersonateLoggedOnUser(v21) )
          wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x1C, v24, v25);
        *(_QWORD *)(a1 + 560) = v20;
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
        v22 = a1 + 312;
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::MakeTextQueryEmbeddingsGeneratorAvailableForOptionsAsync(
          a1 + 312,
          a1 + 560);
        if ( v23 != (void *)-1LL )
        {
          if ( !SetThreadToken(0, v23) )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(v26);
          if ( v23 )
            CloseHandle(v23);
        }
        v27 = *(void **)(a1 + 520);
        if ( v27 && v27 != (void *)-1LL )
          CloseHandle(v27);
      }
      else
      {
        *(_QWORD *)(a1 + 528) = v20;
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
        v22 = a1 + 312;
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::MakeTextQueryEmbeddingsGeneratorAvailableForOptionsAsync(
          a1 + 312,
          a1 + 528);
      }
      if ( *(_DWORD *)(a1 + 112) == 2 )
      {
        *(_DWORD *)(a1 + 536) = 5672;
        *(_QWORD *)(a1 + 544) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generat"
                                "ed Files\\winrt\\Windows.Foundation.h";
        *(_QWORD *)(a1 + 552) = 0;
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)v53,
          (const struct winrt::impl::slim_source_location *)(a1 + 536));
        throw (winrt::hresult_canceled *)v53;
      }
      *(_QWORD *)(a1 + 320) = 0;
      *(_QWORD *)(a1 + 328) = v22;
      *(_QWORD *)(a1 + 336) = 0;
      *(_BYTE *)(a1 + 344) = 1;
      *(_WORD *)(a1 + 152) = 10;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type>(
                              (_QWORD *)(a1 + 320),
                              a1) )
        return;
      goto LABEL_93;
    case 9:
      v14 = *(volatile __int64 **)(a1 + 224);
      if ( v14 )
      {
        v56 = *(_QWORD *)(a1 + 224);
        while ( _InterlockedExchange64(v14, 0) == 1 )
          Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 216) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 216);
      if ( *(_QWORD *)(a1 + 704) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 208);
      v15 = *(void **)(a1 + 160);
      if ( v15 && v15 != (void *)-1LL )
        CloseHandle(v15);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      goto LABEL_144;
    case 0xA:
LABEL_93:
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_resume(
        a1 + 320,
        a1 + 352);
      v30 = *(volatile __int64 **)(a1 + 320);
      v31 = (_QWORD *)(a1 + 352);
      if ( v30 )
      {
        v57 = *(_QWORD *)(a1 + 320);
        v31 = (_QWORD *)(a1 + 352);
        if ( _InterlockedExchange64(v30, 0) == 1 )
        {
          do
            Thrd_yield();
          while ( _InterlockedExchange64(v30, 0) == 1 );
          v31 = (_QWORD *)(a1 + 352);
        }
      }
      if ( *(_QWORD *)(a1 + 312) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 312);
      v32 = v31;
      if ( *(_QWORD *)(a1 + 688) )
      {
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 304);
        v32 = (_QWORD *)(a1 + 352);
      }
      v33 = 2;
      v34 = (__int64 *)(a1 + 256);
      v35 = *(_QWORD *)(a1 + 256);
      if ( v35 )
      {
        *(_DWORD *)(a1 + 588) = 0;
        *(_DWORD *)(a1 + 600) = 1440;
        *(_QWORD *)(a1 + 608) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generat"
                                "ed Files\\winrt\\Microsoft.Windows.Management.Deployment.h";
        *(_QWORD *)(a1 + 616) = 0;
        v36 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 48LL))(v35);
        if ( v36 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v36, a1 + 600);
        }
        v31 = v32;
        if ( *(_DWORD *)(a1 + 588) != 1 )
        {
          *(_DWORD *)(a1 + 360) = 3;
          *(_QWORD *)(a1 + 368) = 0x3FF0000000000000LL;
          *(_OWORD *)(a1 + 192) = *(_OWORD *)(a1 + 360);
          v37 = *(RTL_SRWLOCK **)(a1 + 464);
          WINRT_IMPL_AcquireSRWLockExclusive(v37);
          v38 = *(_QWORD *)(*(_QWORD *)(a1 + 184) + 112LL);
          *(_QWORD *)(a1 + 664) = v38;
          if ( v38 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 8LL))(v38);
            ReleaseSRWLockExclusive_0(v37);
            winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(
              a1 + 664,
              *(_QWORD *)(a1 + 184),
              a1 + 192);
            winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 664);
          }
          else
          {
            ReleaseSRWLockExclusive_0(v37);
          }
          WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)(a1 + 88));
          v39 = (_QWORD *)(a1 + 120);
          if ( (__int64 *)(a1 + 120) != v34 )
          {
            if ( *v39 )
              winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 120);
            v40 = *v34;
            *v34 = 0;
            *v39 = v40;
          }
          ReleaseSRWLockExclusive_0((PSRWLOCK)(a1 + 88));
          if ( *(_QWORD *)(a1 + 352) )
            winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 352);
          if ( *v34 )
            winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 256);
          v41 = *(void **)(a1 + 160);
          if ( v41 && v41 != (void *)-1LL )
            CloseHandle(v41);
          if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) >= 0 )
            goto LABEL_143;
LABEL_142:
          abort();
        }
      }
      v42 = *v31;
      v43 = v31;
      if ( *v31 )
      {
        *(_DWORD *)(a1 + 624) = 0;
        *(_DWORD *)(a1 + 632) = 1440;
        *(_QWORD *)(a1 + 640) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generat"
                                "ed Files\\winrt\\Microsoft.Windows.Management.Deployment.h";
        *(_QWORD *)(a1 + 648) = 0;
        v44 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v42 + 48LL))(v42, a1 + 624);
        if ( v44 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v44, a1 + 632);
        }
        if ( *(_DWORD *)(a1 + 624) != 1 )
        {
          v33 = 3;
          v43 = (_QWORD *)(a1 + 352);
        }
      }
      *(_DWORD *)(a1 + 376) = v33;
      *(_QWORD *)(a1 + 384) = 0x3FF0000000000000LL;
      v55 = *(_OWORD *)(a1 + 376);
      *(_OWORD *)(a1 + 192) = v55;
      v45 = *(RTL_SRWLOCK **)(a1 + 464);
      WINRT_IMPL_AcquireSRWLockExclusive(v45);
      v46 = *(_QWORD *)(*(_QWORD *)(a1 + 184) + 112LL);
      *(_QWORD *)(a1 + 576) = v46;
      if ( v46 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 8LL))(v46);
        ReleaseSRWLockExclusive_0(v45);
        winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(
          a1 + 576,
          *(_QWORD *)(a1 + 184),
          a1 + 192);
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 576);
        v31 = v43;
      }
      else
      {
        v43 = v31;
        ReleaseSRWLockExclusive_0(v45);
      }
      WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)(a1 + 88));
      v47 = (_QWORD *)(a1 + 120);
      if ( (_QWORD *)(a1 + 120) == v31 )
      {
        v49 = v43;
      }
      else
      {
        if ( *v47 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 120);
        v48 = *v43;
        *v43 = 0;
        *v47 = v48;
        v49 = (_QWORD *)(a1 + 352);
      }
      ReleaseSRWLockExclusive_0((PSRWLOCK)(a1 + 88));
      if ( *v43 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v49);
      if ( *(_QWORD *)(a1 + 256) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 256);
      v50 = *(void **)(a1 + 160);
      if ( v50 && v50 != (void *)-1LL )
        CloseHandle(v50);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        goto LABEL_142;
LABEL_143:
      *(_QWORD *)(a1 + 392) = a1 + 16;
      *(_WORD *)(a1 + 152) = 0;
      *(_QWORD *)a1 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::final_suspend_awaiter::await_suspend() )
      {
LABEL_144:
        std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type::~promise_type(a1 + 16);
        if ( *(_QWORD *)(a1 + 144) )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 144);
        if ( *(_WORD *)(a1 + 154) )
          operator delete((void *)a1);
      }
      return;
    case 0xB:
      v28 = *(volatile __int64 **)(a1 + 320);
      if ( v28 )
      {
        v57 = *(_QWORD *)(a1 + 320);
        while ( _InterlockedExchange64(v28, 0) == 1 )
          Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 312) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 312);
      if ( *(_QWORD *)(a1 + 688) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 304);
      if ( *(_QWORD *)(a1 + 256) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 256);
      v29 = *(void **)(a1 + 160);
      if ( v29 && v29 != (void *)-1LL )
        CloseHandle(v29);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      goto LABEL_144;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x180232b40  mov     [rsp+Block], rcx
0x180232b45  push    rbx
0x180232b46  push    rsi
0x180232b47  push    rdi
0x180232b48  push    r12
0x180232b4a  push    r13
0x180232b4c  push    r14
0x180232b4e  push    r15
0x180232b50  sub     rsp, 190h
0x180232b57  mov     rdi, [rsp+1C8h+Block]
0x180232b5f  movzx   eax, word ptr [rdi+98h]
0x180232b66  mov     [rsp+1C8h+var_1A8], ax
0x180232b6b  inc     ax; switch 13 cases
0x180232b6e  cmp     ax, 0Ch
0x180232b72  ja      def_180232B8D; jumptable 0000000180232B8D default case, cases 0,6,7
0x180232b78  movsx   rax, ax
0x180232b7c  lea     rdx, cs:180000000h
0x180232b83  mov     ecx, ds:(jpt_180232B8D - 180000000h)[rdx+rax*4]
0x180232b8a  add     rcx, rdx
0x180232b8d  jmp     rcx; switch jump
0x180232b8f  jmp     loc_180233740; jumptable 0000000180232B8D case 3
0x180232b94  xor     esi, esi; jumptable 0000000180232B8D case 2
0x180232b96  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180232b9d  lea     rcx, [rdi+0A0h]
0x180232ba4  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x180232ba9  nop
0x180232baa  lea     rax, [rdi+10h]
0x180232bae  mov     [rdi+120h], rax
0x180232bb5  mov     [rdi+0A8h], sil
0x180232bbc  mov     ecx, [rax+60h]
0x180232bbf  cmp     ecx, 2
0x180232bc2  jnz     short loc_180232C01
0x180232bc4  lea     rdx, [rdi+190h]; struct winrt::impl::slim_source_location *
0x180232bcb  mov     dword ptr [rdx], 1628h
0x180232bd1  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180232bd8  mov     [rdi+198h], rax
0x180232bdf  mov     [rdi+1A0h], rsi
0x180232be6  lea     rcx, [rsp+1C8h+pExceptionObject]; this
0x180232beb  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180232bf0  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180232bf7  lea     rcx, [rsp+1C8h+pExceptionObject]; pExceptionObject
0x180232bfc  call    _CxxThrowException
0x180232c01  mov     eax, 4
0x180232c06  mov     [rdi+98h], ax
0x180232c0d  mov     rdx, rdi
0x180232c10  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x180232c15  jmp     loc_180233775
0x180232c1a  mov     rcx, [rdi+0A0h]; jumptable 0000000180232B8D case 5
0x180232c21  test    rcx, rcx
0x180232c24  jz      short loc_180232C3B
0x180232c26  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180232c2a  jz      short loc_180232C3B
0x180232c2c  mov     [rsp+1C8h+arg_18], rcx
0x180232c34  call    cs:__imp_CloseHandle
0x180232c3a  nop
0x180232c3b  mov     eax, 0FFFFFFFFh
0x180232c40  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180232c48  sub     eax, 1
0x180232c4b  jz      short loc_180232C57
0x180232c4d  test    eax, eax
0x180232c4f  jns     short loc_180232C57
0x180232c51  call    abort
0x180232c57  jmp     loc_180233740; jumptable 0000000180232B8D cases -1,1
0x180232c5c  mov     rbx, [rdi+120h]; jumptable 0000000180232B8D case 4
0x180232c63  mov     [rdi+0B0h], rbx
0x180232c6a  mov     [rdi+0B8h], rbx
0x180232c71  mov     dword ptr [rdi+0C0h], 1
0x180232c7b  xor     esi, esi
0x180232c7d  mov     [rdi+0C8h], rsi
0x180232c84  lea     r14, [rbx+48h]
0x180232c88  mov     [rdi+1D0h], r14
0x180232c8f  mov     rcx, r14; SRWLock
0x180232c92  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180232c97  mov     rcx, [rbx+70h]
0x180232c9b  mov     [rdi+1A8h], rcx
0x180232ca2  test    rcx, rcx
0x180232ca5  jz      short loc_180232CE5
0x180232ca7  mov     [rsp+1C8h+var_180], rcx
0x180232cac  mov     rax, [rcx]
0x180232caf  mov     rax, [rax+8]
0x180232cb3  call    cs:__guard_dispatch_icall_fptr
0x180232cb9  mov     rcx, r14; SRWLock
0x180232cbc  call    ReleaseSRWLockExclusive_0
0x180232cc1  lea     r8, [rdi+0C0h]
0x180232cc8  mov     rdx, rbx
0x180232ccb  lea     rcx, [rdi+1A8h]
0x180232cd2  call    ??$invoke@U?$AsyncOperationProgressHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@UPackageDeploymentProgress@Deployment@Management@3Microsoft@4@@impl@winrt@@YA_NAEBU?$AsyncOperationProgressHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@1@AEBUpromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@AEBUPackageDeploymentProgress@Deployment@Management@4Microsoft@1@@Z; winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> const &,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type const &,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress const &)
0x180232cd7  lea     rcx, [rdi+1A8h]
0x180232cde  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180232ce3  jmp     short loc_180232CED
0x180232ce5  mov     rcx, r14; SRWLock
0x180232ce8  call    ReleaseSRWLockExclusive_0
0x180232ced  mov     rbx, [rdi+90h]
0x180232cf4  mov     [rdi+2C0h], rbx
0x180232cfb  mov     [rdi+0D0h], rbx
0x180232d02  test    rbx, rbx
0x180232d05  jz      short loc_180232D18
0x180232d07  mov     rax, [rbx]
0x180232d0a  mov     rcx, rbx
0x180232d0d  mov     rax, [rax+8]
0x180232d11  call    cs:__guard_dispatch_icall_fptr
0x180232d17  nop
0x180232d18  mov     r12, [rdi+0A0h]
0x180232d1f  test    r12, r12
0x180232d22  jnz     short loc_180232D5B
0x180232d24  mov     [rdi+1C0h], rbx
0x180232d2b  test    rbx, rbx
0x180232d2e  jz      short loc_180232D40
0x180232d30  mov     rax, [rbx]
0x180232d33  mov     rcx, rbx
0x180232d36  mov     rax, [rax+8]
0x180232d3a  call    cs:__guard_dispatch_icall_fptr
0x180232d40  lea     rbx, [rdi+0D8h]
0x180232d47  lea     rdx, [rdi+1C0h]
0x180232d4e  mov     rcx, rbx
0x180232d51  call    ?MakeEmbeddingsGeneratorAvailableForOptionsAsync@SemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@8@USemanticImageIndexStoreOptions@345678@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::MakeEmbeddingsGeneratorAvailableForOptionsAsync(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions)
0x180232d56  jmp     loc_180232E17
0x180232d5b  lea     rcx, [rdi+1B8h]
0x180232d62  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x180232d67  nop
0x180232d68  mov     r14, [rdi+1B8h]
0x180232d6f  mov     [rdi+1B8h], rsi
0x180232d76  mov     [rdi+1B0h], r14
0x180232d7d  mov     rcx, r12; hToken
0x180232d80  call    cs:__imp_ImpersonateLoggedOnUser
0x180232d86  mov     rcx, [rsp+1C8h]; this
0x180232d8e  test    eax, eax
0x180232d90  jnz     short loc_180232D9C
0x180232d92  mov     edx, 1Ch; void *
0x180232d97  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180232d9c  mov     [rdi+1F8h], rbx
0x180232da3  test    rbx, rbx
0x180232da6  jz      short loc_180232DB8
0x180232da8  mov     rax, [rbx]
0x180232dab  mov     rcx, rbx
0x180232dae  mov     rax, [rax+8]
0x180232db2  call    cs:__guard_dispatch_icall_fptr
0x180232db8  lea     rbx, [rdi+0D8h]
0x180232dbf  lea     rdx, [rdi+1F8h]
0x180232dc6  mov     rcx, rbx
0x180232dc9  call    ?MakeEmbeddingsGeneratorAvailableForOptionsAsync@SemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@8@USemanticImageIndexStoreOptions@345678@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::MakeEmbeddingsGeneratorAvailableForOptionsAsync(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions)
0x180232dce  nop
0x180232dcf  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180232dd3  jz      short loc_180232DF9
0x180232dd5  mov     rdx, r14; Token
0x180232dd8  xor     ecx, ecx; Thread
0x180232dda  call    cs:__imp_SetThreadToken
0x180232de0  test    eax, eax
0x180232de2  jnz     short loc_180232DEA
0x180232de4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180232dea  test    r14, r14
0x180232ded  jz      short loc_180232DF9
0x180232def  mov     rcx, r14; hObject
0x180232df2  call    cs:__imp_CloseHandle
0x180232df8  nop
0x180232df9  mov     rcx, [rdi+1B8h]; hObject
0x180232e00  test    rcx, rcx
0x180232e03  jz      short loc_180232E17
0x180232e05  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180232e09  jz      short loc_180232E17
0x180232e0b  mov     [rsp+1C8h+var_178], rcx
0x180232e10  call    cs:__imp_CloseHandle
0x180232e16  nop
0x180232e17  mov     eax, [rdi+70h]
0x180232e1a  cmp     eax, 2
0x180232e1d  jnz     short loc_180232E62
0x180232e1f  lea     rdx, [rdi+1E0h]; struct winrt::impl::slim_source_location *
0x180232e26  mov     dword ptr [rdx], 1628h
0x180232e2c  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180232e33  mov     [rdi+1E8h], rax
0x180232e3a  mov     [rdi+1F0h], rsi
0x180232e41  lea     rcx, [rsp+1C8h+var_138]; this
0x180232e49  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180232e4e  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180232e55  lea     rcx, [rsp+1C8h+var_138]; pExceptionObject
0x180232e5d  call    _CxxThrowException
0x180232e62  lea     rcx, [rdi+0E0h]
0x180232e69  mov     [rcx], rsi
0x180232e6c  mov     [rdi+0E8h], rbx
0x180232e73  mov     [rdi+0F0h], rsi
0x180232e7a  mov     byte ptr [rdi+0F8h], 1
0x180232e81  mov     eax, 8
0x180232e86  mov     [rdi+98h], ax
0x180232e8d  mov     rdx, rdi
0x180232e90  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type>)
0x180232e95  test    al, al
0x180232e97  jz      loc_180232F49
0x180232e9d  jmp     loc_180233775
0x180232ea2  mov     rbx, [rdi+0E0h]; jumptable 0000000180232B8D case 9
0x180232ea9  test    rbx, rbx
0x180232eac  jz      short loc_180232ED4
0x180232eae  mov     [rsp+1C8h+var_E8], rbx
0x180232eb6  xor     esi, esi
0x180232eb8  mov     eax, esi
0x180232eba  xchg    rax, [rbx]
0x180232ebd  cmp     rax, 1
0x180232ec1  jnz     short loc_180232ED4
0x180232ec3  call    _Thrd_yield
0x180232ec8  mov     rax, rsi
0x180232ecb  xchg    rax, [rbx]
0x180232ece  cmp     rax, 1
0x180232ed2  jz      short loc_180232EC3
0x180232ed4  lea     rcx, [rdi+0D8h]
0x180232edb  mov     rax, [rcx]
0x180232ede  mov     [rsp+1C8h+var_190], rax
0x180232ee3  test    rax, rax
0x180232ee6  jz      short loc_180232EEE
0x180232ee8  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180232eed  nop
0x180232eee  cmp     qword ptr [rdi+2C0h], 0
0x180232ef6  jz      short loc_180232F05
0x180232ef8  lea     rcx, [rdi+0D0h]
0x180232eff  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180232f04  nop
0x180232f05  mov     rcx, [rdi+0A0h]; hObject
0x180232f0c  test    rcx, rcx
0x180232f0f  jz      short loc_180232F26
0x180232f11  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180232f15  jz      short loc_180232F26
0x180232f17  mov     [rsp+1C8h+arg_18], rcx
0x180232f1f  call    cs:__imp_CloseHandle
0x180232f25  nop
0x180232f26  mov     eax, 0FFFFFFFFh
0x180232f2b  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180232f33  sub     eax, 1
0x180232f36  jz      short loc_180232F42
0x180232f38  test    eax, eax
0x180232f3a  jns     short loc_180232F42
0x180232f3c  call    abort
0x180232f42  jmp     loc_180233740; jumptable 0000000180232B8D cases -1,1
0x180232f47  xor     esi, esi; jumptable 0000000180232B8D case 8
0x180232f49  lea     rdx, [rdi+100h]
0x180232f50  lea     rcx, [rdi+0E0h]
0x180232f57  call    ?await_resume@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_resume(void)
0x180232f5c  nop
0x180232f5d  mov     rbx, [rdi+0E0h]
0x180232f64  test    rbx, rbx
0x180232f67  jz      short loc_180232F91
0x180232f69  mov     [rsp+1C8h+var_E8], rbx
0x180232f71  mov     rax, rsi
0x180232f74  xchg    rax, [rbx]
0x180232f77  cmp     rax, 1
0x180232f7b  jnz     short loc_180232F91
0x180232f7d  nop     dword ptr [rax]
0x180232f80  call    _Thrd_yield
0x180232f85  mov     rax, rsi
0x180232f88  xchg    rax, [rbx]
0x180232f8b  cmp     rax, 1
0x180232f8f  jz      short loc_180232F80
0x180232f91  lea     rcx, [rdi+0D8h]
0x180232f98  mov     rax, [rcx]
0x180232f9b  mov     [rsp+1C8h+var_190], rax
0x180232fa0  test    rax, rax
0x180232fa3  jz      short loc_180232FAB
0x180232fa5  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180232faa  nop
0x180232fab  cmp     qword ptr [rdi+2C0h], 0
0x180232fb3  jz      short loc_180232FC1
0x180232fb5  lea     rcx, [rdi+0D0h]
0x180232fbc  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180232fc1  mov     dword ptr [rdi+108h], 1
0x180232fcb  mov     rax, 3FE0000000000000h
0x180232fd5  mov     [rdi+110h], rax
0x180232fdc  movups  xmm0, xmmword ptr [rdi+108h]
0x180232fe3  movups  [rsp+1C8h+var_108], xmm0
0x180232feb  movups  xmmword ptr [rdi+0C0h], xmm0
0x180232ff2  mov     rbx, [rdi+1D0h]
0x180232ff9  mov     rcx, rbx; SRWLock
0x180232ffc  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180233001  mov     r13, [rdi+0B8h]
0x180233008  mov     rcx, [r13+70h]
0x18023300c  mov     [rdi+238h], rcx
0x180233013  test    rcx, rcx
0x180233016  jz      short loc_180233056
0x180233018  mov     [rsp+1C8h+var_170], rcx
0x18023301d  mov     rax, [rcx]
0x180233020  mov     rax, [rax+8]
0x180233024  call    cs:__guard_dispatch_icall_fptr
0x18023302a  mov     rcx, rbx; SRWLock
0x18023302d  call    ReleaseSRWLockExclusive_0
0x180233032  lea     r8, [rdi+0C0h]
0x180233039  mov     rdx, r13
0x18023303c  lea     rcx, [rdi+238h]
0x180233043  call    ??$invoke@U?$AsyncOperationProgressHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@UPackageDeploymentProgress@Deployment@Management@3Microsoft@4@@impl@winrt@@YA_NAEBU?$AsyncOperationProgressHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@1@AEBUpromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@AEBUPackageDeploymentProgress@Deployment@Management@4Microsoft@1@@Z; winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> const &,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type const &,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress const &)
0x180233048  lea     rcx, [rdi+238h]
0x18023304f  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180233054  jmp     short loc_18023305E
0x180233056  mov     rcx, rbx; SRWLock
0x180233059  call    ReleaseSRWLockExclusive_0
0x18023305e  mov     rbx, [rdi+90h]
0x180233065  mov     [rdi+2B0h], rbx
0x18023306c  mov     [rdi+130h], rbx
0x180233073  test    rbx, rbx
0x180233076  jz      short loc_180233089
0x180233078  mov     rax, [rbx]
0x18023307b  mov     rcx, rbx
0x18023307e  mov     rax, [rax+8]
0x180233082  call    cs:__guard_dispatch_icall_fptr
0x180233088  nop
0x180233089  mov     r12, [rdi+0A0h]
  ... truncated ...
```
