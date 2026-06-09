# CShellBrowser::_NavigateToPidl(_ITEMIDLIST_ABSOLUTE const *,ulong,ulong)

- ea: `0x18009044c`
- end: `0x180090d33`
- name: `?_NavigateToPidl@CShellBrowser@@AEAAJPEBU_ITEMIDLIST_ABSOLUTE@@KK@Z`
- size: `2279`
- prototype: `__int64 __fastcall(CShellBrowser *__hidden this, LPCITEMIDLIST pidl, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `50`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180091268`
- `0x1801143f8`

## callees

- `0x1800218ac`
- `0x1800218fc`
- `0x1800235e8`
- `0x180026424`
- `0x18002f35c`
- `0x1800340a0`
- `0x1800391d4`
- `0x180039440`
- `0x180039680`
- `0x18003a0ac`
- `0x18003a138`
- `0x18003a36c`
- `0x18003a968`
- `0x18003b098`
- `0x180047410`
- `0x180072890`
- `0x1800729dc`
- `0x18009044c`
- `0x1800917a4`
- `0x180091874`
- `0x180093a5c`
- `0x1800941dc`
- `0x1800949cc`
- `0x1800a36c0`
- `0x1800bf838`
- `0x1800c9ffc`
- `0x1800df124`
- `0x1800df45c`
- `0x1800e9990`
- `0x1800e9a4c`
- `0x1800edc00`
- `0x1800ee720`
- `0x18010c2f8`
- `0x180116378`
- `0x180116c64`
- `0x180121edc`
- `0x180121f18`
- `0x1801288f4`
- `0x1801298f4`
- `0x18012bb1c`
- `0x18012c314`
- `0x18012feec`
- `0x18012ff30`
- `0x1801302a8`
- `0x18013c048`
- `0x18013f7d0`
- `0x18013fc70`
- `0x18014d314`
- `0x1801cf5e8`
- `0x180210010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18009075f`
- `SHCORE!IUnknown_QueryService` at `0x18009075f`
- `SHELL32!SHGetIDListFromObject` at `0x180090614`
- `SHELL32!SHGetIDListFromObject` at `0x180090614`
- `SHELL32!SHCreateItemFromIDList` at `0x1800907ca`
- `SHELL32!SHCreateItemFromIDList` at `0x1800907ca`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800905df`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800905df`
- `SHELL32!__imp_ILIsEqual` at `0x180090638`
- `SHELL32!__imp_ILIsEqual` at `0x180090638`
- `SHELL32!__imp_ReportNavigationRestriction` at `0x180090b1c`
- `SHELL32!__imp_ReportNavigationRestriction` at `0x180090b1c`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800909f8`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800909f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009053e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180090c31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180090ce0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009053e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180090c31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180090ce0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180090870`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800908be`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009090c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009093c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009096c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180090870`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800908be`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009090c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009093c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009096c`

## string_xrefs

