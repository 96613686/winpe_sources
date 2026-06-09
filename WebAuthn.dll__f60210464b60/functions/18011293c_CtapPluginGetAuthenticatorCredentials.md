# CtapPluginGetAuthenticatorCredentials

- ea: `0x18011293c`
- end: `0x1801139f1`
- name: `CtapPluginGetAuthenticatorCredentials`
- size: `4277`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, __int64)`
- caller_count: `3`
- callee_count: `52`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180081bf8`
- `0x180081dcc`
- `0x180081f54`

## callees

- `0x1800010a8`
- `0x18001ed38`
- `0x18001ee7c`
- `0x1800205e4`
- `0x180021878`
- `0x18002a07c`
- `0x1800328b8`
- `0x1800328dc`
- `0x1800350b4`
- `0x180036da4`
- `0x180037f6c`
- `0x18003988c`
- `0x18003a3c0`
- `0x18003aab8`
- `0x18003ab20`
- `0x1800412c8`
- `0x180042df8`
- `0x180042e40`
- `0x18004349c`
- `0x1800435c0`
- `0x180043f2c`
- `0x1800467e0`
- `0x180046820`
- `0x180048b70`
- `0x18004d8f4`
- `0x18005378c`
- `0x1800537a4`
- `0x18006f174`
- `0x18006f750`
- `0x18007d7c4`
- `0x18007e2a8`
- `0x18007e320`
- `0x18007ed34`
- `0x1800814f8`
- `0x180081648`
- `0x1800835bc`
- `0x180087804`
- `0x180093428`
- `0x1800ae6d8`
- `0x1800af5dc`
- `0x1800baa08`
- `0x1800c2e10`
- `0x1800c3618`
- `0x1800c3bfc`
- `0x18010adf0`
- `0x18010bfa8`
- `0x18010ce04`
- `0x18010dbb8`
- `0x18010ee78`
- `0x18011293c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180113993`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180113993`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180112a76`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180112a76`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180112c9a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180112d75`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180112dcf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180112ec2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180112f84`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180113029`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180113101`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801131d7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180112c9a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180112d75`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180112dcf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180112ec2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180112f84`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180113029`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180113101`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801131d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180112be2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180112be2`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180112b92`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180112b92`

## string_xrefs

