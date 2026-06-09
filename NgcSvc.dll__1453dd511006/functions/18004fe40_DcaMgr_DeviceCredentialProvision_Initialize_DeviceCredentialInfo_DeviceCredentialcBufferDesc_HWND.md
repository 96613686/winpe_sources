# DcaMgr::DeviceCredentialProvision::Initialize(_DeviceCredentialInfo *,_DeviceCredentialcBufferDesc *,HWND__ *)

- ea: `0x18004fe40`
- end: `0x180050b28`
- name: `?Initialize@DeviceCredentialProvision@DcaMgr@@MEAAJPEAU_DeviceCredentialInfo@@PEAU_DeviceCredentialcBufferDesc@@PEAUHWND__@@@Z`
- size: `3304`
- prototype: `int(DcaMgr::DeviceCredentialProvision *__hidden this, struct _DeviceCredentialInfo *, struct _DeviceCredentialcBufferDesc *, HWND)`
- caller_count: `0`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000782c`
- `0x18000926c`
- `0x1800281e0`
- `0x180028200`
- `0x18002832c`
- `0x1800323d0`
- `0x180032c20`
- `0x1800481b8`
- `0x180048304`
- `0x180049a54`
- `0x18004f218`
- `0x18004fe40`
- `0x180050b30`
- `0x180050d10`
- `0x1800527ac`
- `0x1800535f4`
- `0x180054074`
- `0x18005aef8`
- `0x180069c28`
- `0x180097c6c`
- `0x180097cb4`
- `0x1800a05b4`
- `0x1800a22c8`
- `0x1800a5914`
- `0x1800a608c`
- `0x1800a6408`
- `0x1800a6d30`
- `0x1800a7624`
- `0x1800a7b74`
- `0x1800a7bd4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005008d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005010a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180050183`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180050588`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005008d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005010a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180050183`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180050588`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005062d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005062d`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18005098c`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180050996`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18005098c`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180050996`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050485`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800504d4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050687`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050784`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005089c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800508cb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050901`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050939`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050485`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800504d4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050687`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050784`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005089c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800508cb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050901`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050939`
- `RPCRT4!RpcImpersonateClient` at `0x1800502c7`
- `RPCRT4!RpcImpersonateClient` at `0x1800502c7`

## string_xrefs

- `0x18004ffaa`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x18005001f`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800500a9`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x180050126`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x18005019f`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x180050214`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x18005024e`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800502d8`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x18005036e`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x180050494`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x180050530`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800505a4`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x180050648`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800506d7`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x18005071d`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x180050a54`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x180050b02`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800507d0`: `UserSid`
- `0x1800508c0`: `ProtocolVersion`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall DcaMgr::DeviceCredentialProvision::Initialize(
        DcaMgr::DeviceCredentialProvision *this,
        struct _DeviceCredentialInfo *a2,
        struct _DeviceCredentialcBufferDesc *a3,
        HWND a4)
{
  __int64 v6; // r8
  __int64 v7; // r15
  const unsigned __int8 *v8; // r12
  int v9; // r10d
  int v10; // r11d
  unsigned int v11; // r9d
  bool v12; // di
  __int64 v13; // rdx
  int UserSidAndPackageInfoFromToken; // ebx
  __int64 v15; // rcx
  __int64 v16; // rcx
  unsigned int v17; // ebx
  unsigned int v18; // ebx
  unsigned int v19; // ebx
  void *v20; // rdx
  bool *v21; // r9
  int v22; // eax
  int v23; // ecx
  int RsaKeyPair; // esi
  unsigned int v25; // eax
  int v26; // ecx
  __int64 v27; // rdx
  int v28; // ecx
  unsigned int v29; // eax
  __int64 v30; // rdx
  unsigned int v31; // ebx
  __int64 v32; // rdx
  unsigned int ValueW; // eax
  TpmPolicySession *v34; // rcx
  __int64 v35; // rdx
  int v36; // eax
  int v37; // eax
  unsigned __int64 v38; // r9
  int v39; // eax
  int v40; // eax
  int v41; // eax
  const WCHAR *v42; // r9
  int v43; // eax
  const char *v44; // r9
  int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsd; // [rsp+20h] [rbp-E0h]
  int dwOptionse; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsf; // [rsp+20h] [rbp-E0h]
  int dwOptionsg; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsh; // [rsp+20h] [rbp-E0h]
  const char *samDesired; // [rsp+28h] [rbp-D8h]
  HKEY hkey; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpSubKey; // [rsp+58h] [rbp-A8h] BYREF
  LPCVOID v58; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v59; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  BYTE *v61; // [rsp+78h] [rbp-88h] BYREF
  HKEY v62; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int8 *v63; // [rsp+88h] [rbp-78h] BYREF
  BYTE *lpData; // [rsp+90h] [rbp-70h] BYREF
  char v65; // [rsp+98h] [rbp-68h] BYREF
  BYTE *v66; // [rsp+A0h] [rbp-60h] BYREF
  LPCVOID v67; // [rsp+A8h] [rbp-58h] BYREF
  BOOL pvData; // [rsp+B0h] [rbp-50h] BYREF
  char *p_TokenHandle; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v70; // [rsp+C0h] [rbp-40h] BYREF
  char v71; // [rsp+C8h] [rbp-38h]
  DWORD cbData; // [rsp+D0h] [rbp-30h] BYREF
  DWORD v73; // [rsp+D4h] [rbp-2Ch] BYREF
  void *p_hKey; // [rsp+D8h] [rbp-28h] BYREF
  HKEY phkResult; // [rsp+E0h] [rbp-20h] BYREF
  char v76; // [rsp+E8h] [rbp-18h]
  void *p_lpData; // [rsp+F0h] [rbp-10h] BYREF
  HKEY v78; // [rsp+F8h] [rbp-8h] BYREF
  char v79; // [rsp+100h] [rbp+0h]
  BYTE Data[8]; // [rsp+108h] [rbp+8h] BYREF
  HANDLE TokenHandle; // [rsp+110h] [rbp+10h] BYREF
  DWORD pcbData[18]; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]
  __int64 v84; // [rsp+180h] [rbp+80h] BYREF

  *(_DWORD *)Data = 0;
  if ( *((_DWORD *)a3 + 1) != 2 || (v6 = *((_QWORD *)a3 + 1)) == 0 )
  {
    v13 = 150;
    goto LABEL_129;
  }
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 1;
  while ( v11 < 2 )
  {
    if ( *(_DWORD *)(v6 + 16LL * v11) == 1 )
    {
      v8 = *(const unsigned __int8 **)(v6 + 16LL * v11 + 8);
      v10 = *(_DWORD *)(v6 + 16LL * v11 + 4);
    }
    else
    {
      if ( *(_DWORD *)(v6 + 16LL * v11) != 2 )
      {
        v13 = 170;
        goto LABEL_129;
      }
      v7 = *(_QWORD *)(v6 + 16LL * v11 + 8);
      v9 = *(_DWORD *)(v6 + 16LL * v11 + 4);
    }
    ++v11;
  }
  if ( !v7 || v9 != 32 || !v8 || v10 != 32 )
  {
    v13 = 176;
LABEL_129:
    UserSidAndPackageInfoFromToken = -2147024809;
    goto LABEL_130;
  }
  UserSidAndPackageInfoFromToken = ValidateInputString(*((_QWORD *)a2 + 1), 40);
  if ( UserSidAndPackageInfoFromToken < 0 )
  {
    v13 = 180;
LABEL_130:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
      dwOptions);
    return (unsigned int)UserSidAndPackageInfoFromToken;
  }
  UserSidAndPackageInfoFromToken = ValidateInputString(*((_QWORD *)a2 + 2), 64);
  if ( UserSidAndPackageInfoFromToken < 0 )
  {
    v13 = 184;
    goto LABEL_130;
  }
  v15 = *((_QWORD *)a2 + 3);
  if ( v15 )
  {
    UserSidAndPackageInfoFromToken = ValidateInputString(v15, 32);
    if ( UserSidAndPackageInfoFromToken < 0 )
    {
      v13 = 190;
      goto LABEL_130;
    }
  }
  UserSidAndPackageInfoFromToken = DcaMgr::DeviceCredential::Deprovision(*((LPCWSTR *)a2 + 1));
  v16 = UserSidAndPackageInfoFromToken + 0x80000000;
  if ( (int)v16 >= 0 && UserSidAndPackageInfoFromToken != -2147024894 )
  {
    v13 = 198;
    goto LABEL_130;
  }
  TokenHandle = 0;
  p_TokenHandle = (char *)&TokenHandle;
  v70 = 0;
  v71 = 1;
  UserSidAndPackageInfoFromToken = OpenCallerImpersonationToken(v16, &v70);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_TokenHandle);
  if ( UserSidAndPackageInfoFromToken >= 0 )
  {
    lpSubKey = 0;
    v58 = 0;
    p_hKey = &v58;
    phkResult = 0;
    v76 = 1;
    p_TokenHandle = (char *)&lpSubKey;
    v70 = 0;
    v71 = 1;
    UserSidAndPackageInfoFromToken = GetUserSidAndPackageInfoFromToken(TokenHandle);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_TokenHandle);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hKey);
    if ( UserSidAndPackageInfoFromToken < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD3,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
        (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
        dwOptions);
LABEL_125:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v58);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpSubKey);
      goto LABEL_126;
    }
    DevCredSvcTraceLoggingProvider::AppInfo((const unsigned __int16 *)v58, lpSubKey);
    hKey = 0;
    p_hKey = &hKey;
    phkResult = 0;
    v76 = 1;
    v17 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor\\Users",
            0,
            0,
            0,
            0xF003Fu,
            0,
            &phkResult,
            0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    if ( v17 )
    {
      UserSidAndPackageInfoFromToken = wil::details::in1diag3::Return_Win32(
                                         retaddr,
                                         (void *)0xE2,
                                         (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
                                         (const char *)v17,
                                         dwOptionsa);
LABEL_124:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_125;
    }
    v59 = 0;
    p_hKey = &v59;
    phkResult = 0;
    v76 = 1;
    v18 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor\\Devices",
            0,
            0,
            0,
            0xF003Fu,
            0,
            &phkResult,
            0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    if ( v18 )
    {
      UserSidAndPackageInfoFromToken = wil::details::in1diag3::Return_Win32(
                                         retaddr,
                                         (void *)0xEF,
                                         (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
                                         (const char *)v18,
                                         dwOptionsb);
LABEL_123:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v59);
      goto LABEL_124;
    }
    hkey = 0;
    p_hKey = &hkey;
    phkResult = 0;
    v76 = 1;
    v19 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    if ( v19 )
    {
      UserSidAndPackageInfoFromToken = wil::details::in1diag3::Return_Win32(
                                         retaddr,
                                         (void *)0xFC,
                                         (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
                                         (const char *)v19,
                                         dwOptionsc);
LABEL_122:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      goto LABEL_123;
    }
    v61 = 0;
    v73 = 0;
    p_hKey = &v61;
    phkResult = 0;
    v76 = 1;
    UserSidAndPackageInfoFromToken = ReadRegBinaryValue(hkey, &v73);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_hKey);
    if ( (int)(UserSidAndPackageInfoFromToken + 0x80000000) >= 0 && UserSidAndPackageInfoFromToken != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x109,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
        (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
        dwOptionsd);
LABEL_121:
      wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v61);
      goto LABEL_122;
    }
    LOBYTE(v84) = 0;
    v22 = DcaUtil::CheckTokenMembershipSubAuthority0((DcaUtil *)TokenHandle, v20, (unsigned int)&v84, v21);
    RsaKeyPair = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x110,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
        (const char *)(unsigned int)v22,
        dwOptionsd);
