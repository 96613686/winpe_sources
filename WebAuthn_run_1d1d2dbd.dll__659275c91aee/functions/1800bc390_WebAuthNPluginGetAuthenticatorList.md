# WebAuthNPluginGetAuthenticatorList

- ea: `0x1800bc390`
- end: `0x1800bcd44`
- name: `WebAuthNPluginGetAuthenticatorList`
- size: `2484`
- prototype: ``
- caller_count: `2`
- callee_count: `39`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800b9770`
- `0x1800bcd50`

## callees

- `0x18000c9d0`
- `0x180017a88`
- `0x18001cd78`
- `0x180021878`
- `0x1800288c8`
- `0x18003164c`
- `0x180036da4`
- `0x180037f6c`
- `0x18003ee60`
- `0x1800467e0`
- `0x18004d8f4`
- `0x18004f5b4`
- `0x180052e3c`
- `0x18005378c`
- `0x1800537a4`
- `0x180066b34`
- `0x18006ccd4`
- `0x18006d0e4`
- `0x180072a34`
- `0x180092728`
- `0x1800ae560`
- `0x1800af870`
- `0x1800afcec`
- `0x1800b02cc`
- `0x1800b2774`
- `0x1800b2988`
- `0x1800b2eb0`
- `0x1800b3064`
- `0x1800b31d8`
- `0x1800b31fc`
- `0x1800b4170`
- `0x1800b4e44`
- `0x1800b5124`
- `0x1800b56b0`
- `0x1800b73c4`
- `0x1800b7a04`
- `0x1800bab20`
- `0x1800bc390`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800bc5c8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800bc717`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800bc5c8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800bc717`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc7de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc941`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc9fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bcb63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc7de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc941`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc9fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bcb63`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800bc806`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800bca23`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800bc806`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800bca23`

## string_xrefs

- `0x1800bc4f1`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bc57a`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bcce2`: `onecore\ds\security\fido\webauthn\dll\webauthnplugin.cpp`
- `0x1800bc47b`: `WebAuthNPluginGetAuthenticatorListTest::reason::no_authenticators_found`
- `0x1800bc53b`: `WebAuthNPluginGetAuthenticatorListTest::reason::decoding_failed`
- `0x1800bc4ba`: `WebAuthNPluginGetAuthenticatorListTest::reason::generic_failure`
- `0x1800bcc6c`: `WebAuthNPluginGetAuthenticatorListTest::reason::authenticator_list_created`
- `0x1800bc8f2`: `WebAuthNPluginGetAuthenticatorListTest::reason::webauthn_authenticator_db_get_info_failed`
- `0x1800bcb0f`: `WebAuthNPluginGetAuthenticatorListTest::reason::webauthn_authenticator_db_get_info_failed`

## pseudocode

