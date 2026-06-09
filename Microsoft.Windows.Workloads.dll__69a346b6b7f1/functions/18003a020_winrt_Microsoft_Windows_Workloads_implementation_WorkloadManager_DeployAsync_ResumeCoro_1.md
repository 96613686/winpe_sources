# winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::DeployAsync$_ResumeCoro$1

- ea: `0x18003a020`
- end: `0x18003aebc`
- name: `winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::DeployAsync$_ResumeCoro$1`
- size: `3740`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180026450`

## callees

- `0x1800040a0`
- `0x180004350`
- `0x180004810`
- `0x180004a00`
- `0x180004a50`
- `0x18000c530`
- `0x18000e550`
- `0x180013b90`
- `0x180013bd0`
- `0x180014e70`
- `0x1800157c0`
- `0x1800182b0`
- `0x1800182e0`
- `0x18001c360`
- `0x18001c8c0`
- `0x18001d8e0`
- `0x18001e0e0`
- `0x180023260`
- `0x180029c70`
- `0x180030ae5`
- `0x180030aeb`
- `0x180030af1`
- `0x180030af7`
- `0x1800342c4`
- `0x180034450`
- `0x180034ef0`
- `0x180035060`
- `0x18003509c`
- `0x180036f4c`
- `0x18003a020`
- `0x18003bed0`
- `0x18003c020`
- `0x18003c6e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18003a890`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18003a890`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18003a3e9`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18003aaf4`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18003ae4a`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18003a3e9`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18003aaf4`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18003ae4a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18003a89c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18003a89c`

## string_xrefs

- `0x18003a9f3`: `Unexpected code path in package deployement`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
void __fastcall winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::DeployAsync__ResumeCoro_1(
        __int64 a1)
{
  struct winrt::impl::hstring_header *v2; // rdx
  signed __int64 v3; // rcx
  __int64 v4; // rdx
  signed __int64 v5; // rax
  signed __int64 v6; // rtt
  __int64 v7; // rax
  __int64 v8; // rcx
  void *v9; // rax
  int v10; // eax
  _QWORD *v11; // rax
  __int64 v12; // rax
  int v13; // eax
  volatile __int64 *v14; // rbx
  int v15; // eax
  HANDLE v16; // rax
  __int64 *v17; // rsi
  int v18; // ebx
  int v19; // eax
  volatile __int64 *v20; // rbx
  int v21; // eax
  int v22; // eax
  HANDLE v23; // rax
  int v24; // eax
  int v25; // ebx
  int v26; // eax
  unsigned int v27; // ebx
  int v28; // eax
  volatile signed __int32 **v29; // rsi
  int v30; // eax
  void *v31; // rbx
  volatile signed __int32 *v32; // rax
  __int64 v33; // r15
  const void *v34; // rsi
  struct winrt::impl::shared_hstring_header *v35; // rax
  size_t v36; // r8
  void *v37; // rcx
  _DWORD *v38; // r8
  int v39; // eax
  winrt::hresult *v40; // rax
  _QWORD *v41; // r15
  __int64 v42; // rax
  int v43; // ecx
  HANDLE v44; // rax
  volatile __int64 *v45; // rbx
  RTL_SRWLOCK *v46; // r15
  int v47; // eax
  RTL_SRWLOCK *v48; // rsi
  RTL_SRWLOCK *v49; // rbx
  RTL_SRWLOCK *v50; // rsi
  PVOID Ptr; // rax
  volatile __int64 *v52; // rbx
  volatile signed __int32 *v53; // rbx
  int v54; // r13d
  HANDLE ProcessHeap; // rax
  __int128 v56; // [rsp+80h] [rbp-248h]
  _BYTE pExceptionObject[24]; // [rsp+98h] [rbp-230h] BYREF
  _BYTE v58[24]; // [rsp+B0h] [rbp-218h] BYREF
  _BYTE v59[24]; // [rsp+C8h] [rbp-200h] BYREF
  _BYTE v60[24]; // [rsp+E0h] [rbp-1E8h] BYREF
  _BYTE v61[24]; // [rsp+F8h] [rbp-1D0h] BYREF
  _BYTE v62[24]; // [rsp+110h] [rbp-1B8h] BYREF
  volatile signed __int32 *v63; // [rsp+128h] [rbp-1A0h]
  _QWORD *v64; // [rsp+130h] [rbp-198h]
  PVOID v65; // [rsp+138h] [rbp-190h]
  __int64 v67; // [rsp+148h] [rbp-180h]
  __int64 v68; // [rsp+150h] [rbp-178h]
  int v69; // [rsp+158h] [rbp-170h]
  __int64 v70; // [rsp+160h] [rbp-168h]
  __int64 v71; // [rsp+168h] [rbp-160h]
  __int64 v72; // [rsp+170h] [rbp-158h]
  int v73; // [rsp+178h] [rbp-150h]
  int v74; // [rsp+17Ch] [rbp-14Ch]
  int v75; // [rsp+180h] [rbp-148h]

  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_156;
    case 2:
      *(_DWORD *)(a1 + 304) = 0;
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_iCxz8Qnks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_iCxz8Qnks>::GetImpl'::`2'::impl) )
      {
        *(_QWORD *)(a1 + 288) = a1 - 128;
        *(_QWORD *)(a1 + 224) = winrt::impl::duplicate_hstring(*(winrt::impl **)(a1 + 416), v2);
        v7 = winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::DeploySinglePackageAsync(
               *(_QWORD *)(a1 + 408),
               a1 + 232,
               a1 + 224);
        if ( *(_DWORD *)(a1 - 128 + 96) == 2 )
        {
          winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v58);
          throw (winrt::hresult_canceled *)v58;
        }
        *(_QWORD *)(a1 + 240) = 0;
        *(_QWORD *)(a1 + 248) = v7;
        *(_QWORD *)(a1 + 256) = 0;
        *(_BYTE *)(a1 + 264) = 1;
        *(_WORD *)(a1 + 8) = 12;
        if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type>(
                                a1 + 240,
                                a1) )
          return;
