# WebAuthNPluginAddAuthenticator2

- ea: `0x1800bb110`
- end: `0x1800bb663`
- name: `WebAuthNPluginAddAuthenticator2`
- size: `1363`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180049800`

## callees

- `0x180022c60`
- `0x180036da4`
- `0x1800467e0`
- `0x180049dbc`
- `0x180049de0`
- `0x180049e00`
- `0x180049e1c`
- `0x18004d8f4`
- `0x18004f5b4`
- `0x18005378c`
- `0x1800537a4`
- `0x18006cfd4`
- `0x18006f7b0`
- `0x180079444`
- `0x18007e064`
- `0x180092728`
- `0x180095468`
- `0x1800b12bc`
- `0x1800b4170`
- `0x1800b5004`
- `0x1800b5214`
- `0x1800b7a3c`
- `0x1800bb110`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb595`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb5ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb595`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb5ab`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bb249`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bb249`

## string_xrefs

- `0x1800bb161`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bb1cd`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bb281`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bb32a`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bb4ec`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bb607`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bb253`: `WebAuthNPluginAddAuthenticatorTest::reason::invalid_parameters`
- `0x1800bb5d9`: `WebAuthNPluginAddAuthenticatorTest::reason::invalid_parameters`
- `0x1800bb19f`: `WebAuthNPluginAddAuthenticatorTest::reason::remote_session`
- `0x1800bb2f2`: `WebAuthNPluginAddAuthenticatorTest::reason::invalid_kcm_key`
- `0x1800bb4b6`: `WebAuthNPluginAddAuthenticatorTest::reason::generic_failure`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall WebAuthNPluginAddAuthenticator2(__int64 *a1, _QWORD *a2)
{
  const char *v5; // rdx
  const char *v6; // rax
  const char *v7; // rdx
  const char *v8; // rax
  const unsigned __int16 *v9; // rcx
  __int64 v10; // rsi
  __int64 v11; // rax
  const char *v12; // rdx
  const char *v13; // rax
  __int64 v14; // r9
  __int64 v15; // rbx
  __int64 v16; // r8
  __int64 v17; // rdx
  unsigned int v18; // ebx
  const char *v19; // rdx
  const char *v20; // rax
  unsigned int v21; // ebx
  HLOCAL v22; // rcx
  HLOCAL v23; // rax
  HLOCAL v24; // rcx
  HLOCAL v25; // rcx
  const char *v26; // rax
  int v27; // [rsp+20h] [rbp-358h]
  int v28; // [rsp+20h] [rbp-358h]
  bool v29; // [rsp+30h] [rbp-348h] BYREF
  __int64 v30; // [rsp+38h] [rbp-340h] BYREF
  size_t Size; // [rsp+40h] [rbp-338h] BYREF
  HLOCAL v32; // [rsp+48h] [rbp-330h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-328h] BYREF
  __int64 v34; // [rsp+58h] [rbp-320h] BYREF
  void *Src; // [rsp+60h] [rbp-318h] BYREF
  struct _GUID v36; // [rsp+70h] [rbp-308h] BYREF
  _BYTE v37[64]; // [rsp+80h] [rbp-2F8h] BYREF
  _BYTE v38[224]; // [rsp+C0h] [rbp-2B8h] BYREF
  __int64 v39; // [rsp+1A0h] [rbp-1D8h]
  __int64 v40; // [rsp+1B8h] [rbp-1C0h]
  OLECHAR *v41; // [rsp+1C0h] [rbp-1B8h]
  __int64 v42; // [rsp+1D8h] [rbp-1A0h]
  __int64 v43; // [rsp+1E0h] [rbp-198h]
  int v44; // [rsp+258h] [rbp-120h]
  __int64 v45; // [rsp+260h] [rbp-118h]
  int v46; // [rsp+27Ch] [rbp-FCh]
  __int64 v47; // [rsp+280h] [rbp-F8h]
  __int64 v48; // [rsp+2D8h] [rbp-A0h]
  OLECHAR sz[40]; // [rsp+300h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
  {
    v30 = 0;
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::start_and_watch_errors(
      &v30,
      v37);
    *a2 = 0;
    if ( ShouldSendRequestToRemoteSession(0) )
    {
      v6 = tip2::details::reason_string(
             (tip2::details *)"WebAuthNPluginAddAuthenticatorTest::reason::remote_session",
             v5);
      tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
        &v30,
        8,
        v6);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x238,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)0x80090029LL,
        v27);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(v37);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(&v30);
      return 2148073513LL;
    }
    else if ( a1 && *a1 && a1[1] && a1[2] )
    {
      memset_0(sz, 0, sizeof(sz));
      if ( StringFromGUID2((const GUID *const)a1[1], sz, 40) )
      {
        v9 = (const unsigned __int16 *)a1[9];
        v10 = -1;
        if ( !v9 )
          goto LABEL_17;
        v11 = -1;
        do
          ++v11;
        while ( v9[v11] );
        if ( v11 && (v29 = 0, IsKcmKeyValid(v9, &v29), !v29) )
        {
          v13 = tip2::details::reason_string(
                  (tip2::details *)"WebAuthNPluginAddAuthenticatorTest::reason::invalid_kcm_key",
                  v12);
          tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::set_flag_value<long>(
            &v30,
            10,
            v13,
            v14);
          tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v30);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x256,
            (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
            (const char *)0x80090027LL,
            v27);
          tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(v37);
          wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(&v30);
          return 2148073511LL;
        }
        else
        {
LABEL_17:
          memset_0(v38, 0, 0x238u);
          v40 = *a1;
          v39 = a1[2];
          v41 = sz;
          v42 = a1[3];
          v43 = a1[4];
          v44 = *((_DWORD *)a1 + 10);
          v45 = a1[6];
          v46 = *((_DWORD *)a1 + 14);
          v47 = a1[8];
          v48 = a1[9];
          tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::data(
            &v30,
            &v34);
          v15 = v34;
          v16 = -1;
          do
            ++v16;
          while ( sz[v16] );
          std::wstring::_Assign<unsigned short>(v34 + 272, sz);
          v17 = *a1;
          do
            ++v10;
          while ( *(_WORD *)(v17 + 2 * v10) );
          std::wstring::_Assign<unsigned short>(v15 + 304, v17);
          tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::close(&v34);
          Src = 0;
          LODWORD(Size) = 0;
          tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(
            &v30,
            &v36);
          v18 = I_EncodeAndSendRpcRequest(
                  0x64u,
                  &v36,
                  (struct _CTAPCBOR_RPC_REQUEST *)v38,
                  (unsigned int *)&Size,
                  (unsigned __int8 **)&Src);
          if ( (v18 & 0x80000000) == 0 )
          {
            wil::make_unique_hlocal<_EXPERIMENTAL_WEBAUTHN_PLUGIN_ADD_AUTHENTICATOR_RESPONSE,>(&v32);
            v21 = Size;
            wil::make_unique_hlocal<unsigned char [0]>(&hMem, (unsigned int)Size);
            memcpy_0(hMem, Src, v21);
            v22 = hMem;
            hMem = 0;
            *((_QWORD *)v32 + 1) = v22;
            *(_DWORD *)v32 = v21;
            v23 = v32;
            v32 = 0;
            *a2 = v23;
            tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v30);
            v24 = hMem;
            hMem = 0;
            if ( v24 )
              LocalFree(v24);
            v25 = v32;
            v32 = 0;
            if ( v25 )
              LocalFree(v25);
            tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(&v34);
            tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(v37);
            wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(&v30);
            return 0;
          }
          else
          {
            if ( v30 )
            {
              if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v30 + 8) )
              {
                v20 = tip2::details::reason_string(
                        (tip2::details *)"WebAuthNPluginAddAuthenticatorTest::reason::generic_failure",
                        v19);
                tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::set_flag_value<long>(
                  &v30,
                  1,
                  v20,
                  v18);
                tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(&v30);
              }
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x27B,
              (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
              (const char *)v18,
              v28);
            tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(&v34);
            tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(v37);
            wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(&v30);
            return v18;
          }
        }
      }
      else
      {
        v8 = tip2::details::reason_string(
               (tip2::details *)"WebAuthNPluginAddAuthenticatorTest::reason::invalid_parameters",
               v7);
        tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
          &v30,
          2,
          v8);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x249,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
          (const char *)0x80090027LL,
          v27);
        tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(v37);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(&v30);
        return 2148073511LL;
      }
    }
    else
    {
      v26 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginAddAuthenticatorTest::reason::invalid_parameters",
              v5);
      tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(
        &v30,
        2,
        v26);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x241,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)0x80090027LL,
        v27);
      tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(v37);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(&v30);
      return 2148073511LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22E,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x80004001LL,
      v27);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x1800bb110  mov     [rsp+arg_10], rbx
