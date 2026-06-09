# AgentAccountHelpers2::CreateAgentAccount(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180059200`
- end: `0x18005a1b3`
- name: `?CreateAgentAccount@AgentAccountHelpers2@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEAV23@111@Z`
- size: `4019`
- prototype: `__int64 __fastcall(_QWORD *, HKEY, char **, char **, __int64, __int64)`
- caller_count: `2`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180056984`
- `0x18005f3bc`

## callees

- `0x180002520`
- `0x180002a54`
- `0x1800030d0`
- `0x1800031e8`
- `0x1800050cd`
- `0x18000a464`
- `0x18000d19c`
- `0x18000e4ec`
- `0x180010148`
- `0x180010240`
- `0x18001045c`
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
- `0x18004fecc`
- `0x180059200`
- `0x18005a684`
- `0x1800615a8`
- `0x180063980`
- `0x180063a08`
- `0x180063d68`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180059285`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180059285`
- `NETAPI32!NetUserAdd` at `0x180059624`
- `NETAPI32!NetUserAdd` at `0x180059624`
- `NETAPI32!NetUserGetInfo` at `0x180059309`
- `NETAPI32!NetUserGetInfo` at `0x180059309`
- `NETAPI32!NetApiBufferFree` at `0x18005931b`
- `NETAPI32!NetApiBufferFree` at `0x18005931b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059712`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059747`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059765`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059840`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800598da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059bf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059c23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059712`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059747`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059765`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059840`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800598da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059bf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059c23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059725`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059c05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059725`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059c05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005971d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059789`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059864`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059916`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059984`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059c98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059d8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059f01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a142`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005971d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059789`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059864`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059916`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059984`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059c98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059d8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059f01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a142`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180059431`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180059431`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059b65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059c61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059c72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059d57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059d68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059eca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059edb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a10b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a11c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059b65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059c61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059c72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059d57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059d68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059eca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059edb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a10b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a11c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180059bbc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180059bbc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059bfd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059c42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059d38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059eab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a0ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059bfd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059c42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059d38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059eab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a0ec`
- `RPCRT4!UuidCreateSequential` at `0x1800593e6`
- `RPCRT4!UuidCreateSequential` at `0x1800593e6`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800593b1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800593b1`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x1800596e3`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x1800596e3`
- `USERENV!UnloadUserProfile` at `0x180059c82`
- `USERENV!UnloadUserProfile` at `0x180059d78`
- `USERENV!UnloadUserProfile` at `0x180059eeb`
- `USERENV!UnloadUserProfile` at `0x18005a12c`
- `USERENV!UnloadUserProfile` at `0x180059c82`
- `USERENV!UnloadUserProfile` at `0x180059d78`
- `USERENV!UnloadUserProfile` at `0x180059eeb`
- `USERENV!UnloadUserProfile` at `0x18005a12c`
- `USERENV!LoadUserProfileW` at `0x180059814`
- `USERENV!LoadUserProfileW` at `0x180059814`
- `USERENV!GetUserProfileDirectoryW` at `0x1800598d0`
- `USERENV!GetUserProfileDirectoryW` at `0x1800598d0`

## string_xrefs

