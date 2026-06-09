# WebAuthNGetPlatformCredentialListServer

- ea: `0x18008c250`
- end: `0x18008d532`
- name: `WebAuthNGetPlatformCredentialListServer`
- size: `4834`
- prototype: ``
- caller_count: `2`
- callee_count: `98`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800da85c`
- `0x18010a678`

## callees

- `0x18001ee7c`
- `0x180021878`
- `0x18002a07c`
- `0x180031708`
- `0x1800350b4`
- `0x180036da4`
- `0x180037f6c`
- `0x18003988c`
- `0x1800412c8`
- `0x180042e40`
- `0x1800467e0`
- `0x18004685c`
- `0x18004d8f4`
- `0x18004f5b4`
- `0x180052e3c`
- `0x18005378c`
- `0x180067c74`
- `0x180067e00`
- `0x180068214`
- `0x18006f30c`
- `0x18006f730`
- `0x18006f750`
- `0x18006f7b0`
- `0x180072904`
- `0x180072974`
- `0x180072a34`
- `0x180077f4c`
- `0x18007d7c4`
- `0x18007daac`
- `0x18007e2a8`
- `0x18007e320`
- `0x18007f088`
- `0x18007f4c8`
- `0x18007f59c`
- `0x18007f740`
- `0x18007fa40`
- `0x18007faac`
- `0x18007fbb4`
- `0x18007fbe8`
- `0x18007fde4`
- `0x18007fea0`
- `0x18007ff24`
- `0x18007ffe0`
- `0x180080684`
- `0x180080b9c`
- `0x180080bd4`
- `0x180080c04`
- `0x180080c3c`
- `0x180080d34`
- `0x180080d8c`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18008c65d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18008c7c8`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18008c8ac`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18008cb6d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18008ccd1`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18008c65d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18008c7c8`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18008c8ac`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18008cb6d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18008ccd1`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18008c605`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18008c770`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18008c84a`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18008cb15`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18008cc6c`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18008c605`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18008c770`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18008c84a`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18008cb15`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18008cc6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008d386`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008d386`

## string_xrefs

- `0x18008c378`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18008c997`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18008cf35`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18008d207`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18008cf74`: `GetPluginPasskeyCredentialDetailsTest::reason::timed_out`
- `0x18008cfe2`: `GetPluginPasskeyCredentialDetailsTest::reason::timed_out`

## pseudocode

