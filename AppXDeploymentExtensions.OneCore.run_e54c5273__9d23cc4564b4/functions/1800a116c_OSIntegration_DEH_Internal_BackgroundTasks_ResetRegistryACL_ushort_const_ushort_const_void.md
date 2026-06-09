# OSIntegration::DEH::Internal::BackgroundTasks::ResetRegistryACL(ushort const *,ushort const *,void *)

- ea: `0x1800a116c`
- end: `0x1800a1f61`
- name: `?ResetRegistryACL@BackgroundTasks@Internal@DEH@OSIntegration@@YAJPEBG0PEAX@Z`
- size: `3573`
- prototype: `__int64 __fastcall(LPCWSTR StringSid, const unsigned __int16 *, unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180070614`
- `0x180156970`

## callees

- `0x180012964`
- `0x180067050`
- `0x18006cb78`
- `0x1800853cc`
- `0x180098bf4`
- `0x1800a021c`
- `0x1800a116c`
- `0x1800a1f68`
- `0x1800a2030`
- `0x1800a219c`
- `0x1800a2854`
- `0x1800a5970`
- `0x1800baaac`
- `0x1800bc4a0`
- `0x1800f0260`
- `0x1801d9fa0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a1355`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a1355`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a1339`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a1339`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1203`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a128d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a130c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a13a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a142d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a14e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1602`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1700`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1817`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1915`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1a1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1b37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1c32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1d37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1e60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1f1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1203`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a128d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a130c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a13a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a142d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a14e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1602`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1700`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1817`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1915`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1a1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1b37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1c32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1d37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1e60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1f1d`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1800a1852`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1800a1852`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800a1544`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800a1544`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a11ee`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a1278`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a12f7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a1393`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a1418`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a14d0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a15ed`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a16eb`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a1802`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a1900`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a1a07`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a1b22`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a1c1d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a1d22`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a1e4b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a1f08`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a11ee`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a1278`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a12f7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a1393`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a1418`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a14d0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a15ed`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a16eb`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a1802`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a1900`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a1a07`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a1b22`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a1c1d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a1d22`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a1e4b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800a1f08`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1211`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1299`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1318`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a13b4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1439`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a14f1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a160e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a170c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1823`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1921`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1a28`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1b43`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1c3e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1d43`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1e6c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1f50`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1211`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1299`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1318`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a13b4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1439`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a14f1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a160e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a170c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1823`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1921`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1a28`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1b43`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1c3e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1d43`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1e6c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a1f50`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800a1b69`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800a1b69`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800a163f`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800a173b`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800a195a`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800a1a5b`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800a1c6b`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800a1d73`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800a163f`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800a173b`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800a195a`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800a1a5b`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800a1c6b`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800a1d73`

## string_xrefs

