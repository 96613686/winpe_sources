# CtapPluginRemoveAuthenticatorCredentials

- ea: `0x180117bbc`
- end: `0x180118b0d`
- name: `CtapPluginRemoveAuthenticatorCredentials`
- size: `3921`
- prototype: ``
- caller_count: `1`
- callee_count: `43`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800db610`

## callees

- `0x180007f90`
- `0x18001cd78`
- `0x18001df88`
- `0x180021878`
- `0x18003164c`
- `0x1800328b8`
- `0x1800350b4`
- `0x180036da4`
- `0x180037f6c`
- `0x18003988c`
- `0x1800398d8`
- `0x18003a3c0`
- `0x18003a9e8`
- `0x180041350`
- `0x18004349c`
- `0x180043f2c`
- `0x1800467e0`
- `0x180048b70`
- `0x18004ae04`
- `0x18004f5b4`
- `0x18004f5d0`
- `0x180062fcc`
- `0x18006f30c`
- `0x180072974`
- `0x180081454`
- `0x180093428`
- `0x1800b265c`
- `0x1800b2950`
- `0x1800b2e68`
- `0x1800b3014`
- `0x1800d2d14`
- `0x1800d3914`
- `0x18010b444`
- `0x18010bdbc`
- `0x18010bf78`
- `0x18010c8d0`
- `0x18010d430`
- `0x18010dd30`
- `0x18010ea60`
- `0x180117bbc`
- `0x18011c42c`
- `0x180121b94`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180117dae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180117dae`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180118787`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180118787`

## string_xrefs