```c
// Hidden C++ exception states: #wind=47
__int64 __fastcall WebAuthNGetPlatformCredentialListServer(
        __int128 *hExistingToken,
        __int64 a2,
        int a3,
        int a4,
        int a5,
        _DWORD *a6,
        __int64 a7)
{
  int v7; // ebx
  const unsigned __int16 *v9; // r12
  unsigned int v11; // r15d
  _QWORD *v12; // rax
  int DuplicateHandle; // eax
  unsigned int v14; // ebx
  const char *v15; // r9
  __int64 result; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  char IsEnabled; // al
  char *v20; // rdx
  _QWORD *v21; // rax
  const unsigned __int16 *v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rdx
  _QWORD *v25; // rax
  const unsigned __int16 *v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rdx
  const unsigned __int16 *v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rdx
  std::thread *v32; // rbx
  void *v33; // rax
  __int64 v34; // r13
  unsigned int CredentialsFrom; // eax
  CredentialInfo *v36; // rax
  CredentialInfo *v37; // rdi
  char v38; // al
  char *v39; // rdx
  _QWORD *v40; // rax
  const unsigned __int16 *v41; // rdx
  __int64 v42; // rax
  __int64 v43; // rdx
  _QWORD *v44; // rax
  const unsigned __int16 *v45; // rdx
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // rax
  const char *v51; // r9
  CredentialInfo *v52; // r15
  CredentialInfo *i; // r14
  const char *v54; // rdx
  const char *v55; // rax
  const char *v56; // rdx
  const char *v57; // r14
  __int64 v58; // rdi
  const char *v59; // rdx
  const char *v60; // rdi
  _QWORD *v61; // rax
  unsigned __int64 v62; // rdi
  __int64 v63; // rax
  const char *v64; // rdx
  const char *v65; // rax
  const char *v66; // rdx
  const char *v67; // rax
  const char *v68; // rdx
  const char *v69; // rax
  _DWORD *v70; // r12
  _QWORD *v71; // rdi
  HLOCAL v72; // rax
  unsigned __int64 v73; // rdi
  HLOCAL v74; // rcx
  int v75; // [rsp+20h] [rbp-288h]
  int v76; // [rsp+20h] [rbp-288h]
  __int64 v77; // [rsp+30h] [rbp-278h] BYREF
  char v78[8]; // [rsp+38h] [rbp-270h] BYREF
  __int64 v79; // [rsp+40h] [rbp-268h] BYREF
  int v80; // [rsp+48h] [rbp-260h] BYREF
  unsigned int v81; // [rsp+50h] [rbp-258h] BYREF
  char v82[8]; // [rsp+58h] [rbp-250h] BYREF
  __int64 v83; // [rsp+60h] [rbp-248h] BYREF
  int v84; // [rsp+68h] [rbp-240h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-238h] BYREF
  __int64 v86; // [rsp+78h] [rbp-230h] BYREF
  __int64 v87; // [rsp+80h] [rbp-228h] BYREF
  __int64 v88; // [rsp+88h] [rbp-220h] BYREF
  __int64 v89; // [rsp+90h] [rbp-218h] BYREF
  __int128 v90; // [rsp+98h] [rbp-210h] BYREF
  __int128 v91; // [rsp+A8h] [rbp-200h] BYREF
  __int128 v92; // [rsp+B8h] [rbp-1F0h] BYREF
  CredentialInfo *v93[2]; // [rsp+C8h] [rbp-1E0h] BYREF
  __int64 v94; // [rsp+D8h] [rbp-1D0h]
  _DWORD *v95; // [rsp+E0h] [rbp-1C8h]
  __int64 v96; // [rsp+E8h] [rbp-1C0h]
  _BYTE v97[16]; // [rsp+F0h] [rbp-1B8h] BYREF
  __int128 v98; // [rsp+100h] [rbp-1A8h] BYREF
  __int64 v99; // [rsp+110h] [rbp-198h]
  __int128 *v100; // [rsp+118h] [rbp-190h] BYREF
  char v101; // [rsp+120h] [rbp-188h]
  std::thread *v102; // [rsp+128h] [rbp-180h] BYREF
  char v103; // [rsp+130h] [rbp-178h]
  _BYTE v104[24]; // [rsp+138h] [rbp-170h] BYREF
  __int128 v105; // [rsp+150h] [rbp-158h] BYREF
  _BYTE v106[16]; // [rsp+160h] [rbp-148h] BYREF
  _BYTE v107[32]; // [rsp+170h] [rbp-138h] BYREF
  void *Src; // [rsp+190h] [rbp-118h] BYREF
  __int64 v109; // [rsp+198h] [rbp-110h]
  int v110; // [rsp+1A8h] [rbp-100h]
  char v111; // [rsp+1D0h] [rbp-D8h]
  __int64 v112; // [rsp+1E0h] [rbp-C8h] BYREF
  char v113; // [rsp+1E8h] [rbp-C0h]
  char v114; // [rsp+1F0h] [rbp-B8h]
  _BYTE v115[96]; // [rsp+200h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  v7 = a4;
  v9 = (const unsigned __int16 *)a2;
  v100 = hExistingToken;
  LODWORD(hMem) = a5;
  v79 = a2;
  v95 = a6;
  v96 = a7;
  v11 = 0;
  v81 = 0;
  v98 = 0;
  v99 = 0;
  tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>>>(v82);
  if ( v95 )
  {
    v12 = (_QWORD *)v96;
    if ( v96 )
    {
      *v95 = 0;
      *v12 = 0;
    }
  }
  try
  {
    std::promise<CtapCbor::WebAuthNCredentialDetailsList>::promise<CtapCbor::WebAuthNCredentialDetailsList>(v107);
    std::promise<CtapCbor::WebAuthNCredentialDetailsList>::get_future(v107, v106);
    v105 = 0;
    v92 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::GetImpl'::`2'::impl) )
    {
      DuplicateHandle = CtapUtilsGetDuplicateHandle(hExistingToken);
      v14 = DuplicateHandle;
      if ( DuplicateHandle < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x137B,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
          (const char *)(unsigned int)DuplicateHandle,
          v75);
        std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(&v92);
        std::thread::~thread((std::thread *)&v105);
        std::_State_manager<CtapCbor::WebAuthNCredentialDetailsList>::~_State_manager<CtapCbor::WebAuthNCredentialDetailsList>(v106);
        std::promise<CtapCbor::WebAuthNCredentialDetailsList>::~promise<CtapCbor::WebAuthNCredentialDetailsList>(v107);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>,wil::err_returncode_policy>(v82);
        std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(&v98);
        return v14;
      }
      v7 = a4;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::GetImpl'::`2'::impl) )
    {
      wil::impersonate_token(v78, hExistingToken);
      wil::reg::try_get_value<unsigned int>(
        &v77,
        -2147483647,
        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Themes\\Personalize",
        L"SystemUsesLightTheme");
      if ( !BYTE4(v77) || (v11 = 1, *(_DWORD *)std::optional<unsigned int>::value(&v77) != 1) )
        v11 = 2;
      v81 = v11;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v78);
    }
    std::promise<CtapCbor::WebAuthNCredentialDetailsList>::promise<CtapCbor::WebAuthNCredentialDetailsList>(v104);
    std::promise<CtapCbor::WebAuthNCredentialDetailsList>::get_future(v104, v97);
    v90 = 0;
    v89 = 0;
    v88 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl,
                            v17,
                            v18) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
      {
        if ( !v7 || a3 )
          goto LABEL_41;
        IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsFixTipCrash>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsFixTipCrash>::GetImpl'::`2'::impl);
        v20 = v78;
        if ( IsEnabled )
        {
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTest,_tip_GetPluginPasskeyCredentialDetailsTest>>::operator->(
                                  &v89,
                                  v78)
                   + 276LL) = v9 == 0;
          tip2::test_data_control<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTest,_tip_GetPluginPasskeyCredentialDetailsTest>>::~test_data_control<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTest,_tip_GetPluginPasskeyCredentialDetailsTest>>(v78);
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTest,_tip_GetPluginPasskeyCredentialDetailsTest>>::operator->(
                                  &v89,
                                  v78)
                   + 277LL) = a5 != 0;
          tip2::test_data_control<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTest,_tip_GetPluginPasskeyCredentialDetailsTest>>::~test_data_control<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTest,_tip_GetPluginPasskeyCredentialDetailsTest>>(v78);
          if ( v89 && (*(_QWORD *)(v89 + 248) || (*(_DWORD *)(v89 + 72) & 0x100) != 0) )
            wil::com_ptr_t<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTest,_tip_GetPluginPasskeyCredentialDetailsTest>,wil::err_returncode_policy>::reset(&v89);
          v21 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTest,_tip_GetPluginPasskeyCredentialDetailsTest>>::ensure_data(&v89);
          tip2::details::shared_data<0,0,0>::start(*v21 + 8LL, &v102);
          v22 = v9;
          if ( !v9 )
            v22 = &dword_18015030C;
          v23 = std::wstring::wstring(&v112, v22);
          v24 = WebAuthNGetPlatformCredentialListServer_::_46_::_lambda_2_::_lambda_2_(
                  (unsigned int)v115,
                  (unsigned int)v104,
                  (unsigned int)&v92,
                  (unsigned int)&v81,
                  v23,
                  (__int64)&v89);
          std::make_unique_std::tuple__WebAuthNGetPlatformCredentialListServer_::_68_::_lambda_6_____WebAuthNGetPlatformCredentialListServer_::_68_::_lambda_6__0_(
            &v77,
            v24);
          v83 = _o__beginthreadex(
                  0,
                  0,
                  std::thread::_Invoke_std::tuple__WebAuthNGetPlatformCredentialListServer_::_46_::_lambda_2____0_,
                  v77,
                  0,
                  &v84);
          if ( v83 )
          {
            v77 = 0;
            std::unique_ptr_std::tuple__WebAuthNGetPlatformCredentialListServer_::_46_::_lambda_2____std::default_delete_std::tuple__WebAuthNGetPlatformCredentialListServer_::_46_::_lambda_2_______::_unique_ptr_std::tuple__WebAuthNGetPlatformCredentialListServer_::_46_::_lambda_2____std::default_delete_std::tuple__WebAuthNGetPlatformCredentialListServer_::_46_::_lambda_2_______(&v77);
            std::thread::operator=(&v90, &v83);
            std::thread::~thread((std::thread *)&v83);
            WebAuthNGetPlatformCredentialListServer_::_46_::_lambda_2_::__lambda_2_(v115);
LABEL_39:
            std::wstring::_Tidy_deallocate(&v112);
            goto LABEL_41;
          }
          v84 = 0;
          std::_Throw_Cpp_error(6);
        }
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTestOld,_tip_GetPluginPasskeyCredentialDetailsTestOld>>::operator->(
                                &v88,
                                v20)
                 + 276LL) = v9 == 0;
        tip2::test_data_control<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTestOld,_tip_GetPluginPasskeyCredentialDetailsTestOld>>::~test_data_control<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTestOld,_tip_GetPluginPasskeyCredentialDetailsTestOld>>(v78);
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTestOld,_tip_GetPluginPasskeyCredentialDetailsTestOld>>::operator->(
                                &v88,
                                v78)
                 + 277LL) = a5 != 0;
        tip2::test_data_control<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTestOld,_tip_GetPluginPasskeyCredentialDetailsTestOld>>::~test_data_control<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTestOld,_tip_GetPluginPasskeyCredentialDetailsTestOld>>(v78);
        if ( v88 && (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(v88 + 8) )
          wil::com_ptr_t<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTestOld,_tip_GetPluginPasskeyCredentialDetailsTestOld>,wil::err_returncode_policy>::reset(&v88);
        v25 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTestOld,_tip_GetPluginPasskeyCredentialDetailsTestOld>>::ensure_data(&v88);
        tip2::details::shared_data<1,0,0>::start(*v25 + 8LL, &v102);
        v26 = v9;
        if ( !v9 )
          v26 = &dword_18015030C;
        v27 = std::wstring::wstring(&v112, v26);
        v28 = WebAuthNGetPlatformCredentialListServer_::_70_::_lambda_7_::_lambda_7_(
                (unsigned int)&Src,
                (unsigned int)v104,
                (unsigned int)&v92,
                (unsigned int)&v81,
                v27);
        std::make_unique_std::tuple__WebAuthNGetPlatformCredentialListServer_::_70_::_lambda_7_____WebAuthNGetPlatformCredentialListServer_::_70_::_lambda_7__0_(
          &v77,
          v28);
        v83 = _o__beginthreadex(
                0,
                0,
                std::thread::_Invoke_std::tuple__WebAuthNGetPlatformCredentialListServer_::_48_::_lambda_3____0_,
                v77,
                0,
                &v84);
        if ( v83 )
        {
LABEL_38:
          v77 = 0;
          std::unique_ptr_std::tuple__WebAuthNGetPlatformCredentialListServer_::_53_::_lambda_4____std::default_delete_std::tuple__WebAuthNGetPlatformCredentialListServer_::_53_::_lambda_4_______::_unique_ptr_std::tuple__WebAuthNGetPlatformCredentialListServer_::_53_::_lambda_4____std::default_delete_std::tuple__WebAuthNGetPlatformCredentialListServer_::_53_::_lambda_4_______(&v77);
          std::thread::operator=(&v90, &v83);
          std::thread::~thread((std::thread *)&v83);
          WebAuthNGetPlatformCredentialListServer_::_53_::_lambda_4_::__lambda_4_(&Src);
          goto LABEL_39;
        }
        v84 = 0;
        std::_Throw_Cpp_error(6);
      }
      if ( !v7 )
        goto LABEL_41;
      v29 = v9;
      if ( !v9 )
        v29 = &dword_18015030C;
      v30 = std::wstring::wstring(&v112, v29);
      v31 = WebAuthNGetPlatformCredentialListServer_::_70_::_lambda_7_::_lambda_7_(
              (unsigned int)&Src,
              (unsigned int)v104,
              (unsigned int)&v92,
              (unsigned int)&v81,
              v30);
      std::make_unique_std::tuple__WebAuthNGetPlatformCredentialListServer_::_70_::_lambda_7_____WebAuthNGetPlatformCredentialListServer_::_70_::_lambda_7__0_(
        &v77,
        v31);
      v83 = _o__beginthreadex(
              0,
              0,
              std::thread::_Invoke_std::tuple__WebAuthNGetPlatformCredentialListServer_::_53_::_lambda_4____0_,
              v77,
              0,
              &v84);
      if ( v83 )
        goto LABEL_38;
      v84 = 0;
      std::_Throw_Cpp_error(6);
    }
