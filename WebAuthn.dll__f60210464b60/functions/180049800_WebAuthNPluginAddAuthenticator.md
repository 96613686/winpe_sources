# WebAuthNPluginAddAuthenticator

- ea: `0x180049800`
- end: `0x180049db5`
- name: `WebAuthNPluginAddAuthenticator`
- size: `1461`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180036da4`
- `0x1800467e0`
- `0x18004685c`
- `0x180049800`
- `0x180049dbc`
- `0x180049de0`
- `0x180049e00`
- `0x180049e1c`
- `0x18004d8f4`
- `0x18004f5b4`
- `0x18005378c`
- `0x1800537a4`
- `0x180055188`
- `0x18006cfd4`
- `0x18006f7b0`
- `0x180079444`
- `0x18007e064`
- `0x180092728`
- `0x1800b12bc`
- `0x1800b4170`
- `0x1800b5004`
- `0x1800b5214`
- `0x1800b7a3c`
- `0x1800bb110`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049c16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049c2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049c16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049c2c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180049995`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180049995`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x1800498d9`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x1800498d9`

## string_xrefs

- `0x180049851`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x180049918`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800499cd`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x180049b6d`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x180049c8b`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x180049cdc`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x18004999f`: `WebAuthNPluginAddAuthenticatorTest::reason::invalid_parameters`
- `0x180049c5d`: `WebAuthNPluginAddAuthenticatorTest::reason::invalid_parameters`
- `0x1800498ea`: `WebAuthNPluginAddAuthenticatorTest::reason::remote_session`
- `0x180049b37`: `WebAuthNPluginAddAuthenticatorTest::reason::generic_failure`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall WebAuthNPluginAddAuthenticator(__int64 a1, _QWORD *a2, __int64 a3)
{
  const char *v6; // rdx
  const char *v7; // rax
  const char *v8; // rdx
  const char *v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rsi
  __int64 v12; // r8
  __int64 v13; // rdx
  unsigned int v14; // ebx
  const char *v15; // rdx
  const char *v16; // rax
  unsigned int v17; // ebx
  HLOCAL v18; // rcx
  HLOCAL v19; // rax
  HLOCAL v20; // rcx
  HLOCAL v21; // rcx
  const char *v22; // rax
  int v23; // [rsp+20h] [rbp-368h]
  int v24; // [rsp+20h] [rbp-368h]
  _BYTE v25[8]; // [rsp+30h] [rbp-358h] BYREF
  __int64 v26; // [rsp+38h] [rbp-350h] BYREF
  size_t Size; // [rsp+40h] [rbp-348h] BYREF
  __int64 v28; // [rsp+48h] [rbp-340h] BYREF
  HLOCAL v29; // [rsp+50h] [rbp-338h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-330h] BYREF
  void *Src; // [rsp+60h] [rbp-328h] BYREF
  struct _GUID v32; // [rsp+70h] [rbp-318h] BYREF
  __int64 v33[5]; // [rsp+80h] [rbp-308h] BYREF
  int v34; // [rsp+A8h] [rbp-2E0h]
  int v35; // [rsp+ACh] [rbp-2DCh]
  __int64 v36; // [rsp+B0h] [rbp-2D8h]
  int v37; // [rsp+B8h] [rbp-2D0h]
  int v38; // [rsp+BCh] [rbp-2CCh]
  __int64 v39; // [rsp+C0h] [rbp-2C8h]
  __int64 v40; // [rsp+C8h] [rbp-2C0h]
  _BYTE v41[224]; // [rsp+D0h] [rbp-2B8h] BYREF
  __int64 v42; // [rsp+1B0h] [rbp-1D8h]
  __int64 v43; // [rsp+1C8h] [rbp-1C0h]
  OLECHAR *v44; // [rsp+1D0h] [rbp-1B8h]
  __int64 v45; // [rsp+1E8h] [rbp-1A0h]
  __int64 v46; // [rsp+1F0h] [rbp-198h]
  int v47; // [rsp+268h] [rbp-120h]
  __int64 v48; // [rsp+270h] [rbp-118h]
  int v49; // [rsp+28Ch] [rbp-FCh]
  __int64 v50; // [rsp+290h] [rbp-F8h]
  OLECHAR sz[40]; // [rsp+310h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl,
                          a2,
                          a3) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
    {
      if ( a1 )
      {
        v33[0] = *(_QWORD *)a1;
        v33[1] = *(_QWORD *)(a1 + 8);
        v33[2] = *(_QWORD *)(a1 + 16);
        v33[3] = *(_QWORD *)(a1 + 24);
        v33[4] = *(_QWORD *)(a1 + 32);
        v34 = *(_DWORD *)(a1 + 40);
        v35 = 0;
        v36 = *(_QWORD *)(a1 + 48);
        v37 = *(_DWORD *)(a1 + 56);
        v38 = 0;
        v39 = *(_QWORD *)(a1 + 64);
        v40 = 0;
        return WebAuthNPluginAddAuthenticator2(v33, a2);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B4,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
          (const char *)0x80090027LL,
          v23);
        return 2148073511LL;
      }
    }
    else
    {
      v26 = 0;
      tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::start_and_watch_errors(
        &v26,
        v33);
      tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::data(
        &v26,
        &v28);
      v25[0] = 0;
      memset_0(v41, 0, 0x238u);
      *a2 = 0;
      if ( (unsigned __int8)IsWinStationIsSessionRemoteablePresent()
        && (unsigned __int8)WinStationIsSessionRemoteable(0, 0xFFFFFFFFLL, v25)
        && v25[0] )
      {
        v7 = tip2::details::reason_string(
               (tip2::details *)"WebAuthNPluginAddAuthenticatorTest::reason::remote_session",
               v6);
        tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
          &v26,
          8,
          v7);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1D3,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
          (const char *)0x80090029LL,
          v23);
        tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(&v28);
        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(v33);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(&v26);
        return 2148073513LL;
      }
      else if ( a1 && *(_QWORD *)a1 && *(_QWORD *)(a1 + 16) )
      {
        memset_0(sz, 0, sizeof(sz));
        if ( StringFromGUID2(*(const GUID *const *)(a1 + 8), sz, 40) )
        {
          v43 = *(_QWORD *)a1;
          v42 = *(_QWORD *)(a1 + 16);
          v44 = sz;
          v45 = *(_QWORD *)(a1 + 24);
          v46 = *(_QWORD *)(a1 + 32);
          v47 = *(_DWORD *)(a1 + 40);
          v48 = *(_QWORD *)(a1 + 48);
          v49 = *(_DWORD *)(a1 + 56);
          v50 = *(_QWORD *)(a1 + 64);
          v10 = v28;
          v11 = -1;
          v12 = -1;
          do
            ++v12;
          while ( sz[v12] );
          std::wstring::_Assign<unsigned short>(v28 + 272, sz);
          v13 = *(_QWORD *)a1;
          do
            ++v11;
          while ( *(_WORD *)(v13 + 2 * v11) );
          std::wstring::_Assign<unsigned short>(v10 + 304, v13);
          tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::close(&v28);
          Src = 0;
          LODWORD(Size) = 0;
          tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(
            &v26,
            &v32);
          v14 = I_EncodeAndSendRpcRequest(
                  0x64u,
                  &v32,
                  (struct _CTAPCBOR_RPC_REQUEST *)v41,
                  (unsigned int *)&Size,
                  (unsigned __int8 **)&Src);
          if ( (v14 & 0x80000000) == 0 )
          {
            wil::make_unique_hlocal<_EXPERIMENTAL_WEBAUTHN_PLUGIN_ADD_AUTHENTICATOR_RESPONSE,>(&v29);
            v17 = Size;
            wil::make_unique_hlocal<unsigned char [0]>(&hMem, (unsigned int)Size);
            memcpy_0(hMem, Src, v17);
            v18 = hMem;
            hMem = 0;
            *((_QWORD *)v29 + 1) = v18;
            *(_DWORD *)v29 = v17;
            v19 = v29;
            v29 = 0;
            *a2 = v19;
            tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v26);
            v20 = hMem;
            hMem = 0;
            if ( v20 )
              LocalFree(v20);
            v21 = v29;
            v29 = 0;
            if ( v21 )
              LocalFree(v21);
            tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(&v28);
            tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(v33);
            wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(&v26);
            return 0;
          }
          else
          {
            if ( v26 )
            {
              if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v26 + 8) )
              {
                v16 = tip2::details::reason_string(
                        (tip2::details *)"WebAuthNPluginAddAuthenticatorTest::reason::generic_failure",
                        v15);
                tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::set_flag_value<long>(
                  &v26,
                  1,
                  v16,
                  v14);
                tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v26);
              }
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x204,
              (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
              (const char *)v14,
              v24);
            tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(&v28);
            tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(v33);
            wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(&v26);
            return v14;
          }
        }
        else
        {
          v9 = tip2::details::reason_string(
                 (tip2::details *)"WebAuthNPluginAddAuthenticatorTest::reason::invalid_parameters",
                 v8);
          tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
            &v26,
            2,
            v9);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1E3,
            (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
            (const char *)0x80090027LL,
            v23);
          tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(&v28);
          tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(v33);
          wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(&v26);
          return 2148073511LL;
        }
      }
      else
      {
        v22 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginAddAuthenticatorTest::reason::invalid_parameters",
                v6);
        tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
          &v26,
          2,
          v22);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1DB,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
          (const char *)0x80090027LL,
          v23);
        tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(&v28);
        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(v33);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(&v26);
        return 2148073511LL;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80004001LL,
      v23);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x180049800  mov     [rsp+arg_10], rbx
0x180049805  mov     [rsp+arg_18], rsi
0x18004980a  push    rdi
0x18004980b  push    r14
0x18004980d  push    r15
0x18004980f  sub     rsp, 370h
0x180049816  mov     rax, cs:__security_cookie
0x18004981d  xor     rax, rsp
0x180049820  mov     [rsp+388h+var_28], rax
0x180049828  mov     r14, rdx
0x18004982b  mov     rdi, rcx
0x18004982e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators> `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl(void)'::`2'::impl
0x180049835  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(void)
0x18004983a  xor     r15d, r15d
0x18004983d  test    al, al
0x18004983f  jnz     short loc_180049869
0x180049841  mov     rcx, [rsp+388h]; this
0x180049849  mov     ebx, 80004001h
0x18004984e  mov     r9d, ebx; char *
0x180049851  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180049858  mov     edx, 1B0h; void *
0x18004985d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049862  mov     eax, ebx
0x180049864  jmp     loc_180049D8B
0x180049869  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x180049870  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x180049875  test    al, al
0x180049877  jnz     loc_180049CC7
0x18004987d  mov     [rsp+388h+var_350], r15
0x180049882  lea     rdx, [rsp+388h+var_308]
0x18004988a  lea     rcx, [rsp+388h+var_350]
0x18004988f  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::start_and_watch_errors(void)
0x180049894  nop
0x180049895  lea     rdx, [rsp+388h+var_340]
0x18004989a  lea     rcx, [rsp+388h+var_350]
0x18004989f  call    ?data@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::data(void)
0x1800498a4  nop
0x1800498a5  mov     [rsp+388h+var_358], r15b
0x1800498aa  xor     edx, edx; Val
0x1800498ac  mov     r8d, 238h; Size
0x1800498b2  lea     rcx, [rsp+388h+var_2B8]; void *
0x1800498ba  call    memset_0
0x1800498bf  mov     [r14], r15
0x1800498c2  call    IsWinStationIsSessionRemoteablePresent
0x1800498c7  test    al, al
0x1800498c9  jz      loc_180049954
0x1800498cf  lea     r8, [rsp+388h+var_358]
0x1800498d4  or      edx, 0FFFFFFFFh
0x1800498d7  xor     ecx, ecx
0x1800498d9  call    cs:__imp_WinStationIsSessionRemoteable
0x1800498df  test    al, al
0x1800498e1  jz      short loc_180049954
0x1800498e3  cmp     [rsp+388h+var_358], r15b
0x1800498e8  jz      short loc_180049954
0x1800498ea  lea     rcx, aWebauthnplugin_126; "WebAuthNPluginAddAuthenticatorTest::rea"...
0x1800498f1  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800498f6  mov     r8, rax
0x1800498f9  mov     edx, 8
0x1800498fe  lea     rcx, [rsp+388h+var_350]
0x180049903  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x180049908  mov     rcx, [rsp+388h]; this
0x180049910  mov     ebx, 80090029h
0x180049915  mov     r9d, ebx; char *
0x180049918  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004991f  mov     edx, 1D3h; void *
0x180049924  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049929  nop
0x18004992a  lea     rcx, [rsp+388h+var_340]
0x18004992f  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(void)
0x180049934  nop
0x180049935  lea     rcx, [rsp+388h+var_308]
0x18004993d  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(void)
0x180049942  nop
0x180049943  lea     rcx, [rsp+388h+var_350]
0x180049948  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(void)
0x18004994d  mov     eax, ebx
0x18004994f  jmp     loc_180049D8B
0x180049954  test    rdi, rdi
0x180049957  jz      loc_180049C5D
0x18004995d  cmp     [rdi], r15
0x180049960  jz      loc_180049C5D
0x180049966  cmp     [rdi+10h], r15
0x18004996a  jz      loc_180049C5D
0x180049970  xor     edx, edx; Val
0x180049972  lea     r8d, [rdx+50h]; Size
0x180049976  lea     rcx, [rsp+388h+sz]; void *
0x18004997e  call    memset_0
0x180049983  mov     r8d, 28h ; '('; cchMax
0x180049989  lea     rdx, [rsp+388h+sz]; lpsz
0x180049991  mov     rcx, [rdi+8]; rguid
0x180049995  call    cs:__imp_StringFromGUID2
0x18004999b  test    eax, eax
0x18004999d  jnz     short loc_180049A09
0x18004999f  lea     rcx, aWebauthnplugin_117; "WebAuthNPluginAddAuthenticatorTest::rea"...
0x1800499a6  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800499ab  mov     r8, rax
0x1800499ae  mov     edx, 2
0x1800499b3  lea     rcx, [rsp+388h+var_350]
0x1800499b8  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800499bd  mov     rcx, [rsp+388h]; this
0x1800499c5  mov     ebx, 80090027h
0x1800499ca  mov     r9d, ebx; char *
0x1800499cd  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800499d4  mov     edx, 1E3h; void *
0x1800499d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800499de  nop
0x1800499df  lea     rcx, [rsp+388h+var_340]
0x1800499e4  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(void)
0x1800499e9  nop
0x1800499ea  lea     rcx, [rsp+388h+var_308]
0x1800499f2  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(void)
0x1800499f7  nop
0x1800499f8  lea     rcx, [rsp+388h+var_350]
0x1800499fd  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(void)
0x180049a02  mov     eax, ebx
0x180049a04  jmp     loc_180049D8B
0x180049a09  mov     rax, [rdi]
0x180049a0c  mov     [rsp+388h+var_1C0], rax
0x180049a14  mov     rax, [rdi+10h]
0x180049a18  mov     [rsp+388h+var_1D8], rax
0x180049a20  lea     rax, [rsp+388h+sz]
0x180049a28  mov     [rsp+388h+var_1B8], rax
0x180049a30  mov     rax, [rdi+18h]
0x180049a34  mov     [rsp+388h+var_1A0], rax
0x180049a3c  mov     rax, [rdi+20h]
0x180049a40  mov     [rsp+388h+var_198], rax
0x180049a48  mov     eax, [rdi+28h]
0x180049a4b  mov     [rsp+388h+var_120], eax
0x180049a52  mov     rax, [rdi+30h]
0x180049a56  mov     [rsp+388h+var_118], rax
0x180049a5e  mov     eax, [rdi+38h]
0x180049a61  mov     [rsp+388h+var_FC], eax
0x180049a68  mov     rax, [rdi+40h]
0x180049a6c  mov     [rsp+388h+var_F8], rax
0x180049a74  mov     rbx, [rsp+388h+var_340]
0x180049a79  lea     rcx, [rbx+110h]
0x180049a80  lea     rax, [rsp+388h+sz]
0x180049a88  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180049a8c  mov     r8, rsi
0x180049a8f  inc     r8
0x180049a92  cmp     [rax+r8*2], r15w
0x180049a97  jnz     short loc_180049A8F
0x180049a99  lea     rdx, [rsp+388h+sz]
0x180049aa1  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180049aa6  mov     rdx, [rdi]
0x180049aa9  lea     rcx, [rbx+130h]
0x180049ab0  inc     rsi
0x180049ab3  cmp     [rdx+rsi*2], r15w
0x180049ab8  jnz     short loc_180049AB0
0x180049aba  mov     r8, rsi
0x180049abd  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180049ac2  lea     rcx, [rsp+388h+var_340]
0x180049ac7  call    ?close@?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::close(void)
0x180049acc  mov     [rsp+388h+Src], r15
0x180049ad1  mov     dword ptr [rsp+388h+Size], r15d
0x180049ad6  lea     rdx, [rsp+388h+var_318]
0x180049adb  lea     rcx, [rsp+388h+var_350]
0x180049ae0  call    ?test_id@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEBA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(void)
0x180049ae5  movaps  xmm1, xmmword ptr [rsp+388h+var_318.Data1]
0x180049aea  movdqa  xmmword ptr [rsp+388h+var_318.Data1], xmm1
0x180049af0  lea     rax, [rsp+388h+Src]
0x180049af5  mov     qword ptr [rsp+388h+var_368], rax; int
0x180049afa  lea     r9, [rsp+388h+Size]; unsigned int *
0x180049aff  lea     r8, [rsp+388h+var_2B8]; struct _CTAPCBOR_RPC_REQUEST *
0x180049b07  lea     rdx, [rsp+388h+var_318]; struct _GUID *
0x180049b0c  mov     ecx, 64h ; 'd'; unsigned int
0x180049b11  call    ?I_EncodeAndSendRpcRequest@@YAJKU_GUID@@AEAU_CTAPCBOR_RPC_REQUEST@@PEAKPEAPEAE@Z; I_EncodeAndSendRpcRequest(ulong,_GUID,_CTAPCBOR_RPC_REQUEST &,ulong *,uchar * *)
0x180049b16  mov     ebx, eax
0x180049b18  test    eax, eax
0x180049b1a  jns     loc_180049BA9
0x180049b20  mov     rcx, [rsp+388h+var_350]
0x180049b25  test    rcx, rcx
0x180049b28  jz      short loc_180049B62
0x180049b2a  add     rcx, 8
0x180049b2e  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x180049b33  test    al, al
0x180049b35  jz      short loc_180049B62
0x180049b37  lea     rcx, aWebauthnplugin_62; "WebAuthNPluginAddAuthenticatorTest::rea"...
0x180049b3e  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180049b43  mov     r8, rax
0x180049b46  mov     edx, 1
0x180049b4b  mov     r9d, ebx
0x180049b4e  lea     rcx, [rsp+388h+var_350]
0x180049b53  call    ??$set_flag_value@J@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBDJ@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::set_flag_value<long>(ushort,char const *,long)
0x180049b58  lea     rcx, [rsp+388h+var_350]
0x180049b5d  call    ?complete@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(void)
0x180049b62  mov     rcx, [rsp+388h]; this
0x180049b6a  mov     r9d, ebx; char *
0x180049b6d  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180049b74  mov     edx, 204h; void *
0x180049b79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049b7e  nop
0x180049b7f  lea     rcx, [rsp+388h+var_340]
0x180049b84  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(void)
0x180049b89  nop
0x180049b8a  lea     rcx, [rsp+388h+var_308]
0x180049b92  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(void)
0x180049b97  nop
0x180049b98  lea     rcx, [rsp+388h+var_350]
0x180049b9d  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(void)
0x180049ba2  mov     eax, ebx
0x180049ba4  jmp     loc_180049D8B
0x180049ba9  lea     rcx, [rsp+388h+var_338]
0x180049bae  call    ??$make_unique_hlocal@U_EXPERIMENTAL_WEBAUTHN_PLUGIN_ADD_AUTHENTICATOR_RESPONSE@@$$V@wil@@YA?AV?$unique_ptr@U_EXPERIMENTAL_WEBAUTHN_PLUGIN_ADD_AUTHENTICATOR_RESPONSE@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@XZ; wil::make_unique_hlocal<_EXPERIMENTAL_WEBAUTHN_PLUGIN_ADD_AUTHENTICATOR_RESPONSE,>(void)
0x180049bb3  nop
0x180049bb4  mov     ebx, dword ptr [rsp+388h+Size]
0x180049bb8  mov     edx, ebx
0x180049bba  lea     rcx, [rsp+388h+hMem]
0x180049bbf  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x180049bc4  mov     r8d, ebx; Size
0x180049bc7  mov     rdx, [rsp+388h+Src]; Src
0x180049bcc  mov     rcx, [rsp+388h+hMem]; void *
0x180049bd1  call    memcpy_0
0x180049bd6  mov     rcx, [rsp+388h+hMem]
0x180049bdb  mov     [rsp+388h+hMem], r15
0x180049be0  mov     rax, [rsp+388h+var_338]
0x180049be5  mov     [rax+8], rcx
0x180049be9  mov     rax, [rsp+388h+var_338]
0x180049bee  mov     [rax], ebx
0x180049bf0  mov     rax, [rsp+388h+var_338]
0x180049bf5  mov     [rsp+388h+var_338], r15
0x180049bfa  mov     [r14], rax
0x180049bfd  lea     rcx, [rsp+388h+var_350]
0x180049c02  call    ?complete@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(void)
0x180049c07  mov     rcx, [rsp+388h+hMem]; hMem
0x180049c0c  mov     [rsp+388h+hMem], r15
0x180049c11  test    rcx, rcx
0x180049c14  jz      short loc_180049C1D
0x180049c16  call    cs:__imp_LocalFree
0x180049c1c  nop
0x180049c1d  mov     rcx, [rsp+388h+var_338]; hMem
0x180049c22  mov     [rsp+388h+var_338], r15
0x180049c27  test    rcx, rcx
0x180049c2a  jz      short loc_180049C33
0x180049c2c  call    cs:__imp_LocalFree
0x180049c32  nop
0x180049c33  lea     rcx, [rsp+388h+var_340]
0x180049c38  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(void)
0x180049c3d  nop
0x180049c3e  lea     rcx, [rsp+388h+var_308]
0x180049c46  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(void)
0x180049c4b  nop
0x180049c4c  lea     rcx, [rsp+388h+var_350]
0x180049c51  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(void)
0x180049c56  xor     eax, eax
0x180049c58  jmp     loc_180049D8B
0x180049c5d  lea     rcx, aWebauthnplugin_117; "WebAuthNPluginAddAuthenticatorTest::rea"...
0x180049c64  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180049c69  mov     r8, rax
0x180049c6c  mov     edx, 2
0x180049c71  lea     rcx, [rsp+388h+var_350]
0x180049c76  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x180049c7b  mov     rcx, [rsp+388h]; this
0x180049c83  mov     ebx, 80090027h
0x180049c88  mov     r9d, ebx; char *
0x180049c8b  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180049c92  mov     edx, 1DBh; void *
0x180049c97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049c9c  nop
0x180049c9d  lea     rcx, [rsp+388h+var_340]
0x180049ca2  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(void)
0x180049ca7  nop
0x180049ca8  lea     rcx, [rsp+388h+var_308]
0x180049cb0  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(void)
0x180049cb5  nop
0x180049cb6  lea     rcx, [rsp+388h+var_350]
0x180049cbb  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(void)
0x180049cc0  mov     eax, ebx
0x180049cc2  jmp     loc_180049D8B
0x180049cc7  test    rdi, rdi
0x180049cca  jnz     short loc_180049CF4
0x180049ccc  mov     rcx, [rsp+388h]; this
0x180049cd4  mov     ebx, 80090027h
0x180049cd9  mov     r9d, ebx; char *
0x180049cdc  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180049ce3  mov     edx, 1B4h; void *
0x180049ce8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049ced  mov     eax, ebx
0x180049cef  jmp     loc_180049D8B
0x180049cf4  mov     rax, [rdi]
0x180049cf7  mov     [rsp+388h+var_308], rax
0x180049cff  mov     rax, [rdi+8]
0x180049d03  mov     [rsp+388h+var_300], rax
0x180049d0b  mov     rax, [rdi+10h]
0x180049d0f  mov     [rsp+388h+var_2F8], rax
0x180049d17  mov     rax, [rdi+18h]
0x180049d1b  mov     [rsp+388h+var_2F0], rax
0x180049d23  mov     rax, [rdi+20h]
0x180049d27  mov     [rsp+388h+var_2E8], rax
0x180049d2f  mov     eax, [rdi+28h]
0x180049d32  mov     [rsp+388h+var_2E0], eax
0x180049d39  xor     eax, eax
0x180049d3b  mov     [rsp+388h+var_2DC], eax
0x180049d42  mov     rax, [rdi+30h]
0x180049d46  mov     [rsp+388h+var_2D8], rax
0x180049d4e  mov     eax, [rdi+38h]
0x180049d51  mov     [rsp+388h+var_2D0], eax
0x180049d58  xor     eax, eax
0x180049d5a  mov     [rsp+388h+var_2CC], eax
0x180049d61  mov     rax, [rdi+40h]
  ... truncated ...
```