- `0x180117c69`: `WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::invalid_parameters`
- `0x180117ffa`: `WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::invalid_parameters`
- `0x180117caf`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180117d3f`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180117e12`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180117ed6`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180117f97`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18011809e`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180118230`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180118407`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180118507`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180118606`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801186cd`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801187a0`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801188eb`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801189a0`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180118a74`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180118ac5`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801183c8`: `WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::encoding_failed`
- `0x1801184c8`: `WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::encoding_failed`
- `0x180118968`: `WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::credential_list_empty`
- `0x180117cff`: `WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::plugin_authenticators_reg_key_not_found`
- `0x180117f5c`: `WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::decoding_failed`
- `0x1801181f1`: `WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::decoding_failed`
- `0x18011805e`: `WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::name_not_found`
- `0x180117dbe`: `WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::clsid_not_found`
- `0x180117e96`: `WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::package_verification_failed`
- `0x1801185d1`: `WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::credential_id_not_found`
- `0x180118751`: `WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::credentials_removed`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall CtapPluginRemoveAuthenticatorCredentials(
        HANDLE token,
        _OWORD *a2,
        const WCHAR *a3,
        __int64 a4,
        int a5)
{
  const char *v8; // rdx
  __int64 v9; // rax
  int v10; // edi
  const char *v11; // rax
  char v12; // r8
  const char *v14; // rdx
  int UserPluginAuthenticatorsRegKey; // ebx
  const char *v16; // rax
  HKEY *v17; // rax
  const char *v18; // rdx
  int ShouldAllowPluginOperation; // ebx
  HKEY v20; // r8
  const char *v21; // rax
  bool v22; // sf
  const char *v23; // rdx
  const char *v24; // rax
  const char *v25; // rdx
  unsigned int v26; // ebx
  const char *v27; // rax
  unsigned int v28; // eax
  unsigned int v29; // ebx
  __int64 v30; // rbx
  const char *v31; // rdx
  const char *v32; // rax
  char v33; // r8
  const char *v34; // rdx
  int PluginAuthenticatorName; // edi
  const char *v36; // rax
  const char *v37; // rdx
  int ExistingCredentials; // edi
  const char *v39; // rdx
  unsigned int v40; // edi
  const char *v41; // rax
  unsigned int v42; // eax
  unsigned int v43; // ebx
  __int64 v44; // rdi
  const char *v45; // rdx
  unsigned int i; // esi
  __int64 v47; // rdx
  __int64 v48; // r8
  int v49; // esi
  char *v50; // rbx
  int v51; // r15d
  unsigned int j; // r14d
  const char *v53; // rdx
  unsigned int v54; // ebx
  const char *v55; // rax
  unsigned int v56; // eax
  unsigned int v57; // ebx
  const char *v58; // rdx
  unsigned int v59; // ebx
  const char *v60; // rax
  unsigned int v61; // eax
  unsigned int v62; // ebx
  const char *v63; // rax
  __int64 v64; // rax
  int v65; // eax
  const char *v66; // rdx
  unsigned int v67; // edi
  const char *v68; // rax
  unsigned int v69; // eax
  unsigned int v70; // ebx
  const char *v71; // rax
  char v72; // r8
  int phkResult; // [rsp+20h] [rbp-228h]
  int phkResulta; // [rsp+20h] [rbp-228h]
  unsigned int phkResultb; // [rsp+20h] [rbp-228h]
  unsigned int phkResultc; // [rsp+20h] [rbp-228h]
  HKEY v77; // [rsp+30h] [rbp-218h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-210h] BYREF
  __int64 v79; // [rsp+40h] [rbp-208h] BYREF
  __int64 v80; // [rsp+48h] [rbp-200h] BYREF
  int v81; // [rsp+50h] [rbp-1F8h] BYREF
  int v82; // [rsp+54h] [rbp-1F4h] BYREF
  __int128 v83; // [rsp+58h] [rbp-1F0h] BYREF
  __int64 v84; // [rsp+68h] [rbp-1E0h]
  _BYTE v85[56]; // [rsp+70h] [rbp-1D8h] BYREF
  __int64 v86; // [rsp+A8h] [rbp-1A0h] BYREF
  __int64 v87; // [rsp+B0h] [rbp-198h] BYREF
  char *v88; // [rsp+B8h] [rbp-190h] BYREF
  __int64 v89; // [rsp+C0h] [rbp-188h] BYREF
  _OWORD v90[2]; // [rsp+D0h] [rbp-178h] BYREF
  _BYTE v91[16]; // [rsp+F0h] [rbp-158h] BYREF
  __int64 v92; // [rsp+100h] [rbp-148h]
  _BYTE v93[72]; // [rsp+130h] [rbp-118h] BYREF
  _BYTE v94[32]; // [rsp+178h] [rbp-D0h] BYREF
  _BYTE v95[40]; // [rsp+198h] [rbp-B0h] BYREF
  _BYTE v96[32]; // [rsp+1C0h] [rbp-88h] BYREF
  char v97[32]; // [rsp+1E0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  v79 = 0;
  v90[0] = *a2;
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::open_and_watch_errors(
    &v79,
    v85,
    v90);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>(&v79);
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(
    &v79,
    &v86);
  if ( !a3 )
    goto LABEL_7;
  v9 = -1;
  do
    ++v9;
  while ( a3[v9] );
  if ( v9 && a4 )
    v10 = a5;
  else
LABEL_7:
    v10 = a5;
  v11 = tip2::details::reason_string(
          (tip2::details *)"WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::invalid_parameters",
          v8);
  if ( v12 )
    tip2::details::shared_data<1,0,0>::get_or_add_flag_under_lock(v79 + 8, 2, v11);
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(&v79);
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x900,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)0x80004003LL,
      phkResult);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v85);
    return 2147500035LL;
  }
  if ( !a4 || !v10 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x901,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)0x80070057LL,
      phkResult);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v85);
    return 2147942487LL;
  }
  hKey = 0;
  UserPluginAuthenticatorsRegKey = GetUserPluginAuthenticatorsRegKey(token, &hKey);
  if ( UserPluginAuthenticatorsRegKey < 0 )
  {
    v16 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::plugin_authenticators_reg_key_not_found",
            v14);
    tip2::details::shared_data<1,0,0>::set_flag_without_lock(v86 + 8, 12, v16);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90A,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)(unsigned int)UserPluginAuthenticatorsRegKey,
        phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v85);
    return (unsigned int)UserPluginAuthenticatorsRegKey;
  }
  v77 = 0;
  v17 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v77);
  ShouldAllowPluginOperation = RegOpenKeyExW(hKey, a3, 0, 0xF003Fu, v17);
  if ( ShouldAllowPluginOperation )
  {
    v21 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::clsid_not_found",
            v18);
    if ( ShouldAllowPluginOperation == 2 )
      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v86 + 8, 6, v21);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
    {
      v22 = ShouldAllowPluginOperation < 0;
      if ( ShouldAllowPluginOperation > 0 )
      {
        ShouldAllowPluginOperation = (unsigned __int16)ShouldAllowPluginOperation | 0x80070000;
        v22 = ShouldAllowPluginOperation < 0;
      }
      if ( v22 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x918,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
          (const char *)(unsigned int)ShouldAllowPluginOperation,
          phkResulta);
    }
    else if ( ShouldAllowPluginOperation > 0 )
    {
      ShouldAllowPluginOperation = (unsigned __int16)ShouldAllowPluginOperation | 0x80070000;
    }
