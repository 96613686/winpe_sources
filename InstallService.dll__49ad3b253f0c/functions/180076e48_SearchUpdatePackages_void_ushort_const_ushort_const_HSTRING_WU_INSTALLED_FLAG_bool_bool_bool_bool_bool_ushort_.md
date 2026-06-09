# SearchUpdatePackages(void *,ushort const *,ushort const *,HSTRING__ *,WU_INSTALLED_FLAG,bool,bool,bool,bool,bool,ushort const *,IUpdateSession *,char const *,IUpdateCollection * *)

- ea: `0x180076e48`
- end: `0x180077679`
- name: `?SearchUpdatePackages@@YAJPEAXPEBG1PEAUHSTRING__@@W4WU_INSTALLED_FLAG@@_N44441PEAUIUpdateSession@@PEBDPEAPEAUIUpdateCollection@@@Z`
- size: `2097`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `31`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18005e49c`
- `0x180076138`
- `0x1800e2b80`
- `0x1800f29b4`
- `0x1800f4734`
- `0x1800f5abc`
- `0x1801cab88`

## callees

- `0x180009ea0`
- `0x18000ab24`
- `0x1800101f4`
- `0x1800111c8`
- `0x1800127c8`
- `0x18001c108`
- `0x18001c414`
- `0x18001c844`
- `0x18001c964`
- `0x18002234c`
- `0x18006f8b4`
- `0x18006fe58`
- `0x18007023c`
- `0x180071dcc`
- `0x1800722a8`
- `0x180072368`
- `0x180075020`
- `0x180076e48`
- `0x180077c44`
- `0x1800792f0`
- `0x180079878`
- `0x180079a68`
- `0x18007a7cc`
- `0x18007a814`
- `0x18007aa00`
- `0x18007afc0`
- `0x18007c3c4`
- `0x1801f6d0c`
- `0x1801f6dbc`
- `0x1801f6f68`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180077612`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007761c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180077612`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007761c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800774db`
- `OLEAUT32!__imp_SysFreeString` at `0x1800774db`
- `OLEAUT32!__imp_VariantInit` at `0x1800771f1`
- `OLEAUT32!__imp_VariantInit` at `0x1800771f1`

## string_xrefs