- `0x180090912`: `ms-settings:windowsupdate-uninstallupdates`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CShellBrowser::_NavigateToPidl(
        CShellBrowser *this,
        const struct _ITEMIDLIST_ABSOLUTE *pidl,
        int a3,
        int a4)
{
  char v5; // di
  _QWORD *v8; // rax
  __int64 v9; // rax
  _QWORD *v10; // rax
  __int64 v11; // r8
  void **v12; // rax
  unsigned int v13; // ebx
  HRESULT NewConnection; // r14d
  char *v15; // rbx
  __int64 v16; // rdx
  int v17; // edi
  void **v18; // rax
  ULONG (__stdcall *Release)(IUnknown *); // rax
  __int64 v20; // rdx
  bool v21; // di
  const wchar_t *v22; // rsi
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rdx
  const wchar_t *v29; // rdi
  const wchar_t *v30; // rsi
  int v31; // eax
  const wchar_t *v32; // rcx
  struct IUnknownVtbl *lpVtbl; // rax
  int v34; // edi
  const wchar_t *v35; // rcx
  bool v36; // di
  __int64 v37; // r8
  int ShouldAllowAccessToFolder; // eax
  CShellBrowser *v39; // rcx
  IUnknown *v40; // rcx
  LPCITEMIDLIST **bIgnoreCase; // [rsp+20h] [rbp-E0h]
  _BYTE v43[8]; // [rsp+30h] [rbp-D0h] BYREF
  IUnknown *punk; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v45; // [rsp+40h] [rbp-C0h] BYREF
  LPCITEMIDLIST pidl2; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpStringSource; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  void *ppvOut; // [rsp+60h] [rbp-A0h] BYREF
  int v50; // [rsp+68h] [rbp-98h]
  int v51; // [rsp+6Ch] [rbp-94h]
  void *v52; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR *p_lpStringSource; // [rsp+78h] [rbp-88h] BYREF
  __int64 v54; // [rsp+80h] [rbp-80h] BYREF
  char v55; // [rsp+88h] [rbp-78h]
  void **v56; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v57[272]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v58[8]; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE v59[48]; // [rsp+1B0h] [rbp+B0h] BYREF
  LPCITEMIDLIST *p_pidl2; // [rsp+1E0h] [rbp+E0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+1E8h] [rbp+E8h] BYREF
  char v62; // [rsp+1F0h] [rbp+F0h]
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v50 = a4;
  v5 = a3;
  v51 = a3;
  v45 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl'::`2'::impl) )
  {
    v8 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>::ensure_data(&v45);
    tip2::details::shared_data<0,0,0>::start(*v8 + 8LL, &p_pidl2);
    v9 = tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>::operator->(
           &v45,
           &pv);
    _tip_FileExplorerNavigationTest::ProcessMetadata((_tip_FileExplorerNavigationTest *)(*(_QWORD *)v9 + 256LL), pidl);
    tip2::test_data_control<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>::~test_data_control<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>(&pv);
  }
  v10 = (_QWORD *)TelemetryCorrelationVectorServiceProvider::Increment(&pv, *((_QWORD *)this + 80));
  TelemetryCorrelationVector::Make(&v52, *v10);
  if ( pv )
    CoTaskMemFree(pv);
  TelemetryCorrelationVector::Increment(&pv, v52);
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
  {
    bIgnoreCase = &p_pidl2;
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      ShellTraceId_Browseui_Browser_Navigate_Start,
      v11,
      1);
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 91) + 32LL))(*((_QWORD *)this + 91));
  tip2::open<tip2::tip_test<tip2::details::merged_data<GraphFilesTip::_tip_GraphHomeNavigateTip,GraphFilesTip::_tip_GraphHomeNavigateTip>>>(&lpStringSource);
  if ( !lpStringSource || !(unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(lpStringSource + 4) )
  {
    punk = 0;
    v12 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ISyncRootManager>>(&punk);
    if ( SHCreateItemFromParsingName(
           L"shell:::{f874310e-b6b7-47dc-bc84-b9e6b38f5903}",
           0,
           &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
           v12) >= 0 )
    {
      pidl2 = 0;
      p_pidl2 = &pidl2;
      ppidl = 0;
      v62 = 1;
      v13 = (unsigned int)SHGetIDListFromObject(punk, &ppidl) >> 31;
      wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pidl2);
      if ( (unsigned __int8)v13 != 1 && ILIsEqual((LPCITEMIDLIST)pidl, pidl2) )
      {
        tip2::start<tip2::tip_test<tip2::details::merged_data<GraphFilesTip::_tip_GraphHomeNavigateTip,GraphFilesTip::_tip_GraphHomeNavigateTip>>>(&ppvOut);
        wil::com_ptr_t<tip2::details::merged_data<GraphFilesTip::_tip_GraphHomeNavigateTip,GraphFilesTip::_tip_GraphHomeNavigateTip>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<GraphFilesTip::_tip_GraphHomeNavigateTip,GraphFilesTip::_tip_GraphHomeNavigateTip>,wil::err_returncode_policy>(&ppvOut);
      }
      wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &pidl2,
        0);
    }
    Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(&punk);
  }
  wil::com_ptr_t<tip2::details::merged_data<GraphFilesTip::_tip_GraphHomeNavigateTip,GraphFilesTip::_tip_GraphHomeNavigateTip>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<GraphFilesTip::_tip_GraphHomeNavigateTip,GraphFilesTip::_tip_GraphHomeNavigateTip>,wil::err_returncode_policy>(&lpStringSource);
  if ( !(unsigned int)CShellBrowser::_CanNavigate(this) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl'::`2'::impl) )
    {
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>::operator->(
                              &v45,
                              &lpStringSource)
               + 276LL) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>::~test_data_control<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>(&lpStringSource);
    }
    NewConnection = -2147024726;
    v15 = (char *)pv;
    CShellBrowser::_HandleFailedNavigation(this, -2147024726, (const char *)pv);
    goto LABEL_76;
  }
  wil::ActivityBase<FileExplorerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FileExplorerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    &v56,
    "NavigateToPidl");
  v56 = &FileExplorerTelemetry::NavigateToPidl::`vftable';
  v15 = (char *)pv;
  FileExplorerTelemetry::NavigateToPidl::StartActivityWithCorrelationVector(
    (FileExplorerTelemetry::NavigateToPidl *)&v56,
    (const char *)pv);
  if ( (*((_DWORD *)this + 164) & 0x20000) == 0 && (v5 & 0x20) == 0 )
  {
    if ( pidl )
    {
      v16 = *((_QWORD *)this + 49);
      if ( v16 )
      {
        if ( (unsigned int)ILIsEqualIncludingHiddenEx(pidl, v16, 0xFFFFFFFFLL) )
          *((_DWORD *)this + 164) |= 0x20000u;
      }
    }
  }
  ppvOut = 0;
  if ( IUnknown_QueryService(
         *((IUnknown **)this + 80),
         (const GUID *const)&SID_SObjectWithFocus,
         &GUID_b5e9ed86_f7b7_4b8b_b603_01446c759c07,
         &ppvOut) >= 0
    && (v17 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvOut + 24LL))(ppvOut),
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut),
        v17 == 1)
    || (a4 & 0x80000) != 0 )
  {
    *((_DWORD *)this + 94) = 1;
  }
  if ( (a4 & 0x100000) != 0 )
    *((_DWORD *)this + 164) |= 0x20000u;
  punk = 0;
  v18 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ISyncRootManager>>(&punk);
  NewConnection = SHCreateItemFromIDList((LPCITEMIDLIST)pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v18);
  pidl2 = 0;
  Release = punk->lpVtbl[1].Release;
  p_pidl2 = &pidl2;
  ppidl = 0;
  v62 = 1;
  v21 = ((int (__fastcall *)(IUnknown *, __int64, LPITEMIDLIST *))Release)(punk, 2147581953LL, &ppidl) >= 0;
  if ( v62 )
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      p_pidl2,
      ppidl);
  if ( v21 )
  {
    v22 = 0;
    LOBYTE(v20) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::GetImpl'::`2'::impl,
      v20,
      0);
    if ( CompareStringOrdinal(&pidl2->mkid.cb, -1, L"::{BB06C0E4-D293-4F75-8A90-CB05B6477EEE}", -1, 1) == 2 )
    {
      LOBYTE(v23) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::GetImpl'::`2'::impl,
        v23,
        0);
      LOBYTE(v24) = 1;
      LOBYTE(v25) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::GetImpl'::`2'::impl,
        v25,
        v24);
      v22 = L"ms-settings:about";
    }
    if ( CompareStringOrdinal(&pidl2->mkid.cb, -1, L"::{C58C4893-3BE0-4B45-ABB5-A63E4B8C8651}", -1, 1) == 2 )
    {
      LOBYTE(v26) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::GetImpl'::`2'::impl,
        v26,
        0);
      LOBYTE(v27) = 1;
      LOBYTE(v28) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::GetImpl'::`2'::impl,
        v28,
        v27);
      v22 = L"ms-settings:troubleshoot";
    }
    v29 = L"ms-settings:windowsupdate-uninstallupdates";
    if ( CompareStringOrdinal(&pidl2->mkid.cb, -1, L"::{D450A8A1-9568-45C7-9C0E-B4F9FB4537BD}", -1, 1) != 2 )
      v29 = v22;
    v30 = L"ms-settings:defaultapps";
    if ( CompareStringOrdinal(&pidl2->mkid.cb, -1, L"::{17CD9488-1228-4B2F-88CE-4298E93E0966}", -1, 1) != 2 )
      v30 = v29;
    v31 = CompareStringOrdinal(&pidl2->mkid.cb, -1, L"::{BD84B380-8CA2-1069-AB1D-08000948F534}", -1, 1);
    v32 = L"ms-settings:fonts";
    if ( v31 != 2 )
      v32 = v30;
    p_pidl2 = (LPCITEMIDLIST *)v32;
    lpStringSource = 0;
    lpVtbl = punk->lpVtbl;
    p_lpStringSource = &lpStringSource;
    v54 = 0;
    v55 = 1;
    v34 = ((__int64 (__fastcall *)(IUnknown *, __int64, __int64 *))lpVtbl[1].Release)(punk, 2147647488LL, &v54);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_lpStringSource);
    if ( v34 < 0
      || FindStringOrdinal(
           0x200000u,
           lpStringSource,
           -1,
           L"\\::{8E908FC9-BECC-40F6-915B-F4CA0E70D03D}\\Advanced",
           -1,
           1) < 0 )
    {
      v35 = (const wchar_t *)p_pidl2;
      if ( !p_pidl2 )
      {
LABEL_50:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpStringSource);
        goto LABEL_51;
      }
    }
    else
    {
      v35 = L"ms-settings:network-advancedsharing";
    }
    *((_DWORD *)this + 164) |= 0x20000u;
    LaunchRedirectedControlPanelEntryPoint(v35, 3);
    NewConnection = -2147024726;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl'::`2'::impl) )
    {
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>::operator->(
                              &v45,
                              &p_pidl2)
               + 276LL) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>::~test_data_control<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>(&p_pidl2);
    }
    goto LABEL_50;
  }
