# CtapHybridInternal::GetUserLinkedDevicesRegKey(void * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)

- ea: `0x180122d70`
- end: `0x1801231f3`
- name: `?GetUserLinkedDevicesRegKey@CtapHybridInternal@@YAJQEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `1155`
- prototype: ``
- caller_count: `6`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180042050`
- `0x180122920`
- `0x1801231fc`
- `0x180123538`
- `0x1801235dc`
- `0x1801239cc`

## callees

- `0x180017a88`
- `0x180017bb4`
- `0x18001ee7c`
- `0x1800328b8`
- `0x180036da4`
- `0x18003a9e8`
- `0x18004349c`
- `0x180047b08`
- `0x18006f750`
- `0x1801223c4`
- `0x180122d70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180122e00`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180122fbb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801230d9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180122e00`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180122fbb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801230d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180122db7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180122f72`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180123091`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180122db7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180122f72`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180123091`

## string_xrefs

- `0x180123085`: `LinkedDevices`
- `0x1801230cd`: `LinkedDevices`
- `0x180122e15`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridlinkeddevice.cpp`
- `0x180122e58`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridlinkeddevice.cpp`
- `0x180122ecc`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridlinkeddevice.cpp`
- `0x180122fd4`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridlinkeddevice.cpp`
- `0x18012302d`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridlinkeddevice.cpp`
- `0x1801230f2`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridlinkeddevice.cpp`
- `0x180123157`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridlinkeddevice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CtapHybridInternal::GetUserLinkedDevicesRegKey(__int64 a1, __int64 a2)
{
  HKEY *v4; // rax
  LSTATUS v5; // eax
  unsigned int v6; // edi
  HKEY *v7; // rax
  unsigned int Key; // eax
  unsigned int v9; // ebx
  __int64 result; // rax
  int UserSid; // edi
  const char *v12; // r9
  HKEY *v13; // rax
  LSTATUS v14; // eax
  unsigned int v15; // edi
  HKEY *v16; // rax
  unsigned int v17; // eax
  unsigned int v18; // ebx
  HKEY *v19; // rax
  LSTATUS v20; // eax
  unsigned int v21; // edi
  HKEY *v22; // rax
  unsigned int v23; // eax
  unsigned int v24; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-78h]
  int phkResulta; // [rsp+20h] [rbp-78h]
  unsigned int phkResultb; // [rsp+20h] [rbp-78h]
  int phkResultc; // [rsp+20h] [rbp-78h]
  unsigned int phkResultd; // [rsp+20h] [rbp-78h]
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-48h] BYREF
  HKEY v31; // [rsp+58h] [rbp-40h] BYREF
  __int64 v32; // [rsp+60h] [rbp-38h] BYREF
  LPCWSTR *p_lpSubKey; // [rsp+68h] [rbp-30h] BYREF
  unsigned __int16 *v34; // [rsp+70h] [rbp-28h] BYREF
  char v35; // [rsp+78h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  int v37; // [rsp+B0h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+20h] BYREF

  hKey = 0;
  v4 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v5 = RegOpenKeyExW(HKEY_CURRENT_USER, L"SOFTWARE\\Microsoft\\Cryptography\\FIDO", 0, 0xF003Fu, v4);
  v6 = v5;
  if ( v5 == 2 )
  {
    v7 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    Key = RegCreateKeyExW(HKEY_CURRENT_USER, L"SOFTWARE\\Microsoft\\Cryptography\\FIDO", 0, 0, 0, 0xF003Fu, 0, v7, 0);
    if ( Key )
    {
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x6B,
             (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridlinkeddevice.cpp",
             (const char *)Key,
             phkResult);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v9;
    }
LABEL_36:
    try
    {
      lpSubKey = 0;
      wil::impersonate_token(&v37, a1);
      p_lpSubKey = &lpSubKey;
      v34 = 0;
      v35 = 1;
      UserSid = FidoGetUserSid(&v34);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_lpSubKey);
      if ( UserSid < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x74,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridlinkeddevice.cpp",
          (const char *)(unsigned int)UserSid,
          phkResult);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v37);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpSubKey);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return (unsigned int)UserSid;
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v37);
      v31 = 0;
      v13 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v31);
      v14 = RegOpenKeyExW(hKey, lpSubKey, 0, 0xF003Fu, v13);
      v15 = v14;
      if ( v14 == 2 )
      {
        v16 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v31);
        v17 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0xF003Fu, 0, v16, 0);
        if ( v17 )
        {
          v18 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x81,
                  (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridlinkeddevice.cpp",
                  (const char *)v17,
                  phkResultb);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v31);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpSubKey);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return v18;
        }
      }
      else if ( v14 )
      {
        if ( v14 > 0 )
          v15 = (unsigned __int16)v14 | 0x80070000;
        if ( (v15 & 0x80000000) != 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x84,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridlinkeddevice.cpp",
            (const char *)v15,
            phkResulta);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v31);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpSubKey);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v15;
      }
      v32 = 0;
      v19 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v32);
      v20 = RegOpenKeyExW(v31, L"LinkedDevices", 0, 0xF003Fu, v19);
      v21 = v20;
      if ( v20 == 2 )
      {
        v22 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v32);
        v23 = RegCreateKeyExW(v31, L"LinkedDevices", 0, 0, 0, 0xF003Fu, 0, v22, 0);
        if ( v23 )
        {
          v24 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x8B,
                  (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridlinkeddevice.cpp",
                  (const char *)v23,
                  phkResultd);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v32);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v31);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpSubKey);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return v24;
        }
      }
      else if ( v20 )
      {
        if ( v20 > 0 )
          v21 = (unsigned __int16)v20 | 0x80070000;
        if ( (v21 & 0x80000000) != 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8E,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridlinkeddevice.cpp",
            (const char *)v21,
            phkResultc);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v32);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v31);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpSubKey);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v21;
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(
        a2,
        &v32);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v32);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v31);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpSubKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      result = 0;
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x94,
                             (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridlinkeddevice.cpp",
                             v12);
    }
    return result;
  }
  if ( !v5 )
    goto LABEL_36;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( (v6 & 0x80000000) != 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridlinkeddevice.cpp",
      (const char *)v6,
      phkResult);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v6;
}

```

