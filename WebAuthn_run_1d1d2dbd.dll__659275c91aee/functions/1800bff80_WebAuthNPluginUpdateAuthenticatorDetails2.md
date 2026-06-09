# WebAuthNPluginUpdateAuthenticatorDetails2

- ea: `0x1800bff80`
- end: `0x1800c04c6`
- name: `WebAuthNPluginUpdateAuthenticatorDetails2`
- size: `1350`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004d970`

## callees

- `0x180022c60`
- `0x180036da4`
- `0x1800467e0`
- `0x180049de0`
- `0x18004f5b4`
- `0x1800537a4`
- `0x18006cfd4`
- `0x18006f7b0`
- `0x180079444`
- `0x18007e064`
- `0x180095468`
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

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c00a8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c0146`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c00a8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c0146`

## string_xrefs

- `0x1800bffc5`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800c002b`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800c00de`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800c017e`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800c0220`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800c03e3`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800c0479`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bfffd`: `WebAuthNPluginUpdateAuthenticatorDetailsTest::reason::remote_session`
- `0x1800c03ad`: `WebAuthNPluginUpdateAuthenticatorDetailsTest::reason::generic_failure`
- `0x1800c00b2`: `WebAuthNPluginUpdateAuthenticatorDetailsTest::reason::invalid_parameters`
- `0x1800c0150`: `WebAuthNPluginUpdateAuthenticatorDetailsTest::reason::invalid_parameters`
- `0x1800c044b`: `WebAuthNPluginUpdateAuthenticatorDetailsTest::reason::invalid_parameters`
- `0x1800c01e8`: `WebAuthNPluginUpdateAuthenticatorDetailsTest::reason::invalid_kcm_key`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall WebAuthNPluginUpdateAuthenticatorDetails2(__int64 *a1)
{
  const char *v3; // rdx
  const char *v4; // rax
  const char *v5; // rdx
  const char *v6; // rax
  const GUID *v7; // rcx
  const char *v8; // rdx
  const char *v9; // rax
  const unsigned __int16 *v10; // rcx
  __int64 v11; // rsi
  __int64 v12; // rax
  const char *v13; // rdx
  const char *v14; // rax
  __int64 v15; // r9
  __int64 v16; // rbx
  __int64 v17; // r8
  __int64 v18; // rdx
  unsigned int v19; // ebx
  const char *v20; // rdx
  const char *v21; // rax
  const char *v22; // rax
  int v23; // [rsp+20h] [rbp-3A8h]
  int v24; // [rsp+20h] [rbp-3A8h]
  bool v25; // [rsp+30h] [rbp-398h] BYREF
  __int64 v26; // [rsp+38h] [rbp-390h] BYREF
  _QWORD v27[2]; // [rsp+40h] [rbp-388h] BYREF
  struct _GUID v28; // [rsp+50h] [rbp-378h] BYREF
  _BYTE v29[64]; // [rsp+60h] [rbp-368h] BYREF
  _BYTE v30[16]; // [rsp+A0h] [rbp-328h] BYREF
  _BYTE v31[248]; // [rsp+B0h] [rbp-318h] BYREF
  __int64 v32; // [rsp+1A8h] [rbp-220h]
  OLECHAR *v33; // [rsp+1B0h] [rbp-218h]
  unsigned __int64 v34; // [rsp+1B8h] [rbp-210h]
  __int64 v35; // [rsp+1C8h] [rbp-200h]
  __int64 v36; // [rsp+1D0h] [rbp-1F8h]
  int v37; // [rsp+248h] [rbp-180h]
  __int64 v38; // [rsp+250h] [rbp-178h]
  int v39; // [rsp+26Ch] [rbp-15Ch]
  __int64 v40; // [rsp+270h] [rbp-158h]
  __int64 v41; // [rsp+2C8h] [rbp-100h]
  OLECHAR sz[40]; // [rsp+2F0h] [rbp-D8h] BYREF
  OLECHAR v43[40]; // [rsp+340h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    v26 = 0;
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::start_and_watch_errors(
      &v26,
      v29);
    if ( ShouldSendRequestToRemoteSession(0) )
    {
      v4 = tip2::details::reason_string(
             (tip2::details *)"WebAuthNPluginUpdateAuthenticatorDetailsTest::reason::remote_session",
             v3);
      tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
        &v26,
        8,
        v4);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x389,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)0x80090029LL,
        v23);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(v29);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(&v26);
      return 2148073513LL;
    }
    else if ( a1 && *a1 && a1[1] && a1[2] )
    {
      memset_0(sz, 0, sizeof(sz));
      if ( StringFromGUID2((const GUID *const)a1[1], sz, 40) )
      {
        memset_0(v43, 0, sizeof(v43));
        v7 = (const GUID *)a1[2];
        if ( *(_QWORD *)&v7->Data1 == *(_QWORD *)&GUID_NULL.Data1 && *(_QWORD *)v7->Data4 == *(_QWORD *)GUID_NULL.Data4
          || StringFromGUID2(v7, v43, 40) )
        {
          v10 = (const unsigned __int16 *)a1[9];
          v11 = -1;
          if ( !v10 )
            goto LABEL_21;
          v12 = -1;
          do
            ++v12;
          while ( v10[v12] );
          if ( v12 && (v25 = 0, IsKcmKeyValid(v10, &v25), !v25) )
          {
            v14 = tip2::details::reason_string(
                    (tip2::details *)"WebAuthNPluginUpdateAuthenticatorDetailsTest::reason::invalid_kcm_key",
                    v13);
            tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::set_flag_value<long>(
              &v26,
              10,
              v14,
              v15);
            tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v26);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3B2,
              (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
              (const char *)0x80090027LL,
              v23);
            tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(v29);
            wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(&v26);
            return 2148073511LL;
          }
          else
          {
LABEL_21:
            memset_0(v31, 0, 0x238u);
            v32 = *a1;
            v33 = sz;
            v34 = (unsigned __int64)v43 & -(__int64)(v43[0] != 0);
            v35 = a1[3];
            v36 = a1[4];
            v37 = *((_DWORD *)a1 + 10);
            v38 = a1[6];
            v39 = *((_DWORD *)a1 + 14);
            v40 = a1[8];
            v41 = a1[9];
            tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::data(
              &v26,
              v27);
            v16 = v27[0];
            v17 = -1;
            do
              ++v17;
            while ( sz[v17] );
            std::wstring::_Assign<unsigned short>(v27[0] + 272LL, sz);
            v18 = *a1;
            do
              ++v11;
            while ( *(_WORD *)(v18 + 2 * v11) );
            std::wstring::_Assign<unsigned short>(v16 + 304, v18);
            tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::close(v27);
            v28 = *(struct _GUID *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(
                                     &v26,
                                     v30);
            v19 = I_EncodeAndSendRpcRequest(0x66u, &v28, (struct _CTAPCBOR_RPC_REQUEST *)v31, 0, 0);
            if ( (v19 & 0x80000000) == 0 )
            {
              tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v26);
              tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(v27);
              tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(v29);
              wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(&v26);
              return 0;
            }
            else
            {
              if ( v26 )
              {
                if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v26 + 8) )
                {
                  v21 = tip2::details::reason_string(
                          (tip2::details *)"WebAuthNPluginUpdateAuthenticatorDetailsTest::reason::generic_failure",
                          v20);
                  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::set_flag_value<long>(
                    &v26,
                    1,
                    v21,
                    v19);
                  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v26);
                }
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x3CF,
                (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
                (const char *)v19,
                v24);
              tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(v27);
              tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(v29);
              wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(&v26);
              return v19;
            }
          }
        }
        else
        {
          v9 = tip2::details::reason_string(
                 (tip2::details *)"WebAuthNPluginUpdateAuthenticatorDetailsTest::reason::invalid_parameters",
                 v8);
          tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
            &v26,
            2,
            v9);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3A4,
            (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
            (const char *)0x80090027LL,
            v23);
          tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(v29);
          wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(&v26);
          return 2148073511LL;
        }
      }
      else
      {
        v6 = tip2::details::reason_string(
               (tip2::details *)"WebAuthNPluginUpdateAuthenticatorDetailsTest::reason::invalid_parameters",
               v5);
        tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
          &v26,
          2,
          v6);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x39A,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
          (const char *)0x80090027LL,
          v23);
        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(v29);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(&v26);
        return 2148073511LL;
      }
    }
    else
    {
      v22 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginUpdateAuthenticatorDetailsTest::reason::invalid_parameters",
              v3);
      tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
        &v26,
        2,
        v22);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x392,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)0x80090027LL,
        v23);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(v29);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(&v26);
      return 2148073511LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x381,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80004001LL,
      v23);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x1800bff80  push    rbx
