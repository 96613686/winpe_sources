# CtapPluginGetAuthenticatorDetailsList

- ea: `0x1801139f8`
- end: `0x1801147e1`
- name: `CtapPluginGetAuthenticatorDetailsList`
- size: `3561`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `38`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001d264`

## callees

- `0x18001d5fc`
- `0x18001d650`
- `0x18001df88`
- `0x18001ed38`
- `0x18001ee7c`
- `0x1800205e4`
- `0x180021878`
- `0x180023bc8`
- `0x1800328b8`
- `0x1800350b4`
- `0x180036da4`
- `0x180037f6c`
- `0x180042df8`
- `0x180042e40`
- `0x18004349c`
- `0x1800435c0`
- `0x1800467e0`
- `0x1800537a4`
- `0x18006f750`
- `0x180075e24`
- `0x18007ed34`
- `0x180099c24`
- `0x18009c850`
- `0x18009cf1c`
- `0x18009dab4`
- `0x18009e104`
- `0x18009e444`
- `0x1800c1508`
- `0x18010adf0`
- `0x18010bfa8`
- `0x18010dbb8`
- `0x18010ee78`
- `0x1801139f8`
- `0x18011c42c`
- `0x18011e82c`
- `0x18011f0b0`
- `0x18013c090`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180113acd`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180113acd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180113d84`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180113e55`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180113f8d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18011403b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180114124`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801141d2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180113d84`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180113e55`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180113f8d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18011403b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180114124`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801141d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180113c15`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180113c15`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180113ced`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180113ced`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180113bd3`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180113bd3`

## string_xrefs