LABEL_138:
        if ( *(int *)(a1 + 260) < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult(*(unsigned int *)(a1 + 260));
        }
        if ( *(_DWORD *)(a1 + 256) == 2 )
        {
          winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v62);
          throw (winrt::hresult_canceled *)v62;
        }
        v46 = (RTL_SRWLOCK *)(a1 + 272);
        *(_QWORD *)(a1 + 272) = 0;
        *(_DWORD *)(a1 + 304) = 256;
        v47 = (*(__int64 (__fastcall **)(_QWORD, __int64))(***(_QWORD ***)(a1 + 248) + 80LL))(
                **(_QWORD **)(a1 + 248),
                a1 + 272);
        if ( v47 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v47);
        }
        v48 = *(RTL_SRWLOCK **)(a1 + 288);
        v49 = v48 + 9;
        WINRT_IMPL_AcquireSRWLockExclusive(v48 + 9);
        v50 = v48 + 13;
        if ( v50 != v46 )
        {
          if ( v50->Ptr )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v50);
          Ptr = v46->Ptr;
          v46->Ptr = 0;
          v50->Ptr = Ptr;
        }
        ReleaseSRWLockExclusive_0(v49);
        v65 = v46->Ptr;
        if ( v65 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 272);
        if ( *(_QWORD *)(a1 + 240) )
        {
          v52 = *(volatile __int64 **)(a1 + 240);
          while ( _InterlockedExchange64(v52, 0) == 1 )
            Thrd_yield();
        }
        v68 = *(_QWORD *)(a1 + 232);
        if ( v68 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 232);