- `0x18011299a`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801129f6`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180112a8b`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180112ad8`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180112b28`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180113042`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801131f0`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180113319`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180113657`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1801136e3`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=21 #try_helpers=1
__int64 __fastcall CtapPluginGetAuthenticatorCredentials(void *a1, __int64 a2, int a3, _DWORD *a4, _QWORD *a5)
{
  __int64 v6; // rsi
  int UserPluginAuthenticatorsRegKey; // eax
  unsigned int v10; // ebx
  unsigned int v11; // eax
  unsigned int v12; // ebx
  DWORD i; // edi
  HKEY *v14; // rax
  HKEY *v15; // rbx
  HKEY v16; // rcx
  HKEY v17; // rcx
  __int64 v18; // rax
  HKEY v19; // rcx
  HKEY v20; // rcx
  HKEY v21; // rcx
  char *v22; // rsi
  char *v23; // rax
  size_t v24; // rdi
  bool v25; // zf
  PVOID v26; // rax
  HKEY v27; // rcx
  const WCHAR *v28; // r8
  HKEY v29; // rcx
  unsigned int ValueW; // eax
  unsigned int v31; // ebx
  HKEY v32; // rcx
  char *v33; // rsi
  char *v34; // rax
  size_t v35; // rdi
  HKEY v36; // rcx
  unsigned int v37; // eax
  unsigned int v38; // ebx
  unsigned int CredentialsFrom; // eax
  CredentialInfo *v40; // rcx
  CredentialInfo *v41; // rdx
  HKEY v42; // rdx
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // r8
  _QWORD *v47; // r8
  int v48; // r8d
  int v49; // r9d
  int *v50; // rcx
  __int16 *v51; // rdx
  _QWORD *v52; // rax
  __int64 v53; // rbx
  __int64 j; // rbx
  __int64 v55; // rdi
  int v56; // eax
  unsigned int v57; // eax
  CredentialInfo *v58; // rbx
  CredentialInfo *v59; // rdi
  HLOCAL v60; // rax
  HLOCAL v61; // rcx
  int lpcSubKeys; // [rsp+20h] [rbp-528h]
  unsigned int lpcSubKeysa; // [rsp+20h] [rbp-528h]
  unsigned int lpcSubKeysb; // [rsp+20h] [rbp-528h]
  unsigned int lpcSubKeysc; // [rsp+20h] [rbp-528h]
  int lpcSubKeysd; // [rsp+20h] [rbp-528h]
  int v67; // [rsp+60h] [rbp-4E8h] BYREF
  DWORD v68; // [rsp+64h] [rbp-4E4h] BYREF
  DWORD v69; // [rsp+68h] [rbp-4E0h]
  DWORD cbMaxSubKeyLen; // [rsp+6Ch] [rbp-4DCh] BYREF
  DWORD pcbData; // [rsp+70h] [rbp-4D8h] BYREF
  int v72; // [rsp+74h] [rbp-4D4h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-4D0h] BYREF
  PVOID v74[2]; // [rsp+80h] [rbp-4C8h] BYREF
  __int64 v75; // [rsp+90h] [rbp-4B8h]
  DWORD cSubKeys; // [rsp+98h] [rbp-4B0h] BYREF
  CredentialInfo *v77[2]; // [rsp+A0h] [rbp-4A8h] BYREF
  __int64 v78; // [rsp+B0h] [rbp-498h]
  __int128 v79; // [rsp+B8h] [rbp-490h] BYREF
  LPWSTR lpName; // [rsp+C8h] [rbp-480h] BYREF
  _WORD *v81; // [rsp+D0h] [rbp-478h]
  _WORD *v82; // [rsp+D8h] [rbp-470h]
  int pvData; // [rsp+E0h] [rbp-468h] BYREF
  __int64 v84; // [rsp+E8h] [rbp-460h]
  HLOCAL hMem; // [rsp+F0h] [rbp-458h] BYREF
  PVOID v86; // [rsp+F8h] [rbp-450h] BYREF
  _WORD *v87; // [rsp+100h] [rbp-448h]
  _WORD *v88; // [rsp+108h] [rbp-440h]
  int v89; // [rsp+110h] [rbp-438h]
  __int128 v90; // [rsp+118h] [rbp-430h] BYREF
  __int64 v91; // [rsp+128h] [rbp-420h]
  __int128 v92; // [rsp+130h] [rbp-418h] BYREF
  __int64 v93; // [rsp+140h] [rbp-408h]
  __int128 v94; // [rsp+148h] [rbp-400h] BYREF
  __int64 v95; // [rsp+158h] [rbp-3F0h]
  _OWORD v96[2]; // [rsp+160h] [rbp-3E8h] BYREF
  char v97[8]; // [rsp+180h] [rbp-3C8h] BYREF
  void *Src; // [rsp+188h] [rbp-3C0h] BYREF
  __int64 v99; // [rsp+190h] [rbp-3B8h]
  _QWORD v100[2]; // [rsp+1A0h] [rbp-3A8h] BYREF
  _QWORD v101[2]; // [rsp+1B0h] [rbp-398h] BYREF
  _QWORD v102[2]; // [rsp+1C0h] [rbp-388h] BYREF
  _BYTE v103[64]; // [rsp+1D0h] [rbp-378h] BYREF
  char v104; // [rsp+210h] [rbp-338h]
  _QWORD v105[3]; // [rsp+218h] [rbp-330h] BYREF
  unsigned __int64 v106; // [rsp+230h] [rbp-318h]
  _BYTE v107[40]; // [rsp+238h] [rbp-310h] BYREF
  _BYTE v108[32]; // [rsp+260h] [rbp-2E8h] BYREF
  char v109[32]; // [rsp+280h] [rbp-2C8h] BYREF
  _BYTE v110[208]; // [rsp+2A0h] [rbp-2A8h] BYREF
  char v111[32]; // [rsp+370h] [rbp-1D8h] BYREF
  char v112[32]; // [rsp+390h] [rbp-1B8h] BYREF
  _BYTE v113[272]; // [rsp+3B0h] [rbp-198h] BYREF
  _BYTE v114[80]; // [rsp+4C0h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+548h] [rbp+0h]

  v89 = a3;
  v6 = a2;
  v84 = a2;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA1B,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)0x80004003LL,
      lpcSubKeys);
    return 2147500035LL;
  }
  if ( a4 && a5 )
  {
    *a4 = 0;
    *a5 = 0;
  }
  v94 = 0;
  v95 = 0;
  hKey = 0;
  UserPluginAuthenticatorsRegKey = GetUserPluginAuthenticatorsRegKey((__int64)a1, (__int64)&hKey);
  v10 = UserPluginAuthenticatorsRegKey;
  if ( UserPluginAuthenticatorsRegKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA26,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)(unsigned int)UserPluginAuthenticatorsRegKey,
      lpcSubKeys);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(&v94);
    return v10;
  }
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v11 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v11 )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xA2B,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)v11,
            lpcSubKeysa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(&v94);
    return v12;
  }
  ++cbMaxSubKeyLen;
  if ( !cSubKeys )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA30,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)0x80090011LL,
      lpcSubKeysa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(&v94);
    return 2148073489LL;
  }
  if ( !IsHelloEnrolled(a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA34,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)0x80548211LL,
      lpcSubKeysa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(&v94);
    return 2153021969LL;
  }
  for ( i = 0; ; ++i )
  {
    v69 = i;
    if ( i >= cSubKeys )
      break;
    std::vector<unsigned short>::vector<unsigned short>(&lpName, cbMaxSubKeyLen);
    if ( RegEnumKeyW(hKey, i, lpName, cbMaxSubKeyLen) )
      goto LABEL_17;
    v79 = 0;
    v14 = (HKEY *)wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>::put(&v79);
    if ( RegOpenKeyExW(hKey, lpName, 0, 0xF003Fu, v14) )
      goto LABEL_19;
    LOWORD(v67) = 0;
    if ( v81 == v82 )
      std::vector<unsigned short>::_Emplace_reallocate<unsigned short>(&lpName, v81, &v67);
    else
      *v81++ = 0;
    std::wstring::wstring(v107, lpName);
    pvData = 0;
    pcbData = 4;
    v15 = (HKEY *)v79;
    if ( (_QWORD)v79 )
      v16 = *(HKEY *)v79;
    else
      v16 = 0;
    if ( RegGetValueW(v16, 0, L"State", 0x10u, 0, &pvData, &pcbData) )
      goto LABEL_46;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl)
      && !pvData )
    {
      v67 = 0;
      v17 = v15 ? *v15 : 0LL;
      if ( (int)wil::reg::get_value_nothrow<unsigned long,0>(v17, 0, L"StateToggled", &v67) < 0 || v67 == 1 )
        goto LABEL_46;
    }
    v96[0] = 0;
    v18 = *((_QWORD *)&v79 + 1);
    if ( *((_QWORD *)&v79 + 1) )
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v79 + 1) + 8LL));
    *(_QWORD *)&v96[0] = v15;
    *((_QWORD *)&v96[0] + 1) = v18;
    if ( !(unsigned __int8)IsPluginPackagePresent(a1, v96) )
      goto LABEL_46;
    pcbData = 0;
    v19 = v15 ? *v15 : 0LL;
    if ( RegGetValueW(v19, 0, L"Name", 2u, 0, 0, &pcbData) )
      goto LABEL_46;
    std::vector<unsigned short>::vector<unsigned short>(&v86, (unsigned __int64)pcbData >> 1);
    if ( v15 )
      v20 = *v15;
    else
      v20 = 0;
    if ( RegGetValueW(v20, 0, L"Name", 2u, 0, v86, &pcbData) )
    {
      std::vector<unsigned short>::_Tidy(&v86);
LABEL_46:
      std::wstring::_Tidy_deallocate(v107);
      std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(&v79);
      std::vector<unsigned short>::_Tidy(&lpName);
      continue;
    }
    LOWORD(v67) = 0;
    if ( v87 == v88 )
      std::vector<unsigned short>::_Emplace_reallocate<unsigned short>(&v86, v87, &v67);
    else
      *v87++ = 0;
    std::wstring::wstring(v105, v86);
    v68 = 0;
    *(_OWORD *)v74 = 0;
    v75 = 0;
    if ( v89 == 1 )
    {
      if ( v15 )
        v21 = *v15;
      else
        v21 = 0;
      if ( !RegGetValueW(v21, 0, L"DecodedUtf8LightLogo", 8u, 0, 0, &v68) )
      {
        v22 = (char *)v74[1];
        if ( (PVOID)v68 < (PVOID)((char *)v74[1] - (char *)v74[0]) )
        {
          v23 = (char *)v74[0] + v68;
          goto LABEL_62;
        }
        if ( (PVOID)v68 > (PVOID)((char *)v74[1] - (char *)v74[0]) )
        {
          if ( v68 <= v75 - (unsigned __int64)v74[0] )
          {
            v24 = v68 - (unsigned __int64)((char *)v74[1] - (char *)v74[0]);
            memset_0(v74[1], 0, v24);
            v23 = &v22[v24];
LABEL_62:
            v74[1] = v23;
          }
          else
          {
            std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v74, v68);
          }
        }
        v25 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::GetImpl'::`2'::impl) == 0;
        v26 = v74[0];
        if ( v25 )
        {
          if ( v15 )
            v29 = *v15;
          else
            v29 = 0;
          ValueW = RegGetValueW(v29, 0, L"DecodedUtf8LightLogo", 8u, 0, v74[0], &v68);
          if ( ValueW )
          {
            v31 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0xA88,
                    (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                    (const char *)ValueW,
                    lpcSubKeysb);
            std::vector<unsigned char>::_Tidy(v74);
            std::wstring::_Tidy_deallocate(v105);
            std::vector<unsigned short>::_Tidy(&v86);
            std::wstring::_Tidy_deallocate(v107);
            std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(&v79);
            std::vector<unsigned short>::_Tidy(&lpName);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(&v94);
            return v31;
          }
        }
        else
        {
          if ( v15 )
            v27 = *v15;
          else
            v27 = 0;
          v28 = L"DecodedUtf8LightLogo";
LABEL_68:
          if ( RegGetValueW(v27, 0, v28, 8u, 0, v26, &v68) )
          {
            std::vector<unsigned char>::_Tidy(v74);
            std::wstring::_Tidy_deallocate(v105);
            std::vector<unsigned short>::_Tidy(&v86);
            std::wstring::_Tidy_deallocate(v107);
            std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(&v79);
            std::vector<unsigned short>::_Tidy(&lpName);
            i = v69;
            v6 = v84;
            continue;
          }
        }
        goto LABEL_97;
      }
    }
    else if ( v89 == 2 )
    {
      v32 = v15 ? *v15 : 0LL;
      if ( !RegGetValueW(v32, 0, L"DecodedUftf8DarkLogo", 8u, 0, 0, &v68) )
      {
        v33 = (char *)v74[1];
        if ( (PVOID)v68 < (PVOID)((char *)v74[1] - (char *)v74[0]) )
        {
          v34 = (char *)v74[0] + v68;
          goto LABEL_86;
        }
        if ( (PVOID)v68 > (PVOID)((char *)v74[1] - (char *)v74[0]) )
        {
          if ( v68 <= v75 - (unsigned __int64)v74[0] )
          {
            v35 = v68 - (unsigned __int64)((char *)v74[1] - (char *)v74[0]);
            memset_0(v74[1], 0, v35);
            v34 = &v33[v35];
LABEL_86:
            v74[1] = v34;
          }
          else
          {
            std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v74, v68);
          }
        }
        v25 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::GetImpl'::`2'::impl) == 0;
        v26 = v74[0];
        if ( !v25 )
        {
          if ( v15 )
            v27 = *v15;
          else
            v27 = 0;
          v28 = L"DecodedUftf8DarkLogo";
          goto LABEL_68;
        }
        if ( v15 )
          v36 = *v15;
        else
          v36 = 0;
        v37 = RegGetValueW(v36, 0, L"DecodedUftf8DarkLogo", 8u, 0, v74[0], &v68);
        if ( v37 )
        {
          v38 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xA9D,
                  (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                  (const char *)v37,
                  lpcSubKeysc);
          std::vector<unsigned char>::_Tidy(v74);
          std::wstring::_Tidy_deallocate(v105);
          std::vector<unsigned short>::_Tidy(&v86);
          std::wstring::_Tidy_deallocate(v107);
          std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(&v79);
          std::vector<unsigned short>::_Tidy(&lpName);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(&v94);
          return v38;
        }