LABEL_40:
      wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v61);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v59);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v58);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpSubKey);
      UserSidAndPackageInfoFromToken = RsaKeyPair;
      goto LABEL_126;
    }
    v65 = 0;
    p_TokenHandle = &v65;
    LOWORD(v70) = 256;
    if ( !(_BYTE)v84 )
    {
      v25 = RpcImpersonateClient(0);
      if ( v25 )
      {
        UserSidAndPackageInfoFromToken = wil::details::in1diag3::Return_Win32(
                                           retaddr,
                                           (void *)0x120,
                                           (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecr"
                                                         "edentialclass.cpp",
                                           (const char *)v25,
                                           dwOptionsd);
LABEL_120:
        wil::details::ScopeExitFnGuard__lambda_7f3d40de85dbd45b8cf192816ff9c04c___::operator()(&p_TokenHandle);
        goto LABEL_121;
      }
      v65 = 1;
    }
    v63 = 0;
    LODWORD(v84) = 0;
    lpData = 0;
    cbData = 0;
    v78 = 0;
    v79 = 1;
    if ( UserSidAndPackageInfoFromToken )
    {
      p_lpData = &lpData;
      p_hKey = &v63;
      phkResult = 0;
      v76 = 1;
      RsaKeyPair = CreateRsaKeyPair(v23, (int)&phkResult, (int)&v84, (int)&v78, (PUCHAR)&cbData);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_hKey);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_lpData);
      if ( RsaKeyPair < 0 )
      {
        v27 = 305;
LABEL_48:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v27,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
          (const char *)(unsigned int)RsaKeyPair,
          dwOptionse);
