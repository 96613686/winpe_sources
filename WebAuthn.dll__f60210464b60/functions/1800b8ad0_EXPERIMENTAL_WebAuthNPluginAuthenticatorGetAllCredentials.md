# EXPERIMENTAL_WebAuthNPluginAuthenticatorGetAllCredentials

- ea: `0x1800b8ad0`
- end: `0x1800b9021`
- name: `EXPERIMENTAL_WebAuthNPluginAuthenticatorGetAllCredentials`
- size: `1361`
- prototype: ``
- caller_count: `0`
- callee_count: `33`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c9d0`
- `0x180017a88`
- `0x18001cd78`
- `0x1800288c8`
- `0x1800328b8`
- `0x1800365c0`
- `0x180036da4`
- `0x1800467e0`
- `0x18004685c`
- `0x180049de0`
- `0x18004ae04`
- `0x18004f070`
- `0x18004f548`
- `0x18004f5b4`
- `0x1800537a4`
- `0x180055188`
- `0x18006cfd4`
- `0x18006f7b0`
- `0x180079444`
- `0x18007e064`
- `0x180081454`
- `0x180095468`
- `0x1800b265c`
- `0x1800b2918`
- `0x1800b2e20`
- `0x1800b2fc4`
- `0x1800b4170`
- `0x1800b5064`
- `0x1800b5548`
- `0x1800b79cc`
- `0x1800b7b0c`
- `0x1800b8ad0`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b8edf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b8edf`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x1800b8c0a`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x1800b8c0a`

## string_xrefs

- `0x1800b8b22`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800b8bcf`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800b8d80`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800b8db6`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800b8e31`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800b8f01`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800b8df1`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::credential_list_conversion_failed`
- `0x1800b8ba0`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::remote_session`
- `0x1800b8c1b`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::remote_session`
- `0x1800b8f24`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::generic_failure`
- `0x1800b8fb2`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::generic_failure`
- `0x1800b8f5f`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::credential_list_empty`
- `0x1800b8c45`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::invalid_parameters`
- `0x1800b8d4f`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::decoding_failed`

## pseudocode

```c
__int64 __fastcall EXPERIMENTAL_WebAuthNPluginAuthenticatorGetAllCredentials(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rdx
  unsigned int v6; // ebx
  const char *v8; // rdx
  const char *v9; // rax
  __int64 v10; // rdx
  const char *v11; // rax
  const char *v12; // rax
  __int64 v13; // rax
  __int64 v14; // r8
  int v15; // eax
  __int64 v16; // r9
  __int64 v17; // rdx
  int v18; // ebx
  const char *v19; // rdx
  unsigned int v20; // r14d
  const char *v21; // rax
  unsigned int v22; // eax
  struct _WEBAUTHN_CREDENTIAL_DETAILS_LIST *v23; // rbx
  const char *v24; // rdx
  const char *v25; // rax
  int v26; // eax
  __int64 *v27; // rax
  _DWORD *v28; // rdi
  __int64 v29; // rcx
  int v30; // ebx
  __int64 v31; // rax
  _DWORD *v32; // rax
  const char *v33; // rdx
  const char *v34; // rdx
  const char *v35; // rax
  const char *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rcx
  char v39; // r8
  const char *v40; // rdx
  const char *v41; // rax
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  unsigned int v44; // [rsp+20h] [rbp-E0h]
  __int64 v45; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v46[8]; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-C0h] BYREF
  struct _WEBAUTHN_CREDENTIAL_DETAILS_LIST *v48; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v49[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID v50; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v51[64]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v52[256]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v53; // [rsp+1B0h] [rbp+B0h]
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(
                           `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl,
                           a2,
                           a3) )
  {
    v5 = 1680;
LABEL_3:
    v6 = -2147467263;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80004001LL,
      v42);
    return v6;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    v5 = 1681;
    goto LABEL_3;
  }
  v45 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::start_and_watch_errors(
    &v45,
    v51);
  v46[0] = 0;
  memset_0(v52, 0, 0x238u);
  *(_QWORD *)a2 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    if ( ShouldSendRequestToRemoteSession(0) )
    {
      v9 = tip2::details::reason_string(
             (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::remote_session",
             v8);
      tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
        &v45,
        7,
        v9);
      v10 = 1695;
LABEL_10:
      v6 = -2146893783;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)v6,
        v42);
