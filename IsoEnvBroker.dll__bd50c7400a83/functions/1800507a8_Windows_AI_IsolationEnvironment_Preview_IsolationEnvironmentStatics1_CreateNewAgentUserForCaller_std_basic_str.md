# Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics1::CreateNewAgentUserForCaller(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1800507a8`
- end: `0x180051d78`
- name: `?CreateNewAgentUserForCaller@IsolationEnvironmentStatics1@Preview@IsolationEnvironment@AI@Windows@@AEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00000@Z`
- size: `5584`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800501c0`

## callees

- `0x180002520`
- `0x180002a54`
- `0x1800030d0`
- `0x1800031e8`
- `0x18000d19c`
- `0x18000e4ec`
- `0x180010240`
- `0x18001045c`
- `0x180010738`
- `0x180011e18`
- `0x180013270`
- `0x180014c04`
- `0x180021564`
- `0x18003ca08`
- `0x18003dce4`
- `0x18003f5a0`
- `0x1800414dc`
- `0x180046b1c`
- `0x18004705c`
- `0x18004fc48`
- `0x18004fd9c`
- `0x18004fe3c`
- `0x18004fecc`
- `0x18004ffbc`
- `0x1800507a8`
- `0x1800526c0`
- `0x180053070`
- `0x1800615a8`
- `0x180063980`
- `0x180063a08`
- `0x180063d68`

## import_xrefs

- `NETAPI32!NetLocalGroupGetInfo` at `0x180051851`
- `NETAPI32!NetLocalGroupGetInfo` at `0x180051851`
- `NETAPI32!NetUserAdd` at `0x180050e8a`
- `NETAPI32!NetUserAdd` at `0x180050e8a`
- `NETAPI32!NetLocalGroupAddMembers` at `0x180051b5c`
- `NETAPI32!NetLocalGroupAddMembers` at `0x180051b5c`
- `NETAPI32!NetLocalGroupAdd` at `0x1800519a3`
- `NETAPI32!NetLocalGroupAdd` at `0x1800519a3`
- `NETAPI32!NetUserGetInfo` at `0x180050acd`
- `NETAPI32!NetUserGetInfo` at `0x180050acd`
- `NETAPI32!NetApiBufferFree` at `0x180050adf`
- `NETAPI32!NetApiBufferFree` at `0x180051933`
- `NETAPI32!NetApiBufferFree` at `0x180051a7c`
- `NETAPI32!NetApiBufferFree` at `0x180050adf`
- `NETAPI32!NetApiBufferFree` at `0x180051933`
- `NETAPI32!NetApiBufferFree` at `0x180051a7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050935`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050f9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050fd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050fef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800510ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800510cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051162`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800514bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800514f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050935`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050f9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050fd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050fef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800510ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800510cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051162`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800514bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800514f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050948`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050faf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800514d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050948`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050faf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800514d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050fa7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051010`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800510ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005119c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051210`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051564`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051670`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800517e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800518d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051a4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051aea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051cc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050fa7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051010`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800510ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005119c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051210`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051564`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051670`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800517e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800518d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051a4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051aea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051cc4`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800508de`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800508de`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18005089b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18005089b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180050c4d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180050c4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005142e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005152d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005153e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051639`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005164a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800517b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800517c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005189f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800518b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051a14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051a25`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051ab3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051ac4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051c8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051c9e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005142e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005152d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005153e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051639`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005164a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800517b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800517c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005189f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800518b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051a14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051a25`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051ab3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051ac4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051c8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051c9e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005090d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180051485`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005090d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180051485`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050940`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050975`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050b2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050c09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005127c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800514ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005150e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005161a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051791`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051880`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800519f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051a94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051c6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051d09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050940`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050975`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050b2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050c09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005127c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800514ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005150e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005161a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051791`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051880`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800519f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051a94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051c6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051d09`
- `RPCRT4!UuidCreateSequential` at `0x180050bd6`
- `RPCRT4!UuidCreateSequential` at `0x180050bd6`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180050ba3`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180050ba3`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x180050f67`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x180050f67`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800509f9`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800509f9`
- `USERENV!UnloadUserProfile` at `0x18005154e`
- `USERENV!UnloadUserProfile` at `0x18005165a`
- `USERENV!UnloadUserProfile` at `0x1800517d1`
- `USERENV!UnloadUserProfile` at `0x1800518c0`
- `USERENV!UnloadUserProfile` at `0x180051a35`
- `USERENV!UnloadUserProfile` at `0x180051ad4`
- `USERENV!UnloadUserProfile` at `0x180051cae`
- `USERENV!UnloadUserProfile` at `0x18005154e`
- `USERENV!UnloadUserProfile` at `0x18005165a`
- `USERENV!UnloadUserProfile` at `0x1800517d1`
- `USERENV!UnloadUserProfile` at `0x1800518c0`
- `USERENV!UnloadUserProfile` at `0x180051a35`
- `USERENV!UnloadUserProfile` at `0x180051ad4`
- `USERENV!UnloadUserProfile` at `0x180051cae`
- `USERENV!LoadUserProfileW` at `0x18005109f`
- `USERENV!LoadUserProfileW` at `0x18005109f`
- `USERENV!GetUserProfileDirectoryW` at `0x180051158`
- `USERENV!GetUserProfileDirectoryW` at `0x180051158`

## string_xrefs

- `0x180051d3c`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x180051d66`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180051d27`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`
- `0x180051d51`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`
- `0x180051174`: `GetUserProfileDirectoryW failed for AU %s: %#x`
- `0x1800511f1`: `GetUserProfileDirectoryW succeeded, but there is no profile directory for %s.`
- `0x1800515ed`: `Failed to open LSA policy: %#x`
- `0x1800516cc`: `SeDenyServiceLogonRight`
- `0x180050be0`: `Failed to create marker GUID`
- `0x180050dc4`: `Calling NetUserAdd for agent user %s`
- `0x180050ea8`: `Failed to create AU %s: %#x (parm_error: %d)`
- `0x1800519c5`: `Failed to create AG %s: %#x (parm_error: %d)`
- `0x18005134b`: `Loading the user %s profile complete`
- `0x180051bf6`: `(v1) Created AU %s (%s) for %s`

## pseudocode

