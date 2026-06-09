# winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::DeploySinglePackageAsync$_ResumeCoro$1

- ea: `0x18003aec0`
- end: `0x18003b978`
- name: `winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::DeploySinglePackageAsync$_ResumeCoro$1`
- size: `2744`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180023260`

## callees

- `0x180001b90`
- `0x1800027d0`
- `0x1800040a0`
- `0x180004810`
- `0x180004a00`
- `0x18000c530`
- `0x18000d970`
- `0x18000e550`
- `0x180010320`
- `0x1800119b0`
- `0x180013b90`
- `0x180013bd0`
- `0x180014e70`
- `0x1800182e0`
- `0x180019860`
- `0x18001c360`
- `0x180030ae5`
- `0x180030aeb`
- `0x180030af1`
- `0x180030af7`
- `0x1800342c4`
- `0x180034ef0`
- `0x18003509c`
- `0x180036f4c`
- `0x180039893`
- `0x18003aec0`
- `0x18003bed0`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18003b03b`
- `KERNEL32!CreateEventW` at `0x18003b12d`
- `KERNEL32!CreateEventW` at `0x18003b03b`
- `KERNEL32!CreateEventW` at `0x18003b12d`
- `KERNEL32!CloseHandle` at `0x18003b6de`
- `KERNEL32!CloseHandle` at `0x18003b713`
- `KERNEL32!CloseHandle` at `0x18003b728`
- `KERNEL32!CloseHandle` at `0x18003b6de`
- `KERNEL32!CloseHandle` at `0x18003b713`
- `KERNEL32!CloseHandle` at `0x18003b728`
- `KERNEL32!CreateFileMappingW` at `0x18003b085`
- `KERNEL32!CreateFileMappingW` at `0x18003b085`
- `KERNEL32!MapViewOfFile` at `0x18003b0c9`
- `KERNEL32!MapViewOfFile` at `0x18003b0c9`
- `KERNEL32!CreateThreadpoolWork` at `0x18003b2f0`
- `KERNEL32!CreateThreadpoolWork` at `0x18003b2f0`
- `KERNEL32!SubmitThreadpoolWork` at `0x18003b36f`
- `KERNEL32!SubmitThreadpoolWork` at `0x18003b36f`
- `KERNEL32!WaitForMultipleObjects` at `0x18003b3de`
- `KERNEL32!WaitForMultipleObjects` at `0x18003b3de`
- `KERNEL32!ResetEvent` at `0x18003b4f7`
- `KERNEL32!ResetEvent` at `0x18003b4f7`
- `KERNEL32!UnmapViewOfFile` at `0x18003b6fe`
- `KERNEL32!UnmapViewOfFile` at `0x18003b6fe`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x18003b669`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x18003b669`
- `KERNEL32!CloseThreadpoolWork` at `0x18003b672`
- `KERNEL32!CloseThreadpoolWork` at `0x18003b672`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18003b91b`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18003b91b`

## string_xrefs