- `0x180076efd`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180076f79`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180077035`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x1800770cb`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x18007719a`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180077247`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180077341`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x1800773e5`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x18007743d`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180077478`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x1800775c0`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x1800775fe`: `onecoreuap\enduser\winstore\installservice\lib\wuhelpers.cpp`
- `0x180076f58`: `AppId = %s, WU Installed Flag = %d, OnlineSearch = %d, Interactive = %d, Scope = %d, Client ID = %s`
- `0x180076ef0`: `SearchUpdatePackages`
- `0x180076f6c`: `SearchUpdatePackages`
- `0x180077028`: `SearchUpdatePackages`
- `0x1800770bf`: `SearchUpdatePackages`
- `0x18007718e`: `SearchUpdatePackages`
- `0x180077240`: `SearchUpdatePackages`
- `0x180077334`: `SearchUpdatePackages`
- `0x1800773d9`: `SearchUpdatePackages`
- `0x180077431`: `SearchUpdatePackages`
- `0x18007746b`: `SearchUpdatePackages`
- `0x1800775b3`: `SearchUpdatePackages`
- `0x1800775f1`: `SearchUpdatePackages`
- `0x180077187`: `spSearcher.As(&spInternalConfiguration)`
- `0x180077230`: `spInternalConfiguration->put_InternalConfigurationProperty(IUPDATE_INTERNALPROPERTY_SEARCH_USERTOKEN, var)`
- `0x1800771d2`: `_SetWuUserTokenProperty(spInternalConfiguration.Get(), IUPDATE_INTERNALPROPERTY_SEARCH_USERTOKEN, hUserToken)`
- `0x1800772bf`: `IsInstalled=%c AND AppCategoryIDs contains '%s'`
- `0x1800772ed`: ` AND UpdateID='%s'`
- `0x18007745b`: `Unexpected error from IUpdateSearcher::Search`
- `0x1800775dd`: `WININET_E_DECODING_FAILED returned by WU during SearchUpdatePackages and we've detected no proxies on the device`
- `0x18007759f`: `WININET_E_DECODING_FAILED returned by WU during SearchUpdatePackages and we've detected a list of proxies on the device: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall SearchUpdatePackages(
        void *a1,
        _WORD *a2,
        _WORD *a3,
        struct IUpdateInternalConfiguration *a4,
        int a5,
        unsigned __int8 a6,
        char a7,
        char a8,
        char a9,
        char a10,
        unsigned __int16 *a11,
        struct IUpdateSession *a12,
        OLECHAR *a13,
        _QWORD *a14)
{
  struct IUpdateSession *v17; // rbx
  _QWORD *v18; // rbx
  __int64 v19; // rax
  const WCHAR *v20; // rax
  int UpdateSearcher; // edi
  int v22; // eax
  int v23; // eax
  int v24; // eax
  const char *v25; // r9
  unsigned int v26; // edx
  int v27; // eax
  OLECHAR *v28; // rbx
  struct IUpdateSearcher *v29; // rsi
  HRESULT (__stdcall *Search)(IUpdateSearcher *, BSTR, ISearchResult **); // rdi
  int v31; // eax
  struct IUpdateSearcher *v32; // rsi
  HRESULT (__stdcall *v33)(IUpdateSearcher *, BSTR, ISearchResult **); // rdi
  int v34; // eax
  struct IUpdateInternalConfiguration *v35; // rax
  _QWORD *v36; // rax
  const unsigned __int16 *v37; // rdx
  CHttpRequest *v38; // rcx
  const unsigned __int16 *v39; // r8
  bool v40; // r9
  HLOCAL v41; // rsi
  __int64 v42; // rbx
  int v44; // [rsp+28h] [rbp-D8h]
  int v45; // [rsp+28h] [rbp-D8h]
  int v46; // [rsp+28h] [rbp-D8h]
  int v47; // [rsp+28h] [rbp-D8h]
  int v48; // [rsp+28h] [rbp-D8h]
  char *v49; // [rsp+30h] [rbp-D0h]
  struct IUpdateInternalConfiguration *v50; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v51; // [rsp+78h] [rbp-88h] BYREF
  struct IUpdateSearcher *v52; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL v53; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp-70h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v56[2]; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-50h] BYREF
  VARIANTARG v58; // [rsp+D0h] [rbp-30h] BYREF
  int v59; // [rsp+E8h] [rbp-18h]
  char v60; // [rsp+ECh] [rbp-14h]
  int v61; // [rsp+F0h] [rbp-10h]
  char v62; // [rsp+F4h] [rbp-Ch]
  wchar_t pszDest[256]; // [rsp+100h] [rbp+0h] BYREF

  v50 = a4;
  v17 = a12;
  hMem = a12;
  bstrString = a13;
  v56[0] = a14;
  *a14 = 0;
  if ( !a2 || !*a2 )
    LogMessage(
      1u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
      0x113u,
      "SearchUpdatePackages",
      -1,
      L"Assert (%s): %s",
      0,
      0,
      L"pszAppID && *pszAppID",
      L"Failed");
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
    0x118u,
    "SearchUpdatePackages",
    -1,
    L"AppId = %s, WU Installed Flag = %d, OnlineSearch = %d, Interactive = %d, Scope = %d, Client ID = %s",
    0,
    0);
  if ( a12 )
  {
    v18 = operator new(0x10u);
    *v18 = &uus::Session::`vftable';
    v19 = uus::Utility::GetFirstBrainSession<uus::Brain3>(L"wu.core.wuapi");
    v18[1] = v19;
    v53 = v18;
    if ( v19 )
      v20 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 32LL))(v19);
    else
      v20 = L"0.0.0.0";
    std::wstring::wstring(&v58, v20);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
      0x11Eu,
      "SearchUpdatePackages",
      -1,
      L"UUS Version = %s",
      0,
      0);
    std::wstring::_Tidy_deallocate(&v58);
    std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(&v53);
    v17 = (struct IUpdateSession *)hMem;
  }
  v52 = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v52);
  UpdateSearcher = GetUpdateSearcher(
                     v17,
                     (enum tagSearchScope)(a1 != 0 ? searchScopeCurrentUserOnly : searchScopeMachineAndAllUsers),
                     &v52,
                     a11);
  if ( UpdateSearcher >= 0 )
  {
    v22 = ((__int64 (__fastcall *)(struct IUpdateSearcher *, _QWORD))v52->lpVtbl->put_Online)(
            v52,
            (unsigned __int16)((a6 ^ 1) - 1));
    UpdateSearcher = TraceHR(
                       "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                       0x125u,
                       "SearchUpdatePackages",
                       "spSearcher->put_Online(fOnline ? VARIANT_TRUE : VARIANT_FALSE)",
                       v22,
                       v44);
    if ( UpdateSearcher >= 0 )
    {
      UpdateSearcher = SetIntentPFNConfigurationProperty<IUpdateDownloader>(&v52, v50);
      if ( UpdateSearcher >= 0 )
      {
        *(_DWORD *)&v58.vt = 262152;
        LOBYTE(v58.decVal.Hi32) = a8;
        v58.lVal = 262145;
        BYTE4(v58.decVal.Lo64) = a7;
        *((_DWORD *)&v58.decVal + 4) = 262146;
        *((_BYTE *)&v58.decVal + 20) = 0;
        v59 = 262149;
        v60 = a9;
        v61 = 262156;
        v62 = a10;
        UpdateSearcher = SetInternalConfigurationFlags(v52, &v58, 5, bstrString);
        if ( UpdateSearcher >= 0 )
        {
          if ( a1 )
          {
            v50 = 0;
            v23 = Microsoft::WRL::ComPtr<IUpdateSearcher>::As<IUpdateInternalConfiguration>(&v52, &v50);
            UpdateSearcher = TraceHR(
                               "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                               0x13Du,
                               "SearchUpdatePackages",
                               "spSearcher.As(&spInternalConfiguration)",
                               v23,
                               v45);
            if ( UpdateSearcher >= 0 )
            {
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureTokensAreDuplicable>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnsureTokensAreDuplicable>::GetImpl'::`2'::impl) )
              {
                v24 = _SetWuUserTokenProperty(v50, 0x40006u, a1);
                v25 = "_SetWuUserTokenProperty(spInternalConfiguration.Get(), IUPDATE_INTERNALPROPERTY_SEARCH_USERTOKEN, hUserToken)";
                v26 = 322;
              }
              else
              {
                memset(&pvarg, 0, sizeof(pvarg));
                VariantInit(&pvarg);
                pvarg.vt = 19;
                pvarg.lVal = (int)a1;
                v58 = pvarg;
                v24 = (*(__int64 (__fastcall **)(struct IUpdateInternalConfiguration *, __int64, VARIANTARG *))(*(_QWORD *)v50 + 32LL))(
                        v50,
                        262150,
                        &v58);
                v25 = "spInternalConfiguration->put_InternalConfigurationProperty(IUPDATE_INTERNALPROPERTY_SEARCH_USERTOKEN, var)";
                v26 = 330;
              }
              UpdateSearcher = TraceHR(
                                 "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                                 v26,
                                 "SearchUpdatePackages",
                                 v25,
                                 v24,
                                 v46);
            }
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v50);
          }
          if ( UpdateSearcher >= 0 )
          {
            v51 = 0;
            v50 = 0;
            if ( a5 == 2 )
            {
              v27 = StringCchPrintfExW(
                      pszDest,
                      0x100u,
                      &v51,
                      (unsigned __int64 *)&v50,
                      0,
                      L"AppCategoryIDs contains '%s'",
                      a2);
            }
            else
            {
              LODWORD(v49) = 49 - (a5 != 1);
              v27 = StringCchPrintfExW(
                      pszDest,
                      0x100u,
                      &v51,
                      (unsigned __int64 *)&v50,
                      0,
                      L"IsInstalled=%c AND AppCategoryIDs contains '%s'",
                      v49,
                      a2);
            }
            UpdateSearcher = v27;
            if ( v27 >= 0 )
            {
              if ( !a3
                || !*a3
                || (UpdateSearcher = StringCchPrintfW(v51, (unsigned __int64)v50, L" AND UpdateID='%s'", a3),
                    UpdateSearcher >= 0) )
              {
                LogMessage(
                  3u,
                  "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                  0x167u,
                  "SearchUpdatePackages",
                  -1,
                  L"WU query: \"%s\"",
                  0,
                  0);
                UpdateSearcher = -2147024882;
                ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, pszDest);
                v28 = bstrString;
                if ( !bstrString )
                {
LABEL_40:
                  SysFreeString(v28);
                  goto LABEL_41;
                }
                v51 = 0;
                v29 = v52;
                Search = v52->lpVtbl->Search;
                Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v51);
                UpdateSearcher = ((__int64 (__fastcall *)(struct IUpdateSearcher *, OLECHAR *, unsigned __int16 **))Search)(
                                   v29,
                                   v28,
                                   &v51);
                if ( UpdateSearcher == -2145091564 )
                {
                  if ( !a6 )
                  {
                    v31 = ((__int64 (__fastcall *)(struct IUpdateSearcher *, __int64))v52->lpVtbl->put_Online)(
                            v52,
                            0xFFFFFFFFLL);
                    UpdateSearcher = TraceHR(
                                       "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                                       0x173u,
                                       "SearchUpdatePackages",
                                       "spSearcher->put_Online(VARIANT_TRUE)",
                                       v31,
                                       v47);
                    if ( UpdateSearcher < 0 )
                      goto LABEL_39;
                    v32 = v52;
                    v33 = v52->lpVtbl->Search;
                    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v51);
                    v34 = ((__int64 (__fastcall *)(struct IUpdateSearcher *, OLECHAR *, unsigned __int16 **))v33)(
                            v32,
                            v28,
                            &v51);
                    UpdateSearcher = TraceHR(
                                       "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                                       0x176u,
                                       "SearchUpdatePackages",
                                       "spSearcher->Search(sbstrQuery, &spSearchResult)",
                                       v34,
                                       v48);
LABEL_35:
                    if ( UpdateSearcher >= 0 )
                      goto LABEL_36;
LABEL_39:
                    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v51);
                    goto LABEL_40;
                  }
                }
                else if ( UpdateSearcher >= 0 )
                {
LABEL_36:
                  v50 = 0;
                  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v50);
                  UpdateSearcher = PackagesFromSearchResult(v51, &v50);
                  if ( UpdateSearcher >= 0 )
                  {
                    v35 = v50;
                    v50 = 0;
                    *(_QWORD *)v56[0] = v35;
                  }
                  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v50);
                  goto LABEL_39;
                }
                LogSimpleMessage(
                  1u,
                  "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
                  0x17Bu,
                  "SearchUpdatePackages",
                  UpdateSearcher,
                  L"Unexpected error from IUpdateSearcher::Search",
                  0,
                  0);
                goto LABEL_35;
              }
            }
          }
        }
      }
    }
  }
