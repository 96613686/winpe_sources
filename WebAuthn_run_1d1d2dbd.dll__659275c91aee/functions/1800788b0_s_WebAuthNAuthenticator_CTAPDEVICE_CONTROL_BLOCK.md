# s_WebAuthNAuthenticator(_CTAPDEVICE_CONTROL_BLOCK *)

- ea: `0x1800788b0`
- end: `0x18007927e`
- name: `?s_WebAuthNAuthenticator@@YAJPEAU_CTAPDEVICE_CONTROL_BLOCK@@@Z`
- size: `2510`
- prototype: `__int64 __fastcall(struct _CTAPDEVICE_CONTROL_BLOCK *)`
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180027884`
- `0x180028268`
- `0x1800328b8`
- `0x180036da4`
- `0x180047464`
- `0x18004f5b4`
- `0x1800537a4`
- `0x180062c84`
- `0x18006568c`
- `0x180066b34`
- `0x180067c90`
- `0x180067e24`
- `0x18006823c`
- `0x18006f30c`
- `0x180074740`
- `0x1800747b8`
- `0x180074830`
- `0x180075db0`
- `0x180075dd8`
- `0x180077f4c`
- `0x1800788b0`
- `0x18007969c`
- `0x1800acd58`
- `0x1800ad46c`
- `0x1800c0f88`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800789d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078a50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078bd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078c06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078eb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078f75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079087`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800790f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800789d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078a50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078bd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078c06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078eb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078f75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079087`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800790f1`
- `ext-ms-win-security-credui-l1-1-0!CredUIPromptForWindowsCredentialsW` at `0x180078b83`
- `ext-ms-win-security-credui-l1-1-0!CredUIPromptForWindowsCredentialsW` at `0x18007903d`
- `ext-ms-win-security-credui-l1-1-0!CredUIPromptForWindowsCredentialsW` at `0x180078b83`
- `ext-ms-win-security-credui-l1-1-0!CredUIPromptForWindowsCredentialsW` at `0x18007903d`

## string_xrefs

