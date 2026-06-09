# AgentAccountHelpers::CreateAgentAccount(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180041b64`
- end: `0x1800431ff`
- name: `?CreateAgentAccount@AgentAccountHelpers@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@000_NAEAV23@22@Z`
- size: `5787`
- prototype: ``
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180037064`

## callees

- `0x180002520`
- `0x180002a54`
- `0x1800030d0`
- `0x1800031e8`
- `0x1800050cd`
- `0x1800075e4`
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
- `0x18003b4ec`
- `0x18003ca08`
- `0x18003dce4`
- `0x18003e03c`
- `0x18003f5a0`
- `0x18003ff5c`
- `0x180041b64`
- `0x180043208`
- `0x180043eb4`
- `0x180044a68`
- `0x180044df4`
- `0x180045388`
- `0x180046b1c`
- `0x18004705c`
- `0x18004719c`
- `0x18004f7c0`
- `0x1800615a8`
- `0x180063980`
- `0x180063a08`
- `0x180063d68`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180041bfb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180041bfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800423c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800423f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800424f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800425f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042969`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004299e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800423c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800423f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800424f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800425f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042969`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004299e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800423a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004297c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800423a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004297c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041e25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041e25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004239b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004241a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004253b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042630`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800426df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042a10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042c83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042e38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043128`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004239b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004241a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004253b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042630`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800426df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042a10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042c83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042e38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043128`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041ed5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004211e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800428e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800429da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800429ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042b92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042c4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042c5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042e02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042e12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800430f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043102`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041ed5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004211e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800428e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800429da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800429ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042b92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042c4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042c5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042e02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042e12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800430f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043102`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180042937`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180042937`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041c58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041c80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041d3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041d5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041f02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041f27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041f7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041fa4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004200f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042258`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004227d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042466`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004248b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042587`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800425ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004267c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800426a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004272b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042750`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042974`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800429bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042a5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042a81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042c2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042ccf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042cef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042de4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042e84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042ea4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800430d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043174`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043194`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041c58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041c80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041d3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041d5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041f02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041f27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041f7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041fa4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004200f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042258`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004227d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042466`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004248b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042587`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800425ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004267c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800426a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004272b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042750`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042974`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800429bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042a5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042a81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042c2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042ccf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042cef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042de4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042e84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042ea4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800430d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043174`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043194`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180041d9e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180041d9e`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x180042362`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x180042362`
- `USERENV!UnloadUserProfile` at `0x1800429fa`
- `USERENV!UnloadUserProfile` at `0x180042c6d`
- `USERENV!UnloadUserProfile` at `0x180042e22`
- `USERENV!UnloadUserProfile` at `0x180043112`
- `USERENV!UnloadUserProfile` at `0x1800429fa`
- `USERENV!UnloadUserProfile` at `0x180042c6d`
- `USERENV!UnloadUserProfile` at `0x180042e22`
- `USERENV!UnloadUserProfile` at `0x180043112`
- `USERENV!LoadUserProfileW` at `0x1800424eb`
- `USERENV!LoadUserProfileW` at `0x1800424eb`
- `USERENV!GetUserProfileDirectoryW` at `0x1800425e3`
- `USERENV!GetUserProfileDirectoryW` at `0x1800425e3`

## string_xrefs