LABEL_51:
  v36 = 0;
  if ( NewConnection < 0 )
    goto LABEL_70;
  if ( IShellItem_IsPartialCloudFilePlaceholderFromFindData((struct IShellItem *)punk) )
    v36 = IsFolderNotStreamItem((struct IShellItem *)punk);
  lpStringSource = 0;
  v43[0] = 0;
  ShouldAllowAccessToFolder = NamespaceRestrictionHelper::ShouldAllowAccessToFolder(&lpStringSource, punk, v37, v43);
  NewConnection = ShouldAllowAccessToFolder;
  if ( ShouldAllowAccessToFolder >= 0 )
    NewConnection = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x182,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\NamespaceRestrictionHelper.h",
      (const char *)(unsigned int)ShouldAllowAccessToFolder,
      (int)bIgnoreCase);
  if ( NewConnection >= 0 )
  {
    if ( !v43[0] )
    {
      ReportNavigationRestriction(punk, *((_QWORD *)this + 41));
      NewConnection = -2147024891;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl'::`2'::impl) )
      {
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>::operator->(
                                &v45,
                                &p_pidl2)
                 + 276LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>::~test_data_control<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>(&p_pidl2);
      }
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xBED,
      (unsigned int)"shell\\explorerframe\\shbrows2.cpp",
      (const char *)(unsigned int)NewConnection,
      (int)bIgnoreCase);
  }
  Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(&lpStringSource);
  if ( NewConnection < 0 )
    goto LABEL_70;
  if ( !*((_QWORD *)this + 150) && CShellBrowser::_ShouldShowRibbon(v39, (struct IShellItem *)punk) )
    CShellBrowser::_CreateRibbon(this, (struct IShellItem *)punk);
  NewConnection = CShellBrowser::_CreateNewConnection(this, (struct IShellItem *)punk, (__int64)&v52);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl'::`2'::impl)
    && NewConnection == -2147024726 )
  {
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>::operator->(
                            &v45,
                            &p_pidl2)
             + 276LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>::~test_data_control<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>(&p_pidl2);
LABEL_70:
    CShellBrowser::_HandleFailedNavigation(this, NewConnection, v15);
    goto LABEL_71;
  }
  if ( NewConnection < 0 )
    goto LABEL_70;