LABEL_31:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v77);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v85);
    return (unsigned int)ShouldAllowPluginOperation;
  }
  ShouldAllowPluginOperation = CtapPluginInternal::ShouldAllowPluginOperation(token, v77, v20);
  if ( ShouldAllowPluginOperation < 0 )
  {
    v24 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::package_verification_failed",
            v23);
    tip2::details::shared_data<1,0,0>::set_flag_without_lock(v86 + 8, 5, v24);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x925,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)(unsigned int)ShouldAllowPluginOperation,
        phkResulta);
    goto LABEL_31;
  }
  v80 = 0;
  v26 = CtapCborDecodeCredentialDetailsArray(v10, a4, (unsigned int)&v80, 0, 0);
  if ( v26 )
  {
    v27 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::decoding_failed",
            v25);
    tip2::details::shared_data<1,0,0>::set_flag_without_lock(v86 + 8, 4, v27);
    v28 = CtapCborErrorToWin32Error(v26);
    if ( v28 )
    {
      v29 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x937,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
              (const char *)v28,
              phkResultb);
      wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v80);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v77);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v85);
      return v29;
    }
  }
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(
    &v79,
    &v86);
  v30 = v80;
  v32 = tip2::details::reason_string(
          (tip2::details *)"WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::invalid_parameters",
          v31);
  if ( v33 )
    tip2::details::shared_data<1,0,0>::get_or_add_flag_under_lock(v79 + 8, 2, v32);
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(&v79);
  if ( v30 )
  {
    std::wstring::wstring(v94);
    PluginAuthenticatorName = CtapPluginInternal::GetPluginAuthenticatorName(v77, v94);
    if ( PluginAuthenticatorName >= 0 )
    {
      std::wstring::wstring(v96, v94);
      std::wstring::wstring(v97, a3);
      tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(
        &v79,
        &v86);
      std::wstring::operator=(v79 + 304, v94);
      tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(&v79);
      v83 = 0;
      v84 = 0;
      ExistingCredentials = CtapPluginGetExistingCredentials(token, a3, &v83);
      if ( ExistingCredentials < 0 || (_QWORD)v83 == *((_QWORD *)&v83 + 1) )
      {
        v71 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::credential_list_empty",
                v37);
        if ( v72 )
          tip2::details::shared_data<1,0,0>::set_flag_without_lock(v86 + 8, 8, v71);
        if ( ExistingCredentials >= 0 )
        {
          std::vector<unsigned char>::_Tidy(&v83);
          FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v96);
          std::wstring::_Tidy_deallocate(v94);
          wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v80);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v77);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v85);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x953,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)(unsigned int)ExistingCredentials,
            phkResultb);
          std::vector<unsigned char>::_Tidy(&v83);
          FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v96);
          std::wstring::_Tidy_deallocate(v94);
          wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v80);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v77);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v85);
          return (unsigned int)ExistingCredentials;
        }
      }
      else
      {
        v79 = 0;
        v40 = CtapCborDecodeCredentialDetailsArray(DWORD2(v83) - (int)v83, v83, (unsigned int)&v79, 0, 0);
        if ( v40 )
        {
          v41 = tip2::details::reason_string(
                  (tip2::details *)"WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::decoding_failed",
                  v39);
          tip2::details::shared_data<1,0,0>::set_flag_without_lock(v86 + 8, 4, v41);
          v42 = CtapCborErrorToWin32Error(v40);
          if ( v42 )
          {
            v43 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x960,
                    (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                    (const char *)v42,
                    phkResultc);
            wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v79);
            std::vector<unsigned char>::_Tidy(&v83);
            FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v96);
            std::wstring::_Tidy_deallocate(v94);
            wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v80);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v77);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v85);
            return v43;
          }
        }
        v44 = v79;
        if ( v79 )
        {
          std::unordered_set<std::string>::unordered_set<std::string>(v91);
          for ( i = 0; i < *(_DWORD *)v30; ++i )
          {
            v47 = *(_QWORD *)(*(_QWORD *)(v30 + 8) + 8LL * i);
            v48 = std::string::string(v95, *(_QWORD *)(v47 + 8), *(unsigned int *)(v47 + 4));
            std::_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>::emplace<std::string>(
              v91,
              v90,
              v48);
            std::string::_Tidy_deallocate(v95);
          }
          v49 = 0;
          v81 = 0;
          v50 = 0;
          v88 = 0;
          v51 = 0;
          for ( j = 0; j < *(_DWORD *)v44; ++j )
          {
            v89 = *(_QWORD *)(*(_QWORD *)(v44 + 8) + 8LL * j);
            std::string::string(v95, *(_QWORD *)(v89 + 8), *(unsigned int *)(v89 + 4));
            if ( (unsigned __int8)std::_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>::contains(
                                    v91,
                                    v95) )
            {
              ++v51;
            }
            else
            {
              v82 = 0;
              v87 = 0;
              *(_QWORD *)&v90[0] = 1;
              *((_QWORD *)&v90[0] + 1) = &v89;
              v54 = CtapCborEncodeCredentialDetailsList(v90, &v82, &v87);
              if ( v54 )
              {
                v55 = tip2::details::reason_string(
                        (tip2::details *)"WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::encoding_failed",
                        v53);
                tip2::details::shared_data<1,0,0>::set_flag_without_lock(v86 + 8, 3, v55);
                v56 = CtapCborErrorToWin32Error(v54);
                if ( v56 )
                {
                  v57 = wil::details::in1diag3::Return_Win32(
                          retaddr,
                          (void *)0x986,
                          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                          (const char *)v56,
                          phkResultc);
                  std::string::_Tidy_deallocate(v95);
                  std::_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>::~_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>(v91);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v79);
                  std::vector<unsigned char>::_Tidy(&v83);
                  FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v96);
                  std::wstring::_Tidy_deallocate(v94);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v80);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v77);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                  tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v85);
                  return v57;
                }
              }
              v59 = CtapCborEncodeAppendToArray((unsigned int)&v81, (unsigned int)&v88, v82, v87, 0);
              if ( v59 )
              {
                v60 = tip2::details::reason_string(
                        (tip2::details *)"WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::encoding_failed",
                        v58);
                tip2::details::shared_data<1,0,0>::set_flag_without_lock(v86 + 8, 3, v60);
                v61 = CtapCborErrorToWin32Error(v59);
                if ( v61 )
                {
                  v62 = wil::details::in1diag3::Return_Win32(
                          retaddr,
                          (void *)0x991,
                          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                          (const char *)v61,
                          phkResultc);
                  std::string::_Tidy_deallocate(v95);
                  std::_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>::~_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>(v91);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v79);
                  std::vector<unsigned char>::_Tidy(&v83);
                  FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v96);
                  std::wstring::_Tidy_deallocate(v94);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v80);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v77);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                  tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v85);
                  return v62;
                }
              }
              v49 = v81;
              v50 = v88;
            }
            std::string::_Tidy_deallocate(v95);
          }
          if ( v51 != v92 )
          {
            v63 = tip2::details::reason_string(
                    (tip2::details *)"WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::credential_id_not_found",
                    v45);
            tip2::details::shared_data<1,0,0>::set_flag_without_lock(v86 + 8, 7, v63);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x99D,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
              (const char *)0x80090011LL,
              phkResultc);
            std::_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>::~_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>(v91);
            wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v79);
            std::vector<unsigned char>::_Tidy(&v83);
            FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v96);
            std::wstring::_Tidy_deallocate(v94);
            wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v80);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v77);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v85);
            return 2148073489LL;
          }
          if ( v49 )
          {
            v64 = std::vector<unsigned char>::vector<unsigned char>(v90, v50, &v50[v49]);
            v65 = SetCredentials(token, v77, v64);
            v67 = v65;
            if ( v65 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x9A3,
                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                (const char *)(unsigned int)v65,
                phkResultc);
              std::_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>::~_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>(v91);
              wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v79);
              std::vector<unsigned char>::_Tidy(&v83);
              FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v96);
              std::wstring::_Tidy_deallocate(v94);
              wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v80);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v77);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
              tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v85);
              return v67;
            }
            v68 = tip2::details::reason_string(
                    (tip2::details *)"WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::credentials_removed",
                    v66);
            tip2::details::shared_data<1,0,0>::set_flag_without_lock(v86 + 8, 13, v68);
          }
          else
          {
            v69 = RegDeleteValueW(v77, L"AutofillCredentials");
            if ( v69 )
            {
              v70 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x9A8,
                      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                      (const char *)v69,
                      phkResultc);
              std::_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>::~_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>(v91);
              wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v79);
              std::vector<unsigned char>::_Tidy(&v83);
              FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v96);
              std::wstring::_Tidy_deallocate(v94);
              wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v80);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v77);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
              tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v85);
              return v70;
            }
          }
          FidoFree(v50);
          FidoCredProvHelper::Locations::PluginAuthenticator::PluginAuthenticator(
            (FidoCredProvHelper::Locations::PluginAuthenticator *)v93,
            (const struct FidoCredProvHelper::Locations::PluginAuthenticator *)v96);
          v93[64] = 5;
          CredentialAuthenticatorCache::ClearAuthenticator(token, v93);
          std::_Variant_base<FidoCredProvHelper::Locations::Empty,FidoCredProvHelper::Locations::ThisPc,FidoCredProvHelper::Locations::QrCode,FidoCredProvHelper::Locations::SecurityKey,FidoCredProvHelper::Locations::LinkedDevice,FidoCredProvHelper::Locations::PluginAuthenticator,FidoCredProvHelper::Locations::SyncedAccount>::_Destroy(v93);
          std::_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>::~_Hash<std::_Uset_traits<std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::string>,0>>(v91);
          wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v79);
          std::vector<unsigned char>::_Tidy(&v83);
          FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v96);
          std::wstring::_Tidy_deallocate(v94);
          wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v80);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v77);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v85);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x962,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)0x80004003LL,
            phkResultc);
          wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v79);
          std::vector<unsigned char>::_Tidy(&v83);
          FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v96);
          std::wstring::_Tidy_deallocate(v94);
          wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v80);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v77);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v85);
          return 2147500035LL;
        }
      }
    }
    else
    {
      v36 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::name_not_found",
              v34);
      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v86 + 8, 10, v36);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x944,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
          (const char *)(unsigned int)PluginAuthenticatorName,
          phkResultb);
      std::wstring::_Tidy_deallocate(v94);
      wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v80);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v77);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v85);
      return (unsigned int)PluginAuthenticatorName;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x93B,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)0x80004003LL,
      phkResultb);
    wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v80);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v77);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v85);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180117bbc  push    rbx