- `0x1800431d8`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800431ea`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x1800431c3`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`
- `0x180041c3c`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\agentaccounthelpers.cpp`
- `0x180041fe5`: `Failed to get account name for newly created AU %s`
- `0x180041f63`: `Failed to create LSA agent account for AU %s: %#x`
- `0x180042201`: `Failed to get LSA agent account credentials for AU %s: %#x`
- `0x180042603`: `GetUserProfileDirectoryW failed for AU %s: %#x`
- `0x180042812`: `Loading the user profile complete for %s`
- `0x1800426c1`: `GetUserProfileDirectoryW succeeded, but there is no profile directory for %s.`
- `0x180042c03`: `Failed to open LSA policy: %#x`
- `0x180042d17`: `SeDenyServiceLogonRight`
- `0x180042f41`: `(v3) Created AU %s (%s, %s) for %s`
- `0x180042b77`: `Recorded SID for %s: %s`
- `0x180042fe5`: `EventLog::WriteUserCreated failed, %lu`
- `0x180042ff8`: `EventLog::WriteUserCreated - Succeeded`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall AgentAccountHelpers::CreateAgentAccount(
        _QWORD *a1,
        _QWORD *a2,
        wchar_t *a3,
        __int64 *a4,
        char a5,
        char **a6,
        char **a7,
        __int64 a8)
{
  _QWORD *v11; // r8
  const wchar_t *v12; // rdx
  int v13; // eax
  __int64 v14; // rbx
  __int64 v15; // rdi
  HLOCAL *v16; // rax
  char v18; // r15
  int v19; // edi
  wchar_t *v20; // r8
  bool v21; // bl
  __int64 v22; // rdi
  HLOCAL *v23; // rax
  int v24; // eax
  _QWORD *v25; // r15
  HKEY OwningUserRegistry; // r12
  unsigned __int64 v27; // r13
  unsigned __int64 v28; // r8
  int v29; // ebx
  const char *v30; // r9
  __int128 *v31; // r8
  const wchar_t *v32; // r9
  const wchar_t *v33; // r8
  __int128 *v34; // r8
  _QWORD *v35; // rax
  __int64 v36; // r8
  __int64 v37; // rdi
  HLOCAL *v38; // rax
  const wchar_t *v39; // rdx
  int AgentAccount; // eax
  __int64 v41; // rdi
  HLOCAL *v42; // rax
  wchar_t *v43; // r8
  __int64 v44; // rdi
  HLOCAL *v45; // rax
  unsigned __int64 v46; // r8
  __int128 *v47; // r8
  const wchar_t *v48; // r9
  const wchar_t *v49; // r8
  PCWSTR *v50; // r9
  __int128 *v51; // r8
  PCWSTR *v52; // r9
  wchar_t *v53; // rdx
  int SingleUseAgentUserCred; // eax
  __int64 v55; // rdi
  HLOCAL *v56; // rax
  LPCWSTR *v57; // r8
  LPCWSTR *v58; // r8
  const WCHAR *v59; // r8
  const WCHAR *v60; // rdx
  const WCHAR *v61; // rcx
  int v62; // eax
  PWSTR v63; // r12
  PWSTR *v64; // rdi
  void *v65; // r15
  DWORD LastError; // ebx
  DWORD v67; // eax
  PCWSTR *v68; // r9
  signed int v69; // eax
  __int64 v70; // rdi
  HLOCAL *v71; // rax
  WCHAR *v72; // rax
  DWORD v73; // eax
  signed int v74; // eax
  __int64 v75; // rdi
  HLOCAL *v76; // rax
  __int64 v77; // rdi
  HLOCAL *v78; // rax
  __int64 v79; // rdi
  HLOCAL *v80; // rax
  unsigned __int64 v81; // r8
  unsigned __int64 v82; // r8
  int token_information; // eax
  HKEY v84; // r15
  int v85; // ecx
  LPWSTR v86; // rax
  LPWSTR v87; // rdi
  void *v88; // r12
  DWORD v89; // ebx
  signed int v90; // eax
  __int64 v91; // rdi
  HLOCAL *v92; // rax
  unsigned __int64 v93; // r8
  unsigned __int64 v94; // r8
  LPWSTR *v95; // r8
  const wchar_t *v96; // r9
  struct _LSA_UNICODE_STRING *v97; // r8
  struct _LSA_UNICODE_STRING *v98; // r9
  LPWSTR *v99; // r8
  struct _LSA_UNICODE_STRING *v100; // rcx
  __int64 v101; // rdi
  unsigned int v102; // eax
  ULONG v103; // r9d
  unsigned int v104; // ebx
  HLOCAL *v105; // rax
  __int64 v106; // rdx
  __int64 v107; // rcx
  WCHAR *v108; // r8
  __int64 v109; // rax
  USHORT v110; // ax
  wil::reg *v111; // r12
  unsigned int v112; // eax
  unsigned int v113; // ebx
  HLOCAL *v114; // rax
  const WCHAR *v115; // rcx
  int v116; // eax
  PCWSTR *v117; // r9
  _QWORD *v118; // rbx
  _QWORD *v119; // rcx
  PCWSTR *v120; // r9
  __int64 v121; // r9
  PCWSTR *v122; // rdx
  __int64 v123; // r8
  __int64 v124; // r8
  unsigned int v125; // eax
  unsigned __int64 v126; // rdx
  char *v127; // r14
  __int64 v128; // rbx
  __int64 v129; // r8
  HLOCAL v130; // r9
  char *v131; // r14
  __int64 v132; // r8
  HLOCAL *v133; // rax
  int lpData; // [rsp+20h] [rbp-E0h]
  int lpDataa; // [rsp+20h] [rbp-E0h]
  LPCVOID lpDatab; // [rsp+20h] [rbp-E0h]
  wil::reg *Data; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-A8h] BYREF
  char v139[8]; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL v140; // [rsp+68h] [rbp-98h]
  HLOCAL hMem[2]; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL Src; // [rsp+80h] [rbp-80h] BYREF
  DWORD cchSize; // [rsp+88h] [rbp-78h] BYREF
  HKEY v144; // [rsp+90h] [rbp-70h] BYREF
  HKEY v145; // [rsp+98h] [rbp-68h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp-60h] BYREF
  HKEY v147; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD *v148; // [rsp+B0h] [rbp-50h]
  _QWORD v149[5]; // [rsp+B8h] [rbp-48h] BYREF
  char v150; // [rsp+E0h] [rbp-20h]
  _PROFILEINFOW ProfileInfo; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD *v152; // [rsp+120h] [rbp+20h]
  __int64 *v153; // [rsp+128h] [rbp+28h]
  char **v154; // [rsp+130h] [rbp+30h]
  char **v155; // [rsp+138h] [rbp+38h]
  __int64 v156; // [rsp+140h] [rbp+40h]
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+148h] [rbp+48h] BYREF
  PCWSTR SourceString[3]; // [rsp+178h] [rbp+78h] BYREF
  unsigned __int64 v159; // [rsp+190h] [rbp+90h]
  __int128 v160; // [rsp+198h] [rbp+98h] BYREF
  __int128 v161; // [rsp+1A8h] [rbp+A8h]
  LPWSTR StringSid[2]; // [rsp+1B8h] [rbp+B8h] BYREF
  __int128 v163; // [rsp+1C8h] [rbp+C8h]
  LPCWSTR lpszDomain[2]; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 v165; // [rsp+1E8h] [rbp+E8h]
  unsigned __int64 v166; // [rsp+1F0h] [rbp+F0h]
  LPCWSTR lpszUsername[2]; // [rsp+1F8h] [rbp+F8h] BYREF
  __int64 v168; // [rsp+208h] [rbp+108h]
  unsigned __int64 v169; // [rsp+210h] [rbp+110h]
  LPCWSTR lpszPassword[2]; // [rsp+218h] [rbp+118h] BYREF
  __m128i si128; // [rsp+228h] [rbp+128h]
  struct _LSA_UNICODE_STRING phToken[3]; // [rsp+238h] [rbp+138h] BYREF
  wchar_t Buffer[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR ProfileDir[264]; // [rsp+480h] [rbp+380h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6E8h] [rbp+5E8h]

  v153 = a4;
  v148 = a2;
  v152 = a1;
  v155 = a7;
  v154 = a6;
  v156 = a8;
  memset_0(Buffer, 0, 0x204u);
  if ( a1[3] <= 7u )
    v11 = a1;
  else
    v11 = (_QWORD *)*a1;
  _o_wcscpy_s(Buffer, 258, v11);
  v139[0] = 0;
  v140 = 0;
  *(_OWORD *)hMem = 0;
  if ( a2[3] <= 7u )
    v12 = (const wchar_t *)a2;
  else
    v12 = (const wchar_t *)*a2;
  v13 = LsaAgentAccountHelper::Initialize((LsaAgentAccountHelper *)v139, v12);
  LODWORD(v14) = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x81,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\agentaccounthelpers.cpp",
      (const char *)(unsigned int)v13,
      lpData);
    if ( hMem[1] )
    {
      LocalFree(hMem[1]);
      v15 = 16;
      v16 = hMem;
      do
      {
        *(_BYTE *)v16 = 0;
        v16 = (HLOCAL *)((char *)v16 + 1);
        --v15;
      }
      while ( v15 );
    }
    if ( v140 )
      LocalFree(v140);
    return (unsigned int)v14;
  }
  v18 = 0;
  wil::reg::try_get_value<unsigned int>((__int64)&Data, g_agentAccountRegistry, 0, L"NextId");
  if ( BYTE4(Data) )
    v18 = (char)Data;
  v19 = 0;
  while ( 1 )
  {
    swprintf_s(Buffer, 0x102u, L"IEB-%x", (unsigned __int8)(v18 + v19));
    v20 = *((_QWORD *)a3 + 3) <= 7u ? a3 : *(wchar_t **)a3;
    LsaAgentAccountHelper::GetAgentAccountName(v139, &v160, v20, Buffer);
    v21 = (_QWORD)v161 != 0;
    std::wstring::~wstring((char **)&v160);
    if ( !v21 )
      break;
    if ( ++v19 >= 256 )
    {
      if ( hMem[1] )
      {
        LocalFree(hMem[1]);
        v22 = 16;
        v23 = hMem;
        do
        {
          *(_BYTE *)v23 = 0;
          v23 = (HLOCAL *)((char *)v23 + 1);
          --v22;
        }
        while ( v22 );
      }
      if ( v140 )
        LocalFree(v140);
      return 2147942468LL;
    }
  }
  LODWORD(Data) = (unsigned __int8)(v18 + v19 + 1);
  v24 = RegSetKeyValueW(g_agentAccountRegistry, 0, L"NextId", 4u, &Data, 4u);
  if ( v24 > 0 )
    v24 = (unsigned __int16)v24 | 0x80070000;
  if ( v24 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v24,
      lpDataa);
  v25 = v148;
  OwningUserRegistry = (HKEY)AgentAccountRegistry::GetOrCreateOwningUserRegistry(retaddr, v148, a1);
  v147 = OwningUserRegistry;
  v160 = 0;
  v161 = 0;
  v27 = -1;
  v28 = -1;
  do
    ++v28;
  while ( Buffer[v28] );
  std::wstring::_Construct<1,wchar_t const *>((char **)&v160, Buffer, v28);
  v29 = dword_1800B9160;
  if ( v29 != GetCurrentThreadId() )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x15D,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
      v30);
  v31 = &v160;
  if ( *((_QWORD *)&v161 + 1) > 7u )
    v31 = (__int128 *)v160;
  wil::reg::create_unique_key(&Data, *(_QWORD *)OwningUserRegistry, v31);
  if ( *((_QWORD *)a3 + 3) <= 7u )
    v33 = a3;
  else
    v33 = *(const wchar_t **)a3;
  wil::reg::set_value_string(Data, (HKEY)&stru_18009E498, v33, v32);
  v34 = &v160;
  if ( *((_QWORD *)&v161 + 1) > 7u )
    v34 = (__int128 *)v160;
  Log(4u, L"Added reg key for %s", v34);
  v35 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring const &,>(
                    (float *)OwningUserRegistry + 26,
                    (__int64)phToken,
                    &v160);
  std::wstring::operator=(*v35 + 48LL, a3, v36);
  if ( Data )
    RegCloseKey((HKEY)Data);
  std::wstring::~wstring((char **)&v160);
  LODWORD(v14) = SetServiceStartType(2u);
  if ( (int)v14 < 0 )
  {
    if ( hMem[1] )
    {
      LocalFree(hMem[1]);
      v37 = 16;
      v38 = hMem;
      do
      {
        *(_BYTE *)v38 = 0;
        v38 = (HLOCAL *)((char *)v38 + 1);
        --v37;
      }
      while ( v37 );
    }
    if ( v140 )
      LocalFree(v140);
    return (unsigned int)v14;
  }
  if ( *((_QWORD *)a3 + 3) <= 7u )
    v39 = a3;
  else
    v39 = *(const wchar_t **)a3;
  AgentAccount = LsaAgentAccountHelper::CreateAgentAccount((LsaAgentAccountHelper *)v139, v39, Buffer);
  LODWORD(v14) = AgentAccount;
  if ( AgentAccount < 0 )
  {
    Log(2u, L"Failed to create LSA agent account for AU %s: %#x", Buffer, (unsigned int)AgentAccount);
    if ( hMem[1] )
    {
      LocalFree(hMem[1]);
      v41 = 16;
      v42 = hMem;
      do
      {
        *(_BYTE *)v42 = 0;
        v42 = (HLOCAL *)((char *)v42 + 1);
        --v41;
      }
      while ( v41 );
    }
    if ( v140 )
      LocalFree(v140);
    return (unsigned int)v14;
  }
  if ( *((_QWORD *)a3 + 3) <= 7u )
    v43 = a3;
  else
    v43 = *(wchar_t **)a3;
  LsaAgentAccountHelper::GetAgentAccountName(v139, SourceString, v43, Buffer);
  if ( !SourceString[2] )
  {
    Log(2u, L"Failed to get account name for newly created AU %s", Buffer);
    std::wstring::~wstring((char **)SourceString);
    if ( hMem[1] )
    {
      LocalFree(hMem[1]);
      v44 = 16;
      v45 = hMem;
      do
      {
        *(_BYTE *)v45 = 0;
        v45 = (HLOCAL *)((char *)v45 + 1);
        --v44;
      }
      while ( v44 );
    }
LABEL_153:
    if ( v140 )
      LocalFree(v140);
    return 2147500037LL;
  }
  v149[0] = v25;
  v149[1] = Buffer;
  v149[2] = a3;
  v149[3] = SourceString;
  v149[4] = OwningUserRegistry;
  v150 = 1;
  v160 = 0;
  v161 = 0;
  v46 = -1;
  do
    ++v46;
  while ( Buffer[v46] );
  std::wstring::_Construct<1,wchar_t const *>((char **)&v160, Buffer, v46);
  v47 = &v160;
  if ( *((_QWORD *)&v161 + 1) > 7u )
    v47 = (__int128 *)v160;
  wil::reg::create_unique_key(&Data, *(_QWORD *)OwningUserRegistry, v47);
  v49 = (const wchar_t *)SourceString;
  if ( v159 > 7 )
    v49 = SourceString[0];
  wil::reg::set_value_string(Data, (HKEY)&stru_18009A8D0, v49, v48);
  v50 = SourceString;
  if ( v159 > 7 )
    v50 = (PCWSTR *)SourceString[0];
  v51 = &v160;
  if ( *((_QWORD *)&v161 + 1) > 7u )
    v51 = (__int128 *)v160;
  Log(4u, L"Recorded account name for %s: %s", v51, v50);
  if ( Data )
    RegCloseKey((HKEY)Data);
  std::wstring::~wstring((char **)&v160);
  v52 = SourceString;
  if ( v159 > 7 )
    v52 = (PCWSTR *)SourceString[0];
  Log(4u, L"Logging on the user %s (%s)", Buffer, v52);
  *(_OWORD *)lpszUsername = 0;
  v168 = 0;
  v169 = 7;
  LOWORD(lpszUsername[0]) = 0;
  *(_OWORD *)lpszDomain = 0;
  v165 = 0;
  v166 = 7;
  LOWORD(lpszDomain[0]) = 0;
  *(_OWORD *)lpszPassword = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpszPassword[0]) = 0;
  if ( *((_QWORD *)a3 + 3) <= 7u )
    v53 = a3;
  else
    v53 = *(wchar_t **)a3;
  SingleUseAgentUserCred = LsaAgentAccountHelper::GetSingleUseAgentUserCred(
                             v139,
                             v53,
                             Buffer,
                             lpszUsername,
                             lpszDomain,
                             lpszPassword);
  LODWORD(v14) = SingleUseAgentUserCred;
  if ( SingleUseAgentUserCred < 0 )
  {
    Log(2u, L"Failed to get LSA agent account credentials for AU %s: %#x", Buffer, (unsigned int)SingleUseAgentUserCred);
    std::wstring::~wstring((char **)lpszPassword);
    std::wstring::~wstring((char **)lpszDomain);
    std::wstring::~wstring((char **)lpszUsername);
    wil::details::lambda_call__AgentAccountHelpers::CreateAgentAccount_::_2_::_lambda_1___::_lambda_call__AgentAccountHelpers::CreateAgentAccount_::_2_::_lambda_1___(v149);
    std::wstring::~wstring((char **)SourceString);
    if ( hMem[1] )
    {
      LocalFree(hMem[1]);
      v55 = 16;
      v56 = hMem;
      do
      {
        *(_BYTE *)v56 = 0;
        v56 = (HLOCAL *)((char *)v56 + 1);
        --v55;
      }
      while ( v55 );
    }
    if ( v140 )
      LocalFree(v140);
    return (unsigned int)v14;
  }
  if ( v168 )
  {
    v57 = lpszUsername;
    if ( v169 > 7 )
      v57 = (LPCWSTR *)lpszUsername[0];
    Log(4u, L"marshaled username: %s", v57);
  }
  if ( v165 )
  {
    v58 = lpszDomain;
    if ( v166 > 7 )
      v58 = (LPCWSTR *)lpszDomain[0];
    Log(4u, L"marshaled domain: %s", v58);
  }
  hObject = 0;
  *(_QWORD *)&phToken[0].Length = &hObject;
  phToken[0].Buffer = 0;
  LOBYTE(phToken[1].Length) = 1;
  v59 = (const WCHAR *)lpszPassword;
  if ( si128.m128i_i64[1] > 7uLL )
    v59 = lpszPassword[0];
  v60 = (const WCHAR *)lpszDomain;
  if ( v166 > 7 )
    v60 = lpszDomain[0];
  v61 = (const WCHAR *)lpszUsername;
  if ( v169 > 7 )
    v61 = lpszUsername[0];
  v62 = LogonUserW(v61, v60, v59, 2u, 0, (PHANDLE)&phToken[0].Buffer);
  LODWORD(Data) = v62;
  if ( LOBYTE(phToken[1].Length) )
  {
    v63 = phToken[0].Buffer;
    v64 = *(PWSTR **)&phToken[0].Length;
    v65 = **(void ***)&phToken[0].Length;
    if ( (unsigned __int64)(**(_QWORD **)&phToken[0].Length - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v65);
      SetLastError(LastError);
      v62 = (int)Data;
    }
    *v64 = v63;
    OwningUserRegistry = v147;
  }
  if ( !v62 )
  {
    v67 = GetLastError();
    v68 = SourceString;
    if ( v159 > 7 )
      v68 = (PCWSTR *)SourceString[0];
    LODWORD(lpDatab) = v67;
    Log(2u, L"Failed to logon AU %s (%s): %#x", Buffer, v68, lpDatab);
    v69 = GetLastError();
    LODWORD(v14) = v69;
    if ( v69 > 0 )
      LODWORD(v14) = (unsigned __int16)v69 | 0x80070000;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    std::wstring::~wstring((char **)lpszPassword);
    std::wstring::~wstring((char **)lpszDomain);
    std::wstring::~wstring((char **)lpszUsername);
    wil::details::lambda_call__AgentAccountHelpers::CreateAgentAccount_::_2_::_lambda_1___::_lambda_call__AgentAccountHelpers::CreateAgentAccount_::_2_::_lambda_1___(v149);
    std::wstring::~wstring((char **)SourceString);
    if ( hMem[1] )
    {
      LocalFree(hMem[1]);
      v70 = 16;
      v71 = hMem;
      do
      {
        *(_BYTE *)v71 = 0;
        v71 = (HLOCAL *)((char *)v71 + 1);
        --v70;
      }
      while ( v70 );
    }
    if ( v140 )
      LocalFree(v140);
    return (unsigned int)v14;
  }
  Log(4u, L"Loading the user profile for %s", Buffer);
  memset(&ProfileInfo.lpUserName, 0, 48);
  ProfileInfo.dwSize = 56;
  ProfileInfo.dwFlags = 1;
  v72 = (WCHAR *)SourceString;
  if ( v159 > 7 )
    v72 = (WCHAR *)SourceString[0];
  ProfileInfo.lpUserName = v72;
  if ( !LoadUserProfileW(hObject, &ProfileInfo) )
  {
    v73 = GetLastError();
    Log(2u, L"Failed to load profileInfo for AU %s: %#x", Buffer, v73);
    v74 = GetLastError();
    LODWORD(v14) = v74;
    if ( v74 > 0 )
      LODWORD(v14) = (unsigned __int16)v74 | 0x80070000;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    std::wstring::~wstring((char **)lpszPassword);
    std::wstring::~wstring((char **)lpszDomain);
    std::wstring::~wstring((char **)lpszUsername);
    wil::details::lambda_call__AgentAccountHelpers::CreateAgentAccount_::_2_::_lambda_1___::_lambda_call__AgentAccountHelpers::CreateAgentAccount_::_2_::_lambda_1___(v149);
    std::wstring::~wstring((char **)SourceString);
    if ( hMem[1] )
    {
      LocalFree(hMem[1]);
      v75 = 16;
      v76 = hMem;
      do
      {
        *(_BYTE *)v76 = 0;
        v76 = (HLOCAL *)((char *)v76 + 1);
        --v75;
      }
      while ( v75 );
    }
    if ( v140 )
      LocalFree(v140);
    return (unsigned int)v14;
  }
  memset_0(ProfileDir, 0, 0x208u);
  cchSize = 260;
  if ( !GetUserProfileDirectoryW(hObject, ProfileDir, &cchSize) )
  {
    v14 = GetLastError();
    Log(2u, L"GetUserProfileDirectoryW failed for AU %s: %#x", Buffer, v14);
    if ( (int)v14 > 0 )
      LODWORD(v14) = (unsigned __int16)v14 | 0x80070000;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    std::wstring::~wstring((char **)lpszPassword);
    std::wstring::~wstring((char **)lpszDomain);
    std::wstring::~wstring((char **)lpszUsername);
    wil::details::lambda_call__AgentAccountHelpers::CreateAgentAccount_::_2_::_lambda_1___::_lambda_call__AgentAccountHelpers::CreateAgentAccount_::_2_::_lambda_1___(v149);
    std::wstring::~wstring((char **)SourceString);
    if ( hMem[1] )
    {
      LocalFree(hMem[1]);
      v77 = 16;
      v78 = hMem;
      do
      {
        *(_BYTE *)v78 = 0;
        v78 = (HLOCAL *)((char *)v78 + 1);
        --v77;
      }
      while ( v77 );
    }
    if ( v140 )
      LocalFree(v140);
    return (unsigned int)v14;
  }
  if ( !ProfileDir[0] )
  {
    Log(2u, L"GetUserProfileDirectoryW succeeded, but there is no profile directory for %s.", Buffer);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    std::wstring::~wstring((char **)lpszPassword);
    std::wstring::~wstring((char **)lpszDomain);
    std::wstring::~wstring((char **)lpszUsername);
    wil::details::lambda_call__AgentAccountHelpers::CreateAgentAccount_::_2_::_lambda_1___::_lambda_call__AgentAccountHelpers::CreateAgentAccount_::_2_::_lambda_1___(v149);
    std::wstring::~wstring((char **)SourceString);
    if ( hMem[1] )
    {
      LocalFree(hMem[1]);
      v79 = 16;
      v80 = hMem;
      do
      {
        *(_BYTE *)v80 = 0;
        v80 = (HLOCAL *)((char *)v80 + 1);
        --v79;
      }
      while ( v79 );
    }
    goto LABEL_153;
  }
  *(_OWORD *)StringSid = 0;
  v163 = 0;
  v81 = -1;
  do
    ++v81;
  while ( ProfileDir[v81] );
  std::wstring::_Construct<1,wchar_t const *>((char **)StringSid, ProfileDir, v81);
  v160 = 0;
  v161 = 0;
  v82 = -1;
  do
    ++v82;
  while ( Buffer[v82] );
  std::wstring::_Construct<1,wchar_t const *>((char **)&v160, Buffer, v82);
  OwningUserRegistry::StoreAgentProfileDir(OwningUserRegistry, &v160, StringSid);
  std::wstring::~wstring((char **)&v160);
  std::wstring::~wstring((char **)StringSid);
  Log(4u, L"Loading the user profile complete for %s", Buffer);
  *(_QWORD *)&v160 = &hObject;
  *((_QWORD *)&v160 + 1) = &ProfileInfo;
  LOBYTE(v161) = 1;
  wil::reg::create_unique_key(&v145, ProfileInfo.hProfile, L"Software\\Policies\\Microsoft\\Windows\\OOBE");
  LODWORD(Data) = 1;
  wil::reg::set_value<int>(v145, L"DisablePrivacyExperience", &Data);
  wil::reg::create_unique_key(&v144, ProfileInfo.hProfile, L"Software\\Policies\\Microsoft\\Edge");
  LODWORD(Data) = 1;
  wil::reg::set_value<int>(v144, L"HideFirstRunExperience", &Data);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIEPerf_ShellPolicyChanges2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AIEPerf_ShellPolicyChanges2>::GetImpl'::`2'::impl) )
  {
    wil::reg::create_unique_key(
      &hKey,
      ProfileInfo.hProfile,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\PushNotifications");
    LODWORD(Data) = 0;
    wil::reg::set_value<int>(hKey, L"ToastEnabled", &Data);
    if ( hKey )
      RegCloseKey(hKey);
  }
  hKey = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>((void **)&hKey, (__int64)hObject);
  if ( token_information < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x1C9B,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
      (const char *)(unsigned int)token_information,
      (int)lpDatab);
  Src = 0;
  StringSid[0] = (LPWSTR)&Src;
  StringSid[1] = 0;
  LOBYTE(v163) = 1;
  v84 = hKey;
  v85 = ConvertSidToStringSidW(*(PSID *)hKey, &StringSid[1]);
  LODWORD(Data) = v85;
  if ( (_BYTE)v163 )
  {
    v86 = StringSid[1];
    *(LPWSTR *)&phToken[0].Length = StringSid[1];
    v87 = StringSid[0];
    v88 = *(void **)StringSid[0];
    if ( *(_QWORD *)StringSid[0] )
    {
      v89 = GetLastError();
      LocalFree(v88);
      SetLastError(v89);
      v86 = *(LPWSTR *)&phToken[0].Length;
      v85 = (int)Data;
    }
    *(_QWORD *)v87 = v86;
    OwningUserRegistry = v147;
  }
  if ( !v85 )
  {
    v90 = GetLastError();
    LODWORD(v14) = v90;
    if ( v90 > 0 )
      LODWORD(v14) = (unsigned __int16)v90 | 0x80070000;
    if ( Src )
      LocalFree(Src);
    if ( v84 )
      operator delete(v84);
    if ( v144 )
      RegCloseKey(v144);
    if ( v145 )
      RegCloseKey(v145);
    UnloadUserProfile(hObject, ProfileInfo.hProfile);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    std::wstring::~wstring((char **)lpszPassword);
    std::wstring::~wstring((char **)lpszDomain);
    std::wstring::~wstring((char **)lpszUsername);
    wil::details::lambda_call__AgentAccountHelpers::CreateAgentAccount_::_2_::_lambda_1___::_lambda_call__AgentAccountHelpers::CreateAgentAccount_::_2_::_lambda_1___(v149);
    std::wstring::~wstring((char **)SourceString);
    if ( hMem[1] )
    {
      LocalFree(hMem[1]);
      v91 = 16;
      v92 = hMem;
      do
      {
        *(_BYTE *)v92 = 0;
        v92 = (HLOCAL *)((char *)v92 + 1);
        --v91;
      }
      while ( v91 );
    }
    if ( v140 )
      LocalFree(v140);
    return (unsigned int)v14;
  }
  memset(phToken, 0, 32);
  v93 = -1;
  do
    ++v93;
  while ( *((_WORD *)Src + v93) );
  std::wstring::_Construct<1,wchar_t const *>((char **)phToken, Src, v93);
  *(_OWORD *)StringSid = 0;
  v163 = 0;
  v94 = -1;
  do
    ++v94;
  while ( Buffer[v94] );
  std::wstring::_Construct<1,wchar_t const *>((char **)StringSid, Buffer, v94);
  v95 = StringSid;
  if ( *((_QWORD *)&v163 + 1) > 7u )
    v95 = (LPWSTR *)StringSid[0];
  wil::reg::create_unique_key(&v147, *(_QWORD *)OwningUserRegistry, v95);
  v97 = phToken;
  if ( phToken[1].Buffer > (PWSTR)7 )
    v97 = *(struct _LSA_UNICODE_STRING **)&phToken[0].Length;
  wil::reg::set_value_string((wil::reg *)v147, (HKEY)&stru_1800A05C0, &v97->Length, v96);
  v98 = phToken;
  if ( phToken[1].Buffer > (PWSTR)7 )
    v98 = *(struct _LSA_UNICODE_STRING **)&phToken[0].Length;
  v99 = StringSid;
  if ( *((_QWORD *)&v163 + 1) > 7u )
    v99 = (LPWSTR *)StringSid[0];
  Log(4u, L"Recorded SID for %s: %s", v99, v98);
  if ( v147 )
    RegCloseKey(v147);
  std::wstring::~wstring((char **)StringSid);
  std::wstring::~wstring((char **)phToken);
  v101 = 16;
  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_AgentSessionInteractiveLogon>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AgentSessionInteractiveLogon>::GetImpl'::`2'::impl) )
  {
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    Data = 0;
    v102 = LsaOpenPolicy(v100, &ObjectAttributes, 0x810u, (PLSA_HANDLE)&Data);
    v104 = v102;
    if ( v102 )
    {
      Log(2u, L"Failed to open LSA policy: %#x", v102);
      LODWORD(v14) = v104 | 0x10000000;
      if ( Data )
        LsaClose(Data);
      if ( Src )
        LocalFree(Src);
      if ( v84 )
        operator delete(v84);
      if ( v144 )
        RegCloseKey(v144);
      if ( v145 )
        RegCloseKey(v145);
      UnloadUserProfile(hObject, ProfileInfo.hProfile);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      std::wstring::~wstring((char **)lpszPassword);
      std::wstring::~wstring((char **)lpszDomain);
      std::wstring::~wstring((char **)lpszUsername);
      wil::details::lambda_call__AgentAccountHelpers::CreateAgentAccount_::_2_::_lambda_1___::_lambda_call__AgentAccountHelpers::CreateAgentAccount_::_2_::_lambda_1___(v149);
      std::wstring::~wstring((char **)SourceString);
      if ( hMem[1] )
      {
        LocalFree(hMem[1]);
        v105 = hMem;
        do
        {
          *(_BYTE *)v105 = 0;
          v105 = (HLOCAL *)((char *)v105 + 1);
          --v101;
        }
        while ( v101 );
      }
      if ( v140 )
        LocalFree(v140);
      return (unsigned int)v14;
    }
    StringSid[0] = L"SeRemoteInteractiveLogonRight";
    StringSid[1] = L"SeDenyBatchLogonRight";
    *(_QWORD *)&v163 = L"SeDenyServiceLogonRight";
    memset(phToken, 0, sizeof(phToken));
    v106 = 0;
    v107 = 0;
    do
    {
      v108 = StringSid[v106];
      v109 = -1;
      do
        ++v109;
      while ( v108[v109] );
      v110 = 2 * v109;
      phToken[v107].Length = v110;
      phToken[v107].MaximumLength = v110 + 2;
      phToken[v107].Buffer = v108;
      ++v106;
      ++v107;
    }
    while ( v106 != 3 );
    v111 = Data;
    v112 = LsaAddAccountRights(Data, *(PSID *)v84, phToken, v103);
    v113 = v112;
    if ( v112 )
    {
      Log(2u, L"Failed to add account rights: %#x", v112);
      LODWORD(v14) = v113 | 0x10000000;
      if ( v111 )
        LsaClose(v111);
      if ( Src )
        LocalFree(Src);
      if ( v84 )
        operator delete(v84);
      if ( v144 )
        RegCloseKey(v144);
      if ( v145 )
        RegCloseKey(v145);
      UnloadUserProfile(hObject, ProfileInfo.hProfile);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      std::wstring::~wstring((char **)lpszPassword);
      std::wstring::~wstring((char **)lpszDomain);
      std::wstring::~wstring((char **)lpszUsername);
      wil::details::lambda_call__AgentAccountHelpers::CreateAgentAccount_::_2_::_lambda_1___::_lambda_call__AgentAccountHelpers::CreateAgentAccount_::_2_::_lambda_1___(v149);
      std::wstring::~wstring((char **)SourceString);
      if ( hMem[1] )
      {
        LocalFree(hMem[1]);
        v114 = hMem;
        do
        {
          *(_BYTE *)v114 = 0;
          v114 = (HLOCAL *)((char *)v114 + 1);
          --v101;
        }
        while ( v101 );
      }
      if ( v140 )
        LocalFree(v140);
      return (unsigned int)v14;
    }
    if ( v111 )
      LsaClose(v111);
  }
  v115 = (const WCHAR *)SourceString;
  if ( v159 > 7 )
    v115 = SourceString[0];
  v116 = HideUserAccountFromLogonUI(v115);
  if ( v116 < 0 )
  {
    v117 = SourceString;
    if ( v159 > 7 )
      v117 = (PCWSTR *)SourceString[0];
    LODWORD(lpDatab) = v116;
    Log(3u, L"Failed to hide AU %s (%s) from logon UI: %#x", Buffer, v117, lpDatab);
  }
  v118 = v152;
  if ( v152[3] <= 7u )
    v119 = v152;
  else
    v119 = (_QWORD *)*v152;
  v120 = SourceString;
  if ( v159 > 7 )
    v120 = (PCWSTR *)SourceString[0];
  Log(4u, L"(v3) Created AU %s (%s, %s) for %s", Buffer, v120, Src, v119);
  v121 = (__int64)v153;
  if ( (unsigned __int64)v153[3] > 7 )
    v121 = *v153;
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(wchar_t **)a3;
  v122 = SourceString;
  if ( v159 > 7 )
    v122 = (PCWSTR *)SourceString[0];
  if ( v118[3] > 7u )
    v118 = (_QWORD *)*v118;
  LODWORD(v123) = (_DWORD)v148;
  if ( v148[3] > 7u )
    v123 = *v148;
  if ( g_eventLog )
  {
    if ( (Microsoft_Windows_AgenticPlatform_IsoEnvBrokerEnableBits & 1) != 0
      && (v125 = McTemplateU0zzzzzzt_EventWriteTransfer(
                   (_DWORD)Src,
                   (_DWORD)v122,
                   v123,
                   (_DWORD)v118,
                   (__int64)Src,
                   (__int64)v122,
                   (__int64)a3,
                   v121,
                   a5)) != 0 )
    {
      Log(3u, L"EventLog::WriteUserCreated failed, %lu", v125);
    }
    else
    {
      Log(4u, L"EventLog::WriteUserCreated - Succeeded");
    }
  }
  else
  {
    Log(2u, L"EventLog not initialized");
  }
  v150 = 0;
  v126 = -1;
  do
    ++v126;
  while ( Buffer[v126] );
  if ( v126 > (unsigned __int64)v154[3] )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
      v154,
      v126,
      v124,
      Buffer);
  }
  else
  {
    if ( (unsigned __int64)v154[3] <= 7 )
      v127 = (char *)v154;
    else
      v127 = *v154;
    v154[2] = (char *)v126;
    v128 = 2 * v126;
    memmove_0(v127, Buffer, 2 * v126);
    *(_WORD *)&v127[v128] = 0;
  }
  v130 = Src;
  do
    ++v27;
  while ( *((_WORD *)Src + v27) );
  if ( v27 > (unsigned __int64)v155[3] )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
      v155,
      v27,
      v129,
      Src);
  }
  else
  {
    if ( (unsigned __int64)v155[3] <= 7 )
      v131 = (char *)v155;
    else
      v131 = *v155;
    v155[2] = (char *)v27;
    memmove_0(v131, v130, 2 * v27);
    *(_WORD *)&v131[2 * v27] = 0;
  }
  std::wstring::operator=(v156, SourceString, v132);
  if ( Src )
    LocalFree(Src);
  if ( v84 )
    operator delete(v84);
  if ( v144 )
    RegCloseKey(v144);
  if ( v145 )
    RegCloseKey(v145);
  UnloadUserProfile(hObject, ProfileInfo.hProfile);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  std::wstring::~wstring((char **)lpszPassword);
  std::wstring::~wstring((char **)lpszDomain);
  std::wstring::~wstring((char **)lpszUsername);
  wil::details::lambda_call__AgentAccountHelpers::CreateAgentAccount_::_2_::_lambda_1___::_lambda_call__AgentAccountHelpers::CreateAgentAccount_::_2_::_lambda_1___(v149);
  std::wstring::~wstring((char **)SourceString);
  if ( hMem[1] )
  {
    LocalFree(hMem[1]);
    v133 = hMem;
    do
    {
      *(_BYTE *)v133 = 0;
      v133 = (HLOCAL *)((char *)v133 + 1);
      --v101;
    }
    while ( v101 );
  }
  if ( v140 )
    LocalFree(v140);
  return 0;
}

