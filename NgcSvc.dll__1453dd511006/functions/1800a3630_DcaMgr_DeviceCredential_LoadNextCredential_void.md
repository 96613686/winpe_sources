# DcaMgr::DeviceCredential::LoadNextCredential(void)

- ea: `0x1800a3630`
- end: `0x1800a3caa`
- name: `?LoadNextCredential@DeviceCredential@DcaMgr@@QEAAJXZ`
- size: `1658`
- prototype: `__int64 __fastcall(DcaMgr::DeviceCredential *__hidden this)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180008b00`
- `0x18009f320`

## callees

- `0x18000782c`
- `0x1800281e0`
- `0x180028200`
- `0x18002832c`
- `0x1800288a0`
- `0x180032c20`
- `0x180048304`
- `0x180050b30`
- `0x18005bce8`
- `0x180069998`
- `0x180069c28`
- `0x180097c6c`
- `0x180097cb4`
- `0x18009982c`
- `0x1800a3630`
- `0x1800a6408`
- `0x1800a7624`
- `0x1800c40f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a36d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a3786`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a36d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a3786`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a37d2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a3a2a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a3b96`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a37d2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a3a2a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a3b96`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a3b40`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a3bcc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a3b40`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a3bcc`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800a3722`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800a3722`

## string_xrefs

