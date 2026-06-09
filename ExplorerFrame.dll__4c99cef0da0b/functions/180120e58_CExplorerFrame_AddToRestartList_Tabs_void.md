# CExplorerFrame::AddToRestartList_Tabs(void)

- ea: `0x180120e58`
- end: `0x180121e75`
- name: `?AddToRestartList_Tabs@CExplorerFrame@@AEAAJXZ`
- size: `4125`
- prototype: `__int64 __fastcall(CExplorerFrame *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801107d0`

## callees

- `0x1800218fc`
- `0x180022248`
- `0x18002310c`
- `0x1800235e8`
- `0x1800340a0`
- `0x18004c754`
- `0x1800688b0`
- `0x1800739e4`
- `0x1800949cc`
- `0x1800d5974`
- `0x180108840`
- `0x180115a20`
- `0x180120e58`
- `0x180121e7c`
- `0x180121ea4`
- `0x180121f78`
- `0x18013f7d0`
- `0x18018e314`
- `0x18018e374`
- `0x18018e39c`
- `0x18018f7c0`
- `0x1801959dc`
- `0x18019d164`
- `0x180210010`

## import_xrefs

- `SHCORE!SHOpenRegStream2W` at `0x180120fe4`
- `SHCORE!SHOpenRegStream2W` at `0x180120fe4`
- `SHELL32!SHGetIDListFromObject` at `0x180121544`
- `SHELL32!SHGetIDListFromObject` at `0x180121544`
- `SHELL32!__imp_ILSaveToStream` at `0x180121bdd`
- `SHELL32!__imp_ILSaveToStream` at `0x180121bdd`
- `SHLWAPI!__imp_SHGetShellKeyEx` at `0x180120edb`
- `SHLWAPI!__imp_SHGetShellKeyEx` at `0x180120edb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18012103a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180121108`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180121274`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1801213ab`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1801214aa`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180121609`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180121728`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180121889`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180121992`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180121b59`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180121c63`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180121d6e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18012103a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180121108`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180121274`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1801213ab`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1801214aa`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180121609`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180121728`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180121889`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180121992`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180121b59`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180121c63`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180121d6e`
- `USER32!GetWindowRect` at `0x180121aa3`
- `USER32!GetWindowRect` at `0x180121aa3`
- `USER32!GetWindowPlacement` at `0x180121a3d`
- `USER32!GetWindowPlacement` at `0x180121a3d`

## string_xrefs