```

## disassembly

```asm
0x180041b64  push    rbp
0x180041b66  push    rbx
0x180041b67  push    rsi
0x180041b68  push    rdi
0x180041b69  push    r12
0x180041b6b  push    r13
0x180041b6d  push    r14
0x180041b6f  push    r15
0x180041b71  lea     rbp, [rsp-5A8h]
0x180041b79  sub     rsp, 6A8h
0x180041b80  mov     rax, cs:__security_cookie
0x180041b87  xor     rax, rsp
0x180041b8a  mov     [rbp+5E0h+var_50], rax
0x180041b91  mov     [rbp+5E0h+var_5B8], r9
0x180041b95  mov     r14, r8
0x180041b98  mov     rbx, rdx
0x180041b9b  mov     [rbp+5E0h+var_630], rdx
0x180041b9f  mov     r12, rcx
0x180041ba2  mov     [rbp+5E0h+var_5C0], rcx
0x180041ba6  mov     rax, [rbp+5E0h+arg_30]
0x180041bad  mov     [rbp+5E0h+var_5A8], rax
0x180041bb1  mov     rax, [rbp+5E0h+arg_28]
0x180041bb8  mov     [rbp+5E0h+var_5B0], rax
0x180041bbc  mov     rax, [rbp+5E0h+arg_38]
0x180041bc3  mov     [rbp+5E0h+var_5A0], rax
0x180041bc7  xor     r13d, r13d
0x180041bca  xor     edx, edx; Val
0x180041bcc  mov     r8d, 204h; Size
0x180041bd2  lea     rcx, [rbp+5E0h+Buffer]; void *
0x180041bd9  call    memset_0
0x180041bde  cmp     qword ptr [r12+18h], 7
0x180041be4  jbe     short loc_180041BEC
0x180041be6  mov     r8, [r12]
0x180041bea  jmp     short loc_180041BEF
0x180041bec  mov     r8, r12
0x180041bef  mov     edx, 102h
0x180041bf4  lea     rcx, [rbp+5E0h+Buffer]
0x180041bfb  call    cs:__imp__o_wcscpy_s
0x180041c01  mov     [rsp+6E0h+var_680], r13b
0x180041c06  mov     [rsp+6E0h+var_678], r13
0x180041c0b  xorps   xmm0, xmm0
0x180041c0e  movups  xmmword ptr [rsp+6E0h+hMem], xmm0
0x180041c13  cmp     qword ptr [rbx+18h], 7
0x180041c18  jbe     short loc_180041C1F
0x180041c1a  mov     rdx, [rbx]
0x180041c1d  jmp     short loc_180041C22
0x180041c1f  mov     rdx, rbx; wchar_t *
0x180041c22  lea     rcx, [rsp+6E0h+var_680]; this
0x180041c27  call    ?Initialize@LsaAgentAccountHelper@@QEAAJPEB_W@Z; LsaAgentAccountHelper::Initialize(wchar_t const *)
0x180041c2c  mov     ebx, eax
0x180041c2e  test    eax, eax
0x180041c30  jns     short loc_180041C8E
0x180041c32  mov     rcx, [rbp+5E8h]; this
0x180041c39  mov     r9d, eax; char *
0x180041c3c  lea     r8, aOnecoreuapWind_30; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180041c43  mov     edx, 81h; void *
0x180041c48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041c4d  nop
0x180041c4e  mov     rcx, [rsp+6E0h+hMem+8]; hMem
0x180041c53  test    rcx, rcx
0x180041c56  jz      short loc_180041C76
0x180041c58  call    cs:__imp_LocalFree
0x180041c5e  mov     edi, 10h
0x180041c63  lea     rax, [rsp+6E0h+hMem]
0x180041c68  lea     esi, [rdi-0Fh]
0x180041c6b  mov     [rax], r13b
0x180041c6e  add     rax, rsi
0x180041c71  sub     rdi, rsi
0x180041c74  jnz     short loc_180041C6B
0x180041c76  mov     rcx, [rsp+6E0h+var_678]; hMem
0x180041c7b  test    rcx, rcx
0x180041c7e  jz      short loc_180041C87
0x180041c80  call    cs:__imp_LocalFree
0x180041c86  nop
0x180041c87  mov     eax, ebx
0x180041c89  jmp     loc_18004319D
0x180041c8e  mov     r15d, r13d
0x180041c91  lea     r9, ValueName; "NextId"
0x180041c98  xor     r8d, r8d
0x180041c9b  mov     rdx, cs:?g_agentAccountRegistry@@3VAgentAccountRegistry@@A; AgentAccountRegistry g_agentAccountRegistry
0x180041ca2  lea     rcx, [rsp+6E0h+Data]
0x180041ca7  call    ??$try_get_value@I@reg@wil@@YA?AV?$optional@I@std@@PEAUHKEY__@@PEB_W1@Z; wil::reg::try_get_value<uint>(HKEY__ *,wchar_t const *,wchar_t const *)
0x180041cac  cmp     byte ptr [rsp+6E0h+Data+4], r13b
0x180041cb1  cmovnz  r15d, dword ptr [rsp+6E0h+Data]
0x180041cb7  mov     edi, r13d
0x180041cba  mov     esi, 1
0x180041cbf  lea     eax, [r15+rdi]
0x180041cc3  movzx   r13d, al
0x180041cc7  mov     r9d, r13d
0x180041cca  lea     r8, aIebX; "IEB-%x"
0x180041cd1  mov     edx, 102h; BufferCount
0x180041cd6  lea     rcx, [rbp+5E0h+Buffer]; Buffer
0x180041cdd  call    swprintf_s
0x180041ce2  cmp     qword ptr [r14+18h], 7
0x180041ce7  jbe     short loc_180041CEE
0x180041ce9  mov     r8, [r14]
0x180041cec  jmp     short loc_180041CF1
0x180041cee  mov     r8, r14
0x180041cf1  lea     r9, [rbp+5E0h+Buffer]
0x180041cf8  lea     rdx, [rbp+5E0h+var_548]
0x180041cff  lea     rcx, [rsp+6E0h+var_680]
0x180041d04  call    ?GetAgentAccountName@LsaAgentAccountHelper@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0@Z; LsaAgentAccountHelper::GetAgentAccountName(wchar_t const *,wchar_t const *)
0x180041d09  cmp     qword ptr [rbp+5E0h+var_538], 0
0x180041d11  setnz   bl
0x180041d14  lea     rcx, [rbp+5E0h+var_548]
0x180041d1b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180041d20  test    bl, bl
0x180041d22  jz      short loc_180041D6D
0x180041d24  add     edi, esi
0x180041d26  cmp     edi, 100h
0x180041d2c  jl      short loc_180041CBF
0x180041d2e  mov     rcx, [rsp+6E0h+hMem+8]; hMem
0x180041d33  xor     ebx, ebx
0x180041d35  test    rcx, rcx
0x180041d38  jz      short loc_180041D52
0x180041d3a  call    cs:__imp_LocalFree
0x180041d40  lea     edi, [rbx+10h]
0x180041d43  lea     rax, [rsp+6E0h+hMem]
0x180041d48  mov     [rax], bl
0x180041d4a  add     rax, rsi
0x180041d4d  sub     rdi, rsi
0x180041d50  jnz     short loc_180041D48
0x180041d52  mov     rcx, [rsp+6E0h+var_678]; hMem
0x180041d57  test    rcx, rcx
0x180041d5a  jz      short loc_180041D63
0x180041d5c  call    cs:__imp_LocalFree
0x180041d62  nop
0x180041d63  mov     eax, 80070044h
0x180041d68  jmp     loc_18004319D
0x180041d6d  lea     eax, [r13+1]
0x180041d71  movzx   ecx, al
0x180041d74  mov     dword ptr [rsp+6E0h+Data], ecx
0x180041d78  mov     ecx, 4
0x180041d7d  mov     [rsp+6E0h+cbData], ecx; cbData
0x180041d81  lea     rax, [rsp+6E0h+Data]
0x180041d86  mov     [rsp+6E0h+lpData], rax; int
0x180041d8b  mov     r9d, ecx; dwType
0x180041d8e  lea     r8, ValueName; "NextId"
0x180041d95  xor     edx, edx; lpSubKey
0x180041d97  mov     rcx, cs:?g_agentAccountRegistry@@3VAgentAccountRegistry@@A; hKey
0x180041d9e  call    cs:__imp_RegSetKeyValueW
0x180041da4  xor     ebx, ebx
0x180041da6  test    eax, eax
0x180041da8  jle     short loc_180041DB2
0x180041daa  movzx   eax, ax
0x180041dad  or      eax, 80070000h
0x180041db2  mov     rcx, [rbp+5E8h]; this
0x180041db9  test    eax, eax
0x180041dbb  js      loc_1800431D5
0x180041dc1  mov     r8, r12
0x180041dc4  mov     r15, [rbp+5E0h+var_630]
0x180041dc8  mov     rdx, r15
0x180041dcb  call    ?GetOrCreateOwningUserRegistry@AgentAccountRegistry@@QEAAAEAVOwningUserRegistry@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; AgentAccountRegistry::GetOrCreateOwningUserRegistry(std::wstring const &,std::wstring const &)
0x180041dd0  mov     r12, rax
0x180041dd3  mov     [rbp+5E0h+var_638], rax
0x180041dd7  xorps   xmm0, xmm0
0x180041dda  movups  [rbp+5E0h+var_548], xmm0
0x180041de1  xorps   xmm1, xmm1
0x180041de4  movdqu  [rbp+5E0h+var_538], xmm1
0x180041dec  lea     rax, [rbp+5E0h+Buffer]
0x180041df3  or      r13, 0FFFFFFFFFFFFFFFFh
0x180041df7  mov     r8, r13
0x180041dfa  inc     r8
0x180041dfd  cmp     [rax+r8*2], bx
0x180041e02  jnz     short loc_180041DFA
0x180041e04  lea     rdx, [rbp+5E0h+Buffer]
0x180041e0b  lea     rcx, [rbp+5E0h+var_548]
0x180041e12  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180041e17  nop
0x180041e18  mov     ebx, cs:dword_1800B9160
0x180041e1e  mov     rdi, [rbp+5E8h]
0x180041e25  call    cs:__imp_GetCurrentThreadId
0x180041e2b  cmp     ebx, eax
0x180041e2d  jnz     loc_1800431EA
0x180041e33  lea     r8, [rbp+5E0h+var_548]
0x180041e3a  cmp     qword ptr [rbp+5E0h+var_538+8], 7
0x180041e42  cmova   r8, qword ptr [rbp+5E0h+var_548]
0x180041e4a  mov     rdx, [r12]
0x180041e4e  lea     rcx, [rsp+6E0h+Data]
0x180041e53  call    ?create_unique_key@reg@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@PEAUHKEY__@@PEB_WW4key_access@12@@Z; wil::reg::create_unique_key(HKEY__ *,wchar_t const *,wil::reg::key_access)
0x180041e58  nop
0x180041e59  cmp     qword ptr [r14+18h], 7
0x180041e5e  jbe     short loc_180041E65
0x180041e60  mov     r8, [r14]
0x180041e63  jmp     short loc_180041E68
0x180041e65  mov     r8, r14; wchar_t *
0x180041e68  lea     rdx, stru_18009E498; HKEY
0x180041e6f  mov     rcx, [rsp+6E0h+Data]; this
0x180041e74  call    ?set_value_string@reg@wil@@YAXPEAUHKEY__@@PEB_W1@Z; wil::reg::set_value_string(HKEY__ *,wchar_t const *,wchar_t const *)
0x180041e79  lea     r8, [rbp+5E0h+var_548]
0x180041e80  cmp     qword ptr [rbp+5E0h+var_538+8], 7
0x180041e88  cmova   r8, qword ptr [rbp+5E0h+var_548]
0x180041e90  lea     rdx, aAddedRegKeyFor; "Added reg key for %s"
0x180041e97  mov     ecx, 4; unsigned __int8
0x180041e9c  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180041ea1  lea     rcx, [r12+68h]
0x180041ea6  lea     r8, [rbp+5E0h+var_548]
0x180041ead  lea     rdx, [rbp+5E0h+phToken]
0x180041eb4  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180041eb9  mov     rcx, [rax]
0x180041ebc  add     rcx, 30h ; '0'
0x180041ec0  mov     rdx, r14
0x180041ec3  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180041ec8  nop
0x180041ec9  mov     rcx, [rsp+6E0h+Data]; hKey
0x180041ece  xor     edi, edi
0x180041ed0  test    rcx, rcx
0x180041ed3  jz      short loc_180041EDC
0x180041ed5  call    cs:__imp_RegCloseKey
0x180041edb  nop
0x180041edc  lea     rcx, [rbp+5E0h+var_548]
0x180041ee3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180041ee8  mov     ecx, 2; unsigned int
0x180041eed  call    ?SetServiceStartType@@YAJK@Z; SetServiceStartType(ulong)
0x180041ef2  mov     ebx, eax
0x180041ef4  test    eax, eax
0x180041ef6  jns     short loc_180041F33
0x180041ef8  mov     rcx, [rsp+6E0h+hMem+8]; hMem
0x180041efd  test    rcx, rcx
0x180041f00  jz      short loc_180041F1D
0x180041f02  call    cs:__imp_LocalFree
0x180041f08  mov     edi, 10h
0x180041f0d  lea     rax, [rsp+6E0h+hMem]
0x180041f12  mov     byte ptr [rax], 0
0x180041f15  add     rax, rsi
0x180041f18  sub     rdi, rsi
0x180041f1b  jnz     short loc_180041F12
0x180041f1d  mov     rcx, [rsp+6E0h+var_678]; hMem
0x180041f22  test    rcx, rcx
0x180041f25  jz      short loc_180041F2E
0x180041f27  call    cs:__imp_LocalFree
0x180041f2d  nop
0x180041f2e  jmp     loc_180041C87
0x180041f33  cmp     qword ptr [r14+18h], 7
0x180041f38  jbe     short loc_180041F3F
0x180041f3a  mov     rdx, [r14]
0x180041f3d  jmp     short loc_180041F42
0x180041f3f  mov     rdx, r14; wchar_t *
0x180041f42  lea     r8, [rbp+5E0h+Buffer]; wchar_t *
0x180041f49  lea     rcx, [rsp+6E0h+var_680]; this
0x180041f4e  call    ?CreateAgentAccount@LsaAgentAccountHelper@@QEAAJPEB_W0@Z; LsaAgentAccountHelper::CreateAgentAccount(wchar_t const *,wchar_t const *)
0x180041f53  mov     ebx, eax
0x180041f55  test    eax, eax
0x180041f57  jns     short loc_180041FB0
0x180041f59  mov     r9d, eax
0x180041f5c  lea     r8, [rbp+5E0h+Buffer]
0x180041f63  lea     rdx, aFailedToCreate_3; "Failed to create LSA agent account for "...
0x180041f6a  mov     ecx, 2; unsigned __int8
0x180041f6f  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180041f74  nop
0x180041f75  mov     rcx, [rsp+6E0h+hMem+8]; hMem
0x180041f7a  test    rcx, rcx
0x180041f7d  jz      short loc_180041F9A
0x180041f7f  call    cs:__imp_LocalFree
0x180041f85  mov     edi, 10h
0x180041f8a  lea     rax, [rsp+6E0h+hMem]
0x180041f8f  mov     byte ptr [rax], 0
0x180041f92  add     rax, rsi
0x180041f95  sub     rdi, rsi
0x180041f98  jnz     short loc_180041F8F
0x180041f9a  mov     rcx, [rsp+6E0h+var_678]; hMem
0x180041f9f  test    rcx, rcx
0x180041fa2  jz      short loc_180041FAB
0x180041fa4  call    cs:__imp_LocalFree
0x180041faa  nop
0x180041fab  jmp     loc_180041C87
0x180041fb0  cmp     qword ptr [r14+18h], 7
0x180041fb5  jbe     short loc_180041FBC
0x180041fb7  mov     r8, [r14]
0x180041fba  jmp     short loc_180041FBF
0x180041fbc  mov     r8, r14
0x180041fbf  lea     r9, [rbp+5E0h+Buffer]
0x180041fc6  lea     rdx, [rbp+5E0h+SourceString]
0x180041fca  lea     rcx, [rsp+6E0h+var_680]
0x180041fcf  call    ?GetAgentAccountName@LsaAgentAccountHelper@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0@Z; LsaAgentAccountHelper::GetAgentAccountName(wchar_t const *,wchar_t const *)
0x180041fd4  nop
0x180041fd5  cmp     [rbp+5E0h+var_558], rdi
0x180041fdc  jnz     short loc_18004202F
0x180041fde  lea     r8, [rbp+5E0h+Buffer]
0x180041fe5  lea     rdx, aFailedToGetAcc; "Failed to get account name for newly cr"...
0x180041fec  mov     ecx, 2; unsigned __int8
0x180041ff1  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180041ff6  nop
0x180041ff7  lea     rcx, [rbp+5E0h+SourceString]
0x180041ffb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180042000  nop
0x180042001  mov     rcx, [rsp+6E0h+hMem+8]; hMem
0x180042006  test    rcx, rcx
0x180042009  jz      loc_180042746
0x18004200f  call    cs:__imp_LocalFree
0x180042015  mov     edi, 10h
0x18004201a  lea     rax, [rsp+6E0h+hMem]
0x18004201f  mov     byte ptr [rax], 0
0x180042022  add     rax, rsi
0x180042025  sub     rdi, rsi
0x180042028  jnz     short loc_18004201F
0x18004202a  jmp     loc_180042746
0x18004202f  mov     [rbp+5E0h+var_628], r15
0x180042033  lea     rax, [rbp+5E0h+Buffer]
0x18004203a  mov     [rbp+5E0h+var_620], rax
  ... truncated ...
```