- `0x18003b74f`: `WorkloadManager failed to create progress handle.`
- `0x18003b7e7`: `WorkloadManager failed to create progress handle.`
- `0x18003b79e`: `WorkloadManager failed to create shared result section.`
- `0x18003b312`: `WorkloadManager failed to create threadpool work item.`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::DeploySinglePackageAsync__ResumeCoro_1(
        __int64 a1)
{
  __int64 v2; // rdx
  signed __int64 v3; // rax
  signed __int64 v4; // rtt
  __int64 v5; // rbx
  const wchar_t *v6; // rbx
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rcx
  RTL_SRWLOCK *v12; // rdi
  HANDLE EventW; // rax
  HANDLE FileMappingW; // rax
  LPVOID v15; // rax
  winrt::hresult *v16; // rax
  HANDLE v17; // rax
  __int64 v18; // r13
  DWORD v19; // r8d
  _QWORD *v20; // rbx
  HRESULT Instance_0; // eax
  __int64 (__fastcall ****v22)(_QWORD, __int64 *, __int64); // r14
  void *v23; // r9
  _QWORD *v24; // rdx
  __int64 v25; // rax
  wchar_t *v26; // rdx
  __int64 v27; // rdx
  struct _TP_WORK *ThreadpoolWork; // rax
  winrt::hresult *v29; // rax
  char v30; // r13
  DWORD v31; // eax
  winrt::hresult *v32; // rax
  PVOID Ptr; // rax
  int v34; // eax
  __int64 (__fastcall ***v35)(_QWORD, __int64 *, __int64); // rcx
  __int64 v36; // rax
  int v37; // eax
  __int64 v38; // rbx
  const wchar_t *v39; // rbx
  const struct _tlgProvider_t *v40; // rax
  __int64 v41; // r8
  __int64 v42; // r9
  _QWORD *v43; // r14
  __int64 *v44; // rdi
  __int64 v45; // rax
  struct _TP_WORK *v46; // rbx
  __int64 v47; // rdx
  char *v48; // rcx
  char *v49; // rcx
  char *v50; // rcx
  winrt::hresult *v51; // rax
  winrt::hresult *v52; // rax
  winrt::hresult *v53; // rax
  volatile signed __int32 *v55; // rdi
  int v56; // r12d
  HANDLE ProcessHeap; // rax
  bool v58; // [rsp+30h] [rbp-218h]
  _BYTE pExceptionObject[24]; // [rsp+58h] [rbp-1F0h] BYREF
  _BYTE v60[24]; // [rsp+70h] [rbp-1D8h] BYREF
  _BYTE v61[24]; // [rsp+88h] [rbp-1C0h] BYREF
  _BYTE v62[24]; // [rsp+A0h] [rbp-1A8h] BYREF
  _BYTE v63[24]; // [rsp+B8h] [rbp-190h] BYREF
  _BYTE v64[24]; // [rsp+D0h] [rbp-178h] BYREF
  _BYTE v65[24]; // [rsp+E8h] [rbp-160h] BYREF
  __int64 v66; // [rsp+100h] [rbp-148h]
  __int64 v67; // [rsp+108h] [rbp-140h]
  int v68; // [rsp+178h] [rbp-D0h]
  HANDLE v69; // [rsp+180h] [rbp-C8h]
  const void *v70; // [rsp+188h] [rbp-C0h]
  HANDLE v71; // [rsp+190h] [rbp-B8h]
  HANDLE v72; // [rsp+198h] [rbp-B0h]
  __int64 (__fastcall ***v73)(_QWORD, __int64 *, __int64); // [rsp+1A0h] [rbp-A8h]
  PTP_WORK v74; // [rsp+1A8h] [rbp-A0h]
  __int64 (__fastcall ***v75)(_QWORD, __int64 *, __int64); // [rsp+1B0h] [rbp-98h]
  LPCVOID v76; // [rsp+1B8h] [rbp-90h]

  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_92;
    case 2:
      v2 = *(_QWORD *)(a1 + 584);
      *(_QWORD *)(a1 + 16) = 0;
      if ( !v2 )
        goto LABEL_7;
      *(_QWORD *)(a1 + 16) = v2;
      v3 = *(_QWORD *)(v2 + 8);
      if ( v3 < 0 )
        goto LABEL_6;
      break;
    case 6:
      v12 = *(RTL_SRWLOCK **)(a1 + 96);
      EventW = CreateEventW(0, 0, 0, 0);
      *(_QWORD *)(a1 + 40) = EventW;
      if ( !EventW || (v69 = EventW, EventW == (HANDLE)-1LL) )
      {
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)(a1 + 48),
          L"WorkloadManager failed to create progress handle.");
        v53 = winrt::hresult::hresult((winrt::hresult *)(a1 + 80), -2147467259);
        winrt::hresult_error::hresult_error(v65, *(unsigned int *)v53, a1 + 48);
        throw (winrt::hresult_error *)v65;
      }
      FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x10u, 0);
      *(_QWORD *)(a1 + 88) = FileMappingW;
      if ( !FileMappingW || (v71 = FileMappingW, FileMappingW == (HANDLE)-1LL) )
      {
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)(a1 + 112),
          L"WorkloadManager failed to create shared result section.");
        v52 = winrt::hresult::hresult((winrt::hresult *)(a1 + 144), -2147467259);
        winrt::hresult_error::hresult_error(v64, *(unsigned int *)v52, a1 + 112);
        throw (winrt::hresult_error *)v64;
      }
      v71 = *(HANDLE *)(a1 + 88);
      v15 = MapViewOfFile(v71, 0xF001Fu, 0, 0, 0x10u);
      *(_QWORD *)(a1 + 152) = v15;
      if ( !v15 )
      {
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)(a1 + 160),
          L"WorkloadManager failed to map shared result section.");
        v16 = winrt::hresult::hresult((winrt::hresult *)(a1 + 192), -2147467259);
        winrt::hresult_error::hresult_error(v60, *(unsigned int *)v16, a1 + 160);
        throw (winrt::hresult_error *)v60;
      }
      v17 = CreateEventW(0, 0, 0, 0);
      *(_QWORD *)(a1 + 200) = v17;
      if ( !v17 || (v72 = v17, v17 == (HANDLE)-1LL) )
      {
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)(a1 + 208),
          L"WorkloadManager failed to create progress handle.");
        v51 = winrt::hresult::hresult((winrt::hresult *)(a1 + 240), -2147467259);
        winrt::hresult_error::hresult_error(v63, *(unsigned int *)v51, a1 + 208);
        throw (winrt::hresult_error *)v63;
      }
      v18 = *(_QWORD *)(a1 + 584);
      v19 = *(_DWORD *)(v18 + 224);
      *(_DWORD *)(a1 + 248) = -455322399;
      *(_DWORD *)(a1 + 252) = 1148794293;
      *(_DWORD *)(a1 + 256) = -2075124834;
      *(_DWORD *)(a1 + 260) = 1989909936;
      v20 = (_QWORD *)(a1 + 552);
      *(_QWORD *)(a1 + 552) = 0;
      Instance_0 = CoCreateInstance_0(
                     (const IID *const)(a1 + 248),
                     0,
                     v19,
                     &winrt::impl::guid_v<ISessionManagerBroker>,
                     (LPVOID *)(a1 + 552));
      if ( Instance_0 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)Instance_0);
      }
      *(_QWORD *)(a1 + 264) = *v20;
      v22 = (__int64 (__fastcall ****)(_QWORD, __int64 *, __int64))(a1 + 272);
      *(_QWORD *)(a1 + 272) = 0;
      *(_OWORD *)(a1 + 296) = 0;
      *(_QWORD *)(a1 + 312) = 0;
      *(_QWORD *)(a1 + 320) = 7;
      *(_WORD *)(a1 + 296) = 0;
      v23 = (void *)(a1 + 328);
      *(_OWORD *)(a1 + 328) = 0;
      *(_QWORD *)(a1 + 344) = 0;
      *(_QWORD *)(a1 + 352) = 7;
      *(_WORD *)(a1 + 328) = 0;
      *(_OWORD *)(a1 + 360) = 0;
      *(_OWORD *)(a1 + 376) = 0;
      *(_QWORD *)(a1 + 392) = 0;
      v66 = *v20;
      *(_QWORD *)(a1 + 288) = v66;
      v24 = (_QWORD *)(v18 + 72);
      if ( a1 + 296 != v18 + 72 )
      {
        if ( *(_QWORD *)(v18 + 96) > 7u )
          v24 = (_QWORD *)*v24;
        std::wstring::assign((void *)(a1 + 296), v24);
        v23 = (void *)(a1 + 328);
      }
      v25 = *(_QWORD *)(a1 + 592);
      if ( v25 )
        v26 = *(wchar_t **)(v25 + 16);
      else
        v26 = (wchar_t *)&Src;
      std::wstring::assign(v23, v26);
      v69 = *(HANDLE *)(a1 + 40);
      *(_QWORD *)(a1 + 360) = v69;
      v71 = *(HANDLE *)(a1 + 88);
      *(_QWORD *)(a1 + 368) = v71;
      v73 = *v22;
      if ( v73 )
        winrt::com_ptr<ISessionManagerBroker>::unconditional_release_ref(a1 + 272, v27);
      *(_QWORD *)(a1 + 376) = v22;
      v72 = *(HANDLE *)(a1 + 200);
      *(_QWORD *)(a1 + 384) = v72;
      ThreadpoolWork = CreateThreadpoolWork(
                         (PTP_WORK_CALLBACK)winrt::Microsoft::Windows::Workloads::implementation::BrokerMakeAvailableOperation,
                         (PVOID)(a1 + 288),
                         0);
      *(_QWORD *)(a1 + 400) = ThreadpoolWork;
      v58 = ThreadpoolWork != 0;
      v74 = ThreadpoolWork;
      if ( !ThreadpoolWork )
      {
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)(a1 + 408),
          L"WorkloadManager failed to create threadpool work item.");
        v29 = winrt::hresult::hresult((winrt::hresult *)(a1 + 440), -2147467259);
        winrt::hresult_error::hresult_error(v61, *(unsigned int *)v29, a1 + 408);
        throw (winrt::hresult_error *)v61;
      }
      v74 = *(PTP_WORK *)(a1 + 400);
      SubmitThreadpoolWork(v74);
      v69 = *(HANDLE *)(a1 + 40);
      *(_QWORD *)(a1 + 448) = v69;
      v72 = *(HANDLE *)(a1 + 200);
      *(_QWORD *)(a1 + 456) = v72;
      v70 = *(const void **)(a1 + 152);
      v76 = v70;
      v30 = 1;
      while ( v30 )
      {
        v31 = WaitForMultipleObjects(2u, (const HANDLE *)(a1 + 448), 0, 0xFFFFFFFF);
        if ( v31 )
        {
          if ( v31 != 1 )
          {
            winrt::param::hstring::hstring(
              (winrt::param::hstring *)(a1 + 464),
              L"WorkloadManager wait for deployment operation failed.");
            v32 = winrt::hresult::hresult((winrt::hresult *)(a1 + 496), -2147467259);
            winrt::hresult_error::hresult_error(v62, *(unsigned int *)v32, a1 + 464);
            throw (winrt::hresult_error *)v62;
          }
          v30 = 0;
          v68 = *(_DWORD *)(a1 + 392);
          if ( v68 < 0 )
          {
            _mm_lfence();
            winrt::throw_hresult(*(unsigned int *)(a1 + 392));
          }
        }
        else
        {
          WINRT_IMPL_AcquireSRWLockExclusive(v12 + 9);
          Ptr = v12[14].Ptr;
          *(_QWORD *)(a1 + 544) = Ptr;
          if ( Ptr )
          {
            (*(void (**)(void))(*(_QWORD *)Ptr + 8LL))();
            ReleaseSRWLockExclusive_0(v12 + 9);
            winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(
              a1 + 544,
              v12,
              v70);
          }
          else
          {
            ReleaseSRWLockExclusive_0(v12 + 9);
          }
          if ( *(_QWORD *)(a1 + 544) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 544);
          v69 = *(HANDLE *)(a1 + 40);
          ResetEvent(v69);
        }
      }
      *(_QWORD *)(a1 + 504) = 0;
      v73 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, __int64))(a1 + 272);
      v34 = (**v73)(
              v73,
              winrt::impl::guid_v<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>,
              a1 + 504);
      if ( v34 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v34);
      }
      v35 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, __int64))(a1 + 504);
      if ( v35 )
      {
        *(_QWORD *)(a1 + 560) = 0;
        v75 = v35;
        v37 = (**v35)(
                v35,
                winrt::impl::guid_v<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>,
                a1 + 560);
        if ( v37 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v37);
        }
        v36 = *(_QWORD *)(a1 + 560);
        v67 = v36;
      }
      else
      {
        v36 = 0;
      }
      *(_QWORD *)(a1 + 512) = v36;
      v38 = *(_QWORD *)(a1 + 592);
      if ( v38 )
        v39 = *(const wchar_t **)(v38 + 16);
      else
        v39 = &Src;
      v40 = TraceLogger::Provider();
      if ( *(_DWORD *)v40 > 5u )
      {
        *(_QWORD *)(a1 + 568) = v39;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
          (__int64)v40,
          (unsigned __int8 *)&unk_18004D5D8,
          v41,
          v42,
          (const wchar_t **)(a1 + 568));
      }
      WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)(a1 - 56));
      v43 = (_QWORD *)(a1 - 24);
      v44 = (__int64 *)(a1 + 512);
      if ( a1 - 24 != a1 + 512 )
      {
        if ( *v43 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 - 24);
        v45 = *v44;
        *v44 = 0;
        *v43 = v45;
      }
      ReleaseSRWLockExclusive_0((PSRWLOCK)(a1 - 56));
      if ( *v44 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 512);
      v75 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, __int64))(a1 + 504);
      if ( v75 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 504);
      if ( v58 )
      {
        v46 = *(struct _TP_WORK **)(a1 + 400);
        WaitForThreadpoolWorkCallbacks(v46, 1);
        CloseThreadpoolWork(v46);
      }
      std::wstring::_Tidy_deallocate(a1 + 328);
      std::wstring::_Tidy_deallocate(a1 + 296);
      v73 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, __int64))(a1 + 272);
      if ( v73 )
        winrt::com_ptr<ISessionManagerBroker>::unconditional_release_ref(a1 + 272, v47);
      if ( *(_QWORD *)(a1 + 264) )
        winrt::com_ptr<ISessionManagerBroker>::unconditional_release_ref(a1 + 264, v47);
      v48 = *(char **)(a1 + 200);
      if ( (unsigned __int64)(v48 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v48);
      if ( *(_QWORD *)(a1 + 152) )
      {
        v76 = *(LPCVOID *)(a1 + 152);
        UnmapViewOfFile(v76);
      }
      v49 = *(char **)(a1 + 88);
      if ( (unsigned __int64)(v49 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v49);
      v50 = *(char **)(a1 + 40);
      if ( (unsigned __int64)(v50 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v50);
      v70 = *(const void **)(a1 + 16);
      if ( v70 )
        winrt::com_ptr<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager>::unconditional_release_ref(a1 + 16);
      *(_QWORD *)(a1 + 520) = a1 - 128;
      *(_WORD *)(a1 + 8) = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Workloads::implementation::Workload *>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::final_suspend_awaiter::await_suspend() )
        goto LABEL_92;
      return;
    case 7:
      v11 = a1 + 16;
      v70 = *(const void **)(a1 + 16);
      if ( v70 )
        winrt::com_ptr<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager>::unconditional_release_ref(v11);
LABEL_92:
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
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        goto LABEL_108;
      v55 = *(volatile signed __int32 **)(a1 + 592);
      if ( v55 )
      {
        v56 = _InterlockedDecrement(v55 + 6);
        if ( v56 )
        {
          if ( v56 < 0 )
LABEL_108:
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v55);
        }
        *(_QWORD *)(a1 + 592) = 0;
      }
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 128));
      return;
    default:
      __debugbreak();
      return;
  }
  while ( 1 )
  {
    v4 = v3;
    v3 = _InterlockedCompareExchange64((volatile signed __int64 *)(v2 + 8), v3 + 1, v3);
    if ( v4 == v3 )
      break;
    if ( v3 < 0 )
    {
LABEL_6:
      _InterlockedIncrement((volatile signed __int32 *)(2 * v3 + 24));
      break;
    }
  }
