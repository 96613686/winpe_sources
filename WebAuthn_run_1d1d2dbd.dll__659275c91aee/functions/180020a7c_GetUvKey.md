# GetUvKey

- ea: `0x180020a7c`
- end: `0x180021871`
- name: `GetUvKey`
- size: `3573`
- prototype: ``
- caller_count: `2`
- callee_count: `39`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800222d8`
- `0x180033970`

## callees

- `0x180017764`
- `0x180017a88`
- `0x18001ee7c`
- `0x180020584`
- `0x1800205e4`
- `0x180020614`
- `0x180020a7c`
- `0x180021878`
- `0x180021968`
- `0x180021adc`
- `0x180021bac`
- `0x180021d58`
- `0x180021e34`
- `0x180021f78`
- `0x180036da4`
- `0x18004349c`
- `0x18004363c`
- `0x180043a6c`
- `0x18004e08c`
- `0x18004e2a4`
- `0x18004f5b4`
- `0x1800510e8`
- `0x180052974`
- `0x180066b34`
- `0x180067b74`
- `0x18006f750`
- `0x1800ae560`
- `0x1800b134c`
- `0x1800b29c0`
- `0x1800b29f8`
- `0x1800b5810`
- `0x1800b70d4`
- `0x1800b715c`
- `0x18010f29c`
- `0x18011c42c`
- `0x180120dcc`
- `0x1801220ec`
- `0x180122124`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180021531`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180021531`
- `ncrypt!NCryptOpenKey` at `0x18002109b`
- `ncrypt!NCryptOpenKey` at `0x18002109b`
- `ncrypt!NCryptOpenStorageProvider` at `0x180020bd6`
- `ncrypt!NCryptOpenStorageProvider` at `0x180020bd6`

## string_xrefs

- `0x180020b0b`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180020b72`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180020bed`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180020d2b`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180020e98`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180020fe7`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x1800210b6`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x1800212b2`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180021393`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x1800213bb`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180021552`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x1800215bd`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180021710`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x1800214c1`: `WebAuthNPluginSetAuthenticatorStateTest::reason::uv_key_creation_succeeded_with_fallback`
- `0x180020d41`: `WebAuthNPluginSetAuthenticatorStateTest::reason::uv_key_query_kcm_failed`
- `0x180020d76`: `WebAuthNPluginPerformUVTest::reason::uv_key_query_kcm_failed`
- `0x1800214e4`: `WebAuthNPluginPerformUVTest::reason::uv_key_creation_succeeded_with_fallback`

## pseudocode

