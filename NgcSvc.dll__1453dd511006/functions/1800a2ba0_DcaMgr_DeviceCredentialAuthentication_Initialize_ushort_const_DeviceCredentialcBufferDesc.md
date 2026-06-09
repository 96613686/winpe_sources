# DcaMgr::DeviceCredentialAuthentication::Initialize(ushort const *,_DeviceCredentialcBufferDesc *)

- ea: `0x1800a2ba0`
- end: `0x1800a362a`
- name: `?Initialize@DeviceCredentialAuthentication@DcaMgr@@MEAAJPEBGPEAU_DeviceCredentialcBufferDesc@@@Z`
- size: `2698`
- prototype: `int(DcaMgr::DeviceCredentialAuthentication *__hidden this, const unsigned __int16 *, struct _DeviceCredentialcBufferDesc *)`
- caller_count: `0`
- callee_count: `36`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000782c`
- `0x18000926c`
- `0x180013710`
- `0x1800281e0`
- `0x180028200`
- `0x18002832c`
- `0x1800288a0`
- `0x1800323d0`
- `0x180032c20`
- `0x18004826c`
- `0x180048304`
- `0x1800497a0`
- `0x180050b30`
- `0x1800527ac`
- `0x1800535f4`
- `0x1800596ec`
- `0x18005bce8`
- `0x180069998`
- `0x180069b58`
- `0x180069c28`
- `0x180069c60`
- `0x180097c6c`
- `0x180097cb4`
- `0x180098cfc`
- `0x180098e4c`
- `0x18009ffac`
- `0x1800a2170`
- `0x1800a22c8`
- `0x1800a2ba0`
- `0x1800a41ac`
- `0x1800a4334`
- `0x1800a43a8`
- `0x1800a6408`
- `0x1800a66a8`
- `0x1800a6d30`
- `0x1800a7624`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a2edf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a2edf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a2df8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a2e4f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a2fa3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a2df8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a2e4f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a2fa3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a2e97`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a2e97`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800a34b0`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800a34b0`
- `bcrypt!BCryptGenRandom` at `0x1800a30ba`
- `bcrypt!BCryptGenRandom` at `0x1800a30ba`

## string_xrefs

- `0x1800a2c6b`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a2cb6`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a2d2f`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a2ea8`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a2f4f`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a2fb4`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a3051`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a30cb`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a3143`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a3207`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a32d1`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a3369`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a33e6`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a357d`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a35a2`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a35fd`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a2d95`: `UserSid`
- `0x1800a2deb`: `ProtocolVersion`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall DcaMgr::DeviceCredentialAuthentication::Initialize(
        DcaMgr::DeviceCredentialAuthentication *this,
        WCHAR *a2,
        struct _DeviceCredentialcBufferDesc *a3)
{
  __int64 v5; // rcx
  const void *v6; // r13
  rsize_t v7; // rsi
  int i; // edx
  __int64 v9; // rdx
  int UserSidAndPackageInfoFromToken; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  unsigned __int64 v13; // r9
  const unsigned __int16 *v14; // r9
  int v15; // eax
  unsigned int ValueW; // eax
  unsigned int v17; // edx
  __int64 v18; // r9
  __int64 v19; // rdx
  unsigned int v20; // eax
  unsigned int v21; // edx
  DcaMgr *v22; // rcx
  unsigned int v23; // eax
  unsigned int v24; // eax
  HKEY *v25; // r8
  unsigned int v26; // eax
  unsigned int v27; // r12d
  PUCHAR v28; // rbx
  NTSTATUS v29; // eax
  int v30; // edi
  int v31; // r15d
  char *v32; // rdi
  char *v33; // rsi
  __int64 v34; // rcx
  __int64 v35; // rdx
  const char *v36; // r9
  __int64 v37; // rcx
  void *v38; // rdx
  unsigned int v39; // edi
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // rcx
  void *v43; // rdx
  unsigned int pdwType; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypeb; // [rsp+20h] [rbp-E0h]
  int pdwTypec; // [rsp+20h] [rbp-E0h]
  int pdwTyped; // [rsp+20h] [rbp-E0h]
  int pdwTypee; // [rsp+20h] [rbp-E0h]
  int pdwTypef; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpSubKey; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v53; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE TokenHandle; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v55; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v56; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v57; // [rsp+68h] [rbp-98h] BYREF
  void *Source; // [rsp+70h] [rbp-90h] BYREF
  void **p_lpSubKey; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 *v60; // [rsp+80h] [rbp-80h] BYREF
  char v61; // [rsp+88h] [rbp-78h]
  HKEY hkey; // [rsp+90h] [rbp-70h] BYREF
  PUCHAR pbBuffer; // [rsp+98h] [rbp-68h] BYREF
  void *v64; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v65; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v66; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v67; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v68; // [rsp+C0h] [rbp-40h] BYREF
  DcaMgr *pvData; // [rsp+C8h] [rbp-38h] BYREF
  void *Destination; // [rsp+D0h] [rbp-30h] BYREF
  __int64 *p_hkey; // [rsp+D8h] [rbp-28h] BYREF
  struct DcaMgr::DeviceCredentialHmacBase *v72; // [rsp+E0h] [rbp-20h] BYREF
  char v73; // [rsp+E8h] [rbp-18h]
  int v74; // [rsp+F0h] [rbp-10h] BYREF
  int v75; // [rsp+F4h] [rbp-Ch]
  __int64 v76; // [rsp+F8h] [rbp-8h] BYREF
  int v77[16]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]
  DWORD cbData; // [rsp+160h] [rbp+60h] BYREF
  int Data; // [rsp+168h] [rbp+68h] BYREF

  if ( *((_DWORD *)a3 + 1) != 1 || (v5 = *((_QWORD *)a3 + 1)) == 0 )
  {
    v9 = 744;
    goto LABEL_88;
  }
  v6 = 0;
  v7 = 0;
  for ( i = 0; !i; i = 1 )
  {
    if ( *(_DWORD *)v5 != 3 )
    {
      v9 = 762;
      goto LABEL_88;
    }
    v7 = *(unsigned int *)(v5 + 4);
    if ( (unsigned int)v7 > 0x80 )
    {
      v9 = 758;
      goto LABEL_88;
    }
    v6 = *(const void **)(v5 + 8);
  }
  if ( !v6 || !(_DWORD)v7 )
  {
    v9 = 767;
LABEL_88:
    UserSidAndPackageInfoFromToken = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)0x80070057LL,
      pdwType);
    return (unsigned int)UserSidAndPackageInfoFromToken;
  }
  hkey = 0;
  p_hkey = (__int64 *)&hkey;
  v72 = 0;
  v73 = 1;
  UserSidAndPackageInfoFromToken = DcaMgr::OpenDeviceRegKey(a2, (const unsigned __int16 *)&v72, (HKEY *)a3);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hkey);
  if ( UserSidAndPackageInfoFromToken < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x302,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
      pdwType);
LABEL_84:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    return (unsigned int)UserSidAndPackageInfoFromToken;
  }
  TokenHandle = 0;
  p_hkey = (__int64 *)&TokenHandle;
  v72 = 0;
  v73 = 1;
  UserSidAndPackageInfoFromToken = OpenCallerImpersonationToken(v11, (HANDLE *)&v72);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_hkey);
  if ( UserSidAndPackageInfoFromToken < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x307,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
      pdwType);
LABEL_83:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    goto LABEL_84;
  }
  lpSubKey = 0;
  v53 = 0;
  p_lpSubKey = (void **)&v53;
  v60 = 0;
  v61 = 1;
  p_hkey = (__int64 *)&lpSubKey;
  v72 = 0;
  v73 = 1;
  UserSidAndPackageInfoFromToken = GetUserSidAndPackageInfoFromToken(TokenHandle, &v72, (WCHAR **)&v60, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hkey);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_lpSubKey);
  if ( UserSidAndPackageInfoFromToken < 0 )
  {
    v12 = 782;
LABEL_18:
    v13 = (unsigned int)UserSidAndPackageInfoFromToken;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)v13,
      pdwType);
LABEL_82:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v53);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpSubKey);
    goto LABEL_83;
  }
  DevCredSvcTraceLoggingProvider::AppInfo(v53, lpSubKey);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpSubKey,
    0);
  v15 = DcaMgr::ValidateOwnership(hkey, 0, v53, v14);
  UserSidAndPackageInfoFromToken = v15;
  if ( v15 < 0 )
  {
    v13 = (unsigned int)v15;
    v12 = 791;
    goto LABEL_19;
  }
  p_lpSubKey = (void **)&lpSubKey;
  v60 = 0;
  v61 = 1;
  UserSidAndPackageInfoFromToken = ReadRegStringValue(hkey, 0, L"UserSid");
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_lpSubKey);
  if ( UserSidAndPackageInfoFromToken < 0 )
  {
    v12 = 797;
    goto LABEL_18;
  }
  LODWORD(pvData) = 0;
  cbData = 4;
  ValueW = RegGetValueW(hkey, 0, L"ProtocolVersion", 0x10u, 0, &pvData, &cbData);
  if ( ValueW )
  {
    v18 = ValueW;
    v19 = 808;
LABEL_81:
    UserSidAndPackageInfoFromToken = wil::details::in1diag3::Return_Win32(
                                       retaddr,
                                       (void *)v19,
                                       (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
                                       (const char *)v18,
                                       pdwTypea);
    goto LABEL_82;
  }
  UserSidAndPackageInfoFromToken = DcaMgr::ValidateProtocolVersion((DcaMgr *)(unsigned int)pvData, v17);
  v77[0] = 0;
  if ( UserSidAndPackageInfoFromToken >= 0 )
  {
    cbData = 4;
    v20 = RegGetValueW(hkey, 0, L"DeviceCapability", 0x10u, 0, v77, &cbData);
    if ( v20 )
    {
      v18 = v20;
      v19 = 822;
      goto LABEL_81;
    }
    UserSidAndPackageInfoFromToken = DcaMgr::ValidatePolicy(v22, v21);
  }
  Data = 2;
  if ( UserSidAndPackageInfoFromToken < 0 )
  {
    v23 = RegSetValueExW(hkey, L"State", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v23 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x344,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
        (const char *)v23,
        pdwType);
    v12 = 837;
    goto LABEL_18;
  }
  cbData = 4;
  v24 = RegQueryValueExW(hkey, L"State", 0, 0, (LPBYTE)&Data, &cbData);
  if ( v24 )
  {
    v18 = v24;
    v19 = 847;
    goto LABEL_81;
  }
  switch ( Data )
  {
    case 0:
      goto LABEL_85;
    case 2:
      v18 = 1260;
      v19 = 852;
      goto LABEL_81;
    case 3:
LABEL_85:
      v18 = 1168;
      v19 = 856;
      goto LABEL_81;
  }
  v56 = 0;
  p_lpSubKey = (void **)&v56;
  v60 = 0;
  v61 = 1;
  UserSidAndPackageInfoFromToken = DcaMgr::OpenUserRegKey(lpSubKey, (const unsigned __int16 *)&v60, v25);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpSubKey);
  if ( UserSidAndPackageInfoFromToken < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35E,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
      pdwTypea);
LABEL_41:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v56);
    goto LABEL_82;
  }
  v74 = 0;
  cbData = 4;
  v26 = RegGetValueW(v56, 0, L"TpmHmacEnabled", 0x10u, 0, &v74, &cbData);
  if ( v26 )
  {
    UserSidAndPackageInfoFromToken = wil::details::in1diag3::Return_Win32(
                                       retaddr,
                                       (void *)0x369,
                                       (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
                                       (const char *)v26,
                                       pdwTypeb);
    goto LABEL_41;
  }
  Source = 0;
  v55 = 0;
  v57 = 0;
  p_hkey = &v57;
  v72 = 0;
  v73 = 1;
  p_lpSubKey = &Source;
  v60 = 0;
  v61 = 1;
  UserSidAndPackageInfoFromToken = DcaMgr::DeviceCredentialHmacBase::GenerateDeviceNonce(
                                     lpSubKey,
                                     a2,
                                     hkey,
                                     v74 != 0,
                                     &v60,
                                     &v55,
                                     &v72);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_lpSubKey);
  wil::details::out_param_t<wistd::unique_ptr<DcaMgr::DeviceCredentialHmacBase,wistd::default_delete<DcaMgr::DeviceCredentialHmacBase>>>::~out_param_t<wistd::unique_ptr<DcaMgr::DeviceCredentialHmacBase,wistd::default_delete<DcaMgr::DeviceCredentialHmacBase>>>(&p_hkey);
  if ( UserSidAndPackageInfoFromToken < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x376,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
      pdwTypec);
LABEL_46:
    wistd::unique_ptr<DcaMgr::DeviceCredentialHmacBase,wistd::default_delete<DcaMgr::DeviceCredentialHmacBase>>::reset(
      &v57,
      0);
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&Source);
    goto LABEL_41;
  }
  v27 = v55;
  if ( v55 != 32 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  wil::make_unique_hlocal_secure_nothrow<unsigned char [0]>(&pbBuffer, 0x20u);
  v28 = pbBuffer;
  if ( !pbBuffer )
  {
    UserSidAndPackageInfoFromToken = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37B,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)0x8007000ELL,
      pdwTypec);
    goto LABEL_52;
  }
  v29 = BCryptGenRandom(0, pbBuffer, 0x20u, 2u);
  if ( v29 < 0 )
  {
    UserSidAndPackageInfoFromToken = wil::details::in1diag3::Return_NtStatus(
                                       retaddr,
                                       (void *)0x380,
                                       (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
                                       (const char *)(unsigned int)v29,
                                       pdwTypec);
LABEL_52:
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&pbBuffer);
    goto LABEL_46;
  }
  v66 = 0;
  v75 = 0;
  v65 = 0;
  v55 = 0;
  p_lpSubKey = (void **)&v65;
  v60 = 0;
  v61 = 1;
  v30 = ReadRegBinaryValue(hkey, &v55);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_lpSubKey);
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38D,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)(unsigned int)v30,
      pdwTyped);
LABEL_55:
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v65);
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v66);
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&pbBuffer);
    wistd::unique_ptr<DcaMgr::DeviceCredentialHmacBase,wistd::default_delete<DcaMgr::DeviceCredentialHmacBase>>::reset(
      &v57,
      0);
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&Source);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v56);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v53);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpSubKey);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    UserSidAndPackageInfoFromToken = v30;
    goto LABEL_84;
  }
  v67 = 0;
  LODWORD(v68) = 0;
  p_lpSubKey = (void **)&v67;
  v60 = 0;
  v61 = 1;
  v30 = DpapiProtectUnprotect(0, v65, v55, (unsigned int)&v60, (__int64)&v68);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_lpSubKey);
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x396,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)(unsigned int)v30,
      pdwTypee);
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v67);
    goto LABEL_55;
  }
  v31 = v7 + 64;
  wil::make_unique_hlocal_secure_nothrow<unsigned char [0]>(&Destination, (unsigned int)(v7 + 64));
  v32 = (char *)Destination;
  if ( !Destination )
  {
    UserSidAndPackageInfoFromToken = -2147024882;
    v35 = 923;
    goto LABEL_61;
  }
  memcpy_s(Destination, v7, v6, v7);
  v33 = &v32[v7];
  memcpy_s(v33, 0x20u, Source, 0x20u);
  memcpy_s(v33 + 32, 0x20u, v28, 0x20u);
  p_lpSubKey = (void **)&v66;
  v60 = 0;
  v61 = 1;
  pdwTypee = v31;
  UserSidAndPackageInfoFromToken = GenerateHmac(v34, v67, (unsigned int)v68, v32);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_lpSubKey);
  if ( UserSidAndPackageInfoFromToken < 0 )
  {
    v35 = 947;
LABEL_61:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
      pdwTypee);
LABEL_62:
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&Destination);
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v67);
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v65);
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v66);
    goto LABEL_52;
  }
  v64 = 0;
  LODWORD(v68) = 0;
  p_lpSubKey = &v64;
  v60 = 0;
  v61 = 1;
  UserSidAndPackageInfoFromToken = ReadRegBinaryValue(hkey, &v68);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_lpSubKey);
  if ( (int)(UserSidAndPackageInfoFromToken + 0x80000000) >= 0 && UserSidAndPackageInfoFromToken != -2147024894 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3BE,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
      pdwTypef);
    goto LABEL_66;
  }
  v76 = 0;
  v39 = 0;
  v55 = 0;
  if ( UserSidAndPackageInfoFromToken >= 0 )
  {
    p_lpSubKey = (void **)&v76;
    v60 = 0;
    v61 = 1;
    UserSidAndPackageInfoFromToken = DpapiProtectUnprotect(0, (_DWORD)v64, v68, (unsigned int)&v60, (__int64)&v55);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_lpSubKey);
    if ( UserSidAndPackageInfoFromToken < 0 )
    {
      v40 = 969;
LABEL_71:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v40,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
        (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
        pdwTypef);
      wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v76);
LABEL_66:
      v38 = v64;
      v64 = 0;
      if ( v38 )
        wil::hlocal_secure_deleter::operator()<unsigned char>(v37, v38);
      goto LABEL_62;
    }
    v39 = v55;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v68,
    (char *)a2,
    0xFFFFFFFFFFFFFFFFuLL,
    v36);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    (char *)this + 8,
    &v68);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v68);
  if ( !*((_QWORD *)this + 1) )
  {
    UserSidAndPackageInfoFromToken = -2147024882;
    v40 = 973;
    goto LABEL_71;
  }
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::operator=((char *)this + 24, &Source);
  *((_DWORD *)this + 8) = v27;
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::operator=((char *)this + 40, &pbBuffer);
  *((_DWORD *)this + 12) = 32;
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::operator=((char *)this + 72, &v66);
  *((_DWORD *)this + 20) = v75;
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::operator=((char *)this + 56, &v76);
  *((_DWORD *)this + 16) = v39;
  *((_DWORD *)this + 4) = (_DWORD)pvData;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    (char *)this + 88,
    &lpSubKey);
  v41 = v57;
  v57 = 0;
  wistd::unique_ptr<DcaMgr::DeviceCredentialHmacBase,wistd::default_delete<DcaMgr::DeviceCredentialHmacBase>>::reset(
    (char *)this + 104,
    v41);
  _time64((__time64_t *)this + 12);
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v76);
  v43 = v64;
  v64 = 0;
  if ( v43 )
    wil::hlocal_secure_deleter::operator()<unsigned char>(v42, v43);
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&Destination);
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v67);
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v65);
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v66);
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&pbBuffer);
  wistd::unique_ptr<DcaMgr::DeviceCredentialHmacBase,wistd::default_delete<DcaMgr::DeviceCredentialHmacBase>>::reset(
    &v57,
    0);
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&Source);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v56);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v53);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpSubKey);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return 0;
}

```