- `0x1800789b6`: `onecore\ds\security\fido\webauthn\dll\webauthnweb.cpp`
- `0x180078a2f`: `onecore\ds\security\fido\webauthn\dll\webauthnweb.cpp`
- `0x180078ba7`: `onecore\ds\security\fido\webauthn\dll\webauthnweb.cpp`
- `0x180078e94`: `onecore\ds\security\fido\webauthn\dll\webauthnweb.cpp`
- `0x180078f54`: `onecore\ds\security\fido\webauthn\dll\webauthnweb.cpp`
- `0x180079065`: `onecore\ds\security\fido\webauthn\dll\webauthnweb.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall s_WebAuthNAuthenticator(struct _CTAPDEVICE_CONTROL_BLOCK *a1)
{
  _QWORD *v2; // rcx
  __int64 v3; // rax
  __int64 v4; // rax
  int v5; // eax
  unsigned int v6; // edi
  int v8; // eax
  const char *v9; // rdx
  const char *v10; // rax
  _QWORD *v11; // r9
  const char *v12; // rdx
  const char *v13; // rax
  _QWORD *v14; // r9
  DWORD v15; // edi
  unsigned int v16; // ebx
  void *v17; // rcx
  void *v18; // rcx
  const char *v19; // rdx
  const char *v20; // rax
  __int64 v21; // r9
  const char *v22; // rdx
  const char *v23; // rax
  __int64 v24; // r9
  unsigned int v25; // ebx
  const char *v26; // rdx
  _QWORD *v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  const char *v30; // rdx
  int DebugModeString; // eax
  unsigned int v32; // edi
  void *v33; // rcx
  const char *v34; // rdx
  const char *v35; // rax
  __int64 v36; // r9
  int CredentialCredUiInfo; // eax
  void *v38; // rcx
  const char *v39; // rdx
  const char *v40; // rax
  __int64 v41; // r9
  DWORD v42; // edi
  int v43; // ebx
  void *v44; // rcx
  const char *v45; // rdx
  const char *v46; // rax
  __int64 v47; // r9
  void *v48; // rcx
  const char *v49; // rax
  __int64 v50; // r9
  const char *v51; // rdx
  const char *v52; // rax
  const char *v53; // rax
  ULONG ulInAuthBufferSize; // [rsp+20h] [rbp-188h]
  ULONG ulInAuthBufferSizea; // [rsp+20h] [rbp-188h]
  ULONG ulInAuthBufferSizeb; // [rsp+20h] [rbp-188h]
  unsigned int v57; // [rsp+50h] [rbp-158h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-150h] BYREF
  ULONG pulAuthPackage; // [rsp+60h] [rbp-148h] BYREF
  struct _CREDUI_INFOW *p_pUiInfo; // [rsp+68h] [rbp-140h] BYREF
  ULONG pulOutAuthBufferSize; // [rsp+70h] [rbp-138h] BYREF
  _BYTE v62[8]; // [rsp+78h] [rbp-130h] BYREF
  _BYTE v63[56]; // [rsp+80h] [rbp-128h] BYREF
  __int64 v64; // [rsp+B8h] [rbp-F0h]
  _BYTE *v65; // [rsp+C0h] [rbp-E8h]
  unsigned int *v66; // [rsp+C8h] [rbp-E0h]
  char v67; // [rsp+D0h] [rbp-D8h]
  struct _CREDUI_INFOW pUiInfo; // [rsp+E0h] [rbp-C8h] BYREF
  unsigned __int16 *ppvOutAuthBuffer[2]; // [rsp+170h] [rbp-38h] BYREF
  char v70; // [rsp+180h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v57 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::GetImpl'::`2'::impl) )
  {
    tip2::open_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>>(v63);
    v65 = v63;
    v66 = &v57;
    v67 = 1;
    if ( !a1
      || (v28 = *((_QWORD *)a1 + 39)) == 0
      || (v29 = *(_QWORD *)(v28 + 56)) == 0
      || !*(_DWORD *)(v29 + 136)
      || !*(_QWORD *)(v29 + 144)
      || (v27 = *(_QWORD **)(v29 + 152)) == 0
      || !*v27 )
    {
      *(_OWORD *)ppvOutAuthBuffer = 0;
      v43 = -2146893785;
      v57 = -2146893785;
      if ( Microsoft_Windows_WebAuthNEnableBits < 0 )
      {
        McTemplateU0jsdd_EventWriteTransfer(
          (_DWORD)v27,
          (unsigned int)&EVENT_WEBAUTHN_ERROR,
          (unsigned int)ppvOutAuthBuffer,
          (unsigned int)"s_WebAuthNAuthenticatorParametersCheck",
          39,
          39);
        v43 = v57;
      }
      v53 = tip2::details::reason_string((tip2::details *)"WebAuthNAuthenticatorTest::reason::server_failed", v26);
      if ( v43 < 0 )
        tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(v64 + 8, 2, v53, (unsigned int)v43);
      goto LABEL_77;
    }
    if ( (unsigned int)I_IsDebugModeConfigured() )
    {
      memset_0(&pUiInfo, 0, 0x88u);
      p_pUiInfo = &pUiInfo;
      pulOutAuthBufferSize = -9594;
      pulAuthPackage = 0;
      pv = 0;
      ppvOutAuthBuffer[0] = (unsigned __int16 *)&word_18015030C;
      DebugModeString = GetDebugModeString(ppvOutAuthBuffer);
      v32 = DebugModeString;
      if ( DebugModeString < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x48E,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnweb.cpp",
          (const char *)(unsigned int)DebugModeString,
          ulInAuthBufferSize);
        v33 = pv;
        pv = 0;
        if ( v33 )
          CoTaskMemFree(v33);
        wil::details::unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&void WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&void WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>(&p_pUiInfo);
        v35 = tip2::details::reason_string((tip2::details *)"WebAuthNAuthenticatorTest::reason::server_failed", v34);
        if ( (int)v36 < 0 )
          tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(v64 + 8, 2, v35, v36);
LABEL_47:
        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>(v63);
        return v32;
      }
      CredentialCredUiInfo = I_WebAuthNCtapBuildMakeCredentialCredUiInfo(
                               **(HWND **)(*(_QWORD *)(*((_QWORD *)a1 + 39) + 56LL) + 152LL),
                               0x21u,
                               ppvOutAuthBuffer[0],
                               (struct CREDUI_INFO_INTERNAL *)&pUiInfo);
      v32 = CredentialCredUiInfo;
      if ( CredentialCredUiInfo < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x494,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnweb.cpp",
          (const char *)(unsigned int)CredentialCredUiInfo,
          ulInAuthBufferSize);
        v38 = pv;
        pv = 0;
        if ( v38 )
          CoTaskMemFree(v38);
        wil::details::unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&void WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&void WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>(&p_pUiInfo);
        v40 = tip2::details::reason_string((tip2::details *)"WebAuthNAuthenticatorTest::reason::server_failed", v39);
        if ( (int)v41 < 0 )
          tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(v64 + 8, 2, v40, v41);
        goto LABEL_47;
      }
      ppvOutAuthBuffer[0] = (unsigned __int16 *)&pv;
      ppvOutAuthBuffer[1] = 0;
      v70 = 1;
      v42 = CredUIPromptForWindowsCredentialsW(
              &pUiInfo,
              0,
              &pulOutAuthBufferSize,
              *(LPCVOID *)(*(_QWORD *)(*((_QWORD *)a1 + 39) + 56LL) + 144LL),
              *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 39) + 56LL) + 136LL),
              (LPVOID *)&ppvOutAuthBuffer[1],
              &pulAuthPackage,
              0,
              0x8000210u);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(ppvOutAuthBuffer);
      if ( v42 )
      {
        v43 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x4A1,
                (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnweb.cpp",
                (const char *)v42,
                ulInAuthBufferSizeb);
        v44 = pv;
        pv = 0;
        if ( v44 )
          CoTaskMemFree(v44);
        wil::details::unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&void WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&void WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>(&p_pUiInfo);
        v46 = tip2::details::reason_string((tip2::details *)"WebAuthNAuthenticatorTest::reason::server_failed", v45);
        if ( (int)v47 < 0 )
          tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(v64 + 8, 2, v46, v47);
        goto LABEL_77;
      }
      v48 = pv;
      pv = 0;
      if ( v48 )
        CoTaskMemFree(v48);
      wil::details::unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&void WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&void WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>(&p_pUiInfo);
    }
    if ( **(_BYTE **)(*(_QWORD *)(*((_QWORD *)a1 + 39) + 56LL) + 144LL) == 1 )
    {
      v43 = WebAuthNMakeCredentialScenario(a1);
    }
    else
    {
      if ( **(_BYTE **)(*(_QWORD *)(*((_QWORD *)a1 + 39) + 56LL) + 144LL) != 2 )
      {
        v49 = tip2::details::reason_string((tip2::details *)"WebAuthNAuthenticatorTest::reason::server_failed", v30);
        if ( (int)v50 < 0 )
          tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(v64 + 8, 2, v49, v50);
        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>(v63);
        return 2148073511LL;
      }
      v43 = WebAuthNGetAssertionScenario(a1);
    }
    v57 = v43;
    v52 = tip2::details::reason_string((tip2::details *)"WebAuthNAuthenticatorTest::reason::server_failed", v51);
    if ( v43 < 0 )
      tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(v64 + 8, 2, v52, (unsigned int)v43);