LABEL_41:
  if ( UpdateSearcher == -2147012721 )
  {
    v50 = 0;
    v36 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ProxySetTipTest,TipTests::_tip_ProxySetTipTest>>::ensure_data(&v50);
    tip2::details::shared_data<1,0,0>::start(*v36 + 8LL, v56);
    hMem = 0;
    v53 = 0;
    LODWORD(v51) = 0;
    CHttpRequest::CHttpRequest((CHttpRequest *)pszDest);
    if ( (int)CHttpRequest::GetProxyInfoForUrl(
                v38,
                v37,
                v39,
                v40,
                (unsigned __int16 **)&hMem,
                (unsigned __int16 **)&v53,
                (unsigned int *)&v51) >= 0 )
    {
      v41 = hMem;
      if ( hMem )
      {
        v42 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ProxySetTipTest,TipTests::_tip_ProxySetTipTest>>::ensure_data(&v50);
        v56[0] = v42;
        if ( v42 )
          _InterlockedIncrement((volatile signed __int32 *)(v42 + 280));
        tip2::details::shared_data<1,0,0>::begin_update(v42 + 8);
        *(_BYTE *)(v42 + 272) = 1;
        tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_ProxySetTipTest,TipTests::_tip_ProxySetTipTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_ProxySetTipTest,TipTests::_tip_ProxySetTipTest>>(v56);
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
          0x19Au,
          "SearchUpdatePackages",
          -1,
          L"WININET_E_DECODING_FAILED returned by WU during SearchUpdatePackages and we've detected a list of proxies on the device: %s",
          0,
          0,
          v41);
      }
      else
      {
        LogSimpleMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\wuhelpers.cpp",
          0x19Eu,
          "SearchUpdatePackages",
          -1,
          L"WININET_E_DECODING_FAILED returned by WU during SearchUpdatePackages and we've detected no proxies on the device",
          0,
          0);
      }
      LocalFree(v41);
      LocalFree(v53);
    }
    if ( v50 )
      tip2::details::shared_data<1,0,0>::complete_without_lock((char *)v50 + 8);
    CHttpRequest::~CHttpRequest((CHttpRequest *)pszDest);
    wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_ProxySetTipTest,TipTests::_tip_ProxySetTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_ProxySetTipTest,TipTests::_tip_ProxySetTipTest>,wil::err_returncode_policy>(&v50);
  }
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v52);
  return (unsigned int)UpdateSearcher;
}