LABEL_49:
        wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&lpData);
        wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v63);
        wil::details::ScopeExitFnGuard__lambda_7f3d40de85dbd45b8cf192816ff9c04c___::operator()(&p_TokenHandle);
        goto LABEL_40;
      }
      p_lpData = &v61;
      v78 = 0;
      v79 = 1;
      LOBYTE(v26) = 1;
      RsaKeyPair = DpapiProtectUnprotect(v26, (_DWORD)v63, v84, (unsigned int)&v78, (__int64)&v73);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_lpData);
      if ( RsaKeyPair < 0 )
      {
        v27 = 313;
        goto LABEL_48;
      }
      if ( !v63 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( !lpData )
        goto LABEL_59;
    }
    else
    {
      p_lpData = &v63;
      RsaKeyPair = DpapiProtectUnprotect(0, (_DWORD)v61, v73, (unsigned int)&v78, (__int64)&v84);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_lpData);
      if ( RsaKeyPair < 0 )
      {
        v27 = 325;
        goto LABEL_48;
      }
      if ( !v63 )
LABEL_59:
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    wil::details::ScopeExitFnGuard__lambda_7f3d40de85dbd45b8cf192816ff9c04c___::operator()(&p_TokenHandle);
    if ( UserSidAndPackageInfoFromToken )
    {
      v29 = RegSetValueExW(hkey, L"PublicKey", 0, 3u, lpData, cbData);
      if ( v29 )
      {
        v30 = 341;
LABEL_63:
        UserSidAndPackageInfoFromToken = wil::details::in1diag3::Return_Win32(
                                           retaddr,
                                           (void *)v30,
                                           (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecr"
                                                         "edentialclass.cpp",
                                           (const char *)v29,
                                           dwOptionsf);
LABEL_119:
        wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&lpData);
        wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v63);
        goto LABEL_120;
      }
      v29 = RegSetValueExW(hkey, L"PrivateKey", 0, 3u, v61, v73);
      if ( v29 )
      {
        v30 = 349;
        goto LABEL_63;
      }
    }
    v66 = 0;
    cbData = 0;
    p_lpData = &v66;
    v78 = 0;
    v79 = 1;
    LOBYTE(v28) = 1;
    UserSidAndPackageInfoFromToken = DpapiProtectUnprotect(v28, v7, 32, (unsigned int)&v78, (__int64)&cbData);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_lpData);
    if ( UserSidAndPackageInfoFromToken < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x168,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
        (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
        dwOptionsg);
LABEL_118:
      wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v66);
      goto LABEL_119;
    }
    v62 = 0;
    p_lpData = &v62;
    v78 = 0;
    v79 = 1;
    v31 = RegCreateKeyExW(v59, *((LPCWSTR *)a2 + 1), 0, 0, 0, 0xF003Fu, 0, &v78, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpData);
    if ( v31 )
    {
      UserSidAndPackageInfoFromToken = wil::details::in1diag3::Return_Win32(
                                         retaddr,
                                         (void *)0x176,
                                         (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
                                         (const char *)v31,
                                         dwOptionsh);
LABEL_117:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v62);
      goto LABEL_118;
    }
    v59 = 0;
    v67 = 0;
    p_lpData = &v67;
    v78 = 0;
    v79 = 1;
    UserSidAndPackageInfoFromToken = DcaMgr::DeviceCredentialTpmHmac::GenerateHmacKeyName((unsigned __int16 **)&v78);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_lpData);
    if ( UserSidAndPackageInfoFromToken < 0 )
    {
      v32 = 380;
LABEL_114:
      v38 = (unsigned int)UserSidAndPackageInfoFromToken;
      goto LABEL_115;
    }
    pvData = 0;
    pcbData[0] = 4;
    ValueW = RegGetValueW(hkey, 0, L"TpmHmacEnabled", 0x10u, 0, &pvData, pcbData);
    if ( ValueW )
    {
      if ( ValueW != 2 )
      {
        v35 = 395;
        goto LABEL_75;
      }
      if ( TpmPolicySession::IsSupportedTpm20Present(v34) )
      {
LABEL_80:
        UserSidAndPackageInfoFromToken = DcaMgr::DeviceCredentialTpmHmac::ProvisionHmacKey(
                                           (const unsigned __int16 *)v67,
                                           v8,
                                           0x20u,
                                           v12);
        if ( UserSidAndPackageInfoFromToken >= 0 )
        {
          v36 = WriteRegStringValue(v62, 0, (char *)L"TpmHmacKeyName", v67);
          RsaKeyPair = v36;
          if ( v36 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1C0,
              (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
              (const char *)(unsigned int)v36,
              dwOptionsh);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v67);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v62);
            wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v66);
            goto LABEL_49;
          }
        }
        else
        {
          if ( pvData )
            wil::details::in1diag3::Log_HrMsg(
              retaddr,
              (void *)0x1B1,
              (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
              (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
              (int)"Provision TPM HMAC key failed",
              samDesired);
          if ( UserSidAndPackageInfoFromToken != -2147024846 )
          {
            v32 = 438;
            goto LABEL_114;
          }
        }
        if ( v12 || UserSidAndPackageInfoFromToken < 0 )
        {
          pvData = UserSidAndPackageInfoFromToken >= 0;
          ValueW = RegSetValueExW(hkey, L"TpmHmacEnabled", 0, 4u, (const BYTE *)&pvData, 4u);
          if ( ValueW )
          {
            v35 = 461;
            goto LABEL_75;
          }
        }
LABEL_91:
        v37 = DcaMgr::DeviceCredentialSoftwareHmac::ProvisionHmacKey(v62, v8, 0x20u, v63, v84);
        UserSidAndPackageInfoFromToken = v37;
        if ( v37 >= 0 )
        {
          v39 = WriteRegStringValue(v62, 0, (char *)L"UserSid", lpSubKey);
          UserSidAndPackageInfoFromToken = v39;
          if ( v39 >= 0 )
          {
            v40 = WriteRegStringValue(v62, 0, (char *)L"AppId", v58);
            UserSidAndPackageInfoFromToken = v40;
            if ( v40 >= 0 )
            {
              v41 = WriteRegStringValue(v62, 0, (char *)L"FriendlyName", *((LPCVOID *)a2 + 2));
              UserSidAndPackageInfoFromToken = v41;
              if ( v41 >= 0 )
              {
                v42 = &sourceString;
                if ( *((_QWORD *)a2 + 3) )
                  v42 = (const WCHAR *)*((_QWORD *)a2 + 3);
                v43 = WriteRegStringValue(v62, 0, (char *)L"ModelNumber", v42);
                UserSidAndPackageInfoFromToken = v43;
                if ( v43 >= 0 )
                {
                  ValueW = RegSetValueExW(v62, L"DeviceCapability", 0, 4u, (const BYTE *)a2 + 44, 4u);
                  if ( ValueW )
                  {
                    v35 = 507;
                  }
                  else
                  {
                    ValueW = RegSetValueExW(v62, L"ProtocolVersion", 0, 4u, (const BYTE *)a2, 4u);
                    if ( ValueW )
                    {
                      v35 = 515;
                    }
                    else
                    {
                      *(_DWORD *)Data = 0;
                      ValueW = RegSetValueExW(v62, L"State", 0, 4u, Data, 4u);
                      if ( ValueW )
                      {
                        v35 = 524;
                      }
                      else
                      {
                        ValueW = RegSetValueExW(v62, L"AuthKey", 0, 3u, v66, cbData);
                        if ( !ValueW )
                        {
                          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                            &v84,
                            *((char **)a2 + 1),
                            0xFFFFFFFFFFFFFFFFuLL,
                            v44);
                          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                            (char *)this + 8,
                            &v84);
                          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v84);
                          if ( *((_QWORD *)this + 1) )
                          {
                            RegFlushKey(hkey);
                            RegFlushKey(v62);
                            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                              (char *)this + 16,
                              &v58);
                            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                              (char *)this + 24,
                              &lpSubKey);
                            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v67);
                            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v62);
                            wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v66);
                            wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&lpData);
                            wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v63);
                            wil::details::ScopeExitFnGuard__lambda_7f3d40de85dbd45b8cf192816ff9c04c___::operator()(&p_TokenHandle);
                            wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v61);
                            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
                            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v59);
                            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v58);
                            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpSubKey);
                            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
                            return 0;
                          }
                          UserSidAndPackageInfoFromToken = -2147024882;
                          v32 = 535;
                          goto LABEL_114;
                        }
                        v35 = 532;
                      }
                    }
                  }