```c
// Hidden C++ exception states: #wind=17 #try_helpers=1
__int64 __fastcall GetUvKey(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 **a4, NCRYPT_HANDLE *a5, char a6)
{
  NCRYPT_HANDLE v9; // rsi
  char v10; // r12
  char v11; // r15
  int UserPluginAuthenticatorsRegKey; // eax
  unsigned int v13; // ebx
  int v15; // eax
  unsigned int v16; // ebx
  SECURITY_STATUS v17; // eax
  unsigned int v18; // ebx
  _QWORD *v19; // rax
  __int64 *v20; // rcx
  unsigned int KeyFromKcmKeyName; // esi
  char v22; // bl
  _QWORD *v23; // rax
  int v24; // edx
  int v25; // ecx
  const char *v26; // rdx
  const char *v27; // rbx
  _QWORD *v28; // rax
  const char *v29; // rax
  _QWORD *v30; // rax
  int v31; // edx
  int v32; // ecx
  char v33; // di
  NCRYPT_HANDLE v34; // rdi
  int PropertyValue; // eax
  unsigned int v36; // ebx
  unsigned __int16 *v37; // rax
  int InternalUvKeyName; // eax
  unsigned int v39; // ebx
  const WCHAR *v40; // rbx
  SECURITY_STATUS v41; // eax
  unsigned int v42; // ebx
  const wchar_t *v43; // rax
  unsigned int v44; // edi
  wil::reg::reg_view_details::reg_value_type_info *i; // rbx
  wil::reg::reg_view_details::reg_value_type_info *v46; // rdx
  int v47; // eax
  const char *v48; // rdx
  _QWORD *v49; // rax
  wil::reg::reg_view_details::reg_value_type_info *v50; // r8
  __int64 v51; // rdx
  const char *v52; // rax
  const char *v53; // rax
  DWORD cbData; // eax
  int v55; // eax
  int v56; // eax
  unsigned int v57; // ebx
  unsigned __int16 *v58; // rax
  int v59; // eax
  unsigned int v60; // ebx
  unsigned __int16 *v61; // rax
  NCRYPT_KEY_HANDLE v62; // rax
  int dwFlags; // [rsp+20h] [rbp-1B8h]
  int dwFlagsa; // [rsp+20h] [rbp-1B8h]
  unsigned __int16 *v65; // [rsp+30h] [rbp-1A8h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+38h] [rbp-1A0h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-198h] BYREF
  __int64 v68; // [rsp+48h] [rbp-190h] BYREF
  __int64 v69; // [rsp+50h] [rbp-188h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+58h] [rbp-180h] BYREF
  __int64 v71; // [rsp+60h] [rbp-178h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+68h] [rbp-170h] BYREF
  LPCWSTR pszKeyName; // [rsp+70h] [rbp-168h] BYREF
  char v74[8]; // [rsp+78h] [rbp-160h] BYREF
  int v75[2]; // [rsp+80h] [rbp-158h] BYREF
  NCRYPT_HANDLE *v76; // [rsp+88h] [rbp-150h]
  LPCVOID lpData; // [rsp+90h] [rbp-148h] BYREF
  __int64 *v78; // [rsp+98h] [rbp-140h]
  _BYTE v79[40]; // [rsp+A0h] [rbp-138h] BYREF
  __int64 v80; // [rsp+C8h] [rbp-110h] BYREF
  wil::reg::reg_view_details::reg_value_type_info *v81; // [rsp+D0h] [rbp-108h]
  _BYTE v82[32]; // [rsp+E0h] [rbp-F8h] BYREF
  char v83; // [rsp+100h] [rbp-D8h]
  _QWORD v84[5]; // [rsp+108h] [rbp-D0h] BYREF
  _BYTE v85[32]; // [rsp+130h] [rbp-A8h] BYREF
  char v86[32]; // [rsp+150h] [rbp-88h] BYREF
  char v87[32]; // [rsp+170h] [rbp-68h] BYREF
  __int64 v88; // [rsp+190h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]
  __int64 v90; // [rsp+1E8h] [rbp+10h] BYREF

  v90 = a2;
  v76 = a5;
  v9 = 0;
  v69 = 0;
  v68 = 0;
  v10 = tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::open_helper(
          &v69,
          0);
  v11 = tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::open_helper(
          &v68,
          0);
  v71 = 0;
  UserPluginAuthenticatorsRegKey = GetUserPluginAuthenticatorsRegKey(a1, &v71);
  v13 = UserPluginAuthenticatorsRegKey;
  if ( UserPluginAuthenticatorsRegKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12F,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
      (const char *)(unsigned int)UserPluginAuthenticatorsRegKey,
      dwFlags);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v71);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(&v68);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(&v69);
    return v13;
  }
  hKey = 0;
  v15 = wil::reg::open_unique_key_nothrow(v71, a3, &hKey, 1);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x132,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
      (const char *)(unsigned int)v15,
      dwFlags);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v71);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(&v68);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(&v69);
    return v16;
  }
  phProvider = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    &phProvider,
    0);
  v17 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Passport Key Storage Provider", 0);
  v18 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x135,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
      (const char *)(unsigned int)v17,
      dwFlags);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v71);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(&v68);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(&v69);
    return v18;
  }
  wil::impersonate_token(v74, a1);
  v65 = 0;
  hObject = 0;
  wil::reg::try_get_value_string(v79, hKey, L"UvKeyIdFromKcm");
  if ( v79[32] )
  {
    v75[0] = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
      &hObject,
      0);
    v19 = (_QWORD *)std::optional<std::wstring>::value(v79);
    v20 = (__int64 *)v19[2];
    if ( v19[3] > 7u )
      v19 = (_QWORD *)*v19;
    lpData = v19;
    v78 = v20;
    KeyFromKcmKeyName = CtapPluginInternal::GetKeyFromKcmKeyName(a1, &lpData, &hObject, v75);
    v22 = v75[0];
    if ( v75[0] > 1u && (byte_1801AEA05 & 2) != 0 )
    {
      v23 = (_QWORD *)std::optional<std::wstring>::value(v79);
      if ( v23[3] > 7u )
        v23 = (_QWORD *)*v23;
      McTemplateU0zzq_EventWriteTransfer(v25, v24, a3, (_DWORD)v23, v22);
    }
    if ( (KeyFromKcmKeyName & 0x80000000) == 0 )
    {
      v33 = a6;
      if ( !a6 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v65,
          0);
        v34 = hObject;
        PropertyValue = GetPropertyValue(hObject, L"Algorithm Name", &v65);
        v36 = PropertyValue;
        if ( PropertyValue >= 0 )
        {
          v37 = v65;
          v65 = 0;
          *a4 = v37;
          hObject = 0;
          *v76 = v34;
          std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v79);
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v65);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v74);
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v71);
          wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(&v68);
          wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(&v69);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x159,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
            (const char *)(unsigned int)PropertyValue,
            dwFlags);
          std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v79);
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v65);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v74);
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v71);
          wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(&v68);
          wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(&v69);
          return v36;
        }
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x145,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)KeyFromKcmKeyName,
        dwFlags);
      if ( v10 )
      {
        v27 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::uv_key_query_kcm_failed",
                v26);
        v28 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::ensure_data(&v69);
        tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(*v28 + 8LL, 15, v27, KeyFromKcmKeyName);
      }
      if ( v11 )
      {
        v29 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginPerformUVTest::reason::uv_key_query_kcm_failed",
                v26);
        tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::set_flag_value<long>(
          &v68,
          14,
          v29,
          KeyFromKcmKeyName);
      }
      if ( (byte_1801AEA05 & 4) != 0 )
      {
        v30 = (_QWORD *)std::optional<std::wstring>::value(v79);
        if ( v30[3] > 7u )
          v30 = (_QWORD *)*v30;
        McTemplateU0zzdd_EventWriteTransfer(v32, v31, a3, (_DWORD)v30, KeyFromKcmKeyName, KeyFromKcmKeyName);
      }
      v33 = a6;
      if ( !a6 )
      {
        std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v79);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v65);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v74);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v71);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(&v68);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(&v69);
        return KeyFromKcmKeyName;
      }
    }
    v9 = hObject;
  }
  else
  {
    v33 = a6;
  }
  pszKeyName = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pszKeyName,
    0);
  InternalUvKeyName = PluginGetOrCreateInternalUvKeyName(hKey);
  v39 = InternalUvKeyName;
  if ( InternalUvKeyName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x162,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
      (const char *)(unsigned int)InternalUvKeyName,
      dwFlags);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszKeyName);
    std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v79);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v65);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v74);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v71);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(&v68);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(&v69);
    return v39;
  }
  phKey = 0;
  v40 = pszKeyName;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    &phKey,
    0);
  v41 = NCryptOpenKey(phProvider, &phKey, v40, 0, 0);
  v42 = v41;
  if ( v41 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
      (const char *)(unsigned int)v41,
      dwFlagsa);
    if ( !v33 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszKeyName);
      std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v79);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v65);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v74);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v71);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(&v68);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(&v69);
      return v42;
    }
    v84[0] = &phProvider;
    v84[1] = &phKey;
    v84[2] = &pszKeyName;
    v84[3] = &v90;
    wil::reg::try_get_value_string(v82, hKey, L"SigningKeyAlgorithm");
    if ( v83 )
    {
      v43 = (const wchar_t *)std::optional<std::wstring>::value(v82);
      if ( *((_QWORD *)v43 + 3) > 7u )
        v43 = *(const wchar_t **)v43;
    }
    else
    {
      v43 = L"ECDSA_P256";
    }
    *(_QWORD *)v75 = v43;
    std::wstring::wstring(v85, L"ECDSA_P384");
    std::wstring::wstring(v86, L"ECDSA_P256");
    std::wstring::wstring(v87, L"RSA");
    lpData = v85;
    v78 = &v88;
    std::vector<std::wstring>::vector<std::wstring>(&v80, &lpData);
    `eh vector destructor iterator'(
      v85,
      0x20u,
      3u,
      wil::reg::iterator_t<wil::reg::key_iterator_data<std::wstring>>::~iterator_t<wil::reg::key_iterator_data<std::wstring>>);
    std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,unsigned short const *>(
      &lpData,
      v80,
      v81,
      v75);
    v44 = -2146893783;
    for ( i = (wil::reg::reg_view_details::reg_value_type_info *)lpData;
          ;
          i = (wil::reg::reg_view_details::reg_value_type_info *)((char *)i + 32) )
    {
      if ( i == v81 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1BB,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
          (const char *)v44,
          dwFlagsa);
        std::vector<std::wstring>::_Tidy(&v80);
        std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v82);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszKeyName);
        std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v79);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v65);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v74);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v71);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(&v68);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(&v69);
        return v44;
      }
      v46 = *((_QWORD *)i + 3) <= 7u ? i : *(wil::reg::reg_view_details::reg_value_type_info **)i;
      v47 = GetUvKey_::_63_::_lambda_1_::operator()(v84, v46);
      v44 = v47;
      if ( v47 >= 0 )
        break;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)(unsigned int)v47,
        dwFlagsa);
      if ( v44 != -2146893783 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B8,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
          (const char *)v44,
          dwFlagsa);
        std::vector<std::wstring>::_Tidy(&v80);
        std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v82);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszKeyName);
        std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v79);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v65);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v74);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v71);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(&v68);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(&v69);
        return v44;
      }
    }
    if ( !v83 )
      goto LABEL_58;
    v49 = (_QWORD *)std::optional<std::wstring>::value(v82);
    if ( *((_QWORD *)i + 3) <= 7u )
      v50 = i;
    else
      v50 = *(wil::reg::reg_view_details::reg_value_type_info **)i;
    v51 = v49[2];
    if ( v49[3] > 7u )
      v49 = (_QWORD *)*v49;
    if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v49, v51, v50, *((_QWORD *)i + 2)) )
    {
LABEL_58:
      if ( v10 )
      {
        v52 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::uv_key_creation_succeeded_with_fallback",
                v48);
        tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::set_flag(
          &v69,
          14,
          v52);
      }
      if ( v11 )
      {
        v53 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginPerformUVTest::reason::uv_key_creation_succeeded_with_fallback",
                v48);
        tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::set_flag(
          &v68,
          13,
          v53);
      }
      if ( *((_QWORD *)i + 3) > 7u )
        i = *(wil::reg::reg_view_details::reg_value_type_info **)i;
      cbData = wil::reg::reg_view_details::reg_value_type_info::get_buffer_size_bytes(i, (const unsigned __int16 *)v48);
      v55 = RegSetKeyValueW(hKey, 0, L"SigningKeyAlgorithm", 1u, i, cbData);
      if ( v55 > 0 )
        v55 = (unsigned __int16)v55 | 0x80070000;
      if ( v55 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1B2,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
          (const char *)(unsigned int)v55,
          dwFlagsa);
    }
    std::vector<std::wstring>::_Tidy(&v80);
    std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v82);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v65,
    0);
  if ( v9 )
  {
    v56 = GetPropertyValue(v9, L"Algorithm Name", &v65);
    v57 = v56;
    if ( v56 >= 0 )
    {
      v58 = v65;
      v65 = 0;
      *a4 = v58;
      hObject = 0;
      *v76 = v9;
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszKeyName);
      std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v79);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v65);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v74);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v71);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(&v68);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(&v69);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C1,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)(unsigned int)v56,
        dwFlagsa);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszKeyName);
      std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v79);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v65);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v74);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v71);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(&v68);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(&v69);
      return v57;
    }
  }
  else
  {
    v59 = GetPropertyValue(phKey, L"Algorithm Name", &v65);
    v60 = v59;
    if ( v59 >= 0 )
    {
      v61 = v65;
      v65 = 0;
      *a4 = v61;
      v62 = phKey;
      phKey = 0;
      *v76 = v62;
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszKeyName);
      std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v79);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v65);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v74);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v71);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(&v68);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(&v69);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C6,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
        (const char *)(unsigned int)v59,
        dwFlagsa);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszKeyName);
      std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v79);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v65);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v74);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v71);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(&v68);
      wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(&v69);
      return v60;
    }
  }
}