- `0x180113a5b`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180113ae2`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180113b24`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180113b63`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180113b97`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall CtapPluginGetAuthenticatorDetailsList(void *a1, int a2, __int64 a3)
{
  __int64 v3; // r14
  int v4; // edi
  int UserPluginAuthenticatorsRegKey; // eax
  unsigned int v7; // ebx
  unsigned int v9; // eax
  unsigned int v10; // ebx
  DWORD i; // r13d
  HKEY *v12; // rax
  __int64 v13; // r15
  HKEY *v14; // rbx
  const OLECHAR *v15; // rcx
  HRESULT v16; // eax
  HKEY v17; // rcx
  unsigned int ValueW; // eax
  unsigned int v19; // ebx
  HKEY v20; // rcx
  unsigned int v21; // eax
  unsigned int v22; // ebx
  HKEY v23; // rcx
  char *v24; // r14
  char *v25; // rax
  size_t v26; // rdi
  HKEY v27; // rcx
  unsigned int v28; // eax
  unsigned int v29; // ebx
  HKEY v30; // rcx
  char *v31; // r14
  char *v32; // rax
  size_t v33; // rdi
  HKEY v34; // rcx
  unsigned int v35; // eax
  unsigned int v36; // ebx
  HKEY v37; // rcx
  int value; // eax
  unsigned int v39; // edi
  HKEY v40; // rcx
  int v41; // eax
  __int64 v42; // rax
  int v43; // eax
  _QWORD *v44; // rax
  __int64 v45; // rax
  int v46; // eax
  int v47; // ebx
  int v48; // eax
  wil::details::in1diag3 *v49; // rcx
  __int64 v50; // rdx
  int lpcSubKeys; // [rsp+20h] [rbp-268h]
  unsigned int lpcSubKeysa; // [rsp+20h] [rbp-268h]
  int lpcSubKeysb; // [rsp+20h] [rbp-268h]
  unsigned int lpcSubKeysc; // [rsp+20h] [rbp-268h]
  unsigned int lpcSubKeysd; // [rsp+20h] [rbp-268h]
  __int16 v56; // [rsp+60h] [rbp-228h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-220h] BYREF
  DWORD v58; // [rsp+70h] [rbp-218h] BYREF
  int v59; // [rsp+74h] [rbp-214h]
  DWORD cbMaxSubKeyLen; // [rsp+78h] [rbp-210h] BYREF
  unsigned int v61; // [rsp+7Ch] [rbp-20Ch] BYREF
  int v62; // [rsp+80h] [rbp-208h] BYREF
  int v63; // [rsp+84h] [rbp-204h] BYREF
  __int128 v64; // [rsp+88h] [rbp-200h] BYREF
  PVOID v65[2]; // [rsp+98h] [rbp-1F0h] BYREF
  __int64 v66; // [rsp+A8h] [rbp-1E0h]
  __int128 v67; // [rsp+B0h] [rbp-1D8h] BYREF
  DWORD cSubKeys; // [rsp+C0h] [rbp-1C8h] BYREF
  DWORD pcbData; // [rsp+C4h] [rbp-1C4h] BYREF
  PVOID pvData; // [rsp+C8h] [rbp-1C0h] BYREF
  _WORD *v71; // [rsp+D0h] [rbp-1B8h]
  _WORD *v72; // [rsp+D8h] [rbp-1B0h]
  _BYTE v73[16]; // [rsp+E0h] [rbp-1A8h] BYREF
  LPWSTR lpName; // [rsp+F0h] [rbp-198h] BYREF
  _WORD *v75; // [rsp+F8h] [rbp-190h]
  _WORD *v76; // [rsp+100h] [rbp-188h]
  _BYTE v77[24]; // [rsp+108h] [rbp-180h] BYREF
  __int64 v78; // [rsp+120h] [rbp-168h]
  LPVOID ppv[2]; // [rsp+128h] [rbp-160h] BYREF
  __int128 v80; // [rsp+138h] [rbp-150h]
  char v81[8]; // [rsp+148h] [rbp-140h] BYREF
  _OWORD v82[2]; // [rsp+150h] [rbp-138h] BYREF
  char v83[16]; // [rsp+170h] [rbp-118h] BYREF
  char v84[16]; // [rsp+180h] [rbp-108h] BYREF
  char v85[16]; // [rsp+190h] [rbp-F8h] BYREF
  LPCOLESTR lpsz[4]; // [rsp+1A0h] [rbp-E8h] BYREF
  _BYTE v87[32]; // [rsp+1C0h] [rbp-C8h] BYREF
  GUID pclsid; // [rsp+1E0h] [rbp-A8h] BYREF
  int v89; // [rsp+1F0h] [rbp-98h] BYREF
  __int64 v90; // [rsp+1F8h] [rbp-90h] BYREF
  __int128 v91; // [rsp+200h] [rbp-88h]
  _BYTE v92[32]; // [rsp+210h] [rbp-78h] BYREF
  __int128 v93; // [rsp+230h] [rbp-58h] BYREF
  __int64 v94; // [rsp+240h] [rbp-48h]
  bool v95; // [rsp+248h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  v3 = a3;
  v78 = a3;
  v4 = a2;
  v59 = a2;
  hKey = 0;
  UserPluginAuthenticatorsRegKey = GetUserPluginAuthenticatorsRegKey(a1, &hKey);
  v7 = UserPluginAuthenticatorsRegKey;
  if ( UserPluginAuthenticatorsRegKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5CE,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)(unsigned int)UserPluginAuthenticatorsRegKey,
      lpcSubKeys);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v7;
  }
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v9 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v9 )
  {
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x5D3,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)v9,
            lpcSubKeysa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v10;
  }
  ++cbMaxSubKeyLen;
  if ( !cSubKeys )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D7,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)0x80090011LL,
      lpcSubKeysa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return 2148073489LL;
  }
  if ( !IsHelloEnrolled(a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5DC,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)0x80090011LL,
      lpcSubKeysa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return 2148073489LL;
  }
  std::map<std::wstring,PluginAuthenticatorInstance>::map<std::wstring,PluginAuthenticatorInstance>(v73);
  for ( i = 0; i < cSubKeys; ++i )
  {
    std::vector<unsigned short>::vector<unsigned short>(&lpName, cbMaxSubKeyLen);
    if ( RegEnumKeyW(hKey, i, lpName, cbMaxSubKeyLen) )
      goto LABEL_113;
    v67 = 0;
    v12 = (HKEY *)wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>::put(&v67);
    if ( !RegOpenKeyExW(hKey, lpName, 0, 0xF003Fu, v12) )
    {
      v64 = 0;
      v13 = *((_QWORD *)&v67 + 1);
      if ( *((_QWORD *)&v67 + 1) )
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL));
      v14 = (HKEY *)v67;
      *(_QWORD *)&v64 = v67;
      *((_QWORD *)&v64 + 1) = v13;
      if ( (unsigned __int8)IsPluginPackagePresent(a1, &v64) )
      {
        v56 = 0;
        if ( v75 == v76 )
          std::vector<unsigned short>::_Emplace_reallocate<unsigned short>(&lpName, v75, &v56);
        else
          *v75++ = 0;
        std::wstring::wstring(lpsz, lpName);
        pclsid = 0;
        v15 = (const OLECHAR *)lpsz;
        if ( lpsz[3] > (LPCOLESTR)7 )
          v15 = lpsz[0];
        v16 = CLSIDFromString(v15, &pclsid);
        if ( v16 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x5F3,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)(unsigned int)v16,
            lpcSubKeysb);
          std::wstring::_Tidy_deallocate(lpsz);
          std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(&v67);
          goto LABEL_113;
        }
        ConvertGuidToBigEndian(v77, &pclsid);
        pcbData = 0;
        if ( v14 )
          v17 = *v14;
        else
          v17 = 0;
        ValueW = RegGetValueW(v17, 0, L"Name", 2u, 0, 0, &pcbData);
        if ( ValueW )
        {
          v19 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x5FC,
                  (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                  (const char *)ValueW,
                  lpcSubKeysc);
          std::vector<unsigned char>::_Tidy(v77);
          std::wstring::_Tidy_deallocate(lpsz);
          std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(&v67);
          std::vector<unsigned short>::_Tidy(&lpName);
          std::_Tree<std::_Tmap_traits<std::wstring,PluginAuthenticatorInstance,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PluginAuthenticatorInstance>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,PluginAuthenticatorInstance,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PluginAuthenticatorInstance>>,0>>(v73);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return v19;
        }
        std::vector<unsigned short>::vector<unsigned short>(&pvData, (unsigned __int64)pcbData >> 1);
        if ( v14 )
          v20 = *v14;
        else
          v20 = 0;
        v21 = RegGetValueW(v20, 0, L"Name", 2u, 0, pvData, &pcbData);
        if ( v21 )
        {
          v22 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x5FF,
                  (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                  (const char *)v21,
                  lpcSubKeysd);
          std::vector<unsigned short>::_Tidy(&pvData);
          std::vector<unsigned char>::_Tidy(v77);
          std::wstring::_Tidy_deallocate(lpsz);
          std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(&v67);
          std::vector<unsigned short>::_Tidy(&lpName);
          std::_Tree<std::_Tmap_traits<std::wstring,PluginAuthenticatorInstance,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PluginAuthenticatorInstance>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,PluginAuthenticatorInstance,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PluginAuthenticatorInstance>>,0>>(v73);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return v22;
        }
        v56 = 0;
        if ( v71 == v72 )
          std::vector<unsigned short>::_Emplace_reallocate<unsigned short>(&pvData, v71, &v56);
        else
          *v71++ = 0;
        std::wstring::wstring(v87, pvData);
        v58 = 0;
        *(_OWORD *)v65 = 0;
        v66 = 0;
        if ( v4 == 1 )
        {
          if ( v14 )
            v23 = *v14;
          else
            v23 = 0;
          if ( !RegGetValueW(v23, 0, L"DecodedUtf8LightLogo", 8u, 0, 0, &v58) )
          {
            v24 = (char *)v65[1];
            if ( (PVOID)v58 < (PVOID)((char *)v65[1] - (char *)v65[0]) )
            {
              v25 = (char *)v65[0] + v58;
              goto LABEL_47;
            }
            if ( (PVOID)v58 > (PVOID)((char *)v65[1] - (char *)v65[0]) )
            {
              if ( v58 <= v66 - (unsigned __int64)v65[0] )
              {
                v26 = v58 - (unsigned __int64)((char *)v65[1] - (char *)v65[0]);
                memset_0(v65[1], 0, v26);
                v25 = &v24[v26];
LABEL_47:
                v65[1] = v25;
              }
              else
              {
                std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v65, v58);
              }
            }
            if ( v14 )
              v27 = *v14;
            else
              v27 = 0;
            v28 = RegGetValueW(v27, 0, L"DecodedUtf8LightLogo", 8u, 0, v65[0], &v58);
            if ( v28 )
            {
              v29 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x60C,
                      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                      (const char *)v28,
                      lpcSubKeysd);
              std::vector<unsigned char>::_Tidy(v65);
              std::wstring::_Tidy_deallocate(v87);
              std::vector<unsigned short>::_Tidy(&pvData);
              std::vector<unsigned char>::_Tidy(v77);
              std::wstring::_Tidy_deallocate(lpsz);
              std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(&v67);
              std::vector<unsigned short>::_Tidy(&lpName);
              std::_Tree<std::_Tmap_traits<std::wstring,PluginAuthenticatorInstance,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PluginAuthenticatorInstance>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,PluginAuthenticatorInstance,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PluginAuthenticatorInstance>>,0>>(v73);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
              return v29;
            }