- `0x1800a3905`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a39a2`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a3aa0`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a3b4e`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a3c11`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a3c39`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a3c5d`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a3c7f`: `onecore\ds\security\devicecredential\service\lib\devicecredentialclass.cpp`
- `0x1800a3801`: `UserSid`
- `0x1800a3b27`: `ProtocolVersion`

## pseudocode

```c
__int64 __fastcall DcaMgr::DeviceCredential::LoadNextCredential(DcaMgr::DeviceCredential *this)
{
  unsigned int i; // r14d
  const WCHAR *v3; // rdx
  HKEY v4; // rcx
  LSTATUS v5; // ebx
  char *v6; // r15
  unsigned int v7; // eax
  unsigned __int16 *v8; // rax
  __int64 v9; // r8
  int v10; // ecx
  int v11; // edx
  const WCHAR *v12; // rdx
  HKEY v13; // rcx
  unsigned int v14; // ebx
  const char *v15; // r9
  int v16; // esi
  int RegStringValue; // ebx
  unsigned __int16 *v18; // rax
  int v19; // ecx
  int v20; // edx
  unsigned __int16 **v21; // rcx
  unsigned __int16 *v22; // rax
  int v23; // ecx
  int v24; // r8d
  unsigned __int16 **v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rdx
  HKEY v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rcx
  void *v31; // rdx
  unsigned int ValueW; // eax
  HKEY v33; // rcx
  __int64 v34; // rcx
  void *v35; // rdx
  int v37; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-49h]
  int phkResulta; // [rsp+20h] [rbp-49h]
  unsigned int phkResultb; // [rsp+20h] [rbp-49h]
  DWORD cchName; // [rsp+40h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-21h] BYREF
  void *v43; // [rsp+50h] [rbp-19h] BYREF
  unsigned __int16 *v44; // [rsp+58h] [rbp-11h] BYREF
  unsigned __int16 *v45; // [rsp+60h] [rbp-9h] BYREF
  HKEY *p_hKey; // [rsp+68h] [rbp-1h] BYREF
  HKEY v47; // [rsp+70h] [rbp+7h] BYREF
  char v48; // [rsp+78h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  DWORD cbData; // [rsp+D0h] [rbp+67h] BYREF
  int Data; // [rsp+D8h] [rbp+6Fh] BYREF
  int v52; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v53; // [rsp+E8h] [rbp+7Fh] BYREF

  for ( i = *((_DWORD *)this + 20); ; ++i )
  {
    if ( i > *((_DWORD *)this + 21) )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x5C9,
               (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
               (const char *)0x103,
               phkResult);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      this,
      0);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      (char *)this + 8,
      0);
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset((char *)this + 40);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      (char *)this + 16,
      0);
    cchName = *((_DWORD *)this + 26);
    hKey = 0;
    if ( !*((_BYTE *)this + 88) )
    {
      v3 = (const WCHAR *)*((_QWORD *)this + 14);
      if ( v3 )
        break;
    }
    v7 = RegEnumKeyExW(*((HKEY *)this + 15), i - 1, *((LPWSTR *)this + 12), &cchName, 0, 0, 0, 0);
    if ( v7 )
    {
      v27 = 1315;
      goto LABEL_66;
    }
    v8 = (unsigned __int16 *)*((_QWORD *)this + 14);
    if ( !v8 )
      goto LABEL_13;
    v9 = *((_QWORD *)this + 12) - (_QWORD)v8;
    do
    {
      v10 = *(unsigned __int16 *)((char *)v8 + v9);
      v11 = *v8 - v10;
      if ( v11 )
        break;
      ++v8;
    }
    while ( v10 );
    if ( v11 )
    {
LABEL_13:
      v12 = (const WCHAR *)*((_QWORD *)this + 12);
      v13 = (HKEY)*((_QWORD *)this + 15);
      p_hKey = &hKey;
      v47 = 0;
      v48 = 1;
      v14 = RegOpenKeyExW(v13, v12, 0, 0x20019u, &v47);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
      v6 = (char *)*((_QWORD *)this + 12);
      if ( !v14 )
        goto LABEL_14;
      v37 = wil::details::in1diag3::Return_Win32Msg(
              retaddr,
              (void *)0x532,
              (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
              (const char *)v14,
              (unsigned int)"DeviceId=%ws",
              *((const char **)this + 12));
LABEL_67:
      RegStringValue = v37;
      goto LABEL_68;
    }
LABEL_33:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  v4 = (HKEY)*((_QWORD *)this + 15);
  p_hKey = &hKey;
  *((_BYTE *)this + 88) = 1;
  --i;
  v47 = 0;
  v48 = 1;
  v5 = RegOpenKeyExW(v4, v3, 0, 0x20019u, &v47);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( v5 )
    goto LABEL_33;
  v6 = (char *)*((_QWORD *)this + 14);
LABEL_14:
  cbData = 4;
  Data = 0;
  v7 = RegQueryValueExW(hKey, L"State", 0, 0, (LPBYTE)&Data, &cbData);
  if ( v7 )
  {
    v27 = 1342;
LABEL_66:
    v37 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v27,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
            (const char *)v7,
            phkResult);
    goto LABEL_67;
  }
  v16 = Data;
  if ( Data == 3 )
    goto LABEL_33;
  if ( !*((_DWORD *)this + 15) )
  {
    p_hKey = (HKEY *)&v44;
    v44 = 0;
    v47 = 0;
    v48 = 1;
    RegStringValue = ReadRegStringValue(hKey, 0, L"UserSid");
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hKey);
    if ( RegStringValue < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x54C,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
        (const char *)(unsigned int)RegStringValue,
        phkResult);
      v25 = &v44;
      goto LABEL_35;
    }
    v18 = v44;
    do
    {
      v19 = *(unsigned __int16 *)((char *)v18 + *((_QWORD *)this + 8) - (_QWORD)v44);
      v20 = *v18 - v19;
      if ( v20 )
        break;
      ++v18;
    }
    while ( v19 );
    v21 = &v44;
    if ( v20 )
      goto LABEL_32;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v44);
  }
  if ( *((_DWORD *)this + 15) > 1u )
    goto LABEL_37;
  p_hKey = (HKEY *)&v45;
  v45 = 0;
  v47 = 0;
  v48 = 1;
  RegStringValue = ReadRegStringValue(hKey, 0, L"AppId");
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hKey);
  if ( RegStringValue < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55C,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)(unsigned int)RegStringValue,
      phkResult);
    v25 = &v45;
LABEL_35:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v25);
LABEL_68:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return (unsigned int)RegStringValue;
  }
  v22 = v45;
  do
  {
    v23 = *(unsigned __int16 *)((char *)v22 + *((_QWORD *)this + 9) - (_QWORD)v45);
    v24 = *v22 - v23;
    if ( v24 )
      break;
    ++v22;
  }
  while ( v23 );
  if ( v24 && wcscmp_0(L"windows.immersivecontrolpanel_cw5n1h2txyewy", *((const wchar_t **)this + 9)) || v16 != 1 )
  {
    v21 = &v45;
LABEL_32:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v21);
    goto LABEL_33;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v45);
