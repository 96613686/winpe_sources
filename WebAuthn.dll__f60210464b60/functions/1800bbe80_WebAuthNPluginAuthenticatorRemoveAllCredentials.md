# WebAuthNPluginAuthenticatorRemoveAllCredentials

- ea: `0x1800bbe80`
- end: `0x1800bc221`
- name: `WebAuthNPluginAuthenticatorRemoveAllCredentials`
- size: `929`
- prototype: `__int64 __fastcall(GUID *rguid)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180036da4`
- `0x1800467e0`
- `0x18004685c`
- `0x18004f5b4`
- `0x1800537a4`
- `0x180055188`
- `0x18006cfd4`
- `0x18006d0e4`
- `0x18006f7b0`
- `0x180079444`
- `0x18007e064`
- `0x180095468`
- `0x1800b1474`
- `0x1800b265c`
- `0x1800b2934`
- `0x1800b2e44`
- `0x1800b2fec`
- `0x1800b4170`
- `0x1800b5094`
- `0x1800b55a0`
- `0x1800b7b74`
- `0x1800bbe80`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bc02a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bc02a`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x1800bbf99`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x1800bbf99`

## string_xrefs

- `0x1800bbec4`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bbf58`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bbfd8`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bc062`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bc1a1`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bbf2a`: `WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::remote_session`
- `0x1800bbfaa`: `WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::remote_session`
- `0x1800bc149`: `WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::generic_failure`
- `0x1800bc034`: `WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::invalid_parameters`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall WebAuthNPluginAuthenticatorRemoveAllCredentials(GUID *rguid, __int64 a2, __int64 a3)
{
  const char *v5; // rdx
  const char *v6; // rax
  const char *v7; // rdx
  const char *v8; // rax
  const char *v9; // rdx
  const char *v10; // rax
  __int64 v11; // rax
  __int64 v12; // r8
  int v13; // ebx
  const char *v14; // rdx
  unsigned int v15; // eax
  char v16; // r9
  int v17; // [rsp+20h] [rbp-328h]
  int v18; // [rsp+20h] [rbp-328h]
  _BYTE v19[8]; // [rsp+30h] [rbp-318h] BYREF
  __int64 v20; // [rsp+38h] [rbp-310h] BYREF
  _QWORD v21[2]; // [rsp+40h] [rbp-308h] BYREF
  struct _GUID v22; // [rsp+50h] [rbp-2F8h] BYREF
  _BYTE v23[64]; // [rsp+60h] [rbp-2E8h] BYREF
  _BYTE v24[256]; // [rsp+A0h] [rbp-2A8h] BYREF
  OLECHAR *v25; // [rsp+1A0h] [rbp-1A8h]
  OLECHAR sz[40]; // [rsp+2E0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+0h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(
                           `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl,
                           a2,
                           a3) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB18,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80004001LL,
      v17);
    return 2147500033LL;
  }
  v20 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::start_and_watch_errors(
    &v20,
    v23);
  v19[0] = 0;
  memset_0(v24, 0, 0x238u);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    if ( ShouldSendRequestToRemoteSession(0) )
    {
      v6 = tip2::details::reason_string(
             (tip2::details *)"WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::remote_session",
             v5);
      tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
        &v20,
        6,
        v6);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB24,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)0x80090029LL,
        v17);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(v23);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>(&v20);
      return 2148073513LL;
    }
  }
  else if ( (unsigned __int8)IsWinStationIsSessionRemoteablePresent()
         && (unsigned __int8)WinStationIsSessionRemoteable(0, 0xFFFFFFFFLL, v19)
         && v19[0] )
  {
    v8 = tip2::details::reason_string(
           (tip2::details *)"WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::remote_session",
           v7);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      &v20,
      6,
      v8);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB2D,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090029LL,
      v17);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(v23);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>(&v20);
    return 2148073513LL;
  }
  memset_0(sz, 0, sizeof(sz));
  if ( StringFromGUID2(rguid, sz, 40) )
  {
    v25 = sz;
    v11 = tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::ensure_data(&v20);
    tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(
      v21,
      v11);
    v12 = -1;
    do
      ++v12;
    while ( sz[v12] );
    std::wstring::_Assign<unsigned short>(v21[0] + 272LL, sz);
    tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::close(v21);
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(
      &v20,
      &v22);
    v13 = I_EncodeAndSendRpcRequest(0x6Bu, &v22, (struct _CTAPCBOR_RPC_REQUEST *)v24, 0, 0);
    if ( v20 )
    {
      if ( tip2::details::shared_data<1,0,0>::is_running(v20 + 8) )
      {
        v15 = (unsigned int)tip2::details::reason_string(
                              (tip2::details *)"WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::generic_failure",
                              v14);
        tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::set_flag_value_if<long>(
          (unsigned int)&v20,
          1,
          v15,
          v13,
          v16);
        if ( v20 )
          tip2::details::shared_data<1,0,0>::complete_without_lock(v20 + 8);
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
    {
      if ( v13 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB48,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
          (const char *)(unsigned int)v13,
          v18);
    }
    tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(v21);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(v23);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>(&v20);
    return (unsigned int)v13;
  }
  else
  {
    v10 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::invalid_parameters",
            v9);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      &v20,
      2,
      v10);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB36,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090027LL,
      v17);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(v23);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>(&v20);
    return 2148073511LL;
  }
}

```

## disassembly

```asm
0x1800bbe80  mov     [rsp+arg_8], rbx
0x1800bbe85  push    rdi
0x1800bbe86  sub     rsp, 340h
0x1800bbe8d  mov     rax, cs:__security_cookie
0x1800bbe94  xor     rax, rsp
0x1800bbe97  mov     [rsp+348h+var_18], rax
0x1800bbe9f  mov     rbx, rcx
0x1800bbea2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators> `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl(void)'::`2'::impl
0x1800bbea9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(void)
0x1800bbeae  xor     edi, edi
0x1800bbeb0  test    al, al
0x1800bbeb2  jnz     short loc_1800BBEDC
0x1800bbeb4  mov     rcx, [rsp+348h]; this
0x1800bbebc  mov     ebx, 80004001h
0x1800bbec1  mov     r9d, ebx; char *
0x1800bbec4  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bbecb  mov     edx, 0B18h; void *
0x1800bbed0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbed5  mov     eax, ebx
0x1800bbed7  jmp     loc_1800BC1FF
0x1800bbedc  mov     [rsp+348h+var_310], rdi
0x1800bbee1  lea     rdx, [rsp+348h+var_2E8]
0x1800bbee6  lea     rcx, [rsp+348h+var_310]
0x1800bbeeb  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::start_and_watch_errors(void)
0x1800bbef0  nop
0x1800bbef1  mov     [rsp+348h+var_318], dil
0x1800bbef6  xor     edx, edx; Val
0x1800bbef8  mov     r8d, 238h; Size
0x1800bbefe  lea     rcx, [rsp+348h+var_2A8]; void *
0x1800bbf06  call    memset_0
0x1800bbf0b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1800bbf12  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800bbf17  test    al, al
0x1800bbf19  jz      short loc_1800BBF86
0x1800bbf1b  xor     ecx, ecx; unsigned __int8 *
0x1800bbf1d  call    ?ShouldSendRequestToRemoteSession@@YA_NPEAE@Z; ShouldSendRequestToRemoteSession(uchar *)
0x1800bbf22  test    al, al
0x1800bbf24  jz      loc_1800BC006
0x1800bbf2a  lea     rcx, aWebauthnplugin_69; "WebAuthNPluginAuthenticatorRemoveAllCre"...
0x1800bbf31  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bbf36  mov     r8, rax
0x1800bbf39  mov     edx, 6
0x1800bbf3e  lea     rcx, [rsp+348h+var_310]
0x1800bbf43  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bbf48  mov     rcx, [rsp+348h]; this
0x1800bbf50  mov     ebx, 80090029h
0x1800bbf55  mov     r9d, ebx; char *
0x1800bbf58  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bbf5f  mov     edx, 0B24h; void *
0x1800bbf64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbf69  nop
0x1800bbf6a  lea     rcx, [rsp+348h+var_2E8]
0x1800bbf6f  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(void)
0x1800bbf74  nop
0x1800bbf75  lea     rcx, [rsp+348h+var_310]
0x1800bbf7a  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>(void)
0x1800bbf7f  mov     eax, ebx
0x1800bbf81  jmp     loc_1800BC1FF
0x1800bbf86  call    IsWinStationIsSessionRemoteablePresent
0x1800bbf8b  test    al, al
0x1800bbf8d  jz      short loc_1800BC006
0x1800bbf8f  lea     r8, [rsp+348h+var_318]
0x1800bbf94  or      edx, 0FFFFFFFFh
0x1800bbf97  xor     ecx, ecx
0x1800bbf99  call    cs:__imp_WinStationIsSessionRemoteable
0x1800bbf9f  test    al, al
0x1800bbfa1  jz      short loc_1800BC006
0x1800bbfa3  cmp     [rsp+348h+var_318], dil
0x1800bbfa8  jz      short loc_1800BC006
0x1800bbfaa  lea     rcx, aWebauthnplugin_69; "WebAuthNPluginAuthenticatorRemoveAllCre"...
0x1800bbfb1  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bbfb6  mov     r8, rax
0x1800bbfb9  mov     edx, 6
0x1800bbfbe  lea     rcx, [rsp+348h+var_310]
0x1800bbfc3  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bbfc8  mov     rcx, [rsp+348h]; this
0x1800bbfd0  mov     ebx, 80090029h
0x1800bbfd5  mov     r9d, ebx; char *
0x1800bbfd8  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bbfdf  mov     edx, 0B2Dh; void *
0x1800bbfe4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbfe9  nop
0x1800bbfea  lea     rcx, [rsp+348h+var_2E8]
0x1800bbfef  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(void)
0x1800bbff4  nop
0x1800bbff5  lea     rcx, [rsp+348h+var_310]
0x1800bbffa  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>(void)
0x1800bbfff  mov     eax, ebx
0x1800bc001  jmp     loc_1800BC1FF
0x1800bc006  xor     edx, edx; Val
0x1800bc008  lea     r8d, [rdx+50h]; Size
0x1800bc00c  lea     rcx, [rsp+348h+sz]; void *
0x1800bc014  call    memset_0
0x1800bc019  mov     r8d, 28h ; '('; cchMax
0x1800bc01f  lea     rdx, [rsp+348h+sz]; lpsz
0x1800bc027  mov     rcx, rbx; rguid
0x1800bc02a  call    cs:__imp_StringFromGUID2
0x1800bc030  test    eax, eax
0x1800bc032  jnz     short loc_1800BC090
0x1800bc034  lea     rcx, aWebauthnplugin_130; "WebAuthNPluginAuthenticatorRemoveAllCre"...
0x1800bc03b  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bc040  mov     r8, rax
0x1800bc043  mov     edx, 2
0x1800bc048  lea     rcx, [rsp+348h+var_310]
0x1800bc04d  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bc052  mov     rcx, [rsp+348h]; this
0x1800bc05a  mov     ebx, 80090027h
0x1800bc05f  mov     r9d, ebx; char *
0x1800bc062  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bc069  mov     edx, 0B36h; void *
0x1800bc06e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc073  nop
0x1800bc074  lea     rcx, [rsp+348h+var_2E8]
0x1800bc079  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(void)
0x1800bc07e  nop
0x1800bc07f  lea     rcx, [rsp+348h+var_310]
0x1800bc084  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>(void)
0x1800bc089  mov     eax, ebx
0x1800bc08b  jmp     loc_1800BC1FF
0x1800bc090  lea     rax, [rsp+348h+sz]
0x1800bc098  mov     [rsp+348h+var_1A8], rax
0x1800bc0a0  lea     rcx, [rsp+348h+var_310]
0x1800bc0a5  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::ensure_data(void)
0x1800bc0aa  mov     rdx, rax
0x1800bc0ad  lea     rcx, [rsp+348h+var_308]
0x1800bc0b2  call    ??0?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy> const &)
0x1800bc0b7  nop
0x1800bc0b8  mov     rcx, [rsp+348h+var_308]
0x1800bc0bd  add     rcx, 110h
0x1800bc0c4  lea     rax, [rsp+348h+sz]
0x1800bc0cc  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800bc0d0  inc     r8
0x1800bc0d3  cmp     [rax+r8*2], di
0x1800bc0d8  jnz     short loc_1800BC0D0
0x1800bc0da  lea     rdx, [rsp+348h+sz]
0x1800bc0e2  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800bc0e7  lea     rcx, [rsp+348h+var_308]
0x1800bc0ec  call    ?close@?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::close(void)
0x1800bc0f1  lea     rdx, [rsp+348h+var_2F8]
0x1800bc0f6  lea     rcx, [rsp+348h+var_310]
0x1800bc0fb  call    ?test_id@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEBA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(void)
0x1800bc100  movaps  xmm1, xmmword ptr [rsp+348h+var_2F8.Data1]
0x1800bc105  movdqa  xmmword ptr [rsp+348h+var_2F8.Data1], xmm1
0x1800bc10b  mov     qword ptr [rsp+348h+var_328], rdi; unsigned __int8 **
0x1800bc110  xor     r9d, r9d; unsigned int *
0x1800bc113  lea     r8, [rsp+348h+var_2A8]; struct _CTAPCBOR_RPC_REQUEST *
0x1800bc11b  lea     rdx, [rsp+348h+var_2F8]; struct _GUID *
0x1800bc120  lea     ecx, [r9+6Bh]; unsigned int
0x1800bc124  call    ?I_EncodeAndSendRpcRequest@@YAJKU_GUID@@AEAU_CTAPCBOR_RPC_REQUEST@@PEAKPEAPEAE@Z; I_EncodeAndSendRpcRequest(ulong,_GUID,_CTAPCBOR_RPC_REQUEST &,ulong *,uchar * *)
0x1800bc129  mov     ebx, eax
0x1800bc12b  mov     rcx, [rsp+348h+var_310]
0x1800bc130  test    rcx, rcx
0x1800bc133  jz      short loc_1800BC182
0x1800bc135  add     rcx, 8
0x1800bc139  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x1800bc13e  test    al, al
0x1800bc140  jz      short loc_1800BC182
0x1800bc142  mov     r9d, ebx
0x1800bc145  shr     r9d, 1Fh
0x1800bc149  lea     rcx, aWebauthnplugin_96; "WebAuthNPluginAuthenticatorRemoveAllCre"...
0x1800bc150  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bc155  mov     r8, rax
0x1800bc158  mov     edx, 1
0x1800bc15d  mov     byte ptr [rsp+348h+var_328], r9b; int
0x1800bc162  mov     r9d, ebx
0x1800bc165  lea     rcx, [rsp+348h+var_310]
0x1800bc16a  call    ??$set_flag_value_if@J@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBDJ_N@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::set_flag_value_if<long>(ushort,char const *,long,bool)
0x1800bc16f  mov     rcx, [rsp+348h+var_310]
0x1800bc174  test    rcx, rcx
0x1800bc177  jz      short loc_1800BC182
0x1800bc179  add     rcx, 8
0x1800bc17d  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::complete_without_lock(void)
0x1800bc182  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1800bc189  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800bc18e  test    al, al
0x1800bc190  jz      short loc_1800BC1D7
0x1800bc192  test    ebx, ebx
0x1800bc194  jns     short loc_1800BC1B3
0x1800bc196  mov     rcx, [rsp+348h]; this
0x1800bc19e  mov     r9d, ebx; char *
0x1800bc1a1  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bc1a8  mov     edx, 0B48h; void *
0x1800bc1ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc1b2  nop
0x1800bc1b3  lea     rcx, [rsp+348h+var_308]
0x1800bc1b8  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(void)
0x1800bc1bd  nop
0x1800bc1be  lea     rcx, [rsp+348h+var_2E8]
0x1800bc1c3  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(void)
0x1800bc1c8  nop
0x1800bc1c9  lea     rcx, [rsp+348h+var_310]
0x1800bc1ce  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>(void)
0x1800bc1d3  mov     eax, ebx
0x1800bc1d5  jmp     short loc_1800BC1FF
0x1800bc1d7  lea     rcx, [rsp+348h+var_308]
0x1800bc1dc  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(void)
0x1800bc1e1  nop
0x1800bc1e2  lea     rcx, [rsp+348h+var_2E8]
0x1800bc1e7  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>>(void)
0x1800bc1ec  nop
0x1800bc1ed  lea     rcx, [rsp+348h+var_310]
0x1800bc1f2  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>(void)
0x1800bc1f7  mov     eax, ebx
0x1800bc1f9  jmp     short loc_1800BC1FF
0x1800bc1fb  mov     eax, dword ptr [rsp+348h+var_310]
0x1800bc1ff  mov     rcx, [rsp+348h+var_18]
0x1800bc207  xor     rcx, rsp; StackCookie
0x1800bc20a  call    __security_check_cookie
0x1800bc20f  mov     rbx, [rsp+348h+arg_8]
0x1800bc217  add     rsp, 340h
0x1800bc21e  pop     rdi
0x1800bc21f  retn
```