0x1800bb115  mov     [rsp+arg_18], rsi
0x1800bb11a  push    rdi
0x1800bb11b  push    r14
0x1800bb11d  push    r15
0x1800bb11f  sub     rsp, 360h
0x1800bb126  mov     rax, cs:__security_cookie
0x1800bb12d  xor     rax, rsp
0x1800bb130  mov     [rsp+378h+var_28], rax
0x1800bb138  mov     r14, rdx
0x1800bb13b  mov     rdi, rcx
0x1800bb13e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1800bb145  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1800bb14a  xor     r15d, r15d
0x1800bb14d  test    al, al
0x1800bb14f  jnz     short loc_1800BB179
0x1800bb151  mov     rcx, [rsp+378h]; this
0x1800bb159  mov     ebx, 80004001h
0x1800bb15e  mov     r9d, ebx; char *
0x1800bb161  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bb168  mov     edx, 22Eh; void *
0x1800bb16d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb172  mov     eax, ebx
0x1800bb174  jmp     loc_1800BB639
0x1800bb179  mov     [rsp+378h+var_340], r15
0x1800bb17e  lea     rdx, [rsp+378h+var_2F8]
0x1800bb186  lea     rcx, [rsp+378h+var_340]
0x1800bb18b  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::start_and_watch_errors(void)
0x1800bb190  nop
0x1800bb191  mov     [r14], r15
0x1800bb194  xor     ecx, ecx; unsigned __int8 *
0x1800bb196  call    ?ShouldSendRequestToRemoteSession@@YA_NPEAE@Z; ShouldSendRequestToRemoteSession(uchar *)
0x1800bb19b  test    al, al
0x1800bb19d  jz      short loc_1800BB1FE
0x1800bb19f  lea     rcx, aWebauthnplugin_126; "WebAuthNPluginAddAuthenticatorTest::rea"...
0x1800bb1a6  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bb1ab  mov     r8, rax
0x1800bb1ae  mov     edx, 8
0x1800bb1b3  lea     rcx, [rsp+378h+var_340]
0x1800bb1b8  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bb1bd  mov     rcx, [rsp+378h]; this
0x1800bb1c5  mov     ebx, 80090029h
0x1800bb1ca  mov     r9d, ebx; char *
0x1800bb1cd  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bb1d4  mov     edx, 238h; void *
0x1800bb1d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb1de  nop
0x1800bb1df  lea     rcx, [rsp+378h+var_2F8]
0x1800bb1e7  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(void)
0x1800bb1ec  nop
0x1800bb1ed  lea     rcx, [rsp+378h+var_340]
0x1800bb1f2  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(void)
0x1800bb1f7  mov     eax, ebx
0x1800bb1f9  jmp     loc_1800BB639
0x1800bb1fe  test    rdi, rdi
0x1800bb201  jz      loc_1800BB5D9
0x1800bb207  cmp     [rdi], r15
0x1800bb20a  jz      loc_1800BB5D9
0x1800bb210  cmp     [rdi+8], r15
0x1800bb214  jz      loc_1800BB5D9
0x1800bb21a  cmp     [rdi+10h], r15
0x1800bb21e  jz      loc_1800BB5D9
0x1800bb224  xor     edx, edx; Val
0x1800bb226  lea     r8d, [rdx+50h]; Size
0x1800bb22a  lea     rcx, [rsp+378h+sz]; void *
0x1800bb232  call    memset_0
0x1800bb237  mov     r8d, 28h ; '('; cchMax
0x1800bb23d  lea     rdx, [rsp+378h+sz]; lpsz
0x1800bb245  mov     rcx, [rdi+8]; rguid
0x1800bb249  call    cs:__imp_StringFromGUID2
0x1800bb24f  test    eax, eax
0x1800bb251  jnz     short loc_1800BB2B2
0x1800bb253  lea     rcx, aWebauthnplugin_117; "WebAuthNPluginAddAuthenticatorTest::rea"...
0x1800bb25a  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bb25f  mov     r8, rax
0x1800bb262  mov     edx, 2
0x1800bb267  lea     rcx, [rsp+378h+var_340]
0x1800bb26c  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bb271  mov     rcx, [rsp+378h]; this
0x1800bb279  mov     ebx, 80090027h
0x1800bb27e  mov     r9d, ebx; char *
0x1800bb281  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bb288  mov     edx, 249h; void *
0x1800bb28d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb292  nop
0x1800bb293  lea     rcx, [rsp+378h+var_2F8]
0x1800bb29b  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(void)
0x1800bb2a0  nop
0x1800bb2a1  lea     rcx, [rsp+378h+var_340]
0x1800bb2a6  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(void)
0x1800bb2ab  mov     eax, ebx
0x1800bb2ad  jmp     loc_1800BB639
0x1800bb2b2  mov     rcx, [rdi+48h]; unsigned __int16 *
0x1800bb2b6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800bb2ba  test    rcx, rcx
0x1800bb2bd  jz      loc_1800BB35B
0x1800bb2c3  mov     rax, rsi
0x1800bb2c6  inc     rax
0x1800bb2c9  cmp     [rcx+rax*2], r15w
0x1800bb2ce  jnz     short loc_1800BB2C6
0x1800bb2d0  test    rax, rax
0x1800bb2d3  jz      loc_1800BB35B
0x1800bb2d9  mov     [rsp+378h+var_348], r15b
0x1800bb2de  lea     rdx, [rsp+378h+var_348]; bool *
0x1800bb2e3  call    ?IsKcmKeyValid@@YAJPEBGAEA_N@Z; IsKcmKeyValid(ushort const *,bool &)
0x1800bb2e8  mov     r9d, eax
0x1800bb2eb  cmp     [rsp+378h+var_348], r15b
0x1800bb2f0  jnz     short loc_1800BB35B
0x1800bb2f2  lea     rcx, aWebauthnplugin_31; "WebAuthNPluginAddAuthenticatorTest::rea"...
0x1800bb2f9  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bb2fe  mov     r8, rax
0x1800bb301  mov     edx, 0Ah
0x1800bb306  lea     rcx, [rsp+378h+var_340]
0x1800bb30b  call    ??$set_flag_value@J@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBDJ@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::set_flag_value<long>(ushort,char const *,long)
0x1800bb310  lea     rcx, [rsp+378h+var_340]
0x1800bb315  call    ?complete@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(void)
0x1800bb31a  mov     rcx, [rsp+378h]; this
0x1800bb322  mov     ebx, 80090027h
0x1800bb327  mov     r9d, ebx; char *
0x1800bb32a  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bb331  mov     edx, 256h; void *
0x1800bb336  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb33b  nop
0x1800bb33c  lea     rcx, [rsp+378h+var_2F8]
0x1800bb344  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(void)
0x1800bb349  nop
0x1800bb34a  lea     rcx, [rsp+378h+var_340]
0x1800bb34f  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(void)
0x1800bb354  mov     eax, ebx
0x1800bb356  jmp     loc_1800BB639
0x1800bb35b  xor     edx, edx; Val
0x1800bb35d  mov     r8d, 238h; Size
0x1800bb363  lea     rcx, [rsp+378h+var_2B8]; void *
0x1800bb36b  call    memset_0
0x1800bb370  mov     rax, [rdi]
0x1800bb373  mov     [rsp+378h+var_1C0], rax
0x1800bb37b  mov     rax, [rdi+10h]
0x1800bb37f  mov     [rsp+378h+var_1D8], rax
0x1800bb387  lea     rax, [rsp+378h+sz]
0x1800bb38f  mov     [rsp+378h+var_1B8], rax
0x1800bb397  mov     rax, [rdi+18h]
0x1800bb39b  mov     [rsp+378h+var_1A0], rax
0x1800bb3a3  mov     rax, [rdi+20h]
0x1800bb3a7  mov     [rsp+378h+var_198], rax
0x1800bb3af  mov     eax, [rdi+28h]
0x1800bb3b2  mov     [rsp+378h+var_120], eax
0x1800bb3b9  mov     rax, [rdi+30h]
0x1800bb3bd  mov     [rsp+378h+var_118], rax
0x1800bb3c5  mov     eax, [rdi+38h]
0x1800bb3c8  mov     [rsp+378h+var_FC], eax
0x1800bb3cf  mov     rax, [rdi+40h]
0x1800bb3d3  mov     [rsp+378h+var_F8], rax
0x1800bb3db  mov     rax, [rdi+48h]
0x1800bb3df  mov     [rsp+378h+var_A0], rax
0x1800bb3e7  lea     rdx, [rsp+378h+var_320]
0x1800bb3ec  lea     rcx, [rsp+378h+var_340]
0x1800bb3f1  call    ?data@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::data(void)
0x1800bb3f6  nop
0x1800bb3f7  mov     rbx, [rsp+378h+var_320]
0x1800bb3fc  lea     rcx, [rbx+110h]
0x1800bb403  lea     rax, [rsp+378h+sz]
0x1800bb40b  mov     r8, rsi
0x1800bb40e  inc     r8
0x1800bb411  cmp     [rax+r8*2], r15w
0x1800bb416  jnz     short loc_1800BB40E
0x1800bb418  lea     rdx, [rsp+378h+sz]
0x1800bb420  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800bb425  mov     rdx, [rdi]
0x1800bb428  lea     rcx, [rbx+130h]
0x1800bb42f  inc     rsi
0x1800bb432  cmp     [rdx+rsi*2], r15w
0x1800bb437  jnz     short loc_1800BB42F
0x1800bb439  mov     r8, rsi
0x1800bb43c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800bb441  lea     rcx, [rsp+378h+var_320]
0x1800bb446  call    ?close@?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::close(void)
0x1800bb44b  mov     [rsp+378h+Src], r15
0x1800bb450  mov     dword ptr [rsp+378h+Size], r15d
0x1800bb455  lea     rdx, [rsp+378h+var_308]
0x1800bb45a  lea     rcx, [rsp+378h+var_340]
0x1800bb45f  call    ?test_id@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@@tip2@@QEBA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>>::test_id(void)
0x1800bb464  movaps  xmm1, xmmword ptr [rsp+378h+var_308.Data1]
0x1800bb469  movdqa  xmmword ptr [rsp+378h+var_308.Data1], xmm1
0x1800bb46f  lea     rax, [rsp+378h+Src]
0x1800bb474  mov     qword ptr [rsp+378h+var_358], rax; int
0x1800bb479  lea     r9, [rsp+378h+Size]; unsigned int *
0x1800bb47e  lea     r8, [rsp+378h+var_2B8]; struct _CTAPCBOR_RPC_REQUEST *
0x1800bb486  lea     rdx, [rsp+378h+var_308]; struct _GUID *
0x1800bb48b  mov     ecx, 64h ; 'd'; unsigned int
0x1800bb490  call    ?I_EncodeAndSendRpcRequest@@YAJKU_GUID@@AEAU_CTAPCBOR_RPC_REQUEST@@PEAKPEAPEAE@Z; I_EncodeAndSendRpcRequest(ulong,_GUID,_CTAPCBOR_RPC_REQUEST &,ulong *,uchar * *)
0x1800bb495  mov     ebx, eax
0x1800bb497  test    eax, eax
0x1800bb499  jns     loc_1800BB528
0x1800bb49f  mov     rcx, [rsp+378h+var_340]
0x1800bb4a4  test    rcx, rcx
0x1800bb4a7  jz      short loc_1800BB4E1
0x1800bb4a9  add     rcx, 8
0x1800bb4ad  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x1800bb4b2  test    al, al
0x1800bb4b4  jz      short loc_1800BB4E1
0x1800bb4b6  lea     rcx, aWebauthnplugin_62; "WebAuthNPluginAddAuthenticatorTest::rea"...
0x1800bb4bd  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bb4c2  mov     r8, rax
0x1800bb4c5  mov     edx, 1
0x1800bb4ca  mov     r9d, ebx
0x1800bb4cd  lea     rcx, [rsp+378h+var_340]
0x1800bb4d2  call    ??$set_flag_value@J@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBDJ@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::set_flag_value<long>(ushort,char const *,long)
0x1800bb4d7  lea     rcx, [rsp+378h+var_340]
0x1800bb4dc  call    ?complete@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(void)
0x1800bb4e1  mov     rcx, [rsp+378h]; this
0x1800bb4e9  mov     r9d, ebx; char *
0x1800bb4ec  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bb4f3  mov     edx, 27Bh; void *
0x1800bb4f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb4fd  nop
0x1800bb4fe  lea     rcx, [rsp+378h+var_320]
0x1800bb503  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(void)
0x1800bb508  nop
0x1800bb509  lea     rcx, [rsp+378h+var_2F8]
0x1800bb511  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(void)
0x1800bb516  nop
0x1800bb517  lea     rcx, [rsp+378h+var_340]
0x1800bb51c  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(void)
0x1800bb521  mov     eax, ebx
0x1800bb523  jmp     loc_1800BB639
0x1800bb528  lea     rcx, [rsp+378h+var_330]
0x1800bb52d  call    ??$make_unique_hlocal@U_EXPERIMENTAL_WEBAUTHN_PLUGIN_ADD_AUTHENTICATOR_RESPONSE@@$$V@wil@@YA?AV?$unique_ptr@U_EXPERIMENTAL_WEBAUTHN_PLUGIN_ADD_AUTHENTICATOR_RESPONSE@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@XZ; wil::make_unique_hlocal<_EXPERIMENTAL_WEBAUTHN_PLUGIN_ADD_AUTHENTICATOR_RESPONSE,>(void)
0x1800bb532  nop
0x1800bb533  mov     ebx, dword ptr [rsp+378h+Size]
0x1800bb537  mov     edx, ebx
0x1800bb539  lea     rcx, [rsp+378h+hMem]
0x1800bb53e  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x1800bb543  mov     r8d, ebx; Size
0x1800bb546  mov     rdx, [rsp+378h+Src]; Src
0x1800bb54b  mov     rcx, [rsp+378h+hMem]; void *
0x1800bb550  call    memcpy_0
0x1800bb555  mov     rcx, [rsp+378h+hMem]
0x1800bb55a  mov     [rsp+378h+hMem], r15
0x1800bb55f  mov     rax, [rsp+378h+var_330]
0x1800bb564  mov     [rax+8], rcx
0x1800bb568  mov     rax, [rsp+378h+var_330]
0x1800bb56d  mov     [rax], ebx
0x1800bb56f  mov     rax, [rsp+378h+var_330]
0x1800bb574  mov     [rsp+378h+var_330], r15
0x1800bb579  mov     [r14], rax
0x1800bb57c  lea     rcx, [rsp+378h+var_340]
0x1800bb581  call    ?complete@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginCallbackTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginCallbackTest,_tip_WebAuthNPluginCallbackTest>>::complete(void)
0x1800bb586  mov     rcx, [rsp+378h+hMem]; hMem
0x1800bb58b  mov     [rsp+378h+hMem], r15
0x1800bb590  test    rcx, rcx
0x1800bb593  jz      short loc_1800BB59C
0x1800bb595  call    cs:__imp_LocalFree
0x1800bb59b  nop
0x1800bb59c  mov     rcx, [rsp+378h+var_330]; hMem
0x1800bb5a1  mov     [rsp+378h+var_330], r15
0x1800bb5a6  test    rcx, rcx
0x1800bb5a9  jz      short loc_1800BB5B2
0x1800bb5ab  call    cs:__imp_LocalFree
0x1800bb5b1  nop
0x1800bb5b2  lea     rcx, [rsp+378h+var_320]
0x1800bb5b7  call    ??1?$test_data_control@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(void)
0x1800bb5bc  nop
0x1800bb5bd  lea     rcx, [rsp+378h+var_2F8]
0x1800bb5c5  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(void)
0x1800bb5ca  nop
0x1800bb5cb  lea     rcx, [rsp+378h+var_340]
0x1800bb5d0  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(void)
0x1800bb5d5  xor     eax, eax
0x1800bb5d7  jmp     short loc_1800BB639
0x1800bb5d9  lea     rcx, aWebauthnplugin_117; "WebAuthNPluginAddAuthenticatorTest::rea"...
0x1800bb5e0  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bb5e5  mov     r8, rax
0x1800bb5e8  mov     edx, 2
0x1800bb5ed  lea     rcx, [rsp+378h+var_340]
0x1800bb5f2  call    ?complete_and_ignore@?$tip_test@V?$merged_data@U_tip_PluginAuthenticatorGetAssertionScenarioTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_PluginAuthenticatorGetAssertionScenarioTest,_tip_PluginAuthenticatorGetAssertionScenarioTest>>::complete_and_ignore(ushort,char const *)
0x1800bb5f7  mov     rcx, [rsp+378h]; this
0x1800bb5ff  mov     ebx, 80090027h
0x1800bb604  mov     r9d, ebx; char *
0x1800bb607  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bb60e  mov     edx, 241h; void *
0x1800bb613  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb618  nop
0x1800bb619  lea     rcx, [rsp+378h+var_2F8]
0x1800bb621  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>>(void)
0x1800bb626  nop
0x1800bb627  lea     rcx, [rsp+378h+var_340]
0x1800bb62c  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(void)
0x1800bb631  mov     eax, ebx
0x1800bb633  jmp     short loc_1800BB639
0x1800bb635  mov     eax, dword ptr [rsp+378h+Size]
0x1800bb639  mov     rcx, [rsp+378h+var_28]
0x1800bb641  xor     rcx, rsp; StackCookie
0x1800bb644  call    __security_check_cookie
0x1800bb649  lea     r11, [rsp+378h+var_18]
0x1800bb651  mov     rbx, [r11+30h]
0x1800bb655  mov     rsi, [r11+38h]
0x1800bb659  mov     rsp, r11
0x1800bb65c  pop     r15
0x1800bb65e  pop     r14
0x1800bb660  pop     rdi
  ... truncated ...
```
