# Windows::Internal::WiFiCloudStore::StoreSyncNeededProfileInRegistry(_GUID const &,void * const,ushort const *,_FILETIME const &,Windows::Internal::WiFiCloudStore::ProfileModificationType,Windows::Internal::WiFiCloudStore::ProfileGeneration,bool *)

- ea: `0x18003c170`
- end: `0x18003c87c`
- name: `?StoreSyncNeededProfileInRegistry@WiFiCloudStore@Internal@Windows@@YAJAEBU_GUID@@QEAXPEBGAEBU_FILETIME@@W4ProfileModificationType@123@W4ProfileGeneration@123@PEA_N@Z`
- size: `1804`
- prototype: `__int64 __fastcall(__int64, void *, __int64, _DWORD *, unsigned int, unsigned int, _BYTE *)`
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800242a0`
- `0x1800360bc`

## callees

- `0x180006420`
- `0x180007f90`
- `0x180009fb8`
- `0x18000b674`
- `0x18000b714`
- `0x18000cc78`
- `0x180010cb4`
- `0x180016118`
- `0x18001de24`
- `0x18001e1a0`
- `0x180024c14`
- `0x180028a70`
- `0x18002a030`
- `0x18002c138`
- `0x180031ce4`
- `0x18003bf50`
- `0x18003c030`
- `0x18003c068`
- `0x18003c0a8`
- `0x18003c170`
- `0x18003cc9c`
- `0x18003cccc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003c535`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003c535`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003c5e3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003c5e3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c49b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c49b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003c2e2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003c7c1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003c2e2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003c7c1`

## string_xrefs

- `0x18003c1f1`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`
- `0x18003c228`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`
- `0x18003c25d`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`
- `0x18003c291`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`
- `0x18003c2f4`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`
- `0x18003c4b0`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`
- `0x18003c54a`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`
- `0x18003c5f8`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`
- `0x18003c7d3`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`
- `0x18003c835`: `onecore\net\wificloudstore\registry\lib\wificdsproducerreg.cpp`
- `0x18003c821`: `SID: %ws, Profile: %ws, Modification Type: %u`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall Windows::Internal::WiFiCloudStore::StoreSyncNeededProfileInRegistry(
        __int64 a1,
        void *a2,
        __int64 a3,
        _DWORD *a4,
        unsigned int a5,
        unsigned int a6,
        _BYTE *a7)
{
  __int64 v7; // r13
  __int64 v9; // r15
  unsigned int v10; // edi
  unsigned int v12; // r14d
  char v13; // al
  char v14; // al
  int v15; // eax
  const char *v16; // r9
  unsigned int LastError; // ebx
  __int64 v19; // rax
  unsigned int v20; // ebx
  const WCHAR *v21; // rdx
  unsigned int v22; // eax
  unsigned int v23; // ebx
  unsigned int v24; // eax
  unsigned int v25; // ebx
  DWORD i; // esi
  unsigned int v27; // eax
  __int64 v28; // rax
  char *v29; // rcx
  __int64 v30; // rax
  unsigned int v31; // r12d
  _DWORD *v32; // r12
  const char *v33; // r9
  LPWSTR v34; // rax
  const char *v35; // r9
  unsigned int v36; // ebx
  const char *v37; // rdx
  unsigned int dwOptions; // [rsp+20h] [rbp-158h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-158h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-158h]
  HKEY hKey; // [rsp+60h] [rbp-118h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp-110h] BYREF
  LPWSTR v43; // [rsp+70h] [rbp-108h] BYREF
  LPWSTR v44; // [rsp+78h] [rbp-100h] BYREF
  _DWORD *v45; // [rsp+80h] [rbp-F8h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+88h] [rbp-F0h] BYREF
  DWORD cSubKeys; // [rsp+8Ch] [rbp-ECh] BYREF
  int v48; // [rsp+90h] [rbp-E8h] BYREF
  DWORD v49; // [rsp+94h] [rbp-E4h]
  __int64 v50; // [rsp+98h] [rbp-E0h] BYREF
  _BYTE *v51; // [rsp+A0h] [rbp-D8h]
  LPWSTR lpName[3]; // [rsp+A8h] [rbp-D0h] BYREF
  char v53[8]; // [rsp+C0h] [rbp-B8h] BYREF
  char v54[8]; // [rsp+C8h] [rbp-B0h] BYREF
  _DWORD *v55; // [rsp+D0h] [rbp-A8h]
  LPWSTR v56; // [rsp+D8h] [rbp-A0h] BYREF
  __int64 v57; // [rsp+E0h] [rbp-98h]
  _DWORD *v58; // [rsp+E8h] [rbp-90h]
  LPCWSTR lpSubKey[4]; // [rsp+F0h] [rbp-88h] BYREF
  _BYTE v60[32]; // [rsp+110h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v45 = a4;
  v7 = a3;
  v9 = a1;
  v10 = a5;
  v58 = a4;
  v57 = a1;
  v50 = a3;
  v55 = a4;
  v51 = a7;
  if ( !a5 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
      (const char *)a4);
  v12 = a6;
  if ( a5 != 1 || (v13 = 1, a6 == 0x7FFFFFFF) )
    v13 = 0;
  if ( v13 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
      (const char *)a4);
  if ( ((a5 - 4) & 0xFFFFFFFB) != 0 || (v14 = 1, a6 == 0x80000000) )
    v14 = 0;
  if ( v14 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
      (const char *)a4);
  switch ( a5 )
  {
    case 1u:
      v15 = 3;
      break;
    case 2u:
      v15 = 4;
      break;
    case 4u:
      v15 = 10;
      break;
    case 8u:
      v15 = 12;
      break;
    default:
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x54,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
        (const char *)a4);
  }
  v48 = v15;
  *a7 = 0;
  if ( (unsigned int)Windows::Internal::WiFiCloudStore::GetOwnerSecurityOfSid(a2) == 1 )
  {
    StringSid = 0;
    if ( !ConvertSidToStringSidW(a2, &StringSid) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x67,
                    (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
                    v16);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
      return LastError;
    }
    hKey = 0;
    if ( a5 - 1 <= 1 )
      v19 = Windows::Internal::WiFiCloudStore::OpenProfileSyncRegistryKeyForUser(&v44, v9, v12, StringSid);
    else
      v19 = Windows::Internal::WiFiCloudStore::OpenCostSyncRegistryKeyForUser(&v44, v9, v12, StringSid);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(
      &hKey,
      v19);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v44);
    v20 = (unsigned int)StringSid;
    std::wstring::wstring(lpSubKey, v7);
    Windows::Internal::WiFiCloudStore::DeleteRetryCountForProfile((unsigned int)lpSubKey, v9, a5, v12, v20);
    std::wstring::~wstring(lpSubKey);
    Windows::Internal::WiFiCloudStore::StoreSyncNeededProfileForUser(hKey, v7, a4, a5);
    *v51 = 1;
    LODWORD(v45) = *v45;
    HIDWORD(v45) = a4[1];
    v44 = StringSid;
    WiFiCloudStoreTelemetry::WlanStoredNeededChange<unsigned short const * &,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,_GUID const &,unsigned __int64 &,enum WiFiSyncAction const &,unsigned short *>(
      (unsigned int)&v50,
      (unsigned int)&a6,
      v9,
      (unsigned int)&v45,
      (__int64)&v48,
      (__int64)&v44);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    return 0;
  }
  if ( a5 != 1 )
  {
    Windows::Internal::WiFiCloudStore::GetMutableCDSRegistryKey(lpSubKey);
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v21 = (const WCHAR *)lpSubKey;
    if ( lpSubKey[3] > (LPCWSTR)7 )
      v21 = lpSubKey[0];
    v22 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v21, 0, 0, 0, 0xFu, 0, &hKey, 0);
    if ( v22 )
    {
      v23 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x83,
              (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
              (const char *)v22,
              dwOptions);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::~wstring(lpSubKey);
      return v23;
    }
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    v24 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v24 )
    {
      v25 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x88,
              (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
              (const char *)v24,
              dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::~wstring(lpSubKey);
      return v25;
    }
    std::vector<unsigned short>::vector<unsigned short>(lpName, cbMaxSubKeyLen + 1);
    for ( i = 0; ; ++i )
    {
      v49 = i;
      if ( i >= cSubKeys )
        break;
      LODWORD(StringSid) = lpName[1] - lpName[0];
      v27 = RegEnumKeyExW(hKey, i, lpName[0], (LPDWORD)&StringSid, 0, 0, 0, 0);
      try
      {
        if ( v27 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x93,
            (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
            (const char *)v27,
            dwOptionsb);
        v43 = 0;
        if ( v10 == 2 )
        {
          v30 = Windows::Internal::WiFiCloudStore::OpenProfileSyncRegistryKeyForUser(v54, v9, v12, lpName[0]);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(
            &v43,
            v30);
          v29 = v54;
        }
        else
        {
          v28 = Windows::Internal::WiFiCloudStore::OpenCostSyncRegistryKeyForUser(v53, v9, v12, lpName[0]);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(
            &v43,
            v28);
          v29 = v53;
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v29);
        v31 = (unsigned int)lpName[0];
        std::wstring::wstring(v60, v7);
        Windows::Internal::WiFiCloudStore::DeleteRetryCountForProfile((unsigned int)v60, v9, v10, v12, v31);
        std::wstring::~wstring(v60);
        v32 = v55;
        Windows::Internal::WiFiCloudStore::StoreSyncNeededProfileForUser(v43, v7, v55, v10);
        *v51 = 1;
        LODWORD(v44) = *v45;
        HIDWORD(v44) = v32[1];
        v56 = lpName[0];
        WiFiCloudStoreTelemetry::WlanStoredNeededChange<unsigned short const * &,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,_GUID const &,unsigned __int64 &,enum WiFiSyncAction const &,unsigned short *>(
          (unsigned int)&v50,
          (unsigned int)&a6,
          v9,
          (unsigned int)&v44,
          (__int64)&v48,
          (__int64)&v56);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v43);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0xA9,
          (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
          v33);
        v12 = a6;
        v10 = a5;
        i = v49;
        v9 = v57;
        v7 = v50;
        v45 = v58;
        continue;
      }
    }
    std::vector<unsigned short>::_Tidy(lpName);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::~wstring(lpSubKey);
    return 0;
  }
  v34 = 0;
  v43 = 0;
  if ( a2 )
  {
    if ( !ConvertSidToStringSidW(a2, &v43) )
    {
      v36 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xB1,
              (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
              v35);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v43);
      return v36;
    }
    v34 = v43;
  }
  v37 = (const char *)L"null";
  if ( v34 )
    v37 = (const char *)v34;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0xB4,
    (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsproducerreg.cpp",
    (const char *)0x80070057LL,
    (int)"SID: %ws, Profile: %ws, Modification Type: %u",
    v37,
    v7,
    1);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v43);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18003c170  push    rbx