LABEL_155:
        *(_QWORD *)(a1 + 280) = a1 - 128;
        *(_WORD *)(a1 + 8) = 0;
        if ( (unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::final_suspend_awaiter::await_suspend(a1 + 280) )
          return;
LABEL_156:
        if ( *(_QWORD *)(a1 - 16) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 - 16);
        if ( *(_QWORD *)(a1 - 24) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 - 24);
        if ( *(_QWORD *)(a1 - 40) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 - 40);
        if ( *(_QWORD *)(a1 - 48) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 - 48);
        __ExceptionPtrDestroy((void *)(a1 - 72));
        winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Windows::Foundation::IAsyncInfo>::subtract_final_reference(a1 - 128);
        if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) >= 0 )
        {
          v53 = *(volatile signed __int32 **)(a1 + 416);
          if ( !v53 )
            goto LABEL_170;
          v54 = _InterlockedDecrement(v53 + 6);
          if ( !v54 )
          {
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v53);
LABEL_169:
            *(_QWORD *)(a1 + 416) = 0;
LABEL_170:
            if ( *(_WORD *)(a1 + 10) )
              operator delete((void *)(a1 - 128));
            return;
          }
          if ( v54 >= 0 )
            goto LABEL_169;
        }
        abort();
      }
      v4 = *(_QWORD *)(a1 + 408);
      *(_QWORD *)(a1 + 16) = 0;
      if ( v4 )
      {
        *(_QWORD *)(a1 + 16) = v4;
        v5 = *(_QWORD *)(v4 + 8);
        if ( v5 < 0 )
        {
LABEL_7:
          _InterlockedIncrement((volatile signed __int32 *)(2 * v5 + 24));
        }
        else
        {
          while ( 1 )
          {
            v3 = v5 + 1;
            v6 = v5;
            v5 = _InterlockedCompareExchange64((volatile signed __int64 *)(v4 + 8), v5 + 1, v5);
            if ( v6 == v5 )
              break;
            if ( v5 < 0 )
              goto LABEL_7;
          }
        }
      }
      *(_BYTE *)(a1 + 24) = 0;
      if ( *(_DWORD *)(a1 - 32) == 2 )
      {
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject);
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *(_WORD *)(a1 + 8) = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v3, a1);
      return;
    case 4:
      *(_QWORD *)(a1 + 32) = a1 - 128;
      *(_QWORD *)(a1 + 40) = a1 - 128;
      *(_QWORD *)(a1 + 48) = a1 - 128;
      *(_BYTE *)(a1 - 128 + 48) = 1;
      winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::FindApiInfo(
        *(_QWORD *)(a1 + 408),
        a1 + 56,
        a1 + 416);
      *(_QWORD *)(a1 + 360) = 0;
      if ( *(_QWORD *)(a1 + 56) )
      {
        *(_QWORD *)(a1 + 376) = 0;
        (***(void (__fastcall ****)(_QWORD, __int64 *, __int64))(a1 + 56))(
          *(_QWORD *)(a1 + 56),
          &winrt::impl::guid_v<winrt::Microsoft::Windows::Workloads::IApiInfo3>,
          a1 + 376);
        v9 = *(void **)(a1 + 376);
        v65 = v9;
      }
      else
      {
        v9 = 0;
      }
      *(_QWORD *)(a1 + 368) = v9;
      v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v9 + 48LL))(*(_QWORD *)(a1 + 368), a1 + 360);
      if ( v10 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v10);
      }
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 368);
      v11 = *(_QWORD **)(a1 + 360);
      *(_QWORD *)(a1 + 64) = v11;
      *(_DWORD *)(a1 + 304) = 512;
      *(_DWORD *)(a1 + 72) = 0;
      *(_DWORD *)(a1 + 384) = 0;
      v64 = v11;
      v12 = *v11;
      v64 = *(_QWORD **)(a1 + 360);
      v13 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(v12 + 56))(v64, a1 + 384);
      if ( v13 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v13);
      }
      v73 = *(_DWORD *)(a1 + 384);
      *(_DWORD *)(a1 + 76) = v73;
      winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>::begin(
        a1 + 64,
        a1 + 80);
      *(_QWORD *)(a1 + 88) = 0;
      goto LABEL_78;
    case 5:
      v8 = a1 + 16;
      v67 = *(_QWORD *)(a1 + 16);
      if ( v67 )
        winrt::com_ptr<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager>::unconditional_release_ref(v8);
      goto LABEL_156;
    case 0xA:
      while ( 2 )
      {
        if ( *(int *)(a1 + 164) < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult(*(unsigned int *)(a1 + 164));
        }
        if ( *(_DWORD *)(a1 + 160) == 2 )
        {
          winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v59);
          throw (winrt::hresult_canceled *)v59;
        }
        v17 = (__int64 *)(a1 + 176);
        *(_QWORD *)(a1 + 176) = 0;
        v18 = *(_DWORD *)(a1 + 304) | 0x40;
        *(_DWORD *)(a1 + 304) = v18;
        v19 = (*(__int64 (__fastcall **)(_QWORD, __int64))(***(_QWORD ***)(a1 + 152) + 80LL))(
                **(_QWORD **)(a1 + 152),
                a1 + 176);
        if ( v19 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v19);
        }
        *(_DWORD *)(a1 + 304) = v18 & 0xFFFFFF9F | 0x20;
        if ( *(_QWORD *)(a1 + 144) )
        {
          v20 = *(volatile __int64 **)(a1 + 144);
          while ( _InterlockedExchange64(v20, 0) == 1 )
            Thrd_yield();
        }
        v74 = *(_DWORD *)(a1 + 76);
        v69 = *(_DWORD *)(a1 + 72);
        if ( v69 == v74 - 1 )
          goto LABEL_106;
        *(_DWORD *)(a1 + 348) = 0;
        v72 = *v17;
        v21 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v72 + 48LL))(v72, a1 + 348);
        if ( v21 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v21);
        }
        v75 = *(_DWORD *)(a1 + 348);
        if ( v75 != 1 )
        {
LABEL_106:
          WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)(a1 - 56));
          v41 = (_QWORD *)(a1 - 24);
          if ( (__int64 *)(a1 - 24) != v17 )
          {
            if ( *v41 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 - 24);
            v42 = *v17;
            *v17 = 0;
            *v41 = v42;
          }
          ReleaseSRWLockExclusive_0((PSRWLOCK)(a1 - 56));
          v72 = *v17;
          if ( v72 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 176);
          v70 = *(_QWORD *)(a1 + 128);
          if ( v70 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 128);
          if ( *(_QWORD *)(a1 + 312) )
          {
            v43 = _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 312) + 24LL));
            if ( v43 )
            {
              if ( v43 < 0 )
LABEL_118:
                abort();
            }
            else
            {
              v63 = *(volatile signed __int32 **)(a1 + 312);
              v44 = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(v44, 0, (LPVOID)v63);
            }
          }
          v71 = *(_QWORD *)(a1 + 96);
          if ( v71 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 96);
          if ( *(_QWORD *)(a1 + 88) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 88);
          if ( *(_QWORD *)(a1 + 80) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 80);
          v68 = *(_QWORD *)(a1 + 64);
          if ( v68 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 64);
          if ( *(_QWORD *)(a1 + 56) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 56);
          v67 = *(_QWORD *)(a1 + 16);
          if ( v67 )
            winrt::com_ptr<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager>::unconditional_release_ref(a1 + 16);
          goto LABEL_155;
        }
        v69 = *(_DWORD *)(a1 + 72);
        *(_DWORD *)(a1 + 72) = v69 + 1;
        v72 = *v17;
        if ( v72 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 176);
        v70 = *(_QWORD *)(a1 + 128);
        if ( v70 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 128);
        v63 = *(volatile signed __int32 **)(a1 + 312);
        if ( v63 )
        {
          v63 = *(volatile signed __int32 **)(a1 + 312);
          v22 = _InterlockedDecrement(v63 + 6);
          if ( v22 )
          {
            if ( v22 < 0 )
              goto LABEL_118;
          }
          else
          {
            v63 = *(volatile signed __int32 **)(a1 + 312);
            v23 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v23, 0, (LPVOID)v63);
          }
        }
        v71 = *(_QWORD *)(a1 + 96);
        if ( v71 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 96);
        *(_BYTE *)(a1 + 356) = 0;
        v24 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 80) + 64LL))(
                *(_QWORD *)(a1 + 80),
                a1 + 356);
        if ( v24 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v24);
        }
        if ( !*(_BYTE *)(a1 + 356) )
        {
          if ( *(_QWORD *)(a1 + 80) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 80);
          *(_QWORD *)(a1 + 80) = 0;
        }
