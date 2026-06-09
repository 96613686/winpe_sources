# DcaMgr::DeviceCredentialPresenceMonitoring::RegisterOnExistingDevice(ushort const *,ushort const *,_DevicePresenceMonitoringMode)

- ea: `0x1800a4c30`
- end: `0x1800a5003`
- name: `?RegisterOnExistingDevice@DeviceCredentialPresenceMonitoring@DcaMgr@@SAJPEBG0W4_DevicePresenceMonitoringMode@@@Z`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009fc30`

## callees

- `0x18000782c`
- `0x18000926c`
- `0x1800281e0`
- `0x1800323d0`
- `0x180032c20`
- `0x180048304`
- `0x1800535f4`
- `0x18005b5e0`
- `0x18005cee0`
- `0x180097c6c`
- `0x180097cb4`
- `0x180098cfc`
- `0x1800a41ac`
- `0x1800a4444`
- `0x1800a447c`
- `0x1800a4c30`
- `0x1800a5164`
- `0x1800a6d30`
- `0x1800a7b74`
- `0x1800a7bd4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a4e4b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a4e4b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a4eb0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a4eb0`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800a4f5b`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800a4f5b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a4f19`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a4f19`
- `NaturalAuthClient!CdfPluginRegisterDevice` at `0x1800a4f72`
- `NaturalAuthClient!CdfPluginRegisterDevice` at `0x1800a4f72`

## string_xrefs

- `0x1800a4f32`: `DeviceInstancePath`
- `0x1800a4ca6`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x1800a4d0b`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x1800a4d93`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x1800a4e00`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x1800a4e64`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`

## pseudocode

```c
__int64 __fastcall DcaMgr::DeviceCredentialPresenceMonitoring::RegisterOnExistingDevice(
        const WCHAR *a1,
        const void *a2,
        int a3)
{
  int UserSidAndPackageInfoFromToken; // ebx
  __int64 v7; // rdx
  __int64 v8; // r9
  int v9; // eax
  int v10; // ecx
  HKEY *v11; // r8
  __int64 v12; // rdx
  unsigned __int64 v13; // r9
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r9
  const unsigned __int16 *v17; // r9
  int v18; // eax
  int v19; // eax
  __int64 v20; // rdx
  unsigned int lpData; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v24; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE TokenHandle; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v26; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[4]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-9Ch] BYREF
  void *p_TokenHandle; // [rsp+68h] [rbp-98h] BYREF
  HANDLE v30; // [rsp+70h] [rbp-90h] BYREF
  char v31; // [rsp+78h] [rbp-88h]
  void *p_hKey; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v33[4]; // [rsp+88h] [rbp-78h] BYREF
  char v34; // [rsp+90h] [rbp-70h]
  _BYTE v35[336]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  DevCredSvcTraceLoggingProvider::RegisterPresenceMonitoring::Start<>((DevCredSvcTraceLoggingProvider::RegisterPresenceMonitoring *)v35);
  if ( a3 )
  {
    v9 = ValidateInputString(a1, 40);
    UserSidAndPackageInfoFromToken = v9;
    if ( v9 < 0 )
    {
      v7 = 266;
LABEL_5:
      v8 = (unsigned int)v9;
      goto LABEL_6;
    }
    v9 = ValidateInputString(a2, 512);
    UserSidAndPackageInfoFromToken = v9;
    if ( v9 < 0 )
    {
      v7 = 270;
      goto LABEL_5;
    }
    TokenHandle = 0;
    p_TokenHandle = &TokenHandle;
    v30 = 0;
    v31 = 1;
    UserSidAndPackageInfoFromToken = OpenCallerImpersonationToken(v10, &v30);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_TokenHandle);
    if ( UserSidAndPackageInfoFromToken < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x113,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialpresence.cpp",
        (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
        lpData);
LABEL_11:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      goto LABEL_37;
    }
    p_hKey = &v24;
    v26 = 0;
    p_TokenHandle = &v26;
    v24 = 0;
    *(_QWORD *)v33 = 0;
    v34 = 1;
    v30 = 0;
    v31 = 1;
    UserSidAndPackageInfoFromToken = GetUserSidAndPackageInfoFromToken(TokenHandle, &v30, (WCHAR **)v33, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_TokenHandle);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hKey);
    if ( UserSidAndPackageInfoFromToken < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11A,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialpresence.cpp",
        (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
        lpData);
LABEL_14:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v24);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v26);
      goto LABEL_11;
    }
    hKey = 0;
    p_hKey = &hKey;
    *(_QWORD *)v33 = 0;
    v34 = 1;
    UserSidAndPackageInfoFromToken = DcaMgr::OpenDeviceRegKey(a1, v33, v11);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    if ( UserSidAndPackageInfoFromToken < 0 )
    {
      v12 = 285;
LABEL_17:
      v13 = (unsigned int)UserSidAndPackageInfoFromToken;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialpresence.cpp",
        (const char *)v13,
        lpData);
