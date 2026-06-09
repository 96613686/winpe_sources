# InstallAppFromStoreForAllUsers(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,bool,std::chrono::duration<__int64,std::ratio<1,1>>)

- ea: `0x1800105d8`
- end: `0x1800114e9`
- name: `?InstallAppFromStoreForAllUsers@@YA?AUAppInstallResult@@V?$basic_zstring_view@_W@wil@@00_NV?$duration@_JU?$ratio@$00$00@std@@@chrono@std@@@Z`
- size: `3857`
- prototype: `__int64(__int64, __int64 *, __m128i *, __int64 *, char, ...)`
- caller_count: `1`
- callee_count: `27`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013140`

## callees

- `0x180009380`
- `0x18000bdd0`
- `0x18000beb4`
- `0x18000c3c8`
- `0x18000c4a4`
- `0x18000c5e8`
- `0x18000c6c4`
- `0x1800105d8`
- `0x1800114f0`
- `0x1800185bc`
- `0x180018778`
- `0x18001a7fc`
- `0x18002d1a4`
- `0x18002f1f0`
- `0x1800338a4`
- `0x180034a70`
- `0x180034bc4`
- `0x180035a50`
- `0x180036d78`
- `0x180036ed8`
- `0x180056119`
- `0x18005616d`
- `0x1800563c8`
- `0x180056500`
- `0x180056524`
- `0x180058abc`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800110a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800111ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800110a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800111ac`

## pseudocode

