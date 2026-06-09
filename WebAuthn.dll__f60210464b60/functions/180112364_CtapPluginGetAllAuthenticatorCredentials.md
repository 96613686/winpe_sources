# CtapPluginGetAllAuthenticatorCredentials

- ea: `0x180112364`
- end: `0x180112933`
- name: `CtapPluginGetAllAuthenticatorCredentials`
- size: `1487`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800db2b4`

## callees

- `0x1800350b4`
- `0x180036da4`
- `0x18003a9e8`
- `0x18004349c`
- `0x1800467e0`
- `0x18004f5b4`
- `0x18005378c`
- `0x180072974`
- `0x18009b620`
- `0x1800b2918`
- `0x1800b2fc4`
- `0x18010c8d0`
- `0x18010e918`
- `0x180112364`
- `0x18011c42c`
- `0x180121b94`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011257e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011257e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180112872`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180112872`

## string_xrefs

- `0x180112417`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180112495`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801124cd`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18011251f`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801125e2`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801126b5`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801127d2`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18011284c`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180112752`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::credential_list_empty`
- `0x1801123d8`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::invalid_parameters`
- `0x180112457`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::invalid_parameters`
- `0x180112675`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::package_verification_failed`
- `0x18011258e`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::clsid_not_found`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 CtapPluginGetAllAuthenticatorCredentials(HANDLE token, __int128 *a2, const WCHAR *a3, ...)
{
  const char *v5; // rdx
  __int64 v6; // rax
  char v7; // bl
  const char *v8; // rax
  const char *v9; // rdx
  char v10; // r8
  __int64 result; // rax
  _DWORD *v12; // r14
  LPVOID *v13; // rdi
  const char *v14; // rax
  int UserPluginAuthenticatorsRegKey; // eax
  unsigned int v16; // ebx
  HKEY *v17; // rax
  LSTATUS v18; // eax
  const char *v19; // rdx
  HKEY v20; // r8
  signed int ShouldAllowPluginOperation; // ebx
  const char *v22; // rax
  bool v23; // sf
  const char *v24; // rdx
  const char *v25; // rax
  const char *v26; // r9
  int ExistingCredentials; // ebx
  const char *v28; // rdx
  const char *v29; // rax
  _BYTE *v30; // r9
  _BYTE *v31; // r10
  char v32; // r8
  void *v33; // rcx
  int phkResult; // [rsp+20h] [rbp-A8h]
  int phkResulta; // [rsp+20h] [rbp-A8h]
  __int128 v36; // [rsp+30h] [rbp-98h] BYREF
  void *Src[2]; // [rsp+40h] [rbp-88h] BYREF
  __int64 v38; // [rsp+50h] [rbp-78h]
  _BYTE v39[56]; // [rsp+60h] [rbp-68h] BYREF
  __int64 v40; // [rsp+98h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  void *v42; // [rsp+D8h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+E0h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+E8h] [rbp+20h] BYREF
  va_list hKeya; // [rsp+E8h] [rbp+20h]
  __int64 v46; // [rsp+F0h] [rbp+28h]
  __int64 v47; // [rsp+F8h] [rbp+30h] BYREF
  va_list va1; // [rsp+F8h] [rbp+30h]
  __int64 v49; // [rsp+100h] [rbp+38h]
  _DWORD *v50; // [rsp+108h] [rbp+40h]
  LPVOID *v51; // [rsp+110h] [rbp+48h]
  va_list va2; // [rsp+118h] [rbp+50h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(hKeya, a3);
  hKey = va_arg(va1, HKEY);
  v46 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  va_arg(va2, _QWORD);
  v49 = va_arg(va2, _QWORD);
  v50 = va_arg(va2, _DWORD *);
  v51 = va_arg(va2, LPVOID *);
  v47 = 0;
  v36 = *a2;
  tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::open_and_watch_errors(
    (__int64 *)va1,
    v39,
    &v36);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>((__int64 *)va1);
  if ( !a3 )
    goto LABEL_6;
  v6 = -1;
  do
    ++v6;
  while ( a3[v6] );
  if ( v6 )
    v7 = 1;
  else
LABEL_6:
    v7 = 1;
  v8 = tip2::details::reason_string(
         (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::invalid_parameters",
         v5);
  if ( v10 )
    tip2::details::shared_data<1,0,0>::set_flag_without_lock(v40 + 8, 2, v8);
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB00,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)0x80004003LL,
      phkResult);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v39);
    return 2147500035LL;
  }
  v12 = v50;
  v13 = v51;
  if ( v50 && v51 )
    v7 = 0;
  v14 = tip2::details::reason_string(
          (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::invalid_parameters",
          v9);
  if ( v7 )
    tip2::details::shared_data<1,0,0>::set_flag_without_lock(v40 + 8, 2, v14);
  if ( !v12 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB02,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)0x80004003LL,
      phkResult);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v39);
    return 2147500035LL;
  }
  if ( !v13 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB03,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)0x80004003LL,
      phkResult);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v39);
    return 2147500035LL;
  }
  *v12 = 0;
  *v13 = 0;
  hKey = 0;
  UserPluginAuthenticatorsRegKey = GetUserPluginAuthenticatorsRegKey((__int64)token, (__int64)hKeya);
  v16 = UserPluginAuthenticatorsRegKey;
  if ( UserPluginAuthenticatorsRegKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB08,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)(unsigned int)UserPluginAuthenticatorsRegKey,
      phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>((HKEY *)hKeya);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v39);
    return v16;
  }
  v42 = 0;
  v17 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v42);
  v18 = RegOpenKeyExW(hKey, a3, 0, 0xF003Fu, v17);
  try
  {
    ShouldAllowPluginOperation = v18;
    if ( v18 )
    {
      v22 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::clsid_not_found",
              v19);
      if ( ShouldAllowPluginOperation == 2 )
        tip2::details::shared_data<1,0,0>::set_flag_without_lock(v40 + 8, 5, v22);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
      {
        v23 = ShouldAllowPluginOperation < 0;
        if ( ShouldAllowPluginOperation > 0 )
        {
          ShouldAllowPluginOperation = (unsigned __int16)ShouldAllowPluginOperation | 0x80070000;
          v23 = ShouldAllowPluginOperation < 0;
        }
        if ( v23 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB10,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)(unsigned int)ShouldAllowPluginOperation,
            phkResulta);
      }
      else if ( ShouldAllowPluginOperation > 0 )
      {
        ShouldAllowPluginOperation = (unsigned __int16)ShouldAllowPluginOperation | 0x80070000;
      }
    }
    else
    {
      ShouldAllowPluginOperation = CtapPluginInternal::ShouldAllowPluginOperation(token, v42, v20);
      if ( ShouldAllowPluginOperation >= 0 )
      {
        *(_OWORD *)Src = 0;
        v38 = 0;
        ExistingCredentials = CtapPluginGetExistingCredentials(token, a3, Src);
        v29 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::credential_list_empty",
                v28);
        if ( v32 )
        {
          tip2::details::shared_data<1,0,0>::set_flag_without_lock(v40 + 8, 6, v29);
          v30 = Src[1];
          v31 = Src[0];
        }
        if ( v31 == v30 )
        {
          std::vector<unsigned char>::_Tidy(Src);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v42);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>((HKEY *)hKeya);
          tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v39);
          return 0;
        }
        else if ( ExistingCredentials >= 0 )
        {
          wil::make_unique_cotaskmem<unsigned char [0]>(&pv, v30 - v31);
          if ( pv )
          {
            memcpy_0(pv, Src[0], (char *)Src[1] - (char *)Src[0]);
            *v12 = LODWORD(Src[1]) - LODWORD(Src[0]);
            *v13 = pv;
            pv = 0;
            std::vector<unsigned char>::_Tidy(Src);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v42);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>((HKEY *)hKeya);
            tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v39);
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB2D,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
              (const char *)0x8007000ELL,
              phkResulta);
            v33 = pv;
            pv = 0;
            if ( v33 )
              CoTaskMemFree(v33);
            std::vector<unsigned char>::_Tidy(Src);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v42);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>((HKEY *)hKeya);
            tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v39);
            return 2147942414LL;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB29,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)(unsigned int)ExistingCredentials,
            phkResulta);
          std::vector<unsigned char>::_Tidy(Src);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v42);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>((HKEY *)hKeya);
          tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v39);
          return (unsigned int)ExistingCredentials;
        }
      }
      v25 = tip2::details::reason_string(
              (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::package_verification_failed",
              v24);
      tip2::details::shared_data<1,0,0>::set_flag_without_lock(v40 + 8, 4, v25);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB1D,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
          (const char *)(unsigned int)ShouldAllowPluginOperation,
          phkResulta);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v42);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>((HKEY *)hKeya);
    tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(v39);
    result = (unsigned int)ShouldAllowPluginOperation;
  }
  catch ( ... )
  {
    LODWORD(v46) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0xB36,
                     (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                     v26);
    return (unsigned int)v46;
  }
  return result;
}