LABEL_19:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_14;
    }
    *(_DWORD *)Data = 0;
    cbData = 4;
    v14 = RegQueryValueExW(hKey, L"State", 0, 0, Data, &cbData);
    if ( v14 )
    {
      v15 = 295;
    }
    else
    {
      if ( *(_DWORD *)Data != 1 )
      {
        v16 = 13;
        v15 = 299;
        goto LABEL_23;
      }
      if ( RegGetValueW(hKey, 0, L"AuthKey", 8u, 0, 0, &cbData) )
      {
        v16 = 183;
        v15 = 312;
        goto LABEL_23;
      }
      v18 = DcaMgr::ValidateOwnership(hKey, v26, v24, v17);
      UserSidAndPackageInfoFromToken = v18;
      if ( v18 < 0 )
      {
        v13 = (unsigned int)v18;
        v12 = 318;
        goto LABEL_18;
      }
      *(_DWORD *)Data = a3;
      v14 = RegSetValueExW(hKey, L"PresenceMonitoringMode", 0, 4u, Data, 4u);
      if ( !v14 )
      {
        v19 = WriteRegStringValue(hKey, 0, (char *)L"DeviceInstancePath", a2);
        UserSidAndPackageInfoFromToken = v19;
        if ( v19 < 0 )
        {
          v13 = (unsigned int)v19;
          v12 = 333;
          goto LABEL_18;
        }
        RegFlushKey(hKey);
        hKey = 0;
        UserSidAndPackageInfoFromToken = CdfPluginRegisterDevice(a2, a3 != 1);
        if ( UserSidAndPackageInfoFromToken >= 0 )
        {
          LOBYTE(v20) = 1;
          DevCredSvcTraceLoggingProvider::RegisterPresenceMonitoring::Stop(v35, v20, v24, a1, a3);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v24);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v26);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
          UserSidAndPackageInfoFromToken = 0;
          goto LABEL_37;
        }
        DcaMgr::DeviceCredentialPresenceMonitoring::Unregister(a1);
        v12 = 345;
        goto LABEL_17;
      }
      v15 = 327;
    }
    v16 = v14;
LABEL_23:
    UserSidAndPackageInfoFromToken = wil::details::in1diag3::Return_Win32(
                                       retaddr,
                                       (void *)v15,
                                       (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecreden"
                                                     "tialpresence.cpp",
                                       (const char *)v16,
                                       lpData);
    goto LABEL_19;
  }
  UserSidAndPackageInfoFromToken = -2147024809;
  v7 = 262;
  v8 = 2147942487LL;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialpresence.cpp",
    (const char *)v8,
    lpData);
LABEL_37:
  DevCredSvcTraceLoggingProvider::RegisterPresenceMonitoring::~RegisterPresenceMonitoring((DevCredSvcTraceLoggingProvider::RegisterPresenceMonitoring *)v35);
  return (unsigned int)UserSidAndPackageInfoFromToken;
}

