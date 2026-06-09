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
__int64 __fastcall EXPERIMENTAL_WebAuthNPluginAuthenticatorGetAllCredentials(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  unsigned int v5; // ebx
  const char *v7; // rdx
  const char *v8; // rax
  __int64 v9; // rdx
  const char *v10; // rax
  const char *v11; // rax
  __int64 v12; // rax
  __int64 v13; // r8
  int v14; // eax
  __int64 v15; // r9
  __int64 v16; // rdx
  int v17; // ebx
  const char *v18; // rdx
  unsigned int v19; // r14d
  const char *v20; // rax
  unsigned int v21; // eax
  struct _WEBAUTHN_CREDENTIAL_DETAILS_LIST *v22; // rbx
  const char *v23; // rdx
  const char *v24; // rax
  int v25; // eax
  __int64 *v26; // rax
  _DWORD *v27; // rdi
  __int64 v28; // rcx
  int v29; // ebx
  __int64 v30; // rax
  _DWORD *v31; // rax
  const char *v32; // rdx
  const char *v33; // rdx
  const char *v34; // rax
  const char *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rcx
  char v38; // r8
  const char *v39; // rdx
  const char *v40; // rax
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  unsigned int v43; // [rsp+20h] [rbp-E0h]
  __int64 v44; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v45[8]; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-C0h] BYREF
  struct _WEBAUTHN_CREDENTIAL_DETAILS_LIST *v47; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v48[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID v49; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v50[64]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v51[256]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v52; // [rsp+1B0h] [rbp+B0h]
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl) )
  {
    v4 = 1680;
LABEL_3:
    v5 = -2147467263;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80004001LL,
      v41);
    return v5;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    v4 = 1681;
    goto LABEL_3;
  }
  v44 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::start_and_watch_errors(
    &v44,
    v50);
  v45[0] = 0;
  memset_0(v51, 0, 0x238u);
  *(_QWORD *)a2 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    if ( ShouldSendRequestToRemoteSession(0) )
    {
      v8 = tip2::details::reason_string(
             (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::remote_session",
             v7);
      tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
        &v44,
        7,
        v8);
      v9 = 1695;
LABEL_10:
      v5 = -2146893783;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)v5,
        v41);
LABEL_12:
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v50);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>(&v44);
      return v5;
    }
  }
  else if ( (unsigned __int8)IsWinStationIsSessionRemoteablePresent()
         && (unsigned __int8)WinStationIsSessionRemoteable(0, 0xFFFFFFFFLL, v45)
         && v45[0] )
  {
    v10 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::remote_session",
            v7);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      &v44,
      7,
      v10);
    v9 = 1704;
    goto LABEL_10;
  }
  if ( !a1 )
  {
    v11 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::invalid_parameters",
            v7);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      &v44,
      2,
      v11);
    v9 = 1711;
    v5 = -2146893785;
    goto LABEL_11;
  }
  v52 = a1;
  v12 = tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::ensure_data(&v44);
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(
    v48,
    v12);
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)(a1 + 2 * v13) );
  std::wstring::_Assign<unsigned short>(v48[0] + 272LL, a1);
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::close(v48);
  LODWORD(v47) = 0;
  lpMem = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(
    &v44,
    &v49);
  v14 = I_EncodeAndSendRpcRequest(
          0x6Eu,
          &v49,
          (struct _CTAPCBOR_RPC_REQUEST *)v51,
          (unsigned int *)&v47,
          (unsigned __int8 **)&lpMem);
  v5 = v14;
  if ( v14 < 0 )
  {
    v15 = (unsigned int)v14;
    v16 = 1729;
LABEL_40:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)v15,
      v42);
    goto LABEL_41;
  }
  v17 = (int)v47;
  if ( !(_DWORD)v47 || !lpMem )
  {
    v31 = LocalAlloc(0x40u, 0x18u);
    *(_QWORD *)a2 = v31;
    if ( !v31 )
    {
      v5 = -2147024882;
      v16 = 1733;
      v15 = 2147942414LL;
      goto LABEL_40;
    }
    v31[2] = 0;
    *(_QWORD *)(*(_QWORD *)a2 + 16LL) = 0;
    v35 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::credential_list_empty",
            v32);
    v37 = v44;
    if ( v38 )
    {
      if ( !v44 )
        goto LABEL_51;
      LOBYTE(v36) = 1;
      tip2::details::shared_data<1,0,0>::complete_without_lock(v44 + 8, v36, 6, v35);
      v37 = v44;
    }
    if ( v37 && (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v37 + 8) )
    {
      v40 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::generic_failure",
              v39);
      tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::set_flag(
        &v44,
        1,
        v40);
      tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v44);
    }
    goto LABEL_51;
  }
  v47 = 0;
  v19 = CtapCborDecodeCredentialDetailsArray(v17, (_DWORD)lpMem, (unsigned int)&v47, 0, 0);
  if ( v19 )
  {
    v20 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::decoding_failed",
            v18);
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::complete_and_fail(
      &v44,
      3,
      v20);
    v21 = CtapCborErrorToWin32Error(v19);
    if ( v21 )
    {
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x6D4,
             (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
             (const char *)v21,
             v43);
LABEL_28:
      wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v47);
LABEL_41:
      if ( v44 )
      {
        if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v44 + 8) )
        {
          v34 = tip2::details::reason_string(
                  (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::generic_failure",
                  v33);
          tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::set_flag(
            &v44,
            1,
            v34);
          tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v44);
        }
      }
      tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v48);
      goto LABEL_12;
    }
  }
  v22 = v47;
  if ( !v47 )
  {
    v5 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6D6,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80004003LL,
      v43);
    goto LABEL_28;
  }
  CtapCltFree(lpMem);
  lpMem = 0;
  if ( (int)ConvertWebAuthNCredentialsListToWebAuthNPluginCredentialsList(
              v22,
              (struct _EXPERIMENTAL_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS_LIST **)&lpMem) < 0 )
  {
    v24 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::credential_list_conversion_failed",
            v23);
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::complete_and_fail(
      &v44,
      9,
      v24);
    v25 = CtapCborErrorToWin32Error(v19);
    v5 = v25;
    if ( v25 > 0 )
      v5 = (unsigned __int16)v25 | 0x80070000;
    if ( (v5 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6DD,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)v5,
        v43);
    wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&lpMem);
    goto LABEL_28;
  }
  v26 = (__int64 *)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                     &v49,
                     a1,
                     -1);
  v27 = lpMem;
  v28 = *v26;
  *v26 = 0;
  *(_QWORD *)v27 = v28;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v49);
  v29 = v27[2];
  v30 = tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::ensure_data(&v44);
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(
    &lpMem,
    v30);
  *((_DWORD *)lpMem + 100) = v29;
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(&lpMem);
  lpMem = 0;
  *(_QWORD *)a2 = v27;
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v44);
  wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&lpMem);
  wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v47);
LABEL_51:
  tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v48);
  tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v50);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>(&v44);
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