LABEL_41:
    v32 = (std::thread *)&v90;
    v102 = (std::thread *)&v90;
    v103 = 1;
    v33 = operator new(0xF8u);
    v34 = std::_Associated_state<DeviceBoundPasskeyListResult>::_Associated_state<DeviceBoundPasskeyListResult>(v33);
    v112 = v34;
    v113 = 0;
    v114 = 0;
    if ( !(unsigned __int8)std::_State_manager<DeviceBoundPasskeyListResult>::valid(&v112) )
      std::_Throw_future_error2(4);
    v114 = 1;
    v83 = v34;
    LOBYTE(v84) = 1;
    if ( v34 )
      _InterlockedIncrement((volatile signed __int32 *)(v34 + 8));
    v91 = 0;
    v87 = 0;
    v86 = 0;
    *(_OWORD *)v93 = 0;
    v94 = 0;
    v111 = 1;
    CredentialsFrom = CredentialAuthenticatorCache::GetCredentialsFrom(hExistingToken, &Src, v9, v93);
    wil::details::in1diag3::Log_IfFailedWithExpected(
      retaddr,
      (void *)0x1464,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)CredentialsFrom,
      1,
      0x80090011);
    std::_Variant_base<FidoCredProvHelper::Locations::Empty,FidoCredProvHelper::Locations::ThisPc,FidoCredProvHelper::Locations::QrCode,FidoCredProvHelper::Locations::SecurityKey,FidoCredProvHelper::Locations::LinkedDevice,FidoCredProvHelper::Locations::PluginAuthenticator,FidoCredProvHelper::Locations::SyncedAccount>::_Destroy(&Src);
    v36 = v93[0];
    v37 = v93[1];
    if ( v93[0] == v93[1] )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
      {
        v38 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsFixTipCrash>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsFixTipCrash>::GetImpl'::`2'::impl);
        v39 = v78;
        if ( v38 )
        {
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_GetDeviceBoundPasskeyCredentialDetailsTest,_tip_GetDeviceBoundPasskeyCredentialDetailsTest>>::operator->(
                                  &v87,
                                  v78)
                   + 276LL) = v9 == 0;
          tip2::test_data_control<tip2::details::merged_data<_tip_GetDeviceBoundPasskeyCredentialDetailsTest,_tip_GetDeviceBoundPasskeyCredentialDetailsTest>>::~test_data_control<tip2::details::merged_data<_tip_GetDeviceBoundPasskeyCredentialDetailsTest,_tip_GetDeviceBoundPasskeyCredentialDetailsTest>>(v78);
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_GetDeviceBoundPasskeyCredentialDetailsTest,_tip_GetDeviceBoundPasskeyCredentialDetailsTest>>::operator->(
                                  &v87,
                                  v78)
                   + 277LL) = a5 != 0;
          tip2::test_data_control<tip2::details::merged_data<_tip_GetDeviceBoundPasskeyCredentialDetailsTest,_tip_GetDeviceBoundPasskeyCredentialDetailsTest>>::~test_data_control<tip2::details::merged_data<_tip_GetDeviceBoundPasskeyCredentialDetailsTest,_tip_GetDeviceBoundPasskeyCredentialDetailsTest>>(v78);
          if ( v87 && (*(_QWORD *)(v87 + 248) || (*(_DWORD *)(v87 + 72) & 0x100) != 0) )
            wil::com_ptr_t<tip2::details::merged_data<_tip_GetDeviceBoundPasskeyCredentialDetailsTest,_tip_GetDeviceBoundPasskeyCredentialDetailsTest>,wil::err_returncode_policy>::reset(&v87);
          v40 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_GetDeviceBoundPasskeyCredentialDetailsTest,_tip_GetDeviceBoundPasskeyCredentialDetailsTest>>::ensure_data(&v87);
          tip2::details::shared_data<0,0,0>::start(*v40 + 8LL, &v79);
          v41 = v9;
          if ( !v9 )
            v41 = &dword_18015030C;
          v42 = std::wstring::wstring(&Src, v41);
          v43 = WebAuthNGetPlatformCredentialListServer_::_68_::_lambda_6_::_lambda_6_(
                  (unsigned int)v115,
                  (unsigned int)&v112,
                  (unsigned int)&v92,
                  (unsigned int)&v81,
                  v42,
                  (__int64)&v87);
          std::make_unique_std::tuple__WebAuthNGetPlatformCredentialListServer_::_68_::_lambda_6_____WebAuthNGetPlatformCredentialListServer_::_68_::_lambda_6__0_(
            &v77,
            v43);
          v79 = _o__beginthreadex(
                  0,
                  0,
                  std::thread::_Invoke_std::tuple__WebAuthNGetPlatformCredentialListServer_::_68_::_lambda_6____0_,
                  v77,
                  0,
                  &v80);
          if ( v79 )
          {
            v77 = 0;
            std::unique_ptr_std::tuple__WebAuthNGetPlatformCredentialListServer_::_68_::_lambda_6____std::default_delete_std::tuple__WebAuthNGetPlatformCredentialListServer_::_68_::_lambda_6_______::_unique_ptr_std::tuple__WebAuthNGetPlatformCredentialListServer_::_68_::_lambda_6____std::default_delete_std::tuple__WebAuthNGetPlatformCredentialListServer_::_68_::_lambda_6_______(&v77);
            std::thread::operator=(&v91, &v79);
            std::thread::~thread((std::thread *)&v79);
            WebAuthNGetPlatformCredentialListServer_::_68_::_lambda_6_::__lambda_6_(v115);
LABEL_63:
            std::wstring::_Tidy_deallocate(&Src);
            goto LABEL_69;
          }
          v80 = 0;
          std::_Throw_Cpp_error(6);
        }
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_GetDeviceBoundPasskeyCredentialDetailsTestOld,_tip_GetDeviceBoundPasskeyCredentialDetailsTestOld>>::operator->(
                                &v86,
                                v39)
                 + 276LL) = v9 == 0;
        tip2::test_data_control<tip2::details::merged_data<_tip_GetDeviceBoundPasskeyCredentialDetailsTestOld,_tip_GetDeviceBoundPasskeyCredentialDetailsTestOld>>::~test_data_control<tip2::details::merged_data<_tip_GetDeviceBoundPasskeyCredentialDetailsTestOld,_tip_GetDeviceBoundPasskeyCredentialDetailsTestOld>>(v78);
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_GetDeviceBoundPasskeyCredentialDetailsTestOld,_tip_GetDeviceBoundPasskeyCredentialDetailsTestOld>>::operator->(
                                &v86,
                                v78)
                 + 277LL) = a5 != 0;
        tip2::test_data_control<tip2::details::merged_data<_tip_GetDeviceBoundPasskeyCredentialDetailsTestOld,_tip_GetDeviceBoundPasskeyCredentialDetailsTestOld>>::~test_data_control<tip2::details::merged_data<_tip_GetDeviceBoundPasskeyCredentialDetailsTestOld,_tip_GetDeviceBoundPasskeyCredentialDetailsTestOld>>(v78);
        if ( v86 && (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(v86 + 8) )
          wil::com_ptr_t<tip2::details::merged_data<_tip_GetDeviceBoundPasskeyCredentialDetailsTestOld,_tip_GetDeviceBoundPasskeyCredentialDetailsTestOld>,wil::err_returncode_policy>::reset(&v86);
        v44 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_GetDeviceBoundPasskeyCredentialDetailsTestOld,_tip_GetDeviceBoundPasskeyCredentialDetailsTestOld>>::ensure_data(&v86);
        tip2::details::shared_data<1,0,0>::start(*v44 + 8LL, &v79);
        v45 = v9;
        if ( !v9 )
          v45 = &dword_18015030C;
        v46 = std::wstring::wstring(&Src, v45);
        v47 = WebAuthNGetPlatformCredentialListServer_::_70_::_lambda_7_::_lambda_7_(
                (unsigned int)v115,
                (unsigned int)&v112,
                (unsigned int)&v92,
                (unsigned int)&v81,
                v46);
        std::make_unique_std::tuple__WebAuthNGetPlatformCredentialListServer_::_70_::_lambda_7_____WebAuthNGetPlatformCredentialListServer_::_70_::_lambda_7__0_(
          &v77,
          v47);
        v79 = _o__beginthreadex(
                0,
                0,
                std::thread::_Invoke_std::tuple__WebAuthNGetPlatformCredentialListServer_::_70_::_lambda_7____0_,
                v77,
                0,
                &v80);
        if ( v79 )
        {
          v77 = 0;
          std::unique_ptr_std::tuple__WebAuthNGetPlatformCredentialListServer_::_70_::_lambda_7____std::default_delete_std::tuple__WebAuthNGetPlatformCredentialListServer_::_70_::_lambda_7_______::_unique_ptr_std::tuple__WebAuthNGetPlatformCredentialListServer_::_70_::_lambda_7____std::default_delete_std::tuple__WebAuthNGetPlatformCredentialListServer_::_70_::_lambda_7_______(&v77);
          std::thread::operator=(&v91, &v79);
          std::thread::~thread((std::thread *)&v79);
          WebAuthNGetPlatformCredentialListServer_::_70_::_lambda_7_::__lambda_7_(v115);
          goto LABEL_63;
        }
        v80 = 0;
        std::_Throw_Cpp_error(6);
      }
      try
      {
        GetDeviceBoundPasskeyCredentialDetails(&Src, v100, v11, v9);
        std::ranges::_Move_fn::operator()<std::vector<CtapCbor::WebAuthNCredentialDetails> &,std::back_insert_iterator<std::vector<CtapCbor::WebAuthNCredentialDetails>>>(
          &v100,
          (__int64 *)&Src,
          (__int64)&v98);
        v50 = tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>>::operator->(
                v82,
                &v100);
        *(_DWORD *)(*(_QWORD *)v50 + 280LL) = v110;
        tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>>(&v100);
        std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(&Src);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x14B7,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
          v51);
        v32 = v102;
        v34 = v83;
        a5 = (int)hMem;
        v9 = (const unsigned __int16 *)v79;
      }
    }
    else
    {
      v52 = v93[1];
      for ( i = v93[0]; i != v52; i = (CredentialInfo *)((char *)i + 352) )
      {
        std::vector<CtapCbor::WebAuthNCredentialDetails>::_Emplace_one_at_back<CtapCbor::WebAuthNCredentialDetails>(
          &v98,
          i);
        v37 = v93[1];
        v36 = v93[0];
      }
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>>::operator->(
                               v82,
                               &v79)
                + 280LL) = -1171354717 * ((v37 - v36) >> 5);
      tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>>(&v79);
    }
