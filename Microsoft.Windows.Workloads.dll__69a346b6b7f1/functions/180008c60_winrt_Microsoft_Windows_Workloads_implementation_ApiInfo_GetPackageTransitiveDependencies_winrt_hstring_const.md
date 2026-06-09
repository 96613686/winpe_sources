# winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::GetPackageTransitiveDependencies(winrt::hstring const &)

- ea: `0x180008c60`
- end: `0x18000985a`
- name: `?GetPackageTransitiveDependencies@ApiInfo@implementation@Workloads@Windows@Microsoft@winrt@@AEAA?AV?$map@Uhstring@winrt@@UPackageVersion@ApplicationModel@Windows@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UPackageVersion@ApplicationModel@Windows@2@@std@@@7@@std@@AEBUhstring@6@@Z`
- size: `3066`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180007a20`

## callees

- `0x1800027d0`
- `0x1800029f0`
- `0x1800040a0`
- `0x180004810`
- `0x180004c70`
- `0x180008c60`
- `0x1800098d0`
- `0x180009a40`
- `0x18000cb20`
- `0x180015250`
- `0x1800157c0`
- `0x180030ae5`
- `0x180030aeb`
- `0x180034ef0`
- `0x180035060`
- `0x180039899`
- `0x18003bed0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180008f8f`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800094c8`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800094cf`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800094d6`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800097b0`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800097bf`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800097cf`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180008f8f`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800094c8`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800094cf`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800094d6`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800097b0`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800097bf`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800097cf`

## string_xrefs