- `0x18005a1a1`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18005a18c`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`
- `0x1800598ec`: `GetUserProfileDirectoryW failed for AU %s: %#x`
- `0x180059966`: `GetUserProfileDirectoryW succeeded, but there is no profile directory for %s.`
- `0x180059d0c`: `Failed to open LSA policy: %#x`
- `0x180059de9`: `SeDenyServiceLogonRight`
- `0x1800593f0`: `Failed to create marker GUID`
- `0x180059567`: `Calling NetUserAdd for agent user %s`
- `0x180059642`: `Failed to create AU %s: %#x (parm_error: %d)`
- `0x180059a85`: `Loading the user %s profile complete`
- `0x180059533`: `onecoreuap\windows\core\isoenvbroker\lib\v2\agentaccounthelpers.cpp`
- `0x18005a173`: `onecoreuap\windows\core\isoenvbroker\lib\v2\agentaccounthelpers.cpp`
- `0x180059fa8`: `(v2) Created AU %s (%s) for %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall AgentAccountHelpers2::CreateAgentAccount(
        _QWORD *a1,
        HKEY a2,
        char **a3,
        char **a4,
        __int64 a5,
        __int64 a6)
{
  _QWORD *v7; // r8
  unsigned __int64 v8; // rbx
  int v9; // edi
  char v10; // r15
  size_t v11; // rsi
  wchar_t *v12; // r12
  __int64 v13; // rbx
  bool v14; // sf
  int v16; // eax
  __int64 v17; // rcx
  struct OwningUserRegistry *OwningUserRegistry; // r15
  unsigned __int64 v19; // r14
  __int64 v20; // r8
  __int64 v21; // r8
  int Random; // eax
  int started; // eax
  LPCWSTR *v24; // rax
  _QWORD *v25; // rax
  DWORD v26; // eax
  const WCHAR *v27; // r8
  int v28; // edx
  void *v29; // rax
  HANDLE *v30; // rsi
  HANDLE v31; // r12
  DWORD LastError; // ebx
  DWORD v33; // eax
  signed int v34; // eax
  int v35; // eax
  DWORD v36; // eax
  signed int v37; // eax
  int v38; // eax
  int v39; // eax
  int v40; // eax
  __int64 v41; // r8
  __int64 v42; // r8
  int token_information; // eax
  HKEY v44; // rsi
  unsigned int v45; // eax
  unsigned __int64 v46; // rcx
  LPWSTR v47; // r12
  DWORD v48; // ebx
  signed int v49; // eax
  int v50; // eax
  unsigned int v51; // eax
  ULONG v52; // r9d
  unsigned int v53; // ebx
  int v54; // eax
  __int64 v55; // rdx
  __int64 v56; // rcx
  WCHAR *v57; // r8
  __int64 v58; // rax
  USHORT v59; // ax
  LPBYTE v60; // r12
  unsigned int v61; // eax
  unsigned int v62; // ebx
  int v63; // eax
  int v64; // eax
  __int64 v65; // r8
  HLOCAL v66; // r9
  unsigned __int64 v67; // rdx
  char *v68; // rdi
  __int64 v69; // rbx
  __int64 v70; // r8
  unsigned __int64 v71; // rdx
  char *v72; // rdi
  __int64 v73; // rbx
  __int64 v74; // r8
  void *v75; // rdi
  int lpData; // [rsp+20h] [rbp-E0h]
  LPCVOID lpDataa; // [rsp+20h] [rbp-E0h]
  int lpDatab; // [rsp+20h] [rbp-E0h]
  LPBYTE bufptr; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL Src; // [rsp+48h] [rbp-B8h] BYREF
  DWORD parm_err; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v84; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v85; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchSize; // [rsp+68h] [rbp-98h] BYREF
  HANDLE *p_hObject; // [rsp+70h] [rbp-90h]
  void *phToken; // [rsp+78h] [rbp-88h] BYREF
  char v89; // [rsp+80h] [rbp-80h]
  struct _PROFILEINFOW ProfileInfo; // [rsp+90h] [rbp-70h] BYREF
  HLOCAL hMem; // [rsp+C8h] [rbp-38h]
  char **v92; // [rsp+D0h] [rbp-30h]
  char **v93; // [rsp+D8h] [rbp-28h]
  __int64 v94; // [rsp+E0h] [rbp-20h]
  __int64 v95; // [rsp+E8h] [rbp-18h]
  WCHAR *v96; // [rsp+F0h] [rbp-10h]
  OLECHAR *v97; // [rsp+F8h] [rbp-8h]
  struct OwningUserRegistry *v98; // [rsp+100h] [rbp+0h]
  char v99; // [rsp+108h] [rbp+8h]
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+110h] [rbp+10h] BYREF
  BYTE buf[8]; // [rsp+140h] [rbp+40h] BYREF
  LPCWSTR *v102; // [rsp+148h] [rbp+48h]
  int v103; // [rsp+154h] [rbp+54h]
  _QWORD *v104; // [rsp+160h] [rbp+60h]
  int v105; // [rsp+168h] [rbp+68h]
  int v106; // [rsp+1A8h] [rbp+A8h]
  int v107; // [rsp+1ACh] [rbp+ACh]
  LPWSTR StringSid[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v109; // [rsp+1F0h] [rbp+F0h]
  __int128 v110; // [rsp+200h] [rbp+100h] BYREF
  __int128 v111; // [rsp+210h] [rbp+110h]
  _QWORD v112[4]; // [rsp+220h] [rbp+120h] BYREF
  LPCWSTR lpszPassword[2]; // [rsp+240h] [rbp+140h] BYREF
  __m128i si128; // [rsp+250h] [rbp+150h]
  UUID Uuid; // [rsp+260h] [rbp+160h] BYREF
  struct _LSA_UNICODE_STRING UserRights[3]; // [rsp+270h] [rbp+170h] BYREF
  OLECHAR sz[40]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR username[264]; // [rsp+2F0h] [rbp+1F0h] BYREF
  WCHAR ProfileDir[264]; // [rsp+500h] [rbp+400h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+768h] [rbp+668h]

  v93 = a4;
  v92 = a3;
  hKey = a2;
  v94 = a5;
  v95 = a6;
  memset_0(username, 0, 0x204u);
  if ( a1[3] <= 7u )
    v7 = a1;
  else
    v7 = (_QWORD *)*a1;
  _o_wcscpy_s(username, 258, v7);
  v8 = a1[2];
  if ( v8 >= 0xFA )
    v8 = 250;
  v9 = 0;
  v10 = 0;
  wil::reg::try_get_value<unsigned int>(&bufptr, g_agentAccountRegistry, 0, L"NextId");
  if ( BYTE4(bufptr) )
    v10 = (char)bufptr;
  v11 = 258 - v8;
  v12 = &username[v8];
  while ( 1 )
  {
    swprintf_s(v12, v11, L"-AU-%x", (unsigned __int8)(v10 + v9));
    bufptr = 0;
    LODWORD(v13) = NetUserGetInfo(0, username, 0, &bufptr);
    if ( bufptr )
      NetApiBufferFree(bufptr);
    if ( (_DWORD)v13 )
      break;
    if ( ++v9 >= 256 )
      return 2147942468LL;
  }
  if ( (_DWORD)v13 != 2221 )
  {
    v14 = (int)v13 < 0;
    if ( (int)v13 > 0 )
    {
      LODWORD(v13) = (unsigned __int16)v13 | 0x80070000;
      v14 = (int)v13 < 0;
    }
    if ( v14 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x85,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\agentaccounthelpers.cpp",
        (const char *)(unsigned int)v13,
        lpData);
      return (unsigned int)v13;
    }
  }
  LODWORD(bufptr) = (unsigned __int8)(v10 + v9 + 1);
  v16 = RegSetKeyValueW(g_agentAccountRegistry, 0, L"NextId", 4u, &bufptr, 4u);
  if ( v16 > 0 )
    v16 = (unsigned __int16)v16 | 0x80070000;
  if ( v16 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v16,
      (int)lpDataa);
  Uuid = 0;
  if ( UuidCreateSequential(&Uuid) < 0 )
  {
    Log(2u, L"Failed to create marker GUID");
    return 2147549183LL;
  }
  memset_0(sz, 0, sizeof(sz));
  StringFromGUID2(&Uuid, sz, 40);
  OwningUserRegistry = (struct OwningUserRegistry *)AgentAccountRegistry::GetOrCreateOwningUserRegistry(v17, hKey, a1);
  *(_OWORD *)StringSid = 0;
  v109 = 0;
  v19 = -1;
  v20 = -1;
  do
    ++v20;
  while ( sz[v20] );
  std::wstring::_Construct<1,wchar_t const *>(StringSid, sz);
  v110 = 0;
  v111 = 0;
  v21 = -1;
  do
    ++v21;
  while ( username[v21] );
  std::wstring::_Construct<1,wchar_t const *>(&v110, username);
  OwningUserRegistry::AddAgentUserRegKey(OwningUserRegistry, &v110, StringSid);
  std::wstring::~wstring(&v110);
  std::wstring::~wstring(StringSid);
  *(_OWORD *)lpszPassword = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpszPassword[0]) = 0;
  Random = GenerateRandomPassword<42>(lpszPassword);
  LODWORD(v13) = Random;
  if ( Random < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\agentaccounthelpers.cpp",
      (const char *)(unsigned int)Random,
      (int)lpDataa);
LABEL_139:
    std::wstring::~wstring(lpszPassword);
    return (unsigned int)v13;
  }
  started = SetServiceStartType(2u);
  if ( started < 0 )
  {
    LODWORD(v13) = started;
    goto LABEL_139;
  }
  Log(4u, L"Calling NetUserAdd for agent user %s", username);
  parm_err = 0;
  p_hObject = (HANDLE *)L"User account for AIE: {}";
  phToken = (void *)24;
  std::format<wchar_t (&)[40]>(v112);
  memset_0(buf, 0, 0x98u);
  *(_QWORD *)buf = username;
  v24 = lpszPassword;
  if ( si128.m128i_i64[1] > 7uLL )
    v24 = (LPCWSTR *)lpszPassword[0];
  v102 = v24;
  v103 = 1;
  v105 = 66113;
  v25 = v112;
  if ( v112[3] > 7u )
    v25 = (_QWORD *)v112[0];
  v104 = v25;
  v106 = -1;
  v107 = -1;
  v26 = NetUserAdd(0, 2u, buf, &parm_err);
  LODWORD(v13) = v26;
  if ( v26 )
  {
    LODWORD(lpDataa) = parm_err;
    Log(2u, L"Failed to create AU %s: %#x (parm_error: %d)", username, v26, lpDataa);
    if ( (int)v13 > 0 )
      LODWORD(v13) = (unsigned __int16)v13 | 0x80070000;
LABEL_138:
    std::wstring::~wstring(v112);
    goto LABEL_139;
  }
  v96 = username;
  v97 = sz;
  v98 = OwningUserRegistry;
  v99 = 1;
  Log(4u, L"Logging on the user %s", username);
  hObject = 0;
  p_hObject = &hObject;
  phToken = 0;
  v89 = 1;
  v27 = (const WCHAR *)lpszPassword;
  if ( si128.m128i_i64[1] > 7uLL )
    v27 = lpszPassword[0];
  v28 = LogonUserW(username, 0, v27, 2u, 0, &phToken);
  LODWORD(bufptr) = v28;
  if ( v89 )
  {
    v29 = phToken;
    hKey = (HKEY)phToken;
    v30 = p_hObject;
    v31 = *p_hObject;
    if ( (char *)*p_hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      CloseHandle(v31);
      SetLastError(LastError);
      v29 = hKey;
      v28 = (int)bufptr;
    }
    *v30 = v29;
  }
  if ( !v28 )
  {
    v33 = GetLastError();
    Log(2u, L"Failed to logon AU %s: %#x", username, v33);
    v34 = GetLastError();
    LODWORD(v13) = v34;
    if ( v34 > 0 )
      LODWORD(v13) = (unsigned __int16)v34 | 0x80070000;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    v35 = CleanupUserAccount_DropsLock_OLD(username, sz, OwningUserRegistry);
    if ( v35 < 0 )
      Log(2u, L"Failed to cleanup AU %s after creation failure: %#x", username, (unsigned int)v35);
    goto LABEL_138;
  }
  Log(4u, L"Loading the user %s profile", username);
  memset(&ProfileInfo.lpProfilePath, 0, 40);
  ProfileInfo.dwSize = 56;
  ProfileInfo.dwFlags = 1;
  ProfileInfo.lpUserName = username;
  if ( !LoadUserProfileW(hObject, &ProfileInfo) )
  {
    v36 = GetLastError();
    Log(2u, L"Failed to load profileInfo for AU %s: %#x", username, v36);
    v37 = GetLastError();
    LODWORD(v13) = v37;
    if ( v37 > 0 )
      LODWORD(v13) = (unsigned __int16)v37 | 0x80070000;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    v38 = CleanupUserAccount_DropsLock_OLD(username, sz, OwningUserRegistry);
    if ( v38 < 0 )
      Log(2u, L"Failed to cleanup AU %s after creation failure: %#x", username, (unsigned int)v38);
    goto LABEL_138;
  }
  memset_0(ProfileDir, 0, 0x208u);
  cchSize = 260;
  if ( !GetUserProfileDirectoryW(hObject, ProfileDir, &cchSize) )
  {
    v13 = GetLastError();
    Log(2u, L"GetUserProfileDirectoryW failed for AU %s: %#x", username, v13);
    if ( (int)v13 > 0 )
      LODWORD(v13) = (unsigned __int16)v13 | 0x80070000;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    v39 = CleanupUserAccount_DropsLock_OLD(username, sz, OwningUserRegistry);
    if ( v39 < 0 )
      Log(2u, L"Failed to cleanup AU %s after creation failure: %#x", username, (unsigned int)v39);
    goto LABEL_138;
  }
  if ( !ProfileDir[0] )
  {
    Log(2u, L"GetUserProfileDirectoryW succeeded, but there is no profile directory for %s.", username);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    v40 = CleanupUserAccount_DropsLock_OLD(username, sz, OwningUserRegistry);
    if ( v40 < 0 )
      Log(2u, L"Failed to cleanup AU %s after creation failure: %#x", username, (unsigned int)v40);
    std::wstring::~wstring(v112);
    LODWORD(v13) = -2147467259;
    goto LABEL_139;
  }
  *(_OWORD *)StringSid = 0;
  v109 = 0;
  v41 = -1;
  do
    ++v41;
  while ( ProfileDir[v41] );
  std::wstring::_Construct<1,wchar_t const *>(StringSid, ProfileDir);
  v110 = 0;
  v111 = 0;
  v42 = -1;
  do
    ++v42;
  while ( username[v42] );
  std::wstring::_Construct<1,wchar_t const *>(&v110, username);
  OwningUserRegistry::StoreAgentProfileDir(OwningUserRegistry, &v110, StringSid);
  std::wstring::~wstring(&v110);
  std::wstring::~wstring(StringSid);
  Log(4u, L"Loading the user %s profile complete", username);
  *(_QWORD *)&v110 = &hObject;
  *((_QWORD *)&v110 + 1) = &ProfileInfo;
  LOBYTE(v111) = 1;
  wil::reg::create_unique_key(&v85, ProfileInfo.hProfile, L"Software\\Policies\\Microsoft\\Windows\\OOBE");
  LODWORD(bufptr) = 1;
  wil::reg::set_value<int>(v85, L"DisablePrivacyExperience", &bufptr);
  wil::reg::create_unique_key(&v84, ProfileInfo.hProfile, L"Software\\Policies\\Microsoft\\Edge");
  LODWORD(bufptr) = 1;
  wil::reg::set_value<int>(v84, L"HideFirstRunExperience", &bufptr);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIEPerf_ShellPolicyChanges2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AIEPerf_ShellPolicyChanges2>::GetImpl'::`2'::impl) )
  {
    wil::reg::create_unique_key(
      &hKey,
      ProfileInfo.hProfile,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\PushNotifications");
    LODWORD(bufptr) = 0;
    wil::reg::set_value<int>(hKey, L"ToastEnabled", &bufptr);
    if ( hKey )
      RegCloseKey(hKey);
  }
  hKey = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&hKey, hObject);
  if ( token_information < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x1C9B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
      (const char *)(unsigned int)token_information,
      lpDatab);
  Src = 0;
  StringSid[0] = (LPWSTR)&Src;
  StringSid[1] = 0;
  LOBYTE(v109) = 1;
  v44 = hKey;
  v45 = ConvertSidToStringSidW(*(PSID *)hKey, &StringSid[1]);
  v46 = v45;
  LODWORD(bufptr) = v45;
  if ( (_BYTE)v109 )
  {
    p_hObject = (HANDLE *)StringSid[1];
    v47 = StringSid[0];
    hMem = *(HLOCAL *)StringSid[0];
    if ( hMem )
    {
      v48 = GetLastError();
      LocalFree(hMem);
      SetLastError(v48);
      v46 = (unsigned int)bufptr;
    }
    *(_QWORD *)v47 = p_hObject;
  }
  if ( !(_DWORD)v46 )
  {
    v49 = GetLastError();
    LODWORD(v13) = v49;
    if ( v49 > 0 )
      LODWORD(v13) = (unsigned __int16)v49 | 0x80070000;
    if ( Src )
      LocalFree(Src);
    if ( v44 )
      operator delete(v44);
    if ( v84 )
      RegCloseKey(v84);
    if ( v85 )
      RegCloseKey(v85);
    UnloadUserProfile(hObject, ProfileInfo.hProfile);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    v50 = CleanupUserAccount_DropsLock_OLD(username, sz, OwningUserRegistry);
    if ( v50 < 0 )
      Log(2u, L"Failed to cleanup AU %s after creation failure: %#x", username, (unsigned int)v50);
    goto LABEL_138;
  }
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  bufptr = 0;
  v51 = LsaOpenPolicy((PLSA_UNICODE_STRING)v46, &ObjectAttributes, 0x810u, (PLSA_HANDLE)&bufptr);
  v53 = v51;
  if ( v51 )
  {
    Log(2u, L"Failed to open LSA policy: %#x", v51);
    LODWORD(v13) = v53 | 0x10000000;
    if ( bufptr )
      LsaClose(bufptr);
    if ( Src )
      LocalFree(Src);
    if ( v44 )
      operator delete(v44);
    if ( v84 )
      RegCloseKey(v84);
    if ( v85 )
      RegCloseKey(v85);
    UnloadUserProfile(hObject, ProfileInfo.hProfile);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    v54 = CleanupUserAccount_DropsLock_OLD(username, sz, OwningUserRegistry);
    if ( v54 < 0 )
      Log(2u, L"Failed to cleanup AU %s after creation failure: %#x", username, (unsigned int)v54);
    goto LABEL_138;
  }
  StringSid[0] = L"SeRemoteInteractiveLogonRight";
  StringSid[1] = L"SeDenyBatchLogonRight";
  *(_QWORD *)&v109 = L"SeDenyServiceLogonRight";
  memset(UserRights, 0, sizeof(UserRights));
  v55 = 0;
  v56 = 0;
  do
  {
    v57 = StringSid[v55];
    v58 = -1;
    do
      ++v58;
    while ( v57[v58] );
    v59 = 2 * v58;
    UserRights[v56].Length = v59;
    UserRights[v56].MaximumLength = v59 + 2;
    UserRights[v56].Buffer = v57;
    ++v55;
    ++v56;
  }
  while ( v55 != 3 );
  v60 = bufptr;
  v61 = LsaAddAccountRights(bufptr, *(PSID *)v44, UserRights, v52);
  v62 = v61;
  if ( v61 )
  {
    Log(2u, L"Failed to add account rights: %#x", v61);
    LODWORD(v13) = v62 | 0x10000000;
    if ( v60 )
      LsaClose(v60);
    if ( Src )
      LocalFree(Src);
    if ( v44 )
      operator delete(v44);
    if ( v84 )
      RegCloseKey(v84);
    if ( v85 )
      RegCloseKey(v85);
    UnloadUserProfile(hObject, ProfileInfo.hProfile);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    v63 = CleanupUserAccount_DropsLock_OLD(username, sz, OwningUserRegistry);
    if ( v63 < 0 )
      Log(2u, L"Failed to cleanup AU %s after creation failure: %#x", username, (unsigned int)v63);
    goto LABEL_138;
  }
  v64 = HideUserAccountFromLogonUI_1(username);
  if ( v64 < 0 )
    Log(3u, L"Failed to hide AU %s from logon UI: %#x", username, (unsigned int)v64);
  v99 = 0;
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  Log(4u, L"(v2) Created AU %s (%s) for %s", username, Src, a1);
  v66 = Src;
  v67 = -1;
  do
    ++v67;
  while ( *((_WORD *)Src + v67) );
  if ( v67 > (unsigned __int64)v92[3] )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
      v92,
      v67,
      v65,
      Src);
  }
  else
  {
    if ( (unsigned __int64)v92[3] <= 7 )
      v68 = (char *)v92;
    else
      v68 = *v92;
    v92[2] = (char *)v67;
    v69 = 2 * v67;
    memmove_0(v68, v66, 2 * v67);
    *(_WORD *)&v68[v69] = 0;
  }
  v71 = -1;
  do
    ++v71;
  while ( username[v71] );
  if ( v71 > (unsigned __int64)v93[3] )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
      v93,
      v71,
      v70,
      username);
  }
  else
  {
    if ( (unsigned __int64)v93[3] <= 7 )
      v72 = (char *)v93;
    else
      v72 = *v93;
    v93[2] = (char *)v71;
    v73 = 2 * v71;
    memmove_0(v72, username, 2 * v71);
    *(_WORD *)&v72[v73] = 0;
  }
  do
    ++v19;
  while ( sz[v19] );
  if ( v19 > *(_QWORD *)(v94 + 24) )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
      v94,
      v19,
      v74,
      sz);
  }
  else
  {
    if ( *(_QWORD *)(v94 + 24) <= 7u )
      v75 = (void *)v94;
    else
      v75 = *(void **)v94;
    *(_QWORD *)(v94 + 16) = v19;
    memmove_0(v75, sz, 2 * v19);
    *((_WORD *)v75 + v19) = 0;
  }
  std::wstring::operator=(v95, lpszPassword);
  if ( v60 )
    LsaClose(v60);
  if ( Src )
    LocalFree(Src);
  if ( v44 )
    operator delete(v44);
  if ( v84 )
    RegCloseKey(v84);
  if ( v85 )
    RegCloseKey(v85);
  UnloadUserProfile(hObject, ProfileInfo.hProfile);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  std::wstring::~wstring(v112);
  std::wstring::~wstring(lpszPassword);
  return 0;
}