LABEL_69:
    v100 = &v91;
    v101 = 1;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl,
                            v48,
                            v49) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
      {
        if ( !a4
          || a3
          || !(unsigned __int8)std::_State_manager<CtapCbor::WebAuthNCredentialDetailsList>::valid(v97)
          || (v79 = 100,
              (unsigned int)std::_State_manager<CtapCbor::WebAuthNCredentialDetailsList>::wait_for<__int64,std::ratio<1,1000>>(
                              v97,
                              &v79)) )
        {
          if ( DWORD2(v90) )
          {
            std::thread::detach((std::thread *)&v90);
            wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)0x14DC,
              (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
              (const char *)0x800705B4LL,
              v76);
            v55 = tip2::details::reason_string(
                    (tip2::details *)"WebAuthNGetPlatformCredentialListTest::reason::timed_out",
                    v54);
            tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>>::set_flag(
              v82,
              4,
              v55);
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsFixTipCrash>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsFixTipCrash>::GetImpl'::`2'::impl) )
            {
              v57 = tip2::details::reason_string(
                      (tip2::details *)"GetPluginPasskeyCredentialDetailsTest::reason::timed_out",
                      v56);
              v58 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTest,_tip_GetPluginPasskeyCredentialDetailsTest>>::ensure_data(&v89)
                  + 8LL;
              if ( (unsigned __int8)tip2::details::shared_data<0,0,0>::begin_update(v58) )
                tip2::details::shared_data<1,0,0>::get_or_add_flag_under_lock(v58, 2, v57);
              tip2::details::shared_data<0,0,0>::end_update(v58);
            }
            else if ( v88 && (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v88 + 8) )
            {
              v60 = tip2::details::reason_string(
                      (tip2::details *)"GetPluginPasskeyCredentialDetailsTest::reason::timed_out",
                      v59);
              v61 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTestOld,_tip_GetPluginPasskeyCredentialDetailsTestOld>>::ensure_data(&v88);
              tip2::details::shared_data<1,0,0>::set_flag_without_lock(*v61 + 8LL, 2, v60);
            }
          }
          goto LABEL_90;
        }
      }
      else if ( !a4
             || !v9
             || !(unsigned __int8)std::_State_manager<CtapCbor::WebAuthNCredentialDetailsList>::valid(v97)
             || (v79 = 100,
                 (unsigned int)std::_State_manager<CtapCbor::WebAuthNCredentialDetailsList>::wait_for<__int64,std::ratio<1,1000>>(
                                 v97,
                                 &v79)) )
      {
        if ( DWORD2(v90) )
          std::thread::detach((std::thread *)&v90);
        goto LABEL_90;
      }
      std::future<CtapCbor::WebAuthNCredentialDetailsList>::get(v97, &Src);
      std::ranges::_Move_fn::operator()<std::vector<CtapCbor::WebAuthNCredentialDetails> &,std::back_insert_iterator<std::vector<CtapCbor::WebAuthNCredentialDetails>>>(
        &v79,
        (__int64 *)&Src,
        (__int64)&v98);
      v62 = 0xF0F0F0F0F0F0F0F1uLL * ((v109 - (__int64)Src) >> 4);
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>>::operator->(
                               v82,
                               &v79)
                + 284LL) = v62;
      tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>>(&v79);
      std::thread::join((std::thread *)&v90);
      std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(&Src);
    }