0x18003c172  push    rsi
0x18003c173  push    rdi
0x18003c174  push    r12
0x18003c176  push    r13
0x18003c178  push    r14
0x18003c17a  push    r15
0x18003c17c  sub     rsp, 140h
0x18003c183  mov     rax, cs:__security_cookie
0x18003c18a  xor     rax, rsp
0x18003c18d  mov     [rsp+178h+var_48], rax
0x18003c195  mov     rax, r9
0x18003c198  mov     [rsp+178h+var_F8], rax
0x18003c1a0  mov     r13, r8
0x18003c1a3  mov     rsi, rdx
0x18003c1a6  mov     r15, rcx
0x18003c1a9  mov     edi, [rsp+178h+arg_20]
0x18003c1b0  mov     [rsp+178h+var_90], rax
0x18003c1b8  mov     [rsp+178h+var_98], rcx
0x18003c1c0  mov     [rsp+178h+var_E0], r8
0x18003c1c8  mov     r12, r9
0x18003c1cb  mov     [rsp+178h+var_A8], r9
0x18003c1d3  mov     rdx, [rsp+178h+arg_30]
0x18003c1db  mov     [rsp+178h+var_D8], rdx
0x18003c1e3  mov     rcx, [rsp+178h]; this
0x18003c1eb  xor     ebx, ebx
0x18003c1ed  test    edi, edi
0x18003c1ef  jnz     short loc_18003C201
0x18003c1f1  lea     r8, aOnecoreNetWifi_0; "onecore\\net\\wificloudstore\\registry"...
0x18003c1f8  lea     edx, [rdi+5Bh]; void *
0x18003c1fb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18003c201  mov     r14d, [rsp+178h+arg_28]
0x18003c209  cmp     edi, 1
0x18003c20c  jnz     short loc_18003C21A
0x18003c20e  cmp     r14d, 7FFFFFFFh
0x18003c215  mov     al, dil
0x18003c218  jnz     short loc_18003C21C
0x18003c21a  mov     al, bl
0x18003c21c  mov     rcx, [rsp+178h]; this
0x18003c224  test    al, al
0x18003c226  jz      short loc_18003C23A
0x18003c228  lea     r8, aOnecoreNetWifi_0; "onecore\\net\\wificloudstore\\registry"...
0x18003c22f  mov     edx, 5Ch ; '\'; void *
0x18003c234  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18003c23a  lea     eax, [rdi-4]
0x18003c23d  test    eax, 0FFFFFFFBh
0x18003c242  jnz     short loc_18003C24F
0x18003c244  cmp     r14d, 80000000h
0x18003c24b  mov     al, 1
0x18003c24d  jnz     short loc_18003C251
0x18003c24f  mov     al, bl
0x18003c251  mov     rcx, [rsp+178h]; this
0x18003c259  test    al, al
0x18003c25b  jz      short loc_18003C26F
0x18003c25d  lea     r8, aOnecoreNetWifi_0; "onecore\\net\\wificloudstore\\registry"...
0x18003c264  mov     edx, 5Eh ; '^'; void *
0x18003c269  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18003c26f  mov     ecx, edi
0x18003c271  sub     ecx, 1
0x18003c274  jz      short loc_18003C2B6
0x18003c276  sub     ecx, 1
0x18003c279  jz      short loc_18003C2AF
0x18003c27b  sub     ecx, 2
0x18003c27e  jz      short loc_18003C2A8
0x18003c280  mov     eax, 4
0x18003c285  cmp     ecx, eax
0x18003c287  jz      short loc_18003C2A1
0x18003c289  mov     rcx, [rsp+178h]; this
0x18003c291  lea     r8, aOnecoreNetWifi_0; "onecore\\net\\wificloudstore\\registry"...
0x18003c298  lea     edx, [rax+50h]; void *
0x18003c29b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18003c2a1  mov     eax, 0Ch
0x18003c2a6  jmp     short loc_18003C2BB
0x18003c2a8  mov     eax, 0Ah
0x18003c2ad  jmp     short loc_18003C2BB
0x18003c2af  mov     eax, 4
0x18003c2b4  jmp     short loc_18003C2BB
0x18003c2b6  mov     eax, 3
0x18003c2bb  mov     [rsp+178h+var_E8], eax
0x18003c2c2  mov     [rdx], bl
0x18003c2c4  mov     rcx, rsi
0x18003c2c7  call    ?GetOwnerSecurityOfSid@WiFiCloudStore@Internal@Windows@@YA?AW4ProfileOwnerSecurity@123@QEAX@Z; Windows::Internal::WiFiCloudStore::GetOwnerSecurityOfSid(void * const)
0x18003c2cc  cmp     eax, 1
0x18003c2cf  jnz     loc_18003C42C
0x18003c2d5  mov     [rsp+178h+StringSid], rbx
0x18003c2da  lea     rdx, [rsp+178h+StringSid]; StringSid
0x18003c2df  mov     rcx, rsi; Sid
0x18003c2e2  call    cs:__imp_ConvertSidToStringSidW
0x18003c2e8  test    eax, eax
0x18003c2ea  jnz     short loc_18003C316
0x18003c2ec  mov     rcx, [rsp+178h]; this
0x18003c2f4  lea     r8, aOnecoreNetWifi_0; "onecore\\net\\wificloudstore\\registry"...
0x18003c2fb  lea     edx, [rax+67h]; void *
0x18003c2fe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003c303  mov     ebx, eax
0x18003c305  lea     rcx, [rsp+178h+StringSid]
0x18003c30a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003c30f  mov     eax, ebx
0x18003c311  jmp     loc_18003C858
0x18003c316  mov     [rsp+178h+hKey], rbx
0x18003c31b  lea     eax, [rdi-1]
0x18003c31e  mov     r9, [rsp+178h+StringSid]
0x18003c323  mov     r8d, r14d
0x18003c326  mov     rdx, r15
0x18003c329  lea     rcx, [rsp+178h+var_100]
0x18003c32e  cmp     eax, 1
0x18003c331  jbe     short loc_18003C33A
0x18003c333  call    ?OpenCostSyncRegistryKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@W4ProfileGeneration@123@PEBG@Z; Windows::Internal::WiFiCloudStore::OpenCostSyncRegistryKeyForUser(_GUID const &,Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *)
0x18003c338  jmp     short loc_18003C33F
0x18003c33a  call    ?OpenProfileSyncRegistryKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@W4ProfileGeneration@123@PEBG@Z; Windows::Internal::WiFiCloudStore::OpenProfileSyncRegistryKeyForUser(_GUID const &,Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *)
0x18003c33f  mov     rdx, rax
0x18003c342  lea     rcx, [rsp+178h+hKey]
0x18003c347  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&)
0x18003c34c  lea     rcx, [rsp+178h+var_100]
0x18003c351  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003c356  mov     rbx, [rsp+178h+StringSid]
0x18003c35b  mov     rdx, r13
0x18003c35e  lea     rcx, [rsp+178h+lpSubKey]
0x18003c366  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003c36b  nop
0x18003c36c  mov     qword ptr [rsp+178h+dwOptions], rbx
0x18003c371  mov     r9d, r14d
0x18003c374  mov     r8d, edi
0x18003c377  mov     rdx, r15
0x18003c37a  lea     rcx, [rsp+178h+lpSubKey]
0x18003c382  call    ?DeleteRetryCountForProfile@WiFiCloudStore@Internal@Windows@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@W4ProfileModificationType@123@W4ProfileGeneration@123@PEBG@Z; Windows::Internal::WiFiCloudStore::DeleteRetryCountForProfile(std::wstring const &,_GUID const &,Windows::Internal::WiFiCloudStore::ProfileModificationType,Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *)
0x18003c387  nop
0x18003c388  lea     rcx, [rsp+178h+lpSubKey]
0x18003c390  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c395  mov     r9d, edi
0x18003c398  mov     r8, r12
0x18003c39b  mov     rdx, r13
0x18003c39e  mov     rcx, [rsp+178h+hKey]
0x18003c3a3  call    ?StoreSyncNeededProfileForUser@WiFiCloudStore@Internal@Windows@@YAXQEAUHKEY__@@PEBGAEBU_FILETIME@@W4ProfileModificationType@123@@Z; Windows::Internal::WiFiCloudStore::StoreSyncNeededProfileForUser(HKEY__ * const,ushort const *,_FILETIME const &,Windows::Internal::WiFiCloudStore::ProfileModificationType)
0x18003c3a8  mov     rax, [rsp+178h+var_D8]
0x18003c3b0  mov     byte ptr [rax], 1
0x18003c3b3  mov     rax, [rsp+178h+var_F8]
0x18003c3bb  mov     eax, [rax]
0x18003c3bd  mov     dword ptr [rsp+178h+var_F8], eax
0x18003c3c4  mov     eax, [r12+4]
0x18003c3c9  mov     dword ptr [rsp+178h+var_F8+4], eax
0x18003c3d0  mov     rax, [rsp+178h+StringSid]
0x18003c3d5  mov     [rsp+178h+var_100], rax
0x18003c3da  lea     rax, [rsp+178h+var_100]
0x18003c3df  mov     qword ptr [rsp+178h+samDesired], rax
0x18003c3e4  lea     rax, [rsp+178h+var_E8]
0x18003c3ec  mov     qword ptr [rsp+178h+dwOptions], rax
0x18003c3f1  lea     r9, [rsp+178h+var_F8]
0x18003c3f9  mov     r8, r15
0x18003c3fc  lea     rdx, [rsp+178h+arg_28]
0x18003c404  lea     rcx, [rsp+178h+var_E0]
0x18003c40c  call    ??$WlanStoredNeededChange@AEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEBU_GUID@@AEA_KAEBW4WiFiSyncAction@@PEAG@WiFiCloudStoreTelemetry@@SAXAEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEBU_GUID@@AEA_KAEBW4WiFiSyncAction@@$$QEAPEAG@Z; WiFiCloudStoreTelemetry::WlanStoredNeededChange<ushort const * &,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,_GUID const &,unsigned __int64 &,WiFiSyncAction const &,ushort *>(ushort const * &,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,_GUID const &,unsigned __int64 &,WiFiSyncAction const &,ushort * &&)
0x18003c411  nop
0x18003c412  lea     rcx, [rsp+178h+hKey]
0x18003c417  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003c41c  nop
0x18003c41d  lea     rcx, [rsp+178h+StringSid]
0x18003c422  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003c427  jmp     loc_18003C7A5
0x18003c42c  cmp     edi, 1
0x18003c42f  jz      loc_18003C7AC
0x18003c435  lea     rcx, [rsp+178h+lpSubKey]; Src
0x18003c43d  call    ?GetMutableCDSRegistryKey@WiFiCloudStore@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::WiFiCloudStore::GetMutableCDSRegistryKey(void)
0x18003c442  nop
0x18003c443  mov     [rsp+178h+hKey], rbx
0x18003c448  xor     edx, edx
0x18003c44a  lea     rcx, [rsp+178h+hKey]
0x18003c44f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003c454  lea     rdx, [rsp+178h+lpSubKey]
0x18003c45c  cmp     [rsp+178h+var_70], 7
0x18003c465  cmova   rdx, [rsp+178h+lpSubKey]; lpSubKey
0x18003c46e  mov     [rsp+178h+lpdwDisposition], rbx; lpdwDisposition
0x18003c473  lea     rax, [rsp+178h+hKey]
0x18003c478  mov     [rsp+178h+phkResult], rax; phkResult
0x18003c47d  mov     [rsp+178h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18003c482  mov     [rsp+178h+samDesired], 0Fh; samDesired
0x18003c48a  mov     [rsp+178h+dwOptions], ebx; unsigned int
0x18003c48e  xor     r9d, r9d; lpClass
0x18003c491  xor     r8d, r8d; Reserved
0x18003c494  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003c49b  call    cs:__imp_RegCreateKeyExW
0x18003c4a1  test    eax, eax
0x18003c4a3  jz      short loc_18003C4E2
0x18003c4a5  mov     rcx, [rsp+178h]; this
0x18003c4ad  mov     r9d, eax; char *
0x18003c4b0  lea     r8, aOnecoreNetWifi_0; "onecore\\net\\wificloudstore\\registry"...
0x18003c4b7  mov     edx, 83h; void *
0x18003c4bc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003c4c1  mov     ebx, eax
0x18003c4c3  lea     rcx, [rsp+178h+hKey]
0x18003c4c8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003c4cd  nop
0x18003c4ce  lea     rcx, [rsp+178h+lpSubKey]
0x18003c4d6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c4db  mov     eax, ebx
0x18003c4dd  jmp     loc_18003C858
0x18003c4e2  mov     [rsp+178h+cSubKeys], ebx
0x18003c4e9  mov     [rsp+178h+cbMaxSubKeyLen], ebx
0x18003c4f0  mov     [rsp+178h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x18003c4f5  mov     [rsp+178h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x18003c4fa  mov     [rsp+178h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x18003c4ff  mov     [rsp+178h+lpdwDisposition], rbx; lpcbMaxValueNameLen
0x18003c504  mov     [rsp+178h+phkResult], rbx; lpcValues
0x18003c509  mov     [rsp+178h+lpSecurityAttributes], rbx; lpcbMaxClassLen
0x18003c50e  lea     rax, [rsp+178h+cbMaxSubKeyLen]
0x18003c516  mov     qword ptr [rsp+178h+samDesired], rax; lpcbMaxSubKeyLen
0x18003c51b  lea     rax, [rsp+178h+cSubKeys]
0x18003c523  mov     qword ptr [rsp+178h+dwOptions], rax; unsigned int
0x18003c528  xor     r9d, r9d; lpReserved
0x18003c52b  xor     r8d, r8d; lpcchClass
0x18003c52e  xor     edx, edx; lpClass
0x18003c530  mov     rcx, [rsp+178h+hKey]; hKey
0x18003c535  call    cs:__imp_RegQueryInfoKeyW
0x18003c53b  test    eax, eax
0x18003c53d  jz      short loc_18003C57C
0x18003c53f  mov     rcx, [rsp+178h]; this
0x18003c547  mov     r9d, eax; char *
0x18003c54a  lea     r8, aOnecoreNetWifi_0; "onecore\\net\\wificloudstore\\registry"...
0x18003c551  mov     edx, 88h; void *
0x18003c556  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003c55b  mov     ebx, eax
0x18003c55d  lea     rcx, [rsp+178h+hKey]
0x18003c562  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003c567  nop
0x18003c568  lea     rcx, [rsp+178h+lpSubKey]
0x18003c570  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c575  mov     eax, ebx
0x18003c577  jmp     loc_18003C858
0x18003c57c  mov     edx, [rsp+178h+cbMaxSubKeyLen]
0x18003c583  inc     edx
0x18003c585  lea     rcx, [rsp+178h+lpName]
0x18003c58d  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18003c592  nop
0x18003c593  mov     esi, ebx
0x18003c595  mov     [rsp+178h+var_E4], esi
0x18003c59c  cmp     esi, [rsp+178h+cSubKeys]
0x18003c5a3  jnb     loc_18003C77F
0x18003c5a9  mov     r8, [rsp+178h+lpName]; lpName
0x18003c5b1  mov     rax, [rsp+178h+var_C8]
0x18003c5b9  sub     rax, r8
0x18003c5bc  sar     rax, 1
0x18003c5bf  mov     dword ptr [rsp+178h+StringSid], eax
0x18003c5c3  mov     [rsp+178h+phkResult], rbx; lpftLastWriteTime
0x18003c5c8  mov     [rsp+178h+lpSecurityAttributes], rbx; lpcchClass
0x18003c5cd  mov     qword ptr [rsp+178h+samDesired], rbx; lpClass
0x18003c5d2  mov     qword ptr [rsp+178h+dwOptions], rbx; unsigned int
0x18003c5d7  lea     r9, [rsp+178h+StringSid]; lpcchName
0x18003c5dc  mov     edx, esi; dwIndex
0x18003c5de  mov     rcx, [rsp+178h+hKey]; hKey
0x18003c5e3  call    cs:__imp_RegEnumKeyExW
0x18003c5e9  mov     rcx, [rsp+178h]; this
0x18003c5f1  test    eax, eax
0x18003c5f3  jz      short loc_18003C609
0x18003c5f5  mov     r9d, eax; char *
0x18003c5f8  lea     r8, aOnecoreNetWifi_0; "onecore\\net\\wificloudstore\\registry"...
0x18003c5ff  mov     edx, 93h; void *
0x18003c604  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003c609  mov     [rsp+178h+var_108], rbx
0x18003c60e  mov     r9, [rsp+178h+lpName]
0x18003c616  mov     r8d, r14d
0x18003c619  mov     rdx, r15
0x18003c61c  cmp     edi, 2
0x18003c61f  jz      short loc_18003C645
0x18003c621  lea     rcx, [rsp+178h+var_B8]
0x18003c629  call    ?OpenCostSyncRegistryKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@W4ProfileGeneration@123@PEBG@Z; Windows::Internal::WiFiCloudStore::OpenCostSyncRegistryKeyForUser(_GUID const &,Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *)
0x18003c62e  mov     rdx, rax
0x18003c631  lea     rcx, [rsp+178h+var_108]
0x18003c636  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&)
0x18003c63b  lea     rcx, [rsp+178h+var_B8]
0x18003c643  jmp     short loc_18003C667
0x18003c645  lea     rcx, [rsp+178h+var_B0]
0x18003c64d  call    ?OpenProfileSyncRegistryKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@W4ProfileGeneration@123@PEBG@Z; Windows::Internal::WiFiCloudStore::OpenProfileSyncRegistryKeyForUser(_GUID const &,Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *)
0x18003c652  mov     rdx, rax
0x18003c655  lea     rcx, [rsp+178h+var_108]
0x18003c65a  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&)
0x18003c65f  lea     rcx, [rsp+178h+var_B0]
0x18003c667  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003c66c  mov     r12, [rsp+178h+lpName]
0x18003c674  mov     rdx, r13
0x18003c677  lea     rcx, [rsp+178h+var_68]
0x18003c67f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003c684  nop
0x18003c685  mov     qword ptr [rsp+178h+dwOptions], r12
0x18003c68a  mov     r9d, r14d
0x18003c68d  mov     r8d, edi
0x18003c690  mov     rdx, r15
0x18003c693  lea     rcx, [rsp+178h+var_68]
0x18003c69b  call    ?DeleteRetryCountForProfile@WiFiCloudStore@Internal@Windows@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@W4ProfileModificationType@123@W4ProfileGeneration@123@PEBG@Z; Windows::Internal::WiFiCloudStore::DeleteRetryCountForProfile(std::wstring const &,_GUID const &,Windows::Internal::WiFiCloudStore::ProfileModificationType,Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *)
0x18003c6a0  nop
0x18003c6a1  lea     rcx, [rsp+178h+var_68]
0x18003c6a9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c6ae  mov     r9d, edi
0x18003c6b1  mov     r12, [rsp+178h+var_A8]
0x18003c6b9  mov     r8, r12
0x18003c6bc  mov     rdx, r13
0x18003c6bf  mov     rcx, [rsp+178h+var_108]
0x18003c6c4  call    ?StoreSyncNeededProfileForUser@WiFiCloudStore@Internal@Windows@@YAXQEAUHKEY__@@PEBGAEBU_FILETIME@@W4ProfileModificationType@123@@Z; Windows::Internal::WiFiCloudStore::StoreSyncNeededProfileForUser(HKEY__ * const,ushort const *,_FILETIME const &,Windows::Internal::WiFiCloudStore::ProfileModificationType)
0x18003c6c9  mov     rax, [rsp+178h+var_D8]
0x18003c6d1  mov     byte ptr [rax], 1
0x18003c6d4  mov     rax, [rsp+178h+var_F8]
  ... truncated ...
```