LABEL_70:
            v3 = v78;
          }
LABEL_71:
          v61 = 0;
          if ( v14 )
            v37 = *v14;
          else
            v37 = 0;
          value = wil::reg::get_value_nothrow<unsigned long,0>(v37, 0, L"State", &v61);
          v39 = value;
          if ( value < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x61A,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
              (const char *)(unsigned int)value,
              lpcSubKeysd);
            std::vector<unsigned char>::_Tidy(v65);
            std::wstring::_Tidy_deallocate(v87);
            std::vector<unsigned short>::_Tidy(&pvData);
            std::vector<unsigned char>::_Tidy(v77);
            std::wstring::_Tidy_deallocate(lpsz);
            std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(&v67);
            std::vector<unsigned short>::_Tidy(&lpName);
            std::_Tree<std::_Tmap_traits<std::wstring,PluginAuthenticatorInstance,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PluginAuthenticatorInstance>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,PluginAuthenticatorInstance,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PluginAuthenticatorInstance>>,0>>(v73);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            return v39;
          }
          if ( v61 >= 2 )
            v61 = 0;
          v64 = 0;
          if ( v13 )
            _InterlockedIncrement((volatile signed __int32 *)(v13 + 8));
          *(_QWORD *)&v64 = v14;
          *((_QWORD *)&v64 + 1) = v13;
          if ( !(unsigned __int8)IsPluginPackagePresent(a1, &v64) )
            goto LABEL_111;
          v63 = 0;
          if ( v14 )
            v40 = *v14;
          else
            v40 = 0;
          v41 = wil::reg::get_value_nothrow<unsigned long,0>(v40, 0, L"StateToggled", &v63);
          if ( v41 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x627,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
              (const char *)(unsigned int)v41,
              lpcSubKeysd);
          if ( v61 != 1 && v63 )
            goto LABEL_111;
          v62 = 0;
          *(_QWORD *)&v64 = -1;
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
          {
            v42 = wil::impersonate_token(v81, a1);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>>::operator=(
              &v64,
              v42);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v81);
          }
          *(_OWORD *)ppv = 0;
          v80 = 0;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
          {
            memset(v82, 0, sizeof(v82));
            v43 = InstantiatePasskeyManager(a1, lpsz, v82);
            if ( v43 < 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x639,
                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                (const char *)(unsigned int)v43,
                lpcSubKeysd);
              PluginAuthenticatorInstance::~PluginAuthenticatorInstance((PluginAuthenticatorInstance *)v82);
              goto LABEL_110;
            }
            v44 = (_QWORD *)std::map<std::wstring,PluginAuthenticatorInstance>::_Try_emplace<std::wstring const &,>(
                              v73,
                              v83,
                              lpsz);
            PluginAuthenticatorInstance::operator=(*v44 + 64LL, v82);
            PluginAuthenticatorInstance::~PluginAuthenticatorInstance((PluginAuthenticatorInstance *)v82);