```c
__int64 InstallAppFromStoreForAllUsers(__int64 a1, __int64 *a2, __m128i *a3, __int64 *a4, char a5, ...)
{
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // r14d
  void *v12; // rcx
  int v13; // eax
  __int64 v14; // r8
  __int64 v15; // rdx
  char *v16; // rdx
  int v17; // eax
  __int64 v18; // rcx
  int v19; // r14d
  __int64 v20; // rdx
  int v21; // r14d
  void *v22; // rcx
  int v23; // eax
  __int64 v24; // rbx
  __int64 v25; // r8
  __int64 v26; // rax
  int v27; // r14d
  __int128 *v28; // rcx
  char *v29; // r9
  __int64 v30; // rdx
  __int64 v31; // rcx
  char *v32; // rdx
  void *v33; // rcx
  int v34; // eax
  __int64 v35; // rbx
  int v36; // r14d
  void *v37; // rcx
  int v38; // eax
  int v39; // eax
  int v40; // r14d
  int v41; // eax
  unsigned int v42; // r14d
  unsigned int v43; // r12d
  int v44; // eax
  int i; // eax
  int v46; // r14d
  int v47; // eax
  unsigned int v48; // r14d
  int v49; // eax
  volatile signed __int32 *v50; // r13
  const wchar_t *v51; // rdx
  __int64 v52; // rax
  size_t v53; // xmm0_8
  bool v54; // r12
  int v55; // eax
  HANDLE ProcessHeap; // rax
  __m128i *v57; // r14
  __int64 v58; // rcx
  __m128i *v59; // r13
  volatile signed __int32 *v60; // rbx
  __int128 v62; // xmm0
  char *v63; // r12
  __int64 v64; // rcx
  int v65; // eax
  __int64 v66; // r13
  __int64 v67; // r12
  __int64 v68; // rax
  bool v69; // zf
  volatile signed __int32 *v70; // rbx
  int v71; // ecx
  volatile signed __int32 *v72; // rbx
  volatile signed __int32 *v73; // rbx
  int v74; // [rsp+40h] [rbp-168h]
  __m128i *v75; // [rsp+48h] [rbp-160h] BYREF
  int v76; // [rsp+50h] [rbp-158h]
  __int64 v77; // [rsp+58h] [rbp-150h]
  __int128 v78; // [rsp+60h] [rbp-148h] BYREF
  __int128 v79; // [rsp+70h] [rbp-138h]
  __int128 v80; // [rsp+80h] [rbp-128h] BYREF
  __int128 *v81; // [rsp+98h] [rbp-110h]
  __int64 *v82; // [rsp+A0h] [rbp-108h]
  __int128 Src; // [rsp+B0h] [rbp-F8h] BYREF
  __int64 v84; // [rsp+C0h] [rbp-E8h]
  __int64 v85; // [rsp+C8h] [rbp-E0h]
  _BYTE pExceptionObject[24]; // [rsp+D8h] [rbp-D0h] BYREF
  LPVOID lpMem; // [rsp+F0h] [rbp-B8h] BYREF
  __int64 v88; // [rsp+F8h] [rbp-B0h] BYREF
  int v89; // [rsp+100h] [rbp-A8h] BYREF
  __int64 v90; // [rsp+108h] [rbp-A0h] BYREF
  void (__fastcall ***v91)(_QWORD, __int64 *, LPVOID *); // [rsp+110h] [rbp-98h] BYREF
  void (__fastcall ***v92)(_QWORD, __int64 *, LPVOID *, char *); // [rsp+118h] [rbp-90h] BYREF
  _QWORD v93[2]; // [rsp+120h] [rbp-88h] BYREF
  __int128 v94; // [rsp+130h] [rbp-78h] BYREF
  __int128 v95; // [rsp+140h] [rbp-68h] BYREF
  __int64 v96; // [rsp+158h] [rbp-50h]
  va_list va; // [rsp+1D8h] [rbp+30h] BYREF

  va_start(va, a5);
  v75 = a3;
  v77 = a1;
  v82 = a4;
  v76 = 0;
  v94 = 0;
  std::make_shared<AppInstallResultWrapper,>(&v94);
  lpMem = &qword_18009F848;
  _InterlockedIncrement64(&qword_18009F848);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory> )
  {
    `winrt::Windows::Management::Deployment::PackageManager::PackageManager'::`1'::_lambda_15__::operator()(
      v9,
      v93,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>);
    v11 = 64;
    _InterlockedAdd64(&qword_18009F848, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_18009F848, 0xFFFFFFFFFFFFFFFFuLL);
    lpMem = `winrt::Windows::Management::Deployment::PackageManager::PackageManager'::`1'::_lambda_15__::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Management::Deployment::PackageManager (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      v9,
      v93,
      &lpMem);
    v11 = 64;
  }
  if ( a5 )
  {
    if ( v93[0] )
    {
      lpMem = 0;
      v13 = (**(__int64 (__fastcall ***)(_QWORD, __int64 *, LPVOID *))v93[0])(
              v93[0],
              winrt::impl::guid_v<winrt::Windows::Management::Deployment::IPackageManager9>,
              &lpMem);
      if ( v13 < 0 )
        winrt::throw_hresult((unsigned int)v13);
      v12 = lpMem;
    }
    else
    {
      v12 = 0;
    }
    lpMem = v12;
    v11 = 49216;
    v14 = *a4;
    v15 = *((unsigned int *)a4 + 2);
    if ( (_DWORD)v15 )
    {
      if ( *(_WORD *)(v14 + 2 * v15) )
        abort();
      DWORD2(v78) = 1;
      HIDWORD(v78) = v15;
      *((_QWORD *)&v79 + 1) = v14;
      v16 = (char *)&v78 + 8;
    }
    else
    {
      v16 = 0;
    }
    *(_QWORD *)&v78 = v16;
    v17 = (*(__int64 (__fastcall **)(void *, char *, __int64))(*(_QWORD *)v12 + 88LL))(v12, v16, 1);
    if ( v17 < 0 )
      winrt::throw_hresult((unsigned int)v17);
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
  }
  lpMem = &qword_18009F7E8;
  _InterlockedIncrement64(&qword_18009F7E8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory> )
  {
    `winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager::AppInstallManager'::`1'::_lambda_32__::operator()(
      v10,
      &v92,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>);
    v19 = v11 | 0x80;
    _InterlockedAdd64(&qword_18009F7E8, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_18009F7E8, 0xFFFFFFFFFFFFFFFFuLL);
    lpMem = `winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager::AppInstallManager'::`1'::_lambda_32__::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      v10,
      &v92,
      &lpMem);
    v19 = v11 | 0x80;
  }
  lpMem = &qword_18009F7C8;
  _InterlockedIncrement64(&qword_18009F7C8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallOptions,winrt::Windows::Foundation::IActivationFactory> )
  {
    `winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallOptions::AppInstallOptions'::`1'::_lambda_33__::operator()(
      v18,
      &v91,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallOptions,winrt::Windows::Foundation::IActivationFactory>);
    v21 = v19 | 0x100;
    _InterlockedAdd64(&qword_18009F7C8, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_18009F7C8, 0xFFFFFFFFFFFFFFFFuLL);
    lpMem = `winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallOptions::AppInstallOptions'::`1'::_lambda_33__::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallOptions,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallOptions (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      v18,
      &v91,
      &lpMem);
    v21 = v19 | 0x100;
  }
  if ( v91 )
  {
    lpMem = 0;
    (**v91)(
      v91,
      winrt::impl::guid_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions2>,
      &lpMem);
    v22 = lpMem;
  }
  else
  {
    v22 = 0;
  }
  lpMem = v22;
  LOBYTE(v20) = 1;
  v23 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)v22 + 136LL))(v22, v20);
  if ( v23 < 0 )
    winrt::throw_hresult((unsigned int)v23);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
  v24 = *a2;
  Src = 0;
  v84 = 0;
  v85 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&Src);
  v25 = -1;
  do
    ++v25;
  while ( *(_WORD *)(v24 + 2 * v25) );
  v26 = std::wstring::append(&Src);
  v78 = 0;
  v79 = 0u;
  v78 = *(_OWORD *)v26;
  v79 = *(_OWORD *)(v26 + 16);
  *(_QWORD *)(v26 + 16) = 0;
  *(_QWORD *)(v26 + 24) = 7;
  *(_WORD *)v26 = 0;
  v27 = v21 | 0x200;
  v28 = &v78;
  if ( *((_QWORD *)&v79 + 1) > 7u )
    v28 = (__int128 *)v78;
  if ( (_DWORD)v79 )
  {
    if ( *((_WORD *)v28 + (unsigned int)v79) )
      goto LABEL_188;
    DWORD2(v80) = 1;
    HIDWORD(v80) = v79;
    v81 = v28;
    v29 = (char *)&v80 + 8;
    *(_QWORD *)&v80 = (char *)&v80 + 8;
  }
  else
  {
    v29 = 0;
    *(_QWORD *)&v80 = 0;
  }
  v30 = a3->m128i_i64[0];
  v31 = a3->m128i_u32[2];
  if ( (_DWORD)v31 )
  {
    if ( !*(_WORD *)(v30 + 2 * v31) )
    {
      DWORD2(v95) = 1;
      HIDWORD(v95) = v31;
      v96 = v30;
      v32 = (char *)&v95 + 8;
      goto LABEL_37;
    }
LABEL_188:
    abort();
  }
  v32 = 0;