```

## disassembly

```asm
0x180059200  push    rbp
0x180059202  push    rbx
0x180059203  push    rsi
0x180059204  push    rdi
0x180059205  push    r12
0x180059207  push    r13
0x180059209  push    r14
0x18005920b  push    r15
0x18005920d  lea     rbp, [rsp-628h]
0x180059215  sub     rsp, 728h
0x18005921c  mov     rax, cs:__security_cookie
0x180059223  xor     rax, rsp
0x180059226  mov     [rbp+660h+var_50], rax
0x18005922d  mov     [rbp+660h+var_688], r9
0x180059231  mov     [rbp+660h+var_690], r8
0x180059235  mov     [rsp+760h+hKey], rdx
0x18005923a  mov     r13, rcx
0x18005923d  mov     rax, [rbp+660h+arg_20]
0x180059244  mov     [rbp+660h+var_680], rax
0x180059248  mov     rax, [rbp+660h+arg_28]
0x18005924f  mov     [rbp+660h+var_678], rax
0x180059253  xor     edx, edx; Val
0x180059255  mov     r8d, 204h; Size
0x18005925b  lea     rcx, [rbp+660h+username]; void *
0x180059262  call    memset_0
0x180059267  cmp     qword ptr [r13+18h], 7
0x18005926c  jbe     short loc_180059274
0x18005926e  mov     r8, [r13+0]
0x180059272  jmp     short loc_180059277
0x180059274  mov     r8, r13
0x180059277  mov     esi, 102h
0x18005927c  mov     edx, esi
0x18005927e  lea     rcx, [rbp+660h+username]
0x180059285  call    cs:__imp__o_wcscpy_s
0x18005928b  mov     rbx, [r13+10h]
0x18005928f  lea     eax, [rsi-8]
0x180059292  cmp     rbx, rax
0x180059295  cmovnb  rbx, rax
0x180059299  xor     edi, edi
0x18005929b  mov     r15d, edi
0x18005929e  lea     r9, ValueName; "NextId"
0x1800592a5  xor     r8d, r8d
0x1800592a8  mov     rdx, cs:?g_agentAccountRegistry@@3VAgentAccountRegistry@@A; AgentAccountRegistry g_agentAccountRegistry
0x1800592af  lea     rcx, [rsp+760h+bufptr]
0x1800592b4  call    ??$try_get_value@I@reg@wil@@YA?AV?$optional@I@std@@PEAUHKEY__@@PEB_W1@Z; wil::reg::try_get_value<uint>(HKEY__ *,wchar_t const *,wchar_t const *)
0x1800592b9  cmp     byte ptr [rsp+760h+bufptr+4], dil
0x1800592be  cmovnz  r15d, dword ptr [rsp+760h+bufptr]
0x1800592c4  sub     rsi, rbx
0x1800592c7  lea     r12, [rbp+660h+username]
0x1800592ce  lea     r12, [r12+rbx*2]
0x1800592d2  lea     eax, [r15+rdi]
0x1800592d6  movzx   r14d, al
0x1800592da  mov     r9d, r14d
0x1800592dd  lea     r8, aAuX; "-AU-%x"
0x1800592e4  mov     rdx, rsi; BufferCount
0x1800592e7  mov     rcx, r12; Buffer
0x1800592ea  call    swprintf_s
0x1800592ef  mov     [rsp+760h+bufptr], 0
0x1800592f8  lea     r9, [rsp+760h+bufptr]; bufptr
0x1800592fd  xor     r8d, r8d; level
0x180059300  lea     rdx, [rbp+660h+username]; username
0x180059307  xor     ecx, ecx; servername
0x180059309  call    cs:__imp_NetUserGetInfo
0x18005930f  mov     ebx, eax
0x180059311  mov     rcx, [rsp+760h+bufptr]; Buffer
0x180059316  test    rcx, rcx
0x180059319  jz      short loc_180059321
0x18005931b  call    cs:__imp_NetApiBufferFree
0x180059321  xor     ecx, ecx
0x180059323  test    ebx, ebx
0x180059325  jz      short loc_18005934A
0x180059327  mov     al, cl
0x180059329  cmp     ebx, 8ADh
0x18005932f  jz      short loc_180059346
0x180059331  test    ebx, ebx
0x180059333  jle     short loc_180059340
0x180059335  movzx   ebx, bx
0x180059338  or      ebx, 80070000h
0x18005933e  test    ebx, ebx
0x180059340  js      loc_18005A169
0x180059346  test    al, al
0x180059348  jz      short loc_180059380
0x18005934a  inc     edi
0x18005934c  cmp     edi, 100h
0x180059352  jl      loc_1800592D2
0x180059358  mov     eax, 80070044h
0x18005935d  mov     rcx, [rbp+660h+var_50]
0x180059364  xor     rcx, rsp; StackCookie
0x180059367  call    __security_check_cookie
0x18005936c  add     rsp, 728h
0x180059373  pop     r15
0x180059375  pop     r14
0x180059377  pop     r13
0x180059379  pop     r12
0x18005937b  pop     rdi
0x18005937c  pop     rsi
0x18005937d  pop     rbx
0x18005937e  pop     rbp
0x18005937f  retn
0x180059380  lea     eax, [r14+1]
0x180059384  movzx   ecx, al
0x180059387  mov     dword ptr [rsp+760h+bufptr], ecx
0x18005938b  mov     esi, 4
0x180059390  mov     [rsp+760h+cbData], esi; cbData
0x180059394  lea     rax, [rsp+760h+bufptr]
0x180059399  mov     [rsp+760h+lpData], rax; int
0x18005939e  mov     r9d, esi; dwType
0x1800593a1  lea     r8, ValueName; "NextId"
0x1800593a8  xor     edx, edx; lpSubKey
0x1800593aa  mov     rcx, cs:?g_agentAccountRegistry@@3VAgentAccountRegistry@@A; hKey
0x1800593b1  call    cs:__imp_RegSetKeyValueW
0x1800593b7  xor     r12d, r12d
0x1800593ba  test    eax, eax
0x1800593bc  jle     short loc_1800593C6
0x1800593be  movzx   eax, ax
0x1800593c1  or      eax, 80070000h
0x1800593c6  mov     rcx, [rbp+668h]; this
0x1800593cd  test    eax, eax
0x1800593cf  js      loc_18005A19E
0x1800593d5  xorps   xmm0, xmm0
0x1800593d8  movups  xmmword ptr [rbp+660h+Uuid.Data1], xmm0
0x1800593df  lea     rcx, [rbp+660h+Uuid]; Uuid
0x1800593e6  call    cs:__imp_UuidCreateSequential
0x1800593ec  test    eax, eax
0x1800593ee  jns     short loc_18005940B
0x1800593f0  lea     rdx, aFailedToCreate_4; "Failed to create marker GUID"
0x1800593f7  mov     ecx, 2; unsigned __int8
0x1800593fc  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180059401  mov     eax, 8000FFFFh
0x180059406  jmp     loc_18005935D
0x18005940b  xor     edx, edx; Val
0x18005940d  lea     r8d, [rdx+50h]; Size
0x180059411  lea     rcx, [rbp+660h+sz]; void *
0x180059418  call    memset_0
0x18005941d  mov     r8d, 28h ; '('; cchMax
0x180059423  lea     rdx, [rbp+660h+sz]; lpsz
0x18005942a  lea     rcx, [rbp+660h+Uuid]; rguid
0x180059431  call    cs:__imp_StringFromGUID2
0x180059437  mov     r8, r13
0x18005943a  mov     rdx, [rsp+760h+hKey]
0x18005943f  call    ?GetOrCreateOwningUserRegistry@AgentAccountRegistry@@QEAAAEAVOwningUserRegistry@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; AgentAccountRegistry::GetOrCreateOwningUserRegistry(std::wstring const &,std::wstring const &)
0x180059444  mov     r15, rax
0x180059447  xorps   xmm0, xmm0
0x18005944a  movups  xmmword ptr [rbp+660h+StringSid], xmm0
0x180059451  xorps   xmm1, xmm1
0x180059454  movdqu  [rbp+660h+var_570], xmm1
0x18005945c  lea     rax, [rbp+660h+sz]
0x180059463  or      r14, 0FFFFFFFFFFFFFFFFh
0x180059467  mov     r8, r14
0x18005946a  inc     r8
0x18005946d  cmp     [rax+r8*2], r12w
0x180059472  jnz     short loc_18005946A
0x180059474  lea     rdx, [rbp+660h+sz]
0x18005947b  lea     rcx, [rbp+660h+StringSid]
0x180059482  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180059487  nop
0x180059488  xorps   xmm0, xmm0
0x18005948b  movups  [rbp+660h+var_560], xmm0
0x180059492  xorps   xmm1, xmm1
0x180059495  movdqu  [rbp+660h+var_550], xmm1
0x18005949d  lea     rax, [rbp+660h+username]
0x1800594a4  mov     r8, r14
0x1800594a7  inc     r8
0x1800594aa  cmp     [rax+r8*2], r12w
0x1800594af  jnz     short loc_1800594A7
0x1800594b1  lea     rdx, [rbp+660h+username]
0x1800594b8  lea     rcx, [rbp+660h+var_560]
0x1800594bf  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800594c4  nop
0x1800594c5  lea     r8, [rbp+660h+StringSid]
0x1800594cc  lea     rdx, [rbp+660h+var_560]
0x1800594d3  mov     rcx, r15
0x1800594d6  call    ?AddAgentUserRegKey@OwningUserRegistry@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; OwningUserRegistry::AddAgentUserRegKey(std::wstring const &,std::wstring const &)
0x1800594db  nop
0x1800594dc  lea     rcx, [rbp+660h+var_560]
0x1800594e3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800594e8  nop
0x1800594e9  lea     rcx, [rbp+660h+StringSid]
0x1800594f0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800594f5  xorps   xmm0, xmm0
0x1800594f8  movups  xmmword ptr [rbp+660h+lpszPassword], xmm0
0x1800594ff  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180059507  movdqu  [rbp+660h+var_510], xmm1
0x18005950f  mov     word ptr [rbp+660h+lpszPassword], r12w
0x180059517  lea     rcx, [rbp+660h+lpszPassword]; void *
0x18005951e  call    ??$GenerateRandomPassword@$0CK@@@YAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; GenerateRandomPassword<42>(std::wstring &)
0x180059523  mov     ebx, eax
0x180059525  test    eax, eax
0x180059527  jns     short loc_180059549
0x180059529  mov     rcx, [rbp+668h]; this
0x180059530  mov     r9d, eax; char *
0x180059533  lea     r8, aOnecoreuapWind_14; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005953a  mov     edx, 0A8h; void *
0x18005953f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059544  jmp     loc_180059F48
0x180059549  mov     edi, 2
0x18005954e  mov     ecx, edi; unsigned int
0x180059550  call    ?SetServiceStartType@@YAJK@Z; SetServiceStartType(ulong)
0x180059555  test    eax, eax
0x180059557  jns     short loc_180059560
0x180059559  mov     ebx, eax
0x18005955b  jmp     loc_180059F48
0x180059560  lea     r8, [rbp+660h+username]
0x180059567  lea     rdx, aCallingNetuser; "Calling NetUserAdd for agent user %s"
0x18005956e  mov     ecx, esi; unsigned __int8
0x180059570  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180059575  mov     [rsp+760h+parm_err], r12d
0x18005957a  lea     rax, aUserAccountFor; "User account for AIE: {}"
0x180059581  mov     [rsp+760h+var_6F0], rax
0x180059586  mov     [rsp+760h+phToken], 18h
0x18005958f  lea     r8, [rbp+660h+sz]
0x180059596  lea     rdx, [rsp+760h+var_6F0]
0x18005959b  lea     rcx, [rbp+660h+var_540]; Src
0x1800595a2  call    ??$format@AEAY0CI@_W@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@U?$basic_format_string@_WAEAY0CI@_W@0@AEAY0CI@_W@Z; std::format<wchar_t (&)[40]>(std::basic_format_string<wchar_t,wchar_t (&)[40]>,wchar_t (&)[40])
0x1800595a7  nop
0x1800595a8  xor     edx, edx; Val
0x1800595aa  mov     r8d, 98h; Size
0x1800595b0  lea     rcx, [rbp+660h+buf]; void *
0x1800595b4  call    memset_0
0x1800595b9  lea     rax, [rbp+660h+username]
0x1800595c0  mov     qword ptr [rbp+660h+buf], rax
0x1800595c4  lea     rax, [rbp+660h+lpszPassword]
0x1800595cb  cmp     qword ptr [rbp+660h+var_510+8], 7
0x1800595d3  cmova   rax, [rbp+660h+lpszPassword]
0x1800595db  mov     [rbp+660h+var_618], rax
0x1800595df  mov     [rbp+660h+var_60C], 1
0x1800595e6  mov     [rbp+660h+var_5F8], 10241h
0x1800595ed  lea     rax, [rbp+660h+var_540]
0x1800595f4  cmp     [rbp+660h+var_528], 7
0x1800595fc  cmova   rax, [rbp+660h+var_540]
0x180059604  mov     [rbp+660h+var_600], rax
0x180059608  or      eax, 0FFFFFFFFh
0x18005960b  mov     [rbp+660h+var_5B8], eax
0x180059611  mov     [rbp+660h+var_5B4], eax
0x180059617  lea     r9, [rsp+760h+parm_err]; parm_err
0x18005961c  lea     r8, [rbp+660h+buf]; buf
0x180059620  mov     edx, edi; level
0x180059622  xor     ecx, ecx; servername
0x180059624  call    cs:__imp_NetUserAdd
0x18005962a  mov     ebx, eax
0x18005962c  test    eax, eax
0x18005962e  jz      short loc_180059666
0x180059630  mov     ecx, [rsp+760h+parm_err]
0x180059634  mov     dword ptr [rsp+760h+lpData], ecx
0x180059638  mov     r9d, eax
0x18005963b  lea     r8, [rbp+660h+username]
0x180059642  lea     rdx, aFailedToCreate_2; "Failed to create AU %s: %#x (parm_error"...
0x180059649  mov     ecx, edi; unsigned __int8
0x18005964b  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180059650  test    ebx, ebx
0x180059652  jle     loc_180059F3B
0x180059658  movzx   ebx, bx
0x18005965b  or      ebx, 80070000h
0x180059661  jmp     loc_180059F3B
0x180059666  lea     rax, [rbp+660h+username]
0x18005966d  mov     [rbp+660h+var_670], rax
0x180059671  lea     rax, [rbp+660h+sz]
0x180059678  mov     [rbp+660h+var_668], rax
0x18005967c  mov     [rbp+660h+var_660], r15
0x180059680  mov     [rbp+660h+var_658], 1
0x180059684  lea     r8, [rbp+660h+username]
0x18005968b  lea     rdx, aLoggingOnTheUs_0; "Logging on the user %s"
0x180059692  mov     ecx, esi; unsigned __int8
0x180059694  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180059699  mov     [rsp+760h+hObject], r12
0x18005969e  lea     rax, [rsp+760h+hObject]
0x1800596a3  mov     [rsp+760h+var_6F0], rax
0x1800596a8  mov     [rsp+760h+phToken], r12
0x1800596ad  mov     [rbp+660h+var_6E0], 1
0x1800596b1  lea     r8, [rbp+660h+lpszPassword]
0x1800596b8  cmp     qword ptr [rbp+660h+var_510+8], 7
0x1800596c0  cmova   r8, [rbp+660h+lpszPassword]; lpszPassword
0x1800596c8  lea     rax, [rsp+760h+phToken]
0x1800596cd  mov     qword ptr [rsp+760h+cbData], rax; phToken
0x1800596d2  mov     dword ptr [rsp+760h+lpData], r12d; int
0x1800596d7  mov     r9d, edi; dwLogonType
0x1800596da  xor     edx, edx; lpszDomain
0x1800596dc  lea     rcx, [rbp+660h+username]; lpszUsername
0x1800596e3  call    cs:__imp_LogonUserW
0x1800596e9  mov     edx, eax
0x1800596eb  mov     dword ptr [rsp+760h+bufptr], eax
0x1800596ef  cmp     [rbp+660h+var_6E0], r12b
0x1800596f3  jz      short loc_18005973F
0x1800596f5  mov     rax, [rsp+760h+phToken]
0x1800596fa  mov     [rsp+760h+hKey], rax
0x1800596ff  mov     rsi, [rsp+760h+var_6F0]
0x180059704  mov     r12, [rsi]
0x180059707  lea     rcx, [r12-1]
0x18005970c  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180059710  ja      short loc_180059734
0x180059712  call    cs:__imp_GetLastError
0x180059718  mov     ebx, eax
0x18005971a  mov     rcx, r12; hObject
0x18005971d  call    cs:__imp_CloseHandle
0x180059723  mov     ecx, ebx; dwErrCode
0x180059725  call    cs:__imp_SetLastError
0x18005972b  mov     rax, [rsp+760h+hKey]
0x180059730  mov     edx, dword ptr [rsp+760h+bufptr]
0x180059734  mov     [rsi], rax
0x180059737  xor     r12d, r12d
  ... truncated ...
```