- `0x180120ed1`: `RestartCommandsTabs`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall CExplorerFrame::AddToRestartList_Tabs(CExplorerFrame *this)
{
  HKEY v2; // rax
  bool v3; // r14
  __int64 v4; // rdi
  int v5; // eax
  unsigned int v6; // edi
  IStream *v8; // rax
  IStream *v9; // rdi
  __int64 v10; // rbx
  int v11; // eax
  HRESULT v12; // r14d
  __int64 v13; // rbx
  const struct FEBrowserTab *v14; // r15
  const struct FEBrowserTab *v15; // r12
  __int64 (__fastcall **v16)(_QWORD, GUID *, __int64 **); // rax
  int v17; // eax
  __int64 v18; // rdi
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rdi
  __int64 v22; // rdi
  __int64 v23; // rdi
  __int64 v24; // rdi
  __int64 v25; // rax
  __int64 v26; // rdi
  int v27; // eax
  __int64 v28; // rdi
  int v29; // eax
  unsigned int v30; // esi
  __int64 v31; // rdi
  LPCITEMIDLIST *v32; // rsi
  LPCITEMIDLIST *v33; // r15
  HRESULT v34; // eax
  __int64 v35; // rdi
  int v36; // eax
  __int64 v37; // rdi
  int v38; // [rsp+20h] [rbp-228h]
  HKEY hkey; // [rsp+30h] [rbp-218h] BYREF
  struct _ITEMIDLIST_ABSOLUTE *v40; // [rsp+38h] [rbp-210h] BYREF
  LPCITEMIDLIST *v41; // [rsp+40h] [rbp-208h] BYREF
  __int128 v42; // [rsp+48h] [rbp-200h]
  IStream *v43; // [rsp+58h] [rbp-1F0h] BYREF
  int v44; // [rsp+60h] [rbp-1E8h] BYREF
  IUnknown *punk; // [rsp+68h] [rbp-1E0h] BYREF
  __int64 *v46; // [rsp+70h] [rbp-1D8h] BYREF
  int v47; // [rsp+78h] [rbp-1D0h] BYREF
  _BYTE v48[56]; // [rsp+80h] [rbp-1C8h] BYREF
  __int64 v49; // [rsp+B8h] [rbp-190h]
  struct _ITEMIDLIST_ABSOLUTE **v50; // [rsp+C0h] [rbp-188h] BYREF
  LPITEMIDLIST ppidl; // [rsp+C8h] [rbp-180h] BYREF
  char v52; // [rsp+D0h] [rbp-178h]
  _BYTE *v53; // [rsp+D8h] [rbp-170h]
  char v54; // [rsp+E0h] [rbp-168h]
  HKEY *p_hkey; // [rsp+E8h] [rbp-160h]
  WCHAR *v56; // [rsp+F0h] [rbp-158h]
  _BYTE *v57; // [rsp+F8h] [rbp-150h]
  char v58; // [rsp+100h] [rbp-148h]
  struct tagRECT Rect; // [rsp+108h] [rbp-140h] BYREF
  _QWORD v60[2]; // [rsp+118h] [rbp-130h] BYREF
  __int64 v61; // [rsp+128h] [rbp-120h]
  __int64 v62; // [rsp+130h] [rbp-118h]
  WINDOWPLACEMENT wndpl; // [rsp+140h] [rbp-108h] BYREF
  WCHAR pszValue[80]; // [rsp+170h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  v40 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::start_and_watch_errors(
    &v40,
    v48);
  wil::com_ptr_t<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>,wil::err_returncode_policy>(&v40);
  v53 = v48;
  v54 = 1;
  LODWORD(v2) = SHGetShellKeyEx((LPCWSTR)1);
  hkey = v2;
  v3 = v2 != 0;
  v4 = v49;
  v40 = (struct _ITEMIDLIST_ABSOLUTE *)v49;
  if ( v49 )
    _InterlockedAdd((volatile signed __int32 *)(v49 + 280), 1u);
  tip2::details::shared_data<0,0,0>::begin_update(v4 + 8);
  *(_BYTE *)(v4 + 272) = v3;
  tip2::test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(&v40);
  if ( !hkey )
    goto LABEL_122;
  v5 = StringCchPrintfW(pszValue, 0x50u, L"%d", *((unsigned int *)this + 2));
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1519,
      (unsigned int)"shell\\explorerframe\\explorerframep.cpp",
      (const char *)(unsigned int)v5,
      v38);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    tip2::details::shared_data<0,0,0>::complete_without_lock(v49 + 8);
    tip2::test_watcher<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_watcher<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(v48);
    return v6;
  }
  p_hkey = &hkey;
  v56 = pszValue;
  v57 = v48;
  v58 = 1;
  v8 = SHOpenRegStream2W(hkey, 0, pszValue, 1u);
  v9 = v8;
  v43 = v8;
  if ( !v8 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1525,
      (unsigned int)"shell\\explorerframe\\explorerframep.cpp",
      (const char *)0x8007000ELL,
      v38);
    ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&v43);
    if ( hkey )
    {
      RegDeleteValueW(hkey, pszValue);
      v10 = v49;
      v40 = (struct _ITEMIDLIST_ABSOLUTE *)v49;
      if ( v49 )
        _InterlockedAdd((volatile signed __int32 *)(v49 + 280), 1u);
      tip2::details::shared_data<0,0,0>::begin_update(v10 + 8);
      *(_BYTE *)(v10 + 273) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(&v40);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    tip2::details::shared_data<0,0,0>::complete_without_lock(v49 + 8);
    tip2::test_watcher<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_watcher<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(v48);
    return 2147942414LL;
  }
  v11 = (*(__int64 (__fastcall **)(IStream *, __int64 *, __int64))(*(_QWORD *)v8 + 32LL))(v8, &qword_180248660, 2);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1526,
      (unsigned int)"shell\\explorerframe\\explorerframep.cpp",
      (const char *)(unsigned int)v11,
      v38);
    ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&v43);
    if ( hkey )
    {
      RegDeleteValueW(hkey, pszValue);
      v13 = v49;
      v40 = (struct _ITEMIDLIST_ABSOLUTE *)v49;
      if ( v49 )
        _InterlockedAdd((volatile signed __int32 *)(v49 + 280), 1u);
      tip2::details::shared_data<0,0,0>::begin_update(v13 + 8);
      *(_BYTE *)(v13 + 273) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(&v40);
    }
    goto LABEL_109;
  }
  v47 = 0;
  v44 = 0;
  std::vector<unsigned short const *>::vector<unsigned short const *>(&v41);
  v14 = (const struct FEBrowserTab *)*((_QWORD *)this + 82);
  v15 = (const struct FEBrowserTab *)*((_QWORD *)this + 83);
  while ( v14 != v15 )
  {
    FEBrowserTab::FEBrowserTab((FEBrowserTab *)v60, v14);
    v46 = 0;
    v16 = *(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 **))v60[0];
    v46 = 0;
    v17 = (*v16)(v60[0], &GUID_b965e203_2a6a_4e2e_a15d_cecd736f12b2, &v46);
    v12 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x152D,
        (unsigned int)"shell\\explorerframe\\explorerframep.cpp",
        (const char *)(unsigned int)v17,
        v38);
      ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&v46);
      ShellItemData::~ShellItemData((ShellItemData *)v60);
      if ( v41 )
      {
        std::_Destroy_range<std::allocator<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>>(
          v41,
          v42);
        std::_Deallocate<16>(v41, (*((_QWORD *)&v42 + 1) - (_QWORD)v41) & 0xFFFFFFFFFFFFFFF8uLL);
        v41 = 0;
        v42 = 0;
      }
      ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&v43);
      if ( hkey )
      {
        RegDeleteValueW(hkey, pszValue);
        v18 = v49;
        v43 = (IStream *)v49;
        if ( v49 )
          _InterlockedIncrement((volatile signed __int32 *)(v49 + 280));
        tip2::details::shared_data<0,0,0>::begin_update(v18 + 8);
        *(_BYTE *)(v18 + 273) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(&v43);
      }
      goto LABEL_109;
    }
    punk = 0;
    v19 = *v46;
    punk = 0;
    v20 = (*(__int64 (__fastcall **)(__int64 *, GUID *, IUnknown **))(v19 + 56))(
            v46,
            &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
            &punk);
    v12 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x152F,
        (unsigned int)"shell\\explorerframe\\explorerframep.cpp",
        (const char *)(unsigned int)v20,
        v38);
      ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&punk);
      ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&v46);
      ShellItemData::~ShellItemData((ShellItemData *)v60);
      if ( v41 )
      {
        std::_Destroy_range<std::allocator<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>>(
          v41,
          v42);
        std::_Deallocate<16>(v41, (*((_QWORD *)&v42 + 1) - (_QWORD)v41) & 0xFFFFFFFFFFFFFFF8uLL);
        v41 = 0;
        v42 = 0;
      }
      ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&v43);
      if ( hkey )
      {
        RegDeleteValueW(hkey, pszValue);
        v21 = v49;
        v43 = (IStream *)v49;
        if ( v49 )
          _InterlockedIncrement((volatile signed __int32 *)(v49 + 280));
        tip2::details::shared_data<0,0,0>::begin_update(v21 + 8);
        *(_BYTE *)(v21 + 273) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(&v43);
      }
      goto LABEL_109;
    }
    if ( (unsigned int)IsBrowserFrameOptionsSet(punk, 0x2000) )
    {
      ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&punk);
      ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&v46);
      ShellItemData::~ShellItemData((ShellItemData *)v60);
      if ( v41 )
      {
        std::_Destroy_range<std::allocator<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>>(
          v41,
          v42);
        std::_Deallocate<16>(v41, (*((_QWORD *)&v42 + 1) - (_QWORD)v41) & 0xFFFFFFFFFFFFFFF8uLL);
        v41 = 0;
        v42 = 0;
      }
      ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&v43);
      if ( hkey )
      {
        RegDeleteValueW(hkey, pszValue);
        v22 = v49;
        v43 = (IStream *)v49;
        if ( v49 )
          _InterlockedIncrement((volatile signed __int32 *)(v49 + 280));
        tip2::details::shared_data<0,0,0>::begin_update(v22 + 8);
        *(_BYTE *)(v22 + 273) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(&v43);
      }
      goto LABEL_122;
    }
    v40 = 0;
    v50 = &v40;
    ppidl = 0;
    v52 = 1;
    v12 = SHGetIDListFromObject(punk, &ppidl);
    wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v50);
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1535,
        (unsigned int)"shell\\explorerframe\\explorerframep.cpp",
        (const char *)(unsigned int)v12,
        v38);
      wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &v40,
        0);
      ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&punk);
      ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&v46);
      ShellItemData::~ShellItemData((ShellItemData *)v60);
      if ( v41 )
      {
        std::_Destroy_range<std::allocator<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>>(
          v41,
          v42);
        std::_Deallocate<16>(v41, (*((_QWORD *)&v42 + 1) - (_QWORD)v41) & 0xFFFFFFFFFFFFFFF8uLL);
        v41 = 0;
        v42 = 0;
      }
      ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&v43);
      if ( hkey )
      {
        RegDeleteValueW(hkey, pszValue);
        v23 = v49;
        v43 = (IStream *)v49;
        if ( v49 )
          _InterlockedIncrement((volatile signed __int32 *)(v49 + 280));
        tip2::details::shared_data<0,0,0>::begin_update(v23 + 8);
        *(_BYTE *)(v23 + 273) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(&v43);
      }
      goto LABEL_109;
    }
    if ( IsPidlOnNonPersistentDrive(v40) )
    {
      if ( *((_QWORD *)this + 83) - *((_QWORD *)this + 82) == 40 )
      {
        wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &v40,
          0);
        ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&punk);
        ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&v46);
        ShellItemData::~ShellItemData((ShellItemData *)v60);
        if ( v41 )
        {
          std::_Destroy_range<std::allocator<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>>(
            v41,
            v42);
          std::_Deallocate<16>(v41, (*((_QWORD *)&v42 + 1) - (_QWORD)v41) & 0xFFFFFFFFFFFFFFF8uLL);
          v41 = 0;
          v42 = 0;
        }
        ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&v43);
        if ( hkey )
        {
          RegDeleteValueW(hkey, pszValue);
          v24 = v49;
          v43 = (IStream *)v49;
          if ( v49 )
            _InterlockedIncrement((volatile signed __int32 *)(v49 + 280));
          tip2::details::shared_data<0,0,0>::begin_update(v24 + 8);
          *(_BYTE *)(v24 + 273) = 1;
          tip2::test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(&v43);
        }
        goto LABEL_122;
      }
    }
    else
    {
      if ( (_QWORD)v42 == *((_QWORD *)&v42 + 1) )
        std::vector<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Emplace_reallocate<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(
          &v41,
          v42,
          &v40);
      else
        std::vector<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Emplace_back_with_unused_capacity<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(
          &v41,
          &v40);
      v25 = v61 - *((_QWORD *)this + 87);
      if ( v61 == *((_QWORD *)this + 87) )
        v25 = v62 - *((_QWORD *)this + 88);
      if ( !v25 )
        v47 = v44;
      ++v44;
    }
    wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &v40,
      0);
    ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&punk);
    ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&v46);
    ShellItemData::~ShellItemData((ShellItemData *)v60);
    v14 = (const struct FEBrowserTab *)((char *)v14 + 40);
  }
  if ( !v44 )
  {
    if ( v41 )
    {
      std::_Destroy_range<std::allocator<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>>(
        v41,
        v42);
      std::_Deallocate<16>(v41, (*((_QWORD *)&v42 + 1) - (_QWORD)v41) & 0xFFFFFFFFFFFFFFF8uLL);
      v41 = 0;
      v42 = 0;
    }
    ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&v43);
    if ( hkey )
    {
      RegDeleteValueW(hkey, pszValue);
      v26 = v49;
      v40 = (struct _ITEMIDLIST_ABSOLUTE *)v49;
      if ( v49 )
        _InterlockedIncrement((volatile signed __int32 *)(v49 + 280));
      tip2::details::shared_data<0,0,0>::begin_update(v26 + 8);
      *(_BYTE *)(v26 + 273) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(&v40);
    }