LABEL_37:
  *(_QWORD *)&v95 = v32;
  v88 = 0;
  if ( v92 )
  {
    lpMem = 0;
    (**v92)(
      v92,
      winrt::impl::guid_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager6>,
      &lpMem,
      v29);
    v33 = lpMem;
    v29 = (char *)v80;
    v32 = (char *)v95;
  }
  else
  {
    v33 = 0;
  }
  lpMem = v33;
  v34 = (*(__int64 (__fastcall **)(void *, char *, _QWORD, char *, _QWORD, void (__fastcall ***)(_QWORD, __int64 *, LPVOID *), __int64 *))(*(_QWORD *)v33 + 80LL))(
          v33,
          v32,
          0,
          v29,
          0,
          v91,
          &v88);
  if ( v34 < 0 )
    winrt::throw_hresult((unsigned int)v34);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
  v35 = v88;
  v36 = v27 | 0x400;
  std::wstring::~wstring(&v78);
  std::wstring::~wstring(&Src);
  v89 = 0;
  if ( v35 )
  {
    lpMem = 0;
    (**(void (__fastcall ***)(__int64, const char *, LPVOID *))v35)(v35, "6", &lpMem);
    v37 = lpMem;
  }
  else
  {
    v37 = 0;
  }
  lpMem = v37;
  v38 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)v37 + 56LL))(v37, &v89);
  if ( v38 < 0 )
    winrt::throw_hresult((unsigned int)v38);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
  v39 = v89;
  if ( !v89 )
  {
    v39 = winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>>>(&v88);
    v35 = v88;
  }
  if ( v39 == 2 )
  {
    winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject);
    throw (winrt::hresult_canceled *)pExceptionObject;
  }
  v90 = 0;
  v40 = v36 | 0x2000;
  v76 = v40;
  v41 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v35 + 64LL))(v35, &v90);
  if ( v41 < 0 )
    winrt::throw_hresult((unsigned int)v41);
  v42 = v40 & 0xFFFFC7FF | 0x1800;
  v80 = 0;
  v43 = 0;
  v74 = 0;
  v89 = 0;
  v44 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v90 + 56LL))(v90, &v89);
  if ( v44 < 0 )
    winrt::throw_hresult((unsigned int)v44);
  for ( i = v89; ; i = v89 )
  {
    if ( v43 == i )
    {
      v57 = (__m128i *)*((_QWORD *)&v80 + 1);
      v59 = (__m128i *)v80;
      goto LABEL_78;
    }
    *(_QWORD *)&v95 = 0;
    v46 = v42 | 8;
    v76 = v46;
    v47 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v90 + 48LL))(v90, v43, &v95);
    if ( v47 < 0 )
      winrt::throw_hresult((unsigned int)v47);
    v48 = v46 & 0xFFFFFFF3 | 4;
    lpMem = 0;
    v49 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)v95 + 48LL))(v95, &lpMem);
    if ( v49 < 0 )
      winrt::throw_hresult((unsigned int)v49);
    v42 = v48 | 2;
    v50 = (volatile signed __int32 *)lpMem;
    if ( lpMem )
      v51 = (const wchar_t *)*((_QWORD *)lpMem + 2);
    else
      v51 = &S2;
    v52 = -1;
    do
      ++v52;
    while ( v51[v52] );
    v53 = _mm_srli_si128(*v75, 8).m128i_u64[0];
    if ( v53 == v52 )
    {
      if ( v53 )
        v54 = wmemcmp((const wchar_t *)v75->m128i_i64[0], v51, v53) == 0;
      else
        v54 = 1;
    }
    else
    {
      v54 = 0;
    }
    if ( v50 )
    {
      v55 = _InterlockedDecrement(v50 + 6);
      if ( v55 )
      {
        if ( v55 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, lpMem);
      }
    }
    if ( v54 )
      break;
    if ( (_QWORD)v95 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v95);
    v43 = ++v74;
  }
  v57 = (__m128i *)operator new(0x18u);
  v75 = v57;
  v57->m128i_i32[2] = 1;
  v57->m128i_i32[3] = 1;
  v57->m128i_i64[0] = (__int64)&std::_Ref_count_obj2<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::`vftable';
  v58 = v95;
  v57[1].m128i_i64[0] = v95;
  if ( v58 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 8LL))(v58);
  v59 = v57 + 1;
  *(_QWORD *)&v80 = v57 + 1;
  *((_QWORD *)&v80 + 1) = v57;
  if ( (_QWORD)v95 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v95);
LABEL_78:
  if ( v59 )
  {
    v62 = 0;
    if ( *((_QWORD *)&v94 + 1) )
    {
      v62 = v94;
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v94 + 1) + 12LL));
    }
    v95 = v62;
    v78 = 0;
    lpMem = &v95;
    v63 = (char *)operator new(0x20u);
    *(_OWORD *)(v63 + 8) = v95;
    v95 = 0;
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    *((_DWORD *)v63 + 6) = 1;
    *(_QWORD *)v63 = off_180066440;
    lpMem = v63;
    v64 = *((_QWORD *)&v95 + 1);
    if ( *((_QWORD *)&v95 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v95 + 1) + 12LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 8LL))(v64);
    }
    v75 = 0;
    v65 = (*(__int64 (__fastcall **)(__int64, char *, __m128i **))(*(_QWORD *)v59->m128i_i64[0] + 128LL))(
            v59->m128i_i64[0],
            v63,
            &v75);
    if ( v65 < 0 )
      winrt::throw_hresult((unsigned int)v65);
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
    v66 = v94 + 80;
    v95 = (unsigned __int64)(v94 + 80);
    if ( (unsigned int)mtx_do_lock(v94 + 80) )
      std::_Throw_Cpp_error(5);
    if ( *(_DWORD *)(v66 + 76) == 0x7FFFFFFF )
    {
      *(_DWORD *)(v66 + 76) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    BYTE8(v95) = 1;
    v67 = v94;
    v68 = std::_To_absolute_time<__int64,std::ratio<1,1>>(&lpMem, va);
    v75 = (__m128i *)v68;
    if ( *(_BYTE *)v94 )
      goto LABEL_132;
    while ( (unsigned int)std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(
                            v67 + 8,
                            &v95,
                            v68) != 1 )
    {
      v68 = (__int64)v75;
      if ( *(_BYTE *)v94 )
        goto LABEL_132;
    }
    if ( *(_BYTE *)v94 )
    {
LABEL_132:
      v69 = (*(_DWORD *)(v66 + 76))-- == 1;
      if ( v69 )
      {
        *(_DWORD *)(v66 + 72) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)(v66 + 16));
      }
      v71 = *(_DWORD *)(v94 + 4);
      if ( v71 >= 0 )
      {
        if ( v57 )
        {
          if ( _InterlockedExchangeAdd(&v57->m128i_i32[2], 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(__m128i *))v57->m128i_i64[0])(v57);
            if ( _InterlockedExchangeAdd(&v57->m128i_i32[3], 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(__m128i *))(v57->m128i_i64[0] + 8))(v57);
          }
        }
        if ( v90 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v90);
        if ( v35 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v88);
        if ( v91 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v91);
        if ( v92 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v92);
        if ( v93[0] )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v93);
        *(_QWORD *)a1 = 0;
        *(_QWORD *)(a1 + 8) = 0;
        *(_DWORD *)(a1 + 16) = 0;
        *(_DWORD *)(a1 + 20) = 256;
        v73 = (volatile signed __int32 *)*((_QWORD *)&v94 + 1);
        if ( *((_QWORD *)&v94 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v94 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v73)(v73);
            if ( _InterlockedExchangeAdd(v73 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v73 + 8LL))(v73);
          }
        }
        return a1;
      }
      else
      {
        *(_DWORD *)a1 = v71;
        *(_DWORD *)(a1 + 4) = 0;
        *(_QWORD *)(a1 + 8) = 0;
        *(_DWORD *)(a1 + 16) = 2;
        *(_DWORD *)(a1 + 20) = 1;
        if ( v57 )
        {
          if ( _InterlockedExchangeAdd(&v57->m128i_i32[2], 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(__m128i *))v57->m128i_i64[0])(v57);
            if ( _InterlockedExchangeAdd(&v57->m128i_i32[3], 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(__m128i *))(v57->m128i_i64[0] + 8))(v57);
          }
        }
        if ( v90 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v90);
        if ( v35 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v88);
        if ( v91 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v91);
        if ( v92 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v92);
        if ( v93[0] )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v93);
        v72 = (volatile signed __int32 *)*((_QWORD *)&v94 + 1);
        if ( *((_QWORD *)&v94 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v94 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v72)(v72);
            if ( _InterlockedExchangeAdd(v72 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v72 + 8LL))(v72);
          }
        }
        return a1;
      }
    }
    else
    {
      *(_DWORD *)a1 = -2145082834;
      *(_DWORD *)(a1 + 4) = 0;
      *(_QWORD *)(a1 + 8) = 0;
      *(_DWORD *)(a1 + 16) = 6;
      *(_DWORD *)(a1 + 20) = 1;
      v69 = (*(_DWORD *)(v66 + 76))-- == 1;
      if ( v69 )
      {
        *(_DWORD *)(v66 + 72) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)(v66 + 16));
      }
      if ( v57 )
      {
        if ( _InterlockedExchangeAdd(&v57->m128i_i32[2], 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(__m128i *))v57->m128i_i64[0])(v57);
          if ( _InterlockedExchangeAdd(&v57->m128i_i32[3], 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(__m128i *))(v57->m128i_i64[0] + 8))(v57);
        }
      }
      if ( v90 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v90);
      if ( v35 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v88);
      if ( v91 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v91);
      if ( v92 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v92);
      if ( v93[0] )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v93);
      v70 = (volatile signed __int32 *)*((_QWORD *)&v94 + 1);
      if ( *((_QWORD *)&v94 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v94 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v70)(v70);
          if ( _InterlockedExchangeAdd(v70 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v70 + 8LL))(v70);
        }
      }
      return a1;
    }
  }
  else
  {
    *(_DWORD *)a1 = -2147009295;
    *(_DWORD *)(a1 + 4) = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 16) = 9;
    *(_DWORD *)(a1 + 20) = 1;
    if ( v57 )
    {
      if ( _InterlockedExchangeAdd(&v57->m128i_i32[2], 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(__m128i *))v57->m128i_i64[0])(v57);
        if ( _InterlockedExchangeAdd(&v57->m128i_i32[3], 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(__m128i *))(v57->m128i_i64[0] + 8))(v57);
      }
    }
    if ( v90 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v90);
    if ( v35 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v88);
    if ( v91 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v91);
    if ( v92 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v92);
    if ( v93[0] )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v93);
    v60 = (volatile signed __int32 *)*((_QWORD *)&v94 + 1);
    if ( *((_QWORD *)&v94 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v94 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v60)(v60);
      if ( _InterlockedExchangeAdd(v60 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v60 + 8LL))(v60);
    }
    return a1;
  }
}

```