LABEL_94:
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
            {
              if ( !*(_QWORD *)(*(_QWORD *)std::map<std::wstring,PluginAuthenticatorInstance>::_Try_emplace<std::wstring const &,>(
                                             v73,
                                             v84,
                                             lpsz)
                              + 88LL) )
                goto LABEL_110;
              v45 = std::map<std::wstring,PluginAuthenticatorInstance>::_Try_emplace<std::wstring const &,>(
                      v73,
                      v85,
                      lpsz);
              v46 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)(*(_QWORD *)v45 + 88LL) + 48LL))(
                      *(_QWORD *)(*(_QWORD *)v45 + 88LL),
                      &v62);
              v47 = v46;
              if ( v46 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x64C,
                  (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                  (const char *)(unsigned int)v46,
                  lpcSubKeysd);
              if ( v47 != -2147467263 )
              {
                if ( v47 >= 0 )
                {
LABEL_109:
                  v89 = 1;
                  v90 = 0;
                  v91 = 0;
                  std::wstring::wstring(v92);
                  v93 = 0;
                  v94 = 0;
                  std::vector<unsigned char>::operator=(&v93, v65);
                  std::vector<unsigned char>::operator=(&v90, v77);
                  std::wstring::operator=(v92, v87);
                  v95 = v62 == 0;
                  std::vector<CtapCbor::WebAuthNAuthenticatorDetails>::_Emplace_one_at_back<CtapCbor::WebAuthNAuthenticatorDetails>(
                    v3,
                    &v89);
                  CtapCbor::WebAuthNAuthenticatorDetails::~WebAuthNAuthenticatorDetails((CtapCbor::WebAuthNAuthenticatorDetails *)&v89);
                }
LABEL_110:
                PluginAuthenticatorInstance::~PluginAuthenticatorInstance((PluginAuthenticatorInstance *)ppv);
                wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v64);
LABEL_111:
                std::vector<unsigned char>::_Tidy(v65);
                std::wstring::_Tidy_deallocate(v87);
                std::vector<unsigned short>::_Tidy(&pvData);
                std::vector<unsigned char>::_Tidy(v77);
                std::wstring::_Tidy_deallocate(lpsz);
                std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(&v67);
                v4 = v59;
                goto LABEL_113;
              }