LABEL_122:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    tip2::details::shared_data<0,0,0>::complete_without_lock(v49 + 8);
    tip2::test_watcher<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_watcher<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(v48);
    return 0;
  }
  v27 = (*(__int64 (__fastcall **)(IStream *, int *, __int64))(*(_QWORD *)v9 + 32LL))(v9, &v44, 4);
  v12 = v27;
  if ( v27 >= 0 )
  {
    Rect = 0;
    wndpl.length = 44;
    memset(&wndpl.flags, 0, 40);
    if ( GetWindowPlacement(*((HWND *)this + 1), &wndpl) && wndpl.showCmd == 2 )
    {
      Rect = wndpl.rcNormalPosition;
    }
    else if ( (*((_DWORD *)this + 118) & 0x100) != 0 )
    {
      Rect = (struct tagRECT)_mm_load_si128((const __m128i *)&_xmm);
    }
    else
    {
      GetWindowRect(*((HWND *)this + 1), &Rect);
    }
    v29 = (*(__int64 (__fastcall **)(IStream *, struct tagRECT *, __int64))(*(_QWORD *)v9 + 32LL))(v9, &Rect, 16);
    v30 = v29;
    if ( v29 >= 0 )
    {
      v32 = v41;
      v33 = (LPCITEMIDLIST *)v42;
      while ( v32 != v33 )
      {
        v34 = ILSaveToStream(v9, *v32);
        v12 = v34;
        if ( v34 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x155E,
            (unsigned int)"shell\\explorerframe\\explorerframep.cpp",
            (const char *)(unsigned int)v34,
            v38);
          if ( v41 )
          {
            std::_Destroy_range<std::allocator<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>>(
              v41,
              v42);
            std::_Deallocate<16>(v41, (*((_QWORD *)&v42 + 1) - (_QWORD)v41) & 0xFFFFFFFFFFFFFFF8uLL);
            v41 = 0;
            v42 = 0;
          }
          ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&v43);
          if ( hkey )
          {
            RegDeleteValueW(hkey, pszValue);
            v35 = v49;
            v40 = (struct _ITEMIDLIST_ABSOLUTE *)v49;
            if ( v49 )
              _InterlockedIncrement((volatile signed __int32 *)(v49 + 280));
            tip2::details::shared_data<0,0,0>::begin_update(v35 + 8);
            *(_BYTE *)(v35 + 273) = 1;
            tip2::test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(&v40);
          }
          goto LABEL_109;
        }
        ++v32;
      }
      v36 = (*(__int64 (__fastcall **)(IStream *, int *, __int64, _QWORD))(*(_QWORD *)v9 + 32LL))(v9, &v47, 4, 0);
      v30 = v36;
      if ( v36 >= 0 )
      {
        if ( v41 )
        {
          std::_Destroy_range<std::allocator<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>>(
            v41,
            v42);
          std::_Deallocate<16>(v41, (*((_QWORD *)&v42 + 1) - (_QWORD)v41) & 0xFFFFFFFFFFFFFFF8uLL);
          v41 = 0;
          v42 = 0;
        }
        ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&v43);
        goto LABEL_122;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1560,
        (unsigned int)"shell\\explorerframe\\explorerframep.cpp",
        (const char *)(unsigned int)v36,
        v38);
      if ( v41 )
      {
        std::_Destroy_range<std::allocator<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>>(
          v41,
          v42);
        std::_Deallocate<16>(v41, (*((_QWORD *)&v42 + 1) - (_QWORD)v41) & 0xFFFFFFFFFFFFFFF8uLL);
        v41 = 0;
        v42 = 0;
      }
      ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&v43);
      if ( hkey )
      {
        RegDeleteValueW(hkey, pszValue);
        v37 = v49;
        v40 = (struct _ITEMIDLIST_ABSOLUTE *)v49;
        if ( v49 )
          _InterlockedIncrement((volatile signed __int32 *)(v49 + 280));
        tip2::details::shared_data<0,0,0>::begin_update(v37 + 8);
        *(_BYTE *)(v37 + 273) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(&v40);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x155B,
        (unsigned int)"shell\\explorerframe\\explorerframep.cpp",
        (const char *)(unsigned int)v29,
        v38);
      if ( v41 )
      {
        std::_Destroy_range<std::allocator<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>>(
          v41,
          v42);
        std::_Deallocate<16>(v41, (*((_QWORD *)&v42 + 1) - (_QWORD)v41) & 0xFFFFFFFFFFFFFFF8uLL);
        v41 = 0;
        v42 = 0;
      }
      ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&v43);
      if ( hkey )
      {
        RegDeleteValueW(hkey, pszValue);
        v31 = v49;
        v40 = (struct _ITEMIDLIST_ABSOLUTE *)v49;
        if ( v49 )
          _InterlockedIncrement((volatile signed __int32 *)(v49 + 280));
        tip2::details::shared_data<0,0,0>::begin_update(v31 + 8);
        *(_BYTE *)(v31 + 273) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(&v40);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    tip2::details::shared_data<0,0,0>::complete_without_lock(v49 + 8);
    tip2::test_watcher<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_watcher<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(v48);
    return v30;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x154B,
    (unsigned int)"shell\\explorerframe\\explorerframep.cpp",
    (const char *)(unsigned int)v27,
    v38);
  if ( v41 )
  {
    std::_Destroy_range<std::allocator<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>>(
      v41,
      v42);
    std::_Deallocate<16>(v41, (*((_QWORD *)&v42 + 1) - (_QWORD)v41) & 0xFFFFFFFFFFFFFFF8uLL);
    v41 = 0;
    v42 = 0;
  }
  ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&v43);
  if ( hkey )
  {
    RegDeleteValueW(hkey, pszValue);
    v28 = v49;
    v40 = (struct _ITEMIDLIST_ABSOLUTE *)v49;
    if ( v49 )
      _InterlockedIncrement((volatile signed __int32 *)(v49 + 280));
    tip2::details::shared_data<0,0,0>::begin_update(v28 + 8);
    *(_BYTE *)(v28 + 273) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(&v40);
  }
