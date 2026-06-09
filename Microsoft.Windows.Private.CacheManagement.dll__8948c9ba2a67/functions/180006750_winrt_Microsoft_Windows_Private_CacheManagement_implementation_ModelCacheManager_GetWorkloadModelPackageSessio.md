# winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::GetWorkloadModelPackageSessionClassNames(winrt::hstring const &)

- ea: `0x180006750`
- end: `0x180007188`
- name: `?GetWorkloadModelPackageSessionClassNames@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@AEAA?AV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@AEBUhstring@7@@Z`
- size: `2616`
- prototype: `winrt::impl *__fastcall(__int64, winrt::impl *, const wchar_t **)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180007410`

## callees

- `0x180003840`
- `0x180003ee0`
- `0x180004c30`
- `0x180004e10`
- `0x180006750`
- `0x180007190`
- `0x180007330`
- `0x18000a230`
- `0x18000f430`
- `0x180011e70`
- `0x1800127e0`
- `0x180012f10`
- `0x180016298`
- `0x18001629e`
- `0x1800162c2`
- `0x1800181b0`
- `0x18001cdf0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006e72`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006e79`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006ff2`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180007108`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006e72`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006e79`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006ff2`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180007108`

## pseudocode

```c
winrt::impl *__fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::GetWorkloadModelPackageSessionClassNames(
        __int64 a1,
        winrt::impl *a2,
        const wchar_t **a3)
{
  winrt::impl *v4; // r15
  int v5; // eax
  const wchar_t **v6; // rbx
  int v7; // r12d
  int v8; // r12d
  int v9; // eax
  const wchar_t **v10; // rcx
  unsigned int v11; // r12d
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // esi
  __int64 v15; // rdx
  int v16; // r12d
  int v17; // eax
  char v18; // di
  int v19; // eax
  int v20; // r12d
  int v21; // eax
  unsigned int v22; // r12d
  int v23; // eax
  int v24; // r12d
  char v25; // bl
  unsigned int v26; // r8d
  char v27; // bl
  unsigned int v28; // r8d
  char v29; // bl
  unsigned int v30; // r8d
  const wchar_t **v31; // r14
  const wchar_t **v32; // rbx
  int v33; // eax
  unsigned int v34; // r8d
  const wchar_t *v35; // rax
  int v36; // eax
  winrt::impl **v37; // r15
  unsigned int v38; // ecx
  winrt::impl *v39; // rdi
  volatile signed __int32 *v40; // rsi
  winrt::impl *v41; // rcx
  int v42; // eax
  volatile signed __int32 *v43; // rbx
  struct winrt::impl::hstring_header *v44; // rdx
  int v45; // eax
  HANDLE v46; // rax
  _QWORD *v47; // rsi
  int v48; // eax
  HANDLE v49; // rax
  winrt::impl **v50; // rbx
  winrt::impl *v51; // rax
  volatile signed __int32 *v52; // rdi
  winrt::impl *v53; // rcx
  int v54; // eax
  volatile signed __int32 *v55; // rbx
  struct winrt::impl::hstring_header *v56; // rdx
  int v57; // eax
  HANDLE ProcessHeap; // rax
  _QWORD *v59; // rdi
  signed __int32 v60; // r13d
  HANDLE v61; // rax
  __int64 v62; // rdx
  __int64 v63; // rcx
  __int64 v64; // rax
  int v66[2]; // [rsp+20h] [rbp-E0h] BYREF
  const wchar_t **v67; // [rsp+28h] [rbp-D8h] BYREF
  int v68; // [rsp+30h] [rbp-D0h]
  const wchar_t *v69; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v70[2]; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v71; // [rsp+50h] [rbp-B0h]
  LPVOID p_pv; // [rsp+58h] [rbp-A8h] BYREF
  int v73; // [rsp+60h] [rbp-A0h] BYREF
  winrt::impl *v74; // [rsp+68h] [rbp-98h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp-90h] BYREF
  winrt::impl *v76; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v77[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v78[4]; // [rsp+90h] [rbp-70h] BYREF
  int v79[2]; // [rsp+B0h] [rbp-50h] BYREF
  const wchar_t **v80; // [rsp+B8h] [rbp-48h] BYREF
  winrt::impl *v81; // [rsp+C0h] [rbp-40h] BYREF
  winrt::impl *v82; // [rsp+C8h] [rbp-38h] BYREF
  winrt::impl *v83; // [rsp+D0h] [rbp-30h] BYREF
  winrt::impl *v84; // [rsp+D8h] [rbp-28h] BYREF
  const wchar_t **v85; // [rsp+E0h] [rbp-20h] BYREF
  void (__fastcall ***v86)(_QWORD, __int64 *, int *); // [rsp+E8h] [rbp-18h] BYREF
  __int128 v87; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v88; // [rsp+100h] [rbp+0h]
  void (__fastcall ***v89)(_QWORD, __int64 *, int *); // [rsp+108h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v91; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v4 = a2;
  v81 = a2;
  v68 = 0;
  v69 = (const wchar_t *)qword_18002E880;
  v67 = &v69;
  p_pv = &qword_18002E748;
  _InterlockedIncrement64(&qword_18002E748);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics> )
  {
    v80 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t ***))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>
                                                                                + 48LL))(
           winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>,
           v69,
           &v80);
    if ( v5 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v5);
    }
    v6 = v80;
    *(_QWORD *)v79 = v80;
    v7 = 224;
    _InterlockedDecrement64(&qword_18002E748);
  }
  else
  {
    _InterlockedDecrement64(&qword_18002E748);
    winrt::impl::factory_cache_entry<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>::call<_lambda_cb41fde99ba74c6248b3ce76f09f9615_ &>(
      0,
      v79,
      &v67);
    v7 = 32;
    v6 = *(const wchar_t ***)v79;
  }
  v8 = v7 | 0x10;
  v80 = 0;
  v9 = (*((__int64 (__fastcall **)(const wchar_t **, const wchar_t ***))*v6 + 6))(v6, &v80);
  if ( v9 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v9);
  }
  v10 = v80;
  v85 = v80;
  v11 = v8 | 0x100;
  if ( v6 )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v79);
    v10 = v85;
  }
  LODWORD(v83) = 0;
  v12 = (*((__int64 (__fastcall **)(const wchar_t **, winrt::impl **))*v10 + 7))(v10, &v83);
  if ( v12 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v12);
  }
  v67 = a3;
  v13 = 0;
  v14 = (int)v83;
  if ( (_DWORD)v83 )
  {
    v15 = 0;
    do
    {
      *(_QWORD *)v66 = 0;
      v16 = v11 | 0x400;
      v68 = v16;
      v17 = (*((__int64 (__fastcall **)(const wchar_t **, __int64, int *))*v85 + 6))(v85, v15, v66);
      if ( v17 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v17);
      }
      v11 = v16 & 0xFFFFF9FF | 0x200;
      v18 = lambda_61d4f9a59e78ac71736878df22f486c0_::operator()(&v67, v66);
      if ( *(_QWORD *)v66 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v66);
      if ( v18 )
        break;
      v15 = ++v13;
    }
    while ( v13 != v14 );
  }
  LODWORD(v83) = 0;
  v19 = (*((__int64 (__fastcall **)(const wchar_t **, winrt::impl **))*v85 + 7))(v85, &v83);
  if ( v19 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v19);
  }
  if ( v13 == (_DWORD)v83 )
  {
    *(_QWORD *)v4 = 0;
    *((_QWORD *)v4 + 1) = 0;
    *((_QWORD *)v4 + 2) = 0;
    goto LABEL_125;
  }
  *(_QWORD *)v66 = 0;
  v20 = v11 | 0x1000;
  v68 = v20;
  v21 = (*((__int64 (__fastcall **)(const wchar_t **, _QWORD, int *))*v85 + 6))(v85, v13, v66);
  if ( v21 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v21);
  }
  v22 = v20 & 0xFFFFE7FF | 0x800;
  v80 = 0;
  v23 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t ***))(**(_QWORD **)v66 + 80LL))(*(_QWORD *)v66, &v80);
  if ( v23 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v23);
  }
  v24 = v22 | 0x2000;
  if ( *(_QWORD *)v66 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v66);
  v70[0] = 0xE00000001LL;
  v71 = L"SessionClasses";
  v69 = (const wchar_t *)v70;
  winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::TryLookup(
    &v80,
    &v89,
    &v69);
  *(_QWORD *)v79 = 0;
  v25 = winrt::Windows::Foundation::operator==(&v89, v79);
  if ( *(_QWORD *)v79 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v79);
  if ( v25 )
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x168, v26, (const char *)0x80070490LL, v66[0]);
  if ( v89 )
  {
    *(_QWORD *)v79 = 0;
    (**v89)(
      v89,
      winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>>,
      v79);
    *(_QWORD *)v66 = *(_QWORD *)v79;
  }
  else
  {
    *(_QWORD *)v66 = 0;
  }
  *(_QWORD *)v79 = 0;
  v27 = winrt::Windows::Foundation::operator==(v66, v79);
  if ( *(_QWORD *)v79 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v79);
  if ( v27 )
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x16C, v28, (const char *)0x80004005LL, v66[0]);
  v70[0] = 0xC00000001LL;
  v71 = L"SessionClass";
  v69 = (const wchar_t *)v70;
  winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::TryLookup(
    v66,
    &v86,
    &v69);
  *(_QWORD *)v79 = 0;
  v29 = winrt::Windows::Foundation::operator==(&v86, v79);
  if ( *(_QWORD *)v79 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v79);
  if ( v29 )
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x16F, v30, (const char *)0x80070490LL, v66[0]);
  v87 = 0;
  v88 = 0;
  if ( v86 )
  {
    *(_QWORD *)v79 = 0;
    (**v86)(v86, winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>, v79);
    v31 = *(const wchar_t ***)v79;
    v67 = *(const wchar_t ***)v79;
    v32 = *(const wchar_t ***)v79;
  }
  else
  {
    v31 = 0;
    v67 = 0;
    v32 = 0;
  }
  if ( !v32 )
  {
    if ( v86 )
    {
      v81 = 0;
      (**v86)(
        v86,
        winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>>,
        (int *)&v81);
      v51 = v81;
      v83 = v81;
    }
    else
    {
      v83 = 0;
      v51 = 0;
    }
    if ( !v51 )
    {
LABEL_113:
      if ( v83 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v83);
      goto LABEL_115;
    }
    v69 = L"@Name";
    v70[0] = 5;
    winrt::hstring::hstring(&p_pv, &v69);
    v52 = (volatile signed __int32 *)p_pv;
    v78[0] = p_pv;
    winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::TryLookup(
      &v83,
      v79,
      v78);
    if ( *(_QWORD *)v79
      && (v81 = 0,
          (***(void (__fastcall ****)(_QWORD, __int64 *, winrt::impl **))v79)(
            *(_QWORD *)v79,
            winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>,
            &v81),
          v53 = v81,
          (v74 = v81) != 0) )
    {
      v81 = 0;
      v54 = (*(__int64 (__fastcall **)(winrt::impl *, winrt::impl **))(*(_QWORD *)v53 + 152LL))(v53, &v81);
      if ( v54 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v54);
      }
      v55 = (volatile signed __int32 *)v81;
      v84 = v81;
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v74);
      if ( !*(_QWORD *)v79 )
        goto LABEL_101;
    }
    else
    {
      v69 = &S2;
      v70[0] = 0;
      winrt::hstring::hstring(&v84, &v69);
      v55 = (volatile signed __int32 *)v84;
      if ( !*(_QWORD *)v79 )
      {
LABEL_101:
        if ( v52 )
        {
          v57 = _InterlockedDecrement(v52 + 6);
          if ( v57 )
          {
            if ( v57 < 0 )
              abort();
          }
          else
          {
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v52);
          }
        }
        if ( v55 )
        {
          v59 = (_QWORD *)*((_QWORD *)&v87 + 1);
          if ( *((_QWORD *)&v87 + 1) == v88 )
          {
            std::vector<winrt::hstring>::_Emplace_reallocate<winrt::hstring const &>(&v87, *((_QWORD *)&v87 + 1), &v84);
            v55 = (volatile signed __int32 *)v84;
          }
          else
          {
            *v59 = winrt::impl::duplicate_hstring((winrt::impl *)v55, v56);
            *((_QWORD *)&v87 + 1) += 8LL;
          }
        }
        if ( v55 )
        {
          v60 = _InterlockedExchangeAdd(v55 + 6, 0xFFFFFFFF);
          if ( v60 == 1 )
          {
            v61 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v61, 0, (LPVOID)v55);
          }
          else if ( v60 - 1 < 0 )
          {
            abort();
          }
        }
        goto LABEL_113;
      }
    }
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v79);
    goto LABEL_101;
  }
  LODWORD(v83) = 0;
  v33 = (*((__int64 (__fastcall **)(const wchar_t **, winrt::impl **))*v31 + 6))(v31, &v83);
  if ( v33 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v33);
  }
  if ( (_DWORD)v83 != 1037 )
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x174, v34, (const char *)0x8007065ELL, v66[0]);
  pv = 0;
  v91 = 0;
  v35 = *v31;
  p_pv = &pv;
  v73 = 0;
  v36 = (*((__int64 (__fastcall **)(const wchar_t **, int *, LPVOID *))v35 + 38))(v32, &v73, &pv);
  if ( v36 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v36);
  }
  *((_DWORD *)p_pv + 2) = v73;
  v37 = (winrt::impl **)pv;
  v38 = v91;
  p_pv = (char *)pv + 8 * v91;
  if ( pv != p_pv )
  {
    v77[0] = L"@Name";
    v77[1] = 5;
    do
    {
      v39 = *v37;
      v74 = v39;
      if ( v39 )
        (*(void (__fastcall **)(winrt::impl *))(*(_QWORD *)v39 + 8LL))(v39);
      *(_QWORD *)v79 = 0;
      if ( v39 )
        (**(void (__fastcall ***)(winrt::impl *, __int64 *, int *))v39)(
          v39,
          winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>>,
          v79);
      winrt::hstring::hstring(&lpMem, v77);
      v40 = (volatile signed __int32 *)lpMem;
      v78[0] = lpMem;
      winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::TryLookup(
        v79,
        &v84,
        v78);
      if ( v84
        && (v82 = 0,
            (**(void (__fastcall ***)(winrt::impl *, __int64 *, winrt::impl **))v84)(
              v84,
              winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>,
              &v82),
            v41 = v82,
            (v76 = v82) != 0) )
      {
        v82 = 0;
        v42 = (*(__int64 (__fastcall **)(winrt::impl *, winrt::impl **))(*(_QWORD *)v41 + 152LL))(v41, &v82);
        if ( v42 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v42);
        }
        v43 = (volatile signed __int32 *)v82;
        v83 = v82;
        v24 |= 0xAu;
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v76);
        if ( v84 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v84);
      }
      else
      {
        v69 = &S2;
        v70[0] = 0;
        winrt::hstring::hstring(&v83, &v69);
        v24 |= 2u;
        if ( v84 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v84);
        v43 = (volatile signed __int32 *)v83;
      }
      if ( v40 )
      {
        v45 = _InterlockedDecrement(v40 + 6);
        if ( v45 )
        {
          if ( v45 < 0 )
            abort();
        }
        else
        {
          v46 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v46, 0, (LPVOID)v40);
        }
        lpMem = 0;
      }
      if ( v43 )
      {
        v47 = (_QWORD *)*((_QWORD *)&v87 + 1);
        if ( *((_QWORD *)&v87 + 1) == v88 )
        {
          std::vector<winrt::hstring>::_Emplace_reallocate<winrt::hstring const &>(&v87, *((_QWORD *)&v87 + 1), &v83);
          v43 = (volatile signed __int32 *)v83;
        }
        else
        {
          *v47 = winrt::impl::duplicate_hstring((winrt::impl *)v43, v44);
          *((_QWORD *)&v87 + 1) += 8LL;
        }
      }
      if ( v43 )
      {
        v48 = _InterlockedDecrement(v43 + 6);
        if ( v48 )
        {
          if ( v48 < 0 )
            abort();
        }
        else
        {
          v49 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v49, 0, (LPVOID)v43);
        }
        v83 = 0;
      }
      if ( *(_QWORD *)v79 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v79);
      if ( v39 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v74);
      ++v37;
    }
    while ( v37 != p_pv );
    v38 = v91;
    v37 = (winrt::impl **)pv;
  }
  if ( v37 )
  {
    v50 = &v37[v38];
    if ( v37 != v50 )
    {
      do
      {
        if ( *v37 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v37);
        ++v37;
      }
      while ( v37 != v50 );
      v37 = (winrt::impl **)pv;
    }
    CoTaskMemFree_0(v37);
  }
  v4 = v81;