LABEL_78:
        if ( (unsigned __int8)winrt::Windows::Foundation::operator==(a1 + 80, a1 + 88) )
        {
          winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>((_QWORD *)(a1 + 88));
          winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::~IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>((_QWORD *)(a1 + 80));
          winrt::param::hstring::hstring(
            (winrt::param::hstring *)(a1 + 184),
            L"Unexpected code path in package deployement");
          v40 = winrt::hresult::hresult((winrt::hresult *)(a1 + 216), -2147418113);
          winrt::hresult_error::hresult_error(v61, *(unsigned int *)v40, a1 + 184);
          throw (winrt::hresult_error *)v61;
        }
        *(_QWORD *)(a1 + 96) = 0;
        v25 = *(_DWORD *)(a1 + 304) | 0x10;
        *(_DWORD *)(a1 + 304) = v25;
        v26 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 80) + 48LL))(
                *(_QWORD *)(a1 + 80),
                a1 + 96);
        if ( v26 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v26);
        }
        *(_QWORD *)(a1 + 104) = 0;
        v27 = v25 & 0xFFFFFFE6 | 9;
        *(_DWORD *)(a1 + 304) = v27;
        v71 = *(_QWORD *)(a1 + 96);
        v28 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v71 + 56LL))(v71, a1 + 104);
        if ( v28 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v28);
        }
        v29 = (volatile signed __int32 **)(a1 + 312);
        *(_QWORD *)(a1 + 312) = 0;
        v30 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 104) + 48LL))(
                *(_QWORD *)(a1 + 104),
                a1 + 312);
        if ( v30 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v30);
        }
        *(_QWORD *)(a1 + 112) = *v29;
        *(_DWORD *)(a1 + 304) = v27 & 0xFFFFFFFC | 2;
        if ( *(_QWORD *)(a1 + 104) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 104);
        v63 = *v29;
        if ( !v63 )
        {
          v31 = 0;
          goto LABEL_99;
        }
        v63 = *v29;
        v32 = *v29;
        if ( (*v63 & 1) == 0 )
        {
          _InterlockedIncrement(v32 + 6);
          v31 = (void *)*v29;
          v63 = *v29;
          goto LABEL_99;
        }
        v33 = *((unsigned int *)v32 + 1);
        v63 = *v29;
        v34 = (const void *)*((_QWORD *)v32 + 2);
        if ( !(_DWORD)v33 )
        {
          v31 = 0;
          goto LABEL_99;
        }
        v35 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v33);
        v31 = v35;
        v36 = 2 * v33;
        v37 = (char *)v35 + 28;
        if ( !(2 * v33) )
          goto LABEL_99;
        if ( v35 == (struct winrt::impl::shared_hstring_header *)-28LL )
          goto LABEL_98;
        if ( v34 )
        {
          memmove(v37, v34, v36);
        }
        else
        {
          memset(v37, 0, v36);
LABEL_98:
          *_errno() = 22;
          _invalid_parameter_noinfo();
        }