- `0x180008cf0`: `com.microsoft.windows.workload.transitivedependencies`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
_QWORD *__fastcall winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::GetPackageTransitiveDependencies(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3)
{
  __int64 *v3; // rbx
  _QWORD *v4; // rdi
  winrt::impl *v5; // r12
  _QWORD *v6; // rax
  int v7; // eax
  __int64 v8; // rcx
  int v9; // r13d
  int v10; // r13d
  int v11; // eax
  int v12; // r13d
  unsigned int v13; // r15d
  int v14; // eax
  int v15; // r13d
  int v16; // eax
  unsigned int v17; // r13d
  int v18; // eax
  winrt::impl *v19; // rsi
  int v20; // r13d
  int v21; // eax
  int **v22; // rdi
  int v23; // r13d
  int v24; // eax
  __int64 v25; // rax
  __int64 v26; // rcx
  const wchar_t *v27; // rdx
  volatile signed __int32 *v28; // rbx
  size_t v29; // r8
  const wchar_t *v30; // rax
  bool v31; // r14
  int v32; // eax
  HANDLE ProcessHeap; // rax
  int v34; // eax
  winrt::impl *v35; // rax
  int v36; // r13d
  __int64 v37; // rbx
  __int64 (__fastcall *v38)(__int64, int *, winrt::impl **); // rdi
  int v39; // eax
  winrt::impl *v40; // rax
  int v41; // r13d
  int v42; // eax
  int **v43; // r15
  int **v44; // rbx
  int v45; // eax
  int *v46; // rax
  int v47; // eax
  winrt::impl **v48; // rdi
  unsigned int v49; // ecx
  winrt::impl *v50; // rbx
  winrt::impl *v51; // r14
  winrt::impl *v52; // rsi
  __int64 v53; // rcx
  __int64 v54; // rcx
  volatile signed __int32 *v55; // rsi
  const wchar_t *v56; // r12
  unsigned __int64 v57; // r8
  __int64 v58; // rcx
  __int64 *PackageVersionFromString; // r12
  volatile signed __int32 *v60; // rdi
  struct winrt::impl::hstring_header *v61; // rdx
  int v62; // eax
  HANDLE v63; // rax
  int v64; // eax
  HANDLE v65; // rax
  int v66; // eax
  HANDLE v67; // rax
  winrt::impl **v68; // rbx
  winrt::impl *v69; // rsi
  winrt::impl *v70; // rbx
  __int64 v71; // rcx
  __int64 v72; // rcx
  volatile signed __int32 *v73; // rbx
  const wchar_t *v74; // r12
  unsigned __int64 v75; // r8
  __int64 v76; // rcx
  __int64 *v77; // r14
  volatile signed __int32 *v78; // rdi
  struct winrt::impl::hstring_header *v79; // rdx
  void *v80; // r12
  int v81; // eax
  HANDLE v82; // rax
  int v83; // eax
  HANDLE v84; // rax
  int v85; // r14d
  HANDLE v86; // rax
  __int64 v88; // [rsp+20h] [rbp-E0h]
  __int64 v89; // [rsp+20h] [rbp-E0h]
  __int64 v90; // [rsp+20h] [rbp-E0h]
  int **v91; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD *v92; // [rsp+30h] [rbp-D0h]
  winrt::impl *v93; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID *p_pv; // [rsp+40h] [rbp-C0h] BYREF
  int v95; // [rsp+48h] [rbp-B8h] BYREF
  int *v96; // [rsp+50h] [rbp-B0h] BYREF
  int v97; // [rsp+58h] [rbp-A8h] BYREF
  int v98; // [rsp+5Ch] [rbp-A4h]
  const wchar_t *v99; // [rsp+68h] [rbp-98h]
  LPVOID v100; // [rsp+70h] [rbp-90h] BYREF
  __int64 v101; // [rsp+78h] [rbp-88h]
  __int128 v102; // [rsp+80h] [rbp-80h] BYREF
  __int128 v103; // [rsp+90h] [rbp-70h]
  __int128 v104; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v105; // [rsp+B0h] [rbp-50h]
  winrt::impl *v106; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v107; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v108[2]; // [rsp+D8h] [rbp-28h] BYREF
  int **v109; // [rsp+E8h] [rbp-18h] BYREF
  int **v110; // [rsp+F0h] [rbp-10h] BYREF
  winrt::impl *v111; // [rsp+F8h] [rbp-8h] BYREF
  winrt::impl *v112; // [rsp+100h] [rbp+0h] BYREF
  __int64 v113; // [rsp+108h] [rbp+8h] BYREF
  LPVOID lpMem; // [rsp+110h] [rbp+10h] BYREF
  __int64 v115; // [rsp+118h] [rbp+18h] BYREF
  winrt::impl *v116; // [rsp+120h] [rbp+20h] BYREF
  __int64 *v117; // [rsp+128h] [rbp+28h] BYREF
  __int64 v118; // [rsp+130h] [rbp+30h] BYREF
  LPVOID v119; // [rsp+138h] [rbp+38h] BYREF
  LPVOID pv; // [rsp+140h] [rbp+40h] BYREF
  unsigned int v121; // [rsp+148h] [rbp+48h]
  winrt::impl *v122; // [rsp+150h] [rbp+50h] BYREF
  LPVOID v123; // [rsp+158h] [rbp+58h] BYREF
  __int64 *v124; // [rsp+160h] [rbp+60h] BYREF

  v3 = a3;
  v119 = a3;
  v4 = a2;
  v92 = a2;
  v108[1] = a2;
  v5 = 0;
  *(_OWORD *)a2 = 0;
  *a2 = 0;
  a2[1] = 0;
  v6 = operator new(0x30u);
  *v6 = v6;
  v6[1] = v6;
  v6[2] = v6;
  *((_WORD *)v6 + 12) = 257;
  *v4 = v6;
  v97 = 1;
  v98 = 53;
  v99 = L"com.microsoft.windows.workload.transitivedependencies";
  v96 = &v97;
  v91 = &v96;
  v124 = &qword_180059EC8;
  _InterlockedIncrement64(&qword_180059EC8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics> )
  {
    v115 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, int *, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>
                                                              + 48LL))(
           winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>,
           v96,
           &v115);
    if ( v7 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v7);
    }
    v8 = v115;
    v9 = 7169;
    _InterlockedDecrement64(&qword_180059EC8);
  }
  else
  {
    _InterlockedDecrement64(&qword_180059EC8);
    winrt::impl::factory_cache_entry<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>::call<_lambda_cb41fde99ba74c6248b3ce76f09f9615_ &>(
      0,
      &v115,
      &v91);
    v9 = 1025;
    v8 = v115;
  }
  v10 = v9 | 0x200;
  v117 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v8 + 48LL))(v8, &v117);
  if ( v11 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v11);
  }
  v124 = v117;
  v12 = v10 | 0x100;
  v13 = 0;
  LODWORD(v109) = 0;
  v14 = (*(__int64 (__fastcall **)(__int64 *, int ***))(*v117 + 56))(v117, &v109);
  if ( v14 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v14);
  }
  if ( (_DWORD)v109 )
  {
    while ( 1 )
    {
      v118 = 0;
      v15 = v12 | 8;
      v16 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(*v117 + 48))(v117, v13, &v118);
      if ( v16 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v16);
      }
      v17 = v15 & 0xFFFFFFF3 | 4;
      v111 = 0;
      v18 = (*(__int64 (__fastcall **)(__int64, winrt::impl **))(*(_QWORD *)v118 + 72LL))(v118, &v111);
      if ( v18 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v18);
      }
      v19 = v111;
      v112 = v111;
      v20 = v17 | 2;
      v110 = 0;
      v21 = (*(__int64 (__fastcall **)(winrt::impl *, int ***))(*(_QWORD *)v111 + 48LL))(v111, &v110);
      if ( v21 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v21);
      }
      v22 = v110;
      v91 = v110;
      v23 = v20 | 0x10;
      lpMem = 0;
      v24 = (*((__int64 (__fastcall **)(int **, LPVOID *))*v110 + 13))(v110, &lpMem);
      if ( v24 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v24);
      }
      v12 = v23 | 0x20;
      v25 = *v3;
      if ( *v3 )
      {
        v26 = *(unsigned int *)(v25 + 4);
        v27 = *(const wchar_t **)(v25 + 16);
      }
      else
      {
        v26 = 0;
        v27 = &Src;
      }
      v28 = (volatile signed __int32 *)lpMem;
      if ( lpMem )
      {
        v29 = *((unsigned int *)lpMem + 1);
        v30 = (const wchar_t *)*((_QWORD *)lpMem + 2);
      }
      else
      {
        v29 = 0;
        v30 = &Src;
      }
      if ( v29 == v26 )
      {
        if ( v29 )
          v31 = wmemcmp(v30, v27, v29) == 0;
        else
          v31 = 1;
      }
      else
      {
        v31 = 0;
      }
      if ( v28 )
      {
        v32 = _InterlockedDecrement(v28 + 6);
        if ( v32 )
        {
          if ( v32 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, lpMem);
        }
        v22 = v110;
        v19 = v111;
      }
      if ( v22 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v91);
      if ( v19 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v112);
      if ( v31 )
        break;
      if ( v118 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v118);
      if ( ++v13 == (_DWORD)v109 )
        goto LABEL_138;
      v3 = (__int64 *)v119;
    }
    lpMem = 0;
    v34 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v118 + 80LL))(v118, &lpMem);
    if ( v34 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v34);
    }
    v108[0] = lpMem;
    v97 = 1;
    v98 = 22;
    v99 = L"TransitiveDependencies";
    v96 = &v97;
    v35 = 0;
    v111 = 0;
    v36 = v12 | 0xC0;
    if ( lpMem )
    {
      v113 = 0;
      (**(void (__fastcall ***)(LPVOID, __int64 *, __int64 *))lpMem)(
        lpMem,
        winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>>,
        &v113);
      v37 = v113;
      v35 = v111;
    }
    else
    {
      v37 = 0;
    }
    v113 = v37;
    v38 = *(__int64 (__fastcall **)(__int64, int *, winrt::impl **))(*(_QWORD *)v37 + 48LL);
    if ( v35 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v111);
    v39 = v38(v37, v96, &v111);
    if ( v39 != -2147483637 && v39 != -2147467259 && v39 != -2147024894 && v39 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v39);
    }
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v113);
    v40 = v111;
    if ( v111 )
    {
      v113 = 0;
      (**(void (__fastcall ***)(winrt::impl *, __int64 *, __int64 *))v111)(
        v111,
        winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>>,
        &v113);
      v107 = v113;
      if ( v113 )
      {
        v97 = 1;
        v98 = 20;
        v99 = L"TransitiveDependency";
        v96 = &v97;
        v110 = 0;
        v41 = v36 | 0x2000;
        LODWORD(v88) = v41;
        v42 = (*(__int64 (__fastcall **)(__int64, int *, int ***))(*(_QWORD *)v113 + 48LL))(v113, &v97, &v110);
        if ( v42 != -2147483637 && v42 != -2147467259 && v42 != -2147024894 && v42 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v42);
        }
        if ( v110 )
        {
          v109 = 0;
          (*(void (__fastcall **)(int **, __int64 *, int ***))*v110)(
            v110,
            winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>,
            &v109);
          v43 = v109;
          v91 = v109;
          v44 = v109;
        }
        else
        {
          v43 = 0;
          v91 = 0;
          v44 = 0;
        }
        if ( v44 )
        {
          LODWORD(v109) = 0;
          v45 = (*((__int64 (__fastcall **)(int **, int ***))*v43 + 6))(v43, &v109);
          if ( v45 < 0 )
          {
            _mm_lfence();
            winrt::throw_hresult((unsigned int)v45);
          }
          if ( (_DWORD)v109 == 1037 )
          {
            pv = 0;
            v121 = 0;
            v46 = *v43;
            p_pv = &pv;
            v95 = 0;
            v47 = (*((__int64 (__fastcall **)(int **, int *, LPVOID *))v46 + 38))(v44, &v95, &pv);
            if ( v47 < 0 )
            {
              _mm_lfence();
              winrt::throw_hresult((unsigned int)v47);
            }
            *((_DWORD *)p_pv + 2) = v95;
            v48 = (winrt::impl **)pv;
            v109 = (int **)pv;
            v49 = v121;
            v123 = (char *)pv + 8 * v121;
            if ( pv != v123 )
            {
              do
              {
                v50 = *v48;
                v122 = v50;
                if ( v50 )
                  (*(void (__fastcall **)(winrt::impl *))(*(_QWORD *)v50 + 8LL))(v50);
                v116 = v5;
                if ( v50 )
                {
                  (**(void (__fastcall ***)(winrt::impl *, __int64 *, void **))v50)(
                    v50,
                    winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>>,
                    (void **)&v116);
                  v51 = v116;
                  v52 = v116;
                }
                else
                {
                  v51 = v5;
                  v52 = v5;
                }
                if ( v52 )
                {
                  v102 = 0;
                  *(_QWORD *)&v103 = v5;
                  *((_QWORD *)&v103 + 1) = v5;
                  std::wstring::_Construct<1,wchar_t const *>(&v102, L"@FamilyName", 0xBu);
                  v106 = v51;
                  (*(void (__fastcall **)(winrt::impl *))(*(_QWORD *)v52 + 8LL))(v52);
                  winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::TryGetStringPropertyFromMap(
                    v53,
                    &v112,
                    &v106,
                    &v102,
                    v88);
                  v104 = 0;
                  *(_QWORD *)&v105 = v5;
                  *((_QWORD *)&v105 + 1) = v5;
                  std::wstring::_Construct<1,wchar_t const *>(&v104, L"@Version", 8u);
                  v93 = v51;
                  (*(void (__fastcall **)(winrt::impl *))(*(_QWORD *)v52 + 8LL))(v52);
                  winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::TryGetStringPropertyFromMap(
                    v54,
                    &v119,
                    &v93,
                    &v104,
                    v89);
                  v55 = (volatile signed __int32 *)v119;
                  if ( v119 )
                    v56 = (const wchar_t *)*((_QWORD *)v119 + 2);
                  else
                    v56 = &Src;
                  v102 = 0;
                  v103 = 0;
                  v57 = -1;
                  do
                    ++v57;
                  while ( v56[v57] );
                  std::wstring::_Construct<1,wchar_t const *>(&v102, v56, v57);
                  PackageVersionFromString = (__int64 *)winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::GetPackageVersionFromString(
                                                          v58,
                                                          &p_pv,
                                                          &v102);
                  v60 = (volatile signed __int32 *)v112;
                  v100 = winrt::impl::duplicate_hstring(v112, v61);
                  v101 = *PackageVersionFromString;
                  v41 |= 0x4000u;
                  LODWORD(v88) = v41;
                  std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Windows::ApplicationModel::PackageVersion>>,0>>::_Emplace<std::pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>>(
                    v92,
                    &v96,
                    &v100);
                  v5 = (winrt::impl *)v100;
                  if ( v100 )
                  {
                    v62 = _InterlockedDecrement((volatile signed __int32 *)v100 + 6);
                    if ( v62 )
                    {
                      if ( v62 < 0 )
                        abort();
                      v5 = 0;
                      v100 = 0;
                    }
                    else
                    {
                      v63 = WINRT_IMPL_GetProcessHeap();
                      WINRT_IMPL_HeapFree(v63, 0, v5);
                      v5 = 0;
                      v100 = 0;
                    }
                  }
                  std::wstring::_Tidy_deallocate((__int64)&v102);
                  if ( v55 )
                  {
                    v64 = _InterlockedDecrement(v55 + 6);
                    if ( v64 )
                    {
                      if ( v64 < 0 )
                        abort();
                    }
                    else
                    {
                      v65 = WINRT_IMPL_GetProcessHeap();
                      WINRT_IMPL_HeapFree(v65, 0, (LPVOID)v55);
                    }
                    v119 = v5;
                  }
                  if ( v60 )
                  {
                    v66 = _InterlockedDecrement(v60 + 6);
                    if ( v66 )
                    {
                      if ( v66 < 0 )
                        abort();
                    }
                    else
                    {
                      v67 = WINRT_IMPL_GetProcessHeap();
                      WINRT_IMPL_HeapFree(v67, 0, (LPVOID)v60);
                    }
                    v112 = v5;
                  }
                  v48 = (winrt::impl **)v109;
                }
                if ( v51 )
                  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v116);
                if ( v50 )
                  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v122);
                v109 = (int **)++v48;
              }
              while ( v48 != v123 );
              v49 = v121;
              v48 = (winrt::impl **)pv;
            }
            if ( v48 )
            {
              v68 = &v48[v49];
              if ( v48 != v68 )
              {
                do
                {
                  if ( *v48 )
                    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v48);
                  ++v48;
                }
                while ( v48 != v68 );
                v48 = (winrt::impl **)pv;
              }
              CoTaskMemFree_0(v48);
            }
          }
        }
        else
        {
          if ( v110 )
          {
            v112 = 0;
            (*(void (__fastcall **)(int **, __int64 *, winrt::impl **))*v110)(
              v110,
              winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>>,
              &v112);
            v69 = v112;
            v93 = v112;
            v70 = v112;
          }
          else
          {
            v69 = 0;
            v93 = 0;
            v70 = 0;
          }
          if ( v70 )
          {
            v104 = 0;
            v105 = 0u;
            std::wstring::_Construct<1,wchar_t const *>(&v104, L"@FamilyName", 0xBu);
            v112 = v70;
            (*(void (__fastcall **)(winrt::impl *))(*(_QWORD *)v70 + 8LL))(v70);
            winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::TryGetStringPropertyFromMap(
              v71,
              &v122,
              &v112,
              &v104,
              v41);
            v102 = 0;
            v103 = 0u;
            std::wstring::_Construct<1,wchar_t const *>(&v102, L"@Version", 8u);
            v119 = v70;
            (*(void (__fastcall **)(winrt::impl *))(*(_QWORD *)v70 + 8LL))(v70);
            winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::TryGetStringPropertyFromMap(
              v72,
              &v123,
              &v119,
              &v102,
              v90);
            v73 = (volatile signed __int32 *)v123;
            if ( v123 )
              v74 = (const wchar_t *)*((_QWORD *)v123 + 2);
            else
              v74 = &Src;
            v104 = 0;
            v105 = 0;
            v75 = -1;
            do
              ++v75;
            while ( v74[v75] );
            std::wstring::_Construct<1,wchar_t const *>(&v104, v74, v75);
            v77 = (__int64 *)winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::GetPackageVersionFromString(
                               v76,
                               &p_pv,
                               &v104);
            v78 = (volatile signed __int32 *)v122;
            v100 = winrt::impl::duplicate_hstring(v122, v79);
            v101 = *v77;
            std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Windows::ApplicationModel::PackageVersion>>,0>>::_Emplace<std::pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>>(
              v92,
              &v96,
              &v100);
            v80 = v100;
            if ( v100 )
            {
              v81 = _InterlockedDecrement((volatile signed __int32 *)v100 + 6);
              if ( v81 )
              {
                if ( v81 < 0 )
                  abort();
              }
              else
              {
                v82 = WINRT_IMPL_GetProcessHeap();
                WINRT_IMPL_HeapFree(v82, 0, v80);
              }
            }
            std::wstring::_Tidy_deallocate((__int64)&v104);
            if ( v73 )
            {
              v83 = _InterlockedDecrement(v73 + 6);
              if ( v83 )
              {
                if ( v83 < 0 )
                  abort();
              }
              else
              {
                v84 = WINRT_IMPL_GetProcessHeap();
                WINRT_IMPL_HeapFree(v84, 0, (LPVOID)v73);
              }
            }
            if ( v78 )
            {
              v85 = _InterlockedDecrement(v78 + 6);
              if ( v85 )
              {
                if ( v85 < 0 )
                  abort();
              }
              else
              {
                v86 = WINRT_IMPL_GetProcessHeap();
                WINRT_IMPL_HeapFree(v86, 0, (LPVOID)v78);
              }
            }
          }
          if ( v69 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v93);
        }
        if ( v43 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v91);
        if ( v110 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v110);
      }
      if ( v113 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v107);
      v40 = v111;
    }
    if ( v40 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v111);
    if ( lpMem )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v108);
    if ( v118 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v118);