LABEL_115:
  if ( v31 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v67);
  v62 = v88;
  v88 = 0;
  v63 = *((_QWORD *)&v87 + 1);
  v64 = v87;
  v87 = 0u;
  *(_QWORD *)v4 = v64;
  *((_QWORD *)v4 + 1) = v63;
  *((_QWORD *)v4 + 2) = v62;
  if ( v86 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v86);
  if ( *(_QWORD *)v66 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v66);
  if ( v89 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v89);
  if ( v80 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v80);
LABEL_125:
  if ( v85 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v85);
  return v4;
}

```

## disassembly

```asm
0x180006750  mov     [rsp-8+arg_0], rbx
0x180006755  mov     [rsp-8+arg_10], rsi
0x18000675a  mov     [rsp-8+arg_18], rdi
0x18000675f  push    rbp
0x180006760  push    r12
0x180006762  push    r13
0x180006764  push    r14
0x180006766  push    r15
0x180006768  lea     rbp, [rsp-30h]
0x18000676d  sub     rsp, 130h
0x180006774  mov     rax, cs:__security_cookie
0x18000677b  xor     rax, rsp
0x18000677e  mov     [rbp+50h+var_30], rax
0x180006782  mov     rdi, r8
0x180006785  mov     r15, rdx
0x180006788  mov     [rbp+50h+var_90], rdx
0x18000678c  mov     [rsp+150h+var_F8], rdx
0x180006791  xor     r13d, r13d
0x180006794  mov     [rsp+150h+var_120], r13d
0x180006799  mov     rax, cs:qword_18002E880
0x1800067a0  mov     [rsp+150h+var_118], rax
0x1800067a5  lea     rax, [rsp+150h+var_118]
0x1800067aa  mov     [rsp+150h+var_128], rax
0x1800067af  lea     rax, qword_18002E748
0x1800067b6  mov     [rsp+150h+var_F8], rax
0x1800067bb  lock inc cs:qword_18002E748
0x1800067c3  mov     rcx, cs:??$factory_cache_entry_v@UPackageExtensionCatalog@PackageExtensions@ApplicationModel@Windows@winrt@@UIPackageExtensionCatalogStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UPackageExtensionCatalog@PackageExtensions@ApplicationModel@Windows@winrt@@UIPackageExtensionCatalogStatics@2345@@12@A; factory_cache_entry<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>
0x1800067ca  test    rcx, rcx
0x1800067cd  jz      short loc_180006809
0x1800067cf  mov     [rbp+50h+var_98], r13
0x1800067d3  mov     rax, [rcx]
0x1800067d6  lea     r8, [rbp+50h+var_98]
0x1800067da  mov     rdx, [rsp+150h+var_118]
0x1800067df  mov     rax, [rax+30h]
0x1800067e3  call    cs:__guard_dispatch_icall_fptr
0x1800067e9  test    eax, eax
0x1800067eb  js      loc_18000711A
0x1800067f1  mov     rbx, [rbp+50h+var_98]
0x1800067f5  mov     qword ptr [rbp+50h+var_A0], rbx
0x1800067f9  mov     r12d, 0E0h
0x1800067ff  lock dec cs:qword_18002E748
0x180006807  jmp     short loc_180006829
0x180006809  lock dec cs:qword_18002E748
0x180006811  lea     r8, [rsp+150h+var_128]
0x180006816  lea     rdx, [rbp+50h+var_A0]
0x18000681a  call    ??$call@AEAV_lambda_cb41fde99ba74c6248b3ce76f09f9615_@@@?$factory_cache_entry@UPackageExtensionCatalog@PackageExtensions@ApplicationModel@Windows@winrt@@UIPackageExtensionCatalogStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_cb41fde99ba74c6248b3ce76f09f9615_@@@Z
0x18000681f  mov     r12d, 20h ; ' '
0x180006825  mov     rbx, qword ptr [rbp+50h+var_A0]
0x180006829  or      r12d, 10h
0x18000682d  mov     [rbp+50h+var_98], r13
0x180006831  mov     rax, [rbx]
0x180006834  lea     rdx, [rbp+50h+var_98]
0x180006838  mov     rcx, rbx
0x18000683b  mov     rax, [rax+30h]
0x18000683f  call    cs:__guard_dispatch_icall_fptr
0x180006845  test    eax, eax
0x180006847  js      loc_180007125
0x18000684d  mov     rcx, [rbp+50h+var_98]
0x180006851  mov     [rbp+50h+var_70], rcx
0x180006855  bts     r12d, 8
0x18000685a  test    rbx, rbx
0x18000685d  jz      short loc_18000686C
0x18000685f  lea     rcx, [rbp+50h+var_A0]
0x180006863  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180006868  mov     rcx, [rbp+50h+var_70]
0x18000686c  mov     dword ptr [rbp+50h+var_80], r13d
0x180006870  mov     rax, [rcx]
0x180006873  lea     rdx, [rbp+50h+var_80]
0x180006877  mov     rax, [rax+38h]
0x18000687b  call    cs:__guard_dispatch_icall_fptr
0x180006881  test    eax, eax
0x180006883  js      loc_180007130
0x180006889  mov     [rsp+150h+var_128], rdi
0x18000688e  mov     ebx, r13d
0x180006891  mov     esi, dword ptr [rbp+50h+var_80]
0x180006894  test    esi, esi
0x180006896  jz      short loc_180006908
0x180006898  mov     edx, r13d
0x18000689b  nop     dword ptr [rax+rax+00h]
0x1800068a0  mov     qword ptr [rsp+150h+var_130], r13
0x1800068a5  bts     r12d, 0Ah
0x1800068aa  mov     [rsp+150h+var_120], r12d
0x1800068af  mov     rcx, [rbp+50h+var_70]
0x1800068b3  mov     rax, [rcx]
0x1800068b6  lea     r8, [rsp+150h+var_130]
0x1800068bb  mov     rax, [rax+30h]
0x1800068bf  call    cs:__guard_dispatch_icall_fptr
0x1800068c5  test    eax, eax
0x1800068c7  js      loc_180007146
0x1800068cd  btr     r12d, 0Ah
0x1800068d2  bts     r12d, 9
0x1800068d7  lea     rdx, [rsp+150h+var_130]
0x1800068dc  lea     rcx, [rsp+150h+var_128]
0x1800068e1  call    _lambda_61d4f9a59e78ac71736878df22f486c0___operator__
0x1800068e6  movzx   edi, al
0x1800068e9  cmp     qword ptr [rsp+150h+var_130], 0
0x1800068ef  jz      short loc_1800068FB
0x1800068f1  lea     rcx, [rsp+150h+var_130]
0x1800068f6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800068fb  test    dil, dil
0x1800068fe  jnz     short loc_180006908
0x180006900  inc     ebx
0x180006902  mov     edx, ebx
0x180006904  cmp     ebx, esi
0x180006906  jnz     short loc_1800068A0
0x180006908  mov     dword ptr [rbp+50h+var_80], r13d
0x18000690c  mov     rcx, [rbp+50h+var_70]
0x180006910  mov     rax, [rcx]
0x180006913  lea     rdx, [rbp+50h+var_80]
0x180006917  mov     rax, [rax+38h]
0x18000691b  call    cs:__guard_dispatch_icall_fptr
0x180006921  test    eax, eax
0x180006923  js      loc_18000713B
0x180006929  cmp     ebx, dword ptr [rbp+50h+var_80]
0x18000692c  jnz     short loc_18000693E
0x18000692e  mov     [r15], r13
0x180006931  mov     [r15+8], r13
0x180006935  mov     [r15+10h], r13
0x180006939  jmp     loc_1800070C2
0x18000693e  mov     qword ptr [rsp+150h+var_130], r13; int
0x180006943  bts     r12d, 0Ch
0x180006948  mov     [rsp+150h+var_120], r12d
0x18000694d  mov     rcx, [rbp+50h+var_70]
0x180006951  mov     rax, [rcx]
0x180006954  lea     r8, [rsp+150h+var_130]
0x180006959  mov     edx, ebx
0x18000695b  mov     rax, [rax+30h]
0x18000695f  call    cs:__guard_dispatch_icall_fptr
0x180006965  test    eax, eax
0x180006967  js      loc_180007151
0x18000696d  btr     r12d, 0Ch
0x180006972  bts     r12d, 0Bh
0x180006977  mov     [rbp+50h+var_98], r13
0x18000697b  mov     rcx, qword ptr [rsp+150h+var_130]
0x180006980  mov     rax, [rcx]
0x180006983  lea     rdx, [rbp+50h+var_98]
0x180006987  mov     rax, [rax+50h]
0x18000698b  call    cs:__guard_dispatch_icall_fptr
0x180006991  test    eax, eax
0x180006993  js      loc_18000715C
0x180006999  mov     rax, [rbp+50h+var_98]
0x18000699d  mov     [rbp+50h+var_98], rax
0x1800069a1  bts     r12d, 0Dh
0x1800069a6  cmp     qword ptr [rsp+150h+var_130], 0
0x1800069ac  jz      short loc_1800069B8
0x1800069ae  lea     rcx, [rsp+150h+var_130]
0x1800069b3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800069b8  mov     dword ptr [rsp+150h+var_110], 1
0x1800069c0  mov     dword ptr [rsp+150h+var_110+4], 0Eh
0x1800069c8  lea     rax, aSessionclasses; "SessionClasses"
0x1800069cf  mov     [rsp+150h+var_100], rax
0x1800069d4  lea     rax, [rsp+150h+var_110]
0x1800069d9  mov     [rsp+150h+var_118], rax
0x1800069de  lea     r8, [rsp+150h+var_118]
0x1800069e3  lea     rdx, [rbp+50h+var_48]
0x1800069e7  lea     rcx, [rbp+50h+var_98]
0x1800069eb  call    ?TryLookup@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::TryLookup(winrt::param::hstring const &)
0x1800069f0  nop
0x1800069f1  mov     rdi, [rbp+58h]
0x1800069f5  mov     qword ptr [rbp+50h+var_A0], r13
0x1800069f9  lea     rdx, [rbp+50h+var_A0]
0x1800069fd  lea     rcx, [rbp+50h+var_48]
0x180006a01  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180006a06  movzx   ebx, al
0x180006a09  cmp     qword ptr [rbp+50h+var_A0], 0
0x180006a0e  jz      short loc_180006A19
0x180006a10  lea     rcx, [rbp+50h+var_A0]
0x180006a14  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180006a19  test    bl, bl
0x180006a1b  jz      short loc_180006A30
0x180006a1d  mov     edx, 168h; void *
0x180006a22  mov     r9d, 80070490h; char *
0x180006a28  mov     rcx, rdi; this
0x180006a2b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180006a30  mov     rcx, [rbp+50h+var_48]
0x180006a34  test    rcx, rcx
0x180006a37  jnz     short loc_180006A40
0x180006a39  mov     qword ptr [rsp+150h+var_130], r13
0x180006a3e  jmp     short loc_180006A64
0x180006a40  mov     qword ptr [rbp+50h+var_A0], r13
0x180006a44  mov     rax, [rcx]
0x180006a47  lea     r8, [rbp+50h+var_A0]
0x180006a4b  lea     rdx, ??$guid_v@U?$IMap@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>>
0x180006a52  mov     rax, [rax]
0x180006a55  call    cs:__guard_dispatch_icall_fptr
0x180006a5b  mov     rax, qword ptr [rbp+50h+var_A0]
0x180006a5f  mov     qword ptr [rsp+150h+var_130], rax; int
0x180006a64  mov     rdi, [rbp+58h]
0x180006a68  mov     qword ptr [rbp+50h+var_A0], r13
0x180006a6c  lea     rdx, [rbp+50h+var_A0]
0x180006a70  lea     rcx, [rsp+150h+var_130]
0x180006a75  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180006a7a  movzx   ebx, al
0x180006a7d  cmp     qword ptr [rbp+50h+var_A0], 0
0x180006a82  jz      short loc_180006A8D
0x180006a84  lea     rcx, [rbp+50h+var_A0]
0x180006a88  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180006a8d  test    bl, bl
0x180006a8f  jz      short loc_180006AA4
0x180006a91  mov     edx, 16Ch; void *
0x180006a96  mov     r9d, 80004005h; char *
0x180006a9c  mov     rcx, rdi; this
0x180006a9f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180006aa4  mov     dword ptr [rsp+150h+var_110], 1
0x180006aac  mov     dword ptr [rsp+150h+var_110+4], 0Ch
0x180006ab4  lea     rax, aSessionclass; "SessionClass"
0x180006abb  mov     [rsp+150h+var_100], rax
0x180006ac0  lea     rax, [rsp+150h+var_110]
0x180006ac5  mov     [rsp+150h+var_118], rax
0x180006aca  lea     r8, [rsp+150h+var_118]
0x180006acf  lea     rdx, [rbp+50h+var_68]
0x180006ad3  lea     rcx, [rsp+150h+var_130]
0x180006ad8  call    ?TryLookup@?$consume_Windows_Foundation_Collections_IMap@U?$IMap@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::TryLookup(winrt::param::hstring const &)
0x180006add  nop
0x180006ade  mov     rdi, [rbp+58h]
0x180006ae2  mov     qword ptr [rbp+50h+var_A0], r13
0x180006ae6  lea     rdx, [rbp+50h+var_A0]
0x180006aea  lea     rcx, [rbp+50h+var_68]
0x180006aee  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180006af3  movzx   ebx, al
0x180006af6  cmp     qword ptr [rbp+50h+var_A0], 0
0x180006afb  jz      short loc_180006B06
0x180006afd  lea     rcx, [rbp+50h+var_A0]
0x180006b01  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180006b06  test    bl, bl
0x180006b08  jz      short loc_180006B1D
0x180006b0a  mov     edx, 16Fh; void *
0x180006b0f  mov     r9d, 80070490h; char *
0x180006b15  mov     rcx, rdi; this
0x180006b18  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180006b1d  xorps   xmm1, xmm1
0x180006b20  movdqu  [rbp+50h+var_60], xmm1
0x180006b25  mov     [rbp+50h+var_50], r13
0x180006b29  cmp     [rbp+50h+var_68], 0
0x180006b2e  jnz     short loc_180006B3D
0x180006b30  mov     r14, r13
0x180006b33  mov     [rsp+150h+var_128], r13
0x180006b38  mov     rbx, r13
0x180006b3b  jmp     short loc_180006B68
0x180006b3d  mov     qword ptr [rbp+50h+var_A0], r13
0x180006b41  mov     rcx, [rbp+50h+var_68]
0x180006b45  mov     rax, [rcx]
0x180006b48  lea     r8, [rbp+50h+var_A0]
0x180006b4c  lea     rdx, ??$guid_v@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>
0x180006b53  mov     rax, [rax]
0x180006b56  call    cs:__guard_dispatch_icall_fptr
0x180006b5c  mov     r14, qword ptr [rbp+50h+var_A0]
0x180006b60  mov     [rsp+150h+var_128], r14
0x180006b65  mov     rbx, r14
0x180006b68  test    rbx, rbx
0x180006b6b  jz      loc_180006E80
0x180006b71  mov     dword ptr [rbp+50h+var_80], r13d
0x180006b75  mov     rax, [r14]
0x180006b78  lea     rdx, [rbp+50h+var_80]
0x180006b7c  mov     rcx, r14
0x180006b7f  mov     rax, [rax+30h]
0x180006b83  call    cs:__guard_dispatch_icall_fptr
0x180006b89  test    eax, eax
0x180006b8b  js      loc_180007167
0x180006b91  mov     rcx, [rbp+58h]; this
0x180006b95  cmp     dword ptr [rbp+50h+var_80], 40Dh
0x180006b9c  jz      short loc_180006BAE
0x180006b9e  mov     edx, 174h; void *
0x180006ba3  mov     r9d, 8007065Eh; char *
0x180006ba9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180006bae  mov     [rbp+50h+pv], r13
0x180006bb2  mov     [rbp+50h+var_38], r13d
0x180006bb6  mov     rax, [r14]
0x180006bb9  lea     rcx, [rbp+50h+pv]
0x180006bbd  mov     [rsp+150h+var_F8], rcx
0x180006bc2  mov     [rsp+150h+var_F0], r13d
0x180006bc7  lea     r8, [rbp+50h+pv]
0x180006bcb  lea     rdx, [rsp+150h+var_F0]
0x180006bd0  mov     rcx, rbx
0x180006bd3  mov     rax, [rax+130h]
0x180006bda  call    cs:__guard_dispatch_icall_fptr
0x180006be0  test    eax, eax
0x180006be2  js      loc_180007172
0x180006be8  mov     rcx, [rsp+150h+var_F8]
0x180006bed  mov     eax, [rsp+150h+var_F0]
0x180006bf1  mov     [rcx+8], eax
0x180006bf4  mov     r15, [rbp+50h+pv]
0x180006bf8  mov     ecx, [rbp+50h+var_38]
0x180006bfb  lea     rax, [r15+rcx*8]
0x180006bff  mov     [rsp+150h+var_F8], rax
0x180006c04  cmp     r15, rax
0x180006c07  jz      loc_180006E36
0x180006c0d  lea     rax, aName; "@Name"
0x180006c14  mov     [rbp+50h+var_D0], rax
0x180006c18  mov     [rbp+50h+var_C8], 5
0x180006c20  mov     r13d, 0FFFFFFFFh
0x180006c26  lea     rbx, S2
0x180006c2d  mov     rdi, [r15]
0x180006c30  mov     [rsp+150h+var_E8], rdi
0x180006c35  test    rdi, rdi
0x180006c38  jz      short loc_180006C4B
0x180006c3a  mov     rax, [rdi]
0x180006c3d  mov     rcx, rdi
0x180006c40  mov     rax, [rax+8]
0x180006c44  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```