LABEL_97:
        v6 = v84;
        i = v69;
      }
    }
    std::wstring::wstring(v108, v105);
    std::wstring::wstring(v109, v107);
    *(_OWORD *)v77 = 0;
    v78 = 0;
    FidoCredProvHelper::Locations::PluginAuthenticator::PluginAuthenticator(
      (FidoCredProvHelper::Locations::PluginAuthenticator *)v103,
      (const struct FidoCredProvHelper::Locations::PluginAuthenticator *)v108);
    v104 = 5;
    CredentialsFrom = CredentialAuthenticatorCache::GetCredentialsFrom(a1, v103, v6, v77);
    wil::details::in1diag3::Log_IfFailedWithExpected(
      retaddr,
      (void *)0xAA5,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)CredentialsFrom,
      1,
      0x80090011);
    std::_Variant_base<FidoCredProvHelper::Locations::Empty,FidoCredProvHelper::Locations::ThisPc,FidoCredProvHelper::Locations::QrCode,FidoCredProvHelper::Locations::SecurityKey,FidoCredProvHelper::Locations::LinkedDevice,FidoCredProvHelper::Locations::PluginAuthenticator,FidoCredProvHelper::Locations::SyncedAccount>::_Destroy(v103);
    v40 = v77[0];
    v41 = v77[1];
    if ( v77[0] == v77[1] )
    {
      wil::impersonate_token(v97, a1);
      v92 = 0;
      v93 = 0;
      if ( v15 )
        v42 = *v15;
      else
        v42 = 0;
      if ( (int)GetExistingCredentials(a1, v42, &v92) < 0 || (_QWORD)v92 == *((_QWORD *)&v92 + 1) )
      {
        std::vector<unsigned char>::_Tidy(&v92);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v97);
        if ( v77[0] )
        {
          std::_Destroy_range<std::allocator<CredentialInfo>>(v77[0]);
          std::_Deallocate<16>(v77[0], 32 * ((signed __int64)(v78 - (unsigned __int64)v77[0]) >> 5));
          *(_OWORD *)v77 = 0;
          v78 = 0;
        }
        FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v108);
        std::vector<unsigned char>::_Tidy(v74);
        std::wstring::_Tidy_deallocate(v105);
        std::vector<unsigned short>::_Tidy(&v86);
        std::wstring::_Tidy_deallocate(v107);