LABEL_12:
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v51);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>(&v45);
      return v6;
    }
  }
  else if ( (unsigned __int8)IsWinStationIsSessionRemoteablePresent()
         && (unsigned __int8)WinStationIsSessionRemoteable(0, 0xFFFFFFFFLL, v46)
         && v46[0] )
  {
    v11 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::remote_session",
            v8);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      &v45,
      7,
      v11);
    v10 = 1704;
    goto LABEL_10;
  }
  if ( !a1 )
  {
    v12 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::invalid_parameters",
            v8);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      &v45,
      2,
      v12);
    v10 = 1711;
    v6 = -2146893785;
    goto LABEL_11;
  }
  v53 = a1;
  v13 = tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::ensure_data(&v45);
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(
    v49,
    v13);
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(a1 + 2 * v14) );
  std::wstring::_Assign<unsigned short>(v49[0] + 272LL, a1);
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::close(v49);
  LODWORD(v48) = 0;
  lpMem = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(
    &v45,
    &v50);
  v15 = I_EncodeAndSendRpcRequest(
          0x6Eu,
          &v50,
          (struct _CTAPCBOR_RPC_REQUEST *)v52,
          (unsigned int *)&v48,
          (unsigned __int8 **)&lpMem);
  v6 = v15;
  if ( v15 < 0 )
  {
    v16 = (unsigned int)v15;
    v17 = 1729;
LABEL_40:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)v16,
      v43);
    goto LABEL_41;
  }
  v18 = (int)v48;
  if ( !(_DWORD)v48 || !lpMem )
  {
    v32 = LocalAlloc(0x40u, 0x18u);
    *(_QWORD *)a2 = v32;
    if ( !v32 )
    {
      v6 = -2147024882;
      v17 = 1733;
      v16 = 2147942414LL;
      goto LABEL_40;
    }
    v32[2] = 0;
    *(_QWORD *)(*(_QWORD *)a2 + 16LL) = 0;
    v36 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::credential_list_empty",
            v33);
    v38 = v45;
    if ( v39 )
    {
      if ( !v45 )
        goto LABEL_51;
      LOBYTE(v37) = 1;
      tip2::details::shared_data<1,0,0>::complete_without_lock(v45 + 8, v37, 6, v36);
      v38 = v45;
    }
    if ( v38 && (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v38 + 8) )
    {
      v41 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::generic_failure",
              v40);
      tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::set_flag(
        &v45,
        1,
        v41);
      tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v45);
    }
    goto LABEL_51;
  }
  v48 = 0;
  v20 = CtapCborDecodeCredentialDetailsArray(v18, (_DWORD)lpMem, (unsigned int)&v48, 0, 0);
  if ( v20 )
  {
    v21 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::decoding_failed",
            v19);
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::complete_and_fail(
      &v45,
      3,
      v21);
    v22 = CtapCborErrorToWin32Error(v20);
    if ( v22 )
    {
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x6D4,
             (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
             (const char *)v22,
             v44);
LABEL_28:
      wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v48);