LABEL_71:
  wil::ActivityBase<FileExplorerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
    &v56,
    (unsigned int)NewConnection);
  FileExplorerTelemetry::NavigateToPidl::Stop((FileExplorerTelemetry::NavigateToPidl *)&v56, pidl, v36);
  if ( pidl2 )
    CoTaskMemFree((LPVOID)pidl2);
  v40 = punk;
  if ( punk )
  {
    punk = 0;
    ((void (__fastcall *)(IUnknown *))v40->lpVtbl->Release)(v40);
  }
  v56 = &FileExplorerTelemetry::NavigateToPidl::`vftable';
  wil::ActivityBase<FileExplorerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v56);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v59);
  wil::details::shared_object<wil::ActivityBase<FileExplorerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<FileExplorerLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v58);
  wil::ActivityBase<FileExplorerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<FileExplorerLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<FileExplorerLogging,_TlgReflectorTag_Param0IsProviderType>(v57);
LABEL_76:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl'::`2'::impl) )
  {
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>::operator->(
                             &v45,
                             &p_pidl2)
              + 272LL) = NewConnection;
    tip2::test_data_control<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>::~test_data_control<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>(&p_pidl2);
    if ( v45 )
      tip2::details::shared_data<0,0,0>::complete_without_lock(v45 + 8);
  }
  if ( v15 )
    CoTaskMemFree(v15);
  if ( v52 )
    operator delete(v52, (const struct std::nothrow_t *)0x90);
  wil::com_ptr_t<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>,wil::err_returncode_policy>(&v45);
  return (unsigned int)NewConnection;
}