LABEL_138:
    v4 = v92;
  }
  if ( v117 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v124);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v115);
  return v4;
}

```

## disassembly

```asm
0x180008c60  mov     [rsp-8+arg_0], rbx
0x180008c65  mov     [rsp-8+arg_10], rsi
0x180008c6a  mov     [rsp-8+arg_18], rdi
0x180008c6f  push    rbp
0x180008c70  push    r12
0x180008c72  push    r13
0x180008c74  push    r14
0x180008c76  push    r15
0x180008c78  lea     rbp, [rsp-70h]
0x180008c7d  sub     rsp, 170h
0x180008c84  mov     rax, cs:__security_cookie
0x180008c8b  xor     rax, rsp
0x180008c8e  mov     [rbp+90h+var_28], rax
0x180008c92  mov     rbx, r8
0x180008c95  mov     [rbp+90h+var_58], rbx
0x180008c99  mov     rdi, rdx
0x180008c9c  mov     [rsp+190h+var_160], rdx
0x180008ca1  mov     [rbp+90h+var_B0], rdx
0x180008ca5  xor     r12d, r12d
0x180008ca8  mov     dword ptr [rsp+190h+var_170], r12d
0x180008cad  xorps   xmm0, xmm0
0x180008cb0  movups  xmmword ptr [rdx], xmm0
0x180008cb3  mov     [rdx], r12
0x180008cb6  mov     [rdx+8], r12
0x180008cba  mov     ecx, 30h ; '0'; Size
0x180008cbf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008cc4  mov     [rax], rax
0x180008cc7  mov     [rax+8], rax
0x180008ccb  mov     [rax+10h], rax
0x180008ccf  mov     word ptr [rax+18h], 101h
0x180008cd5  mov     [rdi], rax
0x180008cd8  mov     dword ptr [rsp+190h+var_170], 1
0x180008ce0  mov     [rsp+190h+var_138], 1
0x180008ce8  mov     [rsp+190h+var_134], 35h ; '5'
0x180008cf0  lea     rax, aComMicrosoftWi_0; "com.microsoft.windows.workload.transiti"...
0x180008cf7  mov     [rsp+190h+var_128], rax
0x180008cfc  lea     rax, [rsp+190h+var_138]
0x180008d01  mov     [rsp+190h+var_140], rax
0x180008d06  lea     rax, [rsp+190h+var_140]
0x180008d0b  mov     [rsp+190h+var_168], rax
0x180008d10  lea     rax, qword_180059EC8
0x180008d17  mov     [rbp+90h+var_30], rax
0x180008d1b  lock inc cs:qword_180059EC8
0x180008d23  mov     rcx, cs:??$factory_cache_entry_v@UPackageExtensionCatalog@PackageExtensions@ApplicationModel@Windows@winrt@@UIPackageExtensionCatalogStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UPackageExtensionCatalog@PackageExtensions@ApplicationModel@Windows@winrt@@UIPackageExtensionCatalogStatics@2345@@12@A; factory_cache_entry<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>
0x180008d2a  test    rcx, rcx
0x180008d2d  jz      short loc_180008D69
0x180008d2f  mov     [rbp+90h+var_78], r12
0x180008d33  mov     rax, [rcx]
0x180008d36  lea     r8, [rbp+90h+var_78]
0x180008d3a  mov     rdx, [rsp+190h+var_140]
0x180008d3f  mov     rax, [rax+30h]
0x180008d43  call    cs:__guard_dispatch_icall_fptr
0x180008d49  test    eax, eax
0x180008d4b  js      loc_1800097EC
0x180008d51  mov     rcx, [rbp+90h+var_78]
0x180008d55  mov     [rbp+90h+var_78], rcx
0x180008d59  mov     r13d, 1C01h
0x180008d5f  lock dec cs:qword_180059EC8
0x180008d67  jmp     short loc_180008D89
0x180008d69  lock dec cs:qword_180059EC8
0x180008d71  lea     r8, [rsp+190h+var_168]
0x180008d76  lea     rdx, [rbp+90h+var_78]
0x180008d7a  call    ??$call@AEAV_lambda_cb41fde99ba74c6248b3ce76f09f9615_@@@?$factory_cache_entry@UPackageExtensionCatalog@PackageExtensions@ApplicationModel@Windows@winrt@@UIPackageExtensionCatalogStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_cb41fde99ba74c6248b3ce76f09f9615_@@@Z
0x180008d7f  mov     r13d, 401h
0x180008d85  mov     rcx, [rbp+90h+var_78]
0x180008d89  bts     r13d, 9
0x180008d8e  mov     dword ptr [rsp+190h+var_170], r13d
0x180008d93  mov     [rbp+90h+var_68], r12
0x180008d97  mov     rax, [rcx]
0x180008d9a  lea     rdx, [rbp+90h+var_68]
0x180008d9e  mov     rax, [rax+30h]
0x180008da2  call    cs:__guard_dispatch_icall_fptr
0x180008da8  test    eax, eax
0x180008daa  js      loc_1800097F7
0x180008db0  mov     rcx, [rbp+90h+var_68]
0x180008db4  mov     [rbp+90h+var_30], rcx
0x180008db8  bts     r13d, 8
0x180008dbd  mov     dword ptr [rsp+190h+var_170], r13d
0x180008dc2  mov     r15d, r12d
0x180008dc5  mov     dword ptr [rbp+90h+var_A8], r12d
0x180008dc9  mov     rax, [rcx]
0x180008dcc  lea     rdx, [rbp+90h+var_A8]
0x180008dd0  mov     rax, [rax+38h]
0x180008dd4  call    cs:__guard_dispatch_icall_fptr
0x180008dda  test    eax, eax
0x180008ddc  js      loc_180009802
0x180008de2  cmp     dword ptr [rbp+90h+var_A8], r12d
0x180008de6  jz      loc_18000975E
0x180008dec  nop     dword ptr [rax+00h]
0x180008df0  mov     [rbp+90h+var_60], r12
0x180008df4  or      r13d, 8
0x180008df8  mov     dword ptr [rsp+190h+var_170], r13d
0x180008dfd  mov     rcx, [rbp+90h+var_68]
0x180008e01  mov     rax, [rcx]
0x180008e04  lea     r8, [rbp+90h+var_60]
0x180008e08  mov     edx, r15d
0x180008e0b  mov     rax, [rax+30h]
0x180008e0f  call    cs:__guard_dispatch_icall_fptr
0x180008e15  test    eax, eax
0x180008e17  js      loc_1800097E1
0x180008e1d  and     r13d, 0FFFFFFF7h
0x180008e21  or      r13d, 4
0x180008e25  mov     dword ptr [rsp+190h+var_170], r13d
0x180008e2a  mov     [rbp+90h+var_98], r12
0x180008e2e  mov     rcx, [rbp+90h+var_60]
0x180008e32  mov     rax, [rcx]
0x180008e35  lea     rdx, [rbp+90h+var_98]
0x180008e39  mov     rax, [rax+48h]
0x180008e3d  call    cs:__guard_dispatch_icall_fptr
0x180008e43  test    eax, eax
0x180008e45  js      loc_1800097D6
0x180008e4b  mov     rsi, [rbp+90h+var_98]
0x180008e4f  mov     [rbp+90h+var_90], rsi
0x180008e53  or      r13d, 2
0x180008e57  mov     dword ptr [rsp+190h+var_170], r13d
0x180008e5c  mov     [rbp+90h+var_A0], r12
0x180008e60  mov     rax, [rsi]
0x180008e63  lea     rdx, [rbp+90h+var_A0]
0x180008e67  mov     rcx, rsi
0x180008e6a  mov     rax, [rax+30h]
0x180008e6e  call    cs:__guard_dispatch_icall_fptr
0x180008e74  test    eax, eax
0x180008e76  js      loc_18000984F
0x180008e7c  mov     rdi, [rbp+90h+var_A0]
0x180008e80  mov     [rsp+190h+var_168], rdi
0x180008e85  or      r13d, 10h
0x180008e89  mov     dword ptr [rsp+190h+var_170], r13d
0x180008e8e  mov     [rbp+90h+lpMem], r12
0x180008e92  mov     rax, [rdi]
0x180008e95  lea     rdx, [rbp+90h+lpMem]
0x180008e99  mov     rcx, rdi
0x180008e9c  mov     rax, [rax+68h]
0x180008ea0  call    cs:__guard_dispatch_icall_fptr
0x180008ea6  test    eax, eax
0x180008ea8  js      loc_180009844
0x180008eae  or      r13d, 20h
0x180008eb2  mov     dword ptr [rsp+190h+var_170], r13d
0x180008eb7  mov     rax, [rbx]
0x180008eba  test    rax, rax
0x180008ebd  jz      short loc_180008EC8
0x180008ebf  mov     ecx, [rax+4]
0x180008ec2  mov     rdx, [rax+10h]
0x180008ec6  jmp     short loc_180008ED2
0x180008ec8  mov     rcx, r12
0x180008ecb  lea     rdx, Src; S2
0x180008ed2  mov     rbx, [rbp+90h+lpMem]
0x180008ed6  test    rbx, rbx
0x180008ed9  jz      short loc_180008EE5
0x180008edb  mov     r8d, [rbx+4]
0x180008edf  mov     rax, [rbx+10h]
0x180008ee3  jmp     short loc_180008EEF
0x180008ee5  mov     r8, r12; N
0x180008ee8  lea     rax, Src
0x180008eef  cmp     r8, rcx
0x180008ef2  jz      short loc_180008EF9
0x180008ef4  xor     r14b, r14b
0x180008ef7  jmp     short loc_180008F11
0x180008ef9  test    r8, r8
0x180008efc  jnz     short loc_180008F03
0x180008efe  mov     r14b, 1
0x180008f01  jmp     short loc_180008F11
0x180008f03  mov     rcx, rax; S1
0x180008f06  call    wmemcmp
0x180008f0b  test    eax, eax
0x180008f0d  setz    r14b
0x180008f11  test    rbx, rbx
0x180008f14  jz      short loc_180008F46
0x180008f16  mov     eax, 0FFFFFFFFh
0x180008f1b  lock xadd [rbx+18h], eax
0x180008f20  sub     eax, 1
0x180008f23  jnz     short loc_180008F3A
0x180008f25  call    WINRT_IMPL_GetProcessHeap
0x180008f2a  mov     rcx, rax; hHeap
0x180008f2d  mov     r8, [rbp+90h+lpMem]; lpMem
0x180008f31  xor     edx, edx; dwFlags
0x180008f33  call    WINRT_IMPL_HeapFree
0x180008f38  jmp     short loc_180008F3E
0x180008f3a  test    eax, eax
0x180008f3c  js      short loc_180008F8F
0x180008f3e  mov     rdi, [rbp+90h+var_A0]
0x180008f42  mov     rsi, [rbp+90h+var_98]
0x180008f46  test    rdi, rdi
0x180008f49  jz      short loc_180008F56
0x180008f4b  lea     rcx, [rsp+190h+var_168]
0x180008f50  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180008f55  nop
0x180008f56  test    rsi, rsi
0x180008f59  jz      short loc_180008F64
0x180008f5b  lea     rcx, [rbp+90h+var_90]
0x180008f5f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180008f64  test    r14b, r14b
0x180008f67  jnz     short loc_180008F96
0x180008f69  cmp     [rbp+90h+var_60], 0
0x180008f6e  jz      short loc_180008F79
0x180008f70  lea     rcx, [rbp+90h+var_60]
0x180008f74  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180008f79  inc     r15d
0x180008f7c  cmp     r15d, dword ptr [rbp+90h+var_A8]
0x180008f80  jz      loc_180009759
0x180008f86  mov     rbx, [rbp+90h+var_58]
0x180008f8a  jmp     loc_180008DF0
0x180008f8f  call    cs:__imp_abort
0x180008f96  mov     [rbp+90h+lpMem], r12
0x180008f9a  mov     rcx, [rbp+90h+var_60]
0x180008f9e  mov     rax, [rcx]
0x180008fa1  lea     rdx, [rbp+90h+lpMem]
0x180008fa5  mov     rax, [rax+50h]
0x180008fa9  call    cs:__guard_dispatch_icall_fptr
0x180008faf  test    eax, eax
0x180008fb1  js      loc_18000980D
0x180008fb7  mov     rcx, [rbp+90h+lpMem]
0x180008fbb  mov     [rbp+90h+var_B8], rcx
0x180008fbf  or      r13d, 40h
0x180008fc3  mov     [rsp+190h+var_138], 1
0x180008fcb  mov     [rsp+190h+var_134], 16h
0x180008fd3  lea     rax, aTransitivedepe; "TransitiveDependencies"
0x180008fda  mov     [rsp+190h+var_128], rax
0x180008fdf  lea     rax, [rsp+190h+var_138]
0x180008fe4  mov     [rsp+190h+var_140], rax
0x180008fe9  mov     rax, r12
0x180008fec  mov     [rbp+90h+var_98], rax
0x180008ff0  bts     r13d, 7
0x180008ff5  mov     dword ptr [rsp+190h+var_170], r13d
0x180008ffa  test    rcx, rcx
0x180008ffd  jnz     short loc_180009004
0x180008fff  mov     rbx, r12
0x180009002  jmp     short loc_18000902B
0x180009004  mov     [rbp+90h+var_88], r12
0x180009008  mov     rcx, [rbp+90h+lpMem]
0x18000900c  mov     rax, [rcx]
0x18000900f  lea     r8, [rbp+90h+var_88]
0x180009013  lea     rdx, ??$guid_v@U?$IMap@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>>
0x18000901a  mov     rax, [rax]
0x18000901d  call    cs:__guard_dispatch_icall_fptr
0x180009023  mov     rbx, [rbp+90h+var_88]
0x180009027  mov     rax, [rbp+90h+var_98]
0x18000902b  mov     [rbp+90h+var_88], rbx
0x18000902f  mov     rcx, [rbx]
0x180009032  mov     rdi, [rcx+30h]
0x180009036  test    rax, rax
0x180009039  jz      short loc_180009044
0x18000903b  lea     rcx, [rbp+90h+var_98]
0x18000903f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180009044  lea     r8, [rbp+90h+var_98]
0x180009048  mov     rdx, [rsp+190h+var_140]
0x18000904d  mov     rcx, rbx
0x180009050  mov     rax, rdi
0x180009053  call    cs:__guard_dispatch_icall_fptr
0x180009059  cmp     eax, 8000000Bh
0x18000905e  jz      short loc_180009076
0x180009060  cmp     eax, 80004005h
0x180009065  jz      short loc_180009076
0x180009067  cmp     eax, 80070002h
0x18000906c  jz      short loc_180009076
0x18000906e  test    eax, eax
0x180009070  js      loc_180009818
0x180009076  lea     rcx, [rbp+90h+var_88]
0x18000907a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000907f  mov     rax, [rbp+90h+var_98]
0x180009083  test    rax, rax
0x180009086  jz      loc_180009729
0x18000908c  mov     [rbp+90h+var_88], r12
0x180009090  mov     rcx, [rax]
0x180009093  mov     r9, [rcx]
0x180009096  lea     r8, [rbp+90h+var_88]
0x18000909a  lea     rdx, ??$guid_v@U?$IMap@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>>
0x1800090a1  mov     rcx, rax
0x1800090a4  mov     rax, r9
0x1800090a7  call    cs:__guard_dispatch_icall_fptr
0x1800090ad  mov     rcx, [rbp+90h+var_88]
0x1800090b1  mov     [rbp+90h+var_C0], rcx
0x1800090b5  test    rcx, rcx
0x1800090b8  jz      loc_180009715
0x1800090be  mov     [rsp+190h+var_138], 1
0x1800090c6  mov     [rsp+190h+var_134], 14h
0x1800090ce  lea     rax, aTransitivedepe_0; "TransitiveDependency"
0x1800090d5  mov     [rsp+190h+var_128], rax
0x1800090da  lea     rax, [rsp+190h+var_138]
0x1800090df  mov     [rsp+190h+var_140], rax
0x1800090e4  mov     [rbp+90h+var_A0], r12
0x1800090e8  bts     r13d, 0Dh
0x1800090ed  mov     dword ptr [rsp+190h+var_170], r13d
0x1800090f2  mov     rax, [rcx]
0x1800090f5  lea     r8, [rbp+90h+var_A0]
0x1800090f9  lea     rdx, [rsp+190h+var_138]
0x1800090fe  mov     rax, [rax+30h]
0x180009102  call    cs:__guard_dispatch_icall_fptr
0x180009108  cmp     eax, 8000000Bh
0x18000910d  jz      short loc_180009125
0x18000910f  cmp     eax, 80004005h
0x180009114  jz      short loc_180009125
0x180009116  cmp     eax, 80070002h
0x18000911b  jz      short loc_180009125
0x18000911d  test    eax, eax
0x18000911f  js      loc_180009823
0x180009125  cmp     [rbp+90h+var_A0], 0
0x18000912a  jnz     short loc_180009139
0x18000912c  mov     r15, r12
0x18000912f  mov     [rsp+190h+var_168], r12
0x180009134  mov     rbx, r12
  ... truncated ...
```