```c
__int64 __fastcall WebAuthNPluginGetAuthenticatorList(int a1, _QWORD *a2)
{
  _QWORD *v3; // r12
  _QWORD *v4; // rax
  GUID v5; // xmm0
  int v6; // eax
  const char *v7; // rdx
  unsigned int v8; // edi
  _QWORD *v9; // rax
  const char *v10; // rdx
  const char *v11; // rax
  const char *v12; // rbx
  _QWORD *v13; // rax
  unsigned int v14; // ebx
  const char *v15; // rdx
  const char *v16; // rax
  int v17; // eax
  signed int v18; // ebx
  _QWORD *v20; // rdi
  HLOCAL v21; // rax
  _DWORD *v22; // r15
  int v23; // eax
  unsigned int v24; // r13d
  __int64 v25; // r12
  __int64 *v26; // rax
  __int64 v27; // rcx
  __int64 *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  SIZE_T v33; // rdx
  HLOCAL v34; // rax
  unsigned __int8 v35; // r13
  __int64 v36; // rcx
  __int64 v37; // rdx
  size_t v38; // rbx
  void **v39; // rdx
  HLOCAL v40; // rcx
  HLOCAL v41; // rcx
  __int64 v42; // rdx
  unsigned int v43; // eax
  __int64 v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rdx
  const char *v47; // rdx
  const char *v48; // rax
  HLOCAL v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // rdx
  size_t v52; // rbx
  void **v53; // rdx
  HLOCAL v54; // rcx
  HLOCAL v55; // rcx
  __int64 v56; // rdx
  unsigned int v57; // eax
  __int64 v58; // rcx
  __int64 v59; // rax
  __int64 v60; // rdx
  const char *v61; // rdx
  const char *v62; // rax
  HLOCAL v63; // r8
  __int64 v64; // rdx
  int v65; // ecx
  __int64 *v66; // rax
  __int64 v67; // rcx
  __int64 v68; // rbx
  const char *v69; // rdx
  const char *v70; // rax
  int v71; // [rsp+20h] [rbp-E0h]
  int v72; // [rsp+20h] [rbp-E0h]
  __int64 v73; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v74; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v75; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL v76; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL v77; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v78; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL lpMem; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-98h] BYREF
  __int128 v81; // [rsp+70h] [rbp-90h] BYREF
  __int64 v82; // [rsp+80h] [rbp-80h]
  _BYTE v83[8]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v84; // [rsp+90h] [rbp-70h] BYREF
  __int64 v85; // [rsp+A0h] [rbp-60h]
  _BYTE v86[8]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v87[8]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD *v88; // [rsp+B8h] [rbp-48h]
  _BYTE v89[64]; // [rsp+C0h] [rbp-40h] BYREF
  void *Src[2]; // [rsp+100h] [rbp+0h] BYREF
  size_t Size[2]; // [rsp+110h] [rbp+10h]
  GUID pclsid; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v93[296]; // [rsp+140h] [rbp+40h] BYREF
  int v94; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+2C8h]

  v88 = a2;
  v74 = 0;
  v3 = a2;
  v4 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>::ensure_data(&v74);
  tip2::details::shared_data<1,0,0>::start(*v4 + 8LL, Src);
  tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>((struct wil::details::IFailureCallback *)v89);
  memset_0(v93, 0, 0x238u);
  v73 = 0;
  hMem = 0;
  v75 = 0;
  lpMem = 0;
  v94 = a1;
  if ( v74 )
    v5 = *(GUID *)(v74 + 152);
  else
    v5 = 0;
  pclsid = v5;
  v6 = I_EncodeAndSendRpcRequest(0x67u, &pclsid, (struct _CTAPCBOR_RPC_REQUEST *)v93, &v75, (unsigned __int8 **)&lpMem);
  v8 = v6;
  if ( v6 < 0 )
  {
    if ( v6 == -2146893807 )
    {
      v9 = operator new(0x10u);
      v78 = 0;
      *v9 = 0;
      v9[1] = 0;
      *v3 = v9;
      v11 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginGetAuthenticatorListTest::reason::no_authenticators_found",
              v10);
      tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>::set_flag(
        &v74,
        2,
        v11);
      std::unique_ptr<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST>::~unique_ptr<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST>(&v78);
      v8 = 0;
    }
    else
    {
      v12 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginGetAuthenticatorListTest::reason::generic_failure",
              v7);
      v13 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>::ensure_data(&v74);
      tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(*v13 + 8LL, 1, v12, v8);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41F,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)v8,
        v71);
    }
LABEL_14:
    wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&void WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&void WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>(&v73);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>(v89);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>,wil::err_returncode_policy>(&v74);
    return v8;
  }
  v14 = CtapCborDecodePluginAuthenticatorStateList(
          v75,
          (_DWORD)lpMem,
          (unsigned int)&hMem,
          (unsigned int)v83,
          (__int64)&v76);
  CtapCltFree(lpMem);
  if ( v14 )
  {
    v16 = tip2::details::reason_string(
            (tip2::details *)"WebAuthNPluginGetAuthenticatorListTest::reason::decoding_failed",
            v15);
    tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>::set_flag(
      &v74,
      3,
      v16);
    v17 = CtapCborErrorToWin32Error(v14);
    v18 = v17;
    if ( v17 > 0 )
      v18 = (unsigned __int16)v17 | 0x80070000;
    if ( v18 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x42C,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
        (const char *)(unsigned int)v18,
        v72);
    v8 = v18;
    goto LABEL_14;
  }
  v20 = hMem;
  v21 = LocalAlloc(0x40u, 8LL * *(unsigned int *)hMem + 16);
  wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&void WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>::reset(
    &v73,
    v21);
  v22 = (_DWORD *)v73;
  if ( v73 )
  {
    v23 = *(_DWORD *)v20;
    *(_QWORD *)(v73 + 8) = v73 + 16;
    v24 = 0;
    *v22 = v23;
    v85 = 0;
    v82 = 0;
    v84 = 0;
    v75 = 0;
    v81 = 0;
    if ( *(_DWORD *)v20 )
    {
      do
      {
        wil::make_unique_hlocal<_WEBAUTHN_PLUGIN_AUTHENTICATOR_DISPLAY_INFO,>(&v73);
        v25 = v24;
        v26 = (__int64 *)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                           v86,
                           **(_QWORD **)(v20[1] + 8LL * v24),
                           -1);
        v27 = *v26;
        *v26 = 0;
        *(_QWORD *)v73 = v27;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(v86);
        v28 = (__int64 *)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                           v87,
                           *(_QWORD *)(*(_QWORD *)(v20[1] + 8LL * v24) + 8LL),
                           -1);
        v29 = *v28;
        *v28 = 0;
        *(_QWORD *)(v73 + 8) = v29;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(v87);
        std::wstring::wstring(Src, **(_QWORD **)(v20[1] + 8LL * v24));
        v30 = *((_QWORD *)&v84 + 1);
        if ( *((_QWORD *)&v84 + 1) == v85 )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v84, *((_QWORD *)&v84 + 1), Src);
        }
        else
        {
          v31 = *(_OWORD *)Size;
          Size[0] = 0;
          v32 = *(_OWORD *)Src;
          Size[1] = 7;
          LOWORD(Src[0]) = 0;
          **((_OWORD **)&v84 + 1) = v32;
          *(_OWORD *)(v30 + 16) = v31;
          *((_QWORD *)&v84 + 1) += 32LL;
        }
        std::wstring::_Tidy_deallocate(Src);
        if ( a1 )
        {
          v33 = 8;
          if ( a1 == 3 )
            v33 = 16;
          v34 = LocalAlloc(0x40u, v33);
          v35 = 0;
          *(_QWORD *)(v73 + 24) = v34;
          if ( ((a1 - 1) & 0xFFFFFFFD) == 0 )
          {
            wil::make_unique_hlocal<_EXPERIMENTAL_WEBAUTHN_PLUGIN_ADD_AUTHENTICATOR_RESPONSE,>(&v76);
            v36 = *(_QWORD *)(v20[1] + 8 * v25);
            v37 = *(_QWORD *)(v36 + 24);
            if ( v37 )
            {
              std::wstring::wstring(&pclsid, v37);
              anonymous_namespace_::Utf16ToUtf8(Src, &pclsid);
              std::wstring::_Tidy_deallocate(&pclsid);
              v38 = Size[0];
              wil::make_unique_hlocal<unsigned char [0]>(&hMem, Size[0]);
              v39 = Src;
              if ( Size[1] > 0xF )
                v39 = (void **)Src[0];
              memcpy_0(hMem, v39, v38);
              v40 = hMem;
              hMem = 0;
              *((_QWORD *)v76 + 1) = v40;
              *((_DWORD *)v76 + 1) = v38 - 1;
              *(_DWORD *)v76 = 0;
              v41 = hMem;
              hMem = 0;
              if ( v41 )
                LocalFree(v41);
              std::string::_Tidy_deallocate(Src);
            }
            else
            {
              v78 = 0;
              pclsid = 0;
              if ( CLSIDFromString(*(LPCOLESTR *)(v36 + 16), &pclsid) >= 0 )
              {
                *(GUID *)Src = pclsid;
                if ( (int)WebAuthNAuthenticatorDBGetInfo(Src) < 0 )
                {
                  v45 = std::wstring::wstring(Src, *(_QWORD *)(*(_QWORD *)(v20[1] + 8 * v25) + 16LL));
                  v46 = *((_QWORD *)&v81 + 1);
                  if ( *((_QWORD *)&v81 + 1) == v82 )
                  {
                    std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v81, *((_QWORD *)&v81 + 1), v45);
                  }
                  else
                  {
                    **((_OWORD **)&v81 + 1) = 0;
                    *(_QWORD *)(v46 + 16) = 0;
                    *(_QWORD *)(v46 + 24) = 0;
                    *(_OWORD *)v46 = *(_OWORD *)v45;
                    *(_OWORD *)(v46 + 16) = *(_OWORD *)(v45 + 16);
                    *(_QWORD *)(v45 + 16) = 0;
                    *(_QWORD *)(v45 + 24) = 7;
                    *(_WORD *)v45 = 0;
                    *((_QWORD *)&v81 + 1) += 32LL;
                  }
                  std::wstring::_Tidy_deallocate(Src);
                  v48 = tip2::details::reason_string(
                          (tip2::details *)"WebAuthNPluginGetAuthenticatorListTest::reason::webauthn_authenticator_db_get_info_failed",
                          v47);
                  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>::set_flag(
                    &v74,
                    4,
                    v48);
                }
                else
                {
                  v42 = v78;
                  if ( *(_DWORD *)(v78 + 8) )
                  {
                    v43 = 0;
                    while ( 1 )
                    {
                      v44 = *(_QWORD *)(*(_QWORD *)(v78 + 16) + 8LL * v43);
                      if ( !*(_DWORD *)v44 )
                        break;
                      if ( ++v43 >= *(_DWORD *)(v78 + 8) )
                        goto LABEL_42;
                    }
                    *((_QWORD *)v76 + 1) = *(_QWORD *)(v44 + 8);
                    *((_DWORD *)v76 + 1) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v42 + 16) + 8LL * v43) + 4LL);
                    *(_DWORD *)v76 = 0;
                  }
                }
              }
            }
LABEL_42:
            v49 = v76;
            if ( *((_QWORD *)v76 + 1) )
            {
              v35 = 1;
              v76 = 0;
              **(_QWORD **)(v73 + 24) = v49;
              v49 = v76;
            }
            v76 = 0;
            if ( v49 )
              LocalFree(v49);
            if ( a1 == 3 )
              goto LABEL_48;
          }
          if ( a1 == 2 )
          {
LABEL_48:
            wil::make_unique_hlocal<_EXPERIMENTAL_WEBAUTHN_PLUGIN_ADD_AUTHENTICATOR_RESPONSE,>(&v77);
            v50 = *(_QWORD *)(v20[1] + 8 * v25);
            v51 = *(_QWORD *)(v50 + 32);
            if ( v51 )
            {
              std::wstring::wstring(&pclsid, v51);
              anonymous_namespace_::Utf16ToUtf8(Src, &pclsid);
              std::wstring::_Tidy_deallocate(&pclsid);
              v52 = Size[0];
              wil::make_unique_hlocal<unsigned char [0]>(&lpMem, Size[0]);
              v53 = Src;
              if ( Size[1] > 0xF )
                v53 = (void **)Src[0];
              memcpy_0(lpMem, v53, v52);
              v54 = lpMem;
              lpMem = 0;
              *((_QWORD *)v77 + 1) = v54;
              *((_DWORD *)v77 + 1) = v52 - 1;
              *(_DWORD *)v77 = 1;
              v55 = lpMem;
              lpMem = 0;
              if ( v55 )
                LocalFree(v55);
              std::string::_Tidy_deallocate(Src);
            }
            else
            {
              v78 = 0;
              pclsid = 0;
              if ( CLSIDFromString(*(LPCOLESTR *)(v50 + 16), &pclsid) >= 0 )
              {
                *(GUID *)Src = pclsid;
                if ( (int)WebAuthNAuthenticatorDBGetInfo(Src) < 0 )
                {
                  v59 = std::wstring::wstring(Src, *(_QWORD *)(*(_QWORD *)(v20[1] + 8 * v25) + 16LL));
                  v60 = *((_QWORD *)&v81 + 1);
                  if ( *((_QWORD *)&v81 + 1) == v82 )
                  {
                    std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v81, *((_QWORD *)&v81 + 1), v59);
                  }
                  else
                  {
                    **((_OWORD **)&v81 + 1) = 0;
                    *(_QWORD *)(v60 + 16) = 0;
                    *(_QWORD *)(v60 + 24) = 0;
                    *(_OWORD *)v60 = *(_OWORD *)v59;
                    *(_OWORD *)(v60 + 16) = *(_OWORD *)(v59 + 16);
                    *(_QWORD *)(v59 + 16) = 0;
                    *(_QWORD *)(v59 + 24) = 7;
                    *(_WORD *)v59 = 0;
                    *((_QWORD *)&v81 + 1) += 32LL;
                  }
                  std::wstring::_Tidy_deallocate(Src);
                  v62 = tip2::details::reason_string(
                          (tip2::details *)"WebAuthNPluginGetAuthenticatorListTest::reason::webauthn_authenticator_db_get_info_failed",
                          v61);
                  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>::set_flag(
                    &v74,
                    4,
                    v62);
                }
                else
                {
                  v56 = v78;
                  if ( *(_DWORD *)(v78 + 8) )
                  {
                    v57 = 0;
                    while ( 1 )
                    {
                      v58 = *(_QWORD *)(*(_QWORD *)(v78 + 16) + 8LL * v57);
                      if ( *(_DWORD *)v58 == 1 )
                        break;
                      if ( ++v57 >= *(_DWORD *)(v78 + 8) )
                        goto LABEL_66;
                    }
                    *((_QWORD *)v77 + 1) = *(_QWORD *)(v58 + 8);
                    *((_DWORD *)v77 + 1) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v56 + 16) + 8LL * v57) + 4LL);
                    *(_DWORD *)v77 = 1;
                  }
                }
              }
            }
LABEL_66:
            v63 = v77;
            if ( *((_QWORD *)v77 + 1) )
            {
              v77 = 0;
              v64 = v35++;
              *(_QWORD *)(*(_QWORD *)(v73 + 24) + 8 * v64) = v63;
              v63 = v77;
            }
            v77 = 0;
            if ( v63 )
              LocalFree(v63);
          }
          v65 = v35;
          v24 = v75;
          *(_DWORD *)(v73 + 16) = v65;
        }
        *(_DWORD *)(v73 + 32) = *(_DWORD *)(*(_QWORD *)(v20[1] + 8 * v25) + 40LL);
        v66 = (__int64 *)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                           v83,
                           *(_QWORD *)(*(_QWORD *)(v20[1] + 8 * v25) + 48LL),
                           -1);
        v67 = *v66;
        *v66 = 0;
        *(_QWORD *)(v73 + 40) = v67;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(v83);
        ++v24;
        *(_QWORD *)&v22[2 * v25 + 4] = v73;
        v73 = 0;
        v75 = v24;
      }
      while ( v24 < *(_DWORD *)v20 );
      v3 = v88;
    }
    v68 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>::ensure_data(&v74);
    v78 = v68;
    if ( v68 )
      _InterlockedAdd((volatile signed __int32 *)(v68 + 328), 1u);
    tip2::details::shared_data<1,0,0>::begin_update(v68 + 8);
    *(_DWORD *)(v68 + 320) = *(_DWORD *)v20;
    if ( (__int128 *)(v68 + 296) != &v81 )
      std::vector<std::wstring>::_Assign_counted_range<std::wstring *>(
        v68 + 296,
        v81,
        (__int64)(*((_QWORD *)&v81 + 1) - v81) >> 5);
    tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>::close(&v78);
    v73 = 0;
    *v3 = v22;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
    {
      v70 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginGetAuthenticatorListTest::reason::authenticator_list_created",
              v69);
      tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>::set_flag(
        &v74,
        8,
        v70);
    }
    if ( v74 )
      tip2::details::shared_data<1,0,0>::complete_without_lock(v74 + 8);
    tip2::test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>::~test_data_control<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>(&v78);
    std::vector<std::wstring>::_Tidy(&v81);
    std::vector<std::wstring>::_Tidy(&v84);
    wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&void WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&void WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>(&v73);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>(v89);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>,wil::err_returncode_policy>(&v74);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x431,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnplugin.cpp",
      (const char *)0x8007000ELL,
      v72);
    wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&void WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&void WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>(&v73);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>(v89);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>,wil::err_returncode_policy>(&v74);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800bc390  mov     [rsp-8+arg_10], rbx
0x1800bc395  push    rbp
0x1800bc396  push    rsi
0x1800bc397  push    rdi
0x1800bc398  push    r12
0x1800bc39a  push    r13
0x1800bc39c  push    r14
0x1800bc39e  push    r15
0x1800bc3a0  lea     rbp, [rsp-290h]
0x1800bc3a8  sub     rsp, 390h
0x1800bc3af  mov     rax, cs:__security_cookie
0x1800bc3b6  xor     rax, rsp
0x1800bc3b9  mov     [rbp+2C0h+var_40], rax
0x1800bc3c0  mov     r14d, ecx
0x1800bc3c3  mov     [rbp+2C0h+var_308], rdx
0x1800bc3c7  xor     esi, esi
0x1800bc3c9  lea     rcx, [rsp+3C0h+var_388]
0x1800bc3ce  mov     [rsp+3C0h+var_388], rsi
0x1800bc3d3  mov     r12, rdx
0x1800bc3d6  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginGetAuthenticatorListTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginGetAuthenticatorListTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>::ensure_data(void)
0x1800bc3db  lea     rdx, [rbp+2C0h+Src]
0x1800bc3df  mov     rcx, [rax]
0x1800bc3e2  add     rcx, 8
0x1800bc3e6  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x1800bc3eb  lea     rdx, [rsp+3C0h+var_388]
0x1800bc3f0  lea     rcx, [rbp+2C0h+var_300]; struct wil::details::IFailureCallback *
0x1800bc3f4  call    ??0?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginGetAuthenticatorListTest@@U1@@details@tip2@@@tip2@@IEAA@AEAV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginGetAuthenticatorListTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>,wil::err_returncode_policy> &)
0x1800bc3f9  xor     edx, edx; Val
0x1800bc3fb  lea     rcx, [rbp+2C0h+var_280]; void *
0x1800bc3ff  mov     r8d, 238h; Size
0x1800bc405  call    memset_0
0x1800bc40a  mov     rax, [rsp+3C0h+var_388]
0x1800bc40f  mov     [rsp+3C0h+var_390], rsi
0x1800bc414  mov     [rsp+3C0h+hMem], rsi
0x1800bc419  mov     [rsp+3C0h+var_380], esi
0x1800bc41d  mov     [rsp+3C0h+lpMem], rsi
0x1800bc422  mov     [rbp+2C0h+var_158], r14d
0x1800bc429  test    rax, rax
0x1800bc42c  jz      short loc_1800BC437
0x1800bc42e  movups  xmm0, xmmword ptr [rax+98h]
0x1800bc435  jmp     short loc_1800BC43A
0x1800bc437  xorps   xmm0, xmm0
0x1800bc43a  lea     rax, [rsp+3C0h+lpMem]
0x1800bc43f  movdqa  xmmword ptr [rbp+2C0h+pclsid.Data1], xmm0
0x1800bc444  lea     r9, [rsp+3C0h+var_380]; unsigned int *
0x1800bc449  mov     qword ptr [rsp+3C0h+var_3A0], rax; int
0x1800bc44e  lea     r8, [rbp+2C0h+var_280]; struct _CTAPCBOR_RPC_REQUEST *
0x1800bc452  mov     ecx, 67h ; 'g'; unsigned int
0x1800bc457  lea     rdx, [rbp+2C0h+pclsid]; struct _GUID *
0x1800bc45b  call    ?I_EncodeAndSendRpcRequest@@YAJKU_GUID@@AEAU_CTAPCBOR_RPC_REQUEST@@PEAKPEAPEAE@Z; I_EncodeAndSendRpcRequest(ulong,_GUID,_CTAPCBOR_RPC_REQUEST &,ulong *,uchar * *)
0x1800bc460  mov     edi, eax
0x1800bc462  test    eax, eax
0x1800bc464  jns     loc_1800BC50A
0x1800bc46a  cmp     eax, 80090011h
0x1800bc46f  jnz     short loc_1800BC4BA
0x1800bc471  mov     ecx, 10h; Size
0x1800bc476  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bc47b  lea     rcx, aWebauthnplugin_127; "WebAuthNPluginGetAuthenticatorListTest:"...
0x1800bc482  mov     [rsp+3C0h+var_368], rsi
0x1800bc487  mov     [rax], rsi
0x1800bc48a  mov     [rax+8], rsi
0x1800bc48e  mov     [r12], rax
0x1800bc492  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bc497  mov     r8, rax
0x1800bc49a  lea     rcx, [rsp+3C0h+var_388]
0x1800bc49f  mov     edx, 2
0x1800bc4a4  call    ?set_flag@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginGetAuthenticatorListTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>::set_flag(ushort,char const *)
0x1800bc4a9  lea     rcx, [rsp+3C0h+var_368]
0x1800bc4ae  call    ??1?$unique_ptr@U_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST@@U?$default_delete@U_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST@@@std@@@std@@QEAA@XZ; std::unique_ptr<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST>::~unique_ptr<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST>(void)
0x1800bc4b3  mov     edi, esi
0x1800bc4b5  jmp     loc_1800BC590
0x1800bc4ba  lea     rcx, aWebauthnplugin_147; "WebAuthNPluginGetAuthenticatorListTest:"...
0x1800bc4c1  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bc4c6  lea     rcx, [rsp+3C0h+var_388]
0x1800bc4cb  mov     rbx, rax
0x1800bc4ce  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginGetAuthenticatorListTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginGetAuthenticatorListTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>::ensure_data(void)
0x1800bc4d3  mov     edx, 1
0x1800bc4d8  mov     r9d, edi
0x1800bc4db  mov     r8, rbx
0x1800bc4de  mov     rcx, [rax]
0x1800bc4e1  add     rcx, 8
0x1800bc4e5  call    ??$set_flag_value_without_lock@J@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBDJ@Z; tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(ushort,char const *,long)
0x1800bc4ea  mov     rcx, [rbp+2C8h]; this
0x1800bc4f1  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bc4f8  mov     r9d, edi; char *
0x1800bc4fb  mov     edx, 41Fh; void *
0x1800bc500  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc505  jmp     loc_1800BC590
0x1800bc50a  mov     rdx, [rsp+3C0h+lpMem]
0x1800bc50f  lea     rax, [rsp+3C0h+var_378]
0x1800bc514  mov     ecx, [rsp+3C0h+var_380]
0x1800bc518  lea     r9, [rbp+2C0h+var_338]
0x1800bc51c  lea     r8, [rsp+3C0h+hMem]
0x1800bc521  mov     qword ptr [rsp+3C0h+var_3A0], rax; int
0x1800bc526  call    CtapCborDecodePluginAuthenticatorStateList
0x1800bc52b  mov     rcx, [rsp+3C0h+lpMem]; lpMem
0x1800bc530  mov     ebx, eax
0x1800bc532  call    CtapCltFree
0x1800bc537  test    ebx, ebx
0x1800bc539  jz      short loc_1800BC5B4
0x1800bc53b  lea     rcx, aWebauthnplugin_60; "WebAuthNPluginGetAuthenticatorListTest:"...
0x1800bc542  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800bc547  mov     r8, rax
0x1800bc54a  lea     rcx, [rsp+3C0h+var_388]
0x1800bc54f  mov     edx, 3
0x1800bc554  call    ?set_flag@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginGetAuthenticatorListTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>::set_flag(ushort,char const *)
0x1800bc559  mov     ecx, ebx
0x1800bc55b  call    CtapCborErrorToWin32Error
0x1800bc560  mov     ebx, eax
0x1800bc562  test    eax, eax
0x1800bc564  jle     short loc_1800BC56F
0x1800bc566  movzx   ebx, ax
0x1800bc569  or      ebx, 80070000h
0x1800bc56f  test    ebx, ebx
0x1800bc571  jns     short loc_1800BC58E
0x1800bc573  mov     rcx, [rbp+2C8h]; this
0x1800bc57a  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\fido\\webauthn\\"...
0x1800bc581  mov     r9d, ebx; char *
0x1800bc584  mov     edx, 42Ch; void *
0x1800bc589  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc58e  mov     edi, ebx
0x1800bc590  lea     rcx, [rsp+3C0h+var_390]
0x1800bc595  call    ??1?$unique_storage@U?$resource_policy@PEAU_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST@@P6AXPEAU1@@Z$1?WebAuthNPluginFreeAuthenticatorList@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>(void)
0x1800bc59a  lea     rcx, [rbp+2C0h+var_300]
0x1800bc59e  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginGetAuthenticatorListTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>>(void)
0x1800bc5a3  lea     rcx, [rsp+3C0h+var_388]
0x1800bc5a8  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginGetAuthenticatorListTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>,wil::err_returncode_policy>(void)
0x1800bc5ad  mov     eax, edi
0x1800bc5af  jmp     loc_1800BCD1A
0x1800bc5b4  mov     rdi, [rsp+3C0h+hMem]
0x1800bc5b9  mov     ecx, 40h ; '@'; uFlags
0x1800bc5be  mov     edx, [rdi]
0x1800bc5c0  lea     rdx, ds:10h[rdx*8]; uBytes
0x1800bc5c8  call    cs:__imp_LocalAlloc
0x1800bc5ce  mov     rdx, rax
0x1800bc5d1  lea     rcx, [rsp+3C0h+var_390]
0x1800bc5d6  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST@@P6AXPEAU1@@Z$1?WebAuthNPluginFreeAuthenticatorList@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST@@@Z; wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,void (*)(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),&WebAuthNPluginFreeAuthenticatorList(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *,0,std::nullptr_t>>::reset(_WEBAUTHN_PLUGIN_AUTHENTICATOR_LIST *)
0x1800bc5db  mov     r15, [rsp+3C0h+var_390]
0x1800bc5e0  test    r15, r15
0x1800bc5e3  jz      loc_1800BCCDB
0x1800bc5e9  mov     eax, [rdi]
0x1800bc5eb  lea     rcx, [r15+10h]
0x1800bc5ef  mov     [r15+8], rcx
0x1800bc5f3  mov     r13d, esi
0x1800bc5f6  mov     [r15], eax
0x1800bc5f9  xorps   xmm0, xmm0
0x1800bc5fc  mov     [rbp+2C0h+var_320], rsi
0x1800bc600  xorps   xmm1, xmm1
0x1800bc603  mov     [rbp+2C0h+var_340], rsi
0x1800bc607  movdqu  [rbp+2C0h+var_330], xmm0
0x1800bc60c  mov     [rsp+3C0h+var_380], esi
0x1800bc610  mov     esi, 1
0x1800bc615  movdqu  [rsp+3C0h+var_350], xmm1
0x1800bc61b  cmp     [rdi], r13d
0x1800bc61e  jbe     loc_1800BCBEF
0x1800bc624  lea     ebx, [rsi+0Fh]
0x1800bc627  lea     rcx, [rsp+3C0h+var_390]
0x1800bc62c  call    ??$make_unique_hlocal@U_WEBAUTHN_PLUGIN_AUTHENTICATOR_DISPLAY_INFO@@$$V@wil@@YA?AV?$unique_ptr@U_WEBAUTHN_PLUGIN_AUTHENTICATOR_DISPLAY_INFO@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@XZ; wil::make_unique_hlocal<_WEBAUTHN_PLUGIN_AUTHENTICATOR_DISPLAY_INFO,>(void)
0x1800bc631  mov     rax, [rdi+8]
0x1800bc635  lea     rcx, [rbp+2C0h+var_318]
0x1800bc639  mov     r12d, r13d
0x1800bc63c  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800bc640  mov     rdx, [rax+r12*8]
0x1800bc644  mov     rdx, [rdx]
0x1800bc647  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800bc64c  mov     rcx, [rax]
0x1800bc64f  mov     qword ptr [rax], 0
0x1800bc656  mov     rax, [rsp+3C0h+var_390]
0x1800bc65b  mov     [rax], rcx
0x1800bc65e  lea     rcx, [rbp+2C0h+var_318]
0x1800bc662  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1800bc667  mov     rax, [rdi+8]
0x1800bc66b  lea     rcx, [rbp+2C0h+var_310]
0x1800bc66f  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800bc673  mov     rdx, [rax+r12*8]
0x1800bc677  mov     rdx, [rdx+8]
0x1800bc67b  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800bc680  mov     rcx, [rax]
0x1800bc683  mov     qword ptr [rax], 0
0x1800bc68a  mov     rax, [rsp+3C0h+var_390]
0x1800bc68f  mov     [rax+8], rcx
0x1800bc693  lea     rcx, [rbp+2C0h+var_310]
0x1800bc697  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1800bc69c  mov     rax, [rdi+8]
0x1800bc6a0  lea     rcx, [rbp+2C0h+Src]
0x1800bc6a4  mov     rdx, [rax+r12*8]
0x1800bc6a8  mov     rdx, [rdx]
0x1800bc6ab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800bc6b0  mov     rdx, qword ptr [rbp+2C0h+var_330+8]
0x1800bc6b4  cmp     rdx, [rbp+2C0h+var_320]
0x1800bc6b8  jz      short loc_1800BC6E6
0x1800bc6ba  movups  xmm1, xmmword ptr [rbp+2C0h+Size]
0x1800bc6be  xor     eax, eax
0x1800bc6c0  mov     [rbp+2C0h+Size], 0
0x1800bc6c8  movups  xmm0, xmmword ptr [rbp+2C0h+Src]
0x1800bc6cc  mov     [rbp+2C0h+Size+8], 7
0x1800bc6d4  mov     word ptr [rbp+2C0h+Src], ax
0x1800bc6d8  movups  xmmword ptr [rdx], xmm0
0x1800bc6db  movups  xmmword ptr [rdx+10h], xmm1
0x1800bc6df  add     qword ptr [rbp+2C0h+var_330+8], 20h ; ' '
0x1800bc6e4  jmp     short loc_1800BC6F3
0x1800bc6e6  lea     r8, [rbp+2C0h+Src]
0x1800bc6ea  lea     rcx, [rbp+2C0h+var_330]
0x1800bc6ee  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1800bc6f3  lea     rcx, [rbp+2C0h+Src]
0x1800bc6f7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800bc6fc  test    r14d, r14d
0x1800bc6ff  jz      loc_1800BCB7F
0x1800bc705  cmp     r14d, 3
0x1800bc709  mov     edx, 8
0x1800bc70e  mov     ecx, 40h ; '@'; uFlags
0x1800bc713  cmovz   rdx, rbx; uBytes
0x1800bc717  call    cs:__imp_LocalAlloc
0x1800bc71d  mov     rcx, [rsp+3C0h+var_390]
0x1800bc722  xor     ebx, ebx
0x1800bc724  mov     r13b, bl
0x1800bc727  mov     [rcx+18h], rax
0x1800bc72b  lea     eax, [r14-1]
0x1800bc72f  test    eax, 0FFFFFFFDh
0x1800bc734  jnz     loc_1800BC94D
0x1800bc73a  lea     rcx, [rsp+3C0h+var_378]
0x1800bc73f  call    ??$make_unique_hlocal@U_EXPERIMENTAL_WEBAUTHN_PLUGIN_ADD_AUTHENTICATOR_RESPONSE@@$$V@wil@@YA?AV?$unique_ptr@U_EXPERIMENTAL_WEBAUTHN_PLUGIN_ADD_AUTHENTICATOR_RESPONSE@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@XZ; wil::make_unique_hlocal<_EXPERIMENTAL_WEBAUTHN_PLUGIN_ADD_AUTHENTICATOR_RESPONSE,>(void)
0x1800bc744  mov     rax, [rdi+8]
0x1800bc748  mov     rcx, [rax+r12*8]
0x1800bc74c  mov     rdx, [rcx+18h]
0x1800bc750  test    rdx, rdx
0x1800bc753  jz      loc_1800BC7F2
0x1800bc759  lea     rcx, [rbp+2C0h+pclsid]
0x1800bc75d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800bc762  lea     rdx, [rbp+2C0h+pclsid]
0x1800bc766  lea     rcx, [rbp+2C0h+Src]
0x1800bc76a  call    _anonymous_namespace___Utf16ToUtf8
0x1800bc76f  lea     rcx, [rbp+2C0h+pclsid]
0x1800bc773  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800bc778  mov     rbx, [rbp+2C0h+Size]
0x1800bc77c  lea     rcx, [rsp+3C0h+hMem]
0x1800bc781  mov     rdx, rbx
0x1800bc784  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x1800bc789  cmp     [rbp+2C0h+Size+8], 0Fh
0x1800bc78e  lea     rdx, [rbp+2C0h+Src]
0x1800bc792  mov     rcx, [rsp+3C0h+hMem]; void *
0x1800bc797  mov     r8, rbx; Size
0x1800bc79a  cmova   rdx, [rbp+2C0h+Src]; Src
0x1800bc79f  call    memcpy_0
0x1800bc7a4  mov     rcx, [rsp+3C0h+hMem]
0x1800bc7a9  mov     rax, [rsp+3C0h+var_378]
0x1800bc7ae  mov     [rsp+3C0h+hMem], 0
0x1800bc7b7  mov     [rax+8], rcx
0x1800bc7bb  lea     ecx, [rbx-1]
0x1800bc7be  mov     rax, [rsp+3C0h+var_378]
0x1800bc7c3  xor     ebx, ebx
0x1800bc7c5  mov     [rax+4], ecx
0x1800bc7c8  mov     rax, [rsp+3C0h+var_378]
0x1800bc7cd  mov     [rax], ebx
0x1800bc7cf  mov     rcx, [rsp+3C0h+hMem]; hMem
0x1800bc7d4  mov     [rsp+3C0h+hMem], rbx
0x1800bc7d9  test    rcx, rcx
0x1800bc7dc  jz      short loc_1800BC7E4
0x1800bc7de  call    cs:__imp_LocalFree
0x1800bc7e4  lea     rcx, [rbp+2C0h+Src]
0x1800bc7e8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800bc7ed  jmp     loc_1800BC910
0x1800bc7f2  xorps   xmm0, xmm0
0x1800bc7f5  mov     [rsp+3C0h+var_368], rbx
0x1800bc7fa  movups  xmmword ptr [rbp+2C0h+pclsid.Data1], xmm0
0x1800bc7fe  mov     rcx, [rcx+10h]; lpsz
0x1800bc802  lea     rdx, [rbp+2C0h+pclsid]; pclsid
0x1800bc806  call    cs:__imp_CLSIDFromString
0x1800bc80c  test    eax, eax
0x1800bc80e  js      loc_1800BC910
0x1800bc814  movaps  xmm0, xmmword ptr [rbp+2C0h+pclsid.Data1]
0x1800bc818  lea     r8, [rsp+3C0h+var_368]
0x1800bc81d  mov     edx, r14d
0x1800bc820  movdqa  xmmword ptr [rbp+2C0h+Src], xmm0
0x1800bc825  lea     rcx, [rbp+2C0h+Src]; Buf1
0x1800bc829  call    WebAuthNAuthenticatorDBGetInfo
0x1800bc82e  test    eax, eax
0x1800bc830  js      short loc_1800BC889
0x1800bc832  mov     rdx, [rsp+3C0h+var_368]
0x1800bc837  cmp     [rdx+8], ebx
0x1800bc83a  jbe     loc_1800BC910
0x1800bc840  mov     r9, [rdx+10h]
0x1800bc844  mov     eax, ebx
0x1800bc846  mov     r8d, eax
0x1800bc849  mov     rcx, [r9+r8*8]
0x1800bc84d  cmp     [rcx], ebx
0x1800bc84f  jz      short loc_1800BC85D
0x1800bc851  add     eax, esi
0x1800bc853  cmp     eax, [rdx+8]
0x1800bc856  jb      short loc_1800BC846
0x1800bc858  jmp     loc_1800BC910
0x1800bc85d  mov     rax, [rsp+3C0h+var_378]
0x1800bc862  mov     rcx, [rcx+8]
0x1800bc866  mov     [rax+8], rcx
0x1800bc86a  mov     rax, [rdx+10h]
0x1800bc86e  mov     rcx, [rax+r8*8]
0x1800bc872  mov     rax, [rsp+3C0h+var_378]
0x1800bc877  mov     edx, [rcx+4]
0x1800bc87a  mov     [rax+4], edx
0x1800bc87d  mov     rax, [rsp+3C0h+var_378]
  ... truncated ...
```
