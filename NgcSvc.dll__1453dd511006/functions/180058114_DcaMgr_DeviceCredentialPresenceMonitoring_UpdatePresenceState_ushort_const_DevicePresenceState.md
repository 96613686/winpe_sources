# DcaMgr::DeviceCredentialPresenceMonitoring::UpdatePresenceState(ushort const *,_DevicePresenceState)

- ea: `0x180058114`
- end: `0x18005849e`
- name: `?UpdatePresenceState@DeviceCredentialPresenceMonitoring@DcaMgr@@SAJPEBGW4_DevicePresenceState@@@Z`
- size: `906`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18009fe80`

## callees

- `0x18000782c`
- `0x18000926c`
- `0x1800281e0`
- `0x1800323d0`
- `0x180032c20`
- `0x180047228`
- `0x1800535f4`
- `0x180058114`
- `0x1800584a4`
- `0x1800584d0`
- `0x18005bce8`
- `0x18005cee0`
- `0x180097a9c`
- `0x180097c6c`
- `0x180097cb4`
- `0x180098cfc`
- `0x1800a41ac`
- `0x1800a50b8`
- `0x1800a6d30`
- `0x1800a7b74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180058326`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180058326`
- `NaturalAuthClient!CdfPluginUpdatePresenceState` at `0x1800583ba`
- `NaturalAuthClient!CdfPluginUpdatePresenceState` at `0x1800583ba`

## string_xrefs

- `0x180058351`: `DeviceInstancePath`
- `0x18005817f`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x1800581dd`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x180058238`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x18005838a`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x1800583cb`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x18005843d`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x180058141`: `UpdatePresenceState`

## pseudocode

```c
__int64 __fastcall DcaMgr::DeviceCredentialPresenceMonitoring::UpdatePresenceState(const WCHAR *a1, unsigned int a2)
{
  int v4; // eax
  HKEY *v5; // r8
  int UserSidAndPackageInfoFromToken; // ebx
  int v7; // ecx
  const unsigned __int16 *v8; // r9
  __int64 v9; // rdx
  int v10; // eax
  unsigned __int64 v11; // r9
  int updated; // eax
  int lpData; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v16; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v18; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v20; // [rsp+58h] [rbp-A8h] BYREF
  void *p_hKey; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v22[4]; // [rsp+68h] [rbp-98h] BYREF
  char v23; // [rsp+70h] [rbp-90h]
  DWORD cbData; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 **v25; // [rsp+80h] [rbp-80h] BYREF
  WCHAR *v26; // [rsp+88h] [rbp-78h] BYREF
  char v27; // [rsp+90h] [rbp-70h]
  _QWORD v28[42]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  wil::ActivityBase<DevCredSvcTraceLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DevCredSvcTraceLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v28,
    "UpdatePresenceState");
  v28[0] = &DevCredSvcTraceLoggingProvider::UpdatePresenceState::`vftable';
  DevCredSvcTraceLoggingProvider::UpdatePresenceState::StartActivity((DevCredSvcTraceLoggingProvider::UpdatePresenceState *)v28);
  v4 = ValidateInputString(a1, 40);
  UserSidAndPackageInfoFromToken = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DA,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialpresence.cpp",
      (const char *)(unsigned int)v4,
      lpData);
    goto LABEL_24;
  }
  hKey = 0;
  p_hKey = &hKey;
  *(_QWORD *)v22 = 0;
  v23 = 1;
  UserSidAndPackageInfoFromToken = DcaMgr::OpenDeviceRegKey(a1, v22, v5);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( UserSidAndPackageInfoFromToken < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DD,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialpresence.cpp",
      (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
      lpData);
LABEL_23:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_24;
  }
  TokenHandle = 0;
  p_hKey = &TokenHandle;
  *(_QWORD *)v22 = 0;
  v23 = 1;
  UserSidAndPackageInfoFromToken = OpenCallerImpersonationToken(v7, (HANDLE *)v22);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_hKey);
  if ( UserSidAndPackageInfoFromToken < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E2,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialpresence.cpp",
      (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
      lpData);
LABEL_22:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    goto LABEL_23;
  }
  v25 = &v16;
  v18 = 0;
  p_hKey = &v18;
  v16 = 0;
  v26 = 0;
  v27 = 1;
  *(_QWORD *)v22 = 0;
  v23 = 1;
  UserSidAndPackageInfoFromToken = GetUserSidAndPackageInfoFromToken(TokenHandle, v22, &v26, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hKey);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v25);
  if ( UserSidAndPackageInfoFromToken < 0 )
  {
    v9 = 489;
LABEL_19:
    v11 = (unsigned int)UserSidAndPackageInfoFromToken;
    goto LABEL_20;
  }
  v10 = DcaMgr::ValidateOwnership(hKey, v18, v16, v8);
  UserSidAndPackageInfoFromToken = v10;
  if ( v10 < 0 )
  {
    v11 = (unsigned int)v10;
    v9 = 494;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialpresence.cpp",
      (const char *)v11,
      lpData);
    goto LABEL_21;
  }
  *(_DWORD *)Data = 0;
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"PresenceMonitoringMode", 0, 0, Data, &cbData) < 0 || *(_DWORD *)Data != 1 )
  {
    UserSidAndPackageInfoFromToken = -2147418113;
    v9 = 512;
    goto LABEL_19;
  }
  v25 = (unsigned __int16 **)&v20;
  v20 = 0;
  v26 = 0;
  v27 = 1;
  UserSidAndPackageInfoFromToken = ReadRegStringValue(hKey, 0, L"DeviceInstancePath");
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v25);
  if ( UserSidAndPackageInfoFromToken < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x208,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialpresence.cpp",
      (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
      lpData);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v20);