```

## disassembly

```asm
0x1800a4c30  mov     [rsp-8+arg_18], rbx
0x1800a4c35  push    rbp
0x1800a4c36  push    rsi
0x1800a4c37  push    rdi
0x1800a4c38  push    r14
0x1800a4c3a  push    r15
0x1800a4c3c  lea     rbp, [rsp-100h]
0x1800a4c44  sub     rsp, 200h
0x1800a4c4b  mov     rax, cs:__security_cookie
0x1800a4c52  xor     rax, rsp
0x1800a4c55  mov     [rbp+120h+var_30], rax
0x1800a4c5c  mov     rdi, rcx
0x1800a4c5f  mov     esi, r8d
0x1800a4c62  lea     rcx, [rbp+120h+var_180]; this
0x1800a4c66  mov     r14, rdx
0x1800a4c69  call    ??$Start@$$V@RegisterPresenceMonitoring@DevCredSvcTraceLoggingProvider@@SA?AV01@XZ; DevCredSvcTraceLoggingProvider::RegisterPresenceMonitoring::Start<>(void)
0x1800a4c6e  xor     r15d, r15d
0x1800a4c71  test    esi, esi
0x1800a4c73  jnz     short loc_1800A4C84
0x1800a4c75  mov     ebx, 80070057h
0x1800a4c7a  mov     edx, 106h
0x1800a4c7f  mov     r9d, ebx
0x1800a4c82  jmp     short loc_1800A4C9F
0x1800a4c84  mov     edx, 28h ; '('
0x1800a4c89  mov     rcx, rdi
0x1800a4c8c  call    ValidateInputString
0x1800a4c91  mov     ebx, eax
0x1800a4c93  test    eax, eax
0x1800a4c95  jns     short loc_1800A4CB7
0x1800a4c97  mov     edx, 10Ah; void *
0x1800a4c9c  mov     r9d, eax; char *
0x1800a4c9f  mov     rcx, [rbp+128h]; this
0x1800a4ca6  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x1800a4cad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4cb2  jmp     loc_1800A4FD2
0x1800a4cb7  mov     edx, 200h
0x1800a4cbc  mov     rcx, r14
0x1800a4cbf  call    ValidateInputString
0x1800a4cc4  mov     ebx, eax
0x1800a4cc6  test    eax, eax
0x1800a4cc8  jns     short loc_1800A4CD1
0x1800a4cca  mov     edx, 10Eh
0x1800a4ccf  jmp     short loc_1800A4C9C
0x1800a4cd1  lea     rax, [rsp+220h+TokenHandle]
0x1800a4cd6  mov     [rsp+220h+TokenHandle], r15
0x1800a4cdb  lea     rdx, [rsp+220h+var_1B0]
0x1800a4ce0  mov     [rsp+220h+var_1B8], rax
0x1800a4ce5  mov     [rsp+220h+var_1B0], r15
0x1800a4cea  mov     [rsp+220h+var_1A8], 1
0x1800a4cef  call    OpenCallerImpersonationToken
0x1800a4cf4  lea     rcx, [rsp+220h+var_1B8]
0x1800a4cf9  mov     ebx, eax
0x1800a4cfb  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800a4d00  test    ebx, ebx
0x1800a4d02  jns     short loc_1800A4D2E
0x1800a4d04  mov     rcx, [rbp+128h]; this
0x1800a4d0b  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x1800a4d12  mov     r9d, ebx; char *
0x1800a4d15  mov     edx, 113h; void *
0x1800a4d1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4d1f  lea     rcx, [rsp+220h+TokenHandle]
0x1800a4d24  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a4d29  jmp     loc_1800A4FD2
0x1800a4d2e  mov     rcx, [rsp+220h+TokenHandle]; TokenHandle
0x1800a4d33  lea     rax, [rsp+220h+var_1D8]
0x1800a4d38  mov     [rbp+120h+var_1A0], rax
0x1800a4d3c  lea     r8, [rbp+120h+var_198]
0x1800a4d40  lea     rax, [rsp+220h+var_1C8]
0x1800a4d45  mov     [rsp+220h+var_1C8], r15
0x1800a4d4a  xor     r9d, r9d
0x1800a4d4d  mov     [rsp+220h+var_1B8], rax
0x1800a4d52  lea     rdx, [rsp+220h+var_1B0]
0x1800a4d57  mov     [rsp+220h+var_1D8], r15
0x1800a4d5c  mov     qword ptr [rbp+120h+var_198], r15
0x1800a4d60  mov     [rbp+120h+var_190], 1
0x1800a4d64  mov     [rsp+220h+var_1B0], r15
0x1800a4d69  mov     [rsp+220h+var_1A8], 1
0x1800a4d6e  call    GetUserSidAndPackageInfoFromToken
0x1800a4d73  lea     rcx, [rsp+220h+var_1B8]
0x1800a4d78  mov     ebx, eax
0x1800a4d7a  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800a4d7f  lea     rcx, [rbp+120h+var_1A0]
0x1800a4d83  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800a4d88  test    ebx, ebx
0x1800a4d8a  jns     short loc_1800A4DC0
0x1800a4d8c  mov     rcx, [rbp+128h]; this
0x1800a4d93  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x1800a4d9a  mov     r9d, ebx; char *
0x1800a4d9d  mov     edx, 11Ah; void *
0x1800a4da2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4da7  lea     rcx, [rsp+220h+var_1D8]; void *
0x1800a4dac  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a4db1  lea     rcx, [rsp+220h+var_1C8]; void *
0x1800a4db6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a4dbb  jmp     loc_1800A4D1F
0x1800a4dc0  lea     rax, [rsp+220h+hKey]
0x1800a4dc5  mov     [rsp+220h+hKey], r15
0x1800a4dca  lea     rdx, [rbp+120h+var_198]; unsigned __int16 *
0x1800a4dce  mov     [rbp+120h+var_1A0], rax
0x1800a4dd2  mov     rcx, rdi; lpSubKey
0x1800a4dd5  mov     qword ptr [rbp+120h+var_198], r15
0x1800a4dd9  mov     [rbp+120h+var_190], 1
0x1800a4ddd  call    ?OpenDeviceRegKey@DcaMgr@@YAJPEBGPEAPEAUHKEY__@@@Z; DcaMgr::OpenDeviceRegKey(ushort const *,HKEY__ * *)
0x1800a4de2  lea     rcx, [rbp+120h+var_1A0]
0x1800a4de6  mov     ebx, eax
0x1800a4de8  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800a4ded  test    ebx, ebx
0x1800a4def  jns     short loc_1800A4E18
0x1800a4df1  mov     edx, 11Dh; void *
0x1800a4df6  mov     r9d, ebx; char *
0x1800a4df9  mov     rcx, [rbp+128h]; this
0x1800a4e00  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x1800a4e07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4e0c  lea     rcx, [rsp+220h+hKey]
0x1800a4e11  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a4e16  jmp     short loc_1800A4DA7
0x1800a4e18  mov     rcx, [rsp+220h+hKey]; hKey
0x1800a4e1d  lea     rax, [rsp+220h+cbData]
0x1800a4e22  mov     [rsp+220h+lpcbData], rax; lpcbData
0x1800a4e27  lea     rdx, aState; "State"
0x1800a4e2e  lea     rax, [rsp+220h+Data]
0x1800a4e33  mov     dword ptr [rsp+220h+Data], r15d
0x1800a4e38  xor     r9d, r9d; lpType
0x1800a4e3b  mov     [rsp+220h+lpData], rax; unsigned int
0x1800a4e40  xor     r8d, r8d; lpReserved
0x1800a4e43  mov     [rsp+220h+cbData], 4
0x1800a4e4b  call    cs:__imp_RegQueryValueExW
0x1800a4e51  test    eax, eax
0x1800a4e53  jz      short loc_1800A4E74
0x1800a4e55  mov     edx, 127h; void *
0x1800a4e5a  mov     r9d, eax; char *
0x1800a4e5d  mov     rcx, [rbp+128h]; this
0x1800a4e64  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x1800a4e6b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a4e70  mov     ebx, eax
0x1800a4e72  jmp     short loc_1800A4E0C
0x1800a4e74  cmp     dword ptr [rsp+220h+Data], 1
0x1800a4e79  jz      short loc_1800A4E88
0x1800a4e7b  mov     r9d, 0Dh
0x1800a4e81  mov     edx, 12Bh
0x1800a4e86  jmp     short loc_1800A4E5D
0x1800a4e88  mov     rcx, [rsp+220h+hKey]; hkey
0x1800a4e8d  lea     rax, [rsp+220h+cbData]
0x1800a4e92  mov     [rsp+220h+pcbData], rax; pcbData
0x1800a4e97  lea     r8, aAuthkey; "AuthKey"
0x1800a4e9e  mov     [rsp+220h+lpcbData], r15; pvData
0x1800a4ea3  mov     r9d, 8; dwFlags
0x1800a4ea9  xor     edx, edx; lpSubKey
0x1800a4eab  mov     [rsp+220h+lpData], r15; pdwType
0x1800a4eb0  call    cs:__imp_RegGetValueW
0x1800a4eb6  test    eax, eax
0x1800a4eb8  jz      short loc_1800A4EC7
0x1800a4eba  mov     r9d, 0B7h
0x1800a4ec0  mov     edx, 138h
0x1800a4ec5  jmp     short loc_1800A4E5D
0x1800a4ec7  mov     r8, [rsp+220h+var_1D8]; unsigned __int16 *
0x1800a4ecc  mov     rdx, [rsp+220h+var_1C8]; HKEY
0x1800a4ed1  mov     rcx, [rsp+220h+hKey]; hkey
0x1800a4ed6  call    ?ValidateOwnership@DcaMgr@@YAJPEAUHKEY__@@PEBG1@Z; DcaMgr::ValidateOwnership(HKEY__ *,ushort const *,ushort const *)
0x1800a4edb  mov     ebx, eax
0x1800a4edd  test    eax, eax
0x1800a4edf  jns     short loc_1800A4EEE
0x1800a4ee1  mov     r9d, eax
0x1800a4ee4  mov     edx, 13Eh
0x1800a4ee9  jmp     loc_1800A4DF9
0x1800a4eee  mov     rcx, [rsp+220h+hKey]; hKey
0x1800a4ef3  lea     rax, [rsp+220h+Data]
0x1800a4ef8  mov     dword ptr [rsp+220h+lpcbData], 4; cbData
0x1800a4f00  lea     rdx, aPresencemonito; "PresenceMonitoringMode"
0x1800a4f07  mov     r9d, 4; dwType
0x1800a4f0d  mov     [rsp+220h+lpData], rax; lpData
0x1800a4f12  xor     r8d, r8d; Reserved
0x1800a4f15  mov     dword ptr [rsp+220h+Data], esi
0x1800a4f19  call    cs:__imp_RegSetValueExW
0x1800a4f1f  test    eax, eax
0x1800a4f21  jz      short loc_1800A4F2D
0x1800a4f23  mov     edx, 147h
0x1800a4f28  jmp     loc_1800A4E5A
0x1800a4f2d  mov     rcx, [rsp+220h+hKey]; hKey
0x1800a4f32  lea     r8, aDeviceinstance; "DeviceInstancePath"
0x1800a4f39  mov     r9, r14; lpData
0x1800a4f3c  xor     edx, edx; lpSubKey
0x1800a4f3e  call    WriteRegStringValue
0x1800a4f43  mov     ebx, eax
0x1800a4f45  test    eax, eax
0x1800a4f47  jns     short loc_1800A4F56
0x1800a4f49  mov     r9d, eax
0x1800a4f4c  mov     edx, 14Dh
0x1800a4f51  jmp     loc_1800A4DF9
0x1800a4f56  mov     rcx, [rsp+220h+hKey]; hKey
0x1800a4f5b  call    cs:__imp_RegFlushKey
0x1800a4f61  mov     edx, r15d
0x1800a4f64  mov     [rsp+220h+hKey], r15
0x1800a4f69  cmp     esi, 1
0x1800a4f6c  mov     rcx, r14
0x1800a4f6f  setnz   dl
0x1800a4f72  call    cs:__imp_CdfPluginRegisterDevice
0x1800a4f78  mov     ebx, eax
0x1800a4f7a  test    eax, eax
0x1800a4f7c  jns     short loc_1800A4F90
0x1800a4f7e  mov     rcx, rdi; lpSubKey
0x1800a4f81  call    ?Unregister@DeviceCredentialPresenceMonitoring@DcaMgr@@SAJPEBG@Z; DcaMgr::DeviceCredentialPresenceMonitoring::Unregister(ushort const *)
0x1800a4f86  mov     edx, 159h
0x1800a4f8b  jmp     loc_1800A4DF6
0x1800a4f90  mov     r8, [rsp+220h+var_1D8]
0x1800a4f95  lea     rcx, [rbp+120h+var_180]
0x1800a4f99  mov     r9, rdi
0x1800a4f9c  mov     dword ptr [rsp+220h+lpData], esi
0x1800a4fa0  mov     dl, 1
0x1800a4fa2  call    ?Stop@RegisterPresenceMonitoring@DevCredSvcTraceLoggingProvider@@QEAAX_NPEBG1W4_DevicePresenceMonitoringMode@@@Z; DevCredSvcTraceLoggingProvider::RegisterPresenceMonitoring::Stop(bool,ushort const *,ushort const *,_DevicePresenceMonitoringMode)
0x1800a4fa7  lea     rcx, [rsp+220h+hKey]
0x1800a4fac  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a4fb1  lea     rcx, [rsp+220h+var_1D8]; void *
0x1800a4fb6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a4fbb  lea     rcx, [rsp+220h+var_1C8]; void *
0x1800a4fc0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a4fc5  lea     rcx, [rsp+220h+TokenHandle]
0x1800a4fca  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a4fcf  mov     ebx, r15d
0x1800a4fd2  lea     rcx, [rbp+120h+var_180]; this
0x1800a4fd6  call    ??1RegisterPresenceMonitoring@DevCredSvcTraceLoggingProvider@@QEAA@XZ; DevCredSvcTraceLoggingProvider::RegisterPresenceMonitoring::~RegisterPresenceMonitoring(void)
0x1800a4fdb  mov     eax, ebx
0x1800a4fdd  mov     rcx, [rbp+120h+var_30]
0x1800a4fe4  xor     rcx, rsp; StackCookie
0x1800a4fe7  call    __security_check_cookie
0x1800a4fec  mov     rbx, [rsp+220h+arg_18]
0x1800a4ff4  add     rsp, 200h
0x1800a4ffb  pop     r15
0x1800a4ffd  pop     r14
0x1800a4fff  pop     rdi
0x1800a5000  pop     rsi
0x1800a5001  pop     rbp
0x1800a5002  retn
```