LABEL_75:
                  UserSidAndPackageInfoFromToken = wil::details::in1diag3::Return_Win32(
                                                     retaddr,
                                                     (void *)v35,
                                                     (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib"
                                                                   "\\devicecredentialclass.cpp",
                                                     (const char *)ValueW,
                                                     dwOptionsh);
LABEL_116:
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v67);
                  goto LABEL_117;
                }
                v38 = (unsigned int)v43;
                v32 = 499;
              }
              else
              {
                v38 = (unsigned int)v41;
                v32 = 488;
              }
            }
            else
            {
              v38 = (unsigned int)v40;
              v32 = 482;
            }
          }
          else
          {
            v38 = (unsigned int)v39;
            v32 = 476;
          }
        }
        else
        {
          v38 = (unsigned int)v37;
          v32 = 470;
        }
LABEL_115:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v32,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
          (const char *)v38,
          dwOptionsh);
        goto LABEL_116;
      }
      pvData = 0;
      ValueW = RegSetValueExW(hkey, L"TpmHmacEnabled", 0, 4u, (const BYTE *)&pvData, 4u);
      if ( ValueW )
      {
        v35 = 412;
        goto LABEL_75;
      }
    }
    v12 = 0;
    if ( !pvData )
      goto LABEL_91;
    goto LABEL_80;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xCC,
    (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
    (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
    dwOptions);
LABEL_126:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return (unsigned int)UserSidAndPackageInfoFromToken;
}