```

## disassembly

```asm
0x18009044c  mov     [rsp-8+arg_10], rbx
0x180090451  push    rbp
0x180090452  push    rsi
0x180090453  push    rdi
0x180090454  push    r12
0x180090456  push    r13
0x180090458  push    r14
0x18009045a  push    r15
0x18009045c  lea     rbp, [rsp-100h]
0x180090464  sub     rsp, 200h
0x18009046b  mov     rax, cs:__security_cookie
0x180090472  xor     rax, rsp
0x180090475  mov     [rbp+130h+var_38], rax
0x18009047c  mov     esi, r9d
0x18009047f  mov     [rsp+230h+var_1C8], r9d
0x180090484  mov     edi, r8d
0x180090487  mov     [rsp+230h+var_1C4], r8d
0x18009048c  mov     r13, rdx
0x18009048f  mov     r15, rcx
0x180090492  xor     r12d, r12d
0x180090495  mov     [rsp+230h+var_1F0], r12
0x18009049a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56275225@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56275225@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225> `wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl(void)'::`2'::impl
0x1800904a1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56275225@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(void)
0x1800904a6  test    al, al
0x1800904a8  jz      short loc_180090515
0x1800904aa  mov     rcx, [rsp+230h+var_1F0]
0x1800904af  test    rcx, rcx
0x1800904b2  jz      short loc_1800904CB
0x1800904b4  add     rcx, 8
0x1800904b8  call    ?has_ever_started@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,1>::has_ever_started(void)
0x1800904bd  test    al, al
0x1800904bf  jz      short loc_1800904CB
0x1800904c1  lea     rcx, [rsp+230h+var_1F0]
0x1800904c6  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_FileExplorerNavigationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>,wil::err_returncode_policy>::reset(void)
0x1800904cb  lea     rcx, [rsp+230h+var_1F0]
0x1800904d0  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_FileExplorerNavigationTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_FileExplorerNavigationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>::ensure_data(void)
0x1800904d5  mov     rcx, [rax]
0x1800904d8  add     rcx, 8
0x1800904dc  lea     rdx, [rbp+130h+var_50]
0x1800904e3  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x1800904e8  lea     rdx, [rsp+230h+pv]
0x1800904ed  lea     rcx, [rsp+230h+var_1F0]
0x1800904f2  call    ??C?$tip_test@V?$merged_data@U_tip_FileExplorerNavigationTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_FileExplorerNavigationTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>::operator->(void)
0x1800904f7  nop
0x1800904f8  mov     rcx, [rax]
0x1800904fb  add     rcx, 100h; this
0x180090502  mov     rdx, r13; struct _ITEMIDLIST_ABSOLUTE *
0x180090505  call    ?ProcessMetadata@_tip_FileExplorerNavigationTest@@QEAAXPEBU_ITEMIDLIST_ABSOLUTE@@@Z; _tip_FileExplorerNavigationTest::ProcessMetadata(_ITEMIDLIST_ABSOLUTE const *)
0x18009050a  nop
0x18009050b  lea     rcx, [rsp+230h+pv]
0x180090510  call    ??1?$test_data_control@V?$merged_data@U_tip_FileExplorerNavigationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>::~test_data_control<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>(void)
0x180090515  mov     rdx, [r15+280h]
0x18009051c  lea     rcx, [rsp+230h+pv]
0x180090521  call    ?Increment@TelemetryCorrelationVectorServiceProvider@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIUnknown@@@Z; TelemetryCorrelationVectorServiceProvider::Increment(IUnknown *)
0x180090526  mov     rdx, [rax]
0x180090529  lea     rcx, [rsp+230h+var_1C0]
0x18009052e  call    ?Make@TelemetryCorrelationVector@@SA?AV?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@wistd@@@wistd@@PEBD@Z; TelemetryCorrelationVector::Make(char const *)
0x180090533  nop
0x180090534  mov     rcx, [rsp+230h+pv]; pv
0x180090539  test    rcx, rcx
0x18009053c  jz      short loc_180090544
0x18009053e  call    cs:__imp_CoTaskMemFree
0x180090544  mov     rdx, [rsp+230h+var_1C0]
0x180090549  lea     rcx, [rsp+230h+pv]
0x18009054e  call    ?Increment@TelemetryCorrelationVector@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@PEAVTraceLoggingCorrelationVector@@@Z; TelemetryCorrelationVector::Increment(TraceLoggingCorrelationVector *)
0x180090553  nop
0x180090554  mov     r14d, 1
0x18009055a  test    cs:Microsoft_Windows_Shell_CoreEnableBits, r14b
0x180090561  jz      short loc_180090585
0x180090563  lea     rax, [rbp+130h+var_50]
0x18009056a  mov     qword ptr [rsp+230h+bIgnoreCase], rax
0x18009056f  mov     r9d, r14d
0x180090572  lea     rdx, ShellTraceId_Browseui_Browser_Navigate_Start
0x180090579  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x180090580  call    McGenEventWrite_EventWriteTransfer
0x180090585  mov     rcx, [r15+2D8h]
0x18009058c  mov     rax, [rcx]
0x18009058f  mov     rax, [rax+20h]
0x180090593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090598  lea     rcx, [rsp+230h+lpStringSource]
0x18009059d  call    ??$open@V?$tip_test@V?$merged_data@U_tip_GraphHomeNavigateTip@GraphFilesTip@@U12@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_GraphHomeNavigateTip@GraphFilesTip@@U12@@details@tip2@@@0@XZ; tip2::open<tip2::tip_test<tip2::details::merged_data<GraphFilesTip::_tip_GraphHomeNavigateTip,GraphFilesTip::_tip_GraphHomeNavigateTip>>>(void)
0x1800905a2  mov     rcx, [rsp+230h+lpStringSource]
0x1800905a7  test    rcx, rcx
0x1800905aa  jz      short loc_1800905BD
0x1800905ac  add     rcx, 8
0x1800905b0  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x1800905b5  test    al, al
0x1800905b7  jnz     loc_18009066C
0x1800905bd  mov     [rsp+230h+punk], r12
0x1800905c2  lea     rcx, [rsp+230h+punk]
0x1800905c7  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ISyncRootManager>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ISyncRootManager>>)
0x1800905cc  mov     r9, rax; ppv
0x1800905cf  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800905d6  xor     edx, edx; pbc
0x1800905d8  lea     rcx, aShellF874310eB; "shell:::{f874310e-b6b7-47dc-bc84-b9e6b3"...
0x1800905df  call    cs:__imp_SHCreateItemFromParsingName
0x1800905e5  test    eax, eax
0x1800905e7  js      short loc_180090662
0x1800905e9  mov     [rsp+230h+pidl2], r12
0x1800905ee  lea     rax, [rsp+230h+pidl2]
0x1800905f3  mov     [rbp+130h+var_50], rax
0x1800905fa  mov     [rbp+130h+ppidl], r12
0x180090601  mov     [rbp+130h+var_40], r14b
0x180090608  lea     rdx, [rbp+130h+ppidl]; ppidl
0x18009060f  mov     rcx, [rsp+230h+punk]; punk
0x180090614  call    cs:__imp_SHGetIDListFromObject
0x18009061a  mov     ebx, eax
0x18009061c  shr     ebx, 1Fh
0x18009061f  lea     rcx, [rbp+130h+var_50]
0x180090626  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18009062b  xor     bl, r14b
0x18009062e  jz      short loc_180090656
0x180090630  mov     rdx, [rsp+230h+pidl2]; pidl2
0x180090635  mov     rcx, r13; pidl1
0x180090638  call    cs:__imp_ILIsEqual
0x18009063e  test    eax, eax
0x180090640  jz      short loc_180090656
0x180090642  lea     rcx, [rsp+230h+ppvOut]
0x180090647  call    ??$start@V?$tip_test@V?$merged_data@U_tip_GraphHomeNavigateTip@GraphFilesTip@@U12@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_GraphHomeNavigateTip@GraphFilesTip@@U12@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<GraphFilesTip::_tip_GraphHomeNavigateTip,GraphFilesTip::_tip_GraphHomeNavigateTip>>>(void)
0x18009064c  lea     rcx, [rsp+230h+ppvOut]
0x180090651  call    ??1?$com_ptr_t@V?$merged_data@U_tip_GraphHomeNavigateTip@GraphFilesTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<GraphFilesTip::_tip_GraphHomeNavigateTip,GraphFilesTip::_tip_GraphHomeNavigateTip>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<GraphFilesTip::_tip_GraphHomeNavigateTip,GraphFilesTip::_tip_GraphHomeNavigateTip>,wil::err_returncode_policy>(void)
0x180090656  xor     edx, edx
0x180090658  lea     rcx, [rsp+230h+pidl2]
0x18009065d  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x180090662  lea     rcx, [rsp+230h+punk]
0x180090667  call    ?InternalRelease@?$ComPtr@UIKnownFolderProperties@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(void)
0x18009066c  lea     rcx, [rsp+230h+lpStringSource]
0x180090671  call    ??1?$com_ptr_t@V?$merged_data@U_tip_GraphHomeNavigateTip@GraphFilesTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<GraphFilesTip::_tip_GraphHomeNavigateTip,GraphFilesTip::_tip_GraphHomeNavigateTip>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<GraphFilesTip::_tip_GraphHomeNavigateTip,GraphFilesTip::_tip_GraphHomeNavigateTip>,wil::err_returncode_policy>(void)
0x180090676  mov     rcx, r15; this
0x180090679  call    ?_CanNavigate@CShellBrowser@@AEAAHXZ; CShellBrowser::_CanNavigate(void)
0x18009067e  test    eax, eax
0x180090680  jnz     short loc_1800906D6
0x180090682  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56275225@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56275225@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225> `wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl(void)'::`2'::impl
0x180090689  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56275225@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(void)
0x18009068e  test    al, al
0x180090690  jz      short loc_1800906B5
0x180090692  lea     rdx, [rsp+230h+lpStringSource]
0x180090697  lea     rcx, [rsp+230h+var_1F0]
0x18009069c  call    ??C?$tip_test@V?$merged_data@U_tip_FileExplorerNavigationTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_FileExplorerNavigationTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>::operator->(void)
0x1800906a1  mov     rdx, [rax]
0x1800906a4  mov     [rdx+114h], r14b
0x1800906ab  lea     rcx, [rsp+230h+lpStringSource]
0x1800906b0  call    ??1?$test_data_control@V?$merged_data@U_tip_FileExplorerNavigationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>::~test_data_control<tip2::details::merged_data<_tip_FileExplorerNavigationTest,_tip_FileExplorerNavigationTest>>(void)
0x1800906b5  mov     r12d, 800700AAh
0x1800906bb  mov     r14d, r12d
0x1800906be  mov     rbx, [rsp+230h+pv]
0x1800906c3  mov     r8, rbx; char *
0x1800906c6  mov     edx, r12d; int
0x1800906c9  mov     rcx, r15; this
0x1800906cc  call    ?_HandleFailedNavigation@CShellBrowser@@AEAAJJPEBD@Z; CShellBrowser::_HandleFailedNavigation(long,char const *)
0x1800906d1  jmp     loc_180090C8D
0x1800906d6  lea     rdx, aNavigatetopidl; "NavigateToPidl"
0x1800906dd  lea     rcx, [rbp+130h+var_1A0]
0x1800906e1  call    ??0?$ActivityBase@VFileExplorerLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FileExplorerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FileExplorerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800906e6  lea     rax, ??_7NavigateToPidl@FileExplorerTelemetry@@6B@; const FileExplorerTelemetry::NavigateToPidl::`vftable'
0x1800906ed  mov     [rbp+130h+var_1A0], rax
0x1800906f1  mov     rbx, [rsp+230h+pv]
0x1800906f6  mov     rdx, rbx; char *
0x1800906f9  lea     rcx, [rbp+130h+var_1A0]; this
0x1800906fd  call    ?StartActivityWithCorrelationVector@NavigateToPidl@FileExplorerTelemetry@@QEAAXPEBD@Z; FileExplorerTelemetry::NavigateToPidl::StartActivityWithCorrelationVector(char const *)
0x180090702  nop
0x180090703  test    dword ptr [r15+290h], 20000h
0x18009070e  jnz     short loc_180090740
0x180090710  test    dil, 20h
0x180090714  jnz     short loc_180090740
0x180090716  test    r13, r13
0x180090719  jz      short loc_180090740
0x18009071b  mov     rdx, [r15+188h]
0x180090722  test    rdx, rdx
0x180090725  jz      short loc_180090740
0x180090727  or      r8d, 0FFFFFFFFh
0x18009072b  mov     rcx, r13
0x18009072e  call    ?ILIsEqualIncludingHiddenEx@@YAHPEBU_ITEMIDLIST_ABSOLUTE@@0W4IIEIHE@@@Z; ILIsEqualIncludingHiddenEx(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *,IIEIHE)
0x180090733  test    eax, eax
0x180090735  jz      short loc_180090740
0x180090737  bts     dword ptr [r15+290h], 11h
0x180090740  mov     [rsp+230h+ppvOut], r12
0x180090745  lea     r9, [rsp+230h+ppvOut]; ppvOut
0x18009074a  lea     r8, _GUID_b5e9ed86_f7b7_4b8b_b603_01446c759c07; riid
0x180090751  lea     rdx, SID_SObjectWithFocus; guidService
0x180090758  mov     rcx, [r15+280h]; punk
0x18009075f  call    cs:__imp_IUnknown_QueryService
0x180090765  test    eax, eax
0x180090767  js      short loc_180090792
0x180090769  mov     rcx, [rsp+230h+ppvOut]
0x18009076e  mov     rax, [rcx]
0x180090771  mov     rax, [rax+18h]
0x180090775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009077a  mov     edi, eax
0x18009077c  mov     rcx, [rsp+230h+ppvOut]
0x180090781  mov     rdx, [rcx]
0x180090784  mov     rax, [rdx+10h]
0x180090788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009078d  cmp     edi, r14d
0x180090790  jz      short loc_180090798
0x180090792  bt      esi, 13h
0x180090796  jnb     short loc_18009079F
0x180090798  mov     [r15+178h], r14d
0x18009079f  bt      esi, 14h
0x1800907a3  jnb     short loc_1800907AE
0x1800907a5  bts     dword ptr [r15+290h], 11h
0x1800907ae  mov     [rsp+230h+punk], r12
0x1800907b3  lea     rcx, [rsp+230h+punk]
0x1800907b8  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ISyncRootManager>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ISyncRootManager>>)
0x1800907bd  mov     r8, rax; ppv
0x1800907c0  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800907c7  mov     rcx, r13; pidl
0x1800907ca  call    cs:__imp_SHCreateItemFromIDList
0x1800907d0  mov     r14d, eax
0x1800907d3  mov     [rsp+230h+pidl2], r12
0x1800907d8  mov     rcx, [rsp+230h+punk]
0x1800907dd  mov     rdx, [rcx]
0x1800907e0  mov     rax, [rdx+28h]
0x1800907e4  lea     rdx, [rsp+230h+pidl2]
0x1800907e9  mov     [rbp+130h+var_50], rdx
0x1800907f0  mov     [rbp+130h+ppidl], r12
0x1800907f7  mov     [rbp+130h+var_40], 1
0x1800907fe  lea     r8, [rbp+130h+ppidl]
0x180090805  mov     edx, 80018001h
0x18009080a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009080f  mov     edi, eax
0x180090811  shr     edi, 1Fh
0x180090814  xor     dil, 1
0x180090818  cmp     [rbp+130h+var_40], r12b
0x18009081f  jz      short loc_180090834
0x180090821  mov     rdx, [rbp+130h+ppidl]
0x180090828  mov     rcx, [rbp+130h+var_50]
0x18009082f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180090834  mov     r12d, 800700AAh
0x18009083a  test    dil, dil
0x18009083d  jz      loc_180090A73
0x180090843  xor     esi, esi
0x180090845  xor     r8d, r8d
0x180090848  lea     edi, [rsi+1]
0x18009084b  mov     dl, dil
0x18009084e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RedirectSystemControlPanel@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RedirectSystemControlPanel@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RedirectSystemControlPanel> `wil::Feature<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::GetImpl(void)'::`2'::impl
0x180090855  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RedirectSystemControlPanel@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18009085a  mov     [rsp+230h+bIgnoreCase], edi; bIgnoreCase
0x18009085e  or      edx, 0FFFFFFFFh; cchCount1
0x180090861  mov     r9d, edx; cchCount2
0x180090864  lea     r8, aBb06c0e4D2934f; "::{BB06C0E4-D293-4F75-8A90-CB05B6477EEE"...
0x18009086b  mov     rcx, [rsp+230h+pidl2]; lpString1
0x180090870  call    cs:__imp_CompareStringOrdinal
0x180090876  cmp     eax, 2
0x180090879  jnz     short loc_1800908A6
0x18009087b  xor     r8d, r8d
0x18009087e  mov     dl, dil
0x180090881  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RedirectSystemControlPanel@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RedirectSystemControlPanel@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RedirectSystemControlPanel> `wil::Feature<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::GetImpl(void)'::`2'::impl
0x180090888  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RedirectSystemControlPanel@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18009088d  mov     r8b, dil
0x180090890  mov     dl, dil
0x180090893  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RedirectSystemControlPanel@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RedirectSystemControlPanel@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RedirectSystemControlPanel> `wil::Feature<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::GetImpl(void)'::`2'::impl
0x18009089a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RedirectSystemControlPanel@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18009089f  lea     rsi, aMsSettingsAbou; "ms-settings:about"
0x1800908a6  mov     [rsp+230h+bIgnoreCase], edi; bIgnoreCase
0x1800908aa  or      eax, 0FFFFFFFFh
0x1800908ad  mov     r9d, eax; cchCount2
0x1800908b0  lea     r8, aC58c48933be04b; "::{C58C4893-3BE0-4B45-ABB5-A63E4B8C8651"...
0x1800908b7  mov     edx, eax; cchCount1
0x1800908b9  mov     rcx, [rsp+230h+pidl2]; lpString1
0x1800908be  call    cs:__imp_CompareStringOrdinal
0x1800908c4  cmp     eax, 2
0x1800908c7  jnz     short loc_1800908F4
0x1800908c9  xor     r8d, r8d
0x1800908cc  mov     dl, dil
0x1800908cf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RedirectSystemControlPanel@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RedirectSystemControlPanel@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RedirectSystemControlPanel> `wil::Feature<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::GetImpl(void)'::`2'::impl
0x1800908d6  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RedirectSystemControlPanel@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800908db  mov     r8b, dil
0x1800908de  mov     dl, dil
0x1800908e1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RedirectSystemControlPanel@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RedirectSystemControlPanel@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RedirectSystemControlPanel> `wil::Feature<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::GetImpl(void)'::`2'::impl
0x1800908e8  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RedirectSystemControlPanel@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RedirectSystemControlPanel>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800908ed  lea     rsi, aMsSettingsTrou; "ms-settings:troubleshoot"
0x1800908f4  mov     [rsp+230h+bIgnoreCase], edi; bIgnoreCase
0x1800908f8  or      eax, 0FFFFFFFFh
0x1800908fb  mov     r9d, eax; cchCount2
0x1800908fe  lea     r8, aD450a8a1956845; "::{D450A8A1-9568-45C7-9C0E-B4F9FB4537BD"...
0x180090905  mov     edx, eax; cchCount1
0x180090907  mov     rcx, [rsp+230h+pidl2]; lpString1
0x18009090c  call    cs:__imp_CompareStringOrdinal
0x180090912  lea     rdi, aMsSettingsWind; "ms-settings:windowsupdate-uninstallupda"...
0x180090919  cmp     eax, 2
0x18009091c  cmovnz  rdi, rsi
0x180090920  mov     [rsp+230h+bIgnoreCase], 1; bIgnoreCase
0x180090928  or      eax, 0FFFFFFFFh
0x18009092b  mov     r9d, eax; cchCount2
0x18009092e  lea     r8, a17cd948812284b; "::{17CD9488-1228-4B2F-88CE-4298E93E0966"...
0x180090935  mov     edx, eax; cchCount1
0x180090937  mov     rcx, [rsp+230h+pidl2]; lpString1
0x18009093c  call    cs:__imp_CompareStringOrdinal
0x180090942  lea     rsi, aMsSettingsDefa; "ms-settings:defaultapps"
0x180090949  cmp     eax, 2
0x18009094c  cmovnz  rsi, rdi
0x180090950  mov     [rsp+230h+bIgnoreCase], 1; int
0x180090958  or      eax, 0FFFFFFFFh
0x18009095b  mov     r9d, eax; cchCount2
0x18009095e  lea     r8, aBd84b3808ca210; "::{BD84B380-8CA2-1069-AB1D-08000948F534"...
0x180090965  mov     edx, eax; cchCount1
0x180090967  mov     rcx, [rsp+230h+pidl2]; lpString1
0x18009096c  call    cs:__imp_CompareStringOrdinal
0x180090972  lea     rcx, aMsSettingsFont; "ms-settings:fonts"
  ... truncated ...
```