LABEL_99:
        *(_QWORD *)(a1 + 120) = v31;
        winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::DeploySinglePackageAsync(
          *(_QWORD *)(a1 + 408),
          a1 + 128,
          a1 + 120);
        *(_QWORD *)&v56 = a1 + 72;
        *((_QWORD *)&v56 + 1) = a1 + 76;
        v38 = operator new(0x28u);
        v38[2] = 1;
        *((_OWORD *)v38 + 1) = v56;
        *((_QWORD *)v38 + 4) = a1 + 40;
        _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
        *(_QWORD *)v38 = off_18004A9F8;
        *(_QWORD *)(a1 + 136) = v38;
        *(_DWORD *)(a1 + 304) |= 4u;
        v70 = *(_QWORD *)(a1 + 128);
        v39 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v70 + 48LL))(v70, v38);
        if ( v39 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v39);
        }
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 136);
        if ( *(_DWORD *)(a1 - 32) == 2 )
        {
          winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v60);
          throw (winrt::hresult_canceled *)v60;
        }
        *(_QWORD *)(a1 + 144) = 0;
        *(_QWORD *)(a1 + 152) = a1 + 128;
        *(_QWORD *)(a1 + 160) = 0;
        *(_BYTE *)(a1 + 168) = 1;
        *(_WORD *)(a1 + 8) = 10;
        if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type>(
                                a1 + 144,
                                a1) )
          return;
        continue;
      }
    case 0xB:
      if ( *(_QWORD *)(a1 + 144) )
      {
        v14 = *(volatile __int64 **)(a1 + 144);
        while ( _InterlockedExchange64(v14, 0) == 1 )
          Thrd_yield();
      }
      v70 = *(_QWORD *)(a1 + 128);
      if ( v70 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 128);
      if ( *(_QWORD *)(a1 + 312) )
      {
        v15 = _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 312) + 24LL));
        if ( v15 )
        {
          if ( v15 < 0 )
            abort();
        }
        else
        {
          v63 = *(volatile signed __int32 **)(a1 + 312);
          v16 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v16, 0, (LPVOID)v63);
        }
      }
      v71 = *(_QWORD *)(a1 + 96);
      if ( v71 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 96);
      if ( *(_QWORD *)(a1 + 88) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 88);
      if ( *(_QWORD *)(a1 + 80) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 80);
      v68 = *(_QWORD *)(a1 + 64);
      if ( v68 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 64);
      if ( *(_QWORD *)(a1 + 56) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 56);
      v67 = *(_QWORD *)(a1 + 16);
      if ( v67 )
        winrt::com_ptr<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager>::unconditional_release_ref(a1 + 16);
      goto LABEL_156;
    case 0xC:
      goto LABEL_138;
    case 0xD:
      if ( *(_QWORD *)(a1 + 240) )
      {
        v45 = *(volatile __int64 **)(a1 + 240);
        while ( _InterlockedExchange64(v45, 0) == 1 )
          Thrd_yield();
      }
      v68 = *(_QWORD *)(a1 + 232);
      if ( v68 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 232);
      goto LABEL_156;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x18003a020  mov     r11, rsp