LABEL_77:
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorTest,_tip_WebAuthNAuthenticatorTest>>(v63);
    return (unsigned int)v43;
  }
  if ( a1
    && (v3 = *((_QWORD *)a1 + 39)) != 0
    && (v4 = *(_QWORD *)(v3 + 56)) != 0
    && *(_DWORD *)(v4 + 136)
    && *(_QWORD *)(v4 + 144)
    && (v2 = *(_QWORD **)(v4 + 152)) != 0
    && *v2 )
  {
    if ( (unsigned int)I_IsDebugModeConfigured() )
    {
      memset_0(&pUiInfo, 0, 0x88u);
      p_pUiInfo = &pUiInfo;
      pulAuthPackage = -9594;
      pulOutAuthBufferSize = 0;
      pv = 0;
      ppvOutAuthBuffer[0] = (unsigned __int16 *)&word_18015030C;
      v5 = GetDebugModeString(ppvOutAuthBuffer);
      v6 = v5;
      if ( v5 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x431,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnweb.cpp",
          (const char *)(unsigned int)v5,
          ulInAuthBufferSize);
        pv = 0;
LABEL_12:
        wil::details::unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&void WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&void WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>(&p_pUiInfo);
        return v6;
      }
      v8 = I_WebAuthNCtapBuildMakeCredentialCredUiInfo(
             **(HWND **)(*(_QWORD *)(*((_QWORD *)a1 + 39) + 56LL) + 152LL),
             0x21u,
             ppvOutAuthBuffer[0],
             (struct CREDUI_INFO_INTERNAL *)&pUiInfo);
      v6 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x437,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnweb.cpp",
          (const char *)(unsigned int)v8,
          ulInAuthBufferSize);
        pv = 0;
        goto LABEL_12;
      }
      *(_OWORD *)ppvOutAuthBuffer = *(_OWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 39) + 56LL) + 16LL);
      tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>>(
        v62,
        ppvOutAuthBuffer);
      tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>::operator->(
        v62,
        ppvOutAuthBuffer);
      v10 = tip2::details::reason_string((tip2::details *)"WebAuthNUIPerformanceTest::reason::debug_mode", v9);
      tip2::details::shared_data<1,0,0>::get_or_add_flag_under_lock(*v11 + 8LL, 3, v10);
      tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>(ppvOutAuthBuffer);
      tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>::operator->(
        v62,
        ppvOutAuthBuffer);
      v13 = tip2::details::reason_string((tip2::details *)"WebAuthNUIPerformanceTest::reason::ui_invoked", v12);
      tip2::details::shared_data<1,0,0>::get_or_add_flag_under_lock(*v14 + 8LL, 1, v13);
      tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>(ppvOutAuthBuffer);
      ppvOutAuthBuffer[0] = (unsigned __int16 *)&pv;
      ppvOutAuthBuffer[1] = 0;
      v70 = 1;
      v15 = CredUIPromptForWindowsCredentialsW(
              &pUiInfo,
              0,
              &pulAuthPackage,
              *(LPCVOID *)(*(_QWORD *)(*((_QWORD *)a1 + 39) + 56LL) + 144LL),
              *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 39) + 56LL) + 136LL),
              (LPVOID *)&ppvOutAuthBuffer[1],
              &pulOutAuthBufferSize,
              0,
              0x8000210u);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(ppvOutAuthBuffer);
      if ( v15 )
      {
        v16 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x447,
                (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnweb.cpp",
                (const char *)v15,
                ulInAuthBufferSizea);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>(v62);
        v17 = pv;
        pv = 0;
        if ( v17 )
          CoTaskMemFree(v17);
        wil::details::unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&void WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&void WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>(&p_pUiInfo);
        return v16;
      }
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>(v62);
      v18 = pv;
      pv = 0;
      if ( v18 )
        CoTaskMemFree(v18);
      wil::details::unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&void WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&void WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>(&p_pUiInfo);
    }
    if ( **(_BYTE **)(*(_QWORD *)(*((_QWORD *)a1 + 39) + 56LL) + 144LL) == 1 )
    {
      tip2::open_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNAuthenticatorMakeCredentialTest,_tip_WebAuthNAuthenticatorMakeCredentialTest>>>(v63);
      ppvOutAuthBuffer[0] = (unsigned __int16 *)v63;
      ppvOutAuthBuffer[1] = (unsigned __int16 *)&v57;
      v70 = 1;
      v57 = WebAuthNMakeCredentialScenario(a1);
      v23 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNAuthenticatorMakeCredentialTest::reason::server_failed",
              v22);
      if ( (int)v24 < 0 )
        tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(v64 + 8, 2, v23, v24);
    }
    else
    {
      if ( **(_BYTE **)(*(_QWORD *)(*((_QWORD *)a1 + 39) + 56LL) + 144LL) != 2 )
        return 2148073511LL;
      tip2::open_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNAuthenticatorGetAssertionTest,_tip_WebAuthNAuthenticatorGetAssertionTest>>>(v63);
      ppvOutAuthBuffer[0] = (unsigned __int16 *)v63;
      ppvOutAuthBuffer[1] = (unsigned __int16 *)&v57;
      v70 = 1;
      v57 = WebAuthNGetAssertionScenario(a1);
      v20 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNAuthenticatorGetAssertionTest::reason::server_failed",
              v19);
      if ( (int)v21 < 0 )
        tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(v64 + 8, 2, v20, v21);
    }
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorMakeCredentialTest,_tip_WebAuthNAuthenticatorMakeCredentialTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorMakeCredentialTest,_tip_WebAuthNAuthenticatorMakeCredentialTest>>(v63);
    return v57;
  }
  else
  {
    *(_OWORD *)ppvOutAuthBuffer = 0;
    v25 = -2146893785;
    v57 = -2146893785;
    if ( Microsoft_Windows_WebAuthNEnableBits < 0 )
    {
      McTemplateU0jsdd_EventWriteTransfer(
        (_DWORD)v2,
        (unsigned int)&EVENT_WEBAUTHN_ERROR,
        (unsigned int)ppvOutAuthBuffer,
        (unsigned int)"s_WebAuthNAuthenticatorParametersCheck",
        39,
        39);
      return v57;
    }
    return v25;
  }
}