- `0x1800a11cc`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a1255`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a12d4`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a1366`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a13eb`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a1474`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a14a3`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a1559`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a1591`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a15c0`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a1657`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a168f`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a16be`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a176e`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a17a6`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a17d5`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a186a`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a18a4`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a18d3`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a1972`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a19ac`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a19da`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a1a8e`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a1ac6`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a1af5`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a1b7e`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a1bc1`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a1bf0`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a1c83`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a1cc6`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a1cf5`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a1dae`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a1def`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a1e1e`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a1eac`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a1edb`: `onecore\admin\appmodel\osim\src\deh\uex\backgroundtasks\backgroundtasksutilities.cpp`
- `0x1800a13c7`: `SeTakeOwnershipPrivilege`
- `0x1800a144c`: `SeRestorePrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall OSIntegration::DEH::Internal::BackgroundTasks::ResetRegistryACL(
        LPCWSTR StringSid,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        void *a4)
{
  int v7; // eax
  SECURITY_INFORMATION LastError; // ebx
  int v10; // eax
  int v11; // eax
  HANDLE CurrentThread; // rax
  const unsigned __int16 *v13; // r8
  const char *v14; // r9
  int v15; // eax
  const unsigned __int16 *v16; // r8
  bool v17; // r9
  int v18; // eax
  bool v19; // r9
  int v20; // eax
  const char *v21; // r9
  bool v22; // r9
  int v23; // eax
  bool v24; // r9
  int v25; // eax
  DWORD v26; // eax
  bool v27; // r9
  int v28; // eax
  bool v29; // r9
  int v30; // eax
  signed int v31; // eax
  bool v32; // r9
  int v33; // eax
  bool v34; // r9
  int v35; // eax
  NTSTATUS DaclSecurityDescriptor; // eax
  bool v37; // r9
  int v38; // eax
  bool v39; // r9
  int v40; // eax
  DWORD v41; // eax
  bool v42; // r9
  int v43; // eax
  bool v44; // r9
  int v45; // eax
  signed int v46; // eax
  bool v47; // r9
  int v48; // eax
  bool v49; // r9
  int v50; // eax
  const char *v51; // r9
  bool v52; // r9
  int v53; // eax
  bool v54; // r9
  int v55; // eax
  DWORD v56; // eax
  bool v57; // r9
  int v58; // eax
  bool v59; // r9
  int v60; // eax
  signed int v61; // eax
  bool v62; // r9
  int v63; // eax
  bool v64; // r9
  int v65; // eax
  bool v66; // r9
  int v67; // eax
  bool v68; // r9
  int v69; // eax
  int nSubAuthority2; // [rsp+20h] [rbp-E0h]
  int nSubAuthority2a; // [rsp+20h] [rbp-E0h]
  int nSubAuthority2b; // [rsp+20h] [rbp-E0h]
  int nSubAuthority2c; // [rsp+20h] [rbp-E0h]
  unsigned int nSubAuthority2d; // [rsp+20h] [rbp-E0h]
  int nSubAuthority2e; // [rsp+20h] [rbp-E0h]
  int nSubAuthority2f; // [rsp+20h] [rbp-E0h]
  int nSubAuthority2g; // [rsp+20h] [rbp-E0h]
  unsigned int nSubAuthority2h; // [rsp+20h] [rbp-E0h]
  int nSubAuthority2i; // [rsp+20h] [rbp-E0h]
  int nSubAuthority2j; // [rsp+20h] [rbp-E0h]
  unsigned int nSubAuthority2k; // [rsp+20h] [rbp-E0h]
  int nSubAuthority2l; // [rsp+20h] [rbp-E0h]
  int nSubAuthority2m; // [rsp+20h] [rbp-E0h]
  void *TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v85[8]; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hToken; // [rsp+70h] [rbp-90h]
  unsigned __int8 DaclDefaulted; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 DaclPresent[7]; // [rsp+79h] [rbp-87h] BYREF
  PSID psidOwner; // [rsp+80h] [rbp-80h] BYREF
  PSID Sid; // [rsp+88h] [rbp-78h] BYREF
  PACL Dacl; // [rsp+90h] [rbp-70h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+98h] [rbp-68h] BYREF
  WCHAR pObjectName[520]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Buffer[784]; // [rsp+4B0h] [rbp+3B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B18h] [rbp+A18h]

  v85[0] = 0;
  hToken = 0;
  v7 = Common::ImpersonateSelf::Impersonate((Common::ImpersonateSelf *)v85);
  LastError = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
      (const char *)(unsigned int)v7,
      nSubAuthority2);
    if ( !v85[0] )
      return LastError;
    if ( hToken )
    {
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        Common::HandleInternalFailure();
        __debugbreak();
      }
      CloseHandle(hToken);
      return LastError;
    }
    if ( RevertToSelf() )
      return LastError;
    Common::HandleInternalFailure();
  }
  v10 = StringCchPrintfW(
          pObjectName,
          0x208u,
          L"USERS\\%s\\%s",
          StringSid,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Notifications\\BackgroundCapability");
  LastError = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
      (const char *)(unsigned int)v10,
      nSubAuthority2a);
    if ( !v85[0] )
      return LastError;
    if ( hToken )
    {
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        Common::HandleInternalFailure();
        __debugbreak();
      }
      CloseHandle(hToken);
      return LastError;
    }
    if ( RevertToSelf() )
      return LastError;
    Common::HandleInternalFailure();
  }
  v11 = StringCchPrintfW(Buffer, 0x30Cu, L"USERS\\%s", a2);
  LastError = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
      (const char *)(unsigned int)v11,
      nSubAuthority2a);
    if ( !v85[0] )
      return LastError;
    if ( hToken )
    {
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        Common::HandleInternalFailure();
        __debugbreak();
      }
      CloseHandle(hToken);
      return LastError;
    }
    if ( RevertToSelf() )
      return LastError;
    Common::HandleInternalFailure();
  }
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x20u, 1, &TokenHandle) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x50,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
                  v14);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    if ( !v85[0] )
      return LastError;
    if ( hToken )
    {
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        Common::HandleInternalFailure();
        __debugbreak();
      }
      CloseHandle(hToken);
      return LastError;
    }
    if ( RevertToSelf() )
      return LastError;
    Common::HandleInternalFailure();
  }
  LOBYTE(v13) = 1;
  v15 = OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(
          TokenHandle,
          L"SeTakeOwnershipPrivilege",
          v13,
          (bool)v14);
  LastError = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
      (const char *)(unsigned int)v15,
      nSubAuthority2a);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    if ( !v85[0] )
      return LastError;
    if ( hToken )
    {
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        Common::HandleInternalFailure();
        __debugbreak();
      }
      CloseHandle(hToken);
      return LastError;
    }
    if ( RevertToSelf() )
      return LastError;
    Common::HandleInternalFailure();
  }
  LOBYTE(v16) = 1;
  v18 = OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(TokenHandle, L"SeRestorePrivilege", v16, v17);
  LastError = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
      (const char *)(unsigned int)v18,
      nSubAuthority2a);
    v20 = OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(TokenHandle, L"SeTakeOwnershipPrivilege", 0, v19);
    if ( v20 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
        (const char *)(unsigned int)v20,
        nSubAuthority2b);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    if ( !v85[0] )
      return LastError;
    if ( hToken )
    {
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        Common::HandleInternalFailure();
        __debugbreak();
      }
      CloseHandle(hToken);
      return LastError;
    }
    if ( RevertToSelf() )
      return LastError;
    Common::HandleInternalFailure();
  }
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  psidOwner = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &psidOwner) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x6B,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
                  v21);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&psidOwner);
    v23 = OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(TokenHandle, L"SeRestorePrivilege", 0, v22);
    if ( v23 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5B,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
        (const char *)(unsigned int)v23,
        nSubAuthority2c);
    v25 = OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(TokenHandle, L"SeTakeOwnershipPrivilege", 0, v24);
    if ( v25 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
        (const char *)(unsigned int)v25,
        nSubAuthority2c);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    if ( !v85[0] )
      return LastError;
    if ( hToken )
    {
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        Common::HandleInternalFailure();
        __debugbreak();
      }
      CloseHandle(hToken);
      return LastError;
    }
    if ( RevertToSelf() )
      return LastError;
    Common::HandleInternalFailure();
  }
  LastError = 4;
  v26 = SetNamedSecurityInfoW(pObjectName, SE_REGISTRY_KEY, 1u, psidOwner, 0, 0, 0);
  if ( v26 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x75,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
                  (const char *)v26,
                  nSubAuthority2d);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&psidOwner);
    v28 = OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(TokenHandle, L"SeRestorePrivilege", 0, v27);
    if ( v28 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5B,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
        (const char *)(unsigned int)v28,
        nSubAuthority2e);
    v30 = OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(TokenHandle, L"SeTakeOwnershipPrivilege", 0, v29);
    if ( v30 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
        (const char *)(unsigned int)v30,
        nSubAuthority2e);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    if ( !v85[0] )
      return LastError;
    if ( hToken )
    {
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        Common::HandleInternalFailure();
        __debugbreak();
      }
      CloseHandle(hToken);
      return LastError;
    }
    if ( RevertToSelf() )
      return LastError;
    Common::HandleInternalFailure();
  }
  v31 = SetNamedSecurityInfoW(Buffer, (SE_OBJECT_TYPE)LastError, 1u, psidOwner, 0, 0, 0);
  LastError = v31;
  if ( v31 > 0 )
    LastError = (unsigned __int16)v31 | 0x80070000;
  if ( LastError != -2147024894 && (LastError & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x82,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
      (const char *)LastError,
      nSubAuthority2f);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&psidOwner);
    v33 = OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(TokenHandle, L"SeRestorePrivilege", 0, v32);
    if ( v33 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5B,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
        (const char *)(unsigned int)v33,
        nSubAuthority2f);
    v35 = OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(TokenHandle, L"SeTakeOwnershipPrivilege", 0, v34);
    if ( v35 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
        (const char *)(unsigned int)v35,
        nSubAuthority2f);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    if ( !v85[0] )
      return LastError;
    if ( hToken )
    {
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        Common::HandleInternalFailure();
        __debugbreak();
      }
      CloseHandle(hToken);
      return LastError;
    }
    if ( RevertToSelf() )
      return LastError;
    Common::HandleInternalFailure();
  }
  Dacl = 0;
  DaclPresent[0] = 0;
  DaclDefaulted = 0;
  DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(a3, DaclPresent, &Dacl, &DaclDefaulted);
  if ( DaclSecurityDescriptor < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x89,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
                  (const char *)(unsigned int)DaclSecurityDescriptor,
                  nSubAuthority2f);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&psidOwner);
    v38 = OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(TokenHandle, L"SeRestorePrivilege", 0, v37);
    if ( v38 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5B,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
        (const char *)(unsigned int)v38,
        nSubAuthority2g);
    v40 = OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(TokenHandle, L"SeTakeOwnershipPrivilege", 0, v39);
    if ( v40 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
        (const char *)(unsigned int)v40,
        nSubAuthority2g);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    if ( !v85[0] )
      return LastError;
    if ( hToken )
    {
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        Common::HandleInternalFailure();
        __debugbreak();
      }
      CloseHandle(hToken);
      return LastError;
    }
    if ( RevertToSelf() )
      return LastError;
    Common::HandleInternalFailure();
  }
  LastError = -2147483644;
  v41 = SetNamedSecurityInfoW(pObjectName, SE_REGISTRY_KEY, 0x80000004, 0, 0, Dacl, 0);
  if ( v41 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x91,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
                  (const char *)v41,
                  nSubAuthority2h);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&psidOwner);
    v43 = OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(TokenHandle, L"SeRestorePrivilege", 0, v42);
    if ( v43 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5B,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
        (const char *)(unsigned int)v43,
        nSubAuthority2i);
    v45 = OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(TokenHandle, L"SeTakeOwnershipPrivilege", 0, v44);
    if ( v45 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
        (const char *)(unsigned int)v45,
        nSubAuthority2i);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    if ( !v85[0] )
      return LastError;
    if ( hToken )
    {
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        Common::HandleInternalFailure();
        __debugbreak();
      }
      CloseHandle(hToken);
      return LastError;
    }
    if ( RevertToSelf() )
      return LastError;
    Common::HandleInternalFailure();
  }
  v46 = SetNamedSecurityInfoW(Buffer, SE_REGISTRY_KEY, LastError, 0, 0, Dacl, 0);
  LastError = v46;
  if ( v46 > 0 )
    LastError = (unsigned __int16)v46 | 0x80070000;
  if ( LastError != -2147024894 && (LastError & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9D,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
      (const char *)LastError,
      nSubAuthority2j);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&psidOwner);
    v48 = OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(TokenHandle, L"SeRestorePrivilege", 0, v47);
    if ( v48 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5B,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
        (const char *)(unsigned int)v48,
        nSubAuthority2j);
    v50 = OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(TokenHandle, L"SeTakeOwnershipPrivilege", 0, v49);
    if ( v50 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
        (const char *)(unsigned int)v50,
        nSubAuthority2j);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    if ( !v85[0] )
      return LastError;
    if ( hToken )
    {
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        Common::HandleInternalFailure();
        __debugbreak();
      }
      CloseHandle(hToken);
      return LastError;
    }
    if ( RevertToSelf() )
      return LastError;
    Common::HandleInternalFailure();
  }
  Sid = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &Sid,
    0);
  if ( !ConvertStringSidToSidW(StringSid, &Sid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xA2,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
                  v51);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&psidOwner);
    v53 = OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(TokenHandle, L"SeRestorePrivilege", 0, v52);
    if ( v53 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5B,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
        (const char *)(unsigned int)v53,
        nSubAuthority2j);
    v55 = OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(TokenHandle, L"SeTakeOwnershipPrivilege", 0, v54);
    if ( v55 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
        (const char *)(unsigned int)v55,
        nSubAuthority2j);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    if ( !v85[0] )
      return LastError;
    if ( hToken )
    {
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        Common::HandleInternalFailure();
        __debugbreak();
      }
      CloseHandle(hToken);
      return LastError;
    }
    if ( RevertToSelf() )
      return LastError;
    Common::HandleInternalFailure();
  }
  v56 = SetNamedSecurityInfoW(pObjectName, SE_REGISTRY_KEY, 1u, Sid, 0, 0, 0);
  if ( v56 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xAA,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
                  (const char *)v56,
                  nSubAuthority2k);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&psidOwner);
    v58 = OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(TokenHandle, L"SeRestorePrivilege", 0, v57);
    if ( v58 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5B,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
        (const char *)(unsigned int)v58,
        nSubAuthority2l);
    v60 = OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(TokenHandle, L"SeTakeOwnershipPrivilege", 0, v59);
    if ( v60 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
        (const char *)(unsigned int)v60,
        nSubAuthority2l);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    if ( !v85[0] )
      return LastError;
    if ( hToken )
    {
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        Common::HandleInternalFailure();
        __debugbreak();
      }
      CloseHandle(hToken);
      return LastError;
    }
    if ( RevertToSelf() )
      return LastError;
    Common::HandleInternalFailure();
  }
  v61 = SetNamedSecurityInfoW(Buffer, SE_REGISTRY_KEY, 1u, Sid, 0, 0, 0);
  LastError = v61;
  if ( v61 > 0 )
    LastError = (unsigned __int16)v61 | 0x80070000;
  if ( (int)(LastError + 0x80000000) < 0 || LastError == -2147024894 )
    goto LABEL_183;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB8,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
    (const char *)LastError,
    nSubAuthority2m);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&psidOwner);
  v63 = OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(TokenHandle, L"SeRestorePrivilege", 0, v62);
  if ( v63 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
      (const char *)(unsigned int)v63,
      nSubAuthority2m);
  v65 = OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(TokenHandle, L"SeTakeOwnershipPrivilege", 0, v64);
  if ( v65 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
      (const char *)(unsigned int)v65,
      nSubAuthority2m);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  if ( !v85[0] )
    return LastError;
  if ( hToken )
  {
    if ( !ImpersonateLoggedOnUser(hToken) )
    {
      Common::HandleInternalFailure();
      __debugbreak();
    }
    CloseHandle(hToken);
    return LastError;
  }
  if ( RevertToSelf() )
    return LastError;
  Common::HandleInternalFailure();