0x18003a023  mov     [r11+10h], rbx
0x18003a027  mov     [r11+18h], rsi
0x18003a02b  mov     [r11+8], rcx
0x18003a02f  push    rdi
0x18003a030  push    r12
0x18003a032  push    r13
0x18003a034  push    r14
0x18003a036  push    r15
0x18003a038  sub     rsp, 2A0h
0x18003a03f  mov     rax, cs:__security_cookie
0x18003a046  xor     rax, rsp
0x18003a049  mov     [rsp+2C8h+var_30], rax
0x18003a051  mov     rdi, rcx
0x18003a054  mov     [rsp+2C8h+var_268], rcx
0x18003a059  movzx   eax, word ptr [rdi+8]
0x18003a05d  mov     [rsp+2C8h+var_290], ax
0x18003a062  inc     ax; switch 15 cases
0x18003a065  cmp     ax, 0Eh
0x18003a069  ja      def_18003A084; jumptable 000000018003A084 default case, cases 0,6-9
0x18003a06f  movsx   rax, ax
0x18003a073  lea     rdx, cs:180000000h
0x18003a07a  mov     ecx, ds:(jpt_18003A084 - 180000000h)[rdx+rax*4]
0x18003a081  add     rcx, rdx
0x18003a084  jmp     rcx; switch jump
0x18003a086  xor     r14d, r14d; jumptable 000000018003A084 case 3
0x18003a089  mov     r13d, 0FFFFFFFFh
0x18003a08f  jmp     loc_18003AD99
0x18003a094  xor     r14d, r14d; jumptable 000000018003A084 case 2
0x18003a097  mov     [rdi+130h], r14d
0x18003a09e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_iCxz8Qnks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_iCxz8Qnks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_iCxz8Qnks> `wil::Feature<__WilFeatureTraits_Feature_iCxz8Qnks>::GetImpl(void)'::`2'::impl
0x18003a0a5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_iCxz8Qnks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_iCxz8Qnks>::__private_IsEnabled(void)
0x18003a0aa  test    al, al
0x18003a0ac  jz      short loc_18003A129
0x18003a0ae  mov     rdx, [rdi+198h]
0x18003a0b5  mov     [rdi+10h], r14
0x18003a0b9  test    rdx, rdx
0x18003a0bc  jz      short loc_18003A0E6
0x18003a0be  mov     [rdi+10h], rdx
0x18003a0c2  mov     rax, [rdx+8]
0x18003a0c6  test    rax, rax
0x18003a0c9  js      short loc_18003A0E1
0x18003a0cb  nop     dword ptr [rax+rax+00h]
0x18003a0d0  lea     rcx, [rax+1]
0x18003a0d4  lock cmpxchg [rdx+8], rcx
0x18003a0da  jz      short loc_18003A0E6
0x18003a0dc  test    rax, rax
0x18003a0df  jns     short loc_18003A0D0
0x18003a0e1  lock inc dword ptr [rax+rax+18h]
0x18003a0e6  mov     byte ptr [rdi+18h], 0
0x18003a0ea  mov     eax, [rdi-20h]
0x18003a0ed  cmp     eax, 2
0x18003a0f0  jnz     short loc_18003A113
0x18003a0f2  lea     rcx, [rsp+2C8h+pExceptionObject]; this
0x18003a0fa  call    ??0hresult_canceled@winrt@@QEAA@XZ; winrt::hresult_canceled::hresult_canceled(void)
0x18003a0ff  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18003a106  lea     rcx, [rsp+2C8h+pExceptionObject]; pExceptionObject
0x18003a10e  call    _CxxThrowException
0x18003a113  mov     eax, 4
0x18003a118  mov     [rdi+8], ax
0x18003a11c  mov     rdx, rdi
0x18003a11f  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@experimental@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::experimental::coroutine_handle<void>)
0x18003a124  jmp     loc_18003AE52
0x18003a129  lea     rsi, [rdi-80h]
0x18003a12d  mov     [rdi+120h], rsi
0x18003a134  mov     rcx, [rdi+1A0h]; this
0x18003a13b  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18003a140  mov     [rdi+0E0h], rax
0x18003a147  lea     rdx, [rdi+0E8h]
0x18003a14e  lea     r8, [rdi+0E0h]
0x18003a155  mov     rcx, [rdi+198h]
0x18003a15c  call    ?DeploySinglePackageAsync@WorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@AEAA?AU?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@46@Uhstring@6@@Z; winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::DeploySinglePackageAsync(winrt::hstring)
0x18003a161  nop
0x18003a162  mov     ecx, [rsi+60h]
0x18003a165  cmp     ecx, 2
0x18003a168  jnz     short loc_18003A18B
0x18003a16a  lea     rcx, [rsp+2C8h+var_218]; this
0x18003a172  call    ??0hresult_canceled@winrt@@QEAA@XZ; winrt::hresult_canceled::hresult_canceled(void)
0x18003a177  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18003a17e  lea     rcx, [rsp+2C8h+var_218]; pExceptionObject
0x18003a186  call    _CxxThrowException
0x18003a18b  lea     rcx, [rdi+0F0h]
0x18003a192  mov     [rcx], r14
0x18003a195  mov     [rdi+0F8h], rax
0x18003a19c  mov     [rdi+100h], r14
0x18003a1a3  mov     byte ptr [rdi+108h], 1
0x18003a1aa  mov     eax, 0Ch
0x18003a1af  mov     [rdi+8], ax
0x18003a1b3  mov     rdx, rdi
0x18003a1b6  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@PEAUWorkload@implementation@Workloads@3Microsoft@4@@experimental@std@@@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@PEAUWorkload@implementation@Workloads@3Microsoft@4@@experimental@std@@@experimental@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type>(std::experimental::coroutine_handle<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type>)
0x18003a1bb  test    al, al
0x18003a1bd  jz      loc_18003ABFC
0x18003a1c3  jmp     loc_18003AE52
0x18003a1c8  lea     rcx, [rdi+10h]; jumptable 000000018003A084 case 5
0x18003a1cc  mov     rax, [rcx]
0x18003a1cf  mov     [rsp+2C8h+var_180], rax
0x18003a1d7  test    rax, rax
0x18003a1da  jz      short loc_18003A1E2
0x18003a1dc  call    ?unconditional_release_ref@?$com_ptr@UWorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager>::unconditional_release_ref(void)
0x18003a1e1  nop
0x18003a1e2  xor     r14d, r14d
0x18003a1e5  mov     r13d, 0FFFFFFFFh
0x18003a1eb  jmp     loc_18003AD99
0x18003a1f0  lea     rax, [rdi-80h]; jumptable 000000018003A084 case 4
0x18003a1f4  mov     [rdi+20h], rax
0x18003a1f8  mov     [rdi+28h], rax
0x18003a1fc  mov     [rdi+30h], rax
0x18003a200  mov     byte ptr [rax+30h], 1
0x18003a204  lea     r8, [rdi+1A0h]
0x18003a20b  lea     rdx, [rdi+38h]
0x18003a20f  mov     rcx, [rdi+198h]
0x18003a216  call    ?FindApiInfo@WorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@QEAA?AUApiInfo@3456@AEBUhstring@6@@Z; winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::FindApiInfo(winrt::hstring const &)
0x18003a21b  nop
0x18003a21c  xor     r14d, r14d
0x18003a21f  mov     [rdi+168h], r14
0x18003a226  mov     rax, [rdi+38h]
0x18003a22a  mov     [rsp+2C8h+var_298], rax
0x18003a22f  test    rax, rax
0x18003a232  jnz     short loc_18003A239
0x18003a234  mov     eax, r14d
0x18003a237  jmp     short loc_18003A27B
0x18003a239  mov     [rdi+178h], r14
0x18003a240  mov     rax, [rdi+38h]
0x18003a244  mov     [rsp+2C8h+var_298], rax
0x18003a249  mov     rcx, [rax]
0x18003a24c  mov     rax, [rcx]
0x18003a24f  mov     rcx, [rdi+38h]
0x18003a253  mov     [rsp+2C8h+var_298], rcx
0x18003a258  lea     r8, [rdi+178h]
0x18003a25f  lea     rdx, ??$guid_v@UIApiInfo3@Workloads@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::Workloads::IApiInfo3>
0x18003a266  call    cs:__guard_dispatch_icall_fptr
0x18003a26c  mov     rax, [rdi+178h]
0x18003a273  mov     [rsp+2C8h+var_190], rax
0x18003a27b  mov     [rdi+170h], rax
0x18003a282  mov     [rsp+2C8h+var_260], rax
0x18003a287  mov     rcx, [rax]
0x18003a28a  mov     rax, [rcx+30h]
0x18003a28e  mov     rcx, [rdi+170h]
0x18003a295  mov     [rsp+2C8h+var_260], rcx
0x18003a29a  lea     rdx, [rdi+168h]
0x18003a2a1  call    cs:__guard_dispatch_icall_fptr
0x18003a2a7  test    eax, eax
0x18003a2a9  jns     short loc_18003A2B6
0x18003a2ab  lfence
0x18003a2ae  mov     ecx, eax
0x18003a2b0  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x18003a2b6  lea     rcx, [rdi+170h]
0x18003a2bd  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003a2c2  mov     rax, [rdi+168h]
0x18003a2c9  mov     [rdi+40h], rax
0x18003a2cd  mov     dword ptr [rdi+130h], 200h
0x18003a2d7  mov     [rdi+48h], r14d
0x18003a2db  mov     [rdi+180h], r14d
0x18003a2e2  mov     [rsp+2C8h+var_198], rax
0x18003a2ea  mov     rax, [rax]
0x18003a2ed  mov     rcx, [rdi+168h]
0x18003a2f4  mov     [rsp+2C8h+var_198], rcx
0x18003a2fc  lea     rdx, [rdi+180h]
0x18003a303  mov     rax, [rax+38h]
0x18003a307  call    cs:__guard_dispatch_icall_fptr
0x18003a30d  test    eax, eax
0x18003a30f  jns     short loc_18003A31B
0x18003a311  lfence
0x18003a314  mov     ecx, eax
0x18003a316  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x18003a31b  mov     eax, [rdi+180h]
0x18003a321  mov     [rsp+2C8h+var_150], eax
0x18003a328  mov     [rdi+4Ch], eax
0x18003a32b  lea     rdx, [rdi+50h]
0x18003a32f  lea     rcx, [rdi+40h]
0x18003a333  call    ?begin@?$consume_Windows_Foundation_Collections_IIterable@U?$IMapView@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>::begin(void)
0x18003a338  nop
0x18003a339  mov     [rdi+58h], r14
0x18003a33d  mov     r13d, 0FFFFFFFFh
0x18003a343  jmp     loc_18003A710
0x18003a348  xor     r14d, r14d; jumptable 000000018003A084 case 11
0x18003a34b  cmp     [rdi+90h], r14
0x18003a352  jz      short loc_18003A381
0x18003a354  mov     rbx, [rdi+90h]
0x18003a35b  mov     rcx, rbx
0x18003a35e  mov     [rsp+2C8h+var_288], rbx
0x18003a363  mov     eax, r14d
0x18003a366  xchg    rax, [rcx]
0x18003a369  cmp     rax, 1
0x18003a36d  jnz     short loc_18003A381
0x18003a36f  nop
0x18003a370  call    _Thrd_yield
0x18003a375  mov     rax, r14
0x18003a378  xchg    rax, [rbx]
0x18003a37b  cmp     rax, 1
0x18003a37f  jz      short loc_18003A370
0x18003a381  lea     rcx, [rdi+80h]
0x18003a388  mov     rax, [rcx]
0x18003a38b  mov     [rsp+2C8h+var_168], rax
0x18003a393  test    rax, rax
0x18003a396  jz      short loc_18003A39E
0x18003a398  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003a39d  nop
0x18003a39e  mov     r13d, 0FFFFFFFFh
0x18003a3a4  cmp     qword ptr [rdi+138h], 0
0x18003a3ac  jz      short loc_18003A3F0
0x18003a3ae  mov     rcx, [rdi+138h]
0x18003a3b5  mov     eax, r13d
0x18003a3b8  lock xadd [rcx+18h], eax
0x18003a3bd  sub     eax, 1
0x18003a3c0  jnz     short loc_18003A3E5
0x18003a3c2  mov     rbx, [rdi+138h]
0x18003a3c9  mov     [rsp+2C8h+var_1A0], rbx
0x18003a3d1  call    WINRT_IMPL_GetProcessHeap
0x18003a3d6  mov     rcx, rax; hHeap
0x18003a3d9  mov     r8, rbx; lpMem
0x18003a3dc  xor     edx, edx; dwFlags
0x18003a3de  call    WINRT_IMPL_HeapFree
0x18003a3e3  jmp     short loc_18003A3F0
0x18003a3e5  test    eax, eax
0x18003a3e7  jns     short loc_18003A3F0
0x18003a3e9  call    cs:__imp_abort
0x18003a3f0  lea     rcx, [rdi+60h]
0x18003a3f4  mov     rax, [rcx]
0x18003a3f7  mov     [rsp+2C8h+var_160], rax
0x18003a3ff  test    rax, rax
0x18003a402  jz      short loc_18003A40A
0x18003a404  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003a409  nop
0x18003a40a  lea     rcx, [rdi+58h]
0x18003a40e  mov     rax, [rcx]
0x18003a411  mov     [rsp+2C8h+var_250], rax
0x18003a416  test    rax, rax
0x18003a419  jz      short loc_18003A421
0x18003a41b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003a420  nop
0x18003a421  lea     rcx, [rdi+50h]
0x18003a425  mov     rax, [rcx]
0x18003a428  mov     [rsp+2C8h+var_2A0], rax
0x18003a42d  test    rax, rax
0x18003a430  jz      short loc_18003A438
0x18003a432  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003a437  nop
0x18003a438  lea     rcx, [rdi+40h]
0x18003a43c  mov     rax, [rcx]
0x18003a43f  mov     [rsp+2C8h+var_178], rax
0x18003a447  test    rax, rax
0x18003a44a  jz      short loc_18003A452
0x18003a44c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003a451  nop
0x18003a452  lea     rcx, [rdi+38h]
0x18003a456  mov     rax, [rcx]
0x18003a459  mov     [rsp+2C8h+var_298], rax
0x18003a45e  test    rax, rax
0x18003a461  jz      short loc_18003A469
0x18003a463  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003a468  nop
0x18003a469  lea     rcx, [rdi+10h]
0x18003a46d  mov     rax, [rcx]
0x18003a470  mov     [rsp+2C8h+var_180], rax
0x18003a478  test    rax, rax
0x18003a47b  jz      short loc_18003A483
0x18003a47d  call    ?unconditional_release_ref@?$com_ptr@UWorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager>::unconditional_release_ref(void)
0x18003a482  nop
0x18003a483  jmp     loc_18003AD99
0x18003a488  xor     r14d, r14d; jumptable 000000018003A084 case 10
0x18003a48b  mov     r13d, 0FFFFFFFFh
0x18003a491  mov     eax, [rdi+0A4h]
0x18003a497  mov     [rsp+2C8h+var_274], eax
0x18003a49b  test    eax, eax
0x18003a49d  jns     short loc_18003A4B1
0x18003a49f  lfence
0x18003a4a2  mov     ecx, [rdi+0A4h]
0x18003a4a8  mov     [rsp+2C8h+var_274], ecx
0x18003a4ac  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x18003a4b1  mov     eax, [rdi+0A0h]
0x18003a4b7  mov     [rsp+2C8h+var_278], eax
0x18003a4bb  cmp     eax, 2
0x18003a4be  jnz     short loc_18003A4E2
0x18003a4c0  lea     rcx, [rsp+2C8h+var_200]; this
0x18003a4c8  call    ??0hresult_canceled@winrt@@QEAA@XZ; winrt::hresult_canceled::hresult_canceled(void)
0x18003a4cd  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18003a4d4  lea     rcx, [rsp+2C8h+var_200]; pExceptionObject
0x18003a4dc  call    _CxxThrowException
0x18003a4e2  lea     rsi, [rdi+0B0h]
0x18003a4e9  mov     [rsi], r14
0x18003a4ec  mov     ebx, [rdi+130h]
0x18003a4f2  mov     [rsp+2C8h+var_2A8], ebx
0x18003a4f6  or      ebx, 40h
0x18003a4f9  mov     [rdi+130h], ebx
0x18003a4ff  mov     rax, [rdi+98h]
0x18003a506  mov     [rsp+2C8h+var_280], rax
0x18003a50b  mov     rcx, [rax]
0x18003a50e  mov     rax, [rdi+98h]
0x18003a515  mov     [rsp+2C8h+var_280], rax
0x18003a51a  mov     rax, [rax]
0x18003a51d  mov     rdx, [rax]
0x18003a520  mov     rax, [rdx+50h]
0x18003a524  mov     rdx, rsi
0x18003a527  call    cs:__guard_dispatch_icall_fptr
0x18003a52d  test    eax, eax
0x18003a52f  jns     short loc_18003A53B
0x18003a531  lfence
0x18003a534  mov     ecx, eax
0x18003a536  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
  ... truncated ...
```