LABEL_109:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  tip2::details::shared_data<0,0,0>::complete_without_lock(v49 + 8);
  tip2::test_watcher<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_watcher<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(v48);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180120e58  mov     [rsp+arg_8], rbx
0x180120e5d  mov     [rsp+arg_10], rsi
0x180120e62  push    rdi
0x180120e63  push    r12
0x180120e65  push    r13
0x180120e67  push    r14
0x180120e69  push    r15
0x180120e6b  sub     rsp, 220h
0x180120e72  mov     rax, cs:__security_cookie
0x180120e79  xor     rax, rsp
0x180120e7c  mov     [rsp+248h+var_38], rax
0x180120e84  mov     rsi, rcx
0x180120e87  xor     r13d, r13d
0x180120e8a  mov     [rsp+248h+var_210], r13
0x180120e8f  lea     rdx, [rsp+248h+var_1C8]
0x180120e97  lea     rcx, [rsp+248h+var_210]
0x180120e9c  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_AddToRestartListTabsTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_AddToRestartListTabsTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::start_and_watch_errors(void)
0x180120ea1  lea     rcx, [rsp+248h+var_210]
0x180120ea6  call    ??1?$com_ptr_t@V?$merged_data@U_tip_AddToRestartListTabsTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>,wil::err_returncode_policy>(void)
0x180120eab  nop
0x180120eac  lea     rbx, [rsp+248h+var_1C8]
0x180120eb4  mov     [rsp+248h+var_170], rbx
0x180120ebc  lea     r15d, [r13+1]
0x180120ec0  mov     [rsp+248h+var_168], r15b
0x180120ec8  mov     r9d, 2001Fh
0x180120ece  mov     r8d, r15d
0x180120ed1  lea     rdx, aRestartcommand_0; "RestartCommandsTabs"
0x180120ed8  mov     ecx, r15d; pszPath
0x180120edb  call    cs:__imp_SHGetShellKeyEx
0x180120ee1  mov     [rsp+248h+hkey], rax
0x180120ee6  test    rax, rax
0x180120ee9  setnz   r14b
0x180120eed  mov     rdi, [rsp+248h+var_190]
0x180120ef5  mov     [rsp+248h+var_210], rdi
0x180120efa  test    rdi, rdi
0x180120efd  jz      short loc_180120F07
0x180120eff  lock add [rdi+118h], r15d
0x180120f07  lea     rcx, [rdi+8]
0x180120f0b  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x180120f10  mov     [rdi+110h], r14b
0x180120f17  lea     rcx, [rsp+248h+var_210]
0x180120f1c  call    ??1?$test_data_control@V?$merged_data@U_tip_AddToRestartListTabsTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(void)
0x180120f21  cmp     [rsp+248h+hkey], r13
0x180120f26  jz      loc_180121E19
0x180120f2c  mov     r9d, [rsi+8]
0x180120f30  lea     r8, aD; "%d"
0x180120f37  mov     edx, 50h ; 'P'; unsigned __int64
0x180120f3c  lea     rcx, [rsp+248h+pszValue]; unsigned __int16 *
0x180120f44  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180120f49  mov     edi, eax
0x180120f4b  test    eax, eax
0x180120f4d  jns     short loc_180120F9D
0x180120f4f  mov     rcx, [rsp+248h]; this
0x180120f57  mov     r9d, eax; char *
0x180120f5a  lea     r8, aShellExplorerf_10; "shell\\explorerframe\\explorerframep.cp"...
0x180120f61  mov     edx, 1519h; void *
0x180120f66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180120f6b  nop
0x180120f6c  lea     rcx, [rsp+248h+hkey]
0x180120f71  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180120f76  nop
0x180120f77  mov     rcx, [rsp+248h+var_190]
0x180120f7f  add     rcx, 8
0x180120f83  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x180120f88  nop
0x180120f89  lea     rcx, [rsp+248h+var_1C8]
0x180120f91  call    ??1?$test_watcher@V?$merged_data@U_tip_AddToRestartListTabsTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_watcher<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(void)
0x180120f96  mov     eax, edi
0x180120f98  jmp     loc_180121E47
0x180120f9d  lea     rax, [rsp+248h+hkey]
0x180120fa2  mov     [rsp+248h+var_160], rax
0x180120faa  lea     rax, [rsp+248h+pszValue]
0x180120fb2  mov     [rsp+248h+var_158], rax
0x180120fba  lea     rax, [rsp+248h+var_1C8]
0x180120fc2  mov     [rsp+248h+var_150], rax
0x180120fca  mov     [rsp+248h+var_148], r15b
0x180120fd2  mov     r9d, r15d; grfMode
0x180120fd5  lea     r8, [rsp+248h+pszValue]; pszValue
0x180120fdd  xor     edx, edx; pszSubkey
0x180120fdf  mov     rcx, [rsp+248h+hkey]; hkey
0x180120fe4  call    cs:__imp_SHOpenRegStream2W
0x180120fea  mov     rdi, rax
0x180120fed  mov     [rsp+248h+var_1F0], rax
0x180120ff2  test    rax, rax
0x180120ff5  jnz     loc_1801210A6
0x180120ffb  mov     rcx, [rsp+248h]; this
0x180121003  mov     edi, 8007000Eh
0x180121008  mov     r9d, edi; char *
0x18012100b  lea     r8, aShellExplorerf_10; "shell\\explorerframe\\explorerframep.cp"...
0x180121012  mov     edx, 1525h; void *
0x180121017  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012101c  nop
0x18012101d  lea     rcx, [rsp+248h+var_1F0]
0x180121022  call    ??1?$CComPtrBase@UISearchIDListFactory@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(void)
0x180121027  nop
0x180121028  mov     rcx, [rsp+248h+hkey]; hKey
0x18012102d  test    rcx, rcx
0x180121030  jz      short loc_180121075
0x180121032  lea     rdx, [rsp+248h+pszValue]; lpValueName
0x18012103a  call    cs:__imp_RegDeleteValueW
0x180121040  mov     rbx, [rsp+248h+var_190]
0x180121048  mov     [rsp+248h+var_210], rbx
0x18012104d  test    rbx, rbx
0x180121050  jz      short loc_18012105A
0x180121052  lock add [rbx+118h], r15d
0x18012105a  lea     rcx, [rbx+8]
0x18012105e  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x180121063  mov     [rbx+111h], r15b
0x18012106a  lea     rcx, [rsp+248h+var_210]
0x18012106f  call    ??1?$test_data_control@V?$merged_data@U_tip_AddToRestartListTabsTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(void)
0x180121074  nop
0x180121075  lea     rcx, [rsp+248h+hkey]
0x18012107a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012107f  nop
0x180121080  mov     rcx, [rsp+248h+var_190]
0x180121088  add     rcx, 8
0x18012108c  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x180121091  nop
0x180121092  lea     rcx, [rsp+248h+var_1C8]
0x18012109a  call    ??1?$test_watcher@V?$merged_data@U_tip_AddToRestartListTabsTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_watcher<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(void)
0x18012109f  mov     eax, edi
0x1801210a1  jmp     loc_180121E47
0x1801210a6  mov     rax, [rax]
0x1801210a9  xor     r9d, r9d
0x1801210ac  lea     r8d, [r9+2]
0x1801210b0  lea     rdx, qword_180248660
0x1801210b7  mov     rcx, rdi
0x1801210ba  mov     rax, [rax+20h]
0x1801210be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801210c3  mov     r14d, eax
0x1801210c6  test    eax, eax
0x1801210c8  jns     loc_180121175
0x1801210ce  mov     rcx, [rsp+248h]; this
0x1801210d6  mov     r9d, eax; char *
0x1801210d9  lea     r8, aShellExplorerf_10; "shell\\explorerframe\\explorerframep.cp"...
0x1801210e0  mov     edx, 1526h; void *
0x1801210e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801210ea  nop
0x1801210eb  lea     rcx, [rsp+248h+var_1F0]
0x1801210f0  call    ??1?$CComPtrBase@UISearchIDListFactory@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(void)
0x1801210f5  nop
0x1801210f6  mov     rcx, [rsp+248h+hkey]; hKey
0x1801210fb  test    rcx, rcx
0x1801210fe  jz      short loc_180121143
0x180121100  lea     rdx, [rsp+248h+pszValue]; lpValueName
0x180121108  call    cs:__imp_RegDeleteValueW
0x18012110e  mov     rbx, [rsp+248h+var_190]
0x180121116  mov     [rsp+248h+var_210], rbx
0x18012111b  test    rbx, rbx
0x18012111e  jz      short loc_180121128
0x180121120  lock add [rbx+118h], r15d
0x180121128  lea     rcx, [rbx+8]
0x18012112c  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x180121131  mov     [rbx+111h], r15b
0x180121138  lea     rcx, [rsp+248h+var_210]
0x18012113d  call    ??1?$test_data_control@V?$merged_data@U_tip_AddToRestartListTabsTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(void)
0x180121142  nop
0x180121143  lea     rcx, [rsp+248h+hkey]
0x180121148  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012114d  nop
0x18012114e  mov     rcx, [rsp+248h+var_190]
0x180121156  add     rcx, 8
0x18012115a  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x18012115f  nop
0x180121160  lea     rcx, [rsp+248h+var_1C8]
0x180121168  call    ??1?$test_watcher@V?$merged_data@U_tip_AddToRestartListTabsTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_watcher<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(void)
0x18012116d  mov     eax, r14d
0x180121170  jmp     loc_180121E47
0x180121175  mov     [rsp+248h+var_1D0], r13d
0x18012117a  mov     [rsp+248h+var_1E8], r13d
0x18012117f  lea     rcx, [rsp+248h+var_208]
0x180121184  call    ??0?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::vector<ushort const *>::vector<ushort const *>(void)
0x180121189  nop
0x18012118a  mov     r15, [rsi+290h]
0x180121191  mov     r12, [rsi+298h]
0x180121198  cmp     r15, r12
0x18012119b  jz      loc_180121826
0x1801211a1  mov     rdx, r15; struct FEBrowserTab *
0x1801211a4  lea     rcx, [rsp+248h+var_130]; this
0x1801211ac  call    ??0FEBrowserTab@@QEAA@AEBU0@@Z; FEBrowserTab::FEBrowserTab(FEBrowserTab const &)
0x1801211b1  nop
0x1801211b2  mov     [rsp+248h+var_1D8], r13
0x1801211b7  mov     rcx, [rsp+248h+var_130]
0x1801211bf  mov     rax, [rcx]
0x1801211c2  mov     [rsp+248h+var_1D8], r13
0x1801211c7  lea     r8, [rsp+248h+var_1D8]
0x1801211cc  lea     rdx, _GUID_b965e203_2a6a_4e2e_a15d_cecd736f12b2
0x1801211d3  mov     rax, [rax]
0x1801211d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801211db  mov     r14d, eax
0x1801211de  test    eax, eax
0x1801211e0  jns     loc_1801212E0
0x1801211e6  mov     rcx, [rsp+248h]; this
0x1801211ee  mov     r9d, eax; char *
0x1801211f1  lea     r8, aShellExplorerf_10; "shell\\explorerframe\\explorerframep.cp"...
0x1801211f8  mov     edx, 152Dh; void *
0x1801211fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180121202  nop
0x180121203  lea     rcx, [rsp+248h+var_1D8]
0x180121208  call    ??1?$CComPtrBase@UISearchIDListFactory@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(void)
0x18012120d  nop
0x18012120e  lea     rcx, [rsp+248h+var_130]; this
0x180121216  call    ??1ShellItemData@@QEAA@XZ; ShellItemData::~ShellItemData(void)
0x18012121b  nop
0x18012121c  mov     rcx, [rsp+248h+var_208]
0x180121221  test    rcx, rcx
0x180121224  jz      short loc_180121254
0x180121226  mov     rdx, qword ptr [rsp+248h+var_200]
0x18012122b  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@YAXPEAV?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAV12@AEAV?$allocator@V?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@0@@Z; std::_Destroy_range<std::allocator<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>>(wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> *,wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> * const,std::allocator<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>> &)
0x180121230  mov     rcx, [rsp+248h+var_208]
0x180121235  mov     rdx, qword ptr [rsp+248h+var_200+8]
0x18012123a  sub     rdx, rcx
0x18012123d  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180121241  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180121246  mov     [rsp+248h+var_208], r13
0x18012124b  xorps   xmm0, xmm0
0x18012124e  movdqu  [rsp+248h+var_200], xmm0
0x180121254  lea     rcx, [rsp+248h+var_1F0]
0x180121259  call    ??1?$CComPtrBase@UISearchIDListFactory@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(void)
0x18012125e  nop
0x18012125f  lea     rcx, [rsp+248h+hkey]
0x180121264  mov     rcx, [rcx]; hKey
0x180121267  test    rcx, rcx
0x18012126a  jz      short loc_1801212B2
0x18012126c  lea     rdx, [rsp+248h+pszValue]; lpValueName
0x180121274  call    cs:__imp_RegDeleteValueW
0x18012127a  lea     rdi, [rsp+248h+var_1C8]
0x180121282  mov     rdi, [rdi+38h]
0x180121286  mov     [rsp+248h+var_1F0], rdi
0x18012128b  test    rdi, rdi
0x18012128e  jz      short loc_180121297
0x180121290  lock inc dword ptr [rdi+118h]
0x180121297  lea     rcx, [rdi+8]
0x18012129b  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x1801212a0  mov     byte ptr [rdi+111h], 1
0x1801212a7  lea     rcx, [rsp+248h+var_1F0]
0x1801212ac  call    ??1?$test_data_control@V?$merged_data@U_tip_AddToRestartListTabsTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(void)
0x1801212b1  nop
0x1801212b2  lea     rcx, [rsp+248h+hkey]
0x1801212b7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801212bc  nop
0x1801212bd  mov     rcx, [rbx+38h]
0x1801212c1  add     rcx, 8
0x1801212c5  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x1801212ca  nop
0x1801212cb  lea     rcx, [rsp+248h+var_1C8]
0x1801212d3  call    ??1?$test_watcher@V?$merged_data@U_tip_AddToRestartListTabsTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>::~test_watcher<tip2::details::merged_data<_tip_AddToRestartListTabsTipTest,_tip_AddToRestartListTabsTipTest>>(void)
0x1801212d8  mov     eax, r14d
0x1801212db  jmp     loc_180121E47
0x1801212e0  mov     [rsp+248h+punk], r13
0x1801212e5  mov     rcx, [rsp+248h+var_1D8]
0x1801212ea  mov     rax, [rcx]
0x1801212ed  mov     [rsp+248h+punk], r13
0x1801212f2  lea     r8, [rsp+248h+punk]
0x1801212f7  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x1801212fe  mov     rax, [rax+38h]
0x180121302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180121307  mov     r14d, eax
0x18012130a  test    eax, eax
0x18012130c  jns     loc_180121417
0x180121312  mov     rcx, [rsp+248h]; this
0x18012131a  mov     r9d, eax; char *
0x18012131d  lea     r8, aShellExplorerf_10; "shell\\explorerframe\\explorerframep.cp"...
0x180121324  mov     edx, 152Fh; void *
0x180121329  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012132e  nop
0x18012132f  lea     rcx, [rsp+248h+punk]
0x180121334  call    ??1?$CComPtrBase@UISearchIDListFactory@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(void)
0x180121339  nop
0x18012133a  lea     rcx, [rsp+248h+var_1D8]
0x18012133f  call    ??1?$CComPtrBase@UISearchIDListFactory@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(void)
0x180121344  nop
0x180121345  lea     rcx, [rsp+248h+var_130]; this
0x18012134d  call    ??1ShellItemData@@QEAA@XZ; ShellItemData::~ShellItemData(void)
0x180121352  nop
0x180121353  mov     rcx, [rsp+248h+var_208]
0x180121358  test    rcx, rcx
0x18012135b  jz      short loc_18012138B
0x18012135d  mov     rdx, qword ptr [rsp+248h+var_200]
0x180121362  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@YAXPEAV?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAV12@AEAV?$allocator@V?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@0@@Z; std::_Destroy_range<std::allocator<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>>(wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> *,wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> * const,std::allocator<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>> &)
0x180121367  mov     rcx, [rsp+248h+var_208]
0x18012136c  mov     rdx, qword ptr [rsp+248h+var_200+8]
0x180121371  sub     rdx, rcx
0x180121374  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180121378  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012137d  mov     [rsp+248h+var_208], r13
0x180121382  xorps   xmm0, xmm0
0x180121385  movdqu  [rsp+248h+var_200], xmm0
0x18012138b  lea     rcx, [rsp+248h+var_1F0]
0x180121390  call    ??1?$CComPtrBase@UISearchIDListFactory@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(void)
0x180121395  nop
0x180121396  lea     rcx, [rsp+248h+hkey]
0x18012139b  mov     rcx, [rcx]; hKey
0x18012139e  test    rcx, rcx
0x1801213a1  jz      short loc_1801213E9
0x1801213a3  lea     rdx, [rsp+248h+pszValue]; lpValueName
0x1801213ab  call    cs:__imp_RegDeleteValueW
0x1801213b1  lea     rdi, [rsp+248h+var_1C8]
0x1801213b9  mov     rdi, [rdi+38h]
0x1801213bd  mov     [rsp+248h+var_1F0], rdi
  ... truncated ...
```