LABEL_183:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&psidOwner);
  v67 = OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(TokenHandle, L"SeRestorePrivilege", 0, v66);
  if ( v67 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
      (const char *)(unsigned int)v67,
      nSubAuthority2m);
  v69 = OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(TokenHandle, L"SeTakeOwnershipPrivilege", 0, v68);
  if ( v69 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\backgroundtasks\\backgroundtasksutilities.cpp",
      (const char *)(unsigned int)v69,
      nSubAuthority2m);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  if ( v85[0] )
  {
    if ( hToken )
    {
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        Common::HandleInternalFailure();
        __debugbreak();
      }
      CloseHandle(hToken);
    }
    else if ( !RevertToSelf() )
    {
      Common::HandleInternalFailure();
      JUMPOUT(0x1800A1F60LL);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800a116c  mov     [rsp-8+arg_18], rbx
0x1800a1171  push    rbp
0x1800a1172  push    rsi
0x1800a1173  push    rdi
0x1800a1174  push    r12
0x1800a1176  push    r13
0x1800a1178  push    r14
0x1800a117a  push    r15
0x1800a117c  lea     rbp, [rsp-9E0h]
0x1800a1184  sub     rsp, 0AE0h
0x1800a118b  mov     rax, cs:__security_cookie
0x1800a1192  xor     rax, rsp
0x1800a1195  mov     [rbp+0A10h+var_40], rax
0x1800a119c  mov     r14, r8
0x1800a119f  mov     rdi, rdx
0x1800a11a2  mov     rsi, rcx
0x1800a11a5  xor     r15d, r15d
0x1800a11a8  mov     [rsp+0B10h+var_AA8], r15b
0x1800a11ad  mov     [rsp+0B10h+hToken], r15
0x1800a11b2  lea     rcx, [rsp+0B10h+var_AA8]; this
0x1800a11b7  call    ?Impersonate@ImpersonateSelf@Common@@QEAAJXZ; Common::ImpersonateSelf::Impersonate(void)
0x1800a11bc  mov     ebx, eax
0x1800a11be  test    eax, eax
0x1800a11c0  jns     short loc_1800A1221
0x1800a11c2  mov     rcx, [rbp+0A18h]; this
0x1800a11c9  mov     r9d, eax; char *
0x1800a11cc  lea     r8, aOnecoreAdminAp_124; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800a11d3  lea     edx, [r15+42h]; void *
0x1800a11d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a11dc  nop
0x1800a11dd  cmp     [rsp+0B10h+var_AA8], r15b
0x1800a11e2  jz      short loc_1800A120A
0x1800a11e4  mov     rcx, [rsp+0B10h+hToken]; hToken
0x1800a11e9  test    rcx, rcx
0x1800a11ec  jz      short loc_1800A1211
0x1800a11ee  call    cs:__imp_ImpersonateLoggedOnUser
0x1800a11f4  test    eax, eax
0x1800a11f6  jnz     short loc_1800A11FE
0x1800a11f8  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800a11fd  int     3; Trap to Debugger
0x1800a11fe  mov     rcx, [rsp+0B10h+hToken]; hObject
0x1800a1203  call    cs:__imp_CloseHandle
0x1800a1209  nop
0x1800a120a  mov     eax, ebx
0x1800a120c  jmp     loc_1800A1F26
0x1800a1211  call    cs:__imp_RevertToSelf
0x1800a1217  test    eax, eax
0x1800a1219  jnz     short loc_1800A120A
0x1800a121b  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800a1220  nop
0x1800a1221  lea     rax, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800a1228  mov     qword ptr [rsp+0B10h+nSubAuthority2], rax; int
0x1800a122d  mov     r9, rsi
0x1800a1230  lea     r8, aUsersSS; "USERS\\%s\\%s"
0x1800a1237  mov     edx, 208h; unsigned __int64
0x1800a123c  lea     rcx, [rbp+0A10h+pObjectName]; Buffer
0x1800a1240  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a1245  mov     ebx, eax
0x1800a1247  test    eax, eax
0x1800a1249  jns     short loc_1800A12A9
0x1800a124b  mov     rcx, [rbp+0A18h]; this
0x1800a1252  mov     r9d, eax; char *
0x1800a1255  lea     r8, aOnecoreAdminAp_124; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800a125c  mov     edx, 47h ; 'G'; void *
0x1800a1261  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1266  nop
0x1800a1267  cmp     [rsp+0B10h+var_AA8], r15b
0x1800a126c  jz      short loc_1800A1294
0x1800a126e  mov     rcx, [rsp+0B10h+hToken]; hToken
0x1800a1273  test    rcx, rcx
0x1800a1276  jz      short loc_1800A1299
0x1800a1278  call    cs:__imp_ImpersonateLoggedOnUser
0x1800a127e  test    eax, eax
0x1800a1280  jnz     short loc_1800A1288
0x1800a1282  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800a1287  int     3; Trap to Debugger
0x1800a1288  mov     rcx, [rsp+0B10h+hToken]; hObject
0x1800a128d  call    cs:__imp_CloseHandle
0x1800a1293  nop
0x1800a1294  jmp     loc_1800A120A
0x1800a1299  call    cs:__imp_RevertToSelf
0x1800a129f  test    eax, eax
0x1800a12a1  jnz     short loc_1800A1294
0x1800a12a3  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800a12a8  nop
0x1800a12a9  mov     r9, rdi
0x1800a12ac  lea     r8, aUsersS; "USERS\\%s"
0x1800a12b3  mov     edx, 30Ch; unsigned __int64
0x1800a12b8  lea     rcx, [rbp+0A10h+Buffer]; Buffer
0x1800a12bf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a12c4  mov     ebx, eax
0x1800a12c6  test    eax, eax
0x1800a12c8  jns     short loc_1800A1328
0x1800a12ca  mov     rcx, [rbp+0A18h]; this
0x1800a12d1  mov     r9d, eax; char *
0x1800a12d4  lea     r8, aOnecoreAdminAp_124; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800a12db  mov     edx, 48h ; 'H'; void *
0x1800a12e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a12e5  nop
0x1800a12e6  cmp     [rsp+0B10h+var_AA8], r15b
0x1800a12eb  jz      short loc_1800A1313
0x1800a12ed  mov     rcx, [rsp+0B10h+hToken]; hToken
0x1800a12f2  test    rcx, rcx
0x1800a12f5  jz      short loc_1800A1318
0x1800a12f7  call    cs:__imp_ImpersonateLoggedOnUser
0x1800a12fd  test    eax, eax
0x1800a12ff  jnz     short loc_1800A1307
0x1800a1301  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800a1306  int     3; Trap to Debugger
0x1800a1307  mov     rcx, [rsp+0B10h+hToken]; hObject
0x1800a130c  call    cs:__imp_CloseHandle
0x1800a1312  nop
0x1800a1313  jmp     loc_1800A120A
0x1800a1318  call    cs:__imp_RevertToSelf
0x1800a131e  test    eax, eax
0x1800a1320  jnz     short loc_1800A1313
0x1800a1322  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800a1327  nop
0x1800a1328  mov     [rsp+0B10h+TokenHandle], r15
0x1800a132d  xor     edx, edx
0x1800a132f  lea     rcx, [rsp+0B10h+TokenHandle]
0x1800a1334  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800a1339  call    cs:__imp_GetCurrentThread
0x1800a133f  lea     r9, [rsp+0B10h+TokenHandle]; TokenHandle
0x1800a1344  mov     r12d, 1
0x1800a134a  mov     r8d, r12d; OpenAsSelf
0x1800a134d  lea     edx, [r12+1Fh]; DesiredAccess
0x1800a1352  mov     rcx, rax; ThreadHandle
0x1800a1355  call    cs:__imp_OpenThreadToken
0x1800a135b  test    eax, eax
0x1800a135d  jnz     short loc_1800A13C4
0x1800a135f  mov     rcx, [rbp+0A18h]; this
0x1800a1366  lea     r8, aOnecoreAdminAp_124; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800a136d  lea     edx, [rax+50h]; void *
0x1800a1370  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a1375  mov     ebx, eax
0x1800a1377  lea     rcx, [rsp+0B10h+TokenHandle]
0x1800a137c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a1381  nop
0x1800a1382  cmp     [rsp+0B10h+var_AA8], r15b
0x1800a1387  jz      short loc_1800A13AF
0x1800a1389  mov     rcx, [rsp+0B10h+hToken]; hToken
0x1800a138e  test    rcx, rcx
0x1800a1391  jz      short loc_1800A13B4
0x1800a1393  call    cs:__imp_ImpersonateLoggedOnUser
0x1800a1399  test    eax, eax
0x1800a139b  jnz     short loc_1800A13A3
0x1800a139d  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800a13a2  int     3; Trap to Debugger
0x1800a13a3  mov     rcx, [rsp+0B10h+hToken]; hObject
0x1800a13a8  call    cs:__imp_CloseHandle
0x1800a13ae  nop
0x1800a13af  jmp     loc_1800A120A
0x1800a13b4  call    cs:__imp_RevertToSelf
0x1800a13ba  test    eax, eax
0x1800a13bc  jnz     short loc_1800A13AF
0x1800a13be  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800a13c3  nop
0x1800a13c4  mov     r8b, r12b; unsigned __int16 *
0x1800a13c7  lea     rdi, aSetakeownershi; "SeTakeOwnershipPrivilege"
0x1800a13ce  mov     rdx, rdi; void *
0x1800a13d1  mov     rcx, [rsp+0B10h+TokenHandle]; TokenHandle
0x1800a13d6  call    ?SetPrivilege@BackgroundTasks@Internal@DEH@OSIntegration@@YAJPEAXPEBG_N@Z; OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(void *,ushort const *,bool)
0x1800a13db  mov     ebx, eax
0x1800a13dd  test    eax, eax
0x1800a13df  jns     short loc_1800A1449
0x1800a13e1  mov     rcx, [rbp+0A18h]; this
0x1800a13e8  mov     r9d, eax; char *
0x1800a13eb  lea     r8, aOnecoreAdminAp_124; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800a13f2  mov     edx, 53h ; 'S'; void *
0x1800a13f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a13fc  lea     rcx, [rsp+0B10h+TokenHandle]
0x1800a1401  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a1406  nop
0x1800a1407  cmp     [rsp+0B10h+var_AA8], r15b
0x1800a140c  jz      short loc_1800A1434
0x1800a140e  mov     rcx, [rsp+0B10h+hToken]; hToken
0x1800a1413  test    rcx, rcx
0x1800a1416  jz      short loc_1800A1439
0x1800a1418  call    cs:__imp_ImpersonateLoggedOnUser
0x1800a141e  test    eax, eax
0x1800a1420  jnz     short loc_1800A1428
0x1800a1422  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800a1427  int     3; Trap to Debugger
0x1800a1428  mov     rcx, [rsp+0B10h+hToken]; hObject
0x1800a142d  call    cs:__imp_CloseHandle
0x1800a1433  nop
0x1800a1434  jmp     loc_1800A120A
0x1800a1439  call    cs:__imp_RevertToSelf
0x1800a143f  test    eax, eax
0x1800a1441  jnz     short loc_1800A1434
0x1800a1443  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800a1448  nop
0x1800a1449  mov     r8b, r12b; unsigned __int16 *
0x1800a144c  lea     r13, aSerestoreprivi; "SeRestorePrivilege"
0x1800a1453  mov     rdx, r13; void *
0x1800a1456  mov     rcx, [rsp+0B10h+TokenHandle]; TokenHandle
0x1800a145b  call    ?SetPrivilege@BackgroundTasks@Internal@DEH@OSIntegration@@YAJPEAXPEBG_N@Z; OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(void *,ushort const *,bool)
0x1800a1460  mov     ebx, eax
0x1800a1462  test    eax, eax
0x1800a1464  jns     loc_1800A1501
0x1800a146a  mov     rcx, [rbp+0A18h]; this
0x1800a1471  mov     r9d, eax; char *
0x1800a1474  lea     r8, aOnecoreAdminAp_124; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800a147b  mov     edx, 58h ; 'X'; void *
0x1800a1480  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1485  xor     r8d, r8d; unsigned __int16 *
0x1800a1488  mov     rdx, rdi; void *
0x1800a148b  mov     rcx, [rsp+0B10h+TokenHandle]; TokenHandle
0x1800a1490  call    ?SetPrivilege@BackgroundTasks@Internal@DEH@OSIntegration@@YAJPEAXPEBG_N@Z; OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(void *,ushort const *,bool)
0x1800a1495  mov     rcx, [rbp+0A18h]; this
0x1800a149c  test    eax, eax
0x1800a149e  jns     short loc_1800A14B4
0x1800a14a0  mov     r9d, eax; char *
0x1800a14a3  lea     r8, aOnecoreAdminAp_124; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800a14aa  mov     edx, 56h ; 'V'; void *
0x1800a14af  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a14b4  lea     rcx, [rsp+0B10h+TokenHandle]
0x1800a14b9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a14be  nop
0x1800a14bf  cmp     [rsp+0B10h+var_AA8], r15b
0x1800a14c4  jz      short loc_1800A14EC
0x1800a14c6  mov     rcx, [rsp+0B10h+hToken]; hToken
0x1800a14cb  test    rcx, rcx
0x1800a14ce  jz      short loc_1800A14F1
0x1800a14d0  call    cs:__imp_ImpersonateLoggedOnUser
0x1800a14d6  test    eax, eax
0x1800a14d8  jnz     short loc_1800A14E0
0x1800a14da  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800a14df  int     3; Trap to Debugger
0x1800a14e0  mov     rcx, [rsp+0B10h+hToken]; hObject
0x1800a14e5  call    cs:__imp_CloseHandle
0x1800a14eb  nop
0x1800a14ec  jmp     loc_1800A120A
0x1800a14f1  call    cs:__imp_RevertToSelf
0x1800a14f7  test    eax, eax
0x1800a14f9  jnz     short loc_1800A14EC
0x1800a14fb  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800a1500  nop
0x1800a1501  mov     dword ptr [rbp+0A10h+pIdentifierAuthority.Value], r15d
0x1800a1505  mov     word ptr [rbp+0A10h+pIdentifierAuthority.Value+4], 500h
0x1800a150b  mov     [rbp+0A10h+psidOwner], r15
0x1800a150f  lea     rax, [rbp+0A10h+psidOwner]
0x1800a1513  mov     [rsp+0B10h+pSid], rax; pSid
0x1800a1518  mov     [rsp+0B10h+nSubAuthority7], r15d; nSubAuthority7
0x1800a151d  mov     [rsp+0B10h+nSubAuthority6], r15d; nSubAuthority6
0x1800a1522  mov     [rsp+0B10h+nSubAuthority5], r15d; nSubAuthority5
0x1800a1527  mov     [rsp+0B10h+nSubAuthority4], r15d; nSubAuthority4
0x1800a152c  mov     [rsp+0B10h+nSubAuthority3], r15d; nSubAuthority3
0x1800a1531  mov     [rsp+0B10h+nSubAuthority2], r15d; int
0x1800a1536  xor     r9d, r9d; nSubAuthority1
0x1800a1539  lea     r8d, [r9+12h]; nSubAuthority0
0x1800a153d  mov     dl, r12b; nSubAuthorityCount
0x1800a1540  lea     rcx, [rbp+0A10h+pIdentifierAuthority]; pIdentifierAuthority
0x1800a1544  call    cs:__imp_AllocateAndInitializeSid
0x1800a154a  test    eax, eax
0x1800a154c  jnz     loc_1800A161E
0x1800a1552  mov     rcx, [rbp+0A18h]; this
0x1800a1559  lea     r8, aOnecoreAdminAp_124; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800a1560  lea     edx, [rax+6Bh]; void *
0x1800a1563  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a1568  mov     ebx, eax
0x1800a156a  lea     rcx, [rbp+0A10h+psidOwner]
0x1800a156e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a1573  xor     r8d, r8d; unsigned __int16 *
0x1800a1576  mov     rdx, r13; void *
0x1800a1579  mov     rcx, [rsp+0B10h+TokenHandle]; TokenHandle
0x1800a157e  call    ?SetPrivilege@BackgroundTasks@Internal@DEH@OSIntegration@@YAJPEAXPEBG_N@Z; OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(void *,ushort const *,bool)
0x1800a1583  mov     rcx, [rbp+0A18h]; this
0x1800a158a  test    eax, eax
0x1800a158c  jns     short loc_1800A15A2
0x1800a158e  mov     r9d, eax; char *
0x1800a1591  lea     r8, aOnecoreAdminAp_124; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800a1598  mov     edx, 5Bh ; '['; void *
0x1800a159d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a15a2  xor     r8d, r8d; unsigned __int16 *
0x1800a15a5  mov     rdx, rdi; void *
0x1800a15a8  mov     rcx, [rsp+0B10h+TokenHandle]; TokenHandle
0x1800a15ad  call    ?SetPrivilege@BackgroundTasks@Internal@DEH@OSIntegration@@YAJPEAXPEBG_N@Z; OSIntegration::DEH::Internal::BackgroundTasks::SetPrivilege(void *,ushort const *,bool)
0x1800a15b2  mov     rcx, [rbp+0A18h]; this
0x1800a15b9  test    eax, eax
0x1800a15bb  jns     short loc_1800A15D1
0x1800a15bd  mov     r9d, eax; char *
0x1800a15c0  lea     r8, aOnecoreAdminAp_124; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800a15c7  mov     edx, 56h ; 'V'; void *
0x1800a15cc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a15d1  lea     rcx, [rsp+0B10h+TokenHandle]
0x1800a15d6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a15db  nop
0x1800a15dc  cmp     [rsp+0B10h+var_AA8], r15b
0x1800a15e1  jz      short loc_1800A1609
0x1800a15e3  mov     rcx, [rsp+0B10h+hToken]; hToken
0x1800a15e8  test    rcx, rcx
0x1800a15eb  jz      short loc_1800A160E
0x1800a15ed  call    cs:__imp_ImpersonateLoggedOnUser
0x1800a15f3  test    eax, eax
0x1800a15f5  jnz     short loc_1800A15FD
0x1800a15f7  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x1800a15fc  int     3; Trap to Debugger
0x1800a15fd  mov     rcx, [rsp+0B10h+hToken]; hObject
  ... truncated ...
```