LABEL_21:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v16);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v18);
    goto LABEL_22;
  }
  updated = CdfPluginUpdatePresenceState(v20, a2 == 1);
  if ( updated < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x20E,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialpresence.cpp",
      (const char *)(unsigned int)updated,
      lpData);
  DevCredSvcTraceLoggingProvider::UpdatePresenceState::Stop(v28, v16, a1, a2);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v20);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v16);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v18);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  UserSidAndPackageInfoFromToken = 0;
LABEL_24:
  DevCredSvcTraceLoggingProvider::UpdatePresenceState::~UpdatePresenceState((DevCredSvcTraceLoggingProvider::UpdatePresenceState *)v28);
  return (unsigned int)UserSidAndPackageInfoFromToken;
}

```

## disassembly

```asm
0x180058114  mov     [rsp-8+arg_10], rbx
0x180058119  push    rbp
0x18005811a  push    rsi
0x18005811b  push    rdi
0x18005811c  lea     rbp, [rsp-100h]
0x180058124  sub     rsp, 200h
0x18005812b  mov     rax, cs:__security_cookie
0x180058132  xor     rax, rsp
0x180058135  mov     [rbp+110h+var_20], rax
0x18005813c  mov     esi, edx
0x18005813e  mov     rdi, rcx
0x180058141  lea     rdx, aUpdatepresence; "UpdatePresenceState"
0x180058148  lea     rcx, [rbp+110h+var_170]
0x18005814c  call    ??0?$ActivityBase@VDevCredSvcTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DevCredSvcTraceLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DevCredSvcTraceLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180058151  lea     rax, ??_7UpdatePresenceState@DevCredSvcTraceLoggingProvider@@6B@; const DevCredSvcTraceLoggingProvider::UpdatePresenceState::`vftable'
0x180058158  lea     rcx, [rbp+110h+var_170]; this
0x18005815c  mov     [rbp+110h+var_170], rax
0x180058160  call    ?StartActivity@UpdatePresenceState@DevCredSvcTraceLoggingProvider@@QEAAXXZ; DevCredSvcTraceLoggingProvider::UpdatePresenceState::StartActivity(void)
0x180058165  mov     edx, 28h ; '('
0x18005816a  mov     rcx, rdi
0x18005816d  call    ValidateInputString
0x180058172  mov     ebx, eax
0x180058174  test    eax, eax
0x180058176  jns     short loc_180058198
0x180058178  mov     rcx, [rbp+118h]; this
0x18005817f  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x180058186  mov     r9d, eax; char *
0x180058189  mov     edx, 1DAh; void *
0x18005818e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058193  jmp     loc_180058471
0x180058198  lea     rax, [rsp+210h+hKey]
0x18005819d  mov     [rsp+210h+hKey], 0
0x1800581a6  lea     rdx, [rsp+210h+var_1A8]; unsigned __int16 *
0x1800581ab  mov     [rsp+210h+var_1B0], rax
0x1800581b0  mov     rcx, rdi; lpSubKey
0x1800581b3  mov     qword ptr [rsp+210h+var_1A8], 0
0x1800581bc  mov     [rsp+210h+var_1A0], 1
0x1800581c1  call    ?OpenDeviceRegKey@DcaMgr@@YAJPEBGPEAPEAUHKEY__@@@Z; DcaMgr::OpenDeviceRegKey(ushort const *,HKEY__ * *)
0x1800581c6  lea     rcx, [rsp+210h+var_1B0]
0x1800581cb  mov     ebx, eax
0x1800581cd  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800581d2  test    ebx, ebx
0x1800581d4  jns     short loc_1800581F6
0x1800581d6  mov     rcx, [rbp+118h]; this
0x1800581dd  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x1800581e4  mov     r9d, ebx; char *
0x1800581e7  mov     edx, 1DDh; void *
0x1800581ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800581f1  jmp     loc_180058467
0x1800581f6  lea     rax, [rsp+210h+TokenHandle]
0x1800581fb  mov     [rsp+210h+TokenHandle], 0
0x180058204  lea     rdx, [rsp+210h+var_1A8]
0x180058209  mov     [rsp+210h+var_1B0], rax
0x18005820e  mov     qword ptr [rsp+210h+var_1A8], 0
0x180058217  mov     [rsp+210h+var_1A0], 1
0x18005821c  call    OpenCallerImpersonationToken
0x180058221  lea     rcx, [rsp+210h+var_1B0]
0x180058226  mov     ebx, eax
0x180058228  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18005822d  test    ebx, ebx
0x18005822f  jns     short loc_180058251
0x180058231  mov     rcx, [rbp+118h]; this
0x180058238  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x18005823f  mov     r9d, ebx; char *
0x180058242  mov     edx, 1E2h; void *
0x180058247  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005824c  jmp     loc_18005845D
0x180058251  mov     rcx, [rsp+210h+TokenHandle]; TokenHandle
0x180058256  lea     rax, [rsp+210h+var_1D8]
0x18005825b  mov     [rbp+110h+var_190], rax
0x18005825f  lea     r8, [rbp+110h+var_188]
0x180058263  lea     rax, [rsp+210h+var_1C8]
0x180058268  mov     [rsp+210h+var_1C8], 0
0x180058271  xor     r9d, r9d
0x180058274  mov     [rsp+210h+var_1B0], rax
0x180058279  lea     rdx, [rsp+210h+var_1A8]
0x18005827e  mov     [rsp+210h+var_1D8], 0
0x180058287  mov     [rbp+110h+var_188], 0
0x18005828f  mov     [rbp+110h+var_180], 1
0x180058293  mov     qword ptr [rsp+210h+var_1A8], 0
0x18005829c  mov     [rsp+210h+var_1A0], 1
0x1800582a1  call    GetUserSidAndPackageInfoFromToken
0x1800582a6  lea     rcx, [rsp+210h+var_1B0]
0x1800582ab  mov     ebx, eax
0x1800582ad  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800582b2  lea     rcx, [rbp+110h+var_190]
0x1800582b6  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800582bb  test    ebx, ebx
0x1800582bd  jns     short loc_1800582C9
0x1800582bf  mov     edx, 1E9h
0x1800582c4  jmp     loc_180058433
0x1800582c9  mov     r8, [rsp+210h+var_1D8]; unsigned __int16 *
0x1800582ce  mov     rdx, [rsp+210h+var_1C8]; HKEY
0x1800582d3  mov     rcx, [rsp+210h+hKey]; hkey
0x1800582d8  call    ?ValidateOwnership@DcaMgr@@YAJPEAUHKEY__@@PEBG1@Z; DcaMgr::ValidateOwnership(HKEY__ *,ushort const *,ushort const *)
0x1800582dd  mov     ebx, eax
0x1800582df  test    eax, eax
0x1800582e1  jns     short loc_1800582F0
0x1800582e3  mov     r9d, eax
0x1800582e6  mov     edx, 1EEh
0x1800582eb  jmp     loc_180058436
0x1800582f0  mov     rcx, [rsp+210h+hKey]; hKey
0x1800582f5  lea     rax, [rsp+210h+cbData]
0x1800582fa  mov     [rsp+210h+lpcbData], rax; lpcbData
0x1800582ff  lea     rdx, aPresencemonito; "PresenceMonitoringMode"
0x180058306  lea     rax, [rsp+210h+Data]
0x18005830b  mov     dword ptr [rsp+210h+Data], 0
0x180058313  xor     r9d, r9d; lpType
0x180058316  mov     [rsp+210h+lpData], rax; int
0x18005831b  xor     r8d, r8d; lpReserved
0x18005831e  mov     [rsp+210h+cbData], 4
0x180058326  call    cs:__imp_RegQueryValueExW
0x18005832c  test    eax, eax
0x18005832e  js      loc_180058429
0x180058334  cmp     dword ptr [rsp+210h+Data], 1
0x180058339  jnz     loc_180058429
0x18005833f  mov     rcx, [rsp+210h+hKey]; hkey
0x180058344  lea     rax, [rsp+210h+var_1B8]
0x180058349  lea     r9, [rbp+110h+var_188]
0x18005834d  mov     [rbp+110h+var_190], rax
0x180058351  lea     r8, aDeviceinstance; "DeviceInstancePath"
0x180058358  mov     [rsp+210h+var_1B8], 0
0x180058361  xor     edx, edx; lpSubKey
0x180058363  mov     [rbp+110h+var_188], 0
0x18005836b  mov     [rbp+110h+var_180], 1
0x18005836f  call    ReadRegStringValue
0x180058374  lea     rcx, [rbp+110h+var_190]
0x180058378  mov     ebx, eax
0x18005837a  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18005837f  test    ebx, ebx
0x180058381  jns     short loc_1800583AD
0x180058383  mov     rcx, [rbp+118h]; this
0x18005838a  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x180058391  mov     r9d, ebx; char *
0x180058394  mov     edx, 208h; void *
0x180058399  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005839e  lea     rcx, [rsp+210h+var_1B8]; void *
0x1800583a3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800583a8  jmp     loc_180058449
0x1800583ad  mov     rcx, [rsp+210h+var_1B8]
0x1800583b2  xor     edx, edx
0x1800583b4  cmp     esi, 1
0x1800583b7  setz    dl
0x1800583ba  call    cs:__imp_CdfPluginUpdatePresenceState
0x1800583c0  test    eax, eax
0x1800583c2  jns     short loc_1800583DF
0x1800583c4  mov     rcx, [rbp+118h]; this
0x1800583cb  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x1800583d2  mov     r9d, eax; char *
0x1800583d5  mov     edx, 20Eh; void *
0x1800583da  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800583df  mov     rdx, [rsp+210h+var_1D8]
0x1800583e4  lea     rcx, [rbp+110h+var_170]
0x1800583e8  mov     r9d, esi
0x1800583eb  mov     r8, rdi
0x1800583ee  call    ?Stop@UpdatePresenceState@DevCredSvcTraceLoggingProvider@@QEAAXPEBG0W4_DevicePresenceState@@@Z; DevCredSvcTraceLoggingProvider::UpdatePresenceState::Stop(ushort const *,ushort const *,_DevicePresenceState)
0x1800583f3  lea     rcx, [rsp+210h+var_1B8]; void *
0x1800583f8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800583fd  lea     rcx, [rsp+210h+var_1D8]; void *
0x180058402  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180058407  lea     rcx, [rsp+210h+var_1C8]; void *
0x18005840c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180058411  lea     rcx, [rsp+210h+TokenHandle]
0x180058416  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005841b  lea     rcx, [rsp+210h+hKey]
0x180058420  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180058425  xor     ebx, ebx
0x180058427  jmp     short loc_180058471
0x180058429  mov     ebx, 8000FFFFh
0x18005842e  mov     edx, 200h; void *
0x180058433  mov     r9d, ebx; char *
0x180058436  mov     rcx, [rbp+118h]; this
0x18005843d  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x180058444  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058449  lea     rcx, [rsp+210h+var_1D8]; void *
0x18005844e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180058453  lea     rcx, [rsp+210h+var_1C8]; void *
0x180058458  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005845d  lea     rcx, [rsp+210h+TokenHandle]
0x180058462  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180058467  lea     rcx, [rsp+210h+hKey]
0x18005846c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180058471  lea     rcx, [rbp+110h+var_170]; this
0x180058475  call    ??1UpdatePresenceState@DevCredSvcTraceLoggingProvider@@QEAA@XZ; DevCredSvcTraceLoggingProvider::UpdatePresenceState::~UpdatePresenceState(void)
0x18005847a  mov     eax, ebx
0x18005847c  mov     rcx, [rbp+110h+var_20]
0x180058483  xor     rcx, rsp; StackCookie
0x180058486  call    __security_check_cookie
0x18005848b  mov     rbx, [rsp+210h+arg_10]
0x180058493  add     rsp, 200h
0x18005849a  pop     rdi
0x18005849b  pop     rsi
0x18005849c  pop     rbp
0x18005849d  retn
```