LABEL_90:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
    {
      if ( !(unsigned __int8)std::_State_manager<DeviceBoundPasskeyListResult>::valid(&v83)
        || (v79 = a5 != 0 ? 1000 : 200,
            (unsigned int)std::_Associated_state<DeviceBoundPasskeyListResult>::_Wait_for<__int64,std::ratio<1,1000>>(
                            v34,
                            &v79)) )
      {
        if ( DWORD2(v91) )
        {
          std::thread::detach((std::thread *)&v91);
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x1530,
            (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
            (const char *)0x800705B4LL,
            v76);
          v65 = tip2::details::reason_string(
                  (tip2::details *)"WebAuthNGetPlatformCredentialListTest::reason::timed_out",
                  v64);
          tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>>::set_flag(
            v82,
            4,
            v65);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsFixTipCrash>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsFixTipCrash>::GetImpl'::`2'::impl) )
          {
            v67 = tip2::details::reason_string(
                    (tip2::details *)"GetDeviceBoundPasskeyCredentialDetailsTest::reason::timed_out",
                    v66);
            tip2::tip_test<tip2::details::merged_data<_tip_GetDeviceBoundPasskeyCredentialDetailsTest,_tip_GetDeviceBoundPasskeyCredentialDetailsTest>>::set_flag_value<unsigned short>(
              &v87,
              2,
              v67);
          }
          else if ( v86 && (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v86 + 8) )
          {
            v69 = tip2::details::reason_string(
                    (tip2::details *)"GetDeviceBoundPasskeyCredentialDetailsTest::reason::timed_out",
                    v68);
            tip2::tip_test<tip2::details::merged_data<_tip_GetDeviceBoundPasskeyCredentialDetailsTestOld,_tip_GetDeviceBoundPasskeyCredentialDetailsTestOld>>::set_flag_value<unsigned short>(
              &v86,
              2,
              v69);
          }
        }
      }
      else
      {
        std::future<DeviceBoundPasskeyListResult>::get(&v83, &Src);
        std::ranges::_Move_fn::operator()<std::vector<CtapCbor::WebAuthNCredentialDetails> &,std::back_insert_iterator<std::vector<CtapCbor::WebAuthNCredentialDetails>>>(
          &v79,
          (__int64 *)&Src,
          (__int64)&v98);
        v63 = tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>>::operator->(
                v82,
                &v79);
        *(_DWORD *)(*(_QWORD *)v63 + 280LL) = v110;
        tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>>(&v79);
        std::thread::join((std::thread *)&v91);
        std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(&Src);
      }
    }
    v70 = v95;
    if ( v95 )
    {
      v71 = (_QWORD *)v96;
      if ( v96 )
      {
        CtapCbor::WebAuthNCredentialDetailsList::ToCbor(&v98, &Src);
        wil::make_unique_hlocal<unsigned char [0]>(&hMem, v109 - (_QWORD)Src);
        memcpy_0(hMem, Src, v109 - (_QWORD)Src);
        *v70 = wil::safe_cast<unsigned long,unsigned __int64,0>(v109 - (_QWORD)Src);
        v72 = hMem;
        hMem = 0;
        *v71 = v72;
        v73 = 0xF0F0F0F0F0F0F0F1uLL * ((__int64)(*((_QWORD *)&v98 + 1) - v98) >> 4);
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>>::operator->(
                                 v82,
                                 &v79)
                  + 272LL) = v73;
        tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>>(&v79);
        v74 = hMem;
        hMem = 0;
        if ( v74 )
          LocalFree(v74);
        std::vector<unsigned char>::_Tidy(&Src);
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl)
      && DWORD2(v91) )
    {
      std::thread::detach((std::thread *)&v91);
    }
    if ( v93[0] )
    {
      std::_Destroy_range<std::allocator<CredentialInfo>>(v93[0]);
      std::_Deallocate<16>(v93[0], 32 * ((signed __int64)(v94 - (unsigned __int64)v93[0]) >> 5));
      *(_OWORD *)v93 = 0;
      v94 = 0;
    }
    wil::com_ptr_t<tip2::details::merged_data<_tip_GetDeviceBoundPasskeyCredentialDetailsTestOld,_tip_GetDeviceBoundPasskeyCredentialDetailsTestOld>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_GetDeviceBoundPasskeyCredentialDetailsTestOld,_tip_GetDeviceBoundPasskeyCredentialDetailsTestOld>,wil::err_returncode_policy>(&v86);
    wil::com_ptr_t<tip2::details::merged_data<_tip_GetDeviceBoundPasskeyCredentialDetailsTest,_tip_GetDeviceBoundPasskeyCredentialDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_GetDeviceBoundPasskeyCredentialDetailsTest,_tip_GetDeviceBoundPasskeyCredentialDetailsTest>,wil::err_returncode_policy>(&v87);
    std::thread::~thread((std::thread *)&v91);
    std::_State_manager<DeviceBoundPasskeyListResult>::~_State_manager<DeviceBoundPasskeyListResult>(&v83);
    std::promise<DeviceBoundPasskeyListResult>::~promise<DeviceBoundPasskeyListResult>(&v112);
    if ( *((_DWORD *)v32 + 2) )
      std::thread::detach(v32);
    wil::com_ptr_t<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTestOld,_tip_GetPluginPasskeyCredentialDetailsTestOld>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTestOld,_tip_GetPluginPasskeyCredentialDetailsTestOld>,wil::err_returncode_policy>(&v88);
    wil::com_ptr_t<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTest,_tip_GetPluginPasskeyCredentialDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTest,_tip_GetPluginPasskeyCredentialDetailsTest>,wil::err_returncode_policy>(&v89);
    std::thread::~thread((std::thread *)&v90);
    std::_State_manager<CtapCbor::WebAuthNCredentialDetailsList>::~_State_manager<CtapCbor::WebAuthNCredentialDetailsList>(v97);
    std::promise<CtapCbor::WebAuthNCredentialDetailsList>::~promise<CtapCbor::WebAuthNCredentialDetailsList>(v104);
    std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(&v92);
    std::thread::~thread((std::thread *)&v105);
    std::_State_manager<CtapCbor::WebAuthNCredentialDetailsList>::~_State_manager<CtapCbor::WebAuthNCredentialDetailsList>(v106);
    std::promise<CtapCbor::WebAuthNCredentialDetailsList>::~promise<CtapCbor::WebAuthNCredentialDetailsList>(v107);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>,wil::err_returncode_policy>(v82);
    std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(&v98);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x154C,
                           (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x18008c250  mov     [rsp+arg_18], r9d
0x18008c255  mov     [rsp+arg_10], r8d
0x18008c25a  push    rbx
0x18008c25b  push    rsi
0x18008c25c  push    rdi
0x18008c25d  push    r12
0x18008c25f  push    r13
0x18008c261  push    r14
0x18008c263  push    r15
0x18008c265  sub     rsp, 270h
0x18008c26c  mov     rax, cs:__security_cookie
0x18008c273  xor     rax, rsp
0x18008c276  mov     [rsp+2A8h+var_48], rax
0x18008c27e  mov     ebx, r9d
0x18008c281  mov     r14d, r8d
0x18008c284  mov     r12, rdx
0x18008c287  mov     rdi, rcx
0x18008c28a  mov     [rsp+2A8h+var_190], rcx
0x18008c292  mov     r13d, [rsp+2A8h+arg_20]
0x18008c29a  mov     dword ptr [rsp+2A8h+hMem], r13d
0x18008c29f  mov     [rsp+2A8h+var_268], rdx
0x18008c2a4  mov     rax, [rsp+2A8h+arg_28]
0x18008c2ac  mov     [rsp+2A8h+var_1C8], rax
0x18008c2b4  mov     rax, [rsp+2A8h+arg_30]
0x18008c2bc  mov     [rsp+2A8h+var_1C0], rax
0x18008c2c4  xor     esi, esi
0x18008c2c6  mov     r15d, esi
0x18008c2c9  mov     [rsp+2A8h+var_258], esi
0x18008c2cd  xorps   xmm0, xmm0
0x18008c2d0  movdqu  [rsp+2A8h+var_1A8], xmm0
0x18008c2d9  mov     [rsp+2A8h+var_198], rsi
0x18008c2e1  lea     rcx, [rsp+2A8h+var_250]
0x18008c2e6  call    ??$open@V?$tip_test@V?$merged_data@U_tip_WebAuthNGetPlatformCredentialListTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_WebAuthNGetPlatformCredentialListTest@@U1@@details@tip2@@@0@XZ; tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>>>(void)
0x18008c2eb  nop
0x18008c2ec  mov     rcx, [rsp+2A8h+var_1C8]
0x18008c2f4  test    rcx, rcx
0x18008c2f7  jz      short loc_18008C30B
0x18008c2f9  mov     rax, [rsp+2A8h+var_1C0]
0x18008c301  test    rax, rax
0x18008c304  jz      short loc_18008C30B
0x18008c306  mov     [rcx], esi
0x18008c308  mov     [rax], rsi
0x18008c30b  lea     rcx, [rsp+2A8h+var_138]
0x18008c313  call    ??0?$promise@UWebAuthNCredentialDetailsList@CtapCbor@@@std@@QEAA@XZ; std::promise<CtapCbor::WebAuthNCredentialDetailsList>::promise<CtapCbor::WebAuthNCredentialDetailsList>(void)
0x18008c318  nop
0x18008c319  lea     rdx, [rsp+2A8h+var_148]
0x18008c321  lea     rcx, [rsp+2A8h+var_138]
0x18008c329  call    ?get_future@?$promise@UWebAuthNCredentialDetailsList@CtapCbor@@@std@@QEAA?AV?$future@UWebAuthNCredentialDetailsList@CtapCbor@@@2@XZ; std::promise<CtapCbor::WebAuthNCredentialDetailsList>::get_future(void)
0x18008c32e  nop
0x18008c32f  xorps   xmm0, xmm0
0x18008c332  movups  [rsp+2A8h+var_158], xmm0
0x18008c33a  movdqu  [rsp+2A8h+var_1F0], xmm0
0x18008c343  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies> `wil::Feature<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::GetImpl(void)'::`2'::impl
0x18008c34a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::__private_IsEnabled(void)
0x18008c34f  test    al, al
0x18008c351  jz      loc_18008C3E8
0x18008c357  lea     rdx, [rsp+2A8h+var_1F0]
0x18008c35f  mov     rcx, rdi; hExistingToken
0x18008c362  call    ?CtapUtilsGetDuplicateHandle@@YAJQEAXAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; CtapUtilsGetDuplicateHandle(void * const,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &)
0x18008c367  mov     ebx, eax
0x18008c369  test    eax, eax
0x18008c36b  jns     short loc_18008C3E1
0x18008c36d  mov     rcx, [rsp+2A8h]; this
0x18008c375  mov     r9d, eax; char *
0x18008c378  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18008c37f  mov     edx, 137Bh; void *
0x18008c384  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c389  nop
0x18008c38a  lea     rcx, [rsp+2A8h+var_1F0]
0x18008c392  call    ??1?$shared_ptr@UCredentialInfo@@@std@@QEAA@XZ; std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(void)
0x18008c397  nop
0x18008c398  lea     rcx, [rsp+2A8h+var_158]; this
0x18008c3a0  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x18008c3a5  nop
0x18008c3a6  lea     rcx, [rsp+2A8h+var_148]
0x18008c3ae  call    ??1?$_State_manager@UWebAuthNCredentialDetailsList@CtapCbor@@@std@@QEAA@XZ; std::_State_manager<CtapCbor::WebAuthNCredentialDetailsList>::~_State_manager<CtapCbor::WebAuthNCredentialDetailsList>(void)
0x18008c3b3  nop
0x18008c3b4  lea     rcx, [rsp+2A8h+var_138]
0x18008c3bc  call    ??1?$promise@UWebAuthNCredentialDetailsList@CtapCbor@@@std@@QEAA@XZ; std::promise<CtapCbor::WebAuthNCredentialDetailsList>::~promise<CtapCbor::WebAuthNCredentialDetailsList>(void)
0x18008c3c1  nop
0x18008c3c2  lea     rcx, [rsp+2A8h+var_250]
0x18008c3c7  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNGetPlatformCredentialListTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNGetPlatformCredentialListTest,_tip_WebAuthNGetPlatformCredentialListTest>,wil::err_returncode_policy>(void)
0x18008c3cc  nop
0x18008c3cd  lea     rcx, [rsp+2A8h+var_1A8]
0x18008c3d5  call    ?_Tidy@?$vector@UWebAuthNCredentialDetails@CtapCbor@@V?$allocator@UWebAuthNCredentialDetails@CtapCbor@@@std@@@std@@AEAAXXZ; std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(void)
0x18008c3da  mov     eax, ebx
0x18008c3dc  jmp     loc_18008D503
0x18008c3e1  mov     ebx, [rsp+2A8h+arg_18]
0x18008c3e8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies> `wil::Feature<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::GetImpl(void)'::`2'::impl
0x18008c3ef  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::__private_IsEnabled(void)
0x18008c3f4  test    al, al
0x18008c3f6  jz      short loc_18008C456
0x18008c3f8  mov     rdx, rdi
0x18008c3fb  lea     rcx, [rsp+2A8h+var_270]
0x18008c400  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x18008c405  nop
0x18008c406  lea     r9, aSystemusesligh; "SystemUsesLightTheme"
0x18008c40d  lea     r8, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18008c414  mov     rdx, 0FFFFFFFF80000001h
0x18008c41b  lea     rcx, [rsp+2A8h+var_278]
0x18008c420  call    ??$try_get_value@I@reg@wil@@YA?AV?$optional@I@std@@PEAUHKEY__@@PEBG1@Z; wil::reg::try_get_value<uint>(HKEY__ *,ushort const *,ushort const *)
0x18008c425  cmp     byte ptr [rsp+2A8h+var_278+4], sil
0x18008c42a  jz      short loc_18008C441
0x18008c42c  lea     rcx, [rsp+2A8h+var_278]
0x18008c431  call    ?value@?$optional@I@std@@QEGBAAEBIXZ; std::optional<uint>::value(void)
0x18008c436  cmp     dword ptr [rax], 1
0x18008c439  mov     r15d, 1
0x18008c43f  jz      short loc_18008C447
0x18008c441  mov     r15d, 2
0x18008c447  mov     [rsp+2A8h+var_258], r15d
0x18008c44c  lea     rcx, [rsp+2A8h+var_270]
0x18008c451  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18008c456  lea     rcx, [rsp+2A8h+var_170]
0x18008c45e  call    ??0?$promise@UWebAuthNCredentialDetailsList@CtapCbor@@@std@@QEAA@XZ; std::promise<CtapCbor::WebAuthNCredentialDetailsList>::promise<CtapCbor::WebAuthNCredentialDetailsList>(void)
0x18008c463  nop
0x18008c464  lea     rdx, [rsp+2A8h+var_1B8]
0x18008c46c  lea     rcx, [rsp+2A8h+var_170]
0x18008c474  call    ?get_future@?$promise@UWebAuthNCredentialDetailsList@CtapCbor@@@std@@QEAA?AV?$future@UWebAuthNCredentialDetailsList@CtapCbor@@@2@XZ; std::promise<CtapCbor::WebAuthNCredentialDetailsList>::get_future(void)
0x18008c479  nop
0x18008c47a  xorps   xmm0, xmm0
0x18008c47d  movups  [rsp+2A8h+var_210], xmm0
0x18008c485  mov     [rsp+2A8h+var_218], rsi
0x18008c48d  mov     [rsp+2A8h+var_220], rsi
0x18008c495  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators> `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl(void)'::`2'::impl
0x18008c49c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(void)
0x18008c4a1  test    al, al
0x18008c4a3  jz      loc_18008C8B3
0x18008c4a9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x18008c4b0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x18008c4b5  test    al, al
0x18008c4b7  jz      loc_18008C7CF
0x18008c4bd  test    ebx, ebx
0x18008c4bf  jz      loc_18008C8B3
0x18008c4c5  test    r14d, r14d
0x18008c4c8  jnz     loc_18008C8B3
0x18008c4ce  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsFixTipCrash@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsFixTipCrash@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsFixTipCrash> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsFixTipCrash>::GetImpl(void)'::`2'::impl
0x18008c4d5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsFixTipCrash@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsFixTipCrash>::__private_IsEnabled(void)
0x18008c4da  lea     rdx, [rsp+2A8h+var_270]
0x18008c4df  test    al, al
0x18008c4e1  jz      loc_18008C664
0x18008c4e7  lea     rcx, [rsp+2A8h+var_218]
0x18008c4ef  call    ??C?$tip_test@V?$merged_data@U_tip_GetPluginPasskeyCredentialDetailsTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_GetPluginPasskeyCredentialDetailsTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTest,_tip_GetPluginPasskeyCredentialDetailsTest>>::operator->(void)
0x18008c4f4  test    r12, r12
0x18008c4f7  setz    cl
0x18008c4fa  mov     rax, [rax]
0x18008c4fd  mov     [rax+114h], cl
0x18008c503  lea     rcx, [rsp+2A8h+var_270]
0x18008c508  call    ??1?$test_data_control@V?$merged_data@U_tip_GetPluginPasskeyCredentialDetailsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTest,_tip_GetPluginPasskeyCredentialDetailsTest>>::~test_data_control<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTest,_tip_GetPluginPasskeyCredentialDetailsTest>>(void)
0x18008c50d  lea     rdx, [rsp+2A8h+var_270]
0x18008c512  lea     rcx, [rsp+2A8h+var_218]
0x18008c51a  call    ??C?$tip_test@V?$merged_data@U_tip_GetPluginPasskeyCredentialDetailsTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_GetPluginPasskeyCredentialDetailsTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTest,_tip_GetPluginPasskeyCredentialDetailsTest>>::operator->(void)
0x18008c51f  test    r13d, r13d
0x18008c522  setnz   cl
0x18008c525  mov     rax, [rax]
0x18008c528  mov     [rax+115h], cl
0x18008c52e  lea     rcx, [rsp+2A8h+var_270]
0x18008c533  call    ??1?$test_data_control@V?$merged_data@U_tip_GetPluginPasskeyCredentialDetailsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTest,_tip_GetPluginPasskeyCredentialDetailsTest>>::~test_data_control<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTest,_tip_GetPluginPasskeyCredentialDetailsTest>>(void)
0x18008c538  mov     rax, [rsp+2A8h+var_218]
0x18008c540  test    rax, rax
0x18008c543  jz      short loc_18008C564
0x18008c545  cmp     [rax+0F8h], rsi
0x18008c54c  jnz     short loc_18008C557
0x18008c54e  test    dword ptr [rax+48h], 100h
0x18008c555  jz      short loc_18008C564
0x18008c557  lea     rcx, [rsp+2A8h+var_218]
0x18008c55f  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_GetPluginPasskeyCredentialDetailsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTest,_tip_GetPluginPasskeyCredentialDetailsTest>,wil::err_returncode_policy>::reset(void)
0x18008c564  lea     rcx, [rsp+2A8h+var_218]
0x18008c56c  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_GetPluginPasskeyCredentialDetailsTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_GetPluginPasskeyCredentialDetailsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTest,_tip_GetPluginPasskeyCredentialDetailsTest>>::ensure_data(void)
0x18008c571  mov     rcx, [rax]
0x18008c574  add     rcx, 8
0x18008c578  lea     rdx, [rsp+2A8h+var_180]
0x18008c580  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18008c585  lea     r14, dword_18015030C
0x18008c58c  mov     rdx, r12
0x18008c58f  test    r12, r12
0x18008c592  cmovz   rdx, r14
0x18008c596  lea     rcx, [rsp+2A8h+var_C8]
0x18008c59e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008c5a3  nop
0x18008c5a4  lea     rcx, [rsp+2A8h+var_218]
0x18008c5ac  mov     qword ptr [rsp+2A8h+var_280], rcx
0x18008c5b1  mov     qword ptr [rsp+2A8h+var_288], rax
0x18008c5b6  lea     r9, [rsp+2A8h+var_258]
0x18008c5bb  lea     r8, [rsp+2A8h+var_1F0]
0x18008c5c3  lea     rdx, [rsp+2A8h+var_170]
0x18008c5cb  lea     rcx, [rsp+2A8h+var_A8]
0x18008c5d3  call    _WebAuthNGetPlatformCredentialListServer____46____lambda_2____lambda_2_
0x18008c5d8  nop
0x18008c5d9  mov     rdx, rax
0x18008c5dc  lea     rcx, [rsp+2A8h+var_278]
0x18008c5e1  call    std__make_unique_std__tuple__WebAuthNGetPlatformCredentialListServer____68____lambda_6_____WebAuthNGetPlatformCredentialListServer____68____lambda_6__0_
0x18008c5e6  nop
0x18008c5e7  lea     rax, [rsp+2A8h+var_240]
0x18008c5ec  mov     qword ptr [rsp+2A8h+var_280], rax
0x18008c5f1  mov     [rsp+2A8h+var_288], esi
0x18008c5f5  mov     r9, [rsp+2A8h+var_278]
0x18008c5fa  lea     r8, std__thread___Invoke_std__tuple__WebAuthNGetPlatformCredentialListServer____46____lambda_2____0_
0x18008c601  xor     edx, edx
0x18008c603  xor     ecx, ecx
0x18008c605  call    cs:__imp__o__beginthreadex
0x18008c60b  mov     [rsp+2A8h+var_248], rax
0x18008c610  test    rax, rax
0x18008c613  jz      short loc_18008C654
0x18008c615  mov     [rsp+2A8h+var_278], rsi
0x18008c61a  lea     rcx, [rsp+2A8h+var_278]
0x18008c61f  call    std__unique_ptr_std__tuple__WebAuthNGetPlatformCredentialListServer____46____lambda_2____std__default_delete_std__tuple__WebAuthNGetPlatformCredentialListServer____46____lambda_2__________unique_ptr_std__tuple__WebAuthNGetPlatformCredentialListServer____46____lambda_2____std__default_delete_std__tuple__WebAuthNGetPlatformCredentialListServer____46____lambda_2_______
0x18008c624  lea     rdx, [rsp+2A8h+var_248]
0x18008c629  lea     rcx, [rsp+2A8h+var_210]
0x18008c631  call    ??4thread@std@@QEAAAEAV01@$$QEAV01@@Z; std::thread::operator=(std::thread &&)
0x18008c636  lea     rcx, [rsp+2A8h+var_248]; this
0x18008c63b  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x18008c640  nop
0x18008c641  lea     rcx, [rsp+2A8h+var_A8]
0x18008c649  call    _WebAuthNGetPlatformCredentialListServer____46____lambda_2_____lambda_2_
0x18008c64e  nop
0x18008c64f  jmp     loc_18008C894
0x18008c654  mov     [rsp+2A8h+var_240], esi
0x18008c658  mov     ecx, 6
0x18008c65d  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18008c663  nop
0x18008c664  lea     rcx, [rsp+2A8h+var_220]
0x18008c66c  call    ??C?$tip_test@V?$merged_data@U_tip_GetPluginPasskeyCredentialDetailsTestOld@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_GetPluginPasskeyCredentialDetailsTestOld@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTestOld,_tip_GetPluginPasskeyCredentialDetailsTestOld>>::operator->(void)
0x18008c671  test    r12, r12
0x18008c674  setz    cl
0x18008c677  mov     rax, [rax]
0x18008c67a  mov     [rax+114h], cl
0x18008c680  lea     rcx, [rsp+2A8h+var_270]
0x18008c685  call    ??1?$test_data_control@V?$merged_data@U_tip_GetPluginPasskeyCredentialDetailsTestOld@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTestOld,_tip_GetPluginPasskeyCredentialDetailsTestOld>>::~test_data_control<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTestOld,_tip_GetPluginPasskeyCredentialDetailsTestOld>>(void)
0x18008c68a  lea     rdx, [rsp+2A8h+var_270]
0x18008c68f  lea     rcx, [rsp+2A8h+var_220]
0x18008c697  call    ??C?$tip_test@V?$merged_data@U_tip_GetPluginPasskeyCredentialDetailsTestOld@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_GetPluginPasskeyCredentialDetailsTestOld@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTestOld,_tip_GetPluginPasskeyCredentialDetailsTestOld>>::operator->(void)
0x18008c69c  test    r13d, r13d
0x18008c69f  setnz   cl
0x18008c6a2  mov     rax, [rax]
0x18008c6a5  mov     [rax+115h], cl
0x18008c6ab  lea     rcx, [rsp+2A8h+var_270]
0x18008c6b0  call    ??1?$test_data_control@V?$merged_data@U_tip_GetPluginPasskeyCredentialDetailsTestOld@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTestOld,_tip_GetPluginPasskeyCredentialDetailsTestOld>>::~test_data_control<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTestOld,_tip_GetPluginPasskeyCredentialDetailsTestOld>>(void)
0x18008c6b5  mov     rcx, [rsp+2A8h+var_220]
0x18008c6bd  test    rcx, rcx
0x18008c6c0  jz      short loc_18008C6DC
0x18008c6c2  add     rcx, 8
0x18008c6c6  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x18008c6cb  test    al, al
0x18008c6cd  jz      short loc_18008C6DC
0x18008c6cf  lea     rcx, [rsp+2A8h+var_220]
0x18008c6d7  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_GetPluginPasskeyCredentialDetailsTestOld@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTestOld,_tip_GetPluginPasskeyCredentialDetailsTestOld>,wil::err_returncode_policy>::reset(void)
0x18008c6dc  lea     rcx, [rsp+2A8h+var_220]
0x18008c6e4  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_GetPluginPasskeyCredentialDetailsTestOld@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_GetPluginPasskeyCredentialDetailsTestOld@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_GetPluginPasskeyCredentialDetailsTestOld,_tip_GetPluginPasskeyCredentialDetailsTestOld>>::ensure_data(void)
0x18008c6e9  mov     rcx, [rax]
0x18008c6ec  add     rcx, 8
0x18008c6f0  lea     rdx, [rsp+2A8h+var_180]
0x18008c6f8  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x18008c6fd  lea     r14, dword_18015030C
0x18008c704  mov     rdx, r12
0x18008c707  test    r12, r12
0x18008c70a  cmovz   rdx, r14
0x18008c70e  lea     rcx, [rsp+2A8h+var_C8]
0x18008c716  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008c71b  nop
0x18008c71c  mov     qword ptr [rsp+2A8h+var_288], rax
0x18008c721  lea     r9, [rsp+2A8h+var_258]
0x18008c726  lea     r8, [rsp+2A8h+var_1F0]
0x18008c72e  lea     rdx, [rsp+2A8h+var_170]
0x18008c736  lea     rcx, [rsp+2A8h+Src]
0x18008c73e  call    _WebAuthNGetPlatformCredentialListServer____70____lambda_7____lambda_7_
0x18008c743  nop
0x18008c744  mov     rdx, rax
0x18008c747  lea     rcx, [rsp+2A8h+var_278]
0x18008c74c  call    std__make_unique_std__tuple__WebAuthNGetPlatformCredentialListServer____70____lambda_7_____WebAuthNGetPlatformCredentialListServer____70____lambda_7__0_
0x18008c751  nop
0x18008c752  lea     rax, [rsp+2A8h+var_240]
0x18008c757  mov     qword ptr [rsp+2A8h+var_280], rax
0x18008c75c  mov     [rsp+2A8h+var_288], esi
0x18008c760  mov     r9, [rsp+2A8h+var_278]
0x18008c765  lea     r8, std__thread___Invoke_std__tuple__WebAuthNGetPlatformCredentialListServer____48____lambda_3____0_
0x18008c76c  xor     edx, edx
0x18008c76e  xor     ecx, ecx
0x18008c770  call    cs:__imp__o__beginthreadex
0x18008c776  mov     [rsp+2A8h+var_248], rax
0x18008c77b  test    rax, rax
0x18008c77e  jz      short loc_18008C7BF
0x18008c780  mov     [rsp+2A8h+var_278], rsi
0x18008c785  lea     rcx, [rsp+2A8h+var_278]
0x18008c78a  call    std__unique_ptr_std__tuple__WebAuthNGetPlatformCredentialListServer____53____lambda_4____std__default_delete_std__tuple__WebAuthNGetPlatformCredentialListServer____53____lambda_4__________unique_ptr_std__tuple__WebAuthNGetPlatformCredentialListServer____53____lambda_4____std__default_delete_std__tuple__WebAuthNGetPlatformCredentialListServer____53____lambda_4_______
0x18008c78f  lea     rdx, [rsp+2A8h+var_248]
0x18008c794  lea     rcx, [rsp+2A8h+var_210]
0x18008c79c  call    ??4thread@std@@QEAAAEAV01@$$QEAV01@@Z; std::thread::operator=(std::thread &&)
0x18008c7a1  lea     rcx, [rsp+2A8h+var_248]; this
0x18008c7a6  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x18008c7ab  nop
0x18008c7ac  lea     rcx, [rsp+2A8h+Src]
0x18008c7b4  call    _WebAuthNGetPlatformCredentialListServer____53____lambda_4_____lambda_4_
0x18008c7b9  nop
0x18008c7ba  jmp     loc_18008C894
0x18008c7bf  mov     [rsp+2A8h+var_240], esi
0x18008c7c3  mov     ecx, 6
0x18008c7c8  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18008c7ce  nop
0x18008c7cf  lea     r14, dword_18015030C
0x18008c7d6  test    ebx, ebx
  ... truncated ...
```