```c
__int64 __fastcall Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics1::CreateNewAgentUserForCaller(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  _WORD *v7; // rcx
  _WORD *v8; // rcx
  _WORD *v9; // rcx
  _WORD *v10; // rcx
  _WORD *v11; // rcx
  _WORD *v12; // rcx
  HRESULT v13; // eax
  int token_information; // eax
  PSID *v15; // rdi
  BOOL v16; // r12d
  PWSTR Buffer; // r15
  PWSTR *v18; // rsi
  void *v19; // r14
  DWORD LastError; // ebx
  signed int v21; // eax
  __int64 v22; // rbx
  __int64 v24; // r8
  char v25; // r14
  int v26; // esi
  bool v27; // sf
  int v28; // eax
  __int64 v29; // r8
  __int64 v30; // rcx
  struct OwningUserRegistry *v31; // r12
  __int64 v32; // r8
  __int64 v33; // r8
  LPCWSTR *v34; // rax
  _QWORD *v35; // rax
  const WCHAR *v36; // r8
  int v37; // edx
  void *v38; // rax
  _QWORD *v39; // rsi
  void *v40; // r13
  DWORD v41; // ebx
  DWORD v42; // eax
  signed int v43; // eax
  int v44; // eax
  DWORD v45; // eax
  signed int v46; // eax
  int v47; // eax
  int v48; // eax
  int v49; // eax
  __int64 v50; // r8
  __int64 v51; // r8
  int v52; // eax
  HKEY v53; // rsi
  int v54; // ecx
  LPWSTR v55; // r13
  DWORD v56; // ebx
  signed int v57; // eax
  int v58; // eax
  struct _LSA_UNICODE_STRING *v59; // rcx
  unsigned int v60; // eax
  ULONG v61; // r9d
  unsigned int v62; // ebx
  int v63; // eax
  __int64 v64; // rdx
  __int64 v65; // rcx
  WCHAR *v66; // r8
  __int64 v67; // rax
  USHORT v68; // ax
  void *v69; // r13
  unsigned int v70; // eax
  unsigned int v71; // ebx
  int v72; // eax
  signed int Info; // eax
  char v74; // bl
  int v75; // eax
  void *v76; // rcx
  LPWSTR *v77; // rax
  void *v78; // rcx
  int v79; // eax
  DWORD v80; // eax
  int v81; // eax
  __int128 *v82; // rax
  int cchReferencedDomainName; // [rsp+20h] [rbp-E0h]
  LPDWORD cchReferencedDomainNamea; // [rsp+20h] [rbp-E0h]
  LPDWORD cchReferencedDomainNameb; // [rsp+20h] [rbp-E0h]
  LPDWORD cchReferencedDomainNamec; // [rsp+20h] [rbp-E0h]
  void *Block; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL v90; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v92; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v93; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL v94; // [rsp+68h] [rbp-98h] BYREF
  DWORD parm_err; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+80h] [rbp-80h] BYREF
  DWORD v98; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD cchSize; // [rsp+88h] [rbp-78h] BYREF
  struct _PROFILEINFOW ProfileInfo; // [rsp+90h] [rbp-70h] BYREF
  __int64 v101; // [rsp+C8h] [rbp-38h]
  __int64 v102; // [rsp+D0h] [rbp-30h]
  __int64 v103; // [rsp+D8h] [rbp-28h]
  __int64 v104; // [rsp+E0h] [rbp-20h]
  __int64 v105; // [rsp+E8h] [rbp-18h]
  __int64 v106; // [rsp+F0h] [rbp-10h]
  void *v107; // [rsp+F8h] [rbp-8h]
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+100h] [rbp+0h] BYREF
  BYTE buf[8]; // [rsp+130h] [rbp+30h] BYREF
  LPCWSTR *v110; // [rsp+138h] [rbp+38h]
  int v111; // [rsp+144h] [rbp+44h]
  _QWORD *v112; // [rsp+150h] [rbp+50h]
  int v113; // [rsp+158h] [rbp+58h]
  int v114; // [rsp+198h] [rbp+98h]
  int v115; // [rsp+19Ch] [rbp+9Ch]
  LPWSTR v116[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int128 v117; // [rsp+1E0h] [rbp+E0h]
  LPCWSTR lpszPassword[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  __m128i si128; // [rsp+200h] [rbp+100h]
  __int128 v120; // [rsp+210h] [rbp+110h] BYREF
  __int128 v121; // [rsp+220h] [rbp+120h]
  _QWORD Src[4]; // [rsp+230h] [rbp+130h] BYREF
  __int128 v123; // [rsp+250h] [rbp+150h] BYREF
  __int128 v124; // [rsp+260h] [rbp+160h]
  __int128 v125; // [rsp+270h] [rbp+170h] BYREF
  __int128 v126; // [rsp+280h] [rbp+180h]
  UUID Uuid; // [rsp+290h] [rbp+190h] BYREF
  struct _LSA_UNICODE_STRING StringSid[3]; // [rsp+2A0h] [rbp+1A0h] BYREF
  OLECHAR sz[40]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR ReferencedDomainName[8]; // [rsp+320h] [rbp+220h] BYREF
  __int128 v131; // [rsp+330h] [rbp+230h]
  __int16 v132; // [rsp+340h] [rbp+240h]
  WCHAR Name[264]; // [rsp+350h] [rbp+250h] BYREF
  WCHAR ProfileDir[264]; // [rsp+560h] [rbp+460h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+7B8h] [rbp+6B8h]

  v103 = a4;
  v102 = a3;
  v101 = a2;
  v106 = a7;
  v105 = a6;
  v104 = a5;
  if ( *(_QWORD *)(a2 + 24) <= 7u )
    v7 = (_WORD *)a2;
  else
    v7 = *(_WORD **)a2;
  *(_QWORD *)(a2 + 16) = 0;
  *v7 = 0;
  if ( *(_QWORD *)(a3 + 24) <= 7u )
    v8 = (_WORD *)a3;
  else
    v8 = *(_WORD **)a3;
  *(_QWORD *)(a3 + 16) = 0;
  *v8 = 0;
  if ( *(_QWORD *)(a4 + 24) <= 7u )
    v9 = (_WORD *)a4;
  else
    v9 = *(_WORD **)a4;
  *(_QWORD *)(a4 + 16) = 0;
  *v9 = 0;
  if ( *(_QWORD *)(a5 + 24) <= 7u )
    v10 = (_WORD *)a5;
  else
    v10 = *(_WORD **)a5;
  *(_QWORD *)(a5 + 16) = 0;
  *v10 = 0;
  if ( *(_QWORD *)(a6 + 24) <= 7u )
    v11 = (_WORD *)a6;
  else
    v11 = *(_WORD **)a6;
  *(_QWORD *)(a6 + 16) = 0;
  *v11 = 0;
  if ( *(_QWORD *)(a7 + 24) <= 7u )
    v12 = (_WORD *)a7;
  else
    v12 = *(_WORD **)a7;
  *(_QWORD *)(a7 + 16) = 0;
  *v12 = 0;
  v13 = CoImpersonateClient();
  if ( v13 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x14AA,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      (const char *)(unsigned int)v13,
      cchReferencedDomainName);
  Block = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, -5);
  if ( token_information < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x1C9B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
      (const char *)(unsigned int)token_information,
      cchReferencedDomainName);
  v15 = (PSID *)Block;
  v107 = Block;
  CoRevertToSelf();
  hMem = 0;
  *(_QWORD *)&StringSid[0].Length = &hMem;
  StringSid[0].Buffer = 0;
  LOBYTE(StringSid[1].Length) = 1;
  v16 = ConvertSidToStringSidW(*v15, &StringSid[0].Buffer);
  if ( LOBYTE(StringSid[1].Length) )
  {
    Buffer = StringSid[0].Buffer;
    v18 = *(PWSTR **)&StringSid[0].Length;
    v19 = **(void ***)&StringSid[0].Length;
    if ( **(_QWORD **)&StringSid[0].Length )
    {
      LastError = GetLastError();
      LocalFree(v19);
      SetLastError(LastError);
    }
    *v18 = Buffer;
  }
  if ( v16 )
  {
    memset_0(Name, 0, 0x204u);
    cchName = 257;
    *(_OWORD *)ReferencedDomainName = 0;
    v131 = 0;
    v132 = 0;
    v98 = 16;
    peUse = 0;
    if ( LookupAccountSidLocalW(*v15, Name, &cchName, ReferencedDomainName, &v98, &peUse) )
    {
      v120 = 0;
      v121 = 0;
      v24 = -1;
      do
        ++v24;
      while ( Name[v24] );
      std::wstring::_Construct<1,wchar_t const *>(&v120, Name);
      if ( cchName >= 0xFA )
        cchName = 250;
      v25 = 0;
      wil::reg::try_get_value<unsigned int>(&Block, g_agentAccountRegistry, 0, L"NextId");
      if ( BYTE4(Block) )
        v25 = (char)Block;
      v26 = 0;
      while ( 1 )
      {
        swprintf_s(&Name[cchName], 258LL - cchName, L"-AU-%x", (unsigned __int8)(v25 + v26));
        Block = 0;
        LODWORD(v22) = NetUserGetInfo(0, Name, 0, (LPBYTE *)&Block);
        if ( Block )
          NetApiBufferFree(Block);
        if ( (_DWORD)v22 )
          break;
        if ( ++v26 >= 256 )
        {
          std::wstring::~wstring(&v120);
          if ( hMem )
            LocalFree(hMem);
          if ( v15 )
            operator delete(v15);
          return 2147942468LL;
        }
      }
      if ( (_DWORD)v22 != 2221 )
      {
        v27 = (int)v22 < 0;
        if ( (int)v22 > 0 )
        {
          LODWORD(v22) = (unsigned __int16)v22 | 0x80070000;
          v27 = (int)v22 < 0;
        }
        if ( v27 )
        {
LABEL_72:
          std::wstring::~wstring(&v120);
          goto LABEL_28;
        }
      }
      LODWORD(Block) = (unsigned __int8)(v25 + v26 + 1);
      v28 = RegSetKeyValueW(g_agentAccountRegistry, 0, L"NextId", 4u, &Block, 4u);
      if ( v28 > 0 )
        v28 = (unsigned __int16)v28 | 0x80070000;
      if ( v28 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v28,
          (int)cchReferencedDomainNamea);
      Uuid = 0;
      if ( UuidCreateSequential(&Uuid) < 0 )
      {
        Log(2u, L"Failed to create marker GUID");
        std::wstring::~wstring(&v120);
        if ( hMem )
          LocalFree(hMem);
        if ( v15 )
          operator delete(v15);
        return 2147549183LL;
      }
      memset_0(sz, 0, sizeof(sz));
      StringFromGUID2(&Uuid, sz, 40);
      v125 = 0;
      v126 = 0;
      v29 = -1;
      do
        ++v29;
      while ( *((_WORD *)hMem + v29) );
      std::wstring::_Construct<1,wchar_t const *>(&v125, hMem);
      v31 = (struct OwningUserRegistry *)AgentAccountRegistry::GetOrCreateOwningUserRegistry(v30, &v125, &v120);
      std::wstring::~wstring(&v125);
      *(_OWORD *)v116 = 0;
      v117 = 0;
      v32 = -1;
      do
        ++v32;
      while ( sz[v32] );
      std::wstring::_Construct<1,wchar_t const *>(v116, sz);
      v123 = 0;
      v124 = 0;
      v33 = -1;
      do
        ++v33;
      while ( Name[v33] );
      std::wstring::_Construct<1,wchar_t const *>(&v123, Name);
      OwningUserRegistry::AddAgentUserRegKey(v31, &v123, v116);
      std::wstring::~wstring(&v123);
      std::wstring::~wstring(v116);
      *(_OWORD *)lpszPassword = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(lpszPassword[0]) = 0;
      LODWORD(v22) = GenerateRandomPassword<42>(lpszPassword);
      if ( (int)v22 < 0 || (LODWORD(v22) = SetServiceStartType(2u), (int)v22 < 0) )
      {
LABEL_71:
        std::wstring::~wstring(lpszPassword);
        goto LABEL_72;
      }
      Log(4u, L"Calling NetUserAdd for agent user %s", Name);
      parm_err = 0;
      *(_QWORD *)&StringSid[0].Length = L"User account for AIE: {}";
      StringSid[0].Buffer = (PWSTR)24;
      std::format<wchar_t (&)[40]>(Src);
      memset_0(buf, 0, 0x98u);
      *(_QWORD *)buf = Name;
      v34 = lpszPassword;
      if ( si128.m128i_i64[1] > 7uLL )
        v34 = (LPCWSTR *)lpszPassword[0];
      v110 = v34;
      v111 = 1;
      v113 = 66113;
      v35 = Src;
      if ( Src[3] > 7u )
        v35 = (_QWORD *)Src[0];
      v112 = v35;
      v114 = -1;
      v115 = -1;
      LODWORD(v22) = NetUserAdd(0, 2u, buf, &parm_err);
      if ( (_DWORD)v22 )
      {
        LODWORD(cchReferencedDomainNamea) = parm_err;
        Log(2u, L"Failed to create AU %s: %#x (parm_error: %d)", Name, (unsigned int)v22, cchReferencedDomainNamea);
        if ( (int)v22 > 0 )
          LODWORD(v22) = (unsigned __int16)v22 | 0x80070000;
LABEL_81:
        std::wstring::~wstring(Src);
        goto LABEL_71;
      }
      *(_QWORD *)&v123 = Name;
      *((_QWORD *)&v123 + 1) = sz;
      *(_QWORD *)&v124 = v31;
      BYTE8(v124) = 1;
      Log(4u, L"Logging on the user %s", Name);
      hObject = 0;
      *(_QWORD *)&StringSid[0].Length = &hObject;
      StringSid[0].Buffer = 0;
      LOBYTE(StringSid[1].Length) = 1;
      v36 = (const WCHAR *)lpszPassword;
      if ( si128.m128i_i64[1] > 7uLL )
        v36 = lpszPassword[0];
      v37 = LogonUserW(Name, 0, v36, 2u, 0, (PHANDLE)&StringSid[0].Buffer);
      LODWORD(Block) = v37;
      if ( LOBYTE(StringSid[1].Length) )
      {
        v38 = StringSid[0].Buffer;
        v94 = StringSid[0].Buffer;
        v39 = *(_QWORD **)&StringSid[0].Length;
        v40 = **(void ***)&StringSid[0].Length;
        if ( (unsigned __int64)(**(_QWORD **)&StringSid[0].Length - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          v41 = GetLastError();
          CloseHandle(v40);
          SetLastError(v41);
          v38 = v94;
          v37 = (int)Block;
        }
        *v39 = v38;
      }
      if ( !v37 )
      {
        v42 = GetLastError();
        Log(2u, L"Failed to logon AU %s: %#x", Name, v42);
        v43 = GetLastError();
        LODWORD(v22) = v43;
        if ( v43 > 0 )
          LODWORD(v22) = (unsigned __int16)v43 | 0x80070000;
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        v44 = CleanupUserAccount_DropsLock_OLD(Name, sz, v31);
        if ( v44 < 0 )
          Log(2u, L"Failed to cleanup AU %s after creation failure: %#x", Name, (unsigned int)v44);
        goto LABEL_81;
      }
      Log(4u, L"Loading the user %s profile", Name);
      memset(&ProfileInfo.lpProfilePath, 0, 40);
      ProfileInfo.dwSize = 56;
      ProfileInfo.dwFlags = 1;
      ProfileInfo.lpUserName = Name;
      if ( !LoadUserProfileW(hObject, &ProfileInfo) )
      {
        v45 = GetLastError();
        Log(2u, L"Failed to load profileInfo for AU %s: %#x", Name, v45);
        v46 = GetLastError();
        LODWORD(v22) = v46;
        if ( v46 > 0 )
          LODWORD(v22) = (unsigned __int16)v46 | 0x80070000;
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        v47 = CleanupUserAccount_DropsLock_OLD(Name, sz, v31);
        if ( v47 < 0 )
          Log(2u, L"Failed to cleanup AU %s after creation failure: %#x", Name, (unsigned int)v47);
        goto LABEL_81;
      }
      memset_0(ProfileDir, 0, 0x208u);
      cchSize = 260;
      if ( !GetUserProfileDirectoryW(hObject, ProfileDir, &cchSize) )
      {
        v22 = GetLastError();
        Log(2u, L"GetUserProfileDirectoryW failed for AU %s: %#x", Name, v22);
        if ( (int)v22 > 0 )
          LODWORD(v22) = (unsigned __int16)v22 | 0x80070000;
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        v48 = CleanupUserAccount_DropsLock_OLD(Name, sz, v31);
        if ( v48 < 0 )
          Log(2u, L"Failed to cleanup AU %s after creation failure: %#x", Name, (unsigned int)v48);
        goto LABEL_81;
      }
      if ( !ProfileDir[0] )
      {
        Log(2u, L"GetUserProfileDirectoryW succeeded, but there is no profile directory for %s.", Name);
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        v49 = CleanupUserAccount_DropsLock_OLD(Name, sz, v31);
        if ( v49 < 0 )
          Log(2u, L"Failed to cleanup AU %s after creation failure: %#x", Name, (unsigned int)v49);
        std::wstring::~wstring(Src);
        std::wstring::~wstring(lpszPassword);
        std::wstring::~wstring(&v120);
        if ( hMem )
          LocalFree(hMem);
        if ( v15 )
          operator delete(v15);
        return 2147500037LL;
      }
      memset(StringSid, 0, 32);
      v50 = -1;
      do
        ++v50;
      while ( ProfileDir[v50] );
      std::wstring::_Construct<1,wchar_t const *>(StringSid, ProfileDir);
      *(_OWORD *)v116 = 0;
      v117 = 0;
      v51 = -1;
      do
        ++v51;
      while ( Name[v51] );
      std::wstring::_Construct<1,wchar_t const *>(v116, Name);
      OwningUserRegistry::StoreAgentProfileDir(v31, v116, StringSid);
      std::wstring::~wstring(v116);
      std::wstring::~wstring(StringSid);
      Log(4u, L"Loading the user %s profile complete", Name);
      *(_QWORD *)&v125 = &hObject;
      *((_QWORD *)&v125 + 1) = &ProfileInfo;
      LOBYTE(v126) = 1;
      wil::reg::create_unique_key(&v93, ProfileInfo.hProfile, L"Software\\Policies\\Microsoft\\Windows\\OOBE");
      LODWORD(Block) = 1;
      wil::reg::set_value<int>(v93, L"DisablePrivacyExperience", &Block);
      wil::reg::create_unique_key(&v92, ProfileInfo.hProfile, L"Software\\Policies\\Microsoft\\Edge");
      LODWORD(Block) = 1;
      wil::reg::set_value<int>(v92, L"HideFirstRunExperience", &Block);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIEPerf_ShellPolicyChanges2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AIEPerf_ShellPolicyChanges2>::GetImpl'::`2'::impl) )
      {
        wil::reg::create_unique_key(
          &hKey,
          ProfileInfo.hProfile,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\PushNotifications");
        LODWORD(Block) = 0;
        wil::reg::set_value<int>(hKey, L"ToastEnabled", &Block);
        if ( hKey )
          RegCloseKey(hKey);
      }
      hKey = 0;
      v52 = wil::get_token_information_nothrow<_TOKEN_USER,0>(&hKey, hObject);
      if ( v52 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x1C9B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
          (const char *)(unsigned int)v52,
          (int)cchReferencedDomainNameb);
      v90 = 0;
      v116[0] = (LPWSTR)&v90;
      v116[1] = 0;
      LOBYTE(v117) = 1;
      v53 = hKey;
      v54 = ConvertSidToStringSidW(*(PSID *)hKey, &v116[1]);
      LODWORD(Block) = v54;
      if ( (_BYTE)v117 )
      {
        *(LPWSTR *)&StringSid[0].Length = v116[1];
        v55 = v116[0];
        v94 = *(HLOCAL *)v116[0];
        if ( v94 )
        {
          v56 = GetLastError();
          LocalFree(v94);
          SetLastError(v56);
          v54 = (int)Block;
        }
        *(_QWORD *)v55 = *(_QWORD *)&StringSid[0].Length;
      }
      if ( !v54 )
      {
        v57 = GetLastError();
        LODWORD(v22) = v57;
        if ( v57 > 0 )
          LODWORD(v22) = (unsigned __int16)v57 | 0x80070000;
        if ( v90 )
          LocalFree(v90);
        if ( v53 )
          operator delete(v53);
        if ( v92 )
          RegCloseKey(v92);
        if ( v93 )
          RegCloseKey(v93);
        UnloadUserProfile(hObject, ProfileInfo.hProfile);
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        v58 = CleanupUserAccount_DropsLock_OLD(Name, sz, v31);
        if ( v58 < 0 )
          Log(2u, L"Failed to cleanup AU %s after creation failure: %#x", Name, (unsigned int)v58);
        goto LABEL_81;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIE_NoUserRemotePrivilegeFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AIE_NoUserRemotePrivilegeFix>::GetImpl'::`2'::impl) )
      {
        memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
        Block = 0;
        v60 = LsaOpenPolicy(v59, &ObjectAttributes, 0x810u, &Block);
        v62 = v60;
        if ( v60 )
        {
          Log(2u, L"Failed to open LSA policy: %#x", v60);
          LODWORD(v22) = v62 | 0x10000000;
          if ( Block )
            LsaClose(Block);
          if ( v90 )
            LocalFree(v90);
          if ( v53 )
            operator delete(v53);
          if ( v92 )
            RegCloseKey(v92);
          if ( v93 )
            RegCloseKey(v93);
          UnloadUserProfile(hObject, ProfileInfo.hProfile);
          if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(hObject);
          v63 = CleanupUserAccount_DropsLock_OLD(Name, sz, v31);
          if ( v63 < 0 )
            Log(2u, L"Failed to cleanup AU %s after creation failure: %#x", Name, (unsigned int)v63);
          goto LABEL_81;
        }
        v116[0] = L"SeRemoteInteractiveLogonRight";
        v116[1] = L"SeDenyBatchLogonRight";
        *(_QWORD *)&v117 = L"SeDenyServiceLogonRight";
        memset(StringSid, 0, sizeof(StringSid));
        v64 = 0;
        v65 = 0;
        do
        {
          v66 = v116[v64];
          v67 = -1;
          do
            ++v67;
          while ( v66[v67] );
          v68 = 2 * v67;
          StringSid[v65].Length = v68;
          StringSid[v65].MaximumLength = v68 + 2;
          StringSid[v65].Buffer = v66;
          ++v64;
          ++v65;
        }
        while ( v64 != 3 );
        v69 = Block;
        v70 = LsaAddAccountRights(Block, *(PSID *)v53, StringSid, v61);
        v71 = v70;
        if ( v70 )
        {
          Log(2u, L"Failed to add account rights: %#x", v70);
          LODWORD(v22) = v71 | 0x10000000;
          if ( v69 )
            LsaClose(v69);
          if ( v90 )
            LocalFree(v90);
          if ( v53 )
            operator delete(v53);
          if ( v92 )
            RegCloseKey(v92);
          if ( v93 )
            RegCloseKey(v93);
          UnloadUserProfile(hObject, ProfileInfo.hProfile);
          if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(hObject);
          v72 = CleanupUserAccount_DropsLock_OLD(Name, sz, v31);
          if ( v72 < 0 )
            Log(2u, L"Failed to cleanup AU %s after creation failure: %#x", Name, (unsigned int)v72);
          goto LABEL_81;
        }
        if ( v69 )
          LsaClose(v69);
      }
      else
      {
        LODWORD(v22) = Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics1::AddLocalUserToRemoteDesktopGroup(
                         (Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics1 *)v59,
                         *(void **)v53);
        if ( (int)v22 < 0 )
        {
          if ( v90 )
            LocalFree(v90);
          if ( v53 )
            operator delete(v53);
          if ( v92 )
            RegCloseKey(v92);
          if ( v93 )
            RegCloseKey(v93);
          UnloadUserProfile(hObject, ProfileInfo.hProfile);
          if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(hObject);
          v75 = CleanupUserAccount_DropsLock_OLD(Name, sz, v31);
          if ( v75 < 0 )
            Log(2u, L"Failed to cleanup AU %s after creation failure: %#x", Name, (unsigned int)v75);
          goto LABEL_81;
        }
      }
      Block = 0;
      Info = NetLocalGroupGetInfo(0, L"IsoEnvUsers_2025_Preview", 1u, (LPBYTE *)&Block);
      LODWORD(v22) = Info;
      if ( Info )
      {
        if ( Info != 2220 )
        {
          if ( Info > 0 )
            LODWORD(v22) = (unsigned __int16)Info | 0x80070000;
          v78 = Block;
          Block = 0;
          if ( v78 )
            NetApiBufferFree(v78);
          if ( (int)v22 < 0 )
          {
            if ( v90 )
              LocalFree(v90);
            if ( v53 )
              operator delete(v53);
            if ( v92 )
              RegCloseKey(v92);
            if ( v93 )
              RegCloseKey(v93);
            UnloadUserProfile(hObject, ProfileInfo.hProfile);
            if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              CloseHandle(hObject);
            v79 = CleanupUserAccount_DropsLock_OLD(Name, sz, v31);
            if ( v79 < 0 )
              Log(2u, L"Failed to cleanup AU %s after creation failure: %#x", Name, (unsigned int)v79);
            goto LABEL_81;
          }
LABEL_210:
          LODWORD(Block) = 0;
          *(_OWORD *)v116 = 0;
          v117 = 0;
          std::wstring::_Construct<1,wchar_t const *>(v116, L"IsoEnvUsers_2025_Preview");
          v77 = v116;
          if ( *((_QWORD *)&v117 + 1) > 7u )
            v77 = (LPWSTR *)v116[0];
          *(_QWORD *)&StringSid[0].Length = v77;
          LODWORD(v22) = NetLocalGroupAdd(0, 0, (LPBYTE)StringSid, (LPDWORD)&Block);
          if ( (_DWORD)v22 )
          {
            LODWORD(cchReferencedDomainNameb) = (_DWORD)Block;
            Log(
              2u,
              L"Failed to create AG %s: %#x (parm_error: %d)",
              L"IsoEnvUsers_2025_Preview",
              (unsigned int)v22,
              cchReferencedDomainNameb);
            if ( (int)v22 > 0 )
              LODWORD(v22) = (unsigned __int16)v22 | 0x80070000;
            std::wstring::~wstring(v116);
LABEL_216:
            if ( v90 )
              LocalFree(v90);
            if ( v53 )
              operator delete(v53);
            if ( v92 )
              RegCloseKey(v92);
            if ( v93 )
              RegCloseKey(v93);
            UnloadUserProfile(hObject, ProfileInfo.hProfile);
            if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              CloseHandle(hObject);
            wil::details::lambda_call__AgentAccountHelpers2::CreateAgentAccount_::_2_::_lambda_1___::_lambda_call__AgentAccountHelpers2::CreateAgentAccount_::_2_::_lambda_1___(&v123);
            goto LABEL_81;
          }
          std::wstring::~wstring(v116);
LABEL_246:
          v94 = 0;
          v94 = *(HLOCAL *)v53;
          v80 = NetLocalGroupAddMembers(0, L"IsoEnvUsers_2025_Preview", 0, (LPBYTE)&v94, 1u);
          LODWORD(v22) = v80;
          if ( !v80 )
          {
            v81 = HideUserAccountFromLogonUI_0(Name);
            if ( v81 < 0 )
              Log(3u, L"Failed to hide AU %s from logon UI: %#x", Name, (unsigned int)v81);
            BYTE8(v124) = 0;
            v82 = &v120;
            if ( *((_QWORD *)&v121 + 1) > 7u )
              v82 = (__int128 *)v120;
            Log(4u, L"(v1) Created AU %s (%s) for %s", Name, v90, v82);
            std::wstring::operator=(v101, hMem);
            std::wstring::operator=(v102, &v120);
            std::wstring::operator=(v103, v90);
            std::wstring::operator=(v104, Name);
            std::wstring::operator=(v105, sz);
            std::wstring::operator=(v106, lpszPassword);
            if ( v90 )
              LocalFree(v90);
            if ( v53 )
              operator delete(v53);
            if ( v92 )
              RegCloseKey(v92);
            if ( v93 )
              RegCloseKey(v93);
            UnloadUserProfile(hObject, ProfileInfo.hProfile);
            if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              CloseHandle(hObject);
            wil::details::lambda_call__AgentAccountHelpers2::CreateAgentAccount_::_2_::_lambda_1___::_lambda_call__AgentAccountHelpers2::CreateAgentAccount_::_2_::_lambda_1___(&v123);
            std::wstring::~wstring(Src);
            std::wstring::~wstring(lpszPassword);
            std::wstring::~wstring(&v120);
            if ( hMem )
              LocalFree(hMem);
            if ( v15 )
              operator delete(v15);
            return 0;
          }
          LODWORD(cchReferencedDomainNamec) = v80;
          Log(2u, L"Failed to add AU %s to AG %s: %#x", Name, L"IsoEnvUsers_2025_Preview", cchReferencedDomainNamec);
          if ( (int)v22 > 0 )
            LODWORD(v22) = (unsigned __int16)v22 | 0x80070000;
          goto LABEL_216;
        }
        v74 = 0;
      }
      else
      {
        v74 = 1;
      }
      v76 = Block;
      Block = 0;
      if ( v76 )
        NetApiBufferFree(v76);
      if ( v74 )
        goto LABEL_246;
      goto LABEL_210;
    }
  }
  v21 = GetLastError();
  LODWORD(v22) = v21;
  if ( v21 > 0 )
    LODWORD(v22) = (unsigned __int16)v21 | 0x80070000;
