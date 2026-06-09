# WebAuthNPluginUpdateAuthenticatorDetails

- ea: `0x18004d970`
- end: `0x18004e086`
- name: `WebAuthNPluginUpdateAuthenticatorDetails`
- size: `1814`
- prototype: ``
- caller_count: `0`
- callee_count: `30`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001e824`
- `0x1800205e4`
- `0x180022d34`
- `0x180036da4`
- `0x18004349c`
- `0x1800467e0`
- `0x18004685c`
- `0x180049de0`
- `0x18004d970`
- `0x18004e08c`
- `0x18004e0d0`
- `0x18004e2a4`
- `0x18004f5b4`
- `0x1800537a4`
- `0x180055188`
- `0x180067b74`
- `0x18006cfd4`
- `0x18006f7b0`
- `0x180079444`
- `0x18007e064`
- `0x1800b13dc`
- `0x1800b2a14`
- `0x1800b2f78`
- `0x1800b312c`
- `0x1800b4170`
- `0x1800b51e4`
- `0x1800b5278`
- `0x1800b7e08`
- `0x1800bff80`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004db16`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004dbba`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004df7c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004db16`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004dbba`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004df7c`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x18004da23`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x18004da23`

## string_xrefs

- `0x18004d9b5`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004da62`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004dac1`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004db4c`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004dbf2`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004dd95`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004de15`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004decc`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004df00`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004df3e`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004df8c`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004dfce`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004df1e`: `Plugins`
- `0x18004da34`: `WebAuthNPluginUpdateAuthenticatorDetailsTest::reason::remote_session`
- `0x18004dd5f`: `WebAuthNPluginUpdateAuthenticatorDetailsTest::reason::generic_failure`
- `0x18004da95`: `WebAuthNPluginUpdateAuthenticatorDetailsTest::reason::invalid_parameters`
- `0x18004db20`: `WebAuthNPluginUpdateAuthenticatorDetailsTest::reason::invalid_parameters`
- `0x18004dbc4`: `WebAuthNPluginUpdateAuthenticatorDetailsTest::reason::invalid_parameters`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall WebAuthNPluginUpdateAuthenticatorDetails(__int64 *a1, __int64 a2, __int64 a3)
{
  const char *v5; // rdx
  const char *v6; // rax
  const char *v7; // rax
  const char *v8; // rdx
  const char *v9; // rax
  const GUID *v10; // rcx
  __int64 v11; // rax
  const char *v12; // rdx
  const char *v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rsi
  __int64 v16; // r8
  __int64 v17; // rdx
  unsigned int v18; // ebx
  const char *v19; // rdx
  const char *v20; // rax
  int v21; // eax
  int Only; // eax
  int v23; // eax
  int v24; // eax
  _QWORD *v25; // rax
  unsigned int updated; // ebx
  int v27; // [rsp+20h] [rbp-3A8h]
  int v28; // [rsp+20h] [rbp-3A8h]
  _BYTE v29[8]; // [rsp+30h] [rbp-398h] BYREF
  __int64 v30; // [rsp+38h] [rbp-390h] BYREF
  _QWORD v31[2]; // [rsp+40h] [rbp-388h] BYREF
  struct _GUID v32; // [rsp+50h] [rbp-378h] BYREF
  _QWORD v33[2]; // [rsp+60h] [rbp-368h] BYREF
  _QWORD v34[4]; // [rsp+70h] [rbp-358h] BYREF
  char v35; // [rsp+90h] [rbp-338h]
  _BYTE v36[248]; // [rsp+B0h] [rbp-318h] BYREF
  __int64 v37; // [rsp+1A8h] [rbp-220h]
  OLECHAR *v38; // [rsp+1B0h] [rbp-218h]
  unsigned __int64 v39; // [rsp+1B8h] [rbp-210h]
  __int64 v40; // [rsp+1C8h] [rbp-200h]
  __int64 v41; // [rsp+1D0h] [rbp-1F8h]
  int v42; // [rsp+248h] [rbp-180h]
  __int64 v43; // [rsp+250h] [rbp-178h]
  int v44; // [rsp+26Ch] [rbp-15Ch]
  __int64 v45; // [rsp+270h] [rbp-158h]
  OLECHAR sz[4]; // [rsp+2F0h] [rbp-D8h] BYREF
  __int64 v47; // [rsp+2F8h] [rbp-D0h]
  __int64 v48; // [rsp+300h] [rbp-C8h]
  __int64 v49; // [rsp+308h] [rbp-C0h]
  __int64 v50; // [rsp+310h] [rbp-B8h]
  int v51; // [rsp+318h] [rbp-B0h]
  int v52; // [rsp+31Ch] [rbp-ACh]
  __int64 v53; // [rsp+320h] [rbp-A8h]
  int v54; // [rsp+328h] [rbp-A0h]
  int v55; // [rsp+32Ch] [rbp-9Ch]
  __int64 v56; // [rsp+330h] [rbp-98h]
  _QWORD *v57; // [rsp+338h] [rbp-90h]
  OLECHAR v58[40]; // [rsp+340h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl,
                          a2,
                          a3) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
    {
      if ( a1 )
      {
        *(_QWORD *)sz = *a1;
        v47 = a1[1];
        v48 = a1[2];
        v49 = a1[3];
        v50 = a1[4];
        v51 = *((_DWORD *)a1 + 10);
        v52 = 0;
        v53 = a1[6];
        v54 = *((_DWORD *)a1 + 14);
        v55 = 0;
        v56 = a1[8];
        v57 = 0;
        *(_QWORD *)&v32.Data1 = 0;
        v21 = wil::open_current_access_token_nothrow(&v32);
        if ( v21 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x323,
            (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
            (const char *)(unsigned int)v21,
            v27);
        v33[0] = 0;
        Only = CtapPluginInternal::GetUserRegKeyReadOnly(*(_QWORD *)&v32.Data1, v33);
        if ( Only < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x325,
            (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
            (const char *)(unsigned int)Only,
            v27);
        v30 = 0;
        v23 = wil::reg::open_unique_key_nothrow(v33[0], L"Plugins", &v30, 0);
        if ( v23 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x327,
            (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
            (const char *)(unsigned int)v23,
            v27);
        memset_0(v58, 0, sizeof(v58));
        if ( !StringFromGUID2((const GUID *const)a1[1], v58, 40) )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x329,
            (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
            (const char *)0x80090027LL,
            v27);
        v31[0] = 0;
        v24 = wil::reg::open_unique_key_nothrow(v30, v58, v31, 0);
        if ( v24 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x32B,
            (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
            (const char *)(unsigned int)v24,
            v27);
        wil::reg::try_get_value_string(v34, v31[0], L"UvKeyIdFromKcm");
        if ( v35 )
        {
          v25 = v34;
          if ( v34[3] > 7u )
            v25 = (_QWORD *)v34[0];
          v57 = v25;
        }
        updated = WebAuthNPluginUpdateAuthenticatorDetails2(sz);
        std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v34);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v31);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v30);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v33);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v32);
        return updated;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x312,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
          (const char *)0x80090027LL,
          v27);
        return 2148073511LL;
      }
    }
    else
    {
      v30 = 0;
      tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::start_and_watch_errors(
        &v30,
        v34);
      v29[0] = 0;
      memset_0(v36, 0, 0x238u);
      if ( (unsigned __int8)IsWinStationIsSessionRemoteablePresent()
        && (unsigned __int8)WinStationIsSessionRemoteable(0, 0xFFFFFFFFLL, v29)
        && v29[0] )
      {
        v6 = tip2::details::reason_string(
               (tip2::details *)"WebAuthNPluginUpdateAuthenticatorDetailsTest::reason::remote_session",
               v5);
        tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
          &v30,
          8,
          v6);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x340,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
          (const char *)0x80090029LL,
          v27);
        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(v34);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(&v30);
        return 2148073513LL;
      }
      else if ( a1 )
      {
        memset_0(sz, 0, 0x50u);
        if ( StringFromGUID2((const GUID *const)a1[1], sz, 40) )
        {
          memset_0(v58, 0, sizeof(v58));
          v10 = (const GUID *)a1[2];
          v11 = *(_QWORD *)&v10->Data1 - *(_QWORD *)&GUID_NULL.Data1;
          if ( *(_QWORD *)&v10->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
            v11 = *(_QWORD *)v10->Data4 - *(_QWORD *)GUID_NULL.Data4;
          if ( !v11 || StringFromGUID2(v10, v58, 40) )
          {
            v37 = *a1;
            v38 = sz;
            v39 = (unsigned __int64)v58 & -(__int64)(v58[0] != 0);
            v40 = a1[3];
            v41 = a1[4];
            v42 = *((_DWORD *)a1 + 10);
            v43 = a1[6];
            v44 = *((_DWORD *)a1 + 14);
            v45 = a1[8];
            tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::data(
              &v30,
              v31);
            v14 = v31[0];
            v15 = -1;
            v16 = -1;
            do
              ++v16;
            while ( sz[v16] );
            std::wstring::_Assign<unsigned short>(v31[0] + 272LL, sz);
            v17 = *a1;
            do
              ++v15;
            while ( *(_WORD *)(v17 + 2 * v15) );
            std::wstring::_Assign<unsigned short>(v14 + 304, v17);
            tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::close(v31);
            v32 = *(struct _GUID *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(
                                     &v30,
                                     v33);
            v18 = I_EncodeAndSendRpcRequest(0x66u, &v32, (struct _CTAPCBOR_RPC_REQUEST *)v36, 0, 0);
            if ( (v18 & 0x80000000) == 0 )
            {
              tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v30);
              tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(v31);
              tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(v34);
              wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(&v30);
              return 0;
            }
            else
            {
              if ( v30 )
              {
                if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v30 + 8) )
                {
                  v20 = tip2::details::reason_string(
                          (tip2::details *)"WebAuthNPluginUpdateAuthenticatorDetailsTest::reason::generic_failure",
                          v19);
                  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::set_flag_value<long>(
                    &v30,
                    1,
                    v20,
                    v18);
                  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v30);
                }
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x373,
                (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
                (const char *)v18,
                v28);
              tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(v31);
              tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(v34);
              wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(&v30);
              return v18;
            }
          }
          else
          {
            v13 = tip2::details::reason_string(
                    (tip2::details *)"WebAuthNPluginUpdateAuthenticatorDetailsTest::reason::invalid_parameters",
                    v12);
            tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
              &v30,
              2,
              v13);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x358,
              (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
              (const char *)0x80090027LL,
              v27);
            tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(v34);
            wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(&v30);
            return 2148073511LL;
          }
        }
        else
        {
          v9 = tip2::details::reason_string(
                 (tip2::details *)"WebAuthNPluginUpdateAuthenticatorDetailsTest::reason::invalid_parameters",
                 v8);
          tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
            &v30,
            2,
            v9);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x34E,
            (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
            (const char *)0x80090027LL,
            v27);
          tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(v34);
          wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(&v30);
          return 2148073511LL;
        }
      }
      else
      {
        v7 = tip2::details::reason_string(
               (tip2::details *)"WebAuthNPluginUpdateAuthenticatorDetailsTest::reason::invalid_parameters",
               v5);
        tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
          &v30,
          2,
          v7);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x346,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
          (const char *)0x80090027LL,
          v27);
        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(v34);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(&v30);
        return 2148073511LL;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30E,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80004001LL,
      v27);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x18004d970  push    rbx