LABEL_41:
      if ( v45 )
      {
        if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v45 + 8) )
        {
          v35 = tip2::details::reason_string(
                  (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::generic_failure",
                  v34);
          tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::set_flag(
            &v45,
            1,
            v35);
          tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v45);
        }
      }
      tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v49);
      goto LABEL_12;
    }
  }
  v23 = v48;
  if ( !v48 )
  {
    v6 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6D6,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80004003LL,
      v44);
    goto LABEL_28;
  }
  CtapCltFree(lpMem);
  lpMem = 0;
  if ( (int)ConvertWebAuthNCredentialsListToWebAuthNPluginCredentialsList(
              v23,
              (struct _EXPERIMENTAL_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS_LIST **)&lpMem) < 0 )
  {
    v25 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::credential_list_conversion_failed",
            v24);
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::complete_and_fail(
      &v45,
      9,
      v25);
    v26 = CtapCborErrorToWin32Error(v20);
    v6 = v26;
    if ( v26 > 0 )
      v6 = (unsigned __int16)v26 | 0x80070000;
    if ( (v6 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6DD,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)v6,
        v44);
    wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&lpMem);
    goto LABEL_28;
  }
  v27 = (__int64 *)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                     &v50,
                     a1,
                     -1);
  v28 = lpMem;
  v29 = *v27;
  *v27 = 0;
  *(_QWORD *)v28 = v29;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v50);
  v30 = v28[2];
  v31 = tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::ensure_data(&v45);
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(
    &lpMem,
    v31);
  *((_DWORD *)lpMem + 100) = v30;
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(&lpMem);
  lpMem = 0;
  *(_QWORD *)a2 = v28;
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v45);
  wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&lpMem);
  wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v48);
LABEL_51:
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v49);
  tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v51);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>(&v45);
  return 0;
}