## disassembly

```asm
0x1800a2ba0  mov     [rsp-8+arg_0], rbx
0x1800a2ba5  mov     [rsp-8+arg_8], rdx
0x1800a2baa  push    rbp
0x1800a2bab  push    rsi
0x1800a2bac  push    rdi
0x1800a2bad  push    r12
0x1800a2baf  push    r13
0x1800a2bb1  push    r14
0x1800a2bb3  push    r15
0x1800a2bb5  lea     rbp, [rsp-10h]
0x1800a2bba  sub     rsp, 110h
0x1800a2bc1  mov     rdi, rdx
0x1800a2bc4  mov     r14, rcx
0x1800a2bc7  cmp     dword ptr [r8+4], 1
0x1800a2bcc  jnz     loc_1800A35F0
0x1800a2bd2  mov     rcx, [r8+8]
0x1800a2bd6  xor     r15d, r15d
0x1800a2bd9  test    rcx, rcx
0x1800a2bdc  jz      loc_1800A35F0
0x1800a2be2  mov     r13d, r15d
0x1800a2be5  mov     esi, r15d
0x1800a2be8  mov     edx, r15d
0x1800a2beb  cmp     edx, 1
0x1800a2bee  jnb     short loc_1800A2C24
0x1800a2bf0  mov     eax, edx
0x1800a2bf2  add     rax, rax
0x1800a2bf5  cmp     dword ptr [rcx+rax*8], 3
0x1800a2bf9  jnz     short loc_1800A2C1A
0x1800a2bfb  mov     esi, [rcx+rax*8+4]
0x1800a2bff  cmp     esi, 80h
0x1800a2c05  ja      short loc_1800A2C10
0x1800a2c07  mov     r13, [rcx+rax*8+8]
0x1800a2c0c  inc     edx
0x1800a2c0e  jmp     short loc_1800A2BEB
0x1800a2c10  mov     edx, 2F6h
0x1800a2c15  jmp     loc_1800A35F5
0x1800a2c1a  mov     edx, 2FAh
0x1800a2c1f  jmp     loc_1800A35F5
0x1800a2c24  test    r13, r13
0x1800a2c27  jz      loc_1800A35E9
0x1800a2c2d  test    esi, esi
0x1800a2c2f  jz      loc_1800A35E9
0x1800a2c35  mov     [rbp+40h+hkey], r15
0x1800a2c39  lea     rax, [rbp+40h+hkey]
0x1800a2c3d  mov     [rbp+40h+var_68], rax
0x1800a2c41  mov     [rbp+40h+var_60], r15
0x1800a2c45  mov     [rbp+40h+var_58], 1
0x1800a2c49  lea     rdx, [rbp+40h+var_60]; unsigned __int16 *
0x1800a2c4d  mov     rcx, rdi; lpSubKey
0x1800a2c50  call    ?OpenDeviceRegKey@DcaMgr@@YAJPEBGPEAPEAUHKEY__@@@Z; DcaMgr::OpenDeviceRegKey(ushort const *,HKEY__ * *)
0x1800a2c55  mov     ebx, eax
0x1800a2c57  lea     rcx, [rbp+40h+var_68]
0x1800a2c5b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800a2c60  test    ebx, ebx
0x1800a2c62  jns     short loc_1800A2C81
0x1800a2c64  mov     rcx, [rbp+48h]; this
0x1800a2c68  mov     r9d, ebx; char *
0x1800a2c6b  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800a2c72  mov     edx, 302h; void *
0x1800a2c77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2c7c  jmp     loc_1800A35D1
0x1800a2c81  mov     [rsp+140h+TokenHandle], r15
0x1800a2c86  lea     rax, [rsp+140h+TokenHandle]
0x1800a2c8b  mov     [rbp+40h+var_68], rax
0x1800a2c8f  mov     [rbp+40h+var_60], r15
0x1800a2c93  mov     [rbp+40h+var_58], 1
0x1800a2c97  lea     rdx, [rbp+40h+var_60]
0x1800a2c9b  call    OpenCallerImpersonationToken
0x1800a2ca0  mov     ebx, eax
0x1800a2ca2  lea     rcx, [rbp+40h+var_68]
0x1800a2ca6  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800a2cab  test    ebx, ebx
0x1800a2cad  jns     short loc_1800A2CCC
0x1800a2caf  mov     rcx, [rbp+48h]; this
0x1800a2cb3  mov     r9d, ebx; char *
0x1800a2cb6  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800a2cbd  mov     edx, 307h; void *
0x1800a2cc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2cc7  jmp     loc_1800A35C6
0x1800a2ccc  mov     [rsp+140h+lpSubKey], r15
0x1800a2cd1  mov     [rsp+140h+var_F8], r15
0x1800a2cd6  lea     rax, [rsp+140h+var_F8]
0x1800a2cdb  mov     [rsp+140h+var_C8], rax
0x1800a2ce0  mov     [rbp+40h+var_C0], r15
0x1800a2ce4  mov     [rbp+40h+var_B8], 1
0x1800a2ce8  lea     rax, [rsp+140h+lpSubKey]
0x1800a2ced  mov     [rbp+40h+var_68], rax
0x1800a2cf1  mov     [rbp+40h+var_60], r15
0x1800a2cf5  mov     [rbp+40h+var_58], 1
0x1800a2cf9  xor     r9d, r9d
0x1800a2cfc  lea     r8, [rbp+40h+var_C0]
0x1800a2d00  lea     rdx, [rbp+40h+var_60]
0x1800a2d04  mov     rcx, [rsp+140h+TokenHandle]; TokenHandle
0x1800a2d09  call    GetUserSidAndPackageInfoFromToken
0x1800a2d0e  mov     ebx, eax
0x1800a2d10  lea     rcx, [rbp+40h+var_68]
0x1800a2d14  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800a2d19  lea     rcx, [rsp+140h+var_C8]
0x1800a2d1e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800a2d23  test    ebx, ebx
0x1800a2d25  jns     short loc_1800A2D44
0x1800a2d27  mov     edx, 30Eh; void *
0x1800a2d2c  mov     r9d, ebx; char *
0x1800a2d2f  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800a2d36  mov     rcx, [rbp+48h]; this
0x1800a2d3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2d3f  jmp     loc_1800A35B0
0x1800a2d44  mov     rdx, [rsp+140h+lpSubKey]; unsigned __int16 *
0x1800a2d49  mov     rcx, [rsp+140h+var_F8]; unsigned __int16 *
0x1800a2d4e  call    ?AppInfo@DevCredSvcTraceLoggingProvider@@SAXPEBG0@Z; DevCredSvcTraceLoggingProvider::AppInfo(ushort const *,ushort const *)
0x1800a2d53  xor     edx, edx
0x1800a2d55  lea     rcx, [rsp+140h+lpSubKey]
0x1800a2d5a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a2d5f  mov     r8, [rsp+140h+var_F8]; unsigned __int16 *
0x1800a2d64  xor     edx, edx; HKEY
0x1800a2d66  mov     rcx, [rbp+40h+hkey]; hkey
0x1800a2d6a  call    ?ValidateOwnership@DcaMgr@@YAJPEAUHKEY__@@PEBG1@Z; DcaMgr::ValidateOwnership(HKEY__ *,ushort const *,ushort const *)
0x1800a2d6f  mov     ebx, eax
0x1800a2d71  test    eax, eax
0x1800a2d73  jns     short loc_1800A2D7F
0x1800a2d75  mov     r9d, eax
0x1800a2d78  mov     edx, 317h
0x1800a2d7d  jmp     short loc_1800A2D2F
0x1800a2d7f  lea     rax, [rsp+140h+lpSubKey]
0x1800a2d84  mov     [rsp+140h+var_C8], rax
0x1800a2d89  mov     [rbp+40h+var_C0], r15
0x1800a2d8d  mov     [rbp+40h+var_B8], 1
0x1800a2d91  lea     r9, [rbp+40h+var_C0]
0x1800a2d95  lea     r8, aUsersid; "UserSid"
0x1800a2d9c  xor     edx, edx; lpSubKey
0x1800a2d9e  mov     rcx, [rbp+40h+hkey]; hkey
0x1800a2da2  call    ReadRegStringValue
0x1800a2da7  mov     ebx, eax
0x1800a2da9  lea     rcx, [rsp+140h+var_C8]
0x1800a2dae  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800a2db3  test    ebx, ebx
0x1800a2db5  jns     short loc_1800A2DC1
0x1800a2db7  mov     edx, 31Dh
0x1800a2dbc  jmp     loc_1800A2D2C
0x1800a2dc1  mov     dword ptr [rbp+40h+var_78], r15d
0x1800a2dc5  mov     r12d, 4
0x1800a2dcb  mov     [rbp+40h+cbData], r12d
0x1800a2dcf  lea     rax, [rbp+40h+cbData]
0x1800a2dd3  mov     [rsp+140h+pcbData], rax; pcbData
0x1800a2dd8  lea     rax, [rbp+40h+var_78]
0x1800a2ddc  mov     [rsp+140h+pvData], rax; pvData
0x1800a2de1  mov     [rsp+140h+pdwType], r15; pdwType
0x1800a2de6  lea     r9d, [r12+0Ch]; dwFlags
0x1800a2deb  lea     r8, aProtocolversio; "ProtocolVersion"
0x1800a2df2  xor     edx, edx; lpSubKey
0x1800a2df4  mov     rcx, [rbp+40h+hkey]; hkey
0x1800a2df8  call    cs:__imp_RegGetValueW
0x1800a2dfe  test    eax, eax
0x1800a2e00  jz      short loc_1800A2E0F
0x1800a2e02  mov     r9d, eax
0x1800a2e05  mov     edx, 328h
0x1800a2e0a  jmp     loc_1800A359E
0x1800a2e0f  mov     ecx, dword ptr [rbp+40h+var_78]; this
0x1800a2e12  call    ?ValidateProtocolVersion@DcaMgr@@YAJK@Z; DcaMgr::ValidateProtocolVersion(ulong)
0x1800a2e17  mov     ebx, eax
0x1800a2e19  mov     [rbp+40h+var_40], r15d
0x1800a2e1d  test    eax, eax
0x1800a2e1f  js      short loc_1800A2E6D
0x1800a2e21  mov     [rbp+40h+cbData], r12d
0x1800a2e25  lea     rax, [rbp+40h+cbData]
0x1800a2e29  mov     [rsp+140h+pcbData], rax; pcbData
0x1800a2e2e  lea     rax, [rbp+40h+var_40]
0x1800a2e32  mov     [rsp+140h+pvData], rax; pvData
0x1800a2e37  mov     [rsp+140h+pdwType], r15; pdwType
0x1800a2e3c  mov     r9d, 10h; dwFlags
0x1800a2e42  lea     r8, aDevicecapabili; "DeviceCapability"
0x1800a2e49  xor     edx, edx; lpSubKey
0x1800a2e4b  mov     rcx, [rbp+40h+hkey]; hkey
0x1800a2e4f  call    cs:__imp_RegGetValueW
0x1800a2e55  test    eax, eax
0x1800a2e57  jz      short loc_1800A2E66
0x1800a2e59  mov     r9d, eax
0x1800a2e5c  mov     edx, 336h
0x1800a2e61  jmp     loc_1800A359E
0x1800a2e66  call    ?ValidatePolicy@DcaMgr@@YAJK@Z; DcaMgr::ValidatePolicy(ulong)
0x1800a2e6b  mov     ebx, eax
0x1800a2e6d  mov     [rbp+40h+Data], 2
0x1800a2e74  lea     rdx, aState; "State"
0x1800a2e7b  mov     rcx, [rbp+40h+hkey]; hKey
0x1800a2e7f  test    ebx, ebx
0x1800a2e81  jns     short loc_1800A2EC3
0x1800a2e83  mov     dword ptr [rsp+140h+pvData], r12d; cbData
0x1800a2e88  lea     rax, [rbp+40h+Data]
0x1800a2e8c  mov     [rsp+140h+pdwType], rax; unsigned int
0x1800a2e91  mov     r9d, r12d; dwType
0x1800a2e94  xor     r8d, r8d; Reserved
0x1800a2e97  call    cs:__imp_RegSetValueExW
0x1800a2e9d  mov     rcx, [rbp+48h]; this
0x1800a2ea1  test    eax, eax
0x1800a2ea3  jz      short loc_1800A2EB9
0x1800a2ea5  mov     r9d, eax; char *
0x1800a2ea8  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800a2eaf  mov     edx, 344h; void *
0x1800a2eb4  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800a2eb9  mov     edx, 345h
0x1800a2ebe  jmp     loc_1800A2D2C
0x1800a2ec3  mov     [rbp+40h+cbData], r12d
0x1800a2ec7  lea     rax, [rbp+40h+cbData]
0x1800a2ecb  mov     [rsp+140h+pvData], rax; lpcbData
0x1800a2ed0  lea     rax, [rbp+40h+Data]
0x1800a2ed4  mov     [rsp+140h+pdwType], rax; unsigned int
0x1800a2ed9  xor     r9d, r9d; lpType
0x1800a2edc  xor     r8d, r8d; lpReserved
0x1800a2edf  call    cs:__imp_RegQueryValueExW
0x1800a2ee5  test    eax, eax
0x1800a2ee7  jz      short loc_1800A2EF6
0x1800a2ee9  mov     r9d, eax
0x1800a2eec  mov     edx, 34Fh
0x1800a2ef1  jmp     loc_1800A359E
0x1800a2ef6  mov     ecx, [rbp+40h+Data]
0x1800a2ef9  test    ecx, ecx
0x1800a2efb  jz      loc_1800A35DC
0x1800a2f01  sub     ecx, 2
0x1800a2f04  jz      loc_1800A3593
0x1800a2f0a  cmp     ecx, 1
0x1800a2f0d  jz      loc_1800A35DC
0x1800a2f13  mov     [rsp+140h+var_E0], r15
0x1800a2f18  lea     rax, [rsp+140h+var_E0]
0x1800a2f1d  mov     [rsp+140h+var_C8], rax
0x1800a2f22  mov     [rbp+40h+var_C0], r15
0x1800a2f26  mov     [rbp+40h+var_B8], 1
0x1800a2f2a  lea     rdx, [rbp+40h+var_C0]; unsigned __int16 *
0x1800a2f2e  mov     rcx, [rsp+140h+lpSubKey]; lpSubKey
0x1800a2f33  call    ?OpenUserRegKey@DcaMgr@@YAJPEBGPEAPEAUHKEY__@@@Z; DcaMgr::OpenUserRegKey(ushort const *,HKEY__ * *)
0x1800a2f38  mov     ebx, eax
0x1800a2f3a  lea     rcx, [rsp+140h+var_C8]
0x1800a2f3f  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800a2f44  test    ebx, ebx
0x1800a2f46  jns     short loc_1800A2F70
0x1800a2f48  mov     rcx, [rbp+48h]; this
0x1800a2f4c  mov     r9d, ebx; char *
0x1800a2f4f  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800a2f56  mov     edx, 35Eh; void *
0x1800a2f5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2f60  nop
0x1800a2f61  lea     rcx, [rsp+140h+var_E0]
0x1800a2f66  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a2f6b  jmp     loc_1800A35B0
0x1800a2f70  mov     [rbp+40h+var_50], r15d
0x1800a2f74  mov     [rbp+40h+cbData], r12d
0x1800a2f78  lea     rax, [rbp+40h+cbData]
0x1800a2f7c  mov     [rsp+140h+pcbData], rax; pcbData
0x1800a2f81  lea     rax, [rbp+40h+var_50]
0x1800a2f85  mov     [rsp+140h+pvData], rax; pvData
0x1800a2f8a  mov     [rsp+140h+pdwType], r15; unsigned int
0x1800a2f8f  mov     r9d, 10h; dwFlags
0x1800a2f95  lea     r8, aTpmhmacenabled; "TpmHmacEnabled"
0x1800a2f9c  xor     edx, edx; lpSubKey
0x1800a2f9e  mov     rcx, [rsp+140h+var_E0]; hkey
0x1800a2fa3  call    cs:__imp_RegGetValueW
0x1800a2fa9  test    eax, eax
0x1800a2fab  jz      short loc_1800A2FC9
0x1800a2fad  mov     rcx, [rbp+48h]; this
0x1800a2fb1  mov     r9d, eax; char *
0x1800a2fb4  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800a2fbb  mov     edx, 369h; void *
0x1800a2fc0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a2fc5  mov     ebx, eax
0x1800a2fc7  jmp     short loc_1800A2F61
0x1800a2fc9  mov     [rsp+140h+Source], r15
0x1800a2fce  mov     [rsp+140h+var_E8], r15d
0x1800a2fd3  mov     [rsp+140h+var_D8], r15
0x1800a2fd8  lea     rax, [rsp+140h+var_D8]
0x1800a2fdd  mov     [rbp+40h+var_68], rax
0x1800a2fe1  mov     [rbp+40h+var_60], r15
0x1800a2fe5  mov     [rbp+40h+var_58], 1
0x1800a2fe9  lea     rax, [rsp+140h+Source]
0x1800a2fee  mov     [rsp+140h+var_C8], rax
0x1800a2ff3  mov     [rbp+40h+var_C0], r15
0x1800a2ff7  mov     [rbp+40h+var_B8], 1
0x1800a2ffb  cmp     [rbp+40h+var_50], r15d
0x1800a2fff  setnz   r9b; bool
0x1800a3003  lea     rax, [rbp+40h+var_60]
0x1800a3007  mov     [rsp+140h+pcbData], rax; struct DcaMgr::DeviceCredentialHmacBase **
0x1800a300c  lea     rax, [rsp+140h+var_E8]
0x1800a3011  mov     [rsp+140h+pvData], rax; unsigned int *
0x1800a3016  lea     rax, [rbp+40h+var_C0]
0x1800a301a  mov     [rsp+140h+pdwType], rax; int
0x1800a301f  mov     r8, [rbp+40h+hkey]; HKEY
0x1800a3023  mov     rdx, rdi; unsigned __int16 *
0x1800a3026  mov     rcx, [rsp+140h+lpSubKey]; unsigned __int16 *
0x1800a302b  call    ?GenerateDeviceNonce@DeviceCredentialHmacBase@DcaMgr@@SAJPEBG0PEAUHKEY__@@_NPEAPEAEPEAKPEAPEAV12@@Z; DcaMgr::DeviceCredentialHmacBase::GenerateDeviceNonce(ushort const *,ushort const *,HKEY__ *,bool,uchar * *,ulong *,DcaMgr::DeviceCredentialHmacBase * *)
0x1800a3030  mov     ebx, eax
0x1800a3032  lea     rcx, [rsp+140h+var_C8]
0x1800a3037  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
0x1800a303c  nop
0x1800a303d  lea     rcx, [rbp+40h+var_68]
0x1800a3041  call    ??1?$out_param_t@V?$unique_ptr@VDeviceCredentialHmacBase@DcaMgr@@U?$default_delete@VDeviceCredentialHmacBase@DcaMgr@@@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<DcaMgr::DeviceCredentialHmacBase,wistd::default_delete<DcaMgr::DeviceCredentialHmacBase>>>::~out_param_t<wistd::unique_ptr<DcaMgr::DeviceCredentialHmacBase,wistd::default_delete<DcaMgr::DeviceCredentialHmacBase>>>(void)
0x1800a3046  test    ebx, ebx
0x1800a3048  jns     short loc_1800A307F
0x1800a304a  mov     rcx, [rbp+48h]; this
0x1800a304e  mov     r9d, ebx; char *
0x1800a3051  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800a3058  mov     edx, 376h; void *
0x1800a305d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
