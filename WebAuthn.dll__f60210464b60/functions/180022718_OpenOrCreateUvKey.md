# OpenOrCreateUvKey

- ea: `0x180022718`
- end: `0x180022c58`
- name: `OpenOrCreateUvKey`
- size: `1344`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800222d8`
- `0x180033970`

## callees

- `0x180017764`
- `0x180017a88`
- `0x18001ee7c`
- `0x180020584`
- `0x180020614`
- `0x180021878`
- `0x180021f78`
- `0x180022718`
- `0x180036da4`
- `0x180042ebc`
- `0x18004349c`
- `0x180043a6c`
- `0x1800467e0`
- `0x18004e08c`
- `0x18004f5b4`
- `0x1800510e8`
- `0x180052974`
- `0x18005e500`
- `0x18006b260`
- `0x18006f750`
- `0x1800ae560`
- `0x1800b29f8`
- `0x1800b715c`
- `0x18011c42c`
- `0x180120dcc`
- `0x180121120`
- `0x1801220ec`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180022b29`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180022b29`
- `ncrypt!NCryptOpenKey` at `0x1800228ae`
- `ncrypt!NCryptOpenKey` at `0x1800228ae`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800227f9`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800227f9`

## string_xrefs

- `0x180022772`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x1800227b6`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180022810`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x18002297b`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180022a77`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180022bfe`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180022b4a`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`
- `0x180022a36`: `WebAuthNPluginSetAuthenticatorStateTest::reason::uv_key_creation_succeeded_with_fallback`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall OpenOrCreateUvKey(__int64 a1, __int64 a2, __int64 a3, HKEY a4, NCRYPT_KEY_HANDLE *a5)
{
  NCRYPT_KEY_HANDLE *v8; // r12
  const char *v9; // r9
  int UvKeyName; // eax
  unsigned int v11; // ebx
  SECURITY_STATUS v13; // eax
  unsigned int v14; // ebx
  const WCHAR *v15; // rbx
  wil::reg::reg_view_details::reg_value_type_info *i; // rbx
  wil::reg::reg_view_details::reg_value_type_info *v17; // rdx
  int v18; // eax
  unsigned int v19; // edi
  __int64 v20; // r9
  wil::reg::reg_view_details::reg_value_type_info *v21; // rcx
  const char *v22; // rdx
  const char *v23; // rax
  int UserPluginAuthenticatorsRegKey; // eax
  unsigned int v25; // edi
  const unsigned __int16 *v26; // rdx
  DWORD cbData; // eax
  int v28; // eax
  NCRYPT_KEY_HANDLE v29; // rax
  int dwFlags; // [rsp+20h] [rbp-138h]
  int dwFlagsa; // [rsp+20h] [rbp-138h]
  int dwFlagsb; // [rsp+20h] [rbp-138h]
  LPCWSTR pszKeyName; // [rsp+30h] [rbp-128h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+38h] [rbp-120h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+40h] [rbp-118h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-110h] BYREF
  _QWORD v37[2]; // [rsp+50h] [rbp-108h] BYREF
  LPCVOID lpData[2]; // [rsp+60h] [rbp-F8h] BYREF
  char v39[8]; // [rsp+70h] [rbp-E8h] BYREF
  __int64 v40; // [rsp+78h] [rbp-E0h] BYREF
  wil::reg::reg_view_details::reg_value_type_info *v41; // [rsp+80h] [rbp-D8h]
  _QWORD v42[4]; // [rsp+90h] [rbp-C8h] BYREF
  _BYTE v43[32]; // [rsp+B0h] [rbp-A8h] BYREF
  char v44[32]; // [rsp+D0h] [rbp-88h] BYREF
  char v45[32]; // [rsp+F0h] [rbp-68h] BYREF
  __int64 v46; // [rsp+110h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]
  __int64 v48; // [rsp+168h] [rbp+10h] BYREF

  v48 = a2;
  hKey = a4;
  v8 = a5;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x9A,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
      v9);
  pszKeyName = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pszKeyName,
    0);
  UvKeyName = PluginGetUvKeyName(a1, a3, &pszKeyName);
  v11 = UvKeyName;
  if ( UvKeyName >= 0 )
  {
    phProvider = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
      &phProvider,
      0);
    v13 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Passport Key Storage Provider", 0);
    v14 = v13;
    if ( v13 >= 0 )
    {
      wil::impersonate_token(v39, a1);
      phKey = 0;
      v42[0] = &phProvider;
      v42[1] = &phKey;
      v42[2] = &pszKeyName;
      v42[3] = &v48;
      v15 = pszKeyName;
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
        &phKey,
        0);
      if ( NCryptOpenKey(phProvider, &phKey, v15, 0, 0) < 0 )
      {
        std::wstring::wstring(v43, L"ECDSA_P384");
        std::wstring::wstring(v44, L"ECDSA_P256");
        std::wstring::wstring(v45, L"RSA");
        lpData[0] = v43;
        lpData[1] = &v46;
        std::vector<std::wstring>::vector<std::wstring>(&v40, lpData);
        `eh vector destructor iterator'(
          v43,
          0x20u,
          3u,
          wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::~iterator_t<wil::reg::key_iterator_data<std::wstring>>);
        std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,unsigned short const *>(
          lpData,
          v40,
          v41,
          &hKey);
        for ( i = (wil::reg::reg_view_details::reg_value_type_info *)lpData[0];
              ;
              i = (wil::reg::reg_view_details::reg_value_type_info *)((char *)i + 32) )
        {
          if ( i == v41 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xF0,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
              (const char *)0x80090029LL,
              dwFlagsa);
            std::vector<std::wstring>::_Tidy(&v40);
            wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v39);
            wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszKeyName);
            return 2148073513LL;
          }
          v17 = *((_QWORD *)i + 3) <= 7u ? i : *(wil::reg::reg_view_details::reg_value_type_info **)i;
          v18 = OpenOrCreateUvKey_::_3_::_lambda_1_::operator()(v42, v17);
          v19 = v18;
          if ( v18 >= 0 )
            break;
          if ( v18 != -2146893783 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xEC,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
              (const char *)(unsigned int)v18,
              dwFlagsa);
            std::vector<std::wstring>::_Tidy(&v40);
            wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v39);
            wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszKeyName);
            return v19;
          }
        }
        v20 = -1;
        do
          ++v20;
        while ( *((_WORD *)a4 + v20) );
        if ( *((_QWORD *)i + 3) <= 7u )
          v21 = i;
        else
          v21 = *(wil::reg::reg_view_details::reg_value_type_info **)i;
        if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v21, *((_QWORD *)i + 2), a4, v20) )
        {
          lpData[0] = 0;
          tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::open_helper(
            lpData,
            0);
          v23 = tip2::details::reason_string(
                  (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::uv_key_creation_succeeded_with_fallback",
                  v22);
          tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::set_flag(
            lpData,
            14,
            v23);
          v37[0] = 0;
          UserPluginAuthenticatorsRegKey = GetUserPluginAuthenticatorsRegKey(a1, (__int64)v37);
          v25 = UserPluginAuthenticatorsRegKey;
          if ( UserPluginAuthenticatorsRegKey < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xE1,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
              (const char *)(unsigned int)UserPluginAuthenticatorsRegKey,
              dwFlagsa);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v37);
            wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(lpData);
            std::vector<std::wstring>::_Tidy(&v40);
            wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v39);
            wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszKeyName);
            return v25;
          }
          hKey = 0;
          if ( (int)wil::reg::open_unique_key_nothrow(v37[0], a3, &hKey, 0) >= 0 )
          {
            if ( *((_QWORD *)i + 3) > 7u )
              i = *(wil::reg::reg_view_details::reg_value_type_info **)i;
            cbData = wil::reg::reg_view_details::reg_value_type_info::get_buffer_size_bytes(i, v26);
            v28 = RegSetKeyValueW(hKey, 0, L"SigningKeyAlgorithm", 1u, i, cbData);
            if ( v28 > 0 )
              v28 = (unsigned __int16)v28 | 0x80070000;
            if ( v28 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1CBE,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
                (const char *)(unsigned int)v28,
                dwFlagsb);
          }
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v37);
          wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(lpData);
        }
        std::vector<std::wstring>::_Tidy(&v40);
      }
      v29 = phKey;
      phKey = 0;
      *v8 = v29;
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v39);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszKeyName);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)(unsigned int)v13,
        dwFlags);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszKeyName);
      return v14;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9D,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
      (const char *)(unsigned int)UvKeyName,
      dwFlags);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszKeyName);
    return v11;
  }
}

```

## disassembly

```asm
0x180022718  mov     [rsp+arg_8], rdx
0x18002271d  push    rbx
0x18002271e  push    rsi
0x18002271f  push    rdi
0x180022720  push    r12
0x180022722  push    r13
0x180022724  push    r14
0x180022726  push    r15
0x180022728  sub     rsp, 120h
0x18002272f  mov     rax, cs:__security_cookie
0x180022736  xor     rax, rsp
0x180022739  mov     [rsp+158h+var_48], rax
0x180022741  mov     r14, r9
0x180022744  mov     r15, r8
0x180022747  mov     rsi, rcx
0x18002274a  mov     [rsp+158h+hKey], r9
0x18002274f  mov     r12, [rsp+158h+arg_20]
0x180022757  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x18002275e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x180022763  mov     rcx, [rsp+158h]; this
0x18002276b  xor     r13d, r13d
0x18002276e  test    al, al
0x180022770  jz      short loc_180022784
0x180022772  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180022779  mov     edx, 9Ah; void *
0x18002277e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180022784  mov     [rsp+158h+pszKeyName], r13
0x180022789  xor     edx, edx
0x18002278b  lea     rcx, [rsp+158h+pszKeyName]
0x180022790  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180022795  lea     r8, [rsp+158h+pszKeyName]
0x18002279a  mov     rdx, r15
0x18002279d  mov     rcx, rsi
0x1800227a0  call    PluginGetUvKeyName
0x1800227a5  mov     ebx, eax
0x1800227a7  test    eax, eax
0x1800227a9  jns     short loc_1800227D9
0x1800227ab  mov     rcx, [rsp+158h]; this
0x1800227b3  mov     r9d, eax; char *
0x1800227b6  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1800227bd  mov     edx, 9Dh; void *
0x1800227c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800227c7  nop
0x1800227c8  lea     rcx, [rsp+158h+pszKeyName]
0x1800227cd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1800227d2  mov     eax, ebx
0x1800227d4  jmp     loc_180022BC8
0x1800227d9  mov     [rsp+158h+phProvider], r13
0x1800227de  xor     edx, edx
0x1800227e0  lea     rcx, [rsp+158h+phProvider]
0x1800227e5  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x1800227ea  xor     r8d, r8d; dwFlags
0x1800227ed  lea     rdx, pszProviderName; "Microsoft Passport Key Storage Provider"
0x1800227f4  lea     rcx, [rsp+158h+phProvider]; phProvider
0x1800227f9  call    cs:__imp_NCryptOpenStorageProvider
0x1800227ff  mov     ebx, eax
0x180022801  test    eax, eax
0x180022803  jns     short loc_18002283E
0x180022805  mov     rcx, [rsp+158h]; this
0x18002280d  mov     r9d, eax; char *
0x180022810  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180022817  mov     edx, 0A0h; void *
0x18002281c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022821  nop
0x180022822  lea     rcx, [rsp+158h+phProvider]
0x180022827  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18002282c  nop
0x18002282d  lea     rcx, [rsp+158h+pszKeyName]
0x180022832  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180022837  mov     eax, ebx
0x180022839  jmp     loc_180022BC8
0x18002283e  mov     rdx, rsi
0x180022841  lea     rcx, [rsp+158h+var_E8]
0x180022846  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x18002284b  nop
0x18002284c  mov     [rsp+158h+phKey], r13
0x180022851  lea     rax, [rsp+158h+phProvider]
0x180022856  mov     [rsp+158h+var_C8], rax
0x18002285e  lea     rax, [rsp+158h+phKey]
0x180022863  mov     [rsp+158h+var_C0], rax
0x18002286b  lea     rax, [rsp+158h+pszKeyName]
0x180022870  mov     [rsp+158h+var_B8], rax
0x180022878  lea     rax, [rsp+158h+arg_8]
0x180022880  mov     [rsp+158h+var_B0], rax
0x180022888  mov     rbx, [rsp+158h+pszKeyName]
0x18002288d  xor     edx, edx
0x18002288f  lea     rcx, [rsp+158h+phKey]
0x180022894  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x180022899  mov     [rsp+158h+dwFlags], r13d; int
0x18002289e  xor     r9d, r9d; dwLegacyKeySpec
0x1800228a1  mov     r8, rbx; pszKeyName
0x1800228a4  lea     rdx, [rsp+158h+phKey]; phKey
0x1800228a9  mov     rcx, [rsp+158h+phProvider]; hProvider
0x1800228ae  call    cs:__imp_NCryptOpenKey
0x1800228b4  test    eax, eax
0x1800228b6  jns     loc_180022B87
0x1800228bc  lea     rdx, aEcdsaP384; "ECDSA_P384"
0x1800228c3  lea     rcx, [rsp+158h+var_A8]
0x1800228cb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800228d0  nop
0x1800228d1  lea     rdx, pszAlgId; "ECDSA_P256"
0x1800228d8  lea     rcx, [rsp+158h+var_88]
0x1800228e0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800228e5  nop
0x1800228e6  lea     rdx, aRsa; "RSA"
0x1800228ed  lea     rcx, [rsp+158h+var_68]
0x1800228f5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800228fa  nop
0x1800228fb  lea     rax, [rsp+158h+var_A8]
0x180022903  mov     [rsp+158h+lpData], rax
0x180022908  lea     rax, [rsp+158h+var_48]
0x180022910  mov     [rsp+158h+var_F0], rax
0x180022915  lea     rdx, [rsp+158h+lpData]
0x18002291a  lea     rcx, [rsp+158h+var_E0]
0x18002291f  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@V?$initializer_list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::vector<std::wstring>::vector<std::wstring>(std::initializer_list<std::wstring>,std::allocator<std::wstring> const &)
0x180022924  nop
0x180022925  lea     r9, ??1?$iterator_t@V?$key_iterator_data@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@reg@wil@@@reg@wil@@QEAA@XZ; void (*)(void *)
0x18002292c  mov     edx, 20h ; ' '; unsigned __int64
0x180022931  lea     r8d, [rdx-1Dh]; unsigned __int64
0x180022935  lea     rcx, [rsp+158h+var_A8]; void *
0x18002293d  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180022942  lea     r9, [rsp+158h+hKey]
0x180022947  mov     r8, [rsp+158h+var_D8]
0x18002294f  mov     rdx, [rsp+158h+var_E0]
0x180022954  lea     rcx, [rsp+158h+lpData]
0x180022959  call    ??$find@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@PEBG@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@0@V10@V10@AEBQEBG@Z; std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,ushort const *>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,ushort const * const &)
0x18002295e  mov     rbx, [rsp+158h+lpData]
0x180022963  cmp     rbx, [rsp+158h+var_D8]
0x18002296b  jnz     short loc_1800229CD
0x18002296d  mov     rcx, [rsp+158h]; this
0x180022975  mov     r9d, 80090029h; char *
0x18002297b  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180022982  mov     edx, 0F0h; void *
0x180022987  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002298c  nop
0x18002298d  lea     rcx, [rsp+158h+var_E0]
0x180022992  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180022997  nop
0x180022998  lea     rcx, [rsp+158h+phKey]
0x18002299d  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800229a2  nop
0x1800229a3  lea     rcx, [rsp+158h+var_E8]
0x1800229a8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800229ad  nop
0x1800229ae  lea     rcx, [rsp+158h+phProvider]
0x1800229b3  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800229b8  nop
0x1800229b9  lea     rcx, [rsp+158h+pszKeyName]
0x1800229be  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1800229c3  mov     eax, 80090029h
0x1800229c8  jmp     loc_180022BC8
0x1800229cd  cmp     qword ptr [rbx+18h], 7
0x1800229d2  jbe     short loc_1800229D9
0x1800229d4  mov     rdx, [rbx]
0x1800229d7  jmp     short loc_1800229DC
0x1800229d9  mov     rdx, rbx
0x1800229dc  lea     rcx, [rsp+158h+var_C8]
0x1800229e4  call    _OpenOrCreateUvKey____3____lambda_1___operator__
0x1800229e9  mov     edi, eax
0x1800229eb  test    eax, eax
0x1800229ed  js      loc_180022BEB
0x1800229f3  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800229f7  inc     r9
0x1800229fa  cmp     [r14+r9*2], r13w
0x1800229ff  jnz     short loc_1800229F7
0x180022a01  cmp     qword ptr [rbx+18h], 7
0x180022a06  jbe     short loc_180022A0D
0x180022a08  mov     rcx, [rbx]
0x180022a0b  jmp     short loc_180022A10
0x180022a0d  mov     rcx, rbx
0x180022a10  mov     r8, r14
0x180022a13  mov     rdx, [rbx+10h]
0x180022a17  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180022a1c  test    al, al
0x180022a1e  jnz     loc_180022B7D
0x180022a24  mov     [rsp+158h+lpData], r13
0x180022a29  xor     edx, edx
0x180022a2b  lea     rcx, [rsp+158h+lpData]
0x180022a30  call    ?open_helper@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginSetAuthenticatorStateTest@@U1@@details@tip2@@@tip2@@AEAA_NPEAU_GUID@@@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::open_helper(_GUID *)
0x180022a35  nop
0x180022a36  lea     rcx, aWebauthnplugin_77; "WebAuthNPluginSetAuthenticatorStateTest"...
0x180022a3d  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180022a42  mov     r8, rax
0x180022a45  mov     edx, 0Eh
0x180022a4a  lea     rcx, [rsp+158h+lpData]
0x180022a4f  call    ?set_flag@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginSetAuthenticatorStateTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::set_flag(ushort,char const *)
0x180022a54  mov     [rsp+158h+var_108], r13
0x180022a59  lea     rdx, [rsp+158h+var_108]
0x180022a5e  mov     rcx, rsi
0x180022a61  call    GetUserPluginAuthenticatorsRegKey
0x180022a66  mov     edi, eax
0x180022a68  test    eax, eax
0x180022a6a  jns     short loc_180022ADC
0x180022a6c  mov     rcx, [rsp+158h]; this
0x180022a74  mov     r9d, eax; char *
0x180022a77  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180022a7e  mov     edx, 0E1h; void *
0x180022a83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022a88  nop
0x180022a89  lea     rcx, [rsp+158h+var_108]
0x180022a8e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180022a93  nop
0x180022a94  lea     rcx, [rsp+158h+lpData]
0x180022a99  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginSetAuthenticatorStateTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(void)
0x180022a9e  nop
0x180022a9f  lea     rcx, [rsp+158h+var_E0]
0x180022aa4  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180022aa9  nop
0x180022aaa  lea     rcx, [rsp+158h+phKey]
0x180022aaf  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180022ab4  nop
0x180022ab5  lea     rcx, [rsp+158h+var_E8]
0x180022aba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180022abf  nop
0x180022ac0  lea     rcx, [rsp+158h+phProvider]
0x180022ac5  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180022aca  nop
0x180022acb  lea     rcx, [rsp+158h+pszKeyName]
0x180022ad0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180022ad5  mov     eax, edi
0x180022ad7  jmp     loc_180022BC8
0x180022adc  mov     [rsp+158h+hKey], r13
0x180022ae1  xor     r9d, r9d
0x180022ae4  lea     r8, [rsp+158h+hKey]
0x180022ae9  mov     rdx, r15
0x180022aec  mov     rcx, [rsp+158h+var_108]
0x180022af1  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x180022af6  test    eax, eax
0x180022af8  js      short loc_180022B5C
0x180022afa  cmp     qword ptr [rbx+18h], 7
0x180022aff  jbe     short loc_180022B04
0x180022b01  mov     rbx, [rbx]
0x180022b04  mov     rcx, rbx; this
0x180022b07  call    ?get_buffer_size_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAKPEBG@Z; wil::reg::reg_view_details::reg_value_type_info::get_buffer_size_bytes(ushort const *)
0x180022b0c  mov     [rsp+158h+cbData], eax; cbData
0x180022b10  mov     qword ptr [rsp+158h+dwFlags], rbx; int
0x180022b15  mov     r9d, 1; dwType
0x180022b1b  lea     r8, ValueName; "SigningKeyAlgorithm"
0x180022b22  xor     edx, edx; lpSubKey
0x180022b24  mov     rcx, [rsp+158h+hKey]; hKey
0x180022b29  call    cs:__imp_RegSetKeyValueW
0x180022b2f  test    eax, eax
0x180022b31  jle     short loc_180022B3B
0x180022b33  movzx   eax, ax
0x180022b36  or      eax, 80070000h
0x180022b3b  mov     rcx, [rsp+158h]; this
0x180022b43  test    eax, eax
0x180022b45  jns     short loc_180022B5C
0x180022b47  mov     r9d, eax; char *
0x180022b4a  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180022b51  mov     edx, 1CBEh; void *
0x180022b56  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022b5c  lea     rcx, [rsp+158h+hKey]
0x180022b61  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180022b66  nop
0x180022b67  lea     rcx, [rsp+158h+var_108]
0x180022b6c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180022b71  nop
0x180022b72  lea     rcx, [rsp+158h+lpData]
0x180022b77  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginSetAuthenticatorStateTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(void)
0x180022b7c  nop
0x180022b7d  lea     rcx, [rsp+158h+var_E0]
0x180022b82  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180022b87  mov     rax, [rsp+158h+phKey]
0x180022b8c  mov     [rsp+158h+phKey], r13
0x180022b91  mov     [r12], rax
0x180022b95  lea     rcx, [rsp+158h+phKey]
0x180022b9a  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180022b9f  nop
0x180022ba0  lea     rcx, [rsp+158h+var_E8]
0x180022ba5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180022baa  nop
0x180022bab  lea     rcx, [rsp+158h+phProvider]
0x180022bb0  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180022bb5  nop
0x180022bb6  lea     rcx, [rsp+158h+pszKeyName]
0x180022bbb  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180022bc0  xor     eax, eax
0x180022bc2  jmp     short loc_180022BC8
0x180022bc4  mov     eax, dword ptr [rsp+158h+pszKeyName]
0x180022bc8  mov     rcx, [rsp+158h+var_48]
0x180022bd0  xor     rcx, rsp; StackCookie
0x180022bd3  call    __security_check_cookie
0x180022bd8  add     rsp, 120h
0x180022bdf  pop     r15
0x180022be1  pop     r14
0x180022be3  pop     r13
0x180022be5  pop     r12
0x180022be7  pop     rdi
0x180022be8  pop     rsi
0x180022be9  pop     rbx
0x180022bea  retn
0x180022beb  cmp     edi, 80090029h
0x180022bf1  jz      short loc_180022C4D
0x180022bf3  mov     rcx, [rsp+158h]; this
0x180022bfb  mov     r9d, edi; char *
0x180022bfe  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180022c05  mov     edx, 0ECh; void *
0x180022c0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022c0f  nop
  ... truncated ...
```