```

## disassembly

```asm
0x1800b8ad0  mov     [rsp-8+arg_10], rbx
0x1800b8ad5  push    rbp
0x1800b8ad6  push    rdi
0x1800b8ad7  push    r12
0x1800b8ad9  push    r14
0x1800b8adb  push    r15
0x1800b8add  lea     rbp, [rsp-200h]
0x1800b8ae5  sub     rsp, 300h
0x1800b8aec  mov     rax, cs:__security_cookie
0x1800b8af3  xor     rax, rsp
0x1800b8af6  mov     [rbp+220h+var_30], rax
0x1800b8afd  mov     r15, rdx
0x1800b8b00  mov     rdi, rcx
0x1800b8b03  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators> `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl(void)'::`2'::impl
0x1800b8b0a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(void)
0x1800b8b0f  xor     r12d, r12d
0x1800b8b12  test    al, al
0x1800b8b14  jnz     short loc_1800B8B3D
0x1800b8b16  mov     edx, 690h; void *
0x1800b8b1b  mov     rcx, [rbp+228h]; this
0x1800b8b22  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800b8b29  mov     ebx, 80004001h
0x1800b8b2e  mov     r9d, ebx; char *
0x1800b8b31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b8b36  mov     eax, ebx
0x1800b8b38  jmp     loc_1800B8FFA
0x1800b8b3d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1800b8b44  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800b8b49  test    al, al
0x1800b8b4b  jz      short loc_1800B8B54
0x1800b8b4d  mov     edx, 691h
0x1800b8b52  jmp     short loc_1800B8B1B
0x1800b8b54  lea     rdx, [rsp+320h+var_2B0]
0x1800b8b59  mov     [rsp+320h+var_2F0], r12
0x1800b8b5e  lea     rcx, [rsp+320h+var_2F0]
0x1800b8b63  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::start_and_watch_errors(void)
0x1800b8b68  xor     edx, edx; Val
0x1800b8b6a  mov     [rsp+320h+var_2E8], r12b
0x1800b8b6f  mov     r8d, 238h; Size
0x1800b8b75  lea     rcx, [rbp+220h+var_270]; void *
0x1800b8b79  call    memset_0
0x1800b8b7e  mov     [r15], r12
0x1800b8b81  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1800b8b88  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800b8b8d  test    al, al
0x1800b8b8f  jz      short loc_1800B8BF7
0x1800b8b91  xor     ecx, ecx; unsigned __int8 *
0x1800b8b93  call    ?ShouldSendRequestToRemoteSession@@YA_NPEAE@Z; ShouldSendRequestToRemoteSession(uchar *)
0x1800b8b98  test    al, al
0x1800b8b9a  jz      loc_1800B8C40
0x1800b8ba0  lea     rcx, aWebauthnplugin_93; "WebAuthNPluginAuthenticatorGetAllCreden"...
0x1800b8ba7  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800b8bac  mov     r8, rax
0x1800b8baf  lea     rcx, [rsp+320h+var_2F0]
0x1800b8bb4  mov     edx, 7
0x1800b8bb9  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800b8bbe  mov     edx, 69Fh; void *
0x1800b8bc3  mov     ebx, 80090029h
0x1800b8bc8  mov     rcx, [rbp+228h]; this
0x1800b8bcf  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800b8bd6  mov     r9d, ebx; char *
0x1800b8bd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b8bde  lea     rcx, [rsp+320h+var_2B0]
0x1800b8be3  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(void)
0x1800b8be8  lea     rcx, [rsp+320h+var_2F0]
0x1800b8bed  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>(void)
0x1800b8bf2  jmp     loc_1800B8B36
0x1800b8bf7  call    IsWinStationIsSessionRemoteablePresent
0x1800b8bfc  test    al, al
0x1800b8bfe  jz      short loc_1800B8C40
0x1800b8c00  lea     r8, [rsp+320h+var_2E8]
0x1800b8c05  or      edx, 0FFFFFFFFh
0x1800b8c08  xor     ecx, ecx
0x1800b8c0a  call    cs:__imp_WinStationIsSessionRemoteable
0x1800b8c10  test    al, al
0x1800b8c12  jz      short loc_1800B8C40
0x1800b8c14  cmp     [rsp+320h+var_2E8], r12b
0x1800b8c19  jz      short loc_1800B8C40
0x1800b8c1b  lea     rcx, aWebauthnplugin_93; "WebAuthNPluginAuthenticatorGetAllCreden"...
0x1800b8c22  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800b8c27  mov     r8, rax
0x1800b8c2a  lea     rcx, [rsp+320h+var_2F0]
0x1800b8c2f  mov     edx, 7
0x1800b8c34  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800b8c39  mov     edx, 6A8h
0x1800b8c3e  jmp     short loc_1800B8BC3
0x1800b8c40  test    rdi, rdi
0x1800b8c43  jnz     short loc_1800B8C70
0x1800b8c45  lea     rcx, aWebauthnplugin_27; "WebAuthNPluginAuthenticatorGetAllCreden"...
0x1800b8c4c  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800b8c51  mov     r8, rax
0x1800b8c54  lea     edx, [rdi+2]
0x1800b8c57  lea     rcx, [rsp+320h+var_2F0]
0x1800b8c5c  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800b8c61  mov     edx, 6AFh
0x1800b8c66  mov     ebx, 80090027h
0x1800b8c6b  jmp     loc_1800B8BC8
0x1800b8c70  lea     rcx, [rsp+320h+var_2F0]
0x1800b8c75  mov     [rbp+220h+var_170], rdi
0x1800b8c7c  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::ensure_data(void)
0x1800b8c81  mov     rdx, rax
0x1800b8c84  lea     rcx, [rsp+320h+var_2D0]
0x1800b8c89  call    ??0?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy> const &)
0x1800b8c8e  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800b8c92  inc     r8
0x1800b8c95  cmp     [rdi+r8*2], r12w
0x1800b8c9a  jnz     short loc_1800B8C92
0x1800b8c9c  mov     rcx, [rsp+320h+var_2D0]
0x1800b8ca1  mov     rdx, rdi
0x1800b8ca4  add     rcx, 110h
0x1800b8cab  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800b8cb0  lea     rcx, [rsp+320h+var_2D0]
0x1800b8cb5  call    ?close@?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::close(void)
0x1800b8cba  lea     rdx, [rsp+320h+var_2C0]
0x1800b8cbf  mov     dword ptr [rsp+320h+var_2D8], r12d
0x1800b8cc4  lea     rcx, [rsp+320h+var_2F0]
0x1800b8cc9  mov     [rsp+320h+lpMem], r12
0x1800b8cce  call    ?test_id@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEBA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(void)
0x1800b8cd3  movaps  xmm1, xmmword ptr [rsp+320h+var_2C0.Data1]
0x1800b8cd8  lea     rax, [rsp+320h+lpMem]
0x1800b8cdd  lea     r9, [rsp+320h+var_2D8]; unsigned int *
0x1800b8ce2  mov     qword ptr [rsp+320h+var_300], rax; int
0x1800b8ce7  lea     r8, [rbp+220h+var_270]; struct _CTAPCBOR_RPC_REQUEST *
0x1800b8ceb  movdqa  xmmword ptr [rsp+320h+var_2C0.Data1], xmm1
0x1800b8cf1  lea     rdx, [rsp+320h+var_2C0]; struct _GUID *
0x1800b8cf6  mov     ecx, 6Eh ; 'n'; unsigned int
0x1800b8cfb  call    ?I_EncodeAndSendRpcRequest@@YAJKU_GUID@@AEAU_CTAPCBOR_RPC_REQUEST@@PEAKPEAPEAE@Z; I_EncodeAndSendRpcRequest(ulong,_GUID,_CTAPCBOR_RPC_REQUEST &,ulong *,uchar * *)
0x1800b8d00  mov     ebx, eax
0x1800b8d02  test    eax, eax
0x1800b8d04  jns     short loc_1800B8D13
0x1800b8d06  mov     r9d, eax
0x1800b8d09  mov     edx, 6C1h
0x1800b8d0e  jmp     loc_1800B8EFA
0x1800b8d13  mov     ebx, dword ptr [rsp+320h+var_2D8]
0x1800b8d17  test    ebx, ebx
0x1800b8d19  jz      loc_1800B8ED7
0x1800b8d1f  cmp     [rsp+320h+lpMem], r12
0x1800b8d24  jz      loc_1800B8ED7
0x1800b8d2a  mov     rdx, [rsp+320h+lpMem]
0x1800b8d2f  lea     r8, [rsp+320h+var_2D8]
0x1800b8d34  xor     r9d, r9d
0x1800b8d37  mov     [rsp+320h+var_2D8], r12
0x1800b8d3c  mov     ecx, ebx
0x1800b8d3e  mov     qword ptr [rsp+320h+var_300], r12; int
0x1800b8d43  call    CtapCborDecodeCredentialDetailsArray
0x1800b8d48  mov     r14d, eax
0x1800b8d4b  test    eax, eax
0x1800b8d4d  jz      short loc_1800B8DA5
0x1800b8d4f  lea     rcx, aWebauthnplugin_140; "WebAuthNPluginAuthenticatorGetAllCreden"...
0x1800b8d56  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800b8d5b  mov     r8, rax
0x1800b8d5e  lea     rcx, [rsp+320h+var_2F0]
0x1800b8d63  mov     edx, 3
0x1800b8d68  call    ?complete_and_fail@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::complete_and_fail(ushort,char const *)
0x1800b8d6d  mov     ecx, r14d
0x1800b8d70  call    CtapCborErrorToWin32Error
0x1800b8d75  test    eax, eax
0x1800b8d77  jz      short loc_1800B8DA5
0x1800b8d79  mov     rcx, [rbp+228h]; this
0x1800b8d80  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800b8d87  mov     r9d, eax; char *
0x1800b8d8a  mov     edx, 6D4h; void *
0x1800b8d8f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800b8d94  mov     ebx, eax
0x1800b8d96  lea     rcx, [rsp+320h+var_2D8]
0x1800b8d9b  call    ??1?$unique_storage@U?$resource_policy@PEAEP6AXPEAX@Z$1?FidoFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>(void)
0x1800b8da0  jmp     loc_1800B8F0D
0x1800b8da5  mov     rbx, [rsp+320h+var_2D8]
0x1800b8daa  test    rbx, rbx
0x1800b8dad  jnz     short loc_1800B8DD1
0x1800b8daf  mov     rcx, [rbp+228h]; this
0x1800b8db6  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800b8dbd  mov     ebx, 80004003h
0x1800b8dc2  mov     edx, 6D6h; void *
0x1800b8dc7  mov     r9d, ebx; char *
0x1800b8dca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b8dcf  jmp     short loc_1800B8D96
0x1800b8dd1  mov     rcx, [rsp+320h+lpMem]; lpMem
0x1800b8dd6  call    CtapCltFree
0x1800b8ddb  lea     rdx, [rsp+320h+lpMem]; struct _EXPERIMENTAL_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS_LIST **
0x1800b8de0  mov     [rsp+320h+lpMem], r12
0x1800b8de5  mov     rcx, rbx; struct _WEBAUTHN_CREDENTIAL_DETAILS_LIST *
0x1800b8de8  call    ?ConvertWebAuthNCredentialsListToWebAuthNPluginCredentialsList@@YAJPEAU_WEBAUTHN_CREDENTIAL_DETAILS_LIST@@PEAPEAU_EXPERIMENTAL_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS_LIST@@@Z; ConvertWebAuthNCredentialsListToWebAuthNPluginCredentialsList(_WEBAUTHN_CREDENTIAL_DETAILS_LIST *,_EXPERIMENTAL_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS_LIST * *)
0x1800b8ded  test    eax, eax
0x1800b8def  jns     short loc_1800B8E54
0x1800b8df1  lea     rcx, aWebauthnplugin_52; "WebAuthNPluginAuthenticatorGetAllCreden"...
0x1800b8df8  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800b8dfd  mov     r8, rax
0x1800b8e00  lea     rcx, [rsp+320h+var_2F0]
0x1800b8e05  mov     edx, 9
0x1800b8e0a  call    ?complete_and_fail@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::complete_and_fail(ushort,char const *)
0x1800b8e0f  mov     ecx, r14d
0x1800b8e12  call    CtapCborErrorToWin32Error
0x1800b8e17  mov     ebx, eax
0x1800b8e19  test    eax, eax
0x1800b8e1b  jle     short loc_1800B8E26
0x1800b8e1d  movzx   ebx, ax
0x1800b8e20  or      ebx, 80070000h
0x1800b8e26  test    ebx, ebx
0x1800b8e28  jns     short loc_1800B8E45
0x1800b8e2a  mov     rcx, [rbp+228h]; this
0x1800b8e31  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800b8e38  mov     r9d, ebx; char *
0x1800b8e3b  mov     edx, 6DDh; void *
0x1800b8e40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b8e45  lea     rcx, [rsp+320h+lpMem]
0x1800b8e4a  call    ??1?$unique_storage@U?$resource_policy@PEAEP6AXPEAX@Z$1?FidoFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>(void)
0x1800b8e4f  jmp     loc_1800B8D96
0x1800b8e54  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800b8e58  lea     rcx, [rsp+320h+var_2C0]
0x1800b8e5d  mov     rdx, rdi
0x1800b8e60  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800b8e65  mov     rdi, [rsp+320h+lpMem]
0x1800b8e6a  mov     rcx, [rax]
0x1800b8e6d  mov     [rax], r12
0x1800b8e70  mov     [rdi], rcx
0x1800b8e73  lea     rcx, [rsp+320h+var_2C0]
0x1800b8e78  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1800b8e7d  mov     ebx, [rdi+8]
0x1800b8e80  lea     rcx, [rsp+320h+var_2F0]
0x1800b8e85  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::ensure_data(void)
0x1800b8e8a  mov     rdx, rax
0x1800b8e8d  lea     rcx, [rsp+320h+lpMem]
0x1800b8e92  call    ??0?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy> const &)
0x1800b8e97  mov     rax, [rsp+320h+lpMem]
0x1800b8e9c  lea     rcx, [rsp+320h+lpMem]
0x1800b8ea1  mov     [rax+190h], ebx
0x1800b8ea7  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(void)
0x1800b8eac  lea     rcx, [rsp+320h+var_2F0]
0x1800b8eb1  mov     [rsp+320h+lpMem], r12
0x1800b8eb6  mov     [r15], rdi
0x1800b8eb9  call    ?complete@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(void)
0x1800b8ebe  lea     rcx, [rsp+320h+lpMem]
0x1800b8ec3  call    ??1?$unique_storage@U?$resource_policy@PEAEP6AXPEAX@Z$1?FidoFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>(void)
0x1800b8ec8  lea     rcx, [rsp+320h+var_2D8]
0x1800b8ecd  call    ??1?$unique_storage@U?$resource_policy@PEAEP6AXPEAX@Z$1?FidoFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>(void)
0x1800b8ed2  jmp     loc_1800B8FDA
0x1800b8ed7  mov     edx, 18h; uBytes
0x1800b8edc  lea     ecx, [rdx+28h]; uFlags
0x1800b8edf  call    cs:__imp_LocalAlloc
0x1800b8ee5  mov     [r15], rax
0x1800b8ee8  test    rax, rax
0x1800b8eeb  jnz     short loc_1800B8F5B
0x1800b8eed  mov     ebx, 8007000Eh
0x1800b8ef2  mov     edx, 6C5h; void *
0x1800b8ef7  mov     r9d, ebx; char *
0x1800b8efa  mov     rcx, [rbp+228h]; this
0x1800b8f01  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800b8f08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b8f0d  mov     rcx, [rsp+320h+var_2F0]
0x1800b8f12  test    rcx, rcx
0x1800b8f15  jz      short loc_1800B8F4C
0x1800b8f17  add     rcx, 8
0x1800b8f1b  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x1800b8f20  test    al, al
0x1800b8f22  jz      short loc_1800B8F4C
0x1800b8f24  lea     rcx, aWebauthnplugin_132; "WebAuthNPluginAuthenticatorGetAllCreden"...
0x1800b8f2b  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800b8f30  mov     r8, rax
0x1800b8f33  lea     rcx, [rsp+320h+var_2F0]
0x1800b8f38  mov     edx, 1
0x1800b8f3d  call    ?set_flag@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::set_flag(ushort,char const *)
0x1800b8f42  lea     rcx, [rsp+320h+var_2F0]
0x1800b8f47  call    ?complete@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(void)
0x1800b8f4c  lea     rcx, [rsp+320h+var_2D0]
0x1800b8f51  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(void)
0x1800b8f56  jmp     loc_1800B8BDE
0x1800b8f5b  mov     [rax+8], r12d
0x1800b8f5f  lea     rcx, aWebauthnplugin_68; "WebAuthNPluginAuthenticatorGetAllCreden"...
0x1800b8f66  mov     rax, [r15]
0x1800b8f69  test    ebx, ebx
0x1800b8f6b  setz    r8b
0x1800b8f6f  mov     [rax+10h], r12
0x1800b8f73  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800b8f78  mov     rcx, [rsp+320h+var_2F0]
0x1800b8f7d  test    r8b, r8b
0x1800b8f80  jz      short loc_1800B8FA0
0x1800b8f82  test    rcx, rcx
0x1800b8f85  jz      short loc_1800B8FDA
0x1800b8f87  mov     r8d, 6
0x1800b8f8d  add     rcx, 8
0x1800b8f91  mov     r9, rax
0x1800b8f94  mov     dl, 1
0x1800b8f96  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestCompletionKind@@GPEBD@Z; tip2::details::shared_data<1,0,0>::complete_without_lock(TestCompletionKind,ushort,char const *)
0x1800b8f9b  mov     rcx, [rsp+320h+var_2F0]
0x1800b8fa0  test    rcx, rcx
0x1800b8fa3  jz      short loc_1800B8FDA
0x1800b8fa5  add     rcx, 8
0x1800b8fa9  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x1800b8fae  test    al, al
0x1800b8fb0  jz      short loc_1800B8FDA
0x1800b8fb2  lea     rcx, aWebauthnplugin_132; "WebAuthNPluginAuthenticatorGetAllCreden"...
0x1800b8fb9  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800b8fbe  mov     r8, rax
0x1800b8fc1  lea     rcx, [rsp+320h+var_2F0]
0x1800b8fc6  mov     edx, 1
0x1800b8fcb  call    ?set_flag@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::set_flag(ushort,char const *)
0x1800b8fd0  lea     rcx, [rsp+320h+var_2F0]
0x1800b8fd5  call    ?complete@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(void)
0x1800b8fda  lea     rcx, [rsp+320h+var_2D0]
  ... truncated ...
```