```

## disassembly

```asm
0x18004fe40  push    rbp
0x18004fe42  push    rbx
0x18004fe43  push    rsi
0x18004fe44  push    rdi
0x18004fe45  push    r12
0x18004fe47  push    r13
0x18004fe49  push    r14
0x18004fe4b  push    r15
0x18004fe4d  lea     rbp, [rsp-28h]
0x18004fe52  sub     rsp, 128h
0x18004fe59  mov     r14, rdx
0x18004fe5c  mov     r13, rcx
0x18004fe5f  xor     esi, esi
0x18004fe61  mov     dword ptr [rbp+60h+Data], esi
0x18004fe64  cmp     dword ptr [r8+4], 2
0x18004fe69  jnz     loc_180050AF5
0x18004fe6f  mov     r8, [r8+8]
0x18004fe73  test    r8, r8
0x18004fe76  jz      loc_180050AF5
0x18004fe7c  mov     r15d, esi
0x18004fe7f  mov     r12d, esi
0x18004fe82  mov     r10d, esi
0x18004fe85  mov     r11d, esi
0x18004fe88  mov     r9d, esi
0x18004fe8b  lea     edi, [rsi+1]
0x18004fe8e  cmp     r9d, 2
0x18004fe92  jnb     short loc_18004FECB
0x18004fe94  mov     ecx, r9d
0x18004fe97  add     rcx, rcx
0x18004fe9a  mov     edx, [r8+rcx*8]
0x18004fe9e  sub     edx, edi
0x18004fea0  jz      short loc_18004FEB2
0x18004fea2  cmp     edx, edi
0x18004fea4  jnz     short loc_18004FEC1
0x18004fea6  mov     r15, [r8+rcx*8+8]
0x18004feab  mov     r10d, [r8+rcx*8+4]
0x18004feb0  jmp     short loc_18004FEBC
0x18004feb2  mov     r12, [r8+rcx*8+8]
0x18004feb7  mov     r11d, [r8+rcx*8+4]
0x18004febc  add     r9d, edi
0x18004febf  jmp     short loc_18004FE8E
0x18004fec1  mov     edx, 0AAh
0x18004fec6  jmp     loc_180050AFA
0x18004fecb  test    r15, r15
0x18004fece  jz      loc_180050AEE
0x18004fed4  cmp     r10d, 20h ; ' '
0x18004fed8  jnz     loc_180050AEE
0x18004fede  test    r12, r12
0x18004fee1  jz      loc_180050AEE
0x18004fee7  cmp     r11d, r10d
0x18004feea  jnz     loc_180050AEE
0x18004fef0  lea     edx, [r10+8]
0x18004fef4  mov     rcx, [r14+8]
0x18004fef8  call    ValidateInputString
0x18004fefd  mov     ebx, eax
0x18004feff  test    eax, eax
0x18004ff01  jns     short loc_18004FF0D
0x18004ff03  mov     edx, 0B4h
0x18004ff08  jmp     loc_180050AFF
0x18004ff0d  mov     edx, 40h ; '@'
0x18004ff12  mov     rcx, [r14+10h]
0x18004ff16  call    ValidateInputString
0x18004ff1b  mov     ebx, eax
0x18004ff1d  test    eax, eax
0x18004ff1f  jns     short loc_18004FF2B
0x18004ff21  mov     edx, 0B8h
0x18004ff26  jmp     loc_180050AFF
0x18004ff2b  mov     rcx, [r14+18h]
0x18004ff2f  test    rcx, rcx
0x18004ff32  jz      short loc_18004FF4E
0x18004ff34  mov     edx, 20h ; ' '
0x18004ff39  call    ValidateInputString
0x18004ff3e  mov     ebx, eax
0x18004ff40  test    eax, eax
0x18004ff42  jns     short loc_18004FF4E
0x18004ff44  mov     edx, 0BEh
0x18004ff49  jmp     loc_180050AFF
0x18004ff4e  mov     rcx, [r14+8]; lpSubKey
0x18004ff52  call    ?Deprovision@DeviceCredential@DcaMgr@@SAJPEBG@Z; DcaMgr::DeviceCredential::Deprovision(ushort const *)
0x18004ff57  mov     ebx, eax
0x18004ff59  mov     eax, 80000000h
0x18004ff5e  lea     ecx, [rbx+rax]
0x18004ff61  test    eax, ecx
0x18004ff63  jnz     short loc_18004FF77
0x18004ff65  cmp     ebx, 80070002h
0x18004ff6b  jz      short loc_18004FF77
0x18004ff6d  mov     edx, 0C6h
0x18004ff72  jmp     loc_180050AFF
0x18004ff77  mov     [rbp+60h+TokenHandle], rsi
0x18004ff7b  lea     rax, [rbp+60h+TokenHandle]
0x18004ff7f  mov     [rbp+60h+var_A8], rax
0x18004ff83  mov     [rbp+60h+var_A0], rsi
0x18004ff87  mov     [rbp+60h+var_98], dil
0x18004ff8b  lea     rdx, [rbp+60h+var_A0]
0x18004ff8f  call    OpenCallerImpersonationToken
0x18004ff94  mov     ebx, eax
0x18004ff96  lea     rcx, [rbp+60h+var_A8]
0x18004ff9a  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18004ff9f  test    ebx, ebx
0x18004ffa1  jns     short loc_18004FFC0
0x18004ffa3  mov     rcx, [rbp+68h]; this
0x18004ffa7  mov     r9d, ebx; char *
0x18004ffaa  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x18004ffb1  mov     edx, 0CCh; void *
0x18004ffb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ffbb  jmp     loc_180050AE3
0x18004ffc0  mov     [rsp+160h+lpSubKey], rsi
0x18004ffc5  mov     [rsp+160h+var_100], rsi
0x18004ffca  lea     rax, [rsp+160h+var_100]
0x18004ffcf  mov     [rbp+60h+var_88], rax
0x18004ffd3  mov     [rbp+60h+var_80], rsi
0x18004ffd7  mov     [rbp+60h+var_78], dil
0x18004ffdb  lea     rax, [rsp+160h+lpSubKey]
0x18004ffe0  mov     [rbp+60h+var_A8], rax
0x18004ffe4  mov     [rbp+60h+var_A0], rsi
0x18004ffe8  mov     [rbp+60h+var_98], dil
0x18004ffec  xor     r9d, r9d
0x18004ffef  lea     r8, [rbp+60h+var_80]
0x18004fff3  lea     rdx, [rbp+60h+var_A0]
0x18004fff7  mov     rcx, [rbp+60h+TokenHandle]; TokenHandle
0x18004fffb  call    GetUserSidAndPackageInfoFromToken
0x180050000  mov     ebx, eax
0x180050002  lea     rcx, [rbp+60h+var_A8]
0x180050006  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18005000b  lea     rcx, [rbp+60h+var_88]
0x18005000f  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180050014  test    ebx, ebx
0x180050016  jns     short loc_180050035
0x180050018  mov     rcx, [rbp+68h]; this
0x18005001c  mov     r9d, ebx; char *
0x18005001f  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x180050026  mov     edx, 0D3h; void *
0x18005002b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050030  jmp     loc_180050ACD
0x180050035  mov     rdx, [rsp+160h+lpSubKey]; unsigned __int16 *
0x18005003a  mov     rcx, [rsp+160h+var_100]; unsigned __int16 *
0x18005003f  call    ?AppInfo@DevCredSvcTraceLoggingProvider@@SAXPEBG0@Z; DevCredSvcTraceLoggingProvider::AppInfo(ushort const *,ushort const *)
0x180050044  mov     [rsp+160h+hKey], rsi
0x180050049  lea     rax, [rsp+160h+hKey]
0x18005004e  mov     [rbp+60h+var_88], rax
0x180050052  mov     [rbp+60h+var_80], rsi
0x180050056  mov     [rbp+60h+var_78], dil
0x18005005a  mov     [rsp+160h+lpdwDisposition], rsi; lpdwDisposition
0x18005005f  lea     rax, [rbp+60h+var_80]
0x180050063  mov     [rsp+160h+phkResult], rax; phkResult
0x180050068  mov     [rsp+160h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18005006d  mov     [rsp+160h+samDesired], 0F003Fh; samDesired
0x180050075  mov     [rsp+160h+dwOptions], esi; unsigned int
0x180050079  xor     r9d, r9d; lpClass
0x18005007c  xor     r8d, r8d; Reserved
0x18005007f  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180050086  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005008d  call    cs:__imp_RegCreateKeyExW
0x180050093  mov     ebx, eax
0x180050095  lea     rcx, [rbp+60h+var_88]
0x180050099  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18005009e  test    ebx, ebx
0x1800500a0  jz      short loc_1800500C1
0x1800500a2  mov     rcx, [rbp+68h]; this
0x1800500a6  mov     r9d, ebx; char *
0x1800500a9  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800500b0  mov     edx, 0E2h; void *
0x1800500b5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800500ba  mov     ebx, eax
0x1800500bc  jmp     loc_180050AC2
0x1800500c1  mov     [rsp+160h+var_F8], rsi
0x1800500c6  lea     rax, [rsp+160h+var_F8]
0x1800500cb  mov     [rbp+60h+var_88], rax
0x1800500cf  mov     [rbp+60h+var_80], rsi
0x1800500d3  mov     [rbp+60h+var_78], dil
0x1800500d7  mov     [rsp+160h+lpdwDisposition], rsi; lpdwDisposition
0x1800500dc  lea     rax, [rbp+60h+var_80]
0x1800500e0  mov     [rsp+160h+phkResult], rax; phkResult
0x1800500e5  mov     [rsp+160h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800500ea  mov     [rsp+160h+samDesired], 0F003Fh; samDesired
0x1800500f2  mov     [rsp+160h+dwOptions], esi; unsigned int
0x1800500f6  xor     r9d, r9d; lpClass
0x1800500f9  xor     r8d, r8d; Reserved
0x1800500fc  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180050103  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005010a  call    cs:__imp_RegCreateKeyExW
0x180050110  mov     ebx, eax
0x180050112  lea     rcx, [rbp+60h+var_88]
0x180050116  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18005011b  test    ebx, ebx
0x18005011d  jz      short loc_18005013E
0x18005011f  mov     rcx, [rbp+68h]; this
0x180050123  mov     r9d, ebx; char *
0x180050126  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x18005012d  mov     edx, 0EFh; void *
0x180050132  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180050137  mov     ebx, eax
0x180050139  jmp     loc_180050AB7
0x18005013e  mov     [rsp+160h+hkey], rsi
0x180050143  lea     rax, [rsp+160h+hkey]
0x180050148  mov     [rbp+60h+var_88], rax
0x18005014c  mov     [rbp+60h+var_80], rsi
0x180050150  mov     [rbp+60h+var_78], dil
0x180050154  mov     [rsp+160h+lpdwDisposition], rsi; lpdwDisposition
0x180050159  lea     rax, [rbp+60h+var_80]
0x18005015d  mov     [rsp+160h+phkResult], rax; phkResult
0x180050162  mov     [rsp+160h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180050167  mov     [rsp+160h+samDesired], 0F003Fh; samDesired
0x18005016f  mov     [rsp+160h+dwOptions], esi; unsigned int
0x180050173  xor     r9d, r9d; lpClass
0x180050176  xor     r8d, r8d; Reserved
0x180050179  mov     rdx, [rsp+160h+lpSubKey]; lpSubKey
0x18005017e  mov     rcx, [rsp+160h+hKey]; hKey
0x180050183  call    cs:__imp_RegCreateKeyExW
0x180050189  mov     ebx, eax
0x18005018b  lea     rcx, [rbp+60h+var_88]
0x18005018f  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180050194  test    ebx, ebx
0x180050196  jz      short loc_1800501B7
0x180050198  mov     rcx, [rbp+68h]; this
0x18005019c  mov     r9d, ebx; char *
0x18005019f  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800501a6  mov     edx, 0FCh; void *
0x1800501ab  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800501b0  mov     ebx, eax
0x1800501b2  jmp     loc_180050AAC
0x1800501b7  mov     [rsp+160h+var_E8], rsi
0x1800501bc  mov     [rbp+60h+var_8C], esi
0x1800501bf  lea     rax, [rsp+160h+var_E8]
0x1800501c4  mov     [rbp+60h+var_88], rax
0x1800501c8  mov     [rbp+60h+var_80], rsi
0x1800501cc  mov     [rbp+60h+var_78], dil
0x1800501d0  lea     rax, [rbp+60h+var_8C]
0x1800501d4  mov     qword ptr [rsp+160h+dwOptions], rax; unsigned int
0x1800501d9  lea     r9, [rbp+60h+var_80]
0x1800501dd  lea     r8, aPrivatekey; "PrivateKey"
0x1800501e4  mov     rcx, [rsp+160h+hkey]; hkey
0x1800501e9  call    ReadRegBinaryValue
0x1800501ee  mov     ebx, eax
0x1800501f0  lea     rcx, [rbp+60h+var_88]
0x1800501f4  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
0x1800501f9  mov     eax, 80000000h
0x1800501fe  lea     ecx, [rbx+rax]
0x180050201  test    eax, ecx
0x180050203  jnz     short loc_18005022A
0x180050205  cmp     ebx, 80070002h
0x18005020b  jz      short loc_18005022A
0x18005020d  mov     rcx, [rbp+68h]; this
0x180050211  mov     r9d, ebx; char *
0x180050214  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x18005021b  mov     edx, 109h; void *
0x180050220  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050225  jmp     loc_180050AA1
0x18005022a  mov     byte ptr [rbp+60h+arg_10], sil
0x180050231  lea     r8, [rbp+60h+arg_10]; unsigned int
0x180050238  mov     rcx, [rbp+60h+TokenHandle]; this
0x18005023c  call    ?CheckTokenMembershipSubAuthority0@DcaUtil@@YAJPEAXKPEA_N@Z; DcaUtil::CheckTokenMembershipSubAuthority0(void *,ulong,bool *)
0x180050241  mov     esi, eax
0x180050243  test    eax, eax
0x180050245  jns     short loc_1800502A8
0x180050247  mov     rcx, [rbp+68h]; this
0x18005024b  mov     r9d, eax; char *
0x18005024e  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x180050255  mov     edx, 110h; void *
0x18005025a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005025f  nop
0x180050260  lea     rcx, [rsp+160h+var_E8]
0x180050265  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x18005026a  nop
0x18005026b  lea     rcx, [rsp+160h+hkey]
0x180050270  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180050275  nop
0x180050276  lea     rcx, [rsp+160h+var_F8]
0x18005027b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180050280  nop
0x180050281  lea     rcx, [rsp+160h+hKey]
0x180050286  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005028b  nop
0x18005028c  lea     rcx, [rsp+160h+var_100]; void *
0x180050291  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180050296  nop
0x180050297  lea     rcx, [rsp+160h+lpSubKey]; void *
0x18005029c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800502a1  mov     ebx, esi
0x1800502a3  jmp     loc_180050AE3
0x1800502a8  xor     esi, esi
0x1800502aa  mov     [rbp+60h+var_C8], sil
0x1800502ae  lea     rax, [rbp+60h+var_C8]
0x1800502b2  mov     [rbp+60h+var_A8], rax
0x1800502b6  mov     word ptr [rbp+60h+var_A0], 100h
0x1800502bc  cmp     byte ptr [rbp+60h+arg_10], sil
0x1800502c3  jnz     short loc_1800502F4
0x1800502c5  xor     ecx, ecx; BindingHandle
0x1800502c7  call    cs:__imp_RpcImpersonateClient
0x1800502cd  test    eax, eax
0x1800502cf  jz      short loc_1800502F0
0x1800502d1  mov     rcx, [rbp+68h]; this
0x1800502d5  mov     r9d, eax; char *
0x1800502d8  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800502df  mov     edx, 120h; void *
0x1800502e4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800502e9  mov     ebx, eax
0x1800502eb  jmp     loc_180050A97
0x1800502f0  mov     [rbp+60h+var_C8], dil
0x1800502f4  mov     [rbp+60h+var_D8], rsi
  ... truncated ...
```