0x18004d972  push    rsi
0x18004d973  push    rdi
0x18004d974  push    r14
0x18004d976  sub     rsp, 3A8h
0x18004d97d  mov     rax, cs:__security_cookie
0x18004d984  xor     rax, rsp
0x18004d987  mov     [rsp+3C8h+var_38], rax
0x18004d98f  mov     rdi, rcx
0x18004d992  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators> `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl(void)'::`2'::impl
0x18004d999  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(void)
0x18004d99e  xor     r14d, r14d
0x18004d9a1  test    al, al
0x18004d9a3  jnz     short loc_18004D9CD
0x18004d9a5  mov     rcx, [rsp+3C8h]; this
0x18004d9ad  mov     ebx, 80004001h
0x18004d9b2  mov     r9d, ebx; char *
0x18004d9b5  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004d9bc  mov     edx, 30Eh; void *
0x18004d9c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d9c6  mov     eax, ebx
0x18004d9c8  jmp     loc_18004E068
0x18004d9cd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x18004d9d4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x18004d9d9  test    al, al
0x18004d9db  jnz     loc_18004DE00
0x18004d9e1  mov     [rsp+3C8h+var_390], r14
0x18004d9e6  lea     rdx, [rsp+3C8h+var_358]
0x18004d9eb  lea     rcx, [rsp+3C8h+var_390]
0x18004d9f0  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::start_and_watch_errors(void)
0x18004d9f5  nop
0x18004d9f6  mov     [rsp+3C8h+var_398], r14b
0x18004d9fb  xor     edx, edx; Val
0x18004d9fd  mov     r8d, 238h; Size
0x18004da03  lea     rcx, [rsp+3C8h+var_318]; void *
0x18004da0b  call    memset_0
0x18004da10  call    IsWinStationIsSessionRemoteablePresent
0x18004da15  test    al, al
0x18004da17  jz      short loc_18004DA90
0x18004da19  lea     r8, [rsp+3C8h+var_398]
0x18004da1e  or      edx, 0FFFFFFFFh
0x18004da21  xor     ecx, ecx
0x18004da23  call    cs:__imp_WinStationIsSessionRemoteable
0x18004da29  test    al, al
0x18004da2b  jz      short loc_18004DA90
0x18004da2d  cmp     [rsp+3C8h+var_398], r14b
0x18004da32  jz      short loc_18004DA90
0x18004da34  lea     rcx, aWebauthnplugin_103; "WebAuthNPluginUpdateAuthenticatorDetail"...
0x18004da3b  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18004da40  mov     r8, rax
0x18004da43  mov     edx, 8
0x18004da48  lea     rcx, [rsp+3C8h+var_390]
0x18004da4d  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x18004da52  mov     rcx, [rsp+3C8h]; this
0x18004da5a  mov     ebx, 80090029h
0x18004da5f  mov     r9d, ebx; char *
0x18004da62  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004da69  mov     edx, 340h; void *
0x18004da6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004da73  nop
0x18004da74  lea     rcx, [rsp+3C8h+var_358]
0x18004da79  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(void)
0x18004da7e  nop
0x18004da7f  lea     rcx, [rsp+3C8h+var_390]
0x18004da84  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(void)
0x18004da89  mov     eax, ebx
0x18004da8b  jmp     loc_18004E068
0x18004da90  test    rdi, rdi
0x18004da93  jnz     short loc_18004DAEF
0x18004da95  lea     rcx, aWebauthnplugin_76; "WebAuthNPluginUpdateAuthenticatorDetail"...
0x18004da9c  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18004daa1  mov     r8, rax
0x18004daa4  lea     edx, [rdi+2]
0x18004daa7  lea     rcx, [rsp+3C8h+var_390]
0x18004daac  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x18004dab1  mov     rcx, [rsp+3C8h]; this
0x18004dab9  mov     ebx, 80090027h
0x18004dabe  mov     r9d, ebx; char *
0x18004dac1  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004dac8  mov     edx, 346h; void *
0x18004dacd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004dad2  nop
0x18004dad3  lea     rcx, [rsp+3C8h+var_358]
0x18004dad8  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(void)
0x18004dadd  nop
0x18004dade  lea     rcx, [rsp+3C8h+var_390]
0x18004dae3  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(void)
0x18004dae8  mov     eax, ebx
0x18004daea  jmp     loc_18004E068
0x18004daef  mov     ebx, 50h ; 'P'
0x18004daf4  mov     r8d, ebx; Size
0x18004daf7  xor     edx, edx; Val
0x18004daf9  lea     rcx, [rsp+3C8h+sz]; void *
0x18004db01  call    memset_0
0x18004db06  lea     r8d, [rbx-28h]; cchMax
0x18004db0a  lea     rdx, [rsp+3C8h+sz]; lpsz
0x18004db12  mov     rcx, [rdi+8]; rguid
0x18004db16  call    cs:__imp_StringFromGUID2
0x18004db1c  test    eax, eax
0x18004db1e  jnz     short loc_18004DB7A
0x18004db20  lea     rcx, aWebauthnplugin_76; "WebAuthNPluginUpdateAuthenticatorDetail"...
0x18004db27  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18004db2c  mov     r8, rax
0x18004db2f  lea     edx, [rbx-4Eh]
0x18004db32  lea     rcx, [rsp+3C8h+var_390]
0x18004db37  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x18004db3c  mov     rcx, [rsp+3C8h]; this
0x18004db44  mov     ebx, 80090027h
0x18004db49  mov     r9d, ebx; char *
0x18004db4c  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004db53  mov     edx, 34Eh; void *
0x18004db58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004db5d  nop
0x18004db5e  lea     rcx, [rsp+3C8h+var_358]
0x18004db63  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(void)
0x18004db68  nop
0x18004db69  lea     rcx, [rsp+3C8h+var_390]
0x18004db6e  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(void)
0x18004db73  mov     eax, ebx
0x18004db75  jmp     loc_18004E068
0x18004db7a  mov     r8, rbx; Size
0x18004db7d  xor     edx, edx; Val
0x18004db7f  lea     rcx, [rsp+3C8h+var_88]; void *
0x18004db87  call    memset_0
0x18004db8c  mov     rcx, [rdi+10h]; rguid
0x18004db90  mov     rax, [rcx]
0x18004db93  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18004db9a  jnz     short loc_18004DBA7
0x18004db9c  mov     rax, [rcx+8]
0x18004dba0  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18004dba7  test    rax, rax
0x18004dbaa  jz      short loc_18004DC20
0x18004dbac  mov     r8d, 28h ; '('; cchMax
0x18004dbb2  lea     rdx, [rsp+3C8h+var_88]; lpsz
0x18004dbba  call    cs:__imp_StringFromGUID2
0x18004dbc0  test    eax, eax
0x18004dbc2  jnz     short loc_18004DC20
0x18004dbc4  lea     rcx, aWebauthnplugin_76; "WebAuthNPluginUpdateAuthenticatorDetail"...
0x18004dbcb  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18004dbd0  mov     r8, rax
0x18004dbd3  mov     edx, 2
0x18004dbd8  lea     rcx, [rsp+3C8h+var_390]
0x18004dbdd  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x18004dbe2  mov     rcx, [rsp+3C8h]; this
0x18004dbea  mov     ebx, 80090027h
0x18004dbef  mov     r9d, ebx; char *
0x18004dbf2  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004dbf9  mov     edx, 358h; void *
0x18004dbfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004dc03  nop
0x18004dc04  lea     rcx, [rsp+3C8h+var_358]
0x18004dc09  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(void)
0x18004dc0e  nop
0x18004dc0f  lea     rcx, [rsp+3C8h+var_390]
0x18004dc14  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(void)
0x18004dc19  mov     eax, ebx
0x18004dc1b  jmp     loc_18004E068
0x18004dc20  mov     rax, [rdi]
0x18004dc23  mov     [rsp+3C8h+var_220], rax
0x18004dc2b  lea     rax, [rsp+3C8h+sz]
0x18004dc33  mov     [rsp+3C8h+var_218], rax
0x18004dc3b  movzx   eax, [rsp+3C8h+var_88]
0x18004dc43  neg     ax
0x18004dc46  sbb     rcx, rcx
0x18004dc49  lea     rax, [rsp+3C8h+var_88]
0x18004dc51  and     rcx, rax
0x18004dc54  mov     [rsp+3C8h+var_210], rcx
0x18004dc5c  mov     rax, [rdi+18h]
0x18004dc60  mov     [rsp+3C8h+var_200], rax
0x18004dc68  mov     rax, [rdi+20h]
0x18004dc6c  mov     [rsp+3C8h+var_1F8], rax
0x18004dc74  mov     eax, [rdi+28h]
0x18004dc77  mov     [rsp+3C8h+var_180], eax
0x18004dc7e  mov     rax, [rdi+30h]
0x18004dc82  mov     [rsp+3C8h+var_178], rax
0x18004dc8a  mov     eax, [rdi+38h]
0x18004dc8d  mov     [rsp+3C8h+var_15C], eax
0x18004dc94  mov     rax, [rdi+40h]
0x18004dc98  mov     [rsp+3C8h+var_158], rax
0x18004dca0  lea     rdx, [rsp+3C8h+var_388]
0x18004dca5  lea     rcx, [rsp+3C8h+var_390]
0x18004dcaa  call    ?data@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::data(void)
0x18004dcaf  nop
0x18004dcb0  mov     rbx, [rsp+3C8h+var_388]
0x18004dcb5  lea     rcx, [rbx+110h]
0x18004dcbc  lea     rax, [rsp+3C8h+sz]
0x18004dcc4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004dcc8  mov     r8, rsi
0x18004dccb  inc     r8
0x18004dcce  cmp     [rax+r8*2], r14w
0x18004dcd3  jnz     short loc_18004DCCB
0x18004dcd5  lea     rdx, [rsp+3C8h+sz]
0x18004dcdd  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004dce2  mov     rdx, [rdi]
0x18004dce5  lea     rcx, [rbx+130h]
0x18004dcec  inc     rsi
0x18004dcef  cmp     [rdx+rsi*2], r14w
0x18004dcf4  jnz     short loc_18004DCEC
0x18004dcf6  mov     r8, rsi
0x18004dcf9  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004dcfe  lea     rcx, [rsp+3C8h+var_388]
0x18004dd03  call    ?close@?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::close(void)
0x18004dd08  lea     rdx, [rsp+3C8h+var_368]
0x18004dd0d  lea     rcx, [rsp+3C8h+var_390]
0x18004dd12  call    ?test_id@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEBA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(void)
0x18004dd17  movups  xmm1, xmmword ptr [rax]
0x18004dd1a  movdqu  xmmword ptr [rsp+3C8h+var_378.Data1], xmm1
0x18004dd20  mov     qword ptr [rsp+3C8h+var_3A8], r14; int
0x18004dd25  xor     r9d, r9d; unsigned int *
0x18004dd28  lea     r8, [rsp+3C8h+var_318]; struct _CTAPCBOR_RPC_REQUEST *
0x18004dd30  lea     rdx, [rsp+3C8h+var_378]; struct _GUID *
0x18004dd35  lea     ecx, [r9+66h]; unsigned int
0x18004dd39  call    ?I_EncodeAndSendRpcRequest@@YAJKU_GUID@@AEAU_CTAPCBOR_RPC_REQUEST@@PEAKPEAPEAE@Z; I_EncodeAndSendRpcRequest(ulong,_GUID,_CTAPCBOR_RPC_REQUEST &,ulong *,uchar * *)
0x18004dd3e  mov     ebx, eax
0x18004dd40  test    eax, eax
0x18004dd42  jns     loc_18004DDCE
0x18004dd48  mov     rcx, [rsp+3C8h+var_390]
0x18004dd4d  test    rcx, rcx
0x18004dd50  jz      short loc_18004DD8A
0x18004dd52  add     rcx, 8
0x18004dd56  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x18004dd5b  test    al, al
0x18004dd5d  jz      short loc_18004DD8A
0x18004dd5f  lea     rcx, aWebauthnplugin_57; "WebAuthNPluginUpdateAuthenticatorDetail"...
0x18004dd66  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18004dd6b  mov     r8, rax
0x18004dd6e  mov     edx, 1
0x18004dd73  mov     r9d, ebx
0x18004dd76  lea     rcx, [rsp+3C8h+var_390]
0x18004dd7b  call    ??$set_flag_value@J@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBDJ@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::set_flag_value<long>(ushort,char const *,long)
0x18004dd80  lea     rcx, [rsp+3C8h+var_390]
0x18004dd85  call    ?complete@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(void)
0x18004dd8a  mov     rcx, [rsp+3C8h]; this
0x18004dd92  mov     r9d, ebx; char *
0x18004dd95  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004dd9c  mov     edx, 373h; void *
0x18004dda1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004dda6  nop
0x18004dda7  lea     rcx, [rsp+3C8h+var_388]
0x18004ddac  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(void)
0x18004ddb1  nop
0x18004ddb2  lea     rcx, [rsp+3C8h+var_358]
0x18004ddb7  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(void)
0x18004ddbc  nop
0x18004ddbd  lea     rcx, [rsp+3C8h+var_390]
0x18004ddc2  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(void)
0x18004ddc7  mov     eax, ebx
0x18004ddc9  jmp     loc_18004E068
0x18004ddce  lea     rcx, [rsp+3C8h+var_390]
0x18004ddd3  call    ?complete@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(void)
0x18004ddd8  nop
0x18004ddd9  lea     rcx, [rsp+3C8h+var_388]
0x18004ddde  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(void)
0x18004dde3  nop
0x18004dde4  lea     rcx, [rsp+3C8h+var_358]
0x18004dde9  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(void)
0x18004ddee  nop
0x18004ddef  lea     rcx, [rsp+3C8h+var_390]
0x18004ddf4  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(void)
0x18004ddf9  xor     eax, eax
0x18004ddfb  jmp     loc_18004E068
0x18004de00  test    rdi, rdi
0x18004de03  jnz     short loc_18004DE2D
0x18004de05  mov     rcx, [rsp+3C8h]; this
0x18004de0d  mov     ebx, 80090027h
0x18004de12  mov     r9d, ebx; char *
0x18004de15  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004de1c  mov     edx, 312h; void *
0x18004de21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004de26  mov     eax, ebx
0x18004de28  jmp     loc_18004E068
0x18004de2d  mov     rax, [rdi]
0x18004de30  mov     qword ptr [rsp+3C8h+sz], rax
0x18004de38  mov     rax, [rdi+8]
0x18004de3c  mov     [rsp+3C8h+var_D0], rax
0x18004de44  mov     rax, [rdi+10h]
0x18004de48  mov     [rsp+3C8h+var_C8], rax
0x18004de50  mov     rax, [rdi+18h]
0x18004de54  mov     [rsp+3C8h+var_C0], rax
0x18004de5c  mov     rax, [rdi+20h]
0x18004de60  mov     [rsp+3C8h+var_B8], rax
0x18004de68  mov     eax, [rdi+28h]
0x18004de6b  mov     [rsp+3C8h+var_B0], eax
0x18004de72  xor     eax, eax
0x18004de74  mov     [rsp+3C8h+var_AC], eax
0x18004de7b  mov     rax, [rdi+30h]
0x18004de7f  mov     [rsp+3C8h+var_A8], rax
0x18004de87  mov     eax, [rdi+38h]
0x18004de8a  mov     [rsp+3C8h+var_A0], eax
0x18004de91  xor     eax, eax
0x18004de93  mov     [rsp+3C8h+var_9C], eax
0x18004de9a  mov     rax, [rdi+40h]
0x18004de9e  mov     [rsp+3C8h+var_98], rax
0x18004dea6  mov     [rsp+3C8h+var_90], r14
0x18004deae  mov     qword ptr [rsp+3C8h+var_378.Data1], r14
0x18004deb3  lea     rcx, [rsp+3C8h+var_378]
0x18004deb8  call    ?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)
0x18004debd  mov     rcx, [rsp+3C8h]; this
0x18004dec5  test    eax, eax
0x18004dec7  jns     short loc_18004DEDD
  ... truncated ...
```