LABEL_37:
  *((_DWORD *)this + 6) = v16;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v53,
    v6,
    0xFFFFFFFFFFFFFFFFuLL,
    v15);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    this,
    &v53);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v53);
  if ( !*(_QWORD *)this )
  {
    RegStringValue = -2147024882;
    v26 = 1386;
    goto LABEL_62;
  }
  p_hKey = (HKEY *)((char *)this + 8);
  v47 = 0;
  v48 = 1;
  RegStringValue = ReadRegStringValue(hKey, 0, L"FriendlyName");
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hKey);
  if ( RegStringValue < 0 )
  {
    v26 = 1392;
LABEL_62:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
      (const char *)(unsigned int)RegStringValue,
      phkResult);
    goto LABEL_68;
  }
  p_hKey = (HKEY *)((char *)this + 16);
  v47 = 0;
  v48 = 1;
  RegStringValue = ReadRegStringValue(hKey, 0, L"ModelNumber");
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hKey);
  if ( RegStringValue < 0 )
  {
    v26 = 1398;
    goto LABEL_62;
  }
  v52 = 0;
  cbData = 4;
  v7 = RegQueryValueExW(hKey, L"DeviceCapability", 0, 0, (LPBYTE)&v52, &cbData);
  if ( v7 )
  {
    v27 = 1408;
    goto LABEL_66;
  }
  v28 = hKey;
  *((_DWORD *)this + 7) = v52;
  p_hKey = (HKEY *)&v43;
  v43 = 0;
  LODWORD(v53) = 0;
  v47 = 0;
  v48 = 1;
  RegStringValue = ReadRegBinaryValue(v28, &v53);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_hKey);
  if ( (int)(RegStringValue + 0x80000000) >= 0 && RegStringValue != -2147024894 )
  {
    v29 = 1420;
    goto LABEL_48;
  }
  *((_DWORD *)this + 12) = 0;
  if ( RegStringValue >= 0 )
  {
    p_hKey = (HKEY *)((char *)this + 40);
    v47 = 0;
    v48 = 1;
    RegStringValue = DpapiProtectUnprotect(0, (_DWORD)v43, v53, (unsigned int)&v47, (__int64)this + 48);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_hKey);
    if ( RegStringValue < 0 )
    {
      v29 = 1430;
LABEL_48:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
        (const char *)(unsigned int)RegStringValue,
        phkResulta);