LABEL_108:
              v62 = 0;
              goto LABEL_109;
            }
            if ( !*((_QWORD *)&v80 + 1) )
            {
              if ( !(_QWORD)v80 )
                goto LABEL_110;
              goto LABEL_108;
            }
            v48 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)&v80 + 1) + 48LL))(
                    *((_QWORD *)&v80 + 1),
                    &v62);
            v49 = retaddr;
            if ( v48 >= 0 )
              goto LABEL_109;
            v50 = 1632;
          }
          else
          {
            v48 = InstantiatePasskeyManagerOld((LPCOLESTR)lpsz, ppv);
            v49 = retaddr;
            if ( v48 >= 0 )
              goto LABEL_94;
            v50 = 1601;
          }
          wil::details::in1diag3::_Log_Hr(
            v49,
            (void *)v50,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)(unsigned int)v48,
            lpcSubKeysd);
          goto LABEL_110;
        }
        if ( v4 != 2 )
          goto LABEL_71;
        v30 = v14 ? *v14 : 0LL;
        if ( RegGetValueW(v30, 0, L"DecodedUftf8DarkLogo", 8u, 0, 0, &v58) )
          goto LABEL_71;
        v31 = (char *)v65[1];
        if ( (PVOID)v58 < (PVOID)((char *)v65[1] - (char *)v65[0]) )
        {
          v32 = (char *)v65[0] + v58;
          goto LABEL_64;
        }
        if ( (PVOID)v58 > (PVOID)((char *)v65[1] - (char *)v65[0]) )
        {
          if ( v58 <= v66 - (unsigned __int64)v65[0] )
          {
            v33 = v58 - (unsigned __int64)((char *)v65[1] - (char *)v65[0]);
            memset_0(v65[1], 0, v33);
            v32 = &v31[v33];
LABEL_64:
            v65[1] = v32;
          }
          else
          {
            std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v65, v58);
          }
        }
        if ( v14 )
          v34 = *v14;
        else
          v34 = 0;
        v35 = RegGetValueW(v34, 0, L"DecodedUftf8DarkLogo", 8u, 0, v65[0], &v58);
        if ( v35 )
        {
          v36 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x615,
                  (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                  (const char *)v35,
                  lpcSubKeysd);
          std::vector<unsigned char>::_Tidy(v65);
          std::wstring::_Tidy_deallocate(v87);
          std::vector<unsigned short>::_Tidy(&pvData);
          std::vector<unsigned char>::_Tidy(v77);
          std::wstring::_Tidy_deallocate(lpsz);
          std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(&v67);
          std::vector<unsigned short>::_Tidy(&lpName);
          std::_Tree<std::_Tmap_traits<std::wstring,PluginAuthenticatorInstance,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PluginAuthenticatorInstance>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,PluginAuthenticatorInstance,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PluginAuthenticatorInstance>>,0>>(v73);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return v36;
        }
        goto LABEL_70;
      }
    }
    std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(&v67);
LABEL_113:
    std::vector<unsigned short>::_Tidy(&lpName);
  }
  std::_Tree<std::_Tmap_traits<std::wstring,PluginAuthenticatorInstance,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PluginAuthenticatorInstance>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,PluginAuthenticatorInstance,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PluginAuthenticatorInstance>>,0>>(v73);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x1801139f8  mov     [rsp+arg_8], rbx