## disassembly

```asm
0x180122d70  mov     rax, rsp
0x180122d73  mov     [rax+8], rbx
0x180122d77  mov     [rax+10h], rdx
0x180122d7b  push    rsi
0x180122d7c  push    rdi
0x180122d7d  push    r15
0x180122d7f  sub     rsp, 80h
0x180122d86  mov     rsi, rdx
0x180122d89  mov     r15, rcx
0x180122d8c  xor     ebx, ebx
0x180122d8e  mov     [rax+20h], rbx
0x180122d92  lea     rcx, [rax+20h]
0x180122d96  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180122d9b  mov     [rsp+98h+phkResult], rax; int
0x180122da0  mov     r9d, 0F003Fh; samDesired
0x180122da6  xor     r8d, r8d; ulOptions
0x180122da9  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Cryptography\\FIDO"
0x180122db0  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180122db7  call    cs:__imp_RegOpenKeyExW
0x180122dbd  mov     edi, eax
0x180122dbf  cmp     eax, 2
0x180122dc2  jnz     short loc_180122E3A
0x180122dc4  lea     rcx, [rsp+98h+hKey]
0x180122dcc  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180122dd1  mov     [rsp+98h+lpdwDisposition], rbx; lpdwDisposition
0x180122dd6  mov     [rsp+98h+var_60], rax; phkResult
0x180122ddb  mov     [rsp+98h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180122de0  mov     [rsp+98h+samDesired], 0F003Fh; samDesired
0x180122de8  mov     dword ptr [rsp+98h+phkResult], ebx; int
0x180122dec  xor     r9d, r9d; lpClass
0x180122def  xor     r8d, r8d; Reserved
0x180122df2  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Cryptography\\FIDO"
0x180122df9  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180122e00  call    cs:__imp_RegCreateKeyExW
0x180122e06  test    eax, eax
0x180122e08  jz      short loc_180122E7E
0x180122e0a  mov     rcx, [rsp+98h]; this
0x180122e12  mov     r9d, eax; char *
0x180122e15  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180122e1c  lea     edx, [rbx+6Bh]; void *
0x180122e1f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180122e24  mov     ebx, eax
0x180122e26  lea     rcx, [rsp+98h+hKey]
0x180122e2e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180122e33  mov     eax, ebx
0x180122e35  jmp     loc_1801231DE
0x180122e3a  test    eax, eax
0x180122e3c  jz      short loc_180122E7E
0x180122e3e  jle     short loc_180122E49
0x180122e40  movzx   edi, ax
0x180122e43  or      edi, 80070000h
0x180122e49  test    edi, edi
0x180122e4b  jns     short loc_180122E6A
0x180122e4d  mov     rcx, [rsp+98h]; this
0x180122e55  mov     r9d, edi; char *
0x180122e58  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180122e5f  mov     edx, 6Eh ; 'n'; void *
0x180122e64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180122e69  nop
0x180122e6a  lea     rcx, [rsp+98h+hKey]
0x180122e72  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180122e77  mov     eax, edi
0x180122e79  jmp     loc_1801231DE
0x180122e7e  mov     [rsp+98h+lpSubKey], rbx
0x180122e83  mov     rdx, r15
0x180122e86  lea     rcx, [rsp+98h+arg_10]
0x180122e8e  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x180122e93  lea     rax, [rsp+98h+lpSubKey]
0x180122e98  mov     [rsp+98h+var_30], rax
0x180122e9d  mov     [rsp+98h+var_28], rbx
0x180122ea2  mov     [rsp+98h+var_20], 1
0x180122ea7  lea     rcx, [rsp+98h+var_28]; unsigned __int16 **
0x180122eac  call    ?FidoGetUserSid@@YAJPEAPEAG@Z; FidoGetUserSid(ushort * *)
0x180122eb1  mov     edi, eax
0x180122eb3  lea     rcx, [rsp+98h+var_30]
0x180122eb8  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180122ebd  test    edi, edi
0x180122ebf  jns     short loc_180122F0A
0x180122ec1  mov     rcx, [rsp+98h]; this
0x180122ec9  mov     r9d, edi; char *
0x180122ecc  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180122ed3  mov     edx, 74h ; 't'; void *
0x180122ed8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180122edd  lea     rcx, [rsp+98h+arg_10]
0x180122ee5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180122eea  nop
0x180122eeb  lea     rcx, [rsp+98h+lpSubKey]
0x180122ef0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180122ef5  nop
0x180122ef6  lea     rcx, [rsp+98h+hKey]
0x180122efe  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180122f03  mov     eax, edi
0x180122f05  jmp     loc_1801231DE
0x180122f0a  lea     rcx, [rsp+98h+arg_10]
0x180122f12  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180122f17  nop
0x180122f18  jmp     short loc_180122F48
0x180122f1a  lea     rcx, [rsp+98h+lpSubKey]
0x180122f1f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180122f24  nop
0x180122f25  lea     rcx, [rsp+98h+hKey]
0x180122f2d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180122f32  mov     eax, [rsp+98h+arg_10]
0x180122f39  jmp     loc_1801231DE
0x180122f3e  xor     ebx, ebx
0x180122f40  mov     rsi, [rsp+98h+arg_8]
0x180122f48  mov     [rsp+98h+var_40], rbx
0x180122f4d  lea     rcx, [rsp+98h+var_40]
0x180122f52  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180122f57  mov     [rsp+98h+phkResult], rax; int
0x180122f5c  mov     r9d, 0F003Fh; samDesired
0x180122f62  xor     r8d, r8d; ulOptions
0x180122f65  mov     rdx, [rsp+98h+lpSubKey]; lpSubKey
0x180122f6a  mov     rcx, [rsp+98h+hKey]; hKey
0x180122f72  call    cs:__imp_RegOpenKeyExW
0x180122f78  mov     edi, eax
0x180122f7a  cmp     eax, 2
0x180122f7d  jnz     loc_18012300F
0x180122f83  lea     rcx, [rsp+98h+var_40]
0x180122f88  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180122f8d  mov     [rsp+98h+lpdwDisposition], rbx; lpdwDisposition
0x180122f92  mov     [rsp+98h+var_60], rax; phkResult
0x180122f97  mov     [rsp+98h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180122f9c  mov     [rsp+98h+samDesired], 0F003Fh; samDesired
0x180122fa4  mov     dword ptr [rsp+98h+phkResult], ebx; unsigned int
0x180122fa8  xor     r9d, r9d; lpClass
0x180122fab  xor     r8d, r8d; Reserved
0x180122fae  mov     rdx, [rsp+98h+lpSubKey]; lpSubKey
0x180122fb3  mov     rcx, [rsp+98h+hKey]; hKey
0x180122fbb  call    cs:__imp_RegCreateKeyExW
0x180122fc1  test    eax, eax
0x180122fc3  jz      loc_180123068
0x180122fc9  mov     rcx, [rsp+98h]; this
0x180122fd1  mov     r9d, eax; char *
0x180122fd4  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180122fdb  lea     edx, [rdi+7Fh]; void *
0x180122fde  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180122fe3  mov     ebx, eax
0x180122fe5  lea     rcx, [rsp+98h+var_40]
0x180122fea  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180122fef  nop
0x180122ff0  lea     rcx, [rsp+98h+lpSubKey]
0x180122ff5  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180122ffa  nop
0x180122ffb  lea     rcx, [rsp+98h+hKey]
0x180123003  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180123008  mov     eax, ebx
0x18012300a  jmp     loc_1801231DE
0x18012300f  test    eax, eax
0x180123011  jz      short loc_180123068
0x180123013  jle     short loc_18012301E
0x180123015  movzx   edi, ax
0x180123018  or      edi, 80070000h
0x18012301e  test    edi, edi
0x180123020  jns     short loc_18012303E
0x180123022  mov     rcx, [rsp+98h]; this
0x18012302a  mov     r9d, edi; char *
0x18012302d  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180123034  mov     edx, 84h; void *
0x180123039  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012303e  lea     rcx, [rsp+98h+var_40]
0x180123043  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180123048  nop
0x180123049  lea     rcx, [rsp+98h+lpSubKey]
0x18012304e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180123053  nop
0x180123054  lea     rcx, [rsp+98h+hKey]
0x18012305c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180123061  mov     eax, edi
0x180123063  jmp     loc_1801231DE
0x180123068  mov     [rsp+98h+var_38], rbx
0x18012306d  lea     rcx, [rsp+98h+var_38]
0x180123072  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180123077  mov     [rsp+98h+phkResult], rax; int
0x18012307c  mov     r9d, 0F003Fh; samDesired
0x180123082  xor     r8d, r8d; ulOptions
0x180123085  lea     rdx, aLinkeddevices; "LinkedDevices"
0x18012308c  mov     rcx, [rsp+98h+var_40]; hKey
0x180123091  call    cs:__imp_RegOpenKeyExW
0x180123097  mov     edi, eax
0x180123099  cmp     eax, 2
0x18012309c  jnz     loc_180123139
0x1801230a2  lea     rcx, [rsp+98h+var_38]
0x1801230a7  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1801230ac  mov     [rsp+98h+lpdwDisposition], rbx; lpdwDisposition
0x1801230b1  mov     [rsp+98h+var_60], rax; phkResult
0x1801230b6  mov     [rsp+98h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1801230bb  mov     [rsp+98h+samDesired], 0F003Fh; samDesired
0x1801230c3  mov     dword ptr [rsp+98h+phkResult], ebx; unsigned int
0x1801230c7  xor     r9d, r9d; lpClass
0x1801230ca  xor     r8d, r8d; Reserved
0x1801230cd  lea     rdx, aLinkeddevices; "LinkedDevices"
0x1801230d4  mov     rcx, [rsp+98h+var_40]; hKey
0x1801230d9  call    cs:__imp_RegCreateKeyExW
0x1801230df  test    eax, eax
0x1801230e1  jz      loc_180123199
0x1801230e7  mov     rcx, [rsp+98h]; this
0x1801230ef  mov     r9d, eax; char *
0x1801230f2  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1801230f9  mov     edx, 8Bh; void *
0x1801230fe  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180123103  mov     ebx, eax
0x180123105  lea     rcx, [rsp+98h+var_38]
0x18012310a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012310f  lea     rcx, [rsp+98h+var_40]
0x180123114  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180123119  nop
0x18012311a  lea     rcx, [rsp+98h+lpSubKey]
0x18012311f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180123124  nop
0x180123125  lea     rcx, [rsp+98h+hKey]
0x18012312d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180123132  mov     eax, ebx
0x180123134  jmp     loc_1801231DE
0x180123139  test    eax, eax
0x18012313b  jz      short loc_180123199
0x18012313d  jle     short loc_180123148
0x18012313f  movzx   edi, ax
0x180123142  or      edi, 80070000h
0x180123148  test    edi, edi
0x18012314a  jns     short loc_180123168
0x18012314c  mov     rcx, [rsp+98h]; this
0x180123154  mov     r9d, edi; char *
0x180123157  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18012315e  mov     edx, 8Eh; void *
0x180123163  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123168  lea     rcx, [rsp+98h+var_38]
0x18012316d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180123172  lea     rcx, [rsp+98h+var_40]
0x180123177  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012317c  nop
0x18012317d  lea     rcx, [rsp+98h+lpSubKey]
0x180123182  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180123187  nop
0x180123188  lea     rcx, [rsp+98h+hKey]
0x180123190  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180123195  mov     eax, edi
0x180123197  jmp     short loc_1801231DE
0x180123199  lea     rdx, [rsp+98h+var_38]
0x18012319e  mov     rcx, rsi
0x1801231a1  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&)
0x1801231a6  lea     rcx, [rsp+98h+var_38]
0x1801231ab  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801231b0  lea     rcx, [rsp+98h+var_40]
0x1801231b5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801231ba  nop
0x1801231bb  lea     rcx, [rsp+98h+lpSubKey]
0x1801231c0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1801231c5  nop
0x1801231c6  lea     rcx, [rsp+98h+hKey]
0x1801231ce  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801231d3  xor     eax, eax
0x1801231d5  jmp     short loc_1801231DE
0x1801231d7  mov     eax, [rsp+98h+arg_10]
0x1801231de  mov     rbx, [rsp+98h+arg_0]
0x1801231e6  add     rsp, 80h
0x1801231ed  pop     r15
0x1801231ef  pop     rdi
0x1801231f0  pop     rsi
0x1801231f1  retn
```