LABEL_7:
  v5 = *(_QWORD *)(a1 + 592);
  if ( v5 )
    v6 = *(const wchar_t **)(v5 + 16);
  else
    v6 = &Src;
  v7 = TraceLogger::Provider();
  if ( *(_DWORD *)v7 > 5u )
  {
    *(_QWORD *)(a1 + 536) = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (__int64)v7,
      (unsigned __int8 *)byte_18004D615,
      v9,
      v10,
      (const wchar_t **)(a1 + 536));
  }
  *(_QWORD *)(a1 + 96) = a1 - 128;
  *(_QWORD *)(a1 + 24) = a1 - 128;
  *(_BYTE *)(a1 - 128 + 48) = 1;
  *(_BYTE *)(a1 + 32) = 0;
  if ( *(_DWORD *)(a1 - 32) == 2 )
  {
    winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject);
    throw (winrt::hresult_canceled *)pExceptionObject;
  }
  *(_WORD *)(a1 + 8) = 6;
  `winrt::resume_background'::`2'::awaitable::await_suspend(v8, a1);
}

```

## disassembly

```asm
0x18003aec0  mov     r11, rsp
0x18003aec3  mov     [r11+10h], rbx
0x18003aec7  mov     [r11+18h], rsi
0x18003aecb  mov     [r11+8], rcx
0x18003aecf  push    rdi
0x18003aed0  push    r12
0x18003aed2  push    r13
0x18003aed4  push    r14
0x18003aed6  push    r15
0x18003aed8  sub     rsp, 220h
0x18003aedf  mov     rax, cs:__security_cookie
0x18003aee6  xor     rax, rsp
0x18003aee9  mov     [rsp+248h+var_38], rax
0x18003aef1  mov     rsi, rcx
0x18003aef4  mov     [rsp+248h+var_208], rcx
0x18003aef9  movzx   eax, word ptr [rsi+8]
0x18003aefd  mov     [rsp+248h+var_214], ax
0x18003af02  inc     ax; switch 9 cases
0x18003af05  cmp     ax, 8
0x18003af09  ja      def_18003AF24; jumptable 000000018003AF24 default case, cases 0,4,5
0x18003af0f  movsx   rax, ax
0x18003af13  lea     rdx, cs:180000000h
0x18003af1a  mov     ecx, ds:(jpt_18003AF24 - 180000000h)[rdx+rax*4]
0x18003af21  add     rcx, rdx
0x18003af24  jmp     rcx; switch jump
0x18003af26  xor     r15d, r15d; jumptable 000000018003AF24 case 3
0x18003af29  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18003af30  jmp     loc_18003B86A
0x18003af35  xor     r15d, r15d; jumptable 000000018003AF24 case 2
0x18003af38  mov     rdx, [rsi+248h]
0x18003af3f  mov     [rsi+10h], r15
0x18003af43  test    rdx, rdx
0x18003af46  jz      short loc_18003AF76
0x18003af48  mov     [rsi+10h], rdx
0x18003af4c  mov     rax, [rdx+8]
0x18003af50  test    rax, rax
0x18003af53  js      short loc_18003AF71
0x18003af55  nop     word ptr [rax+rax+00000000h]
0x18003af60  lea     rcx, [rax+1]
0x18003af64  lock cmpxchg [rdx+8], rcx
0x18003af6a  jz      short loc_18003AF76
0x18003af6c  test    rax, rax
0x18003af6f  jns     short loc_18003AF60
0x18003af71  lock inc dword ptr [rax+rax+18h]
0x18003af76  mov     rbx, [rsi+250h]
0x18003af7d  test    rbx, rbx
0x18003af80  jz      short loc_18003AF88
0x18003af82  mov     rbx, [rbx+10h]
0x18003af86  jmp     short loc_18003AF8F
0x18003af88  lea     rbx, Src
0x18003af8f  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x18003af94  cmp     dword ptr [rax], 5
0x18003af97  jbe     short loc_18003AFB7
0x18003af99  lea     rcx, [rsi+218h]
0x18003afa0  mov     [rcx], rbx
0x18003afa3  mov     qword ptr [rsp+248h+dwMaximumSizeLow], rcx
0x18003afa8  lea     rdx, byte_18004D615
0x18003afaf  mov     rcx, rax
0x18003afb2  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18003afb7  lea     rax, [rsi-80h]
0x18003afbb  mov     [rsi+60h], rax
0x18003afbf  mov     [rsi+18h], rax
0x18003afc3  mov     byte ptr [rax+30h], 1
0x18003afc7  mov     byte ptr [rsi+20h], 0
0x18003afcb  mov     eax, [rsi-20h]
0x18003afce  cmp     eax, 2
0x18003afd1  jnz     short loc_18003AFEE
0x18003afd3  lea     rcx, [rsp+248h+pExceptionObject]; this
0x18003afd8  call    ??0hresult_canceled@winrt@@QEAA@XZ; winrt::hresult_canceled::hresult_canceled(void)
0x18003afdd  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18003afe4  lea     rcx, [rsp+248h+pExceptionObject]; pExceptionObject
0x18003afe9  call    _CxxThrowException
0x18003afee  mov     eax, 6
0x18003aff3  mov     [rsi+8], ax
0x18003aff7  mov     rdx, rsi
0x18003affa  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@experimental@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::experimental::coroutine_handle<void>)
0x18003afff  jmp     loc_18003B923
0x18003b004  lea     rcx, [rsi+10h]; jumptable 000000018003AF24 case 7
0x18003b008  mov     rax, [rcx]
0x18003b00b  mov     [rsp+248h+var_C0], rax
0x18003b013  test    rax, rax
0x18003b016  jz      short loc_18003B01E
0x18003b018  call    ?unconditional_release_ref@?$com_ptr@UWorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager>::unconditional_release_ref(void)
0x18003b01d  nop
0x18003b01e  xor     r15d, r15d
0x18003b021  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18003b028  jmp     loc_18003B86A
0x18003b02d  mov     rdi, [rsi+60h]; jumptable 000000018003AF24 case 6
0x18003b031  xor     r9d, r9d; lpName
0x18003b034  xor     r8d, r8d; bInitialState
0x18003b037  xor     edx, edx; bManualReset
0x18003b039  xor     ecx, ecx; lpEventAttributes
0x18003b03b  call    cs:__imp_CreateEventW
0x18003b041  mov     [rsi+28h], rax
0x18003b045  test    rax, rax
0x18003b048  jz      loc_18003B7E7
0x18003b04e  mov     [rsp+248h+var_C8], rax
0x18003b056  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003b05a  jz      loc_18003B7E7
0x18003b060  xor     r15d, r15d
0x18003b063  mov     [rsp+248h+lpName], r15; lpName
0x18003b068  mov     [rsp+248h+dwMaximumSizeLow], 10h; dwMaximumSizeLow
0x18003b070  xor     r9d, r9d; dwMaximumSizeHigh
0x18003b073  xor     edx, edx; lpFileMappingAttributes
0x18003b075  mov     r8d, 4; flProtect
0x18003b07b  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18003b082  mov     rcx, r12; hFile
0x18003b085  call    cs:__imp_CreateFileMappingW
0x18003b08b  mov     [rsi+58h], rax
0x18003b08f  test    rax, rax
0x18003b092  jz      loc_18003B79E
0x18003b098  mov     [rsp+248h+var_B8], rax
0x18003b0a0  cmp     rax, r12
0x18003b0a3  jz      loc_18003B79E
0x18003b0a9  mov     rcx, [rsi+58h]; hFileMappingObject
0x18003b0ad  mov     [rsp+248h+var_B8], rcx
0x18003b0b5  mov     qword ptr [rsp+248h+dwMaximumSizeLow], 10h; dwNumberOfBytesToMap
0x18003b0be  xor     r9d, r9d; dwFileOffsetLow
0x18003b0c1  xor     r8d, r8d; dwFileOffsetHigh
0x18003b0c4  mov     edx, 0F001Fh; dwDesiredAccess
0x18003b0c9  call    cs:__imp_MapViewOfFile
0x18003b0cf  mov     [rsi+98h], rax
0x18003b0d6  test    rax, rax
0x18003b0d9  jnz     short loc_18003B123
0x18003b0db  lea     rdx, aWorkloadmanage_3; "WorkloadManager failed to map shared re"...
0x18003b0e2  lea     rcx, [rsi+0A0h]; this
0x18003b0e9  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18003b0ee  lea     rcx, [rsi+0C0h]; this
0x18003b0f5  mov     edx, 80004005h; int
0x18003b0fa  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18003b0ff  lea     r8, [rsi+0A0h]
0x18003b106  mov     edx, [rax]
0x18003b108  lea     rcx, [rsp+248h+var_1D8]
0x18003b10d  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &)
0x18003b112  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18003b119  lea     rcx, [rsp+248h+var_1D8]; pExceptionObject
0x18003b11e  call    _CxxThrowException
0x18003b123  xor     r9d, r9d; lpName
0x18003b126  xor     r8d, r8d; bInitialState
0x18003b129  xor     edx, edx; bManualReset
0x18003b12b  xor     ecx, ecx; lpEventAttributes
0x18003b12d  call    cs:__imp_CreateEventW
0x18003b133  mov     [rsi+0C8h], rax
0x18003b13a  test    rax, rax
0x18003b13d  jz      loc_18003B74F
0x18003b143  mov     [rsp+248h+var_B0], rax
0x18003b14b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003b14f  jz      loc_18003B74F
0x18003b155  mov     r13, [rsi+248h]
0x18003b15c  mov     r8d, [r13+0E0h]; dwClsContext
0x18003b163  lea     rcx, [rsi+0F8h]; rclsid
0x18003b16a  mov     dword ptr [rcx], 0E4DC54E1h
0x18003b170  mov     dword ptr [rsi+0FCh], 447935B5h
0x18003b17a  mov     dword ptr [rsi+100h], 84501B9Eh
0x18003b184  mov     dword ptr [rsi+104h], 769B9DB0h
0x18003b18e  lea     rbx, [rsi+228h]
0x18003b195  mov     [rbx], r15
0x18003b198  mov     qword ptr [rsp+248h+dwMaximumSizeLow], rbx; ppv
0x18003b19d  lea     r9, ??$guid_v@UISessionManagerBroker@@@impl@winrt@@3Uguid@2@B; riid
0x18003b1a4  xor     edx, edx; pUnkOuter
0x18003b1a6  call    CoCreateInstance_0
0x18003b1ab  test    eax, eax
0x18003b1ad  jns     short loc_18003B1B9
0x18003b1af  lfence
0x18003b1b2  mov     ecx, eax
0x18003b1b4  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x18003b1b9  mov     rax, [rbx]
0x18003b1bc  mov     [rsi+108h], rax
0x18003b1c3  lea     r14, [rsi+110h]
0x18003b1ca  mov     [r14], r15
0x18003b1cd  lea     rcx, [rsi+128h]; void *
0x18003b1d4  xorps   xmm0, xmm0
0x18003b1d7  movups  xmmword ptr [rcx], xmm0
0x18003b1da  mov     [rsi+138h], r15
0x18003b1e1  mov     qword ptr [rsi+140h], 7
0x18003b1ec  xor     eax, eax
0x18003b1ee  mov     [rcx], ax
0x18003b1f1  lea     r9, [rsi+148h]
0x18003b1f8  movups  xmmword ptr [r9], xmm0
0x18003b1fc  mov     [rsi+158h], r15
0x18003b203  mov     qword ptr [rsi+160h], 7
0x18003b20e  mov     [r9], ax
0x18003b212  movups  xmmword ptr [rsi+168h], xmm0
0x18003b219  movups  xmmword ptr [rsi+178h], xmm0
0x18003b220  mov     [rsi+188h], rax
0x18003b227  mov     rax, [rbx]
0x18003b22a  mov     [rsp+248h+var_148], rax
0x18003b232  mov     [rsi+120h], rax
0x18003b239  lea     rdx, [r13+48h]
0x18003b23d  cmp     rcx, rdx
0x18003b240  jz      short loc_18003B25C
0x18003b242  mov     r8, [rdx+10h]
0x18003b246  cmp     qword ptr [rdx+18h], 7
0x18003b24b  jbe     short loc_18003B250
0x18003b24d  mov     rdx, [rdx]; Src
0x18003b250  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x18003b255  lea     r9, [rsi+148h]
0x18003b25c  mov     rax, [rsi+250h]
0x18003b263  test    rax, rax
0x18003b266  jz      short loc_18003B272
0x18003b268  mov     rdx, [rax+10h]
0x18003b26c  mov     r8d, [rax+4]
0x18003b270  jmp     short loc_18003B27C
0x18003b272  lea     rdx, Src; Src
0x18003b279  mov     r8, r15
0x18003b27c  mov     rcx, r9; void *
0x18003b27f  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x18003b284  mov     rax, [rsi+28h]
0x18003b288  mov     [rsp+248h+var_C8], rax
0x18003b290  mov     [rsi+168h], rax
0x18003b297  mov     rax, [rsi+58h]
0x18003b29b  mov     [rsp+248h+var_B8], rax
0x18003b2a3  mov     [rsi+170h], rax
0x18003b2aa  mov     rax, [r14]
0x18003b2ad  mov     [rsp+248h+var_A8], rax
0x18003b2b5  test    rax, rax
0x18003b2b8  jz      short loc_18003B2C2
0x18003b2ba  mov     rcx, r14
0x18003b2bd  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerBroker@@@winrt@@AEAAXXZ; winrt::com_ptr<ISessionManagerBroker>::unconditional_release_ref(void)
0x18003b2c2  mov     [rsi+178h], r14
0x18003b2c9  mov     rax, [rsi+0C8h]
0x18003b2d0  mov     [rsp+248h+var_B0], rax
0x18003b2d8  mov     [rsi+180h], rax
0x18003b2df  xor     r8d, r8d; pcbe
0x18003b2e2  lea     rdx, [rsi+120h]; pv
0x18003b2e9  lea     rcx, ?BrokerMakeAvailableOperation@implementation@Workloads@Windows@Microsoft@winrt@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18003b2f0  call    cs:__imp_CreateThreadpoolWork
0x18003b2f6  mov     [rsi+190h], rax
0x18003b2fd  test    rax, rax
0x18003b300  setnz   [rsp+248h+var_218]
0x18003b305  mov     [rsp+248h+var_A0], rax
0x18003b30d  test    rax, rax
0x18003b310  jnz     short loc_18003B360
0x18003b312  lea     rdx, aWorkloadmanage_0; "WorkloadManager failed to create thread"...
0x18003b319  lea     rcx, [rsi+198h]; this
0x18003b320  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18003b325  lea     rcx, [rsi+1B8h]; this
0x18003b32c  mov     edx, 80004005h; int
0x18003b331  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18003b336  lea     r8, [rsi+198h]
0x18003b33d  mov     edx, [rax]
0x18003b33f  lea     rcx, [rsp+248h+var_1C0]
0x18003b347  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &)
0x18003b34c  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18003b353  lea     rcx, [rsp+248h+var_1C0]; pExceptionObject
0x18003b35b  call    _CxxThrowException
0x18003b360  mov     rcx, [rsi+190h]; pwk
0x18003b367  mov     [rsp+248h+var_A0], rcx
0x18003b36f  call    cs:__imp_SubmitThreadpoolWork
0x18003b375  mov     rax, [rsi+28h]
0x18003b379  mov     [rsp+248h+var_C8], rax
0x18003b381  mov     [rsi+1C0h], rax
0x18003b388  mov     rax, [rsi+0C8h]
0x18003b38f  mov     [rsp+248h+var_B0], rax
0x18003b397  mov     [rsi+1C8h], rax
0x18003b39e  mov     rax, [rsi+98h]
0x18003b3a5  mov     [rsp+248h+var_C0], rax
0x18003b3ad  mov     [rsp+248h+var_90], rax
0x18003b3b5  mov     r13b, 1
0x18003b3b8  nop     dword ptr [rax+rax+00000000h]
0x18003b3c0  test    r13b, r13b
0x18003b3c3  jz      loc_18003B502
0x18003b3c9  lea     rdx, [rsi+1C0h]; lpHandles
0x18003b3d0  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x18003b3d6  xor     r8d, r8d; bWaitAll
0x18003b3d9  mov     ecx, 2; nCount
0x18003b3de  call    cs:__imp_WaitForMultipleObjects
0x18003b3e4  test    eax, eax
0x18003b3e6  jz      loc_18003B46C
0x18003b3ec  cmp     eax, 1
0x18003b3ef  jz      short loc_18003B43F
0x18003b3f1  lea     rdx, aWorkloadmanage_2; "WorkloadManager wait for deployment ope"...
0x18003b3f8  lea     rcx, [rsi+1D0h]; this
0x18003b3ff  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18003b404  lea     rcx, [rsi+1F0h]; this
0x18003b40b  mov     edx, 80004005h; int
0x18003b410  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18003b415  lea     r8, [rsi+1D0h]
0x18003b41c  mov     edx, [rax]
0x18003b41e  lea     rcx, [rsp+248h+var_1A8]
0x18003b426  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &)
0x18003b42b  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18003b432  lea     rcx, [rsp+248h+var_1A8]; pExceptionObject
0x18003b43a  call    _CxxThrowException
0x18003b43f  xor     r13b, r13b
0x18003b442  mov     eax, [rsi+188h]
0x18003b448  mov     [rsp+248h+var_D0], eax
0x18003b44f  test    eax, eax
0x18003b451  jns     loc_18003B3C0
0x18003b457  lfence
0x18003b45a  mov     ecx, [rsi+188h]
0x18003b460  mov     [rsp+248h+var_D0], ecx
0x18003b467  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x18003b46c  lea     rcx, [rdi+48h]; SRWLock
0x18003b470  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18003b475  mov     rax, [rdi+70h]
0x18003b479  mov     [rsi+220h], rax
0x18003b480  test    rax, rax
0x18003b483  jz      short loc_18003B4C5
0x18003b485  mov     [rsp+248h+var_210], rax
  ... truncated ...
```