0x180117bbe  push    rsi
0x180117bbf  push    rdi
0x180117bc0  push    r12
0x180117bc2  push    r13
0x180117bc4  push    r14
0x180117bc6  push    r15
0x180117bc8  sub     rsp, 210h
0x180117bcf  mov     rax, cs:__security_cookie
0x180117bd6  xor     rax, rsp
0x180117bd9  mov     [rsp+248h+var_48], rax
0x180117be1  mov     r14, r9
0x180117be4  mov     rsi, r8
0x180117be7  mov     r12, rcx
0x180117bea  xor     r13d, r13d
0x180117bed  mov     [rsp+248h+var_208], r13
0x180117bf2  movups  xmm0, xmmword ptr [rdx]
0x180117bf5  movdqu  [rsp+248h+var_178], xmm0
0x180117bfe  lea     r8, [rsp+248h+var_178]
0x180117c06  lea     rdx, [rsp+248h+var_1D8]
0x180117c0b  lea     rcx, [rsp+248h+var_208]
0x180117c10  call    ?open_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@2@U_GUID@@@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::open_and_watch_errors(_GUID)
0x180117c15  lea     rcx, [rsp+248h+var_208]
0x180117c1a  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>(void)
0x180117c1f  nop
0x180117c20  lea     rdx, [rsp+248h+var_1A0]
0x180117c28  lea     rcx, [rsp+248h+var_208]
0x180117c2d  call    ??0?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy> const &)
0x180117c32  test    rsi, rsi
0x180117c35  jz      short loc_180117C5F
0x180117c37  or      rax, 0FFFFFFFFFFFFFFFFh
0x180117c3b  inc     rax
0x180117c3e  cmp     [rsi+rax*2], r13w
0x180117c43  jnz     short loc_180117C3B
0x180117c45  test    rax, rax
0x180117c48  jz      short loc_180117C5F
0x180117c4a  test    r14, r14
0x180117c4d  jz      short loc_180117C5F
0x180117c4f  mov     edi, [rsp+248h+arg_20]
0x180117c56  test    edi, edi
0x180117c58  jz      short loc_180117C66
0x180117c5a  mov     r8b, r13b
0x180117c5d  jmp     short loc_180117C69
0x180117c5f  mov     edi, [rsp+248h+arg_20]
0x180117c66  mov     r8b, 1
0x180117c69  lea     rcx, aWebauthnplugin_135; "WebAuthNPluginAuthenticatorRemoveCreden"...
0x180117c70  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180117c75  test    r8b, r8b
0x180117c78  jz      short loc_180117C90
0x180117c7a  mov     edx, 2
0x180117c7f  mov     rcx, [rsp+248h+var_208]
0x180117c84  add     rcx, 8
0x180117c88  mov     r8, rax
0x180117c8b  call    ?get_or_add_flag_under_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEAUtest_flag@3@GPEBD@Z; tip2::details::shared_data<1,0,0>::get_or_add_flag_under_lock(ushort,char const *)
0x180117c90  lea     rcx, [rsp+248h+var_208]
0x180117c95  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(void)
0x180117c9a  test    rsi, rsi
0x180117c9d  jnz     short loc_180117CD2
0x180117c9f  mov     rcx, [rsp+248h]; this
0x180117ca7  mov     ebx, 80004003h
0x180117cac  mov     r9d, ebx; char *
0x180117caf  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180117cb6  mov     edx, 900h; void *
0x180117cbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117cc0  nop
0x180117cc1  lea     rcx, [rsp+248h+var_1D8]
0x180117cc6  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(void)
0x180117ccb  mov     eax, ebx
0x180117ccd  jmp     loc_180118AE9
0x180117cd2  test    r14, r14
0x180117cd5  jz      loc_180118AB5
0x180117cdb  test    edi, edi
0x180117cdd  jz      loc_180118AB5
0x180117ce3  mov     [rsp+248h+hKey], r13
0x180117ce8  lea     rdx, [rsp+248h+hKey]
0x180117ced  mov     rcx, r12
0x180117cf0  call    GetUserPluginAuthenticatorsRegKey
0x180117cf5  mov     ebx, eax
0x180117cf7  test    eax, eax
0x180117cf9  jns     loc_180117D89
0x180117cff  lea     rcx, aWebauthnplugin_145; "WebAuthNPluginAuthenticatorRemoveCreden"...
0x180117d06  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180117d0b  mov     r8, rax
0x180117d0e  mov     edx, 0Ch
0x180117d13  mov     rcx, [rsp+248h+var_1A0]
0x180117d1b  add     rcx, 8
0x180117d1f  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x180117d24  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x180117d2b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x180117d30  test    al, al
0x180117d32  jz      short loc_180117D6D
0x180117d34  mov     rcx, [rsp+248h]; this
0x180117d3c  mov     r9d, ebx; char *
0x180117d3f  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180117d46  mov     edx, 90Ah; void *
0x180117d4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117d50  nop
0x180117d51  lea     rcx, [rsp+248h+hKey]
0x180117d56  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180117d5b  nop
0x180117d5c  lea     rcx, [rsp+248h+var_1D8]
0x180117d61  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(void)
0x180117d66  mov     eax, ebx
0x180117d68  jmp     loc_180118AE9
0x180117d6d  lea     rcx, [rsp+248h+hKey]
0x180117d72  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180117d77  nop
0x180117d78  lea     rcx, [rsp+248h+var_1D8]
0x180117d7d  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(void)
0x180117d82  mov     eax, ebx
0x180117d84  jmp     loc_180118AE9
0x180117d89  mov     [rsp+248h+var_218], r13
0x180117d8e  lea     rcx, [rsp+248h+var_218]
0x180117d93  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180117d98  mov     qword ptr [rsp+248h+phkResult], rax; int
0x180117d9d  mov     r9d, 0F003Fh; samDesired
0x180117da3  xor     r8d, r8d; ulOptions
0x180117da6  mov     rdx, rsi; lpSubKey
0x180117da9  mov     rcx, [rsp+248h+hKey]; hKey
0x180117dae  call    cs:__imp_RegOpenKeyExW
0x180117db4  mov     ebx, eax
0x180117db6  test    eax, eax
0x180117db8  jz      loc_180117E7F
0x180117dbe  lea     rcx, aWebauthnplugin_29; "WebAuthNPluginAuthenticatorRemoveCreden"...
0x180117dc5  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180117dca  cmp     ebx, 2
0x180117dcd  jnz     short loc_180117DE6
0x180117dcf  lea     edx, [rbx+4]
0x180117dd2  mov     rcx, [rsp+248h+var_1A0]
0x180117dda  add     rcx, 8
0x180117dde  mov     r8, rax
0x180117de1  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x180117de6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x180117ded  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x180117df2  test    al, al
0x180117df4  jz      short loc_180117E4B
0x180117df6  test    ebx, ebx
0x180117df8  jle     short loc_180117E05
0x180117dfa  movzx   ebx, bx
0x180117dfd  or      ebx, 80070000h
0x180117e03  test    ebx, ebx
0x180117e05  jns     short loc_180117E24
0x180117e07  mov     rcx, [rsp+248h]; this
0x180117e0f  mov     r9d, ebx; char *
0x180117e12  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180117e19  mov     edx, 918h; void *
0x180117e1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117e23  nop
0x180117e24  lea     rcx, [rsp+248h+var_218]
0x180117e29  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180117e2e  nop
0x180117e2f  lea     rcx, [rsp+248h+hKey]
0x180117e34  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180117e39  nop
0x180117e3a  lea     rcx, [rsp+248h+var_1D8]
0x180117e3f  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(void)
0x180117e44  mov     eax, ebx
0x180117e46  jmp     loc_180118AE9
0x180117e4b  test    ebx, ebx
0x180117e4d  jle     short loc_180117E58
0x180117e4f  movzx   ebx, bx
0x180117e52  or      ebx, 80070000h
0x180117e58  lea     rcx, [rsp+248h+var_218]
0x180117e5d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180117e62  nop
0x180117e63  lea     rcx, [rsp+248h+hKey]
0x180117e68  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180117e6d  nop
0x180117e6e  lea     rcx, [rsp+248h+var_1D8]
0x180117e73  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(void)
0x180117e78  mov     eax, ebx
0x180117e7a  jmp     loc_180118AE9
0x180117e7f  mov     rdx, [rsp+248h+var_218]; void *
0x180117e84  mov     rcx, r12; token
0x180117e87  call    ?ShouldAllowPluginOperation@CtapPluginInternal@@YAJQEAXQEAUHKEY__@@@Z; CtapPluginInternal::ShouldAllowPluginOperation(void * const,HKEY__ * const)
0x180117e8c  mov     ebx, eax
0x180117e8e  test    eax, eax
0x180117e90  jns     loc_180117F36
0x180117e96  lea     rcx, aWebauthnplugin_41; "WebAuthNPluginAuthenticatorRemoveCreden"...
0x180117e9d  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180117ea2  mov     r8, rax
0x180117ea5  mov     edx, 5
0x180117eaa  mov     rcx, [rsp+248h+var_1A0]
0x180117eb2  add     rcx, 8
0x180117eb6  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x180117ebb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x180117ec2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x180117ec7  test    al, al
0x180117ec9  jz      short loc_180117F0F
0x180117ecb  mov     rcx, [rsp+248h]; this
0x180117ed3  mov     r9d, ebx; char *
0x180117ed6  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180117edd  mov     edx, 925h; void *
0x180117ee2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117ee7  nop
0x180117ee8  lea     rcx, [rsp+248h+var_218]
0x180117eed  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180117ef2  nop
0x180117ef3  lea     rcx, [rsp+248h+hKey]
0x180117ef8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180117efd  nop
0x180117efe  lea     rcx, [rsp+248h+var_1D8]
0x180117f03  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(void)
0x180117f08  mov     eax, ebx
0x180117f0a  jmp     loc_180118AE9
0x180117f0f  lea     rcx, [rsp+248h+var_218]
0x180117f14  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180117f19  nop
0x180117f1a  lea     rcx, [rsp+248h+hKey]
0x180117f1f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180117f24  nop
0x180117f25  lea     rcx, [rsp+248h+var_1D8]
0x180117f2a  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(void)
0x180117f2f  mov     eax, ebx
0x180117f31  jmp     loc_180118AE9
0x180117f36  mov     [rsp+248h+var_200], r13
0x180117f3b  mov     qword ptr [rsp+248h+phkResult], r13; int
0x180117f40  xor     r9d, r9d
0x180117f43  lea     r8, [rsp+248h+var_200]
0x180117f48  mov     rdx, r14
0x180117f4b  mov     ecx, edi
0x180117f4d  call    CtapCborDecodeCredentialDetailsArray
0x180117f52  mov     ebx, eax
0x180117f54  test    eax, eax
0x180117f56  jz      loc_180117FDC
0x180117f5c  lea     rcx, aWebauthnplugin_114; "WebAuthNPluginAuthenticatorRemoveCreden"...
0x180117f63  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180117f68  mov     r8, rax
0x180117f6b  mov     edx, 4
0x180117f70  mov     rcx, [rsp+248h+var_1A0]
0x180117f78  add     rcx, 8
0x180117f7c  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x180117f81  mov     ecx, ebx
0x180117f83  call    CtapCborErrorToWin32Error
0x180117f88  test    eax, eax
0x180117f8a  jz      short loc_180117FDC
0x180117f8c  mov     rcx, [rsp+248h]; this
0x180117f94  mov     r9d, eax; char *
0x180117f97  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180117f9e  mov     edx, 937h; void *
0x180117fa3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180117fa8  mov     ebx, eax
0x180117faa  lea     rcx, [rsp+248h+var_200]
0x180117faf  call    ??1?$unique_storage@U?$resource_policy@PEAEP6AXPEAX@Z$1?FidoFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>(void)
0x180117fb4  nop
0x180117fb5  lea     rcx, [rsp+248h+var_218]
0x180117fba  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180117fbf  nop
0x180117fc0  lea     rcx, [rsp+248h+hKey]
0x180117fc5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180117fca  nop
0x180117fcb  lea     rcx, [rsp+248h+var_1D8]
0x180117fd0  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(void)
0x180117fd5  mov     eax, ebx
0x180117fd7  jmp     loc_180118AE9
0x180117fdc  lea     rdx, [rsp+248h+var_1A0]
0x180117fe4  lea     rcx, [rsp+248h+var_208]
0x180117fe9  call    ??0?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy> const &)
0x180117fee  mov     rbx, [rsp+248h+var_200]
0x180117ff3  test    rbx, rbx
0x180117ff6  setz    r8b
0x180117ffa  lea     rcx, aWebauthnplugin_135; "WebAuthNPluginAuthenticatorRemoveCreden"...
0x180118001  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180118006  test    r8b, r8b
0x180118009  jz      short loc_180118021
0x18011800b  mov     edx, 2
0x180118010  mov     rcx, [rsp+248h+var_208]
0x180118015  add     rcx, 8
0x180118019  mov     r8, rax
0x18011801c  call    ?get_or_add_flag_under_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEAUtest_flag@3@GPEBD@Z; tip2::details::shared_data<1,0,0>::get_or_add_flag_under_lock(ushort,char const *)
0x180118021  lea     rcx, [rsp+248h+var_208]
0x180118026  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(void)
0x18011802b  test    rbx, rbx
0x18011802e  jz      loc_180118A64
0x180118034  lea     rcx, [rsp+248h+var_D0]
0x18011803c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180118041  nop
0x180118042  lea     rdx, [rsp+248h+var_D0]
0x18011804a  mov     rcx, [rsp+248h+var_218]
0x18011804f  call    ?GetPluginAuthenticatorName@CtapPluginInternal@@YAJPEAUHKEY__@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CtapPluginInternal::GetPluginAuthenticatorName(HKEY__ *,std::wstring &)
0x180118054  mov     edi, eax
0x180118056  test    eax, eax
0x180118058  jns     loc_180118130
0x18011805e  lea     rcx, aWebauthnplugin_86; "WebAuthNPluginAuthenticatorRemoveCreden"...
0x180118065  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18011806a  mov     r8, rax
0x18011806d  mov     edx, 0Ah
0x180118072  mov     rcx, [rsp+248h+var_1A0]
0x18011807a  add     rcx, 8
0x18011807e  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x180118083  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x18011808a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x18011808f  test    al, al
0x180118091  jz      short loc_1801180F0
0x180118093  mov     rcx, [rsp+248h]; this
0x18011809b  mov     r9d, edi; char *
0x18011809e  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1801180a5  mov     edx, 944h; void *
0x1801180aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801180af  nop
  ... truncated ...
```