```

## disassembly

```asm
0x1800788b0  mov     [rsp+arg_8], rbx
0x1800788b5  mov     [rsp+arg_10], rsi
0x1800788ba  push    rdi
0x1800788bb  sub     rsp, 1A0h
0x1800788c2  mov     rax, cs:__security_cookie
0x1800788c9  xor     rax, rsp
0x1800788cc  mov     [rsp+1A8h+var_18], rax
0x1800788d4  mov     rbx, rcx
0x1800788d7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies> `wil::Feature<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::GetImpl(void)'::`2'::impl
0x1800788de  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::__private_IsEnabled(void)
0x1800788e3  xor     esi, esi
0x1800788e5  mov     [rsp+1A8h+var_158], esi
0x1800788e9  test    al, al
0x1800788eb  jz      loc_180078D98
0x1800788f1  test    rbx, rbx
0x1800788f4  jz      loc_180078D4D
0x1800788fa  mov     rax, [rbx+138h]
0x180078901  test    rax, rax
0x180078904  jz      loc_180078D4D
0x18007890a  mov     rax, [rax+38h]
0x18007890e  test    rax, rax
0x180078911  jz      loc_180078D4D
0x180078917  cmp     [rax+88h], esi
0x18007891d  jz      loc_180078D4D
0x180078923  cmp     [rax+90h], rsi
0x18007892a  jz      loc_180078D4D
0x180078930  mov     rcx, [rax+98h]
0x180078937  test    rcx, rcx
0x18007893a  jz      loc_180078D4D
0x180078940  cmp     [rcx], rsi
0x180078943  jz      loc_180078D4D
0x180078949  call    ?I_IsDebugModeConfigured@@YAHXZ; I_IsDebugModeConfigured(void)
0x18007894e  test    eax, eax
0x180078950  jz      loc_180078C17
0x180078956  xor     edx, edx; Val
0x180078958  mov     r8d, 88h; Size
0x18007895e  lea     rcx, [rsp+1A8h+pUiInfo]; void *
0x180078966  call    memset_0
0x18007896b  lea     rax, [rsp+1A8h+pUiInfo]
0x180078973  mov     [rsp+1A8h+var_140], rax
0x180078978  mov     [rsp+1A8h+pulAuthPackage], 0FFFFDA86h
0x180078980  mov     [rsp+1A8h+var_138], esi
0x180078984  mov     [rsp+1A8h+pv], rsi
0x180078989  lea     rax, word_18015030C
0x180078990  mov     [rsp+1A8h+var_38], rax
0x180078998  lea     rcx, [rsp+1A8h+var_38]
0x1800789a0  call    _GetDebugModeString
0x1800789a5  mov     edi, eax
0x1800789a7  test    eax, eax
0x1800789a9  jns     short loc_1800789EF
0x1800789ab  mov     rcx, [rsp+1A8h]; this
0x1800789b3  mov     r9d, eax; char *
0x1800789b6  lea     r8, aOnecoreDsSecur_41; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800789bd  mov     edx, 431h; void *
0x1800789c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800789c7  nop
0x1800789c8  mov     rcx, [rsp+1A8h+pv]; pv
0x1800789cd  mov     [rsp+1A8h+pv], rsi
0x1800789d2  test    rcx, rcx
0x1800789d5  jz      short loc_1800789DE
0x1800789d7  call    cs:__imp_CoTaskMemFree
0x1800789dd  nop
0x1800789de  lea     rcx, [rsp+1A8h+var_140]
0x1800789e3  call    ??1?$unique_storage@U?$resource_policy@PEAUCREDUI_INFO_INTERNAL@@P6AXPEAU1@@Z$1?WebAuthNFreeCredUiInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>(void)
0x1800789e8  mov     eax, edi
0x1800789ea  jmp     loc_180079258
0x1800789ef  mov     rax, [rbx+138h]
0x1800789f6  mov     rcx, [rax+38h]
0x1800789fa  mov     rcx, [rcx+98h]
0x180078a01  lea     r9, [rsp+1A8h+pUiInfo]; struct CREDUI_INFO_INTERNAL *
0x180078a09  mov     r8, [rsp+1A8h+var_38]; unsigned __int16 *
0x180078a11  mov     edx, 21h ; '!'; unsigned int
0x180078a16  mov     rcx, [rcx]; HWND
0x180078a19  call    ?I_WebAuthNCtapBuildMakeCredentialCredUiInfo@@YAJPEAUHWND__@@KPEBGPEAUCREDUI_INFO_INTERNAL@@@Z; I_WebAuthNCtapBuildMakeCredentialCredUiInfo(HWND__ *,ulong,ushort const *,CREDUI_INFO_INTERNAL *)
0x180078a1e  mov     edi, eax
0x180078a20  test    eax, eax
0x180078a22  jns     short loc_180078A68
0x180078a24  mov     rcx, [rsp+1A8h]; this
0x180078a2c  mov     r9d, eax; char *
0x180078a2f  lea     r8, aOnecoreDsSecur_41; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180078a36  mov     edx, 437h; void *
0x180078a3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078a40  nop
0x180078a41  mov     rcx, [rsp+1A8h+pv]; pv
0x180078a46  mov     [rsp+1A8h+pv], rsi
0x180078a4b  test    rcx, rcx
0x180078a4e  jz      short loc_180078A57
0x180078a50  call    cs:__imp_CoTaskMemFree
0x180078a56  nop
0x180078a57  lea     rcx, [rsp+1A8h+var_140]
0x180078a5c  call    ??1?$unique_storage@U?$resource_policy@PEAUCREDUI_INFO_INTERNAL@@P6AXPEAU1@@Z$1?WebAuthNFreeCredUiInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>(void)
0x180078a61  mov     eax, edi
0x180078a63  jmp     loc_180079258
0x180078a68  mov     rax, [rbx+138h]
0x180078a6f  mov     rcx, [rax+38h]
0x180078a73  movups  xmm0, xmmword ptr [rcx+10h]
0x180078a77  movdqu  xmmword ptr [rsp+1A8h+var_38], xmm0
0x180078a80  lea     rdx, [rsp+1A8h+var_38]
0x180078a88  lea     rcx, [rsp+1A8h+var_130]
0x180078a8d  call    ??$open@V?$tip_test@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@@0@U_GUID@@@Z; tip2::open<tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>>(_GUID)
0x180078a92  lea     rdx, [rsp+1A8h+var_38]
0x180078a9a  lea     rcx, [rsp+1A8h+var_130]
0x180078a9f  call    ??C?$tip_test@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>::operator->(void)
0x180078aa4  mov     r9, rax
0x180078aa7  lea     rcx, aWebauthnuiperf_0; "WebAuthNUIPerformanceTest::reason::debu"...
0x180078aae  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180078ab3  mov     r8, rax
0x180078ab6  mov     edx, 3
0x180078abb  mov     rcx, [r9]
0x180078abe  add     rcx, 8
0x180078ac2  call    ?get_or_add_flag_under_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEAUtest_flag@3@GPEBD@Z; tip2::details::shared_data<1,0,0>::get_or_add_flag_under_lock(ushort,char const *)
0x180078ac7  lea     rcx, [rsp+1A8h+var_38]
0x180078acf  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>(void)
0x180078ad4  lea     rdx, [rsp+1A8h+var_38]
0x180078adc  lea     rcx, [rsp+1A8h+var_130]
0x180078ae1  call    ??C?$tip_test@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>::operator->(void)
0x180078ae6  mov     r9, rax
0x180078ae9  lea     rcx, aWebauthnuiperf; "WebAuthNUIPerformanceTest::reason::ui_i"...
0x180078af0  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180078af5  mov     r8, rax
0x180078af8  mov     edx, 1
0x180078afd  mov     rcx, [r9]
0x180078b00  add     rcx, 8
0x180078b04  call    ?get_or_add_flag_under_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEAUtest_flag@3@GPEBD@Z; tip2::details::shared_data<1,0,0>::get_or_add_flag_under_lock(ushort,char const *)
0x180078b09  lea     rcx, [rsp+1A8h+var_38]
0x180078b11  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>>(void)
0x180078b16  lea     rax, [rsp+1A8h+pv]
0x180078b1b  mov     [rsp+1A8h+var_38], rax
0x180078b23  mov     [rsp+1A8h+var_38+8], rsi
0x180078b2b  mov     [rsp+1A8h+var_28], 1
0x180078b33  mov     rax, [rbx+138h]
0x180078b3a  mov     r9, [rax+38h]
0x180078b3e  mov     [rsp+1A8h+dwFlags], 8000210h; dwFlags
0x180078b46  mov     [rsp+1A8h+pfSave], rsi; pfSave
0x180078b4b  lea     rax, [rsp+1A8h+var_138]
0x180078b50  mov     [rsp+1A8h+pulOutAuthBufferSize], rax; pulOutAuthBufferSize
0x180078b55  lea     rax, [rsp+1A8h+var_38+8]
0x180078b5d  mov     [rsp+1A8h+ppvOutAuthBuffer], rax; ppvOutAuthBuffer
0x180078b62  mov     eax, [r9+88h]
0x180078b69  mov     [rsp+1A8h+ulInAuthBufferSize], eax; unsigned int
0x180078b6d  mov     r9, [r9+90h]; pvInAuthBuffer
0x180078b74  lea     r8, [rsp+1A8h+pulAuthPackage]; pulAuthPackage
0x180078b79  xor     edx, edx; dwAuthError
0x180078b7b  lea     rcx, [rsp+1A8h+pUiInfo]; pUiInfo
0x180078b83  call    cs:__imp_CredUIPromptForWindowsCredentialsW
0x180078b89  mov     edi, eax
0x180078b8b  lea     rcx, [rsp+1A8h+var_38]
0x180078b93  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180078b98  test    edi, edi
0x180078b9a  jz      short loc_180078BEC
0x180078b9c  mov     rcx, [rsp+1A8h]; this
0x180078ba4  mov     r9d, edi; char *
0x180078ba7  lea     r8, aOnecoreDsSecur_41; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180078bae  mov     edx, 447h; void *
0x180078bb3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180078bb8  mov     ebx, eax
0x180078bba  lea     rcx, [rsp+1A8h+var_130]
0x180078bbf  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>(void)
0x180078bc4  nop
0x180078bc5  mov     rcx, [rsp+1A8h+pv]; pv
0x180078bca  mov     [rsp+1A8h+pv], rsi
0x180078bcf  test    rcx, rcx
0x180078bd2  jz      short loc_180078BDB
0x180078bd4  call    cs:__imp_CoTaskMemFree
0x180078bda  nop
0x180078bdb  lea     rcx, [rsp+1A8h+var_140]
0x180078be0  call    ??1?$unique_storage@U?$resource_policy@PEAUCREDUI_INFO_INTERNAL@@P6AXPEAU1@@Z$1?WebAuthNFreeCredUiInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>(void)
0x180078be5  mov     eax, ebx
0x180078be7  jmp     loc_180079258
0x180078bec  lea     rcx, [rsp+1A8h+var_130]
0x180078bf1  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNUIPerformanceTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNUIPerformanceTest,_tip_WebAuthNUIPerformanceTest>,wil::err_returncode_policy>(void)
0x180078bf6  nop
0x180078bf7  mov     rcx, [rsp+1A8h+pv]; pv
0x180078bfc  mov     [rsp+1A8h+pv], rsi
0x180078c01  test    rcx, rcx
0x180078c04  jz      short loc_180078C0D
0x180078c06  call    cs:__imp_CoTaskMemFree
0x180078c0c  nop
0x180078c0d  lea     rcx, [rsp+1A8h+var_140]
0x180078c12  call    ??1?$unique_storage@U?$resource_policy@PEAUCREDUI_INFO_INTERNAL@@P6AXPEAU1@@Z$1?WebAuthNFreeCredUiInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<CREDUI_INFO_INTERNAL *,void (*)(CREDUI_INFO_INTERNAL *),&WebAuthNFreeCredUiInfo(CREDUI_INFO_INTERNAL *),wistd::integral_constant<unsigned __int64,0>,CREDUI_INFO_INTERNAL *,CREDUI_INFO_INTERNAL *,0,std::nullptr_t>>(void)
0x180078c17  mov     rax, [rbx+138h]
0x180078c1e  mov     rcx, [rax+38h]
0x180078c22  mov     rax, [rcx+90h]
0x180078c29  movzx   ecx, byte ptr [rax]
0x180078c2c  sub     ecx, 1
0x180078c2f  jz      loc_180078CC5
0x180078c35  cmp     ecx, 1
0x180078c38  jz      short loc_180078C44
0x180078c3a  mov     eax, 80090027h
0x180078c3f  jmp     loc_180079258
0x180078c44  lea     rcx, [rsp+1A8h+var_128]
0x180078c4c  call    ??$open_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_WebAuthNAuthenticatorGetAssertionTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180078c51  nop
0x180078c52  lea     rax, [rsp+1A8h+var_128]
0x180078c5a  mov     [rsp+1A8h+var_38], rax
0x180078c62  lea     rax, [rsp+1A8h+var_158]
0x180078c67  mov     [rsp+1A8h+var_38+8], rax
0x180078c6f  mov     [rsp+1A8h+var_28], 1
0x180078c77  mov     rcx, rbx; struct _CTAPDEVICE_CONTROL_BLOCK *
0x180078c7a  call    ?WebAuthNGetAssertionScenario@@YAJPEAU_CTAPDEVICE_CONTROL_BLOCK@@@Z; WebAuthNGetAssertionScenario(_CTAPDEVICE_CONTROL_BLOCK *)
0x180078c7f  mov     r9d, eax
0x180078c82  mov     [rsp+1A8h+var_158], eax
0x180078c86  lea     rcx, aWebauthnauthen_22; "WebAuthNAuthenticatorGetAssertionTest::"...
0x180078c8d  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180078c92  mov     ecx, r9d
0x180078c95  shr     ecx, 1Fh
0x180078c98  test    cl, cl
0x180078c9a  jz      short loc_180078CB6
0x180078c9c  mov     edx, 2
0x180078ca1  mov     rcx, [rsp+1A8h+var_F0]
0x180078ca9  add     rcx, 8
0x180078cad  mov     r8, rax
0x180078cb0  call    ??$set_flag_value_without_lock@J@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBDJ@Z; tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(ushort,char const *,long)
0x180078cb5  nop
0x180078cb6  lea     rcx, [rsp+1A8h+var_128]
0x180078cbe  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNAuthenticatorMakeCredentialTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorMakeCredentialTest,_tip_WebAuthNAuthenticatorMakeCredentialTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorMakeCredentialTest,_tip_WebAuthNAuthenticatorMakeCredentialTest>>(void)
0x180078cc3  jmp     short loc_180078D44
0x180078cc5  lea     rcx, [rsp+1A8h+var_128]
0x180078ccd  call    ??$open_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_WebAuthNAuthenticatorMakeCredentialTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180078cd2  nop
0x180078cd3  lea     rax, [rsp+1A8h+var_128]
0x180078cdb  mov     [rsp+1A8h+var_38], rax
0x180078ce3  lea     rax, [rsp+1A8h+var_158]
0x180078ce8  mov     [rsp+1A8h+var_38+8], rax
0x180078cf0  mov     [rsp+1A8h+var_28], 1
0x180078cf8  mov     rcx, rbx; struct _CTAPDEVICE_CONTROL_BLOCK *
0x180078cfb  call    ?WebAuthNMakeCredentialScenario@@YAJPEAU_CTAPDEVICE_CONTROL_BLOCK@@@Z; WebAuthNMakeCredentialScenario(_CTAPDEVICE_CONTROL_BLOCK *)
0x180078d00  mov     r9d, eax
0x180078d03  mov     [rsp+1A8h+var_158], eax
0x180078d07  lea     rcx, aWebauthnauthen_17; "WebAuthNAuthenticatorMakeCredentialTest"...
0x180078d0e  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180078d13  mov     ecx, r9d
0x180078d16  shr     ecx, 1Fh
0x180078d19  test    cl, cl
0x180078d1b  jz      short loc_180078D37
0x180078d1d  mov     edx, 2
0x180078d22  mov     rcx, [rsp+1A8h+var_F0]
0x180078d2a  add     rcx, 8
0x180078d2e  mov     r8, rax
0x180078d31  call    ??$set_flag_value_without_lock@J@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBDJ@Z; tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(ushort,char const *,long)
0x180078d36  nop
0x180078d37  lea     rcx, [rsp+1A8h+var_128]
0x180078d3f  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNAuthenticatorMakeCredentialTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorMakeCredentialTest,_tip_WebAuthNAuthenticatorMakeCredentialTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNAuthenticatorMakeCredentialTest,_tip_WebAuthNAuthenticatorMakeCredentialTest>>(void)
0x180078d44  mov     eax, [rsp+1A8h+var_158]
0x180078d48  jmp     loc_180079258
0x180078d4d  xorps   xmm0, xmm0
0x180078d50  movups  xmmword ptr [rsp+1A8h+var_38], xmm0
0x180078d58  mov     ebx, 80090027h
0x180078d5d  mov     [rsp+1A8h+var_158], ebx
0x180078d61  cmp     cs:Microsoft_Windows_WebAuthNEnableBits, sil
0x180078d68  jge     short loc_180078D91
0x180078d6a  mov     dword ptr [rsp+1A8h+ppvOutAuthBuffer], ebx
0x180078d6e  mov     [rsp+1A8h+ulInAuthBufferSize], ebx
0x180078d72  lea     r9, aSWebauthnauthe_1; "s_WebAuthNAuthenticatorParametersCheck"
0x180078d79  lea     r8, [rsp+1A8h+var_38]
0x180078d81  lea     rdx, EVENT_WEBAUTHN_ERROR
0x180078d88  call    McTemplateU0jsdd_EventWriteTransfer
0x180078d8d  mov     ebx, [rsp+1A8h+var_158]
0x180078d91  mov     eax, ebx
0x180078d93  jmp     loc_180079258
0x180078d98  lea     rcx, [rsp+1A8h+var_128]
0x180078da0  call    ??$open_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_WebAuthNAuthenticatorTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180078da5  nop
0x180078da6  lea     rax, [rsp+1A8h+var_128]
0x180078dae  mov     [rsp+1A8h+var_E8], rax
0x180078db6  lea     rax, [rsp+1A8h+var_158]
0x180078dbb  mov     [rsp+1A8h+var_E0], rax
0x180078dc3  mov     [rsp+1A8h+var_D8], 1
0x180078dcb  test    rbx, rbx
0x180078dce  jz      loc_1800791CD
0x180078dd4  mov     rax, [rbx+138h]
0x180078ddb  test    rax, rax
0x180078dde  jz      loc_1800791CD
0x180078de4  mov     rax, [rax+38h]
0x180078de8  test    rax, rax
0x180078deb  jz      loc_1800791CD
0x180078df1  cmp     [rax+88h], esi
0x180078df7  jz      loc_1800791CD
0x180078dfd  cmp     [rax+90h], rsi
0x180078e04  jz      loc_1800791CD
0x180078e0a  mov     rcx, [rax+98h]
0x180078e11  test    rcx, rcx
0x180078e14  jz      loc_1800791CD
0x180078e1a  cmp     [rcx], rsi
0x180078e1d  jz      loc_1800791CD
0x180078e23  call    ?I_IsDebugModeConfigured@@YAHXZ; I_IsDebugModeConfigured(void)
0x180078e28  test    eax, eax
0x180078e2a  jz      loc_180079102
0x180078e30  xor     edx, edx; Val
0x180078e32  mov     r8d, 88h; Size
0x180078e38  lea     rcx, [rsp+1A8h+pUiInfo]; void *
0x180078e40  call    memset_0
0x180078e45  lea     rax, [rsp+1A8h+pUiInfo]
0x180078e4d  mov     [rsp+1A8h+var_140], rax
0x180078e52  mov     [rsp+1A8h+var_138], 0FFFFDA86h
0x180078e5a  mov     [rsp+1A8h+pulAuthPackage], esi
0x180078e5e  mov     [rsp+1A8h+pv], rsi
0x180078e63  lea     rax, word_18015030C
0x180078e6a  mov     [rsp+1A8h+var_38], rax
0x180078e72  lea     rcx, [rsp+1A8h+var_38]
  ... truncated ...
```