```

## disassembly

```asm
0x180112364  mov     rax, rsp
0x180112367  mov     [rax+8], rbx
0x18011236b  mov     [rax+20h], r9
0x18011236f  push    rsi
0x180112370  push    rdi
0x180112371  push    r12
0x180112373  push    r14
0x180112375  push    r15
0x180112377  sub     rsp, 0A0h
0x18011237e  mov     rsi, r8
0x180112381  mov     r15, rcx
0x180112384  xor     r12d, r12d
0x180112387  mov     [rax+30h], r12
0x18011238b  movups  xmm0, xmmword ptr [rdx]
0x18011238e  movdqu  [rsp+0C8h+var_98], xmm0
0x180112394  lea     r8, [rsp+0C8h+var_98]
0x180112399  lea     rdx, [rax-68h]
0x18011239d  lea     rcx, [rax+30h]
0x1801123a1  call    ?open_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@2@U_GUID@@@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::open_and_watch_errors(_GUID)
0x1801123a6  lea     rcx, [rsp+0C8h+arg_28]
0x1801123ae  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>(void)
0x1801123b3  nop
0x1801123b4  test    rsi, rsi
0x1801123b7  jz      short loc_1801123D3
0x1801123b9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801123bd  inc     rax
0x1801123c0  cmp     [rsi+rax*2], r12w
0x1801123c5  jnz     short loc_1801123BD
0x1801123c7  test    rax, rax
0x1801123ca  jz      short loc_1801123D3
0x1801123cc  mov     r8b, r12b
0x1801123cf  mov     bl, 1
0x1801123d1  jmp     short loc_1801123D8
0x1801123d3  mov     bl, 1
0x1801123d5  mov     r8b, bl
0x1801123d8  lea     rcx, aWebauthnplugin_27; "WebAuthNPluginAuthenticatorGetAllCreden"...
0x1801123df  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1801123e4  test    r8b, r8b
0x1801123e7  jz      short loc_180112402
0x1801123e9  mov     edx, 2
0x1801123ee  mov     rcx, [rsp+0C8h+var_30]
0x1801123f6  add     rcx, 8
0x1801123fa  mov     r8, rax
0x1801123fd  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x180112402  test    rsi, rsi
0x180112405  jnz     short loc_18011243A
0x180112407  mov     rcx, [rsp+0C8h]; this
0x18011240f  mov     ebx, 80004003h
0x180112414  mov     r9d, ebx; char *
0x180112417  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18011241e  mov     edx, 0B00h; void *
0x180112423  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180112428  nop
0x180112429  lea     rcx, [rsp+0C8h+var_68]
0x18011242e  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(void)
0x180112433  mov     eax, ebx
0x180112435  jmp     loc_18011291A
0x18011243a  mov     r14, [rsp+0C8h+arg_38]
0x180112442  mov     rdi, [rsp+0C8h+arg_40]
0x18011244a  test    r14, r14
0x18011244d  jz      short loc_180112457
0x18011244f  test    rdi, rdi
0x180112452  jz      short loc_180112457
0x180112454  mov     bl, r12b
0x180112457  lea     rcx, aWebauthnplugin_27; "WebAuthNPluginAuthenticatorGetAllCreden"...
0x18011245e  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180112463  test    bl, bl
0x180112465  jz      short loc_180112480
0x180112467  mov     edx, 2
0x18011246c  mov     rcx, [rsp+0C8h+var_30]
0x180112474  add     rcx, 8
0x180112478  mov     r8, rax
0x18011247b  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x180112480  test    r14, r14
0x180112483  jnz     short loc_1801124B8
0x180112485  mov     rcx, [rsp+0C8h]; this
0x18011248d  mov     ebx, 80004003h
0x180112492  mov     r9d, ebx; char *
0x180112495  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18011249c  mov     edx, 0B02h; void *
0x1801124a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801124a6  nop
0x1801124a7  lea     rcx, [rsp+0C8h+var_68]
0x1801124ac  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(void)
0x1801124b1  mov     eax, ebx
0x1801124b3  jmp     loc_18011291A
0x1801124b8  test    rdi, rdi
0x1801124bb  jnz     short loc_1801124F0
0x1801124bd  mov     rcx, [rsp+0C8h]; this
0x1801124c5  mov     ebx, 80004003h
0x1801124ca  mov     r9d, ebx; char *
0x1801124cd  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1801124d4  mov     edx, 0B03h; void *
0x1801124d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801124de  nop
0x1801124df  lea     rcx, [rsp+0C8h+var_68]
0x1801124e4  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(void)
0x1801124e9  mov     eax, ebx
0x1801124eb  jmp     loc_18011291A
0x1801124f0  mov     [r14], r12d
0x1801124f3  mov     [rdi], r12
0x1801124f6  mov     [rsp+0C8h+hKey], r12
0x1801124fe  lea     rdx, [rsp+0C8h+hKey]
0x180112506  mov     rcx, r15
0x180112509  call    GetUserPluginAuthenticatorsRegKey
0x18011250e  mov     ebx, eax
0x180112510  test    eax, eax
0x180112512  jns     short loc_180112550
0x180112514  mov     rcx, [rsp+0C8h]; this
0x18011251c  mov     r9d, eax; char *
0x18011251f  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180112526  mov     edx, 0B08h; void *
0x18011252b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180112530  nop
0x180112531  lea     rcx, [rsp+0C8h+hKey]
0x180112539  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011253e  nop
0x18011253f  lea     rcx, [rsp+0C8h+var_68]
0x180112544  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(void)
0x180112549  mov     eax, ebx
0x18011254b  jmp     loc_18011291A
0x180112550  mov     [rsp+0C8h+arg_8], r12
0x180112558  lea     rcx, [rsp+0C8h+arg_8]
0x180112560  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180112565  mov     qword ptr [rsp+0C8h+phkResult], rax; int
0x18011256a  mov     r9d, 0F003Fh; samDesired
0x180112570  xor     r8d, r8d; ulOptions
0x180112573  mov     rdx, rsi; lpSubKey
0x180112576  mov     rcx, [rsp+0C8h+hKey]; hKey
0x18011257e  call    cs:__imp_RegOpenKeyExW
0x180112584  mov     ebx, eax
0x180112586  test    eax, eax
0x180112588  jz      loc_18011265B
0x18011258e  lea     rcx, aWebauthnplugin_106; "WebAuthNPluginAuthenticatorGetAllCreden"...
0x180112595  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18011259a  cmp     ebx, 2
0x18011259d  jnz     short loc_1801125B6
0x18011259f  lea     edx, [rbx+3]
0x1801125a2  mov     rcx, [rsp+0C8h+var_30]
0x1801125aa  add     rcx, 8
0x1801125ae  mov     r8, rax
0x1801125b1  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x1801125b6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1801125bd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1801125c2  test    al, al
0x1801125c4  jz      short loc_180112621
0x1801125c6  test    ebx, ebx
0x1801125c8  jle     short loc_1801125D5
0x1801125ca  movzx   ebx, bx
0x1801125cd  or      ebx, 80070000h
0x1801125d3  test    ebx, ebx
0x1801125d5  jns     short loc_1801125F4
0x1801125d7  mov     rcx, [rsp+0C8h]; this
0x1801125df  mov     r9d, ebx; char *
0x1801125e2  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1801125e9  mov     edx, 0B10h; void *
0x1801125ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801125f3  nop
0x1801125f4  lea     rcx, [rsp+0C8h+arg_8]
0x1801125fc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180112601  nop
0x180112602  lea     rcx, [rsp+0C8h+hKey]
0x18011260a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011260f  nop
0x180112610  lea     rcx, [rsp+0C8h+var_68]
0x180112615  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(void)
0x18011261a  mov     eax, ebx
0x18011261c  jmp     loc_18011291A
0x180112621  test    ebx, ebx
0x180112623  jle     short loc_18011262E
0x180112625  movzx   ebx, bx
0x180112628  or      ebx, 80070000h
0x18011262e  lea     rcx, [rsp+0C8h+arg_8]
0x180112636  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011263b  nop
0x18011263c  lea     rcx, [rsp+0C8h+hKey]
0x180112644  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180112649  nop
0x18011264a  lea     rcx, [rsp+0C8h+var_68]
0x18011264f  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(void)
0x180112654  mov     eax, ebx
0x180112656  jmp     loc_18011291A
0x18011265b  mov     rdx, [rsp+0C8h+arg_8]; void *
0x180112663  mov     rcx, r15; token
0x180112666  call    ?ShouldAllowPluginOperation@CtapPluginInternal@@YAJQEAXQEAUHKEY__@@@Z; CtapPluginInternal::ShouldAllowPluginOperation(void * const,HKEY__ * const)
0x18011266b  mov     ebx, eax
0x18011266d  test    eax, eax
0x18011266f  jns     loc_180112721
0x180112675  lea     rcx, aWebauthnplugin_141; "WebAuthNPluginAuthenticatorGetAllCreden"...
0x18011267c  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180112681  mov     r8, rax
0x180112684  mov     edx, 4
0x180112689  mov     rcx, [rsp+0C8h+var_30]
0x180112691  add     rcx, 8
0x180112695  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x18011269a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x1801126a1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x1801126a6  test    al, al
0x1801126a8  jz      short loc_1801126F4
0x1801126aa  mov     rcx, [rsp+0C8h]; this
0x1801126b2  mov     r9d, ebx; char *
0x1801126b5  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1801126bc  mov     edx, 0B1Dh; void *
0x1801126c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801126c6  nop
0x1801126c7  lea     rcx, [rsp+0C8h+arg_8]
0x1801126cf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801126d4  nop
0x1801126d5  lea     rcx, [rsp+0C8h+hKey]
0x1801126dd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801126e2  nop
0x1801126e3  lea     rcx, [rsp+0C8h+var_68]
0x1801126e8  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(void)
0x1801126ed  mov     eax, ebx
0x1801126ef  jmp     loc_18011291A
0x1801126f4  lea     rcx, [rsp+0C8h+arg_8]
0x1801126fc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180112701  nop
0x180112702  lea     rcx, [rsp+0C8h+hKey]
0x18011270a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011270f  nop
0x180112710  lea     rcx, [rsp+0C8h+var_68]
0x180112715  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(void)
0x18011271a  mov     eax, ebx
0x18011271c  jmp     loc_18011291A
0x180112721  xorps   xmm0, xmm0
0x180112724  movdqu  xmmword ptr [rsp+0C8h+Src], xmm0
0x18011272a  mov     [rsp+0C8h+var_78], r12
0x18011272f  lea     r8, [rsp+0C8h+Src]
0x180112734  mov     rdx, rsi
0x180112737  mov     rcx, r15
0x18011273a  call    ?CtapPluginGetExistingCredentials@@YAJQEAXPEBGAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; CtapPluginGetExistingCredentials(void * const,ushort const *,std::vector<uchar> &)
0x18011273f  mov     ebx, eax
0x180112741  mov     r10, [rsp+0C8h+Src]
0x180112746  mov     r9, [rsp+0C8h+Src+8]
0x18011274b  cmp     r10, r9
0x18011274e  setz    r8b
0x180112752  lea     rcx, aWebauthnplugin_68; "WebAuthNPluginAuthenticatorGetAllCreden"...
0x180112759  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18011275e  test    r8b, r8b
0x180112761  jz      short loc_180112786
0x180112763  mov     edx, 6
0x180112768  mov     rcx, [rsp+0C8h+var_30]
0x180112770  add     rcx, 8
0x180112774  mov     r8, rax
0x180112777  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x18011277c  mov     r9, [rsp+0C8h+Src+8]
0x180112781  mov     r10, [rsp+0C8h+Src]
0x180112786  cmp     r10, r9
0x180112789  jnz     short loc_1801127C3
0x18011278b  lea     rcx, [rsp+0C8h+Src]
0x180112790  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180112795  nop
0x180112796  lea     rcx, [rsp+0C8h+arg_8]
0x18011279e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801127a3  nop
0x1801127a4  lea     rcx, [rsp+0C8h+hKey]
0x1801127ac  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801127b1  nop
0x1801127b2  lea     rcx, [rsp+0C8h+var_68]
0x1801127b7  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(void)
0x1801127bc  xor     eax, eax
0x1801127be  jmp     loc_18011291A
0x1801127c3  test    ebx, ebx
0x1801127c5  jns     short loc_18011281C
0x1801127c7  mov     rcx, [rsp+0C8h]; this
0x1801127cf  mov     r9d, ebx; char *
0x1801127d2  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1801127d9  mov     edx, 0B29h; void *
0x1801127de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801127e3  nop
0x1801127e4  lea     rcx, [rsp+0C8h+Src]
0x1801127e9  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801127ee  nop
0x1801127ef  lea     rcx, [rsp+0C8h+arg_8]
0x1801127f7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801127fc  nop
0x1801127fd  lea     rcx, [rsp+0C8h+hKey]
0x180112805  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011280a  nop
0x18011280b  lea     rcx, [rsp+0C8h+var_68]
0x180112810  call    ??1?$test_watcher@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::~test_watcher<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>(void)
0x180112815  mov     eax, ebx
0x180112817  jmp     loc_18011291A
0x18011281c  sub     r9, r10
0x18011281f  mov     rdx, r9
0x180112822  lea     rcx, [rsp+0C8h+pv]
0x18011282a  call    ??$make_unique_cotaskmem@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<uchar [0]>(unsigned __int64)
0x18011282f  mov     rcx, [rsp+0C8h+pv]; void *
0x180112837  test    rcx, rcx
0x18011283a  jnz     short loc_1801128AE
0x18011283c  mov     rcx, [rsp+0C8h]; this
0x180112844  mov     ebx, 8007000Eh
0x180112849  mov     r9d, ebx; char *
0x18011284c  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180112853  mov     edx, 0B2Dh; void *
0x180112858  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011285d  mov     rcx, [rsp+0C8h+pv]; pv
0x180112865  mov     [rsp+0C8h+pv], r12
0x18011286d  test    rcx, rcx
  ... truncated ...
```
