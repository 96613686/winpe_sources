# WebAuthNPluginAuthenticatorRemoveCredentials

- ea: `0x18004e2e0`
- end: `0x18004e858`
- name: `WebAuthNPluginAuthenticatorRemoveCredentials`
- size: `1400`
- prototype: `__int64 __fastcall(GUID *rguid)`
- caller_count: `0`
- callee_count: `27`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001cd78`
- `0x180036da4`
- `0x1800467e0`
- `0x18004685c`
- `0x18004e2e0`
- `0x18004e860`
- `0x18004f5b4`
- `0x1800537a4`
- `0x180055188`
- `0x18006cfd4`
- `0x18006d0e4`
- `0x18006f7b0`
- `0x180079444`
- `0x18007e064`
- `0x180095468`
- `0x1800b14c4`
- `0x1800b265c`
- `0x1800b2950`
- `0x1800b2e68`
- `0x1800b3014`
- `0x1800b366c`
- `0x1800b4170`
- `0x1800b50c4`
- `0x1800b55f8`
- `0x1800b7bdc`
- `0x1800d3914`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004e47f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004e47f`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x18004e3dd`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x18004e3dd`

## string_xrefs

- `0x18004e39c`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004e41c`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004e4b7`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004e54a`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004e622`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004e6be`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004e7df`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004e81a`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004e489`: `WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::invalid_parameters`
- `0x18004e51c`: `WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::invalid_parameters`
- `0x18004e5f9`: `WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::invalid_parameters`
- `0x18004e67b`: `WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::invalid_parameters`
- `0x18004e7b1`: `WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::invalid_parameters`
- `0x18004e36f`: `WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::remote_session`
- `0x18004e3ee`: `WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::remote_session`
- `0x18004e750`: `WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::generic_failure`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall WebAuthNPluginAuthenticatorRemoveCredentials(
        GUID *rguid,
        unsigned int a2,
        const struct _WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS *a3)
{
  const char *v6; // rdx
  const char *v7; // rax
  const char *v9; // rax
  const char *v10; // rdx
  const char *v11; // rax
  unsigned int i; // ecx
  unsigned __int64 v13; // rax
  const char *v14; // rax
  __int64 v15; // rax
  __int64 v16; // rbx
  __int64 v17; // r8
  const char *v18; // rdx
  int v19; // ebx
  const char *v20; // rax
  const char *v21; // rdx
  unsigned int v22; // ebx
  const char *v23; // rax
  int v24; // eax
  int v25; // ebx
  const char *v26; // rdx
  unsigned int v27; // eax
  char v28; // r9
  const char *v29; // rax
  int v30; // [rsp+20h] [rbp-348h]
  _BYTE v31[8]; // [rsp+30h] [rbp-338h] BYREF
  __int64 v32; // [rsp+38h] [rbp-330h] BYREF
  _QWORD v33[2]; // [rsp+40h] [rbp-328h] BYREF
  struct _GUID v34; // [rsp+50h] [rbp-318h] BYREF
  _BYTE v35[64]; // [rsp+60h] [rbp-308h] BYREF
  _BYTE v36[16]; // [rsp+A0h] [rbp-2C8h] BYREF
  _BYTE v37[232]; // [rsp+B0h] [rbp-2B8h] BYREF
  _BYTE v38[8]; // [rsp+198h] [rbp-1D0h] BYREF
  _BYTE v39[16]; // [rsp+1A0h] [rbp-1C8h] BYREF
  OLECHAR *v40; // [rsp+1B0h] [rbp-1B8h]
  OLECHAR sz[40]; // [rsp+2F0h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl) )
  {
    v32 = 0;
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::start_and_watch_errors(
      &v32,
      v35);
    v31[0] = 0;
    memset_0(v37, 0, 0x238u);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
    {
      if ( ShouldSendRequestToRemoteSession(0) )
      {
        v7 = tip2::details::reason_string(
               (tip2::details *)"WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::remote_session",
               v6);
        tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
          &v32,
          9,
          v7);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAC1,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
          (const char *)0x80090029LL,
          v30);
        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v35);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>(&v32);
        return 2148073513LL;
      }
    }
    else if ( (unsigned __int8)IsWinStationIsSessionRemoteablePresent()
           && (unsigned __int8)WinStationIsSessionRemoteable(0, 0xFFFFFFFFLL, v31)
           && v31[0] )
    {
      v9 = tip2::details::reason_string(
             (tip2::details *)"WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::remote_session",
             v6);
      tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
        &v32,
        9,
        v9);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xACA,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)0x80090029LL,
        v30);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v35);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>(&v32);
      return 2148073513LL;
    }
    if ( a2 && a3 )
    {
      memset_0(sz, 0, sizeof(sz));
      if ( StringFromGUID2(rguid, sz, 40) )
      {
        for ( i = 0; i < a2; ++i )
        {
          v13 = (unsigned __int64)i << 6;
          if ( !*(_QWORD *)((char *)a3 + v13 + 16)
            || !*(_QWORD *)((char *)a3 + v13 + 24)
            || !*(_QWORD *)((char *)a3 + v13 + 48)
            || !*(_DWORD *)((char *)a3 + v13)
            || !*(_QWORD *)((char *)a3 + v13 + 8) )
          {
            v14 = tip2::details::reason_string(
                    (tip2::details *)"WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::invalid_parameters",
                    v10);
            tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
              &v32,
              2,
              v14);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xAE6,
              (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
              (const char *)0x80090027LL,
              v30);
            tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v35);
            wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>(&v32);
            return 2148073511LL;
          }
        }
        v40 = sz;
        v15 = tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::ensure_data(&v32);
        tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(
          v33,
          v15);
        v16 = v33[0];
        v17 = -1;
        do
          ++v17;
        while ( sz[v17] );
        std::wstring::_Assign<unsigned short>(v33[0] + 272LL, sz);
        *(_DWORD *)(v16 + 400) = a2;
        tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::close(v33);
        *(_QWORD *)&v34.Data1 = 0;
        v19 = ConvertExperimental2CredentialDetailsArrayToWebAuthNCredentialsList(
                a2,
                a3,
                (struct _WEBAUTHN_CREDENTIAL_DETAILS_LIST **)&v34);
        if ( v19 >= 0 )
        {
          v22 = CtapCborEncodeCredentialDetailsList(*(_QWORD *)&v34.Data1, v38, v39);
          if ( v22 )
          {
            v23 = tip2::details::reason_string(
                    (tip2::details *)"WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::invalid_parameters",
                    v21);
            tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::set_flag(
              &v32,
              2,
              v23);
            v24 = CtapCborErrorToWin32Error(v22);
            v25 = v24;
            if ( v24 > 0 )
              v25 = (unsigned __int16)v24 | 0x80070000;
            if ( v25 < 0 )
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xB06,
                (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
                (const char *)(unsigned int)v25,
                v30);
          }
          else
          {
            v34 = *(struct _GUID *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(
                                     &v32,
                                     v36);
            v25 = I_EncodeAndSendRpcRequest(0x6Au, &v34, (struct _CTAPCBOR_RPC_REQUEST *)v37, 0, 0);
            if ( v32 )
            {
              if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v32 + 8) )
              {
                v27 = (unsigned int)tip2::details::reason_string(
                                      (tip2::details *)"WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::generic_failure",
                                      v26);
                tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::set_flag_value_if<long>(
                  (unsigned int)&v32,
                  1,
                  v27,
                  v25,
                  v28);
                if ( v32 )
                  tip2::details::shared_data<1,0,0>::complete_without_lock(v32 + 8);
              }
            }
          }
          tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v33);
          tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v35);
          wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>(&v32);
          return (unsigned int)v25;
        }
        else
        {
          v20 = tip2::details::reason_string(
                  (tip2::details *)"WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::invalid_parameters",
                  v18);
          tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::set_flag(
            &v32,
            2,
            v20);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAF7,
            (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
            (const char *)(unsigned int)v19,
            v30);
          tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v33);
          tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v35);
          wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>(&v32);
          return (unsigned int)v19;
        }
      }
      else
      {
        v11 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::invalid_parameters",
                v10);
        tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
          &v32,
          2,
          v11);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAD9,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
          (const char *)0x80090027LL,
          v30);
        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v35);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>(&v32);
        return 2148073511LL;
      }
    }
    else
    {
      v29 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::invalid_parameters",
              v6);
      tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
        &v32,
        2,
        v29);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAD1,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)0x80090027LL,
        v30);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(v35);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>(&v32);
      return 2148073511LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAB5,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80004001LL,
      v30);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x18004e2e0  mov     [rsp+arg_18], rbx