```

## disassembly

```asm
0x180020a7c  mov     [rsp+arg_8], rdx
0x180020a81  push    rbx
0x180020a82  push    rsi
0x180020a83  push    rdi
0x180020a84  push    r12
0x180020a86  push    r13
0x180020a88  push    r14
0x180020a8a  push    r15
0x180020a8c  sub     rsp, 1A0h
0x180020a93  mov     rax, cs:__security_cookie
0x180020a9a  xor     rax, rsp
0x180020a9d  mov     [rsp+1D8h+var_48], rax
0x180020aa5  mov     r13, r9
0x180020aa8  mov     r14, r8
0x180020aab  mov     rdi, rcx
0x180020aae  mov     rax, [rsp+1D8h+arg_20]
0x180020ab6  mov     [rsp+1D8h+var_150], rax
0x180020abe  xor     esi, esi
0x180020ac0  mov     [rsp+1D8h+var_188], rsi
0x180020ac5  mov     [rsp+1D8h+var_190], rsi
0x180020aca  xor     edx, edx
0x180020acc  lea     rcx, [rsp+1D8h+var_188]
0x180020ad1  call    ?open_helper@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginSetAuthenticatorStateTest@@U1@@details@tip2@@@tip2@@AEAA_NPEAU_GUID@@@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::open_helper(_GUID *)
0x180020ad6  mov     r12b, al
0x180020ad9  xor     edx, edx
0x180020adb  lea     rcx, [rsp+1D8h+var_190]
0x180020ae0  call    ?open_helper@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@AEAA_NPEAU_GUID@@@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::open_helper(_GUID *)
0x180020ae5  mov     r15b, al
0x180020ae8  mov     [rsp+1D8h+var_178], rsi
0x180020aed  lea     rdx, [rsp+1D8h+var_178]
0x180020af2  mov     rcx, rdi
0x180020af5  call    GetUserPluginAuthenticatorsRegKey
0x180020afa  mov     ebx, eax
0x180020afc  test    eax, eax
0x180020afe  jns     short loc_180020B44
0x180020b00  mov     rcx, [rsp+1D8h]; this
0x180020b08  mov     r9d, eax; char *
0x180020b0b  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180020b12  mov     edx, 12Fh; void *
0x180020b17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020b1c  nop
0x180020b1d  lea     rcx, [rsp+1D8h+var_178]
0x180020b22  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180020b27  nop
0x180020b28  lea     rcx, [rsp+1D8h+var_190]
0x180020b2d  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(void)
0x180020b32  nop
0x180020b33  lea     rcx, [rsp+1D8h+var_188]
0x180020b38  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginSetAuthenticatorStateTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(void)
0x180020b3d  mov     eax, ebx
0x180020b3f  jmp     loc_18002184D
0x180020b44  mov     [rsp+1D8h+hKey], rsi
0x180020b49  mov     r9d, 1
0x180020b4f  lea     r8, [rsp+1D8h+hKey]
0x180020b54  mov     rdx, r14
0x180020b57  mov     rcx, [rsp+1D8h+var_178]
0x180020b5c  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x180020b61  mov     ebx, eax
0x180020b63  test    eax, eax
0x180020b65  jns     short loc_180020BB6
0x180020b67  mov     rcx, [rsp+1D8h]; this
0x180020b6f  mov     r9d, eax; char *
0x180020b72  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180020b79  mov     edx, 132h; void *
0x180020b7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020b83  nop
0x180020b84  lea     rcx, [rsp+1D8h+hKey]
0x180020b89  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180020b8e  nop
0x180020b8f  lea     rcx, [rsp+1D8h+var_178]
0x180020b94  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180020b99  nop
0x180020b9a  lea     rcx, [rsp+1D8h+var_190]
0x180020b9f  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(void)
0x180020ba4  nop
0x180020ba5  lea     rcx, [rsp+1D8h+var_188]
0x180020baa  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginSetAuthenticatorStateTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(void)
0x180020baf  mov     eax, ebx
0x180020bb1  jmp     loc_18002184D
0x180020bb6  mov     [rsp+1D8h+phProvider], rsi
0x180020bbb  xor     edx, edx
0x180020bbd  lea     rcx, [rsp+1D8h+phProvider]
0x180020bc2  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x180020bc7  xor     r8d, r8d; dwFlags
0x180020bca  lea     rdx, pszProviderName; "Microsoft Passport Key Storage Provider"
0x180020bd1  lea     rcx, [rsp+1D8h+phProvider]; phProvider
0x180020bd6  call    cs:__imp_NCryptOpenStorageProvider
0x180020bdc  mov     ebx, eax
0x180020bde  test    eax, eax
0x180020be0  jns     short loc_180020C3C
0x180020be2  mov     rcx, [rsp+1D8h]; this
0x180020bea  mov     r9d, eax; char *
0x180020bed  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180020bf4  mov     edx, 135h; void *
0x180020bf9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020bfe  nop
0x180020bff  lea     rcx, [rsp+1D8h+phProvider]
0x180020c04  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180020c09  nop
0x180020c0a  lea     rcx, [rsp+1D8h+hKey]
0x180020c0f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180020c14  nop
0x180020c15  lea     rcx, [rsp+1D8h+var_178]
0x180020c1a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180020c1f  nop
0x180020c20  lea     rcx, [rsp+1D8h+var_190]
0x180020c25  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(void)
0x180020c2a  nop
0x180020c2b  lea     rcx, [rsp+1D8h+var_188]
0x180020c30  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginSetAuthenticatorStateTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(void)
0x180020c35  mov     eax, ebx
0x180020c37  jmp     loc_18002184D
0x180020c3c  mov     rdx, rdi
0x180020c3f  lea     rcx, [rsp+1D8h+var_160]
0x180020c44  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x180020c49  nop
0x180020c4a  mov     [rsp+1D8h+var_1A8], rsi
0x180020c4f  mov     [rsp+1D8h+hObject], rsi
0x180020c54  lea     r8, aUvkeyidfromkcm; "UvKeyIdFromKcm"
0x180020c5b  mov     rdx, [rsp+1D8h+hKey]
0x180020c60  lea     rcx, [rsp+1D8h+var_138]
0x180020c68  call    ?try_get_value_string@reg@wil@@YA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAUHKEY__@@PEBG@Z; wil::reg::try_get_value_string(HKEY__ *,ushort const *)
0x180020c6d  nop
0x180020c6e  cmp     [rsp+1D8h+var_118], 0
0x180020c76  jz      loc_180020FA7
0x180020c7c  mov     [rsp+1D8h+var_158], 0
0x180020c87  xor     edx, edx
0x180020c89  lea     rcx, [rsp+1D8h+hObject]
0x180020c8e  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x180020c93  lea     rcx, [rsp+1D8h+var_138]
0x180020c9b  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x180020ca0  mov     rcx, [rax+10h]
0x180020ca4  cmp     qword ptr [rax+18h], 7
0x180020ca9  jbe     short loc_180020CAE
0x180020cab  mov     rax, [rax]
0x180020cae  mov     [rsp+1D8h+lpData], rax
0x180020cb6  mov     [rsp+1D8h+var_140], rcx
0x180020cbe  lea     r9, [rsp+1D8h+var_158]
0x180020cc6  lea     r8, [rsp+1D8h+hObject]
0x180020ccb  lea     rdx, [rsp+1D8h+lpData]
0x180020cd3  mov     rcx, rdi
0x180020cd6  call    ?GetKeyFromKcmKeyName@CtapPluginInternal@@YAJQEAXV?$basic_zstring_view@G@wil@@PEA_KPEAI@Z; CtapPluginInternal::GetKeyFromKcmKeyName(void * const,wil::basic_zstring_view<ushort>,unsigned __int64 *,uint *)
0x180020cdb  mov     esi, eax
0x180020cdd  mov     ebx, [rsp+1D8h+var_158]
0x180020ce4  cmp     ebx, 1
0x180020ce7  jbe     short loc_180020D18
0x180020ce9  test    cs:byte_1801AEA05, 2
0x180020cf0  jz      short loc_180020D18
0x180020cf2  lea     rcx, [rsp+1D8h+var_138]
0x180020cfa  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x180020cff  cmp     qword ptr [rax+18h], 7
0x180020d04  jbe     short loc_180020D09
0x180020d06  mov     rax, [rax]
0x180020d09  mov     [rsp+1D8h+dwFlags], ebx; int
0x180020d0d  mov     r9, rax
0x180020d10  mov     r8, r14
0x180020d13  call    McTemplateU0zzq_EventWriteTransfer
0x180020d18  mov     rcx, [rsp+1D8h]; this
0x180020d20  test    esi, esi
0x180020d22  jns     loc_180020E4A
0x180020d28  mov     r9d, esi; char *
0x180020d2b  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180020d32  mov     edx, 145h; void *
0x180020d37  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020d3c  test    r12b, r12b
0x180020d3f  jz      short loc_180020D71
0x180020d41  lea     rcx, aWebauthnplugin_35; "WebAuthNPluginSetAuthenticatorStateTest"...
0x180020d48  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180020d4d  mov     rbx, rax
0x180020d50  lea     rcx, [rsp+1D8h+var_188]
0x180020d55  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginSetAuthenticatorStateTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginSetAuthenticatorStateTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::ensure_data(void)
0x180020d5a  mov     edx, 0Fh
0x180020d5f  mov     rcx, [rax]
0x180020d62  add     rcx, 8
0x180020d66  mov     r9d, esi
0x180020d69  mov     r8, rbx
0x180020d6c  call    ??$set_flag_value_without_lock@J@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBDJ@Z; tip2::details::shared_data<1,0,0>::set_flag_value_without_lock<long>(ushort,char const *,long)
0x180020d71  test    r15b, r15b
0x180020d74  jz      short loc_180020D97
0x180020d76  lea     rcx, aWebauthnplugin_33; "WebAuthNPluginPerformUVTest::reason::uv"...
0x180020d7d  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180020d82  mov     r8, rax
0x180020d85  mov     edx, 0Eh
0x180020d8a  mov     r9d, esi
0x180020d8d  lea     rcx, [rsp+1D8h+var_190]
0x180020d92  call    ??$set_flag_value@J@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBDJ@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::set_flag_value<long>(ushort,char const *,long)
0x180020d97  test    cs:byte_1801AEA05, 4
0x180020d9e  jz      short loc_180020DCA
0x180020da0  lea     rcx, [rsp+1D8h+var_138]
0x180020da8  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x180020dad  cmp     qword ptr [rax+18h], 7
0x180020db2  jbe     short loc_180020DB7
0x180020db4  mov     rax, [rax]
0x180020db7  mov     [rsp+1D8h+cbData], esi
0x180020dbb  mov     [rsp+1D8h+dwFlags], esi
0x180020dbf  mov     r9, rax
0x180020dc2  mov     r8, r14
0x180020dc5  call    McTemplateU0zzdd_EventWriteTransfer
0x180020dca  mov     dil, [rsp+1D8h+arg_28]
0x180020dd2  xor     r14d, r14d
0x180020dd5  test    dil, dil
0x180020dd8  jnz     loc_180020FA0
0x180020dde  lea     rcx, [rsp+1D8h+var_138]
0x180020de6  call    ??1?$_Optional_destruct_base@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x180020deb  nop
0x180020dec  lea     rcx, [rsp+1D8h+hObject]
0x180020df1  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180020df6  nop
0x180020df7  lea     rcx, [rsp+1D8h+var_1A8]
0x180020dfc  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180020e01  nop
0x180020e02  lea     rcx, [rsp+1D8h+var_160]
0x180020e07  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180020e0c  nop
0x180020e0d  lea     rcx, [rsp+1D8h+phProvider]
0x180020e12  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180020e17  nop
0x180020e18  lea     rcx, [rsp+1D8h+hKey]
0x180020e1d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180020e22  nop
0x180020e23  lea     rcx, [rsp+1D8h+var_178]
0x180020e28  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180020e2d  nop
0x180020e2e  lea     rcx, [rsp+1D8h+var_190]
0x180020e33  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(void)
0x180020e38  nop
0x180020e39  lea     rcx, [rsp+1D8h+var_188]
0x180020e3e  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginSetAuthenticatorStateTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(void)
0x180020e43  mov     eax, esi
0x180020e45  jmp     loc_18002184D
0x180020e4a  mov     dil, [rsp+1D8h+arg_28]
0x180020e52  xor     r14d, r14d
0x180020e55  test    dil, dil
0x180020e58  jnz     loc_180020FA0
0x180020e5e  xor     edx, edx
0x180020e60  lea     rcx, [rsp+1D8h+var_1A8]
0x180020e65  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180020e6a  lea     r8, [rsp+1D8h+var_1A8]; unsigned __int16 **
0x180020e6f  lea     rdx, pszProperty; "Algorithm Name"
0x180020e76  mov     rdi, [rsp+1D8h+hObject]
0x180020e7b  mov     rcx, rdi; hObject
0x180020e7e  call    ?GetPropertyValue@@YAJ_KPEBGPEAPEAG@Z; GetPropertyValue(unsigned __int64,ushort const *,ushort * *)
0x180020e83  mov     ebx, eax
0x180020e85  test    eax, eax
0x180020e87  jns     loc_180020F16
0x180020e8d  mov     rcx, [rsp+1D8h]; this
0x180020e95  mov     r9d, eax; char *
0x180020e98  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180020e9f  mov     edx, 159h; void *
0x180020ea4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020ea9  nop
0x180020eaa  lea     rcx, [rsp+1D8h+var_138]
0x180020eb2  call    ??1?$_Optional_destruct_base@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x180020eb7  nop
0x180020eb8  lea     rcx, [rsp+1D8h+hObject]
0x180020ebd  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180020ec2  nop
0x180020ec3  lea     rcx, [rsp+1D8h+var_1A8]
0x180020ec8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180020ecd  nop
0x180020ece  lea     rcx, [rsp+1D8h+var_160]
0x180020ed3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180020ed8  nop
0x180020ed9  lea     rcx, [rsp+1D8h+phProvider]
0x180020ede  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180020ee3  nop
0x180020ee4  lea     rcx, [rsp+1D8h+hKey]
0x180020ee9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180020eee  nop
0x180020eef  lea     rcx, [rsp+1D8h+var_178]
0x180020ef4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180020ef9  nop
0x180020efa  lea     rcx, [rsp+1D8h+var_190]
0x180020eff  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(void)
0x180020f04  nop
0x180020f05  lea     rcx, [rsp+1D8h+var_188]
0x180020f0a  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginSetAuthenticatorStateTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(void)
0x180020f0f  mov     eax, ebx
0x180020f11  jmp     loc_18002184D
0x180020f16  mov     rax, [rsp+1D8h+var_1A8]
0x180020f1b  mov     [rsp+1D8h+var_1A8], r14
0x180020f20  mov     [r13+0], rax
0x180020f24  mov     [rsp+1D8h+hObject], r14
0x180020f29  mov     rcx, [rsp+1D8h+var_150]
0x180020f31  mov     [rcx], rdi
0x180020f34  lea     rcx, [rsp+1D8h+var_138]
0x180020f3c  call    ??1?$_Optional_destruct_base@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x180020f41  nop
0x180020f42  lea     rcx, [rsp+1D8h+hObject]
0x180020f47  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180020f4c  nop
0x180020f4d  lea     rcx, [rsp+1D8h+var_1A8]
0x180020f52  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180020f57  nop
0x180020f58  lea     rcx, [rsp+1D8h+var_160]
0x180020f5d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180020f62  nop
0x180020f63  lea     rcx, [rsp+1D8h+phProvider]
0x180020f68  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180020f6d  nop
  ... truncated ...
```