LABEL_28:
  if ( hMem )
    LocalFree(hMem);
  if ( v15 )
    operator delete(v15);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x1800507a8  mov     [rsp-8+arg_0], rbx
0x1800507ad  push    rbp
0x1800507ae  push    rsi
0x1800507af  push    rdi
0x1800507b0  push    r12
0x1800507b2  push    r13
0x1800507b4  push    r14
0x1800507b6  push    r15
0x1800507b8  lea     rbp, [rsp-680h]
0x1800507c0  sub     rsp, 780h
0x1800507c7  mov     rax, cs:__security_cookie
0x1800507ce  xor     rax, rsp
0x1800507d1  mov     [rbp+6B0h+var_40], rax
0x1800507d8  mov     r10, r9
0x1800507db  mov     [rbp+6B0h+var_6D8], r9
0x1800507df  mov     r11, r8
0x1800507e2  mov     [rbp+6B0h+var_6E0], r8
0x1800507e6  mov     rax, rdx
0x1800507e9  mov     [rbp+6B0h+var_6E8], rdx
0x1800507ed  mov     rdx, [rbp+6B0h+arg_30]
0x1800507f4  mov     [rbp+6B0h+var_6C0], rdx
0x1800507f8  mov     r8, [rbp+6B0h+arg_28]
0x1800507ff  mov     [rbp+6B0h+var_6C8], r8
0x180050803  mov     r9, [rbp+6B0h+arg_20]
0x18005080a  mov     [rbp+6B0h+var_6D0], r9
0x18005080e  cmp     qword ptr [rax+18h], 7
0x180050813  jbe     short loc_18005081A
0x180050815  mov     rcx, [rax]
0x180050818  jmp     short loc_18005081D
0x18005081a  mov     rcx, rax
0x18005081d  xor     r13d, r13d
0x180050820  mov     [rax+10h], r13
0x180050824  mov     [rcx], r13w
0x180050828  cmp     qword ptr [r11+18h], 7
0x18005082d  jbe     short loc_180050834
0x18005082f  mov     rcx, [r11]
0x180050832  jmp     short loc_180050837
0x180050834  mov     rcx, r11
0x180050837  mov     [r11+10h], r13
0x18005083b  mov     [rcx], r13w
0x18005083f  cmp     qword ptr [r10+18h], 7
0x180050844  jbe     short loc_18005084B
0x180050846  mov     rcx, [r10]
0x180050849  jmp     short loc_18005084E
0x18005084b  mov     rcx, r10
0x18005084e  mov     [r10+10h], r13
0x180050852  mov     [rcx], r13w
0x180050856  cmp     qword ptr [r9+18h], 7
0x18005085b  jbe     short loc_180050862
0x18005085d  mov     rcx, [r9]
0x180050860  jmp     short loc_180050865
0x180050862  mov     rcx, r9
0x180050865  mov     [r9+10h], r13
0x180050869  mov     [rcx], r13w
0x18005086d  cmp     qword ptr [r8+18h], 7
0x180050872  jbe     short loc_180050879
0x180050874  mov     rcx, [r8]
0x180050877  jmp     short loc_18005087C
0x180050879  mov     rcx, r8
0x18005087c  mov     [r8+10h], r13
0x180050880  mov     [rcx], r13w
0x180050884  cmp     qword ptr [rdx+18h], 7
0x180050889  jbe     short loc_180050890
0x18005088b  mov     rcx, [rdx]
0x18005088e  jmp     short loc_180050893
0x180050890  mov     rcx, rdx
0x180050893  mov     [rdx+10h], r13
0x180050897  mov     [rcx], r13w
0x18005089b  call    cs:__imp_CoImpersonateClient
0x1800508a1  mov     rcx, [rbp+6B8h]; this
0x1800508a8  test    eax, eax
0x1800508aa  js      loc_180051D39
0x1800508b0  mov     [rsp+7B0h+Block], r13
0x1800508b5  mov     rdx, 0FFFFFFFFFFFFFFFBh
0x1800508bc  lea     rcx, [rsp+7B0h+Block]
0x1800508c1  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x1800508c6  mov     rcx, [rbp+6B8h]; this
0x1800508cd  test    eax, eax
0x1800508cf  js      loc_180051D4E
0x1800508d5  mov     rdi, [rsp+7B0h+Block]
0x1800508da  mov     [rbp+6B0h+var_6B8], rdi
0x1800508de  call    cs:__imp_CoRevertToSelf
0x1800508e4  mov     [rsp+7B0h+hMem], r13
0x1800508e9  lea     rax, [rsp+7B0h+hMem]
0x1800508ee  mov     [rbp+6B0h+StringSid], rax
0x1800508f5  mov     [rbp+6B0h+StringSid+8], r13
0x1800508fc  mov     byte ptr [rbp+6B0h+var_500], 1
0x180050903  lea     rdx, [rbp+6B0h+StringSid+8]; StringSid
0x18005090a  mov     rcx, [rdi]; Sid
0x18005090d  call    cs:__imp_ConvertSidToStringSidW
0x180050913  mov     r12d, eax
0x180050916  cmp     byte ptr [rbp+6B0h+var_500], r13b
0x18005091d  jz      short loc_180050951
0x18005091f  mov     r15, [rbp+6B0h+StringSid+8]
0x180050926  mov     rsi, [rbp+6B0h+StringSid]
0x18005092d  mov     r14, [rsi]
0x180050930  test    r14, r14
0x180050933  jz      short loc_18005094E
0x180050935  call    cs:__imp_GetLastError
0x18005093b  mov     ebx, eax
0x18005093d  mov     rcx, r14; hMem
0x180050940  call    cs:__imp_LocalFree
0x180050946  mov     ecx, ebx; dwErrCode
0x180050948  call    cs:__imp_SetLastError
0x18005094e  mov     [rsi], r15
0x180050951  test    r12d, r12d
0x180050954  jnz     short loc_180050990
0x180050956  call    cs:__imp_GetLastError
0x18005095c  test    eax, eax
0x18005095e  mov     ebx, eax
0x180050960  jle     short loc_18005096B
0x180050962  movzx   ebx, ax
0x180050965  or      ebx, 80070000h
0x18005096b  mov     rcx, [rsp+7B0h+hMem]; hMem
0x180050970  test    rcx, rcx
0x180050973  jz      short loc_18005097C
0x180050975  call    cs:__imp_LocalFree
0x18005097b  nop
0x18005097c  test    rdi, rdi
0x18005097f  jz      short loc_180050989
0x180050981  mov     rcx, rdi; Block
0x180050984  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180050989  mov     eax, ebx
0x18005098b  jmp     loc_180050B48
0x180050990  xor     edx, edx; Val
0x180050992  mov     r8d, 204h; Size
0x180050998  lea     rcx, [rbp+6B0h+Name]; void *
0x18005099f  call    memset_0
0x1800509a4  mov     [rsp+7B0h+cchName], 101h
0x1800509ac  xorps   xmm0, xmm0
0x1800509af  xor     eax, eax
0x1800509b1  movups  xmmword ptr [rbp+6B0h+ReferencedDomainName], xmm0
0x1800509b8  movups  [rbp+6B0h+var_480], xmm0
0x1800509bf  mov     [rbp+6B0h+var_470], ax
0x1800509c6  mov     [rbp+6B0h+var_72C], 10h
0x1800509cd  mov     [rbp+6B0h+var_730], r13d
0x1800509d1  lea     rax, [rbp+6B0h+var_730]
0x1800509d5  mov     [rsp+7B0h+peUse], rax; peUse
0x1800509da  lea     rax, [rbp+6B0h+var_72C]
0x1800509de  mov     [rsp+7B0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800509e3  lea     r9, [rbp+6B0h+ReferencedDomainName]; ReferencedDomainName
0x1800509ea  lea     r8, [rsp+7B0h+cchName]; cchName
0x1800509ef  lea     rdx, [rbp+6B0h+Name]; Name
0x1800509f6  mov     rcx, [rdi]; Sid
0x1800509f9  call    cs:__imp_LookupAccountSidLocalW
0x1800509ff  test    eax, eax
0x180050a01  jz      loc_180050956
0x180050a07  xorps   xmm0, xmm0
0x180050a0a  movups  [rbp+6B0h+var_5A0], xmm0
0x180050a11  xorps   xmm1, xmm1
0x180050a14  movdqu  [rbp+6B0h+var_590], xmm1
0x180050a1c  lea     rax, [rbp+6B0h+Name]
0x180050a23  or      r8, 0FFFFFFFFFFFFFFFFh
0x180050a27  inc     r8
0x180050a2a  cmp     [rax+r8*2], r13w
0x180050a2f  jnz     short loc_180050A27
0x180050a31  lea     rdx, [rbp+6B0h+Name]
0x180050a38  lea     rcx, [rbp+6B0h+var_5A0]
0x180050a3f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180050a44  nop
0x180050a45  mov     eax, 0FAh
0x180050a4a  cmp     [rsp+7B0h+cchName], eax
0x180050a4e  jb      short loc_180050A54
0x180050a50  mov     [rsp+7B0h+cchName], eax
0x180050a54  mov     r14d, r13d
0x180050a57  lea     r9, ValueName; "NextId"
0x180050a5e  xor     r8d, r8d
0x180050a61  mov     rdx, cs:?g_agentAccountRegistry@@3VAgentAccountRegistry@@A; AgentAccountRegistry g_agentAccountRegistry
0x180050a68  lea     rcx, [rsp+7B0h+Block]
0x180050a6d  call    ??$try_get_value@I@reg@wil@@YA?AV?$optional@I@std@@PEAUHKEY__@@PEB_W1@Z; wil::reg::try_get_value<uint>(HKEY__ *,wchar_t const *,wchar_t const *)
0x180050a72  cmp     byte ptr [rsp+7B0h+Block+4], r13b
0x180050a77  cmovnz  r14d, dword ptr [rsp+7B0h+Block]
0x180050a7d  mov     esi, r13d
0x180050a80  mov     r15d, 80070000h
0x180050a86  xor     r12d, r12d
0x180050a89  lea     eax, [r14+rsi]
0x180050a8d  movzx   r13d, al
0x180050a91  mov     eax, [rsp+7B0h+cchName]
0x180050a95  mov     edx, 102h
0x180050a9a  sub     rdx, rax; BufferCount
0x180050a9d  lea     rcx, [rbp+6B0h+Name]
0x180050aa4  lea     rcx, [rcx+rax*2]; Buffer
0x180050aa8  mov     r9d, r13d
0x180050aab  lea     r8, aAuX; "-AU-%x"
0x180050ab2  call    swprintf_s
0x180050ab7  mov     [rsp+7B0h+Block], r12
0x180050abc  lea     r9, [rsp+7B0h+Block]; bufptr
0x180050ac1  xor     r8d, r8d; level
0x180050ac4  lea     rdx, [rbp+6B0h+Name]; username
0x180050acb  xor     ecx, ecx; servername
0x180050acd  call    cs:__imp_NetUserGetInfo
0x180050ad3  mov     ebx, eax
0x180050ad5  mov     rcx, [rsp+7B0h+Block]; Buffer
0x180050ada  test    rcx, rcx
0x180050add  jz      short loc_180050AE5
0x180050adf  call    cs:__imp_NetApiBufferFree
0x180050ae5  test    ebx, ebx
0x180050ae7  jz      short loc_180050B0A
0x180050ae9  mov     al, r12b
0x180050aec  cmp     ebx, 8ADh
0x180050af2  jz      short loc_180050B06
0x180050af4  test    ebx, ebx
0x180050af6  jle     short loc_180050B00
0x180050af8  movzx   ebx, bx
0x180050afb  or      ebx, r15d
0x180050afe  test    ebx, ebx
0x180050b00  js      loc_180050D98
0x180050b06  test    al, al
0x180050b08  jz      short loc_180050B72
0x180050b0a  inc     esi
0x180050b0c  cmp     esi, 100h
0x180050b12  jl      loc_180050A89
0x180050b18  lea     rcx, [rbp+6B0h+var_5A0]
0x180050b1f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180050b24  nop
0x180050b25  mov     rcx, [rsp+7B0h+hMem]; hMem
0x180050b2a  test    rcx, rcx
0x180050b2d  jz      short loc_180050B36
0x180050b2f  call    cs:__imp_LocalFree
0x180050b35  nop
0x180050b36  test    rdi, rdi
0x180050b39  jz      short loc_180050B43
0x180050b3b  mov     rcx, rdi; Block
0x180050b3e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180050b43  mov     eax, 80070044h
0x180050b48  mov     rcx, [rbp+6B0h+var_40]
0x180050b4f  xor     rcx, rsp; StackCookie
0x180050b52  call    __security_check_cookie
0x180050b57  mov     rbx, [rsp+7B0h+arg_0]
0x180050b5f  add     rsp, 780h
0x180050b66  pop     r15
0x180050b68  pop     r14
0x180050b6a  pop     r13
0x180050b6c  pop     r12
0x180050b6e  pop     rdi
0x180050b6f  pop     rsi
0x180050b70  pop     rbp
0x180050b71  retn
0x180050b72  lea     eax, [r13+1]
0x180050b76  movzx   ecx, al
0x180050b79  mov     dword ptr [rsp+7B0h+Block], ecx
0x180050b7d  mov     ecx, 4
0x180050b82  mov     dword ptr [rsp+7B0h+peUse], ecx; cbData
0x180050b86  lea     rax, [rsp+7B0h+Block]
0x180050b8b  mov     [rsp+7B0h+cchReferencedDomainName], rax; int
0x180050b90  mov     r9d, ecx; dwType
0x180050b93  lea     r8, ValueName; "NextId"
0x180050b9a  xor     edx, edx; lpSubKey
0x180050b9c  mov     rcx, cs:?g_agentAccountRegistry@@3VAgentAccountRegistry@@A; hKey
0x180050ba3  call    cs:__imp_RegSetKeyValueW
0x180050ba9  xor     r13d, r13d
0x180050bac  test    eax, eax
0x180050bae  jle     short loc_180050BB6
0x180050bb0  movzx   eax, ax
0x180050bb3  or      eax, r15d
0x180050bb6  mov     rcx, [rbp+6B8h]; this
0x180050bbd  test    eax, eax
0x180050bbf  js      loc_180051D63
0x180050bc5  xorps   xmm0, xmm0
0x180050bc8  movups  xmmword ptr [rbp+6B0h+Uuid.Data1], xmm0
0x180050bcf  lea     rcx, [rbp+6B0h+Uuid]; Uuid
0x180050bd6  call    cs:__imp_UuidCreateSequential
0x180050bdc  test    eax, eax
0x180050bde  jns     short loc_180050C27
0x180050be0  lea     rdx, aFailedToCreate_4; "Failed to create marker GUID"
0x180050be7  mov     ecx, 2; unsigned __int8
0x180050bec  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180050bf1  nop
0x180050bf2  lea     rcx, [rbp+6B0h+var_5A0]
0x180050bf9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180050bfe  nop
0x180050bff  mov     rcx, [rsp+7B0h+hMem]; hMem
0x180050c04  test    rcx, rcx
0x180050c07  jz      short loc_180050C10
0x180050c09  call    cs:__imp_LocalFree
0x180050c0f  nop
0x180050c10  test    rdi, rdi
0x180050c13  jz      short loc_180050C1D
0x180050c15  mov     rcx, rdi; Block
0x180050c18  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180050c1d  mov     eax, 8000FFFFh
0x180050c22  jmp     loc_180050B48
0x180050c27  xor     edx, edx; Val
0x180050c29  lea     r8d, [rdx+50h]; Size
0x180050c2d  lea     rcx, [rbp+6B0h+sz]; void *
0x180050c34  call    memset_0
0x180050c39  mov     r8d, 28h ; '('; cchMax
0x180050c3f  lea     rdx, [rbp+6B0h+sz]; lpsz
0x180050c46  lea     rcx, [rbp+6B0h+Uuid]; rguid
0x180050c4d  call    cs:__imp_StringFromGUID2
0x180050c53  mov     rdx, [rsp+7B0h+hMem]
0x180050c58  xorps   xmm0, xmm0
0x180050c5b  movups  [rbp+6B0h+var_540], xmm0
0x180050c62  xorps   xmm1, xmm1
0x180050c65  movdqu  [rbp+6B0h+var_530], xmm1
0x180050c6d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180050c71  mov     r8, rsi
0x180050c74  inc     r8
0x180050c77  cmp     [rdx+r8*2], r13w
0x180050c7c  jnz     short loc_180050C74
  ... truncated ...
```