0x1801139fd  mov     [rsp+arg_18], rsi
0x180113a02  push    rdi
0x180113a03  push    r12
0x180113a05  push    r13
0x180113a07  push    r14
0x180113a09  push    r15
0x180113a0b  sub     rsp, 260h
0x180113a12  mov     rax, cs:__security_cookie
0x180113a19  xor     rax, rsp
0x180113a1c  mov     [rsp+288h+var_38], rax
0x180113a24  mov     r14, r8
0x180113a27  mov     [rsp+288h+var_168], r8
0x180113a2f  mov     edi, edx
0x180113a31  mov     [rsp+288h+var_214], edx
0x180113a35  mov     r12, rcx
0x180113a38  xor     r15d, r15d
0x180113a3b  mov     [rsp+288h+hKey], r15
0x180113a40  lea     rdx, [rsp+288h+hKey]
0x180113a45  call    GetUserPluginAuthenticatorsRegKey
0x180113a4a  mov     ebx, eax
0x180113a4c  test    eax, eax
0x180113a4e  jns     short loc_180113A7E
0x180113a50  mov     rcx, [rsp+288h]; this
0x180113a58  mov     r9d, eax; char *
0x180113a5b  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180113a62  mov     edx, 5CEh; void *
0x180113a67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180113a6c  nop
0x180113a6d  lea     rcx, [rsp+288h+hKey]
0x180113a72  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180113a77  mov     eax, ebx
0x180113a79  jmp     loc_1801147B3
0x180113a7e  mov     [rsp+288h+cSubKeys], r15d
0x180113a86  mov     [rsp+288h+cbMaxSubKeyLen], r15d
0x180113a8b  mov     [rsp+288h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180113a90  mov     [rsp+288h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180113a95  mov     [rsp+288h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180113a9a  mov     [rsp+288h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180113a9f  mov     [rsp+288h+lpcValues], r15; lpcValues
0x180113aa4  mov     [rsp+288h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180113aa9  lea     rax, [rsp+288h+cbMaxSubKeyLen]
0x180113aae  mov     [rsp+288h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180113ab3  lea     rax, [rsp+288h+cSubKeys]
0x180113abb  mov     [rsp+288h+lpcSubKeys], rax; int
0x180113ac0  xor     r9d, r9d; lpReserved
0x180113ac3  xor     r8d, r8d; lpcchClass
0x180113ac6  xor     edx, edx; lpClass
0x180113ac8  mov     rcx, [rsp+288h+hKey]; hKey
0x180113acd  call    cs:__imp_RegQueryInfoKeyW
0x180113ad3  test    eax, eax
0x180113ad5  jz      short loc_180113B06
0x180113ad7  mov     rcx, [rsp+288h]; this
0x180113adf  mov     r9d, eax; char *
0x180113ae2  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180113ae9  mov     edx, 5D3h; void *
0x180113aee  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180113af3  mov     ebx, eax
0x180113af5  lea     rcx, [rsp+288h+hKey]
0x180113afa  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180113aff  mov     eax, ebx
0x180113b01  jmp     loc_1801147B3
0x180113b06  inc     [rsp+288h+cbMaxSubKeyLen]
0x180113b0a  cmp     [rsp+288h+cSubKeys], r15d
0x180113b12  jnz     short loc_180113B47
0x180113b14  mov     rcx, [rsp+288h]; this
0x180113b1c  mov     ebx, 80090011h
0x180113b21  mov     r9d, ebx; char *
0x180113b24  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180113b2b  mov     edx, 5D7h; void *
0x180113b30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180113b35  nop
0x180113b36  lea     rcx, [rsp+288h+hKey]
0x180113b3b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180113b40  mov     eax, ebx
0x180113b42  jmp     loc_1801147B3
0x180113b47  mov     rcx, r12; void *
0x180113b4a  call    ?IsHelloEnrolled@@YA_NQEAX@Z; IsHelloEnrolled(void * const)
0x180113b4f  test    al, al
0x180113b51  jnz     short loc_180113B86
0x180113b53  mov     rcx, [rsp+288h]; this
0x180113b5b  mov     ebx, 80090011h
0x180113b60  mov     r9d, ebx; char *
0x180113b63  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180113b6a  mov     edx, 5DCh; void *
0x180113b6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180113b74  nop
0x180113b75  lea     rcx, [rsp+288h+hKey]
0x180113b7a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180113b7f  mov     eax, ebx
0x180113b81  jmp     loc_1801147B3
0x180113b86  lea     rcx, [rsp+288h+var_1A8]
0x180113b8e  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginAuthenticatorInstance@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginAuthenticatorInstance@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,PluginAuthenticatorInstance>::map<std::wstring,PluginAuthenticatorInstance>(void)
0x180113b93  nop
0x180113b94  mov     r13d, r15d
0x180113b97  lea     rsi, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180113b9e  cmp     r13d, [rsp+288h+cSubKeys]
0x180113ba6  jnb     loc_180114790
0x180113bac  mov     edx, [rsp+288h+cbMaxSubKeyLen]
0x180113bb0  lea     rcx, [rsp+288h+lpName]
0x180113bb8  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x180113bbd  nop
0x180113bbe  mov     r9d, [rsp+288h+cbMaxSubKeyLen]; cchName
0x180113bc3  mov     r8, [rsp+288h+lpName]; lpName
0x180113bcb  mov     edx, r13d; dwIndex
0x180113bce  mov     rcx, [rsp+288h+hKey]; hKey
0x180113bd3  call    cs:__imp_RegEnumKeyW
0x180113bd9  test    eax, eax
0x180113bdb  jnz     loc_18011477B
0x180113be1  xorps   xmm0, xmm0
0x180113be4  movdqu  [rsp+288h+var_1D8], xmm0
0x180113bed  lea     rcx, [rsp+288h+var_1D8]
0x180113bf5  call    ?put@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>::put(void)
0x180113bfa  mov     [rsp+288h+lpcSubKeys], rax; int
0x180113bff  mov     r9d, 0F003Fh; samDesired
0x180113c05  xor     r8d, r8d; ulOptions
0x180113c08  mov     rdx, [rsp+288h+lpName]; lpSubKey
0x180113c10  mov     rcx, [rsp+288h+hKey]; hKey
0x180113c15  call    cs:__imp_RegOpenKeyExW
0x180113c1b  test    eax, eax
0x180113c1d  jnz     loc_18011476D
0x180113c23  xorps   xmm0, xmm0
0x180113c26  movdqu  [rsp+288h+var_200], xmm0
0x180113c2f  mov     r15, qword ptr [rsp+288h+var_1D8+8]
0x180113c37  test    r15, r15
0x180113c3a  jz      short loc_180113C41
0x180113c3c  lock inc dword ptr [r15+8]
0x180113c41  mov     rbx, qword ptr [rsp+288h+var_1D8]
0x180113c49  mov     qword ptr [rsp+288h+var_200], rbx
0x180113c51  mov     qword ptr [rsp+288h+var_200+8], r15
0x180113c59  lea     rdx, [rsp+288h+var_200]
0x180113c61  mov     rcx, r12
0x180113c64  call    IsPluginPackagePresent
0x180113c69  test    al, al
0x180113c6b  jz      loc_18011476A
0x180113c71  xor     eax, eax
0x180113c73  mov     [rsp+288h+var_228], ax
0x180113c78  mov     rdx, [rsp+288h+var_190]
0x180113c80  cmp     rdx, [rsp+288h+var_188]
0x180113c88  jz      short loc_180113C98
0x180113c8a  mov     [rdx], ax
0x180113c8d  add     [rsp+288h+var_190], 2
0x180113c96  jmp     short loc_180113CAA
0x180113c98  lea     r8, [rsp+288h+var_228]
0x180113c9d  lea     rcx, [rsp+288h+lpName]
0x180113ca5  call    ??$_Emplace_reallocate@G@?$vector@GV?$allocator@G@std@@@std@@AEAAPEAGQEAG$$QEAG@Z; std::vector<ushort>::_Emplace_reallocate<ushort>(ushort * const,ushort &&)
0x180113caa  mov     rdx, [rsp+288h+lpName]
0x180113cb2  lea     rcx, [rsp+288h+lpsz]
0x180113cba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180113cbf  nop
0x180113cc0  xorps   xmm0, xmm0
0x180113cc3  movups  xmmword ptr [rsp+288h+pclsid.Data1], xmm0
0x180113ccb  lea     rcx, [rsp+288h+lpsz]
0x180113cd3  cmp     [rsp+288h+var_D0], 7
0x180113cdc  cmova   rcx, [rsp+288h+lpsz]; lpsz
0x180113ce5  lea     rdx, [rsp+288h+pclsid]; pclsid
0x180113ced  call    cs:__imp_CLSIDFromString
0x180113cf3  mov     rcx, [rsp+288h]; this
0x180113cfb  test    eax, eax
0x180113cfd  jns     short loc_180113D34
0x180113cff  mov     r9d, eax; char *
0x180113d02  mov     r8, rsi; unsigned int
0x180113d05  mov     edx, 5F3h; void *
0x180113d0a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180113d0f  nop
0x180113d10  lea     rcx, [rsp+288h+lpsz]
0x180113d18  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180113d1d  nop
0x180113d1e  lea     rcx, [rsp+288h+var_1D8]
0x180113d26  call    ??1?$shared_ptr@UCredentialInfo@@@std@@QEAA@XZ; std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(void)
0x180113d2b  nop
0x180113d2c  xor     r15d, r15d
0x180113d2f  jmp     loc_18011477B
0x180113d34  lea     rdx, [rsp+288h+pclsid]
0x180113d3c  lea     rcx, [rsp+288h+var_180]
0x180113d44  call    ?ConvertGuidToBigEndian@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBU_GUID@@@Z; ConvertGuidToBigEndian(_GUID const &)
0x180113d49  nop
0x180113d4a  xor     edx, edx; lpSubKey
0x180113d4c  mov     [rsp+288h+pcbData], edx
0x180113d53  test    rbx, rbx
0x180113d56  jz      short loc_180113D5D
0x180113d58  mov     rcx, [rbx]
0x180113d5b  jmp     short loc_180113D60
0x180113d5d  mov     rcx, rdx; hkey
0x180113d60  lea     rax, [rsp+288h+pcbData]
0x180113d68  mov     [rsp+288h+lpcbMaxClassLen], rax; pcbData
0x180113d6d  mov     [rsp+288h+lpcbMaxSubKeyLen], rdx; pvData
0x180113d72  mov     [rsp+288h+lpcSubKeys], rdx; unsigned int
0x180113d77  mov     r9d, 2; dwFlags
0x180113d7d  lea     r8, aName; "Name"
0x180113d84  call    cs:__imp_RegGetValueW
0x180113d8a  test    eax, eax
0x180113d8c  jz      short loc_180113DFF
0x180113d8e  mov     rcx, [rsp+288h]; this
0x180113d96  mov     r9d, eax; char *
0x180113d99  mov     r8, rsi; unsigned int
0x180113d9c  mov     edx, 5FCh; void *
0x180113da1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180113da6  mov     ebx, eax
0x180113da8  lea     rcx, [rsp+288h+var_180]
0x180113db0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180113db5  nop
0x180113db6  lea     rcx, [rsp+288h+lpsz]
0x180113dbe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180113dc3  nop
0x180113dc4  lea     rcx, [rsp+288h+var_1D8]
0x180113dcc  call    ??1?$shared_ptr@UCredentialInfo@@@std@@QEAA@XZ; std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(void)
0x180113dd1  nop
0x180113dd2  lea     rcx, [rsp+288h+lpName]
0x180113dda  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180113ddf  nop
0x180113de0  lea     rcx, [rsp+288h+var_1A8]
0x180113de8  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginAuthenticatorInstance@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginAuthenticatorInstance@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,PluginAuthenticatorInstance,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PluginAuthenticatorInstance>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,PluginAuthenticatorInstance,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PluginAuthenticatorInstance>>,0>>(void)
0x180113ded  nop
0x180113dee  lea     rcx, [rsp+288h+hKey]
0x180113df3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180113df8  mov     eax, ebx
0x180113dfa  jmp     loc_1801147B3
0x180113dff  mov     edx, [rsp+288h+pcbData]
0x180113e06  shr     rdx, 1
0x180113e09  lea     rcx, [rsp+288h+pvData]
0x180113e11  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x180113e16  nop
0x180113e17  mov     rax, [rsp+288h+pvData]
0x180113e1f  test    rbx, rbx
0x180113e22  jz      short loc_180113E29
0x180113e24  mov     rcx, [rbx]
0x180113e27  jmp     short loc_180113E2B
0x180113e29  xor     ecx, ecx; hkey
0x180113e2b  lea     rdx, [rsp+288h+pcbData]
0x180113e33  mov     [rsp+288h+lpcbMaxClassLen], rdx; pcbData
0x180113e38  mov     [rsp+288h+lpcbMaxSubKeyLen], rax; pvData
0x180113e3d  mov     [rsp+288h+lpcSubKeys], 0; unsigned int
0x180113e46  mov     r9d, 2; dwFlags
0x180113e4c  lea     r8, aName; "Name"
0x180113e53  xor     edx, edx; lpSubKey
0x180113e55  call    cs:__imp_RegGetValueW
0x180113e5b  test    eax, eax
0x180113e5d  jz      short loc_180113EDE
0x180113e5f  mov     rcx, [rsp+288h]; this
0x180113e67  mov     r9d, eax; char *
0x180113e6a  mov     r8, rsi; unsigned int
0x180113e6d  mov     edx, 5FFh; void *
0x180113e72  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180113e77  mov     ebx, eax
0x180113e79  lea     rcx, [rsp+288h+pvData]
0x180113e81  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180113e86  nop
0x180113e87  lea     rcx, [rsp+288h+var_180]
0x180113e8f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180113e94  nop
0x180113e95  lea     rcx, [rsp+288h+lpsz]
0x180113e9d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180113ea2  nop
0x180113ea3  lea     rcx, [rsp+288h+var_1D8]
0x180113eab  call    ??1?$shared_ptr@UCredentialInfo@@@std@@QEAA@XZ; std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(void)
0x180113eb0  nop
0x180113eb1  lea     rcx, [rsp+288h+lpName]
0x180113eb9  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180113ebe  nop
0x180113ebf  lea     rcx, [rsp+288h+var_1A8]
0x180113ec7  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginAuthenticatorInstance@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginAuthenticatorInstance@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,PluginAuthenticatorInstance,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PluginAuthenticatorInstance>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,PluginAuthenticatorInstance,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PluginAuthenticatorInstance>>,0>>(void)
0x180113ecc  nop
0x180113ecd  lea     rcx, [rsp+288h+hKey]
0x180113ed2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180113ed7  mov     eax, ebx
0x180113ed9  jmp     loc_1801147B3
0x180113ede  xor     eax, eax
0x180113ee0  mov     [rsp+288h+var_228], ax
0x180113ee5  mov     rdx, [rsp+288h+var_1B8]
0x180113eed  cmp     rdx, [rsp+288h+var_1B0]
0x180113ef5  jz      short loc_180113F05
0x180113ef7  mov     [rdx], ax
0x180113efa  add     [rsp+288h+var_1B8], 2
0x180113f03  jmp     short loc_180113F17
0x180113f05  lea     r8, [rsp+288h+var_228]
0x180113f0a  lea     rcx, [rsp+288h+pvData]
0x180113f12  call    ??$_Emplace_reallocate@G@?$vector@GV?$allocator@G@std@@@std@@AEAAPEAGQEAG$$QEAG@Z; std::vector<ushort>::_Emplace_reallocate<ushort>(ushort * const,ushort &&)
0x180113f17  mov     rdx, [rsp+288h+pvData]
0x180113f1f  lea     rcx, [rsp+288h+var_C8]
0x180113f27  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180113f2c  nop
0x180113f2d  mov     [rsp+288h+var_218], 0
0x180113f35  xorps   xmm0, xmm0
0x180113f38  movdqu  xmmword ptr [rsp+288h+var_1F0], xmm0
0x180113f41  mov     [rsp+288h+var_1E0], 0
0x180113f4d  cmp     edi, 1
0x180113f50  jnz     loc_1801140E4
0x180113f56  test    rbx, rbx
0x180113f59  jz      short loc_180113F60
0x180113f5b  mov     rcx, [rbx]
0x180113f5e  jmp     short loc_180113F62
0x180113f60  xor     ecx, ecx; hkey
0x180113f62  lea     rax, [rsp+288h+var_218]
0x180113f67  mov     [rsp+288h+lpcbMaxClassLen], rax; pcbData
0x180113f6c  mov     [rsp+288h+lpcbMaxSubKeyLen], 0; pvData
0x180113f75  mov     [rsp+288h+lpcSubKeys], 0; pdwType
0x180113f7e  mov     r9d, 8; dwFlags
0x180113f84  lea     r8, aDecodedutf8lig; "DecodedUtf8LightLogo"
0x180113f8b  xor     edx, edx; lpSubKey
  ... truncated ...
```
