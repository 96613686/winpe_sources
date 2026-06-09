# winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::StartWorkloadSessionAndCacheModels(winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem const &)

- ea: `0x180007410`
- end: `0x180007c33`
- name: `?StartWorkloadSessionAndCacheModels@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@AEAAXAEBUCacheQueueItem@1234567@@Z`
- size: `2083`
- prototype: `void __fastcall(winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *__hidden this, const struct winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *)`
- caller_count: `3`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180007ed0`
- `0x18001c7a0`
- `0x18001ca20`

## callees

- `0x180003840`
- `0x180003ee0`
- `0x180006750`
- `0x180007410`
- `0x180007c40`
- `0x1800095d0`
- `0x180009e10`
- `0x18000a5d0`
- `0x18000a740`
- `0x18000a770`
- `0x18000adb0`
- `0x18000e830`
- `0x18000f840`
- `0x180010cb0`
- `0x180011800`
- `0x1800119c0`
- `0x180011aa0`
- `0x180011c00`
- `0x180011ce0`
- `0x1800127e0`
- `0x180012f10`
- `0x180016298`
- `0x18001629e`
- `0x1800181b0`
- `0x180018238`
- `0x18001c77d`
- `0x18001cdf0`
- `0x18001d600`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180007a74`
- `KERNEL32!LeaveCriticalSection` at `0x180007a74`
- `KERNEL32!EnterCriticalSection` at `0x1800074b7`
- `KERNEL32!EnterCriticalSection` at `0x180007a46`
- `KERNEL32!EnterCriticalSection` at `0x1800074b7`
- `KERNEL32!EnterCriticalSection` at `0x180007a46`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180007b58`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180007b58`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180007b5f`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180007b6e`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180007b5f`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180007b6e`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::StartWorkloadSessionAndCacheModels(
        winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *this,
        const struct winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CacheQueueItem *a2)
{
  wchar_t *v3; // rdi
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  __int64 v5; // r8
  __int64 v6; // rcx
  __int64 v7; // rcx
  int v8; // eax
  __int64 *v9; // rbx
  HRESULT v10; // eax
  LPVOID v11; // rsi
  int v12; // eax
  int v13; // eax
  void (__fastcall ***v14)(LPVOID, __int64 *, LPVOID *); // rdi
  int v15; // eax
  int v16; // eax
  LPVOID v17; // r14
  int v18; // eax
  volatile signed __int32 *v19; // r12
  char *v20; // r13
  char *v21; // r14
  __int64 v22; // rsi
  LPVOID v23; // rcx
  LPVOID v24; // rbx
  int v25; // eax
  __int64 v26; // rcx
  LPVOID v27; // rsi
  const wchar_t *v28; // rdx
  struct winrt::impl::hstring_header *v29; // rdx
  volatile signed __int32 *v30; // rbx
  int v31; // eax
  int v32; // eax
  int v33; // eax
  HANDLE ProcessHeap; // rax
  _DWORD *v35; // r14
  struct _RTL_CRITICAL_SECTION *v36; // r15
  int v37; // eax
  HANDLE v38; // rax
  unsigned __int64 v39; // rdx
  char *v40; // rax
  IID rclsid; // [rsp+30h] [rbp-D0h] BYREF
  __int64 (__fastcall *v42)(const struct winrt::Windows::Foundation::IActivationFactory *); // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v43; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v44; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v45; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v46; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v47; // [rsp+68h] [rbp-98h] BYREF
  void *v48; // [rsp+70h] [rbp-90h] BYREF
  char *v49; // [rsp+78h] [rbp-88h]
  __int64 v50; // [rsp+80h] [rbp-80h]
  _QWORD v51[2]; // [rsp+88h] [rbp-78h] BYREF
  LPVOID v52; // [rsp+98h] [rbp-68h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v54; // [rsp+A8h] [rbp-58h] BYREF
  __int64 *v55; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID ppv; // [rsp+B8h] [rbp-48h] BYREF
  LPVOID lpMem; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v58; // [rsp+C8h] [rbp-38h] BYREF
  __int64 (__fastcall ***v59)(_QWORD, __int64 *, LPVOID *); // [rsp+D0h] [rbp-30h] BYREF
  __int64 (__fastcall ***v60)(_QWORD, __int64 *, _QWORD); // [rsp+D8h] [rbp-28h] BYREF
  _OWORD v61[3]; // [rsp+E0h] [rbp-20h] BYREF
  LPVOID v62; // [rsp+110h] [rbp+10h]
  _OWORD v63[21]; // [rsp+120h] [rbp+20h] BYREF

  memset(v61, 0, sizeof(v61));
  v62 = 0;
  pv = 0;
  tip2::tip_test<tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>>::start_and_watch_errors(
    &pv,
    v61);
  if ( pv )
    tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::Release(pv);
  if ( *(_QWORD *)a2 )
    v3 = *(wchar_t **)(*(_QWORD *)a2 + 16LL);
  else
    v3 = (wchar_t *)&S2;
  v4 = (struct _RTL_CRITICAL_SECTION *)v62;
  v43 = (__int64 *)v62;
  if ( v62 )
    _InterlockedIncrement((volatile signed __int32 *)v62 + 74);
  EnterCriticalSection(v4 + 5);
  v5 = -1;
  do
    ++v5;
  while ( v3[v5] );
  std::wstring::assign(&v4[6].LockSemaphore, v3);
  if ( v4 )
  {
    tip2::details::shared_data<0,0,0>::end_update(&v4->LockCount);
    tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::Release(v4);
  }
  winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::GetWorkloadModelPackageSessionClassNames(
    v6,
    &v48,
    a2);
  v43 = &qword_18002E6F8;
  _InterlockedIncrement64(&qword_18002E6F8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory> )
  {
    _lambda_6fd1ee5d6179fa7e6cafc7c7248cd72e_::operator()(
      v7,
      &v58,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_18002E6F8);
  }
  else
  {
    _InterlockedDecrement64(&qword_18002E6F8);
    v42 = _lambda_6fd1ee5d6179fa7e6cafc7c7248cd72e_::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Management::Deployment::PackageManager (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      v7,
      &v58,
      &v42);
  }
  v55 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 **))(*(_QWORD *)v58 + 168LL))(
         v58,
         0,
         *(_QWORD *)a2,
         &v55);
  if ( v8 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v8);
  }
  v9 = v55;
  v43 = v55;
  if ( v58 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v58);
  rclsid.Data1 = -455322399;
  *(_DWORD *)&rclsid.Data2 = 1148794293;
  *(_DWORD *)rclsid.Data4 = -2075124834;
  *(_DWORD *)&rclsid.Data4[4] = 1989909936;
  ppv = 0;
  v10 = CoCreateInstance_0(&rclsid, 0, 4u, &winrt::impl::guid_v<ISessionManagerBroker>, &ppv);
  if ( v10 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v10);
  }
  v11 = ppv;
  v47 = ppv;
  v60 = 0;
  v12 = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall ****)(_QWORD, __int64 *, _QWORD)))(*(_QWORD *)ppv + 24LL))(
          ppv,
          &v60);
  if ( v12 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v12);
  }
  v59 = 0;
  v13 = (**v60)(
          v60,
          winrt::impl::guid_v<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManager>,
          &v59);
  if ( v13 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v13);
  }
  if ( v59 )
  {
    pv = 0;
    v15 = (**v59)(
            v59,
            winrt::impl::guid_v<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManager>,
            &pv);
    if ( v15 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v15);
    }
    v14 = (void (__fastcall ***)(LPVOID, __int64 *, LPVOID *))pv;
    v42 = (__int64 (__fastcall *)(const struct winrt::Windows::Foundation::IActivationFactory *))pv;
  }
  else
  {
    v14 = 0;
    v42 = 0;
  }
  pv = 0;
  v16 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(*v9 + 48))(v9, &pv);
  if ( v16 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v16);
  }
  v17 = pv;
  v54 = pv;
  lpMem = 0;
  v18 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)pv + 104LL))(pv, &lpMem);
  if ( v18 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v18);
  }
  v19 = (volatile signed __int32 *)lpMem;
  *(_QWORD *)&rclsid.Data1 = lpMem;
  if ( v17 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v54);
  v20 = (char *)v48;
  v21 = (char *)v48;
  if ( v48 != v49 )
  {
    do
    {
      v22 = *(_QWORD *)v21;
      v54 = 0;
      v52 = 0;
      if ( v14 )
      {
        (**v14)(
          v14,
          winrt::impl::guid_v<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManager3>,
          &v52);
        v23 = v52;
        v24 = v52;
      }
      else
      {
        v23 = 0;
        v24 = 0;
      }
      v25 = (*(__int64 (__fastcall **)(LPVOID, volatile signed __int32 *, __int64, _QWORD, LPVOID *))(*(_QWORD *)v23 + 48LL))(
              v23,
              v19,
              v22,
              0,
              &v54);
      if ( v25 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v25);
      }
      if ( v24 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v52);
      v52 = v54;
      winrt::impl::wait_get<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::IInspectable>>(
        &v58,
        &v52);
      if ( v52 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v52);
      v26 = v58;
      if ( v58 )
      {
        v52 = 0;
        (**(void (__fastcall ***)(__int64, __int64 *, LPVOID *))v58)(
          v58,
          winrt::impl::guid_v<winrt::Microsoft::Windows::PrivateCommon::IModelManager2>,
          &v52);
        v27 = v52;
        v46 = v52;
        if ( v52 )
        {
          std::chrono::steady_clock::now(&v45);
          memset(v63, 0, 0x148u);
          if ( *(_QWORD *)v21 )
            v28 = *(const wchar_t **)(*(_QWORD *)v21 + 16LL);
          else
            v28 = &S2;
          DWORD2(v63[0]) = 0;
          BYTE12(v63[0]) = 0;
          BYTE8(v63[4]) = 0;
          LODWORD(v63[3]) = 0;
          *((_QWORD *)&v63[3] + 1) = "ModelCaching";
          *(_QWORD *)&v63[4] = 0;
          LODWORD(v63[5]) = 0;
          v63[15] = 0;
          *(_OWORD *)((char *)&v63[5] + 8) = 0;
          *(_OWORD *)((char *)&v63[6] + 8) = 0;
          *(_OWORD *)((char *)&v63[7] + 8) = 0;
          *(_OWORD *)((char *)&v63[8] + 8) = 0;
          *(_OWORD *)((char *)&v63[9] + 8) = 0;
          *(_OWORD *)((char *)&v63[10] + 8) = 0;
          *(_OWORD *)((char *)&v63[11] + 8) = 0;
          *(_OWORD *)((char *)&v63[12] + 8) = 0;
          *(_OWORD *)((char *)&v63[13] + 8) = 0;
          *((_QWORD *)&v63[14] + 1) = 0;
          LODWORD(v63[16]) = 1;
          *((_QWORD *)&v63[16] + 1) = 0;
          *(_QWORD *)&v63[17] = (char *)v63 + 8;
          *((_QWORD *)&v63[17] + 1) = 0;
          *(_QWORD *)&v63[18] = 0;
          *((_QWORD *)&v63[18] + 1) = v63;
          *(_QWORD *)&v63[19] = 0;
          DWORD2(v63[19]) = 0;
          *(_QWORD *)&v63[20] = &v63[3];
          *(_QWORD *)&v63[0] = &TelemetryLogger::ModelCaching::`vftable';
          TelemetryLogger::ModelCaching::StartActivity((TelemetryLogger::ModelCaching *)v63, v28, *((_BYTE *)a2 + 24));
          if ( *((_BYTE *)a2 + 16) )
          {
            v30 = (volatile signed __int32 *)winrt::impl::duplicate_hstring(*((winrt::impl **)a2 + 1), v29);
            pv = (LPVOID)v30;
          }
          else
          {
            v51[0] = &S2;
            v51[1] = 0;
            winrt::hstring::hstring(&pv, v51);
            v30 = (volatile signed __int32 *)pv;
          }
          v31 = (*(__int64 (__fastcall **)(LPVOID, volatile signed __int32 *))(*(_QWORD *)v27 + 48LL))(v27, v19);
          if ( v31 < 0 )
          {
            _mm_lfence();
            winrt::throw_hresult((unsigned int)v31);
          }
          v54 = 0;
          (**(void (__fastcall ***)(LPVOID, __int64 *, LPVOID *))v27)(
            v27,
            winrt::impl::guid_v<winrt::Microsoft::Windows::PrivateCommon::IModelManager>,
            &v54);
          v32 = (*(__int64 (__fastcall **)(LPVOID, volatile signed __int32 *))(*(_QWORD *)v54 + 56LL))(v54, v30);
          if ( v32 < 0 )
          {
            _mm_lfence();
            winrt::throw_hresult((unsigned int)v32);
          }
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v54);
          std::chrono::steady_clock::now(&v44);
          TelemetryLogger::ModelCaching::Stop(v63, (v44 - v45) / 1000000);
          if ( v30 )
          {
            v33 = _InterlockedDecrement(v30 + 6);
            if ( v33 )
            {
              if ( v33 < 0 )
                abort();
            }
            else
            {
              ProcessHeap = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v30);
            }
            pv = 0;
            v27 = v52;
            v19 = (volatile signed __int32 *)lpMem;
          }
          TelemetryLogger::ModelCaching::~ModelCaching((TelemetryLogger::ModelCaching *)v63);
        }
        if ( v27 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v46);
        v26 = v58;
      }
      if ( v26 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v58);
      v21 += 8;
    }
    while ( v21 != v49 );
    v9 = v55;
    v11 = ppv;
  }
  v35 = v62;
  v36 = (struct _RTL_CRITICAL_SECTION *)((char *)v62 + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)v62 + 5);
  v35[18] |= 0x300u;
  if ( *((_QWORD *)v35 + 30) )
    tip2::details::shared_data<0,0,0>::complete_helper(v35 + 2, 2);
  if ( v36 )
    LeaveCriticalSection(v36);
  if ( v19 )
  {
    v37 = _InterlockedDecrement(v19 + 6);
    if ( v37 )
    {
      if ( v37 < 0 )
        abort();
    }
    else
    {
      v38 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v38, 0, lpMem);
    }
    v11 = ppv;
    v9 = v55;
  }
  if ( v14 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v42);
  if ( v59 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v59);
  if ( v60 )
    winrt::com_ptr<ISessionManagerBroker>::unconditional_release_ref(&v60);
  if ( v11 )
    winrt::com_ptr<ISessionManagerBroker>::unconditional_release_ref(&v47);
  if ( v9 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v43);
  if ( v20 )
  {
    std::_Destroy_range<std::allocator<winrt::hstring>>(v20, v49);
    v39 = (v50 - (_QWORD)v20) & 0xFFFFFFFFFFFFFFF8uLL;
    v40 = v20;
    if ( v39 >= 0x1000 )
    {
      _mm_lfence();
      v39 += 39LL;
      v20 = (char *)*((_QWORD *)v20 - 1);
      if ( (unsigned __int64)(v40 - v20 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    operator delete(v20, v39);
  }
  if ( v62 )
    tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::Release(v62);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)((char *)v61 + 8));
}

```

## disassembly

```asm
0x180007410  mov     [rsp-8+arg_0], rbx
0x180007415  mov     [rsp-8+arg_10], rsi
0x18000741a  mov     [rsp-8+arg_18], rdi
0x18000741f  push    rbp
0x180007420  push    r12
0x180007422  push    r13
0x180007424  push    r14
0x180007426  push    r15
0x180007428  lea     rbp, [rsp-180h]
0x180007430  sub     rsp, 280h
0x180007437  mov     rax, cs:__security_cookie
0x18000743e  xor     rax, rsp
0x180007441  mov     [rbp+1A0h+var_30], rax
0x180007448  mov     r15, rdx
0x18000744b  xor     r12d, r12d
0x18000744e  xorps   xmm0, xmm0
0x180007451  xor     eax, eax
0x180007453  movups  [rbp+1A0h+var_1C0], xmm0
0x180007457  movups  [rbp+1A0h+var_1B0], xmm0
0x18000745b  movups  [rbp+1A0h+var_1A0], xmm0
0x18000745f  mov     [rbp+1A0h+var_190], rax
0x180007463  mov     [rbp+1A0h+pv], r12
0x180007467  lea     rdx, [rbp+1A0h+var_1C0]
0x18000746b  lea     rcx, [rbp+1A0h+pv]
0x18000746f  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_ModelCacheManagerPackageCacheGenerationTest@AIFabricTipTest@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_ModelCacheManagerPackageCacheGenerationTest@AIFabricTipTest@@U12@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>>::start_and_watch_errors(void)
0x180007474  mov     rcx, [rbp+1A0h+pv]; pv
0x180007478  test    rcx, rcx
0x18000747b  jz      short loc_180007483
0x18000747d  call    ?Release@?$merged_data@U_tip_ModelCacheManagerPackageCacheGenerationTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::Release(void)
0x180007482  nop
0x180007483  mov     rdi, [r15]
0x180007486  lea     rax, S2
0x18000748d  test    rdi, rdi
0x180007490  jz      short loc_180007498
0x180007492  mov     rdi, [rdi+10h]
0x180007496  jmp     short loc_18000749B
0x180007498  mov     rdi, rax
0x18000749b  mov     rbx, [rbp+1A0h+var_190]
0x18000749f  mov     [rsp+2A0h+var_258], rbx
0x1800074a4  test    rbx, rbx
0x1800074a7  jz      short loc_1800074B0
0x1800074a9  lock inc dword ptr [rbx+128h]
0x1800074b0  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800074b7  call    cs:__imp_EnterCriticalSection
0x1800074bd  nop
0x1800074be  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800074c5  inc     r8
0x1800074c8  cmp     word ptr [rdi+r8*2], 0
0x1800074ce  jnz     short loc_1800074C5
0x1800074d0  lea     rcx, [rbx+108h]; void *
0x1800074d7  mov     rdx, rdi; Src
0x1800074da  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x1800074df  nop
0x1800074e0  test    rbx, rbx
0x1800074e3  jz      short loc_1800074F6
0x1800074e5  lea     rcx, [rbx+8]
0x1800074e9  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x1800074ee  mov     rcx, rbx; pv
0x1800074f1  call    ?Release@?$merged_data@U_tip_ModelCacheManagerPackageCacheGenerationTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::Release(void)
0x1800074f6  mov     r8, r15
0x1800074f9  lea     rdx, [rsp+2A0h+var_230]
0x1800074fe  call    ?GetWorkloadModelPackageSessionClassNames@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@AEAA?AV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@AEBUhstring@7@@Z; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::GetWorkloadModelPackageSessionClassNames(winrt::hstring const &)
0x180007503  nop
0x180007504  lea     rax, qword_18002E6F8
0x18000750b  mov     [rsp+2A0h+var_258], rax
0x180007510  lock inc cs:qword_18002E6F8
0x180007518  cmp     cs:??$factory_cache_entry_v@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, 0; factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>
0x180007520  jz      short loc_18000753D
0x180007522  lea     r8, ??$factory_cache_entry_v@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>
0x180007529  lea     rdx, [rbp+1A0h+var_1D8]
0x18000752d  call    ??R_lambda_6fd1ee5d6179fa7e6cafc7c7248cd72e_@@QEBA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_6fd1ee5d6179fa7e6cafc7c7248cd72e_::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x180007532  nop
0x180007533  lock dec cs:qword_18002E6F8
0x18000753b  jmp     short loc_180007560
0x18000753d  lock dec cs:qword_18002E6F8
0x180007545  lea     rax, ?_lambda_invoker_cdecl_@_lambda_6fd1ee5d6179fa7e6cafc7c7248cd72e_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_6fd1ee5d6179fa7e6cafc7c7248cd72e_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x18000754c  mov     [rsp+2A0h+var_260], rax
0x180007551  lea     r8, [rsp+2A0h+var_260]
0x180007556  lea     rdx, [rbp+1A0h+var_1D8]
0x18000755a  call    ??$call@P6A?AUPackageManager@Deployment@Management@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUPackageManager@Deployment@Management@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x18000755f  nop
0x180007560  mov     [rbp+1A0h+var_1F0], r12
0x180007564  mov     rcx, [rbp+1A0h+var_1D8]
0x180007568  mov     rax, [rcx]
0x18000756b  lea     r9, [rbp+1A0h+var_1F0]
0x18000756f  mov     r8, [r15]
0x180007572  xor     edx, edx
0x180007574  mov     rax, [rax+0A8h]
0x18000757b  call    cs:__guard_dispatch_icall_fptr
0x180007581  test    eax, eax
0x180007583  js      loc_180007BD0
0x180007589  mov     rbx, [rbp+1A0h+var_1F0]
0x18000758d  mov     [rsp+2A0h+var_258], rbx
0x180007592  cmp     [rbp+1A0h+var_1D8], 0
0x180007597  jz      short loc_1800075A2
0x180007599  lea     rcx, [rbp+1A0h+var_1D8]
0x18000759d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800075a2  mov     [rsp+2A0h+rclsid.Data1], 0E4DC54E1h
0x1800075aa  mov     dword ptr [rsp+2A0h+rclsid.Data2], 447935B5h
0x1800075b2  mov     dword ptr [rsp+2A0h+rclsid.Data4], 84501B9Eh
0x1800075ba  mov     dword ptr [rsp+2A0h+rclsid.Data4+4], 769B9DB0h
0x1800075c2  mov     [rbp+1A0h+var_1E8], r12
0x1800075c6  lea     rax, [rbp+1A0h+var_1E8]
0x1800075ca  mov     [rsp+2A0h+ppv], rax; ppv
0x1800075cf  lea     r9, ??$guid_v@UISessionManagerBroker@@@impl@winrt@@3Uguid@2@B; riid
0x1800075d6  xor     edx, edx; pUnkOuter
0x1800075d8  mov     r8d, 4; dwClsContext
0x1800075de  lea     rcx, [rsp+2A0h+rclsid]; rclsid
0x1800075e3  call    CoCreateInstance_0
0x1800075e8  test    eax, eax
0x1800075ea  js      loc_180007BDB
0x1800075f0  mov     rsi, [rbp+1A0h+var_1E8]
0x1800075f4  mov     [rsp+2A0h+var_238], rsi
0x1800075f9  mov     [rbp+1A0h+var_1C8], r12
0x1800075fd  mov     rax, [rsi]
0x180007600  lea     rdx, [rbp+1A0h+var_1C8]
0x180007604  mov     rcx, rsi
0x180007607  mov     rax, [rax+18h]
0x18000760b  call    cs:__guard_dispatch_icall_fptr
0x180007611  test    eax, eax
0x180007613  js      loc_180007BE6
0x180007619  mov     [rbp+1A0h+var_1D0], r12
0x18000761d  mov     rcx, [rbp+1A0h+var_1C8]
0x180007621  mov     rax, [rcx]
0x180007624  lea     r8, [rbp+1A0h+var_1D0]
0x180007628  lea     rdx, ??$guid_v@UISessionManager@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManager>
0x18000762f  mov     rax, [rax]
0x180007632  call    cs:__guard_dispatch_icall_fptr
0x180007638  test    eax, eax
0x18000763a  js      loc_180007BF1
0x180007640  mov     rcx, [rbp+1A0h+var_1D0]
0x180007644  test    rcx, rcx
0x180007647  jnz     short loc_180007653
0x180007649  mov     rdi, r12
0x18000764c  mov     [rsp+2A0h+var_260], r12
0x180007651  jmp     short loc_18000767F
0x180007653  mov     [rbp+1A0h+pv], r12
0x180007657  mov     rax, [rcx]
0x18000765a  lea     r8, [rbp+1A0h+pv]
0x18000765e  lea     rdx, ??$guid_v@UISessionManager@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManager>
0x180007665  mov     rax, [rax]
0x180007668  call    cs:__guard_dispatch_icall_fptr
0x18000766e  test    eax, eax
0x180007670  js      loc_180007BFC
0x180007676  mov     rdi, [rbp+1A0h+pv]
0x18000767a  mov     [rsp+2A0h+var_260], rdi
0x18000767f  mov     [rbp+1A0h+pv], r12
0x180007683  mov     rax, [rbx]
0x180007686  lea     rdx, [rbp+1A0h+pv]
0x18000768a  mov     rcx, rbx
0x18000768d  mov     rax, [rax+30h]
0x180007691  call    cs:__guard_dispatch_icall_fptr
0x180007697  test    eax, eax
0x180007699  js      loc_180007C07
0x18000769f  mov     r14, [rbp+1A0h+pv]
0x1800076a3  mov     [rbp+1A0h+var_1F8], r14
0x1800076a7  mov     [rbp+1A0h+lpMem], r12
0x1800076ab  mov     rax, [r14]
0x1800076ae  lea     rdx, [rbp+1A0h+lpMem]
0x1800076b2  mov     rcx, r14
0x1800076b5  mov     rax, [rax+68h]
0x1800076b9  call    cs:__guard_dispatch_icall_fptr
0x1800076bf  test    eax, eax
0x1800076c1  js      loc_180007C12
0x1800076c7  mov     r12, [rbp+1A0h+lpMem]
0x1800076cb  mov     qword ptr [rsp+2A0h+rclsid.Data1], r12
0x1800076d0  test    r14, r14
0x1800076d3  jz      short loc_1800076DE
0x1800076d5  lea     rcx, [rbp+1A0h+var_1F8]
0x1800076d9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800076de  mov     r13, [rsp+2A0h+var_230]
0x1800076e3  mov     r14, r13
0x1800076e6  cmp     r13, [rsp+2A0h+var_228]
0x1800076eb  jz      loc_180007A38
0x1800076f1  nop     dword ptr [rax+00h]
0x1800076f5  nop     word ptr [rax+rax+00000000h]
0x180007700  mov     rsi, [r14]
0x180007703  xor     eax, eax
0x180007705  mov     [rbp+1A0h+var_1F8], rax
0x180007709  mov     [rbp+1A0h+var_208], rax
0x18000770d  test    rdi, rdi
0x180007710  jnz     short loc_180007718
0x180007712  mov     ecx, eax
0x180007714  mov     ebx, eax
0x180007716  jmp     short loc_18000773D
0x180007718  mov     rax, [rdi]
0x18000771b  lea     r8, [rbp+1A0h+var_208]
0x18000771f  lea     rdx, ??$guid_v@UISessionManager3@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManager3>
0x180007726  mov     rcx, rdi
0x180007729  mov     rax, [rax]
0x18000772c  call    cs:__guard_dispatch_icall_fptr
0x180007732  mov     rcx, [rbp+1A0h+var_208]
0x180007736  mov     [rbp+1A0h+var_208], rcx
0x18000773a  mov     rbx, rcx
0x18000773d  mov     rax, [rcx]
0x180007740  lea     rdx, [rbp+1A0h+var_1F8]
0x180007744  mov     [rsp+2A0h+ppv], rdx
0x180007749  xor     r9d, r9d
0x18000774c  mov     r8, rsi
0x18000774f  mov     rdx, r12
0x180007752  mov     rax, [rax+30h]
0x180007756  call    cs:__guard_dispatch_icall_fptr
0x18000775c  test    eax, eax
0x18000775e  js      loc_180007BC5
0x180007764  test    rbx, rbx
0x180007767  jz      short loc_180007772
0x180007769  lea     rcx, [rbp+1A0h+var_208]
0x18000776d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180007772  mov     rax, [rbp+1A0h+var_1F8]
0x180007776  mov     [rbp+1A0h+var_208], rax
0x18000777a  lea     rdx, [rbp+1A0h+var_208]
0x18000777e  lea     rcx, [rbp+1A0h+var_1D8]
0x180007782  call    ??$wait_get@U?$IAsyncOperation@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@1@@Z
0x180007787  nop
0x180007788  cmp     [rbp+1A0h+var_208], 0
0x18000778d  jz      short loc_180007798
0x18000778f  lea     rcx, [rbp+1A0h+var_208]
0x180007793  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180007798  mov     rcx, [rbp+1A0h+var_1D8]
0x18000779c  test    rcx, rcx
0x18000779f  jz      loc_180007A13
0x1800077a5  xor     ebx, ebx
0x1800077a7  mov     [rbp+1A0h+var_208], rbx
0x1800077ab  mov     rax, [rcx]
0x1800077ae  lea     r8, [rbp+1A0h+var_208]
0x1800077b2  lea     rdx, ??$guid_v@UIModelManager2@PrivateCommon@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::PrivateCommon::IModelManager2>
0x1800077b9  mov     rax, [rax]
0x1800077bc  call    cs:__guard_dispatch_icall_fptr
0x1800077c2  mov     rsi, [rbp+1A0h+var_208]
0x1800077c6  mov     [rsp+2A0h+var_240], rsi
0x1800077cb  test    rsi, rsi
0x1800077ce  jz      loc_180007A00
0x1800077d4  lea     rcx, [rsp+2A0h+var_248]
0x1800077d9  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x1800077de  xor     edx, edx; Val
0x1800077e0  mov     r8d, 148h; Size
0x1800077e6  lea     rcx, [rbp+1A0h+var_180]; void *
0x1800077ea  call    memset
0x1800077ef  mov     rax, [r14]
0x1800077f2  test    rax, rax
0x1800077f5  jz      short loc_1800077FD
0x1800077f7  mov     rdx, [rax+10h]
0x1800077fb  jmp     short loc_180007804
0x1800077fd  lea     rdx, S2; wchar_t *
0x180007804  mov     [rbp+1A0h+var_178], ebx
0x180007807  mov     [rbp+1A0h+var_174], 0
0x18000780b  mov     [rbp+1A0h+var_138], 0
0x18000780f  mov     [rbp+1A0h+var_150], ebx
0x180007812  lea     rax, aModelcaching; "ModelCaching"
0x180007819  mov     [rbp+1A0h+var_148], rax
0x18000781d  mov     [rbp+1A0h+var_140], rbx
0x180007821  mov     [rbp+1A0h+var_130], ebx
0x180007824  xorps   xmm0, xmm0
0x180007827  movdqa  [rbp+1A0h+var_90], xmm0
0x18000782f  xorps   xmm1, xmm1
0x180007832  xor     eax, eax
0x180007834  movups  [rbp+1A0h+var_128], xmm1
0x180007838  movups  [rbp+1A0h+var_118], xmm1
0x18000783f  movups  [rbp+1A0h+var_108], xmm1
0x180007846  movups  [rbp+1A0h+var_F8], xmm1
0x18000784d  movups  [rbp+1A0h+var_E8], xmm1
0x180007854  movups  [rbp+1A0h+var_D8], xmm1
0x18000785b  movups  [rbp+1A0h+var_C8], xmm1
0x180007862  movups  [rbp+1A0h+var_B8], xmm1
0x180007869  movups  [rbp+1A0h+var_A8], xmm1
0x180007870  mov     [rbp+1A0h+var_98], rax
0x180007877  mov     [rbp+1A0h+var_80], 1
0x180007881  mov     [rbp+1A0h+var_78], rax
0x180007888  lea     rax, [rbp+1A0h+var_178]
0x18000788c  mov     [rbp+1A0h+var_70], rax
0x180007893  mov     [rbp+1A0h+var_68], rbx
0x18000789a  mov     [rbp+1A0h+var_60], rbx
0x1800078a1  lea     rax, [rbp+1A0h+var_180]
0x1800078a5  mov     [rbp+1A0h+var_58], rax
0x1800078ac  mov     [rbp+1A0h+var_50], rbx
0x1800078b3  mov     [rbp+1A0h+var_48], ebx
0x1800078b9  lea     rax, [rbp+1A0h+var_150]
0x1800078bd  mov     [rbp+1A0h+var_40], rax
0x1800078c4  lea     rax, ??_7ModelCaching@TelemetryLogger@@6B@; const TelemetryLogger::ModelCaching::`vftable'
0x1800078cb  mov     [rbp+1A0h+var_180], rax
0x1800078cf  movzx   r8d, byte ptr [r15+18h]; bool
0x1800078d4  lea     rcx, [rbp+1A0h+var_180]; this
0x1800078d8  call    ?StartActivity@ModelCaching@TelemetryLogger@@QEAAXPEB_W_N@Z; TelemetryLogger::ModelCaching::StartActivity(wchar_t const *,bool)
0x1800078dd  nop
0x1800078de  cmp     byte ptr [r15+10h], 0
0x1800078e3  jz      short loc_1800078F7
0x1800078e5  mov     rcx, [r15+8]; this
0x1800078e9  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x1800078ee  mov     rbx, rax
0x1800078f1  mov     [rbp+1A0h+pv], rax
0x1800078f5  jmp     short loc_180007917
0x1800078f7  lea     rax, S2
0x1800078fe  mov     [rbp+1A0h+var_218], rax
0x180007902  mov     [rbp+1A0h+var_210], rbx
0x180007906  lea     rdx, [rbp+1A0h+var_218]
0x18000790a  lea     rcx, [rbp+1A0h+pv]
0x18000790e  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x180007913  mov     rbx, [rbp+1A0h+pv]
0x180007917  mov     rax, [rsi]
0x18000791a  mov     rdx, r12
  ... truncated ...
```
