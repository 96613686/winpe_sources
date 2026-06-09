# WebAuthNPluginRemoveAuthenticator

- ea: `0x1800bf5c0`
- end: `0x1800bf94b`
- name: `WebAuthNPluginRemoveAuthenticator`
- size: `907`
- prototype: `__int64 __fastcall(GUID *rguid)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180036da4`
- `0x1800467e0`
- `0x18004685c`
- `0x180049de0`
- `0x18004f5b4`
- `0x1800537a4`
- `0x180055188`
- `0x18006cfd4`
- `0x18006f7b0`
- `0x180079444`
- `0x18007e064`
- `0x180095468`
- `0x1800b1394`
- `0x1800b2624`
- `0x1800b29dc`
- `0x1800b2f30`
- `0x1800b30dc`
- `0x1800b4170`
- `0x1800b5184`
- `0x1800b57b8`
- `0x1800b7da0`
- `0x1800bf5c0`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bf76a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bf76a`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x1800bf6d9`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x1800bf6d9`

## string_xrefs

- `0x1800bf604`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bf698`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bf718`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bf7a2`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bf8c0`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bf774`: `WebAuthNPluginRemoveAuthenticatorTest::reason::invalid_parameters`
- `0x1800bf66a`: `WebAuthNPluginRemoveAuthenticatorTest::reason::remote_session`
- `0x1800bf6ea`: `WebAuthNPluginRemoveAuthenticatorTest::reason::remote_session`
- `0x1800bf88a`: `WebAuthNPluginRemoveAuthenticatorTest::reason::generic_failure`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall WebAuthNPluginRemoveAuthenticator(GUID *rguid, __int64 a2, __int64 a3)
{
  const char *v5; // rdx
  const char *v6; // rax
  const char *v7; // rdx
  const char *v8; // rax
  const char *v9; // rdx
  const char *v10; // rax
  __int64 v11; // rax
  __int64 v12; // r8
  unsigned int v13; // ebx
  const char *v14; // rdx
  const char *v15; // rax
  int v16; // [rsp+20h] [rbp-328h]
  int v17; // [rsp+20h] [rbp-328h]
  _BYTE v18[8]; // [rsp+30h] [rbp-318h] BYREF
  __int64 v19; // [rsp+38h] [rbp-310h] BYREF
  _QWORD v20[2]; // [rsp+40h] [rbp-308h] BYREF
  struct _GUID v21; // [rsp+50h] [rbp-2F8h] BYREF
  _BYTE v22[64]; // [rsp+60h] [rbp-2E8h] BYREF
  _BYTE v23[256]; // [rsp+A0h] [rbp-2A8h] BYREF
  OLECHAR *v24; // [rsp+1A0h] [rbp-1A8h]
  OLECHAR sz[40]; // [rsp+2E0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+0h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(
                           `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl,
                           a2,
                           a3) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9EC,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80004001LL,
      v16);
    return 2147500033LL;
  }
  v19 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::start_and_watch_errors(
    &v19,
    v22);
  v18[0] = 0;
  memset_0(v23, 0, 0x238u);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    if ( ShouldSendRequestToRemoteSession(0) )
    {
      v6 = tip2::details::reason_string(
             (tip2::details *)"WebAuthNPluginRemoveAuthenticatorTest::reason::remote_session",
             v5);
      tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
        &v19,
        7,
        v6);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9F9,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)0x80090029LL,
        v16);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(v22);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>(&v19);
      return 2148073513LL;
    }
  }
  else if ( (unsigned __int8)IsWinStationIsSessionRemoteablePresent()
         && (unsigned __int8)WinStationIsSessionRemoteable(0, 0xFFFFFFFFLL, v18)
         && v18[0] )
  {
    v8 = tip2::details::reason_string(
           (tip2::details *)"WebAuthNPluginRemoveAuthenticatorTest::reason::remote_session",
           v7);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      &v19,
      7,
      v8);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA02,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090029LL,
      v16);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(v22);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>(&v19);
    return 2148073513LL;
  }
  memset_0(sz, 0, sizeof(sz));
  if ( StringFromGUID2(rguid, sz, 40) )
  {
    v24 = sz;
    v11 = tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::ensure_data(&v19);
    tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(
      v20,
      v11);
    v12 = -1;
    do
      ++v12;
    while ( sz[v12] );
    std::wstring::_Assign<unsigned short>(v20[0] + 272LL, sz);
    tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::close(v20);
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(
      &v19,
      &v21);
    v13 = I_EncodeAndSendRpcRequest(0x65u, &v21, (struct _CTAPCBOR_RPC_REQUEST *)v23, 0, 0);
    if ( (v13 & 0x80000000) == 0 )
    {
      tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v19);
      tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(v20);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(v22);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>(&v19);
      return 0;
    }
    else
    {
      if ( v19 )
      {
        if ( tip2::details::shared_data<1,0,0>::is_running(v19 + 8) )
        {
          v15 = tip2::details::reason_string(
                  (tip2::details *)"WebAuthNPluginRemoveAuthenticatorTest::reason::generic_failure",
                  v14);
          tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::set_flag_value<long>(
            &v19,
            1,
            v15,
            v13);
          tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v19);
        }
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA1D,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)v13,
        v17);
      tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(v20);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(v22);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>(&v19);
      return v13;
    }
  }
  else
  {
    v10 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginRemoveAuthenticatorTest::reason::invalid_parameters",
            v9);
    tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
      &v19,
      2,
      v10);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80090027LL,
      v16);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(v22);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>(&v19);
    return 2148073511LL;
  }
}

```

## disassembly

```asm
0x1800bf5c0  mov     [rsp+arg_8], rbx
0x1800bf5c5  push    rdi
0x1800bf5c6  sub     rsp, 340h
0x1800bf5cd  mov     rax, cs:__security_cookie
0x1800bf5d4  xor     rax, rsp
0x1800bf5d7  mov     [rsp+348h+var_18], rax
0x1800bf5df  mov     rbx, rcx
0x1800bf5e2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators> `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl(void)'::`2'::impl
0x1800bf5e9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(void)
0x1800bf5ee  xor     edi, edi
0x1800bf5f0  test    al, al
0x1800bf5f2  jnz     short loc_1800BF61C
0x1800bf5f4  mov     rcx, [rsp+348h]; this
0x1800bf5fc  mov     ebx, 80004001h
0x1800bf601  mov     r9d, ebx; char *
0x1800bf604  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bf60b  mov     edx, 9ECh; void *
0x1800bf610  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf615  mov     eax, ebx
0x1800bf617  jmp     loc_1800BF929
0x1800bf61c  mov     [rsp+348h+var_310], rdi
0x1800bf621  lea     rdx, [rsp+348h+var_2E8]
0x1800bf626  lea     rcx, [rsp+348h+var_310]
0x1800bf62b  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::start_and_watch_errors(void)
0x1800bf630  nop
0x1800bf631  mov     [rsp+348h+var_318], dil
0x1800bf636  xor     edx, edx; Val
0x1800bf638  mov     r8d, 238h; Size
0x1800bf63e  lea     rcx, [rsp+348h+var_2A8]; void *
0x1800bf646  call    memset_0
0x1800bf64b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1800bf652  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800bf657  test    al, al
0x1800bf659  jz      short loc_1800BF6C6
0x1800bf65b  xor     ecx, ecx; unsigned __int8 *
0x1800bf65d  call    ?ShouldSendRequestToRemoteSession@@YA_NPEAE@Z; ShouldSendRequestToRemoteSession(uchar *)
0x1800bf662  test    al, al
0x1800bf664  jz      loc_1800BF746
0x1800bf66a  lea     rcx, aWebauthnplugin_121; "WebAuthNPluginRemoveAuthenticatorTest::"...
0x1800bf671  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bf676  mov     r8, rax
0x1800bf679  mov     edx, 7
0x1800bf67e  lea     rcx, [rsp+348h+var_310]
0x1800bf683  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bf688  mov     rcx, [rsp+348h]; this
0x1800bf690  mov     ebx, 80090029h
0x1800bf695  mov     r9d, ebx; char *
0x1800bf698  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bf69f  mov     edx, 9F9h; void *
0x1800bf6a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf6a9  nop
0x1800bf6aa  lea     rcx, [rsp+348h+var_2E8]
0x1800bf6af  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(void)
0x1800bf6b4  nop
0x1800bf6b5  lea     rcx, [rsp+348h+var_310]
0x1800bf6ba  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>(void)
0x1800bf6bf  mov     eax, ebx
0x1800bf6c1  jmp     loc_1800BF929
0x1800bf6c6  call    IsWinStationIsSessionRemoteablePresent
0x1800bf6cb  test    al, al
0x1800bf6cd  jz      short loc_1800BF746
0x1800bf6cf  lea     r8, [rsp+348h+var_318]
0x1800bf6d4  or      edx, 0FFFFFFFFh
0x1800bf6d7  xor     ecx, ecx
0x1800bf6d9  call    cs:__imp_WinStationIsSessionRemoteable
0x1800bf6df  test    al, al
0x1800bf6e1  jz      short loc_1800BF746
0x1800bf6e3  cmp     [rsp+348h+var_318], dil
0x1800bf6e8  jz      short loc_1800BF746
0x1800bf6ea  lea     rcx, aWebauthnplugin_121; "WebAuthNPluginRemoveAuthenticatorTest::"...
0x1800bf6f1  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bf6f6  mov     r8, rax
0x1800bf6f9  mov     edx, 7
0x1800bf6fe  lea     rcx, [rsp+348h+var_310]
0x1800bf703  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bf708  mov     rcx, [rsp+348h]; this
0x1800bf710  mov     ebx, 80090029h
0x1800bf715  mov     r9d, ebx; char *
0x1800bf718  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bf71f  mov     edx, 0A02h; void *
0x1800bf724  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf729  nop
0x1800bf72a  lea     rcx, [rsp+348h+var_2E8]
0x1800bf72f  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(void)
0x1800bf734  nop
0x1800bf735  lea     rcx, [rsp+348h+var_310]
0x1800bf73a  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>(void)
0x1800bf73f  mov     eax, ebx
0x1800bf741  jmp     loc_1800BF929
0x1800bf746  xor     edx, edx; Val
0x1800bf748  lea     r8d, [rdx+50h]; Size
0x1800bf74c  lea     rcx, [rsp+348h+sz]; void *
0x1800bf754  call    memset_0
0x1800bf759  mov     r8d, 28h ; '('; cchMax
0x1800bf75f  lea     rdx, [rsp+348h+sz]; lpsz
0x1800bf767  mov     rcx, rbx; rguid
0x1800bf76a  call    cs:__imp_StringFromGUID2
0x1800bf770  test    eax, eax
0x1800bf772  jnz     short loc_1800BF7D0
0x1800bf774  lea     rcx, aWebauthnplugin_80; "WebAuthNPluginRemoveAuthenticatorTest::"...
0x1800bf77b  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bf780  mov     r8, rax
0x1800bf783  mov     edx, 2
0x1800bf788  lea     rcx, [rsp+348h+var_310]
0x1800bf78d  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bf792  mov     rcx, [rsp+348h]; this
0x1800bf79a  mov     ebx, 80090027h
0x1800bf79f  mov     r9d, ebx; char *
0x1800bf7a2  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bf7a9  mov     edx, 0A0Bh; void *
0x1800bf7ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf7b3  nop
0x1800bf7b4  lea     rcx, [rsp+348h+var_2E8]
0x1800bf7b9  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(void)
0x1800bf7be  nop
0x1800bf7bf  lea     rcx, [rsp+348h+var_310]
0x1800bf7c4  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>(void)
0x1800bf7c9  mov     eax, ebx
0x1800bf7cb  jmp     loc_1800BF929
0x1800bf7d0  lea     rax, [rsp+348h+sz]
0x1800bf7d8  mov     [rsp+348h+var_1A8], rax
0x1800bf7e0  lea     rcx, [rsp+348h+var_310]
0x1800bf7e5  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::ensure_data(void)
0x1800bf7ea  mov     rdx, rax
0x1800bf7ed  lea     rcx, [rsp+348h+var_308]
0x1800bf7f2  call    ??0?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy> const &)
0x1800bf7f7  nop
0x1800bf7f8  mov     rcx, [rsp+348h+var_308]
0x1800bf7fd  add     rcx, 110h
0x1800bf804  lea     rax, [rsp+348h+sz]
0x1800bf80c  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800bf810  inc     r8
0x1800bf813  cmp     [rax+r8*2], di
0x1800bf818  jnz     short loc_1800BF810
0x1800bf81a  lea     rdx, [rsp+348h+sz]
0x1800bf822  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800bf827  lea     rcx, [rsp+348h+var_308]
0x1800bf82c  call    ?close@?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::close(void)
0x1800bf831  lea     rdx, [rsp+348h+var_2F8]
0x1800bf836  lea     rcx, [rsp+348h+var_310]
0x1800bf83b  call    ?test_id@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEBA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(void)
0x1800bf840  movaps  xmm1, xmmword ptr [rsp+348h+var_2F8.Data1]
0x1800bf845  movdqa  xmmword ptr [rsp+348h+var_2F8.Data1], xmm1
0x1800bf84b  mov     qword ptr [rsp+348h+var_328], rdi; int
0x1800bf850  xor     r9d, r9d; unsigned int *
0x1800bf853  lea     r8, [rsp+348h+var_2A8]; struct _CTAPCBOR_RPC_REQUEST *
0x1800bf85b  lea     rdx, [rsp+348h+var_2F8]; struct _GUID *
0x1800bf860  lea     ecx, [r9+65h]; unsigned int
0x1800bf864  call    ?I_EncodeAndSendRpcRequest@@YAJKU_GUID@@AEAU_CTAPCBOR_RPC_REQUEST@@PEAKPEAPEAE@Z; I_EncodeAndSendRpcRequest(ulong,_GUID,_CTAPCBOR_RPC_REQUEST &,ulong *,uchar * *)
0x1800bf869  mov     ebx, eax
0x1800bf86b  test    eax, eax
0x1800bf86d  jns     loc_1800BF8F6
0x1800bf873  mov     rcx, [rsp+348h+var_310]
0x1800bf878  test    rcx, rcx
0x1800bf87b  jz      short loc_1800BF8B5
0x1800bf87d  add     rcx, 8
0x1800bf881  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x1800bf886  test    al, al
0x1800bf888  jz      short loc_1800BF8B5
0x1800bf88a  lea     rcx, aWebauthnplugin_65; "WebAuthNPluginRemoveAuthenticatorTest::"...
0x1800bf891  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bf896  mov     r8, rax
0x1800bf899  mov     edx, 1
0x1800bf89e  mov     r9d, ebx
0x1800bf8a1  lea     rcx, [rsp+348h+var_310]
0x1800bf8a6  call    ??$set_flag_value@J@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBDJ@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::set_flag_value<long>(ushort,char const *,long)
0x1800bf8ab  lea     rcx, [rsp+348h+var_310]
0x1800bf8b0  call    ?complete@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(void)
0x1800bf8b5  mov     rcx, [rsp+348h]; this
0x1800bf8bd  mov     r9d, ebx; char *
0x1800bf8c0  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bf8c7  mov     edx, 0A1Dh; void *
0x1800bf8cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf8d1  nop
0x1800bf8d2  lea     rcx, [rsp+348h+var_308]
0x1800bf8d7  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(void)
0x1800bf8dc  nop
0x1800bf8dd  lea     rcx, [rsp+348h+var_2E8]
0x1800bf8e2  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(void)
0x1800bf8e7  nop
0x1800bf8e8  lea     rcx, [rsp+348h+var_310]
0x1800bf8ed  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>(void)
0x1800bf8f2  mov     eax, ebx
0x1800bf8f4  jmp     short loc_1800BF929
0x1800bf8f6  lea     rcx, [rsp+348h+var_310]
0x1800bf8fb  call    ?complete@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(void)
0x1800bf900  nop
0x1800bf901  lea     rcx, [rsp+348h+var_308]
0x1800bf906  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(void)
0x1800bf90b  nop
0x1800bf90c  lea     rcx, [rsp+348h+var_2E8]
0x1800bf911  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>>(void)
0x1800bf916  nop
0x1800bf917  lea     rcx, [rsp+348h+var_310]
0x1800bf91c  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>(void)
0x1800bf921  xor     eax, eax
0x1800bf923  jmp     short loc_1800BF929
0x1800bf925  mov     eax, dword ptr [rsp+348h+var_310]
0x1800bf929  mov     rcx, [rsp+348h+var_18]
0x1800bf931  xor     rcx, rsp; StackCookie
0x1800bf934  call    __security_check_cookie
0x1800bf939  mov     rbx, [rsp+348h+arg_8]
0x1800bf941  add     rsp, 340h
0x1800bf948  pop     rdi
0x1800bf949  retn
```