0x18004e2e5  push    rsi
0x18004e2e6  push    rdi
0x18004e2e7  push    r14
0x18004e2e9  sub     rsp, 350h
0x18004e2f0  mov     rax, cs:__security_cookie
0x18004e2f7  xor     rax, rsp
0x18004e2fa  mov     [rsp+368h+var_28], rax
0x18004e302  mov     rdi, r8
0x18004e305  mov     esi, edx
0x18004e307  mov     rbx, rcx
0x18004e30a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators> `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl(void)'::`2'::impl
0x18004e311  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(void)
0x18004e316  xor     r14d, r14d
0x18004e319  test    al, al
0x18004e31b  jz      loc_18004E80A
0x18004e321  mov     [rsp+368h+var_330], r14
0x18004e326  lea     rdx, [rsp+368h+var_308]
0x18004e32b  lea     rcx, [rsp+368h+var_330]
0x18004e330  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::start_and_watch_errors(void)
0x18004e335  nop
0x18004e336  mov     [rsp+368h+var_338], r14b
0x18004e33b  xor     edx, edx; Val
0x18004e33d  mov     r8d, 238h; Size
0x18004e343  lea     rcx, [rsp+368h+var_2B8]; void *
0x18004e34b  call    memset_0
0x18004e350  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x18004e357  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x18004e35c  test    al, al
0x18004e35e  jz      short loc_18004E3CA
0x18004e360  xor     ecx, ecx; unsigned __int8 *
0x18004e362  call    ?ShouldSendRequestToRemoteSession@@YA_NPEAE@Z; ShouldSendRequestToRemoteSession(uchar *)
0x18004e367  test    al, al
0x18004e369  jz      loc_18004E44A
0x18004e36f  lea     rcx, aWebauthnplugin_56; "WebAuthNPluginAuthenticatorRemoveCreden"...
0x18004e376  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18004e37b  mov     r8, rax
0x18004e37e  lea     edx, [r14+9]
0x18004e382  lea     rcx, [rsp+368h+var_330]
0x18004e387  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x18004e38c  mov     rcx, [rsp+368h]; this
0x18004e394  mov     ebx, 80090029h
0x18004e399  mov     r9d, ebx; char *
0x18004e39c  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004e3a3  mov     edx, 0AC1h; void *
0x18004e3a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e3ad  nop
0x18004e3ae  lea     rcx, [rsp+368h+var_308]
0x18004e3b3  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(void)
0x18004e3b8  nop
0x18004e3b9  lea     rcx, [rsp+368h+var_330]
0x18004e3be  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>(void)
0x18004e3c3  mov     eax, ebx
0x18004e3c5  jmp     loc_18004E833
0x18004e3ca  call    IsWinStationIsSessionRemoteablePresent
0x18004e3cf  test    al, al
0x18004e3d1  jz      short loc_18004E44A
0x18004e3d3  lea     r8, [rsp+368h+var_338]
0x18004e3d8  or      edx, 0FFFFFFFFh
0x18004e3db  xor     ecx, ecx
0x18004e3dd  call    cs:__imp_WinStationIsSessionRemoteable
0x18004e3e3  test    al, al
0x18004e3e5  jz      short loc_18004E44A
0x18004e3e7  cmp     [rsp+368h+var_338], r14b
0x18004e3ec  jz      short loc_18004E44A
0x18004e3ee  lea     rcx, aWebauthnplugin_56; "WebAuthNPluginAuthenticatorRemoveCreden"...
0x18004e3f5  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18004e3fa  mov     r8, rax
0x18004e3fd  mov     edx, 9
0x18004e402  lea     rcx, [rsp+368h+var_330]
0x18004e407  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x18004e40c  mov     rcx, [rsp+368h]; this
0x18004e414  mov     ebx, 80090029h
0x18004e419  mov     r9d, ebx; char *
0x18004e41c  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004e423  mov     edx, 0ACAh; void *
0x18004e428  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e42d  nop
0x18004e42e  lea     rcx, [rsp+368h+var_308]
0x18004e433  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(void)
0x18004e438  nop
0x18004e439  lea     rcx, [rsp+368h+var_330]
0x18004e43e  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>(void)
0x18004e443  mov     eax, ebx
0x18004e445  jmp     loc_18004E833
0x18004e44a  test    esi, esi
0x18004e44c  jz      loc_18004E7B1
0x18004e452  test    rdi, rdi
0x18004e455  jz      loc_18004E7B1
0x18004e45b  xor     edx, edx; Val
0x18004e45d  lea     r8d, [rdx+50h]; Size
0x18004e461  lea     rcx, [rsp+368h+sz]; void *
0x18004e469  call    memset_0
0x18004e46e  mov     r8d, 28h ; '('; cchMax
0x18004e474  lea     rdx, [rsp+368h+sz]; lpsz
0x18004e47c  mov     rcx, rbx; rguid
0x18004e47f  call    cs:__imp_StringFromGUID2
0x18004e485  test    eax, eax
0x18004e487  jnz     short loc_18004E4E5
0x18004e489  lea     rcx, aWebauthnplugin_135; "WebAuthNPluginAuthenticatorRemoveCreden"...
0x18004e490  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18004e495  mov     r8, rax
0x18004e498  mov     edx, 2
0x18004e49d  lea     rcx, [rsp+368h+var_330]
0x18004e4a2  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x18004e4a7  mov     rcx, [rsp+368h]; this
0x18004e4af  mov     ebx, 80090027h
0x18004e4b4  mov     r9d, ebx; char *
0x18004e4b7  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004e4be  mov     edx, 0AD9h; void *
0x18004e4c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e4c8  nop
0x18004e4c9  lea     rcx, [rsp+368h+var_308]
0x18004e4ce  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(void)
0x18004e4d3  nop
0x18004e4d4  lea     rcx, [rsp+368h+var_330]
0x18004e4d9  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>(void)
0x18004e4de  mov     eax, ebx
0x18004e4e0  jmp     loc_18004E833
0x18004e4e5  mov     ecx, r14d
0x18004e4e8  cmp     ecx, esi
0x18004e4ea  jnb     loc_18004E578
0x18004e4f0  mov     eax, ecx
0x18004e4f2  shl     rax, 6
0x18004e4f6  cmp     [rax+rdi+10h], r14
0x18004e4fb  jz      short loc_18004E51C
0x18004e4fd  cmp     [rax+rdi+18h], r14
0x18004e502  jz      short loc_18004E51C
0x18004e504  cmp     [rax+rdi+30h], r14
0x18004e509  jz      short loc_18004E51C
0x18004e50b  cmp     [rax+rdi], r14d
0x18004e50f  jz      short loc_18004E51C
0x18004e511  cmp     [rax+rdi+8], r14
0x18004e516  jz      short loc_18004E51C
0x18004e518  inc     ecx
0x18004e51a  jmp     short loc_18004E4E8
0x18004e51c  lea     rcx, aWebauthnplugin_135; "WebAuthNPluginAuthenticatorRemoveCreden"...
0x18004e523  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18004e528  mov     r8, rax
0x18004e52b  mov     edx, 2
0x18004e530  lea     rcx, [rsp+368h+var_330]
0x18004e535  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x18004e53a  mov     rcx, [rsp+368h]; this
0x18004e542  mov     ebx, 80090027h
0x18004e547  mov     r9d, ebx; char *
0x18004e54a  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004e551  mov     edx, 0AE6h; void *
0x18004e556  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e55b  nop
0x18004e55c  lea     rcx, [rsp+368h+var_308]
0x18004e561  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(void)
0x18004e566  nop
0x18004e567  lea     rcx, [rsp+368h+var_330]
0x18004e56c  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>(void)
0x18004e571  mov     eax, ebx
0x18004e573  jmp     loc_18004E833
0x18004e578  lea     rax, [rsp+368h+sz]
0x18004e580  mov     [rsp+368h+var_1B8], rax
0x18004e588  lea     rcx, [rsp+368h+var_330]
0x18004e58d  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::ensure_data(void)
0x18004e592  mov     rdx, rax
0x18004e595  lea     rcx, [rsp+368h+var_328]
0x18004e59a  call    ??0?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy> const &)
0x18004e59f  nop
0x18004e5a0  mov     rbx, [rsp+368h+var_328]
0x18004e5a5  lea     rcx, [rbx+110h]
0x18004e5ac  lea     rax, [rsp+368h+sz]
0x18004e5b4  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004e5b8  inc     r8
0x18004e5bb  cmp     [rax+r8*2], r14w
0x18004e5c0  jnz     short loc_18004E5B8
0x18004e5c2  lea     rdx, [rsp+368h+sz]
0x18004e5ca  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004e5cf  mov     [rbx+190h], esi
0x18004e5d5  lea     rcx, [rsp+368h+var_328]
0x18004e5da  call    ?close@?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::close(void)
0x18004e5df  mov     qword ptr [rsp+368h+var_318.Data1], r14
0x18004e5e4  lea     r8, [rsp+368h+var_318]; struct _WEBAUTHN_CREDENTIAL_DETAILS_LIST **
0x18004e5e9  mov     rdx, rdi; struct _WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS *
0x18004e5ec  mov     ecx, esi; unsigned int
0x18004e5ee  call    ?ConvertExperimental2CredentialDetailsArrayToWebAuthNCredentialsList@@YAJKPEBU_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS@@PEAPEAU_WEBAUTHN_CREDENTIAL_DETAILS_LIST@@@Z; ConvertExperimental2CredentialDetailsArrayToWebAuthNCredentialsList(ulong,_WEBAUTHN_PLUGIN_CREDENTIAL_DETAILS const *,_WEBAUTHN_CREDENTIAL_DETAILS_LIST * *)
0x18004e5f3  mov     ebx, eax
0x18004e5f5  test    eax, eax
0x18004e5f7  jns     short loc_18004E65B
0x18004e5f9  lea     rcx, aWebauthnplugin_135; "WebAuthNPluginAuthenticatorRemoveCreden"...
0x18004e600  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18004e605  mov     r8, rax
0x18004e608  mov     edx, 2
0x18004e60d  lea     rcx, [rsp+368h+var_330]
0x18004e612  call    ?set_flag@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::set_flag(ushort,char const *)
0x18004e617  mov     rcx, [rsp+368h]; this
0x18004e61f  mov     r9d, ebx; char *
0x18004e622  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004e629  mov     edx, 0AF7h; void *
0x18004e62e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e633  nop
0x18004e634  lea     rcx, [rsp+368h+var_328]
0x18004e639  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(void)
0x18004e63e  nop
0x18004e63f  lea     rcx, [rsp+368h+var_308]
0x18004e644  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(void)
0x18004e649  nop
0x18004e64a  lea     rcx, [rsp+368h+var_330]
0x18004e64f  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>(void)
0x18004e654  mov     eax, ebx
0x18004e656  jmp     loc_18004E833
0x18004e65b  lea     r8, [rsp+368h+var_1C8]
0x18004e663  lea     rdx, [rsp+368h+var_1D0]
0x18004e66b  mov     rcx, qword ptr [rsp+368h+var_318.Data1]
0x18004e670  call    CtapCborEncodeCredentialDetailsList
0x18004e675  mov     ebx, eax
0x18004e677  test    eax, eax
0x18004e679  jz      short loc_18004E6F7
0x18004e67b  lea     rcx, aWebauthnplugin_135; "WebAuthNPluginAuthenticatorRemoveCreden"...
0x18004e682  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18004e687  mov     r8, rax
0x18004e68a  mov     edx, 2
0x18004e68f  lea     rcx, [rsp+368h+var_330]
0x18004e694  call    ?set_flag@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::set_flag(ushort,char const *)
0x18004e699  mov     ecx, ebx
0x18004e69b  call    CtapCborErrorToWin32Error
0x18004e6a0  mov     ebx, eax
0x18004e6a2  test    eax, eax
0x18004e6a4  jle     short loc_18004E6AF
0x18004e6a6  movzx   ebx, ax
0x18004e6a9  or      ebx, 80070000h
0x18004e6af  test    ebx, ebx
0x18004e6b1  jns     short loc_18004E6D0
0x18004e6b3  mov     rcx, [rsp+368h]; this
0x18004e6bb  mov     r9d, ebx; char *
0x18004e6be  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004e6c5  mov     edx, 0B06h; void *
0x18004e6ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e6cf  nop
0x18004e6d0  lea     rcx, [rsp+368h+var_328]
0x18004e6d5  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(void)
0x18004e6da  nop
0x18004e6db  lea     rcx, [rsp+368h+var_308]
0x18004e6e0  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(void)
0x18004e6e5  nop
0x18004e6e6  lea     rcx, [rsp+368h+var_330]
0x18004e6eb  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>(void)
0x18004e6f0  mov     eax, ebx
0x18004e6f2  jmp     loc_18004E833
0x18004e6f7  lea     rdx, [rsp+368h+var_2C8]
0x18004e6ff  lea     rcx, [rsp+368h+var_330]
0x18004e704  call    ?test_id@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEBA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(void)
0x18004e709  movups  xmm1, xmmword ptr [rax]
0x18004e70c  movdqu  xmmword ptr [rsp+368h+var_318.Data1], xmm1
0x18004e712  mov     qword ptr [rsp+368h+var_348], r14; unsigned __int8 **
0x18004e717  xor     r9d, r9d; unsigned int *
0x18004e71a  lea     r8, [rsp+368h+var_2B8]; struct _CTAPCBOR_RPC_REQUEST *
0x18004e722  lea     rdx, [rsp+368h+var_318]; struct _GUID *
0x18004e727  lea     ecx, [r9+6Ah]; unsigned int
0x18004e72b  call    ?I_EncodeAndSendRpcRequest@@YAJKU_GUID@@AEAU_CTAPCBOR_RPC_REQUEST@@PEAKPEAPEAE@Z; I_EncodeAndSendRpcRequest(ulong,_GUID,_CTAPCBOR_RPC_REQUEST &,ulong *,uchar * *)
0x18004e730  mov     ebx, eax
0x18004e732  mov     rcx, [rsp+368h+var_330]
0x18004e737  test    rcx, rcx
0x18004e73a  jz      short loc_18004E78A
0x18004e73c  add     rcx, 8
0x18004e740  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x18004e745  test    al, al
0x18004e747  jz      short loc_18004E78A
0x18004e749  mov     r9d, ebx
0x18004e74c  shr     r9d, 1Fh
0x18004e750  lea     rcx, aWebauthnplugin_120; "WebAuthNPluginAuthenticatorRemoveCreden"...
0x18004e757  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18004e75c  mov     r8, rax
0x18004e75f  mov     edx, 1
0x18004e764  mov     byte ptr [rsp+368h+var_348], r9b
0x18004e769  mov     r9d, ebx
0x18004e76c  lea     rcx, [rsp+368h+var_330]
0x18004e771  call    ??$set_flag_value_if@J@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBDJ_N@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::set_flag_value_if<long>(ushort,char const *,long,bool)
0x18004e776  mov     rcx, [rsp+368h+var_330]
0x18004e77b  test    rcx, rcx
0x18004e77e  jz      short loc_18004E78A
0x18004e780  add     rcx, 8
0x18004e784  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::complete_without_lock(void)
0x18004e789  nop
0x18004e78a  lea     rcx, [rsp+368h+var_328]
0x18004e78f  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(void)
0x18004e794  nop
0x18004e795  lea     rcx, [rsp+368h+var_308]
0x18004e79a  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>(void)
0x18004e79f  nop
0x18004e7a0  lea     rcx, [rsp+368h+var_330]
0x18004e7a5  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>(void)
0x18004e7aa  mov     eax, ebx
0x18004e7ac  jmp     loc_18004E833
0x18004e7b1  lea     rcx, aWebauthnplugin_135; "WebAuthNPluginAuthenticatorRemoveCreden"...
0x18004e7b8  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18004e7bd  mov     r8, rax
0x18004e7c0  mov     edx, 2
0x18004e7c5  lea     rcx, [rsp+368h+var_330]
0x18004e7ca  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x18004e7cf  mov     rcx, [rsp+368h]; this
0x18004e7d7  mov     ebx, 80090027h
0x18004e7dc  mov     r9d, ebx; char *
0x18004e7df  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004e7e6  mov     edx, 0AD1h; void *
  ... truncated ...
```