```

## disassembly

```asm
0x180076e48  push    rbp
0x180076e4a  push    rbx
0x180076e4b  push    rsi
0x180076e4c  push    rdi
0x180076e4d  push    r12
0x180076e4f  push    r13
0x180076e51  push    r14
0x180076e53  push    r15
0x180076e55  lea     rbp, [rsp-218h]
0x180076e5d  sub     rsp, 318h
0x180076e64  mov     rax, cs:__security_cookie
0x180076e6b  xor     rax, rsp
0x180076e6e  mov     [rbp+250h+var_50], rax
0x180076e75  mov     [rsp+350h+var_2E0], r9
0x180076e7a  mov     r14, r8
0x180076e7d  mov     rsi, rdx
0x180076e80  mov     r15, rcx
0x180076e83  mov     r13, [rbp+250h+arg_50]
0x180076e8a  mov     rbx, [rbp+250h+arg_58]
0x180076e91  mov     [rbp+250h+hMem], rbx
0x180076e95  mov     rax, [rbp+250h+arg_60]
0x180076e9c  mov     [rbp+250h+bstrString], rax
0x180076ea0  mov     rax, [rbp+250h+arg_68]
0x180076ea7  mov     [rbp+250h+var_2B0], rax
0x180076eab  xor     edx, edx
0x180076ead  mov     [rax], rdx
0x180076eb0  test    rsi, rsi
0x180076eb3  jz      short loc_180076EBA
0x180076eb5  cmp     [rsi], dx
0x180076eb8  jnz     short loc_180076F10
0x180076eba  lea     rax, aFailed_1; "Failed"
0x180076ec1  mov     [rsp+350h+var_308], rax
0x180076ec6  lea     rax, aPszappidPszapp; "pszAppID && *pszAppID"
0x180076ecd  mov     [rsp+350h+var_310], rax
0x180076ed2  mov     [rsp+350h+var_318], rdx; unsigned __int16 *
0x180076ed7  mov     [rsp+350h+var_320], rdx; char *
0x180076edc  lea     rax, aAssertSS; "Assert (%s): %s"
0x180076ee3  mov     [rsp+350h+var_328], rax; unsigned __int16 *
0x180076ee8  mov     dword ptr [rsp+350h+var_330], 0FFFFFFFFh; int
0x180076ef0  lea     r9, aSearchupdatepa; "SearchUpdatePackages"
0x180076ef7  mov     r8d, 113h; unsigned int
0x180076efd  lea     rdx, aOnecoreuapEndu_18; "onecoreuap\\enduser\\winstore\\installs"...
0x180076f04  mov     ecx, 1; unsigned int
0x180076f09  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180076f0e  xor     edx, edx
0x180076f10  mov     rax, r15
0x180076f13  neg     rax
0x180076f16  sbb     edi, edi
0x180076f18  and     edi, 0FFFFFFFEh
0x180076f1b  add     edi, 4
0x180076f1e  movzx   ecx, [rbp+250h+arg_30]
0x180076f25  movzx   eax, [rbp+250h+arg_28]
0x180076f2c  mov     [rsp+350h+var_2E8], r13
0x180076f31  mov     [rsp+350h+var_2F0], edi
0x180076f35  mov     [rsp+350h+var_2F8], ecx
0x180076f39  mov     [rsp+350h+var_300], eax
0x180076f3d  mov     r12d, [rbp+250h+arg_20]
0x180076f44  mov     dword ptr [rsp+350h+var_308], r12d
0x180076f49  mov     [rsp+350h+var_310], rsi
0x180076f4e  mov     [rsp+350h+var_318], rdx; unsigned __int16 *
0x180076f53  mov     [rsp+350h+var_320], rdx; char *
0x180076f58  lea     rax, aAppidSWuInstal; "AppId = %s, WU Installed Flag = %d, Onl"...
0x180076f5f  mov     [rsp+350h+var_328], rax; unsigned __int16 *
0x180076f64  mov     dword ptr [rsp+350h+var_330], 0FFFFFFFFh; int
0x180076f6c  lea     r9, aSearchupdatepa; "SearchUpdatePackages"
0x180076f73  mov     r8d, 118h; unsigned int
0x180076f79  lea     rdx, aOnecoreuapEndu_18; "onecoreuap\\enduser\\winstore\\installs"...
0x180076f80  mov     ecx, 3; unsigned int
0x180076f85  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180076f8a  test    rbx, rbx
0x180076f8d  jz      loc_18007705E
0x180076f93  mov     ecx, 10h; Size
0x180076f98  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180076f9d  mov     rbx, rax
0x180076fa0  mov     [rbp+250h+var_2C8], rax
0x180076fa4  lea     rax, ??_7Session@uus@@6B@; const uus::Session::`vftable'
0x180076fab  mov     [rbx], rax
0x180076fae  lea     rcx, aWuCoreWuapi; "wu.core.wuapi"
0x180076fb5  call    ??$GetFirstBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@PEBGI@Z; uus::Utility::GetFirstBrainSession<uus::Brain3>(ushort const *,uint)
0x180076fba  mov     rdx, rax
0x180076fbd  mov     [rbx+8], rax
0x180076fc1  mov     [rbp+250h+var_2C8], rbx
0x180076fc5  test    rax, rax
0x180076fc8  jz      short loc_180076FDB
0x180076fca  mov     rcx, [rax]
0x180076fcd  mov     rax, [rcx+20h]
0x180076fd1  mov     rcx, rdx
0x180076fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076fd9  jmp     short loc_180076FE2
0x180076fdb  lea     rax, a0000; "0.0.0.0"
0x180076fe2  mov     rdx, rax
0x180076fe5  lea     rcx, [rbp+250h+var_280]
0x180076fe9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180076fee  nop
0x180076fef  lea     rax, [rbp+250h+var_280]
0x180076ff3  cmp     [rbp+250h+var_268], 7
0x180076ff8  cmova   rax, qword ptr [rbp+250h+var_280]
0x180076ffd  mov     [rsp+350h+var_310], rax
0x180077002  mov     [rsp+350h+var_318], 0; unsigned __int16 *
0x18007700b  mov     [rsp+350h+var_320], 0; char *
0x180077014  lea     rax, aUusVersionS; "UUS Version = %s"
0x18007701b  mov     [rsp+350h+var_328], rax; int
0x180077020  mov     dword ptr [rsp+350h+var_330], 0FFFFFFFFh; int
0x180077028  lea     r9, aSearchupdatepa; "SearchUpdatePackages"
0x18007702f  mov     r8d, 11Eh; unsigned int
0x180077035  lea     rdx, aOnecoreuapEndu_18; "onecoreuap\\enduser\\winstore\\installs"...
0x18007703c  mov     ecx, 3; unsigned int
0x180077041  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180077046  nop
0x180077047  lea     rcx, [rbp+250h+var_280]
0x18007704b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180077050  nop
0x180077051  lea     rcx, [rbp+250h+var_2C8]
0x180077055  call    ??1?$unique_ptr@V_Facet_base@std@@U?$default_delete@V_Facet_base@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(void)
0x18007705a  mov     rbx, [rbp+250h+hMem]
0x18007705e  mov     [rbp+250h+var_2D0], 0
0x180077066  lea     rcx, [rbp+250h+var_2D0]
0x18007706a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007706f  mov     r9, r13; unsigned __int16 *
0x180077072  lea     r8, [rbp+250h+var_2D0]; struct IUpdateSearcher **
0x180077076  mov     edx, edi; enum tagSearchScope
0x180077078  mov     rcx, rbx; struct IUpdateSession *
0x18007707b  call    ?GetUpdateSearcher@@YAJPEAUIUpdateSession@@W4tagSearchScope@@PEAPEAUIUpdateSearcher@@PEBG@Z; GetUpdateSearcher(IUpdateSession *,tagSearchScope,IUpdateSearcher * *,ushort const *)
0x180077080  mov     edi, eax
0x180077082  test    eax, eax
0x180077084  js      loc_1800774E3
0x18007708a  mov     rcx, [rbp+250h+var_2D0]
0x18007708e  mov     r8, [rcx]
0x180077091  mov     r13b, [rbp+250h+arg_28]
0x180077098  mov     al, r13b
0x18007709b  mov     ebx, 1
0x1800770a0  xor     al, bl
0x1800770a2  movzx   edx, al
0x1800770a5  sub     dx, bx
0x1800770a8  mov     rax, [r8+0A8h]
0x1800770af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800770b4  mov     dword ptr [rsp+350h+var_330], eax; int
0x1800770b8  lea     r9, aSpsearcherPutO; "spSearcher->put_Online(fOnline ? VARIAN"...
0x1800770bf  lea     r8, aSearchupdatepa; "SearchUpdatePackages"
0x1800770c6  mov     edx, 125h; unsigned int
0x1800770cb  lea     rcx, aOnecoreuapEndu_18; "onecoreuap\\enduser\\winstore\\installs"...
0x1800770d2  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x1800770d7  mov     edi, eax
0x1800770d9  test    eax, eax
0x1800770db  js      loc_1800774E3
0x1800770e1  mov     rdx, [rsp+350h+var_2E0]
0x1800770e6  lea     rcx, [rbp+250h+var_2D0]
0x1800770ea  call    ??$SetIntentPFNConfigurationProperty@UIUpdateDownloader@@@@YAJAEAV?$ComPtr@UIUpdateDownloader@@@WRL@Microsoft@@PEAUHSTRING__@@@Z; SetIntentPFNConfigurationProperty<IUpdateDownloader>(Microsoft::WRL::ComPtr<IUpdateDownloader> &,HSTRING__ *)
0x1800770ef  mov     edi, eax
0x1800770f1  test    eax, eax
0x1800770f3  js      loc_1800774E3
0x1800770f9  mov     dword ptr [rbp+250h+var_280], 40008h
0x180077100  mov     al, [rbp+250h+arg_38]
0x180077106  mov     byte ptr [rbp+250h+var_280+4], al
0x180077109  mov     dword ptr [rbp+250h+var_280+8], 40001h
0x180077110  mov     al, [rbp+250h+arg_30]
0x180077116  mov     byte ptr [rbp+250h+var_280+0Ch], al
0x180077119  mov     dword ptr [rbp+250h+var_270], 40002h
0x180077120  mov     byte ptr [rbp+250h+var_270+4], 0
0x180077124  mov     dword ptr [rbp+250h+var_268], 40005h
0x18007712b  mov     al, [rbp+250h+arg_40]
0x180077131  mov     byte ptr [rbp+250h+var_268+4], al
0x180077134  mov     [rbp+250h+var_260], 4000Ch
0x18007713b  mov     al, [rbp+250h+arg_48]
0x180077141  mov     [rbp+250h+var_25C], al
0x180077144  mov     r9, [rbp+250h+bstrString]
0x180077148  lea     r8d, [rbx+4]
0x18007714c  lea     rdx, [rbp+250h+var_280]
0x180077150  mov     rcx, [rbp+250h+var_2D0]
0x180077154  call    _SetInternalConfigurationFlags
0x180077159  mov     edi, eax
0x18007715b  test    eax, eax
0x18007715d  js      loc_1800774E3
0x180077163  test    r15, r15
0x180077166  jz      loc_18007725F
0x18007716c  mov     [rsp+350h+var_2E0], 0
0x180077175  lea     rdx, [rsp+350h+var_2E0]
0x18007717a  lea     rcx, [rbp+250h+var_2D0]
0x18007717e  call    ??$As@UIUpdateInternalConfiguration@@@?$ComPtr@UIUpdateSearcher@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUpdateInternalConfiguration@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IUpdateSearcher>::As<IUpdateInternalConfiguration>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IUpdateInternalConfiguration>>)
0x180077183  mov     dword ptr [rsp+350h+var_330], eax; int
0x180077187  lea     r9, aSpsearcherAsSp; "spSearcher.As(&spInternalConfiguration)"
0x18007718e  lea     r8, aSearchupdatepa; "SearchUpdatePackages"
0x180077195  mov     edx, 13Dh; unsigned int
0x18007719a  lea     rcx, aOnecoreuapEndu_18; "onecoreuap\\enduser\\winstore\\installs"...
0x1800771a1  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x1800771a6  mov     edi, eax
0x1800771a8  test    eax, eax
0x1800771aa  js      loc_180077255
0x1800771b0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnsureTokensAreDuplicable@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnsureTokensAreDuplicable@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureTokensAreDuplicable> `wil::Feature<__WilFeatureTraits_Feature_EnsureTokensAreDuplicable>::GetImpl(void)'::`2'::impl
0x1800771b7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnsureTokensAreDuplicable@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnsureTokensAreDuplicable>::__private_IsEnabled(void)
0x1800771bc  test    al, al
0x1800771be  jz      short loc_1800771E0
0x1800771c0  mov     r8, r15; void *
0x1800771c3  mov     edx, 40006h; unsigned int
0x1800771c8  mov     rcx, [rsp+350h+var_2E0]; struct IUpdateInternalConfiguration *
0x1800771cd  call    ?_SetWuUserTokenProperty@@YAJPEAUIUpdateInternalConfiguration@@KPEAX@Z; _SetWuUserTokenProperty(IUpdateInternalConfiguration *,ulong,void *)
0x1800771d2  lea     r9, aSetwuusertoken_0; "_SetWuUserTokenProperty(spInternalConfi"...
0x1800771d9  mov     edx, 142h
0x1800771de  jmp     short loc_18007723C
0x1800771e0  xorps   xmm0, xmm0
0x1800771e3  xor     eax, eax
0x1800771e5  movups  xmmword ptr [rbp+250h+pvarg], xmm0
0x1800771e9  mov     qword ptr [rbp+250h+pvarg+10h], rax
0x1800771ed  lea     rcx, [rbp+250h+pvarg]; pvarg
0x1800771f1  call    cs:__imp_VariantInit
0x1800771f7  mov     eax, 13h
0x1800771fc  mov     word ptr [rbp+250h+pvarg], ax
0x180077200  mov     dword ptr [rbp+250h+pvarg+8], r15d
0x180077204  mov     rcx, [rsp+350h+var_2E0]
0x180077209  movups  xmm0, xmmword ptr [rbp+250h+pvarg]
0x18007720d  movaps  [rbp+250h+var_280], xmm0
0x180077211  movsd   xmm1, qword ptr [rbp+250h+pvarg+10h]
0x180077216  movsd   [rbp+250h+var_270], xmm1
0x18007721b  mov     rax, [rcx]
0x18007721e  lea     r8, [rbp+250h+var_280]
0x180077222  mov     edx, 40006h
0x180077227  mov     rax, [rax+20h]
0x18007722b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077230  lea     r9, aSpinternalconf_2; "spInternalConfiguration->put_InternalCo"...
0x180077237  mov     edx, 14Ah; unsigned int
0x18007723c  mov     dword ptr [rsp+350h+var_330], eax; int
0x180077240  lea     r8, aSearchupdatepa; "SearchUpdatePackages"
0x180077247  lea     rcx, aOnecoreuapEndu_18; "onecoreuap\\enduser\\winstore\\installs"...
0x18007724e  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x180077253  mov     edi, eax
0x180077255  lea     rcx, [rsp+350h+var_2E0]
0x18007725a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007725f  xor     r15d, r15d
0x180077262  test    edi, edi
0x180077264  js      loc_1800774E6
0x18007726a  mov     [rsp+350h+var_2D8], r15
0x18007726f  mov     [rsp+350h+var_2E0], r15
0x180077274  lea     r9, [rsp+350h+var_2E0]; unsigned __int64 *
0x180077279  lea     r8, [rsp+350h+var_2D8]; unsigned __int16 **
0x18007727e  mov     edx, 100h; unsigned __int64
0x180077283  lea     rcx, [rbp+250h+pszDest]; pszDest
0x180077287  cmp     r12d, 2
0x18007728b  jnz     short loc_1800772AA
0x18007728d  mov     [rsp+350h+var_320], rsi
0x180077292  lea     rax, aAppcategoryids; "AppCategoryIDs contains '%s'"
0x180077299  mov     [rsp+350h+var_328], rax; unsigned __int16 *
0x18007729e  mov     [rsp+350h+var_330], r15; unsigned int
0x1800772a3  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800772a8  jmp     short loc_1800772D5
0x1800772aa  mov     eax, ebx
0x1800772ac  sub     eax, r12d
0x1800772af  neg     eax
0x1800772b1  sbb     eax, eax
0x1800772b3  add     eax, 31h ; '1'
0x1800772b6  mov     [rsp+350h+var_318], rsi
0x1800772bb  mov     dword ptr [rsp+350h+var_320], eax
0x1800772bf  lea     rax, aIsinstalledCAn; "IsInstalled=%c AND AppCategoryIDs conta"...
0x1800772c6  mov     [rsp+350h+var_328], rax; unsigned __int16 *
0x1800772cb  mov     [rsp+350h+var_330], r15; unsigned int
0x1800772d0  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800772d5  mov     edi, eax
0x1800772d7  test    eax, eax
0x1800772d9  js      loc_1800774E6
0x1800772df  test    r14, r14
0x1800772e2  jz      short loc_18007730D
0x1800772e4  cmp     [r14], r15w
0x1800772e8  jz      short loc_18007730D
0x1800772ea  mov     r9, r14
0x1800772ed  lea     r8, aAndUpdateidS; " AND UpdateID='%s'"
0x1800772f4  mov     rdx, [rsp+350h+var_2E0]; unsigned __int64
0x1800772f9  mov     rcx, [rsp+350h+var_2D8]; unsigned __int16 *
0x1800772fe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180077303  mov     edi, eax
0x180077305  test    eax, eax
0x180077307  js      loc_1800774E6
0x18007730d  lea     rax, [rbp+250h+pszDest]
0x180077311  mov     [rsp+350h+var_310], rax
0x180077316  mov     [rsp+350h+var_318], r15; unsigned __int16 *
0x18007731b  mov     [rsp+350h+var_320], r15; char *
0x180077320  lea     rax, aWuQueryS; "WU query: \"%s\""
0x180077327  mov     [rsp+350h+var_328], rax; int
0x18007732c  mov     dword ptr [rsp+350h+var_330], 0FFFFFFFFh; int
0x180077334  lea     r9, aSearchupdatepa; "SearchUpdatePackages"
0x18007733b  mov     r8d, 167h; unsigned int
0x180077341  lea     rdx, aOnecoreuapEndu_18; "onecoreuap\\enduser\\winstore\\installs"...
0x180077348  mov     ecx, 3; unsigned int
0x18007734d  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180077352  mov     edi, 8007000Eh
0x180077357  lea     rdx, [rbp+250h+pszDest]; unsigned __int16 *
0x18007735b  lea     rcx, [rbp+250h+bstrString]; this
0x18007735f  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180077364  nop
0x180077365  mov     rbx, [rbp+250h+bstrString]
0x180077369  test    rbx, rbx
0x18007736c  jz      loc_1800774D8
0x180077372  mov     [rsp+350h+var_2D8], r15
0x180077377  mov     rsi, [rbp+250h+var_2D0]
0x18007737b  mov     rax, [rsi]
0x18007737e  mov     rdi, [rax+98h]
0x180077385  lea     rcx, [rsp+350h+var_2D8]
0x18007738a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007738f  lea     r8, [rsp+350h+var_2D8]
0x180077394  mov     rdx, rbx
0x180077397  mov     rcx, rsi
0x18007739a  mov     rax, rdi
  ... truncated ...
```