0x1800bff82  push    rsi
0x1800bff83  push    rdi
0x1800bff84  push    r14
0x1800bff86  sub     rsp, 3A8h
0x1800bff8d  mov     rax, cs:__security_cookie
0x1800bff94  xor     rax, rsp
0x1800bff97  mov     [rsp+3C8h+var_38], rax
0x1800bff9f  mov     rdi, rcx
0x1800bffa2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1800bffa9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800bffae  xor     r14d, r14d
0x1800bffb1  test    al, al
0x1800bffb3  jnz     short loc_1800BFFDD
0x1800bffb5  mov     rcx, [rsp+3C8h]; this
0x1800bffbd  mov     ebx, 80004001h
0x1800bffc2  mov     r9d, ebx; char *
0x1800bffc5  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bffcc  mov     edx, 381h; void *
0x1800bffd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bffd6  mov     eax, ebx
0x1800bffd8  jmp     loc_1800C04A8
0x1800bffdd  mov     [rsp+3C8h+var_390], r14
0x1800bffe2  lea     rdx, [rsp+3C8h+var_368]
0x1800bffe7  lea     rcx, [rsp+3C8h+var_390]
0x1800bffec  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::start_and_watch_errors(void)
0x1800bfff1  nop
0x1800bfff2  xor     ecx, ecx; unsigned __int8 *
0x1800bfff4  call    ?ShouldSendRequestToRemoteSession@@YA_NPEAE@Z; ShouldSendRequestToRemoteSession(uchar *)
0x1800bfff9  test    al, al
0x1800bfffb  jz      short loc_1800C0059
0x1800bfffd  lea     rcx, aWebauthnplugin_103; "WebAuthNPluginUpdateAuthenticatorDetail"...
0x1800c0004  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800c0009  mov     r8, rax
0x1800c000c  mov     edx, 8
0x1800c0011  lea     rcx, [rsp+3C8h+var_390]
0x1800c0016  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800c001b  mov     rcx, [rsp+3C8h]; this
0x1800c0023  mov     ebx, 80090029h
0x1800c0028  mov     r9d, ebx; char *
0x1800c002b  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800c0032  mov     edx, 389h; void *
0x1800c0037  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c003c  nop
0x1800c003d  lea     rcx, [rsp+3C8h+var_368]
0x1800c0042  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(void)
0x1800c0047  nop
0x1800c0048  lea     rcx, [rsp+3C8h+var_390]
0x1800c004d  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(void)
0x1800c0052  mov     eax, ebx
0x1800c0054  jmp     loc_1800C04A8
0x1800c0059  test    rdi, rdi
0x1800c005c  jz      loc_1800C044B
0x1800c0062  cmp     [rdi], r14
0x1800c0065  jz      loc_1800C044B
0x1800c006b  cmp     [rdi+8], r14
0x1800c006f  jz      loc_1800C044B
0x1800c0075  cmp     [rdi+10h], r14
0x1800c0079  jz      loc_1800C044B
0x1800c007f  mov     esi, 50h ; 'P'
0x1800c0084  mov     r8d, esi; Size
0x1800c0087  xor     edx, edx; Val
0x1800c0089  lea     rcx, [rsp+3C8h+sz]; void *
0x1800c0091  call    memset_0
0x1800c0096  lea     ebx, [rsi-28h]
0x1800c0099  mov     r8d, ebx; cchMax
0x1800c009c  lea     rdx, [rsp+3C8h+sz]; lpsz
0x1800c00a4  mov     rcx, [rdi+8]; rguid
0x1800c00a8  call    cs:__imp_StringFromGUID2
0x1800c00ae  test    eax, eax
0x1800c00b0  jnz     short loc_1800C010C
0x1800c00b2  lea     rcx, aWebauthnplugin_76; "WebAuthNPluginUpdateAuthenticatorDetail"...
0x1800c00b9  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800c00be  mov     r8, rax
0x1800c00c1  lea     edx, [rsi-4Eh]
0x1800c00c4  lea     rcx, [rsp+3C8h+var_390]
0x1800c00c9  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800c00ce  mov     rcx, [rsp+3C8h]; this
0x1800c00d6  mov     ebx, 80090027h
0x1800c00db  mov     r9d, ebx; char *
0x1800c00de  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800c00e5  mov     edx, 39Ah; void *
0x1800c00ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c00ef  nop
0x1800c00f0  lea     rcx, [rsp+3C8h+var_368]
0x1800c00f5  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(void)
0x1800c00fa  nop
0x1800c00fb  lea     rcx, [rsp+3C8h+var_390]
0x1800c0100  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(void)
0x1800c0105  mov     eax, ebx
0x1800c0107  jmp     loc_1800C04A8
0x1800c010c  mov     r8, rsi; Size
0x1800c010f  xor     edx, edx; Val
0x1800c0111  lea     rcx, [rsp+3C8h+var_88]; void *
0x1800c0119  call    memset_0
0x1800c011e  mov     rcx, [rdi+10h]; rguid
0x1800c0122  mov     rax, [rcx]
0x1800c0125  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800c012c  jnz     short loc_1800C013B
0x1800c012e  mov     rax, [rcx+8]
0x1800c0132  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800c0139  jz      short loc_1800C01AC
0x1800c013b  mov     r8d, ebx; cchMax
0x1800c013e  lea     rdx, [rsp+3C8h+var_88]; lpsz
0x1800c0146  call    cs:__imp_StringFromGUID2
0x1800c014c  test    eax, eax
0x1800c014e  jnz     short loc_1800C01AC
0x1800c0150  lea     rcx, aWebauthnplugin_76; "WebAuthNPluginUpdateAuthenticatorDetail"...
0x1800c0157  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800c015c  mov     r8, rax
0x1800c015f  mov     edx, 2
0x1800c0164  lea     rcx, [rsp+3C8h+var_390]
0x1800c0169  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800c016e  mov     rcx, [rsp+3C8h]; this
0x1800c0176  mov     ebx, 80090027h
0x1800c017b  mov     r9d, ebx; char *
0x1800c017e  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800c0185  mov     edx, 3A4h; void *
0x1800c018a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c018f  nop
0x1800c0190  lea     rcx, [rsp+3C8h+var_368]
0x1800c0195  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(void)
0x1800c019a  nop
0x1800c019b  lea     rcx, [rsp+3C8h+var_390]
0x1800c01a0  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(void)
0x1800c01a5  mov     eax, ebx
0x1800c01a7  jmp     loc_1800C04A8
0x1800c01ac  mov     rcx, [rdi+48h]; unsigned __int16 *
0x1800c01b0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800c01b4  test    rcx, rcx
0x1800c01b7  jz      loc_1800C024E
0x1800c01bd  mov     rax, rsi
0x1800c01c0  inc     rax
0x1800c01c3  cmp     [rcx+rax*2], r14w
0x1800c01c8  jnz     short loc_1800C01C0
0x1800c01ca  test    rax, rax
0x1800c01cd  jz      short loc_1800C024E
0x1800c01cf  mov     [rsp+3C8h+var_398], r14b
0x1800c01d4  lea     rdx, [rsp+3C8h+var_398]; bool *
0x1800c01d9  call    ?IsKcmKeyValid@@YAJPEBGAEA_N@Z; IsKcmKeyValid(ushort const *,bool &)
0x1800c01de  mov     r9d, eax
0x1800c01e1  cmp     [rsp+3C8h+var_398], r14b
0x1800c01e6  jnz     short loc_1800C024E
0x1800c01e8  lea     rcx, aWebauthnplugin_74; "WebAuthNPluginUpdateAuthenticatorDetail"...
0x1800c01ef  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800c01f4  mov     r8, rax
0x1800c01f7  mov     edx, 0Ah
0x1800c01fc  lea     rcx, [rsp+3C8h+var_390]
0x1800c0201  call    ??$set_flag_value@J@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBDJ@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::set_flag_value<long>(ushort,char const *,long)
0x1800c0206  lea     rcx, [rsp+3C8h+var_390]
0x1800c020b  call    ?complete@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(void)
0x1800c0210  mov     rcx, [rsp+3C8h]; this
0x1800c0218  mov     ebx, 80090027h
0x1800c021d  mov     r9d, ebx; char *
0x1800c0220  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800c0227  mov     edx, 3B2h; void *
0x1800c022c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0231  nop
0x1800c0232  lea     rcx, [rsp+3C8h+var_368]
0x1800c0237  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(void)
0x1800c023c  nop
0x1800c023d  lea     rcx, [rsp+3C8h+var_390]
0x1800c0242  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(void)
0x1800c0247  mov     eax, ebx
0x1800c0249  jmp     loc_1800C04A8
0x1800c024e  xor     edx, edx; Val
0x1800c0250  mov     r8d, 238h; Size
0x1800c0256  lea     rcx, [rsp+3C8h+var_318]; void *
0x1800c025e  call    memset_0
0x1800c0263  mov     rax, [rdi]
0x1800c0266  mov     [rsp+3C8h+var_220], rax
0x1800c026e  lea     rax, [rsp+3C8h+sz]
0x1800c0276  mov     [rsp+3C8h+var_218], rax
0x1800c027e  movzx   eax, [rsp+3C8h+var_88]
0x1800c0286  neg     ax
0x1800c0289  sbb     rcx, rcx
0x1800c028c  lea     rax, [rsp+3C8h+var_88]
0x1800c0294  and     rcx, rax
0x1800c0297  mov     [rsp+3C8h+var_210], rcx
0x1800c029f  mov     rax, [rdi+18h]
0x1800c02a3  mov     [rsp+3C8h+var_200], rax
0x1800c02ab  mov     rax, [rdi+20h]
0x1800c02af  mov     [rsp+3C8h+var_1F8], rax
0x1800c02b7  mov     eax, [rdi+28h]
0x1800c02ba  mov     [rsp+3C8h+var_180], eax
0x1800c02c1  mov     rax, [rdi+30h]
0x1800c02c5  mov     [rsp+3C8h+var_178], rax
0x1800c02cd  mov     eax, [rdi+38h]
0x1800c02d0  mov     [rsp+3C8h+var_15C], eax
0x1800c02d7  mov     rax, [rdi+40h]
0x1800c02db  mov     [rsp+3C8h+var_158], rax
0x1800c02e3  mov     rax, [rdi+48h]
0x1800c02e7  mov     [rsp+3C8h+var_100], rax
0x1800c02ef  lea     rdx, [rsp+3C8h+var_388]
0x1800c02f4  lea     rcx, [rsp+3C8h+var_390]
0x1800c02f9  call    ?data@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::data(void)
0x1800c02fe  nop
0x1800c02ff  mov     rbx, [rsp+3C8h+var_388]
0x1800c0304  lea     rcx, [rbx+110h]
0x1800c030b  lea     rax, [rsp+3C8h+sz]
0x1800c0313  mov     r8, rsi
0x1800c0316  inc     r8
0x1800c0319  cmp     [rax+r8*2], r14w
0x1800c031e  jnz     short loc_1800C0316
0x1800c0320  lea     rdx, [rsp+3C8h+sz]
0x1800c0328  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800c032d  mov     rdx, [rdi]
0x1800c0330  lea     rcx, [rbx+130h]
0x1800c0337  inc     rsi
0x1800c033a  cmp     [rdx+rsi*2], r14w
0x1800c033f  jnz     short loc_1800C0337
0x1800c0341  mov     r8, rsi
0x1800c0344  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800c0349  lea     rcx, [rsp+3C8h+var_388]
0x1800c034e  call    ?close@?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::close(void)
0x1800c0353  lea     rdx, [rsp+3C8h+var_328]
0x1800c035b  lea     rcx, [rsp+3C8h+var_390]
0x1800c0360  call    ?test_id@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEBA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(void)
0x1800c0365  movups  xmm1, xmmword ptr [rax]
0x1800c0368  movdqu  xmmword ptr [rsp+3C8h+var_378.Data1], xmm1
0x1800c036e  mov     qword ptr [rsp+3C8h+var_3A8], r14; int
0x1800c0373  xor     r9d, r9d; unsigned int *
0x1800c0376  lea     r8, [rsp+3C8h+var_318]; struct _CTAPCBOR_RPC_REQUEST *
0x1800c037e  lea     rdx, [rsp+3C8h+var_378]; struct _GUID *
0x1800c0383  lea     ecx, [r9+66h]; unsigned int
0x1800c0387  call    ?I_EncodeAndSendRpcRequest@@YAJKU_GUID@@AEAU_CTAPCBOR_RPC_REQUEST@@PEAKPEAPEAE@Z; I_EncodeAndSendRpcRequest(ulong,_GUID,_CTAPCBOR_RPC_REQUEST &,ulong *,uchar * *)
0x1800c038c  mov     ebx, eax
0x1800c038e  test    eax, eax
0x1800c0390  jns     loc_1800C041C
0x1800c0396  mov     rcx, [rsp+3C8h+var_390]
0x1800c039b  test    rcx, rcx
0x1800c039e  jz      short loc_1800C03D8
0x1800c03a0  add     rcx, 8
0x1800c03a4  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x1800c03a9  test    al, al
0x1800c03ab  jz      short loc_1800C03D8
0x1800c03ad  lea     rcx, aWebauthnplugin_57; "WebAuthNPluginUpdateAuthenticatorDetail"...
0x1800c03b4  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800c03b9  mov     r8, rax
0x1800c03bc  mov     edx, 1
0x1800c03c1  mov     r9d, ebx
0x1800c03c4  lea     rcx, [rsp+3C8h+var_390]
0x1800c03c9  call    ??$set_flag_value@J@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBDJ@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::set_flag_value<long>(ushort,char const *,long)
0x1800c03ce  lea     rcx, [rsp+3C8h+var_390]
0x1800c03d3  call    ?complete@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(void)
0x1800c03d8  mov     rcx, [rsp+3C8h]; this
0x1800c03e0  mov     r9d, ebx; char *
0x1800c03e3  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800c03ea  mov     edx, 3CFh; void *
0x1800c03ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c03f4  nop
0x1800c03f5  lea     rcx, [rsp+3C8h+var_388]
0x1800c03fa  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(void)
0x1800c03ff  nop
0x1800c0400  lea     rcx, [rsp+3C8h+var_368]
0x1800c0405  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(void)
0x1800c040a  nop
0x1800c040b  lea     rcx, [rsp+3C8h+var_390]
0x1800c0410  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(void)
0x1800c0415  mov     eax, ebx
0x1800c0417  jmp     loc_1800C04A8
0x1800c041c  lea     rcx, [rsp+3C8h+var_390]
0x1800c0421  call    ?complete@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(void)
0x1800c0426  nop
0x1800c0427  lea     rcx, [rsp+3C8h+var_388]
0x1800c042c  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(void)
0x1800c0431  nop
0x1800c0432  lea     rcx, [rsp+3C8h+var_368]
0x1800c0437  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(void)
0x1800c043c  nop
0x1800c043d  lea     rcx, [rsp+3C8h+var_390]
0x1800c0442  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(void)
0x1800c0447  xor     eax, eax
0x1800c0449  jmp     short loc_1800C04A8
0x1800c044b  lea     rcx, aWebauthnplugin_76; "WebAuthNPluginUpdateAuthenticatorDetail"...
0x1800c0452  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800c0457  mov     r8, rax
0x1800c045a  mov     edx, 2
0x1800c045f  lea     rcx, [rsp+3C8h+var_390]
0x1800c0464  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800c0469  mov     rcx, [rsp+3C8h]; this
0x1800c0471  mov     ebx, 80090027h
0x1800c0476  mov     r9d, ebx; char *
0x1800c0479  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800c0480  mov     edx, 392h; void *
0x1800c0485  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c048a  nop
0x1800c048b  lea     rcx, [rsp+3C8h+var_368]
0x1800c0490  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>>(void)
0x1800c0495  nop
0x1800c0496  lea     rcx, [rsp+3C8h+var_390]
0x1800c049b  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(void)
0x1800c04a0  mov     eax, ebx
0x1800c04a2  jmp     short loc_1800C04A8
0x1800c04a4  mov     eax, dword ptr [rsp+3C8h+var_390]
0x1800c04a8  mov     rcx, [rsp+3C8h+var_38]
0x1800c04b0  xor     rcx, rsp; StackCookie
0x1800c04b3  call    __security_check_cookie
0x1800c04b8  add     rsp, 3A8h
0x1800c04bf  pop     r14
  ... truncated ...
```