## disassembly

```asm
0x1800105d8  mov     r11, rsp
0x1800105db  push    rbx
0x1800105dc  push    rsi
0x1800105dd  push    rdi
0x1800105de  push    r12
0x1800105e0  push    r13
0x1800105e2  push    r14
0x1800105e4  push    r15
0x1800105e6  sub     rsp, 170h
0x1800105ed  mov     rax, cs:__security_cookie
0x1800105f4  xor     rax, rsp
0x1800105f7  mov     [rsp+1A8h+var_48], rax
0x1800105ff  mov     rbx, r9
0x180010602  mov     r13, r8
0x180010605  mov     [rsp+1A8h+var_160], r8
0x18001060a  mov     r12, rdx
0x18001060d  mov     r15, rcx
0x180010610  mov     [rsp+1A8h+var_150], rcx
0x180010615  mov     [rsp+1A8h+var_108], rbx
0x18001061d  xor     edi, edi
0x18001061f  mov     [rsp+1A8h+var_158], edi
0x180010623  xorps   xmm0, xmm0
0x180010626  movups  xmmword ptr [r11-78h], xmm0
0x18001062b  lea     rcx, [r11-78h]
0x18001062f  call    ??$make_shared@UAppInstallResultWrapper@@$$V@std@@YA?AV?$shared_ptr@UAppInstallResultWrapper@@@0@XZ; std::make_shared<AppInstallResultWrapper,>(void)
0x180010634  nop
0x180010635  lea     rax, qword_18009F848
0x18001063c  mov     [rsp+1A8h+lpMem], rax
0x180010644  lock inc cs:qword_18009F848
0x18001064c  cmp     cs:??$factory_cache_entry_v@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, rdi; factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>
0x180010653  jz      short loc_18001067B
0x180010655  lea     r8, ??$factory_cache_entry_v@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>
0x18001065c  lea     rdx, [rsp+1A8h+var_88]
0x180010664  call    ??R_lambda_15__@?0???0PackageManager@Deployment@Management@Windows@winrt@@QEAA@XZ@QEBA@AEBUIActivationFactory@Foundation@45@@Z; `winrt::Windows::Management::Deployment::PackageManager::PackageManager(void)'::`1'::_lambda_15__::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x180010669  lea     r14d, [rdi+40h]
0x18001066d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180010671  lock add cs:qword_18009F848, rsi
0x180010679  jmp     short loc_1800106AF
0x18001067b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001067f  lock add cs:qword_18009F848, rsi
0x180010687  lea     rax, ?_lambda_invoker_cdecl_@_lambda_15__@?0???0PackageManager@Deployment@Management@Windows@winrt@@QEAA@XZ@SA@AEBUIActivationFactory@Foundation@56@@Z; `winrt::Windows::Management::Deployment::PackageManager::PackageManager(void)'::`1'::_lambda_15__::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x18001068e  mov     [rsp+1A8h+lpMem], rax
0x180010696  lea     r8, [rsp+1A8h+lpMem]
0x18001069e  lea     rdx, [rsp+1A8h+var_88]
0x1800106a6  call    ??$call@P6A?AUPackageManager@Deployment@Management@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUPackageManager@Deployment@Management@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x1800106ab  lea     r14d, [rsi+41h]
0x1800106af  cmp     [rsp+1A8h+arg_20], dil
0x1800106b7  jz      loc_18001076B
0x1800106bd  mov     rcx, [rsp+1A8h+var_88]
0x1800106c5  test    rcx, rcx
0x1800106c8  jnz     short loc_1800106CF
0x1800106ca  mov     rcx, rdi
0x1800106cd  jmp     short loc_180010701
0x1800106cf  mov     [rsp+1A8h+lpMem], rdi
0x1800106d7  mov     rax, [rcx]
0x1800106da  lea     r8, [rsp+1A8h+lpMem]
0x1800106e2  lea     rdx, ??$guid_v@UIPackageManager9@Deployment@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Deployment::IPackageManager9>
0x1800106e9  mov     rax, [rax]
0x1800106ec  call    _guard_dispatch_icall
0x1800106f1  test    eax, eax
0x1800106f3  js      loc_18001144A
0x1800106f9  mov     rcx, [rsp+1A8h+lpMem]
0x180010701  mov     [rsp+1A8h+lpMem], rcx
0x180010709  mov     r14d, 0C040h
0x18001070f  mov     r8, [rbx]
0x180010712  mov     edx, [rbx+8]
0x180010715  test    edx, edx
0x180010717  jnz     short loc_18001071E
0x180010719  mov     rdx, rdi
0x18001071c  jmp     short loc_18001073F
0x18001071e  cmp     [r8+rdx*2], di
0x180010723  jnz     loc_180011452
0x180010729  mov     dword ptr [rsp+1A8h+var_148+8], 1
0x180010731  mov     dword ptr [rsp+1A8h+var_148+0Ch], edx
0x180010735  mov     qword ptr [rsp+1A8h+var_138+8], r8
0x18001073a  lea     rdx, [rsp+1A8h+var_148+8]
0x18001073f  mov     qword ptr [rsp+1A8h+var_148], rdx
0x180010744  mov     rax, [rcx]
0x180010747  mov     r8d, 1
0x18001074d  mov     rax, [rax+58h]
0x180010751  call    _guard_dispatch_icall
0x180010756  test    eax, eax
0x180010758  js      loc_180011458
0x18001075e  lea     rcx, [rsp+1A8h+lpMem]
0x180010766  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001076b  lea     rax, qword_18009F7E8
0x180010772  mov     [rsp+1A8h+lpMem], rax
0x18001077a  lock inc cs:qword_18009F7E8
0x180010782  cmp     cs:??$factory_cache_entry_v@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@3U?$factory_cache_entry@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@12@A, rdi; factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>
0x180010789  jz      short loc_1800107AE
0x18001078b  lea     r8, ??$factory_cache_entry_v@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@3U?$factory_cache_entry@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@12@A; factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>
0x180010792  lea     rdx, [rsp+1A8h+var_90]
0x18001079a  call    ??R_lambda_32__@?0???0AppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@QEAA@XZ@QEBA@AEBUIActivationFactory@Foundation@67@@Z; `winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager::AppInstallManager(void)'::`1'::_lambda_32__::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x18001079f  bts     r14d, 7
0x1800107a4  lock add cs:qword_18009F7E8, rsi
0x1800107ac  jmp     short loc_1800107DF
0x1800107ae  lock add cs:qword_18009F7E8, rsi
0x1800107b6  lea     rax, ?_lambda_invoker_cdecl_@_lambda_32__@?0???0AppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@QEAA@XZ@SA@AEBUIActivationFactory@Foundation@78@@Z; `winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager::AppInstallManager(void)'::`1'::_lambda_32__::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x1800107bd  mov     [rsp+1A8h+lpMem], rax
0x1800107c5  lea     r8, [rsp+1A8h+lpMem]
0x1800107cd  lea     rdx, [rsp+1A8h+var_90]
0x1800107d5  call    ??$call@P6A?AUAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@AEBUIActivationFactory@Foundation@67@@Z@?$factory_cache_entry@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@QEAA?A_P$$QEAP6A?AUAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@2@AEBUIActivationFactory@Foundation@82@@Z@Z
0x1800107da  bts     r14d, 7
0x1800107df  lea     rax, qword_18009F7C8
0x1800107e6  mov     [rsp+1A8h+lpMem], rax
0x1800107ee  lock inc cs:qword_18009F7C8
0x1800107f6  cmp     cs:??$factory_cache_entry_v@UAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@3U?$factory_cache_entry@UAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@12@A, rdi; factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallOptions,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallOptions,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallOptions,winrt::Windows::Foundation::IActivationFactory>
0x1800107fd  jz      short loc_180010822
0x1800107ff  lea     r8, ??$factory_cache_entry_v@UAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@3U?$factory_cache_entry@UAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@12@A; factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallOptions,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallOptions,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallOptions,winrt::Windows::Foundation::IActivationFactory>
0x180010806  lea     rdx, [rsp+1A8h+var_98]
0x18001080e  call    ??R_lambda_33__@?0???0AppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@QEAA@XZ@QEBA@AEBUIActivationFactory@Foundation@67@@Z; `winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallOptions::AppInstallOptions(void)'::`1'::_lambda_33__::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x180010813  bts     r14d, 8
0x180010818  lock add cs:qword_18009F7C8, rsi
0x180010820  jmp     short loc_180010853
0x180010822  lock add cs:qword_18009F7C8, rsi
0x18001082a  lea     rax, ?_lambda_invoker_cdecl_@_lambda_33__@?0???0AppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@QEAA@XZ@SA@AEBUIActivationFactory@Foundation@78@@Z; `winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallOptions::AppInstallOptions(void)'::`1'::_lambda_33__::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x180010831  mov     [rsp+1A8h+lpMem], rax
0x180010839  lea     r8, [rsp+1A8h+lpMem]
0x180010841  lea     rdx, [rsp+1A8h+var_98]
0x180010849  call    ??$call@P6A?AUAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@AEBUIActivationFactory@Foundation@67@@Z@?$factory_cache_entry@UAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@QEAA?A_P$$QEAP6A?AUAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@2@AEBUIActivationFactory@Foundation@82@@Z@Z
0x18001084e  bts     r14d, 8
0x180010853  mov     rcx, [rsp+1A8h+var_98]
0x18001085b  test    rcx, rcx
0x18001085e  jnz     short loc_180010865
0x180010860  mov     rcx, rdi
0x180010863  jmp     short loc_18001088F
0x180010865  mov     [rsp+1A8h+lpMem], rdi
0x18001086d  mov     rax, [rcx]
0x180010870  lea     r8, [rsp+1A8h+lpMem]
0x180010878  lea     rdx, ??$guid_v@UIAppInstallOptions2@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions2>
0x18001087f  mov     rax, [rax]
0x180010882  call    _guard_dispatch_icall
0x180010887  mov     rcx, [rsp+1A8h+lpMem]
0x18001088f  mov     [rsp+1A8h+lpMem], rcx
0x180010897  mov     rax, [rcx]
0x18001089a  mov     dl, 1
0x18001089c  mov     rax, [rax+88h]
0x1800108a3  call    _guard_dispatch_icall
0x1800108a8  test    eax, eax
0x1800108aa  js      loc_180011460
0x1800108b0  lea     rcx, [rsp+1A8h+lpMem]
0x1800108b8  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800108bd  mov     rbx, [r12]
0x1800108c1  xorps   xmm0, xmm0
0x1800108c4  movups  [rsp+1A8h+Src], xmm0
0x1800108cc  mov     [rsp+1A8h+var_E8], rdi
0x1800108d4  mov     [rsp+1A8h+var_E0], rdi
0x1800108dc  mov     r8d, 16h
0x1800108e2  lea     rdx, aUoExpeditedsto; "UO_ExpeditedStoreWork_"
0x1800108e9  lea     rcx, [rsp+1A8h+Src]
0x1800108f1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800108f6  nop
0x1800108f7  mov     r8, rsi
0x1800108fa  inc     r8
0x1800108fd  cmp     [rbx+r8*2], di
0x180010902  jnz     short loc_1800108FA
0x180010904  mov     rdx, rbx
0x180010907  lea     rcx, [rsp+1A8h+Src]; Src
0x18001090f  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x180010914  xorps   xmm0, xmm0
0x180010917  movups  [rsp+1A8h+var_148], xmm0
0x18001091c  mov     qword ptr [rsp+1A8h+var_138], rdi
0x180010921  mov     qword ptr [rsp+1A8h+var_138+8], rdi
0x180010926  movups  xmm0, xmmword ptr [rax]
0x180010929  movups  [rsp+1A8h+var_148], xmm0
0x18001092e  movups  xmm1, xmmword ptr [rax+10h]
0x180010932  movups  [rsp+1A8h+var_138], xmm1
0x180010937  mov     [rax+10h], rdi
0x18001093b  mov     qword ptr [rax+18h], 7
0x180010943  mov     [rax], di
0x180010946  bts     r14d, 9
0x18001094b  lea     rcx, [rsp+1A8h+var_148]
0x180010950  cmp     qword ptr [rsp+1A8h+var_138+8], 7
0x180010956  cmova   rcx, qword ptr [rsp+1A8h+var_148]
0x18001095c  mov     edx, dword ptr [rsp+1A8h+var_138]
0x180010960  test    edx, edx
0x180010962  jnz     short loc_180010971
0x180010964  mov     r9, rdi
0x180010967  mov     qword ptr [rsp+1A8h+var_128], rdi
0x18001096f  jmp     short loc_1800109A5
0x180010971  cmp     [rcx+rdx*2], di
0x180010975  jnz     loc_1800114E2
0x18001097b  mov     dword ptr [rsp+1A8h+var_128+8], 1
0x180010986  mov     dword ptr [rsp+1A8h+var_128+0Ch], edx
0x18001098d  mov     [rsp+1A8h+var_110], rcx
0x180010995  lea     r9, [rsp+1A8h+var_128+8]
0x18001099d  mov     qword ptr [rsp+1A8h+var_128], r9
0x1800109a5  mov     rdx, [r13+0]
0x1800109a9  mov     ecx, [r13+8]
0x1800109ad  test    ecx, ecx
0x1800109af  jnz     short loc_1800109B6
0x1800109b1  mov     rdx, rdi
0x1800109b4  jmp     short loc_1800109E2
0x1800109b6  cmp     [rdx+rcx*2], di
0x1800109ba  jnz     loc_1800114E2
0x1800109c0  mov     dword ptr [rsp+1A8h+var_68+8], 1
0x1800109cb  mov     dword ptr [rsp+1A8h+var_68+0Ch], ecx
0x1800109d2  mov     [rsp+1A8h+var_50], rdx
0x1800109da  lea     rdx, [rsp+1A8h+var_68+8]
0x1800109e2  mov     qword ptr [rsp+1A8h+var_68], rdx
0x1800109ea  mov     [rsp+1A8h+var_B0], rdi
0x1800109f2  mov     rcx, [rsp+1A8h+var_90]
0x1800109fa  test    rcx, rcx
0x1800109fd  jnz     short loc_180010A04
0x1800109ff  mov     rcx, rdi
0x180010a02  jmp     short loc_180010A3E
0x180010a04  mov     [rsp+1A8h+lpMem], rdi
0x180010a0c  mov     rax, [rcx]
0x180010a0f  lea     r8, [rsp+1A8h+lpMem]
0x180010a17  lea     rdx, ??$guid_v@UIAppInstallManager6@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager6>
0x180010a1e  mov     rax, [rax]
0x180010a21  call    _guard_dispatch_icall
0x180010a26  mov     rcx, [rsp+1A8h+lpMem]
0x180010a2e  mov     r9, qword ptr [rsp+1A8h+var_128]
0x180010a36  mov     rdx, qword ptr [rsp+1A8h+var_68]
0x180010a3e  mov     [rsp+1A8h+lpMem], rcx
0x180010a46  mov     r8, [rsp+1A8h+var_98]
0x180010a4e  mov     rax, [rcx]
0x180010a51  lea     r10, [rsp+1A8h+var_B0]
0x180010a59  mov     [rsp+1A8h+var_178], r10
0x180010a5e  mov     [rsp+1A8h+var_180], r8
0x180010a63  mov     [rsp+1A8h+var_188], rdi
0x180010a68  xor     r8d, r8d
0x180010a6b  mov     rax, [rax+50h]
0x180010a6f  call    _guard_dispatch_icall
0x180010a74  test    eax, eax
0x180010a76  js      loc_180011468
0x180010a7c  lea     rcx, [rsp+1A8h+lpMem]
0x180010a84  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010a89  mov     rbx, [rsp+1A8h+var_B0]
0x180010a91  mov     [rsp+1A8h+var_B0], rbx
0x180010a99  bts     r14d, 0Ah
0x180010a9e  lea     rcx, [rsp+1A8h+var_148]; void *
0x180010aa3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010aa8  nop
0x180010aa9  lea     rcx, [rsp+1A8h+Src]; void *
0x180010ab1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010ab6  mov     [rsp+1A8h+var_A8], edi
0x180010abd  test    rbx, rbx
0x180010ac0  jnz     short loc_180010AC7
0x180010ac2  mov     rcx, rdi
0x180010ac5  jmp     short loc_180010AF4
0x180010ac7  mov     [rsp+1A8h+lpMem], rdi
0x180010acf  mov     rax, [rbx]
0x180010ad2  lea     r8, [rsp+1A8h+lpMem]
0x180010ada  lea     rdx, ??$guid_v@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; "6"
0x180010ae1  mov     rcx, rbx
0x180010ae4  mov     rax, [rax]
0x180010ae7  call    _guard_dispatch_icall
0x180010aec  mov     rcx, [rsp+1A8h+lpMem]
0x180010af4  mov     [rsp+1A8h+lpMem], rcx
0x180010afc  mov     rax, [rcx]
0x180010aff  lea     rdx, [rsp+1A8h+var_A8]
0x180010b07  mov     rax, [rax+38h]
0x180010b0b  call    _guard_dispatch_icall
0x180010b10  test    eax, eax
0x180010b12  js      loc_180011470
0x180010b18  lea     rcx, [rsp+1A8h+lpMem]
0x180010b20  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010b25  mov     eax, [rsp+1A8h+var_A8]
0x180010b2c  test    eax, eax
0x180010b2e  jnz     short loc_180010B45
0x180010b30  lea     rcx, [rsp+1A8h+var_B0]
0x180010b38  call    ??$wait_for_completed@U?$IAsyncOperation@U?$IVectorView@UAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@U?$IVectorView@UAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@Foundation@Windows@1@I@Z
0x180010b3d  mov     rbx, [rsp+1A8h+var_B0]
0x180010b45  cmp     eax, 2
0x180010b48  jz      loc_180011478
0x180010b4e  mov     [rsp+1A8h+var_A0], rdi
0x180010b56  bts     r14d, 0Dh
0x180010b5b  mov     [rsp+1A8h+var_158], r14d
0x180010b60  mov     rax, [rbx]
0x180010b63  lea     rdx, [rsp+1A8h+var_A0]
0x180010b6b  mov     rcx, rbx
0x180010b6e  mov     rax, [rax+40h]
0x180010b72  call    _guard_dispatch_icall
0x180010b77  test    eax, eax
0x180010b79  js      loc_18001149A
0x180010b7f  btr     r14d, 0Dh
0x180010b84  or      r14d, 1800h
0x180010b8b  xorps   xmm1, xmm1
0x180010b8e  movdqu  [rsp+1A8h+var_128], xmm1
0x180010b97  mov     r12d, edi
0x180010b9a  mov     [rsp+1A8h+var_168], edi
0x180010b9e  mov     [rsp+1A8h+var_A8], edi
0x180010ba5  mov     rcx, [rsp+1A8h+var_A0]
0x180010bad  mov     rax, [rcx]
0x180010bb0  lea     rdx, [rsp+1A8h+var_A8]
0x180010bb8  mov     rax, [rax+38h]
0x180010bbc  call    _guard_dispatch_icall
0x180010bc1  test    eax, eax
0x180010bc3  js      loc_1800114A2
0x180010bc9  mov     eax, [rsp+1A8h+var_A8]
0x180010bd0  mov     [rsp+1A8h+var_A8], eax
0x180010bd7  cmp     r12d, eax
0x180010bda  jz      loc_180010D98
0x180010be0  mov     qword ptr [rsp+1A8h+var_68], rdi
0x180010be8  or      r14d, 8
0x180010bec  mov     [rsp+1A8h+var_158], r14d
0x180010bf1  mov     rcx, [rsp+1A8h+var_A0]
0x180010bf9  mov     rax, [rcx]
  ... truncated ...
```