LABEL_19:
        std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(&v79);
LABEL_17:
        std::vector<unsigned short>::_Tidy(&lpName);
        continue;
      }
      v90 = 0;
      v91 = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsPostGAFixes>::GetImpl'::`2'::impl) )
      {
        LOBYTE(v67) = 0;
        v100[0] = v92;
        v100[1] = *((_QWORD *)&v92 + 1) - v92;
        v43 = CtapCbor::WebAuthNCredentialDetailsList::FromCborFallback(v96, v100);
        v101[0] = &v67;
        v101[1] = &v90;
        std::tuple<CtapCbor::WebAuthNCredentialDetailsList &,bool &>::operator=<CtapCbor::WebAuthNCredentialDetailsList,bool,0>(
          v101,
          v43);
        std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy((char *)v96 + 8);
        if ( (_BYTE)v67 )
        {
          if ( (byte_1801AEA05 & 2) != 0 )
          {
            v47 = v105;
            if ( v106 > 7 )
              v47 = (_QWORD *)v105[0];
            McTemplateU0z_EventWriteTransfer(v45, v44, v47);
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                                  `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                                  v44,
                                  v46) )
          {
            v50 = *(int **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
            if ( (unsigned int)*v50 > 3 )
            {
              v51 = (__int16 *)&dword_18018C234;
              goto LABEL_115;
            }
          }
          else if ( (unsigned int)dword_1801AB110 > 3 )
          {
            v51 = word_18018C1B2;
            v50 = &dword_1801AB110;
LABEL_115:
            v52 = v105;
            if ( v106 > 7 )
              v52 = (_QWORD *)v105[0];
            *(_QWORD *)&v96[0] = v52;
            v72 = -2089418750;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v50,
              (_DWORD)v51,
              v48,
              v49,
              (__int64)&v72,
              (__int64)v96);
          }
        }
      }
      else
      {
        v102[0] = v92;
        v102[1] = *((_QWORD *)&v92 + 1) - v92;
        v53 = CtapCbor::WebAuthNCredentialDetailsList::FromCbor(v96, v102);
        if ( &v90 != (__int128 *)v53 )
        {
          std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(&v90);
          v90 = *(_OWORD *)v53;
          v91 = *(_QWORD *)(v53 + 16);
          *(_QWORD *)v53 = 0;
          *(_QWORD *)(v53 + 8) = 0;
          *(_QWORD *)(v53 + 16) = 0;
        }
        std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(v96);
      }
      v55 = *((_QWORD *)&v90 + 1);
      for ( j = v90; j != v55; j += 272 )
      {
        CtapCbor::WebAuthNCredentialDetails::WebAuthNCredentialDetails(v110, j);
        std::vector<unsigned char>::_Assign_counted_range<unsigned char const *>(
          v112,
          v74[0],
          (char *)v74[1] - (char *)v74[0]);
        std::wstring::operator=(v111, v105);
        CtapCbor::WebAuthNCredentialDetails::WebAuthNCredentialDetails(v113, v110);
        FidoCredProvHelper::Locations::PluginAuthenticator::PluginAuthenticator(
          (FidoCredProvHelper::Locations::PluginAuthenticator *)v114,
          (const struct FidoCredProvHelper::Locations::PluginAuthenticator *)v108);
        v114[64] = 5;
        v114[76] = 0;
        v56 = CredentialAuthenticatorCache::AddCredential(a1, (const struct CredentialInfo *)v113);
        if ( v56 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xAD7,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)(unsigned int)v56,
            lpcSubKeysd);
        CredentialInfo::~CredentialInfo((CredentialInfo *)v113);
        CtapCbor::WebAuthNCredentialDetails::~WebAuthNCredentialDetails((CtapCbor::WebAuthNCredentialDetails *)v110);
      }
      FidoCredProvHelper::Locations::PluginAuthenticator::PluginAuthenticator(
        (FidoCredProvHelper::Locations::PluginAuthenticator *)v103,
        (const struct FidoCredProvHelper::Locations::PluginAuthenticator *)v108);
      v104 = 5;
      v57 = CredentialAuthenticatorCache::GetCredentialsFrom(a1, v103, v6, v77);
      wil::details::in1diag3::Log_IfFailedWithExpected(
        retaddr,
        (void *)0xAD9,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)v57,
        1,
        0x80090011);
      std::_Variant_base<FidoCredProvHelper::Locations::Empty,FidoCredProvHelper::Locations::ThisPc,FidoCredProvHelper::Locations::QrCode,FidoCredProvHelper::Locations::SecurityKey,FidoCredProvHelper::Locations::LinkedDevice,FidoCredProvHelper::Locations::PluginAuthenticator,FidoCredProvHelper::Locations::SyncedAccount>::_Destroy(v103);
      std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(&v90);
      std::vector<unsigned char>::_Tidy(&v92);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v97);
      v41 = v77[1];
      v40 = v77[0];
    }
    v58 = v40;
    v59 = v41;
    while ( v58 != v59 )
    {
      std::vector<CtapCbor::WebAuthNCredentialDetails>::_Emplace_one_at_back<CtapCbor::WebAuthNCredentialDetails>(
        &v94,
        v58);
      v58 = (CredentialInfo *)((char *)v58 + 352);
      v40 = v77[0];
    }
    if ( v40 )
    {
      std::_Destroy_range<std::allocator<CredentialInfo>>(v40);
      std::_Deallocate<16>(v77[0], 32 * ((signed __int64)(v78 - (unsigned __int64)v77[0]) >> 5));
      *(_OWORD *)v77 = 0;
      v78 = 0;
    }
    FidoCredProvHelper::CreatedPasskeyInfo::~CreatedPasskeyInfo((FidoCredProvHelper::CreatedPasskeyInfo *)v108);
    std::vector<unsigned char>::_Tidy(v74);
    std::wstring::_Tidy_deallocate(v105);
    std::vector<unsigned short>::_Tidy(&v86);
    std::wstring::_Tidy_deallocate(v107);
    std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(&v79);
    std::vector<unsigned short>::_Tidy(&lpName);
    i = v69;
  }
  CtapCbor::WebAuthNCredentialDetailsList::ToCbor(&v94, &Src);
  wil::make_unique_hlocal<unsigned char [0]>(&hMem, v99 - (_QWORD)Src);
  memcpy_0(hMem, Src, v99 - (_QWORD)Src);
  if ( a4 && a5 )
  {
    v60 = hMem;
    hMem = 0;
    *a5 = v60;
    *a4 = wil::safe_cast<unsigned long,unsigned __int64,0>(v99 - (_QWORD)Src);
  }
  v61 = hMem;
  hMem = 0;
  if ( v61 )
    LocalFree(v61);
  std::vector<unsigned char>::_Tidy(&Src);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(&v94);
  return 0;
}

```

## disassembly

```asm
0x18011293c  mov     [rsp+arg_10], rbx
0x180112941  push    rsi
0x180112942  push    rdi
0x180112943  push    r12
0x180112945  push    r14
0x180112947  push    r15
0x180112949  sub     rsp, 520h
0x180112950  mov     rax, cs:__security_cookie
0x180112957  xor     rax, rsp
0x18011295a  mov     [rsp+548h+var_38], rax
0x180112962  mov     r12, r9
0x180112965  mov     [rsp+548h+var_438], r8d
0x18011296d  mov     rsi, rdx
0x180112970  mov     [rsp+548h+var_460], rdx
0x180112978  mov     r14, rcx
0x18011297b  mov     r15, [rsp+548h+arg_20]
0x180112983  xor     edi, edi
0x180112985  test    rdx, rdx
0x180112988  jnz     short loc_1801129B2
0x18011298a  mov     rcx, [rsp+548h]; this
0x180112992  mov     ebx, 80004003h
0x180112997  mov     r9d, ebx; char *
0x18011299a  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1801129a1  mov     edx, 0A1Bh; void *
0x1801129a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801129ab  mov     eax, ebx
0x1801129ad  jmp     loc_1801139C8
0x1801129b2  test    r12, r12
0x1801129b5  jz      short loc_1801129C2
0x1801129b7  test    r15, r15
0x1801129ba  jz      short loc_1801129C2
0x1801129bc  mov     [r9], edi
0x1801129bf  mov     [r15], rdi
0x1801129c2  xorps   xmm0, xmm0
0x1801129c5  movdqu  [rsp+548h+var_400], xmm0
0x1801129ce  mov     [rsp+548h+var_3F0], rdi
0x1801129d6  mov     [rsp+548h+hKey], rdi
0x1801129db  lea     rdx, [rsp+548h+hKey]
0x1801129e0  call    GetUserPluginAuthenticatorsRegKey
0x1801129e5  mov     ebx, eax
0x1801129e7  test    eax, eax
0x1801129e9  jns     short loc_180112A27
0x1801129eb  mov     rcx, [rsp+548h]; this
0x1801129f3  mov     r9d, eax; char *
0x1801129f6  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1801129fd  mov     edx, 0A26h; void *
0x180112a02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180112a07  nop
0x180112a08  lea     rcx, [rsp+548h+hKey]
0x180112a0d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180112a12  nop
0x180112a13  lea     rcx, [rsp+548h+var_400]
0x180112a1b  call    ?_Tidy@?$vector@UWebAuthNCredentialDetails@CtapCbor@@V?$allocator@UWebAuthNCredentialDetails@CtapCbor@@@std@@@std@@AEAAXXZ; std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(void)
0x180112a20  mov     eax, ebx
0x180112a22  jmp     loc_1801139C8
0x180112a27  xor     ebx, ebx
0x180112a29  mov     [rsp+548h+cSubKeys], ebx
0x180112a30  mov     [rsp+548h+cbMaxSubKeyLen], ebx
0x180112a34  mov     [rsp+548h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x180112a39  mov     [rsp+548h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x180112a3e  mov     [rsp+548h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x180112a43  mov     [rsp+548h+lpcbMaxValueNameLen], rbx; lpcbMaxValueNameLen
0x180112a48  mov     [rsp+548h+lpcValues], rbx; lpcValues
0x180112a4d  mov     [rsp+548h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x180112a52  lea     rax, [rsp+548h+cbMaxSubKeyLen]
0x180112a57  mov     [rsp+548h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180112a5c  lea     rax, [rsp+548h+cSubKeys]
0x180112a64  mov     [rsp+548h+lpcSubKeys], rax; int
0x180112a69  xor     r9d, r9d; lpReserved
0x180112a6c  xor     r8d, r8d; lpcchClass
0x180112a6f  xor     edx, edx; lpClass
0x180112a71  mov     rcx, [rsp+548h+hKey]; hKey
0x180112a76  call    cs:__imp_RegQueryInfoKeyW
0x180112a7c  test    eax, eax
0x180112a7e  jz      short loc_180112ABD
0x180112a80  mov     rcx, [rsp+548h]; this
0x180112a88  mov     r9d, eax; char *
0x180112a8b  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180112a92  mov     edx, 0A2Bh; void *
0x180112a97  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180112a9c  mov     ebx, eax
0x180112a9e  lea     rcx, [rsp+548h+hKey]
0x180112aa3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180112aa8  nop
0x180112aa9  lea     rcx, [rsp+548h+var_400]
0x180112ab1  call    ?_Tidy@?$vector@UWebAuthNCredentialDetails@CtapCbor@@V?$allocator@UWebAuthNCredentialDetails@CtapCbor@@@std@@@std@@AEAAXXZ; std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(void)
0x180112ab6  mov     eax, ebx
0x180112ab8  jmp     loc_1801139C8
0x180112abd  inc     [rsp+548h+cbMaxSubKeyLen]
0x180112ac1  cmp     [rsp+548h+cSubKeys], ebx
0x180112ac8  jnz     short loc_180112B0C
0x180112aca  mov     rcx, [rsp+548h]; this
0x180112ad2  mov     r9d, 80090011h; char *
0x180112ad8  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180112adf  mov     edx, 0A30h; void *
0x180112ae4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180112ae9  nop
0x180112aea  lea     rcx, [rsp+548h+hKey]
0x180112aef  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180112af4  nop
0x180112af5  lea     rcx, [rsp+548h+var_400]
0x180112afd  call    ?_Tidy@?$vector@UWebAuthNCredentialDetails@CtapCbor@@V?$allocator@UWebAuthNCredentialDetails@CtapCbor@@@std@@@std@@AEAAXXZ; std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(void)
0x180112b02  mov     eax, 80090011h
0x180112b07  jmp     loc_1801139C8
0x180112b0c  mov     rcx, r14; void *
0x180112b0f  call    ?IsHelloEnrolled@@YA_NQEAX@Z; IsHelloEnrolled(void * const)
0x180112b14  test    al, al
0x180112b16  jnz     short loc_180112B59
0x180112b18  mov     rcx, [rsp+548h]; this
0x180112b20  mov     ebx, 80548211h
0x180112b25  mov     r9d, ebx; char *
0x180112b28  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180112b2f  mov     edx, 0A34h; void *
0x180112b34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180112b39  nop
0x180112b3a  lea     rcx, [rsp+548h+hKey]
0x180112b3f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180112b44  nop
0x180112b45  lea     rcx, [rsp+548h+var_400]
0x180112b4d  call    ?_Tidy@?$vector@UWebAuthNCredentialDetails@CtapCbor@@V?$allocator@UWebAuthNCredentialDetails@CtapCbor@@@std@@@std@@AEAAXXZ; std::vector<CtapCbor::WebAuthNCredentialDetails>::_Tidy(void)
0x180112b52  mov     eax, ebx
0x180112b54  jmp     loc_1801139C8
0x180112b59  mov     edi, ebx
0x180112b5b  mov     [rsp+548h+var_4E0], edi
0x180112b5f  cmp     edi, [rsp+548h+cSubKeys]
0x180112b66  jnb     loc_1801138F4
0x180112b6c  mov     edx, [rsp+548h+cbMaxSubKeyLen]
0x180112b70  lea     rcx, [rsp+548h+lpName]
0x180112b78  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x180112b7d  nop
0x180112b7e  mov     r9d, [rsp+548h+cbMaxSubKeyLen]; cchName
0x180112b83  mov     r8, [rsp+548h+lpName]; lpName
0x180112b8b  mov     edx, edi; dwIndex
0x180112b8d  mov     rcx, [rsp+548h+hKey]; hKey
0x180112b92  call    cs:__imp_RegEnumKeyW
0x180112b98  test    eax, eax
0x180112b9a  jz      short loc_180112BAE
0x180112b9c  lea     rcx, [rsp+548h+lpName]
0x180112ba4  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180112ba9  jmp     loc_180112E12
0x180112bae  xorps   xmm0, xmm0
0x180112bb1  movdqu  [rsp+548h+var_490], xmm0
0x180112bba  lea     rcx, [rsp+548h+var_490]
0x180112bc2  call    ?put@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>::put(void)
0x180112bc7  mov     [rsp+548h+lpcSubKeys], rax; phkResult
0x180112bcc  mov     r9d, 0F003Fh; samDesired
0x180112bd2  xor     r8d, r8d; ulOptions
0x180112bd5  mov     rdx, [rsp+548h+lpName]; lpSubKey
0x180112bdd  mov     rcx, [rsp+548h+hKey]; hKey
0x180112be2  call    cs:__imp_RegOpenKeyExW
0x180112be8  test    eax, eax
0x180112bea  jz      short loc_180112BFB
0x180112bec  lea     rcx, [rsp+548h+var_490]
0x180112bf4  call    ??1?$shared_ptr@UCredentialInfo@@@std@@QEAA@XZ; std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(void)
0x180112bf9  jmp     short loc_180112B9C
0x180112bfb  mov     word ptr [rsp+548h+var_4E8], bx
0x180112c00  mov     rdx, [rsp+548h+var_478]
0x180112c08  cmp     rdx, [rsp+548h+var_470]
0x180112c10  jz      short loc_180112C20
0x180112c12  mov     [rdx], bx
0x180112c15  add     [rsp+548h+var_478], 2
0x180112c1e  jmp     short loc_180112C32
0x180112c20  lea     r8, [rsp+548h+var_4E8]
0x180112c25  lea     rcx, [rsp+548h+lpName]
0x180112c2d  call    ??$_Emplace_reallocate@G@?$vector@GV?$allocator@G@std@@@std@@AEAAPEAGQEAG$$QEAG@Z; std::vector<ushort>::_Emplace_reallocate<ushort>(ushort * const,ushort &&)
0x180112c32  mov     rdx, [rsp+548h+lpName]
0x180112c3a  lea     rcx, [rsp+548h+var_310]
0x180112c42  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180112c47  nop
0x180112c48  mov     [rsp+548h+pvData], ebx
0x180112c4f  mov     [rsp+548h+pcbData], 4
0x180112c57  mov     rbx, qword ptr [rsp+548h+var_490]
0x180112c5f  test    rbx, rbx
0x180112c62  jz      short loc_180112C69
0x180112c64  mov     rcx, [rbx]
0x180112c67  jmp     short loc_180112C6B
0x180112c69  xor     ecx, ecx; hkey
0x180112c6b  lea     rax, [rsp+548h+pcbData]
0x180112c70  mov     [rsp+548h+lpcbMaxClassLen], rax; pcbData
0x180112c75  lea     rax, [rsp+548h+pvData]
0x180112c7d  mov     [rsp+548h+lpcbMaxSubKeyLen], rax; pvData
0x180112c82  mov     [rsp+548h+lpcSubKeys], 0; pdwType
0x180112c8b  mov     r9d, 10h; dwFlags
0x180112c91  lea     r8, aState; "State"
0x180112c98  xor     edx, edx; lpSubKey
0x180112c9a  call    cs:__imp_RegGetValueW
0x180112ca0  test    eax, eax
0x180112ca2  jnz     loc_180112DE7
0x180112ca8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements> `wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl(void)'::`2'::impl
0x180112caf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(void)
0x180112cb4  test    al, al
0x180112cb6  jz      short loc_180112CFC
0x180112cb8  cmp     [rsp+548h+pvData], 0
0x180112cc0  jnz     short loc_180112CFC
0x180112cc2  mov     [rsp+548h+var_4E8], 0
0x180112cca  test    rbx, rbx
0x180112ccd  jz      short loc_180112CD4
0x180112ccf  mov     rcx, [rbx]
0x180112cd2  jmp     short loc_180112CD6
0x180112cd4  xor     ecx, ecx
0x180112cd6  lea     r9, [rsp+548h+var_4E8]
0x180112cdb  lea     r8, aStatetoggled; "StateToggled"
0x180112ce2  xor     edx, edx
0x180112ce4  call    ??$get_value_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z; wil::reg::get_value_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180112ce9  test    eax, eax
0x180112ceb  js      loc_180112DE7
0x180112cf1  cmp     [rsp+548h+var_4E8], 1
0x180112cf6  jz      loc_180112DE7
0x180112cfc  xorps   xmm0, xmm0
0x180112cff  movdqu  [rsp+548h+var_3E8], xmm0
0x180112d08  mov     rax, qword ptr [rsp+548h+var_490+8]
0x180112d10  test    rax, rax
0x180112d13  jz      short loc_180112D19
0x180112d15  lock inc dword ptr [rax+8]
0x180112d19  mov     qword ptr [rsp+548h+var_3E8], rbx
0x180112d21  mov     qword ptr [rsp+548h+var_3E8+8], rax
0x180112d29  lea     rdx, [rsp+548h+var_3E8]
0x180112d31  mov     rcx, r14
0x180112d34  call    IsPluginPackagePresent
0x180112d39  xor     edx, edx; lpSubKey
0x180112d3b  test    al, al
0x180112d3d  jz      loc_180112DE7
0x180112d43  mov     [rsp+548h+pcbData], edx
0x180112d47  test    rbx, rbx
0x180112d4a  jz      short loc_180112D51
0x180112d4c  mov     rcx, [rbx]
0x180112d4f  jmp     short loc_180112D54
0x180112d51  mov     rcx, rdx; hkey
0x180112d54  lea     rax, [rsp+548h+pcbData]
0x180112d59  mov     [rsp+548h+lpcbMaxClassLen], rax; pcbData
0x180112d5e  mov     [rsp+548h+lpcbMaxSubKeyLen], rdx; pvData
0x180112d63  mov     [rsp+548h+lpcSubKeys], rdx; pdwType
0x180112d68  mov     r9d, 2; dwFlags
0x180112d6e  lea     r8, aName; "Name"
0x180112d75  call    cs:__imp_RegGetValueW
0x180112d7b  test    eax, eax
0x180112d7d  jnz     short loc_180112DE7
0x180112d7f  mov     edx, [rsp+548h+pcbData]
0x180112d83  shr     rdx, 1
0x180112d86  lea     rcx, [rsp+548h+var_450]
0x180112d8e  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x180112d93  nop
0x180112d94  mov     rax, [rsp+548h+var_450]
0x180112d9c  test    rbx, rbx
0x180112d9f  jz      short loc_180112DA6
0x180112da1  mov     rcx, [rbx]
0x180112da4  jmp     short loc_180112DA8
0x180112da6  xor     ecx, ecx; hkey
0x180112da8  lea     rdx, [rsp+548h+pcbData]
0x180112dad  mov     [rsp+548h+lpcbMaxClassLen], rdx; pcbData
0x180112db2  mov     [rsp+548h+lpcbMaxSubKeyLen], rax; pvData
0x180112db7  mov     [rsp+548h+lpcSubKeys], 0; pdwType
0x180112dc0  mov     r9d, 2; dwFlags
0x180112dc6  lea     r8, aName; "Name"
0x180112dcd  xor     edx, edx; lpSubKey
0x180112dcf  call    cs:__imp_RegGetValueW
0x180112dd5  test    eax, eax
0x180112dd7  jz      short loc_180112E19
0x180112dd9  lea     rcx, [rsp+548h+var_450]
0x180112de1  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180112de6  nop
0x180112de7  lea     rcx, [rsp+548h+var_310]
0x180112def  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180112df4  nop
0x180112df5  lea     rcx, [rsp+548h+var_490]
0x180112dfd  call    ??1?$shared_ptr@UCredentialInfo@@@std@@QEAA@XZ; std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(void)
0x180112e02  nop
0x180112e03  lea     rcx, [rsp+548h+lpName]
0x180112e0b  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180112e10  xor     ebx, ebx
0x180112e12  inc     edi
0x180112e14  jmp     loc_180112B5B
0x180112e19  xor     eax, eax
0x180112e1b  mov     word ptr [rsp+548h+var_4E8], ax
0x180112e20  mov     rdx, [rsp+548h+var_448]
0x180112e28  cmp     rdx, [rsp+548h+var_440]
0x180112e30  jz      short loc_180112E40
0x180112e32  mov     [rdx], ax
0x180112e35  add     [rsp+548h+var_448], 2
0x180112e3e  jmp     short loc_180112E52
0x180112e40  lea     r8, [rsp+548h+var_4E8]
0x180112e45  lea     rcx, [rsp+548h+var_450]
0x180112e4d  call    ??$_Emplace_reallocate@G@?$vector@GV?$allocator@G@std@@@std@@AEAAPEAGQEAG$$QEAG@Z; std::vector<ushort>::_Emplace_reallocate<ushort>(ushort * const,ushort &&)
0x180112e52  mov     rdx, [rsp+548h+var_450]
0x180112e5a  lea     rcx, [rsp+548h+var_330]
0x180112e62  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180112e67  nop
0x180112e68  xor     edx, edx
0x180112e6a  mov     [rsp+548h+var_4E4], edx
0x180112e6e  xorps   xmm0, xmm0
0x180112e71  movdqu  xmmword ptr [rsp+548h+var_4C8], xmm0
0x180112e7a  mov     [rsp+548h+var_4B8], rdx
0x180112e82  mov     eax, [rsp+548h+var_438]
0x180112e89  cmp     eax, 1
0x180112e8c  jnz     loc_1801130C8
0x180112e92  test    rbx, rbx
0x180112e95  jz      short loc_180112E9C
0x180112e97  mov     rcx, [rbx]
0x180112e9a  jmp     short loc_180112E9F
0x180112e9c  mov     rcx, rdx; hkey
  ... truncated ...
```