LABEL_49:
      v31 = v43;
      v43 = 0;
      if ( v31 )
        wil::hlocal_secure_deleter::operator()<unsigned char>(v30, v31);
      goto LABEL_68;
    }
  }
  cbData = 4;
  ValueW = RegGetValueW(hKey, 0, L"ProtocolVersion", 0x10u, 0, (char *)this + 32, &cbData);
  if ( ValueW )
  {
    RegStringValue = wil::details::in1diag3::Return_Win32(
                       retaddr,
                       (void *)0x5A1,
                       (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialclass.cpp",
                       (const char *)ValueW,
                       phkResultb);
    goto LABEL_49;
  }
  v33 = hKey;
  *((_DWORD *)this + 13) = 0;
  Data = 0;
  cbData = 4;
  if ( RegQueryValueExW(v33, L"PresenceMonitoringMode", 0, 0, (LPBYTE)&Data, &cbData) >= 0 )
    *((_DWORD *)this + 13) = Data;
  *((_BYTE *)this + 56) = RegGetValueW(hKey, 0, L"AuthKey", 8u, 0, 0, &cbData) == 0;
  v35 = v43;
  *((_DWORD *)this + 20) = i + 1;
  v43 = 0;
  if ( v35 )
    wil::hlocal_secure_deleter::operator()<unsigned char>(v34, v35);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x1800a3630  push    rbp
0x1800a3632  push    rbx
0x1800a3633  push    rsi
0x1800a3634  push    rdi
0x1800a3635  push    r12
0x1800a3637  push    r13
0x1800a3639  push    r14
0x1800a363b  push    r15
0x1800a363d  lea     rbp, [rsp-1Fh]
0x1800a3642  sub     rsp, 88h
0x1800a3649  mov     r14d, [rcx+50h]
0x1800a364d  mov     rdi, rcx
0x1800a3650  xor     ebx, ebx
0x1800a3652  cmp     r14d, [rdi+54h]
0x1800a3656  ja      loc_1800A3C7B
0x1800a365c  xor     edx, edx
0x1800a365e  mov     rcx, rdi
0x1800a3661  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a3666  lea     r12, [rdi+8]
0x1800a366a  xor     edx, edx
0x1800a366c  mov     rcx, r12
0x1800a366f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a3674  lea     rcx, [rdi+28h]
0x1800a3678  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a367d  lea     r13, [rdi+10h]
0x1800a3681  xor     edx, edx
0x1800a3683  mov     rcx, r13
0x1800a3686  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a368b  mov     eax, [rdi+68h]
0x1800a368e  mov     [rbp+57h+cchName], eax
0x1800a3691  mov     [rbp+57h+hKey], rbx
0x1800a3695  cmp     [rdi+58h], bl
0x1800a3698  jnz     short loc_1800A36FE
0x1800a369a  mov     rdx, [rdi+70h]; lpSubKey
0x1800a369e  test    rdx, rdx
0x1800a36a1  jz      short loc_1800A36FE
0x1800a36a3  mov     rcx, [rdi+78h]; hKey
0x1800a36a7  lea     rax, [rbp+57h+hKey]
0x1800a36ab  mov     [rbp+57h+var_58], rax
0x1800a36af  mov     r9d, 20019h; samDesired
0x1800a36b5  lea     rax, [rbp+57h+var_50]
0x1800a36b9  mov     byte ptr [rdi+58h], 1
0x1800a36bd  xor     r8d, r8d; ulOptions
0x1800a36c0  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800a36c5  dec     r14d
0x1800a36c8  mov     [rbp+57h+var_50], rbx
0x1800a36cc  mov     [rbp+57h+var_48], 1
0x1800a36d0  call    cs:__imp_RegOpenKeyExW
0x1800a36d6  lea     rcx, [rbp+57h+var_58]
0x1800a36da  mov     ebx, eax
0x1800a36dc  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800a36e1  test    ebx, ebx
0x1800a36e3  jz      short loc_1800A36F5
0x1800a36e5  lea     rcx, [rbp+57h+hKey]
0x1800a36e9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a36ee  xor     ebx, ebx
0x1800a36f0  jmp     loc_1800A38F9
0x1800a36f5  mov     r15, [rdi+70h]
0x1800a36f9  jmp     loc_1800A37A3
0x1800a36fe  mov     r8, [rdi+60h]; lpName
0x1800a3702  lea     edx, [r14-1]; dwIndex
0x1800a3706  mov     rcx, [rdi+78h]; hKey
0x1800a370a  lea     r9, [rbp+57h+cchName]; lpcchName
0x1800a370e  mov     [rsp+0C0h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x1800a3713  mov     [rsp+0C0h+lpcchClass], rbx; lpcchClass
0x1800a3718  mov     [rsp+0C0h+lpClass], rbx; lpClass
0x1800a371d  mov     [rsp+0C0h+phkResult], rbx; unsigned int
0x1800a3722  call    cs:__imp_RegEnumKeyExW
0x1800a3728  test    eax, eax
0x1800a372a  jnz     loc_1800A3C54
0x1800a3730  mov     rax, [rdi+70h]
0x1800a3734  test    rax, rax
0x1800a3737  jz      short loc_1800A375C
0x1800a3739  mov     r8, [rdi+60h]
0x1800a373d  sub     r8, rax
0x1800a3740  movzx   edx, word ptr [rax]
0x1800a3743  movzx   ecx, word ptr [rax+r8]
0x1800a3748  sub     edx, ecx
0x1800a374a  jnz     short loc_1800A3754
0x1800a374c  add     rax, 2
0x1800a3750  test    ecx, ecx
0x1800a3752  jnz     short loc_1800A3740
0x1800a3754  test    edx, edx
0x1800a3756  jz      loc_1800A38F0
0x1800a375c  mov     rdx, [rdi+60h]; lpSubKey
0x1800a3760  lea     rax, [rbp+57h+hKey]
0x1800a3764  mov     rcx, [rdi+78h]; hKey
0x1800a3768  mov     r9d, 20019h; samDesired
0x1800a376e  mov     [rbp+57h+var_58], rax
0x1800a3772  xor     r8d, r8d; ulOptions
0x1800a3775  lea     rax, [rbp+57h+var_50]
0x1800a3779  mov     [rbp+57h+var_50], rbx
0x1800a377d  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800a3782  mov     [rbp+57h+var_48], 1
0x1800a3786  call    cs:__imp_RegOpenKeyExW
0x1800a378c  lea     rcx, [rbp+57h+var_58]
0x1800a3790  mov     ebx, eax
0x1800a3792  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800a3797  mov     r15, [rdi+60h]
0x1800a379b  test    ebx, ebx
0x1800a379d  jnz     loc_1800A3C29
0x1800a37a3  mov     rcx, [rbp+57h+hKey]; hKey
0x1800a37a7  lea     rax, [rbp+57h+cbData]
0x1800a37ab  mov     [rsp+0C0h+lpClass], rax; lpcbData
0x1800a37b0  lea     rdx, aState; "State"
0x1800a37b7  lea     rax, [rbp+57h+Data]
0x1800a37bb  mov     [rbp+57h+cbData], 4
0x1800a37c2  xor     ebx, ebx
0x1800a37c4  mov     [rsp+0C0h+phkResult], rax; int
0x1800a37c9  xor     r9d, r9d; lpType
0x1800a37cc  mov     [rbp+57h+Data], ebx
0x1800a37cf  xor     r8d, r8d; lpReserved
0x1800a37d2  call    cs:__imp_RegQueryValueExW
0x1800a37d8  test    eax, eax
0x1800a37da  jnz     loc_1800A3C22
0x1800a37e0  mov     esi, [rbp+57h+Data]
0x1800a37e3  cmp     esi, 3
0x1800a37e6  jz      loc_1800A38F0
0x1800a37ec  cmp     [rdi+3Ch], ebx
0x1800a37ef  jnz     short loc_1800A3860
0x1800a37f1  mov     rcx, [rbp+57h+hKey]; hkey
0x1800a37f5  lea     rax, [rbp+57h+var_68]
0x1800a37f9  lea     r9, [rbp+57h+var_50]
0x1800a37fd  mov     [rbp+57h+var_58], rax
0x1800a3801  lea     r8, aUsersid; "UserSid"
0x1800a3808  mov     [rbp+57h+var_68], rbx
0x1800a380c  xor     edx, edx; lpSubKey
0x1800a380e  mov     [rbp+57h+var_50], rbx
0x1800a3812  mov     [rbp+57h+var_48], 1
0x1800a3816  call    ReadRegStringValue
0x1800a381b  lea     rcx, [rbp+57h+var_58]
0x1800a381f  mov     ebx, eax
0x1800a3821  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800a3826  test    ebx, ebx
0x1800a3828  js      loc_1800A3901
0x1800a382e  mov     rax, [rbp+57h+var_68]
0x1800a3832  mov     r8, [rdi+40h]
0x1800a3836  sub     r8, rax
0x1800a3839  movzx   edx, word ptr [rax]
0x1800a383c  movzx   ecx, word ptr [rax+r8]
0x1800a3841  sub     edx, ecx
0x1800a3843  jnz     short loc_1800A384D
0x1800a3845  add     rax, 2
0x1800a3849  test    ecx, ecx
0x1800a384b  jnz     short loc_1800A3839
0x1800a384d  xor     ebx, ebx
0x1800a384f  lea     rcx, [rbp+57h+var_68]; void *
0x1800a3853  test    edx, edx
0x1800a3855  jnz     loc_1800A38EB
0x1800a385b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a3860  cmp     dword ptr [rdi+3Ch], 1
0x1800a3864  ja      loc_1800A3930
0x1800a386a  mov     rcx, [rbp+57h+hKey]; hkey
0x1800a386e  lea     rax, [rbp+57h+var_60]
0x1800a3872  lea     r9, [rbp+57h+var_50]
0x1800a3876  mov     [rbp+57h+var_58], rax
0x1800a387a  lea     r8, aAppid; "AppId"
0x1800a3881  mov     [rbp+57h+var_60], rbx
0x1800a3885  xor     edx, edx; lpSubKey
0x1800a3887  mov     [rbp+57h+var_50], rbx
0x1800a388b  mov     [rbp+57h+var_48], 1
0x1800a388f  call    ReadRegStringValue
0x1800a3894  lea     rcx, [rbp+57h+var_58]
0x1800a3898  mov     ebx, eax
0x1800a389a  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800a389f  test    ebx, ebx
0x1800a38a1  js      loc_1800A399E
0x1800a38a7  mov     rdx, [rdi+48h]; String2
0x1800a38ab  mov     rax, [rbp+57h+var_60]
0x1800a38af  mov     r9, rdx
0x1800a38b2  sub     r9, rax
0x1800a38b5  movzx   r8d, word ptr [rax]
0x1800a38b9  movzx   ecx, word ptr [rax+r9]
0x1800a38be  sub     r8d, ecx
0x1800a38c1  jnz     short loc_1800A38CB
0x1800a38c3  add     rax, 2
0x1800a38c7  test    ecx, ecx
0x1800a38c9  jnz     short loc_1800A38B5
0x1800a38cb  xor     ebx, ebx
0x1800a38cd  test    r8d, r8d
0x1800a38d0  jz      short loc_1800A38E2
0x1800a38d2  lea     rcx, aWindowsImmersi; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x1800a38d9  call    wcscmp_0
0x1800a38de  test    eax, eax
0x1800a38e0  jnz     short loc_1800A38E7
0x1800a38e2  cmp     esi, 1
0x1800a38e5  jz      short loc_1800A3927
0x1800a38e7  lea     rcx, [rbp+57h+var_60]; void *
0x1800a38eb  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a38f0  lea     rcx, [rbp+57h+hKey]
0x1800a38f4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a38f9  inc     r14d
0x1800a38fc  jmp     loc_1800A3652
0x1800a3901  mov     rcx, [rbp+5Fh]; this
0x1800a3905  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800a390c  mov     r9d, ebx; char *
0x1800a390f  mov     edx, 54Ch; void *
0x1800a3914  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3919  lea     rcx, [rbp+57h+var_68]; void *
0x1800a391d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a3922  jmp     loc_1800A3C6E
0x1800a3927  lea     rcx, [rbp+57h+var_60]; void *
0x1800a392b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a3930  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800a3934  mov     [rdi+18h], esi
0x1800a3937  mov     rdx, r15
0x1800a393a  lea     rcx, [rbp+57h+arg_18]
0x1800a393e  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a3943  lea     rdx, [rbp+57h+arg_18]
0x1800a3947  mov     rcx, rdi
0x1800a394a  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800a394f  lea     rcx, [rbp+57h+arg_18]; void *
0x1800a3953  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a3958  xor     esi, esi
0x1800a395a  cmp     [rdi], rsi
0x1800a395d  jz      loc_1800A3C03
0x1800a3963  mov     rcx, [rbp+57h+hKey]; hkey
0x1800a3967  lea     r9, [rbp+57h+var_50]
0x1800a396b  lea     r8, aFriendlyname; "FriendlyName"
0x1800a3972  mov     [rbp+57h+var_58], r12
0x1800a3976  xor     edx, edx; lpSubKey
0x1800a3978  mov     [rbp+57h+var_50], rsi
0x1800a397c  mov     [rbp+57h+var_48], 1
0x1800a3980  call    ReadRegStringValue
0x1800a3985  lea     rcx, [rbp+57h+var_58]
0x1800a3989  mov     ebx, eax
0x1800a398b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800a3990  test    ebx, ebx
0x1800a3992  jns     short loc_1800A39BF
0x1800a3994  mov     edx, 570h
0x1800a3999  jmp     loc_1800A3C0D
0x1800a399e  mov     rcx, [rbp+5Fh]; this
0x1800a39a2  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800a39a9  mov     r9d, ebx; char *
0x1800a39ac  mov     edx, 55Ch; void *
0x1800a39b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a39b6  lea     rcx, [rbp+57h+var_60]
0x1800a39ba  jmp     loc_1800A391D
0x1800a39bf  mov     rcx, [rbp+57h+hKey]; hkey
0x1800a39c3  lea     r9, [rbp+57h+var_50]
0x1800a39c7  lea     r8, aModelnumber; "ModelNumber"
0x1800a39ce  mov     [rbp+57h+var_58], r13
0x1800a39d2  xor     edx, edx; lpSubKey
0x1800a39d4  mov     [rbp+57h+var_50], rsi
0x1800a39d8  mov     [rbp+57h+var_48], 1
0x1800a39dc  call    ReadRegStringValue
0x1800a39e1  lea     rcx, [rbp+57h+var_58]
0x1800a39e5  mov     ebx, eax
0x1800a39e7  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800a39ec  test    ebx, ebx
0x1800a39ee  jns     short loc_1800A39FA
0x1800a39f0  mov     edx, 576h
0x1800a39f5  jmp     loc_1800A3C0D
0x1800a39fa  mov     rcx, [rbp+57h+hKey]; hKey
0x1800a39fe  lea     rax, [rbp+57h+cbData]
0x1800a3a02  mov     [rsp+0C0h+lpClass], rax; lpcbData
0x1800a3a07  lea     rdx, aDevicecapabili; "DeviceCapability"
0x1800a3a0e  lea     rax, [rbp+57h+arg_10]
0x1800a3a12  mov     [rbp+57h+arg_10], esi
0x1800a3a15  mov     r15d, 4
0x1800a3a1b  mov     [rsp+0C0h+phkResult], rax; lpData
0x1800a3a20  xor     r9d, r9d; lpType
0x1800a3a23  mov     [rbp+57h+cbData], r15d
0x1800a3a27  xor     r8d, r8d; lpReserved
0x1800a3a2a  call    cs:__imp_RegQueryValueExW
0x1800a3a30  test    eax, eax
0x1800a3a32  jz      short loc_1800A3A3E
0x1800a3a34  mov     edx, 580h
0x1800a3a39  jmp     loc_1800A3C59
0x1800a3a3e  mov     eax, [rbp+57h+arg_10]
0x1800a3a41  lea     r9, [rbp+57h+var_50]
0x1800a3a45  mov     rcx, [rbp+57h+hKey]; hkey
0x1800a3a49  lea     r8, aOpaqueblob; "OpaqueBlob"
0x1800a3a50  mov     [rdi+1Ch], eax
0x1800a3a53  lea     rax, [rbp+57h+var_70]
0x1800a3a57  mov     [rbp+57h+var_58], rax
0x1800a3a5b  lea     rax, [rbp+57h+arg_18]
0x1800a3a5f  mov     [rsp+0C0h+phkResult], rax; int
0x1800a3a64  mov     [rbp+57h+var_70], rsi
0x1800a3a68  mov     dword ptr [rbp+57h+arg_18], esi
0x1800a3a6b  mov     [rbp+57h+var_50], rsi
0x1800a3a6f  mov     [rbp+57h+var_48], 1
0x1800a3a73  call    ReadRegBinaryValue
0x1800a3a78  lea     rcx, [rbp+57h+var_58]
0x1800a3a7c  mov     ebx, eax
0x1800a3a7e  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
0x1800a3a83  mov     eax, 80000000h
0x1800a3a88  lea     ecx, [rbx+rax]
0x1800a3a8b  test    eax, ecx
0x1800a3a8d  jnz     short loc_1800A3ACA
0x1800a3a8f  cmp     ebx, 80070002h
0x1800a3a95  jz      short loc_1800A3ACA
0x1800a3a97  mov     edx, 58Ch; void *
0x1800a3a9c  mov     rcx, [rbp+5Fh]; this
0x1800a3aa0  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\devicecredential"...
0x1800a3aa7  mov     r9d, ebx; char *
0x1800a3aaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3aaf  mov     rdx, [rbp+57h+var_70]
0x1800a3ab3  mov     [rbp+57h+var_70], rsi
0x1800a3ab7  test    rdx, rdx
  ... truncated ...
```
