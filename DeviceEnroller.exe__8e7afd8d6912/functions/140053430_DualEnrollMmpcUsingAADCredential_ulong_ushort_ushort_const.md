# DualEnrollMmpcUsingAADCredential(ulong,ushort *,ushort const *)

- ea: `0x140053430`
- end: `0x140054318`
- name: `?DualEnrollMmpcUsingAADCredential@@YAJKPEAGPEBG@Z`
- size: `3816`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140055fa0`

## callees

- `0x1400042f0`
- `0x140004e28`
- `0x140007c44`
- `0x140009140`
- `0x1400095b4`
- `0x14000a088`
- `0x14000a6a8`
- `0x14000ad3c`
- `0x14000f78c`
- `0x1400176f0`
- `0x14001d7ec`
- `0x1400347e8`
- `0x140034c50`
- `0x140049e88`
- `0x1400521c4`
- `0x140052fc0`
- `0x140053430`
- `0x1400556bc`
- `0x140055714`
- `0x140055960`
- `0x1400563f8`
- `0x14005d010`

## import_xrefs

- `DMCmnUtils!DmGetAadDeviceToken` at `0x140053c76`
- `DMCmnUtils!DmGetAadDeviceToken` at `0x140053c76`
- `omadmapi!__imp_OmaDmCreateInternalAcctID` at `0x140053a23`
- `omadmapi!__imp_OmaDmCreateInternalAcctID` at `0x140053a23`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14005371c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140053804`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140053908`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140053a82`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400540a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14005419a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14005371c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140053804`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140053908`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140053a82`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400540a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14005419a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140053628`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140053628`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140054070`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140054070`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140054062`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140054062`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140053c41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140053fcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140053c41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140053fcc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140053c57`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140053fe3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140053c57`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140053fe3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400534e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400535ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053769`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053851`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053955`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053acf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053fda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400540f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400541e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400534e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400535ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053769`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053851`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053955`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053acf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140053fda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400540f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400541e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140053cb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140053cdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140053cf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140053d17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140053d34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140053d53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140053cb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140053cdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140053cf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140053d17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140053d34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140053d53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140053dab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140053dab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140054012`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140054012`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005359a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140053739`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140053821`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140053925`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140053a9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400540c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400541b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005359a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140053739`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140053821`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140053925`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140053a9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400540c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400541b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400534d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400535b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005370d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140053758`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400537f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140053840`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400538f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140053944`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140053a59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140053a73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140053abe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140053b25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140053c4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140054056`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005407f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140054099`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400540e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005414c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005418b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400541d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005423d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400534d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400535b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005370d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140053758`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400537f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140053840`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400538f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140053944`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140053a59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140053a73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140053abe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140053b25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140053c4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140054056`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005407f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140054099`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400540e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005414c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005418b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400541d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005423d`
- `dsreg!DsrGetJoinInfo` at `0x1400537c0`
- `dsreg!DsrGetJoinInfo` at `0x1400537c0`
- `dsreg!DsrFreeJoinInfo` at `0x1400538e9`
- `dsreg!DsrFreeJoinInfo` at `0x140053a64`
- `dsreg!DsrFreeJoinInfo` at `0x14005408a`
- `dsreg!DsrFreeJoinInfo` at `0x1400538e9`
- `dsreg!DsrFreeJoinInfo` at `0x140053a64`
- `dsreg!DsrFreeJoinInfo` at `0x14005408a`

## string_xrefs

- `0x1400536d3`: `Already has MMP-C enrollment`
- `0x140053e89`: `DeclaredConfigurationEnrollment failed`
- `0x140053c96`: `DmGetAadDeviceToken failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall DualEnrollMmpcUsingAADCredential(__int64 a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  int SystemSecurityDescriptor; // eax
  __int64 v4; // r8
  __int64 v5; // r9
  unsigned int v6; // ebx
  int v7; // eax
  __int64 v8; // r8
  const char *v9; // r9
  HANDLE v10; // rdi
  DWORD v11; // eax
  unsigned int v12; // r8d
  const char *v13; // r9
  void *v14; // r13
  __int64 v15; // rcx
  __int64 v16; // rcx
  CEnrollmentLogger *Logger; // rax
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  int JoinInfo; // eax
  __int64 v23; // rcx
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // rax
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  const char *v32; // r9
  const WCHAR *v33; // rsi
  HLOCAL v34; // rbx
  __int64 v35; // rcx
  __int64 v36; // rdx
  char v37; // r14
  const WCHAR *v38; // r12
  int v39; // eax
  __int64 v40; // rcx
  unsigned int v41; // r15d
  __int64 v42; // r8
  const char *v43; // r9
  __int64 v44; // r8
  const char *v45; // r9
  unsigned int v47; // r8d
  const unsigned __int16 *v48; // r8
  const unsigned __int16 *v49; // rcx
  int AadDeviceToken; // r14d
  WCHAR *v51; // rsi
  unsigned __int16 *v52; // rdi
  __int64 v53; // rcx
  const wchar_t *v54; // r8
  __int64 v55; // rcx
  DWORD LastError; // r14d
  __int64 v57; // r14
  __int64 v58; // rdx
  __int64 v59; // rdx
  __int64 v60; // rdx
  __int64 v61; // rdx
  __int64 v62; // rcx
  HRESULT v63; // eax
  int v64; // edx
  unsigned int v65; // r8d
  __int64 v66; // r14
  const WCHAR *v67; // rax
  __int64 (__fastcall ***v68)(_QWORD, GUID *, __int64 *); // rcx
  DWORD v69; // edx
  int v70; // r8d
  __int64 (__fastcall ***v71)(_QWORD, GUID *, __int64 *); // r14
  const WCHAR *v72; // rax
  void *v73; // rcx
  DWORD v74; // r14d
  const unsigned __int16 *StringRawBuffer; // rax
  HANDLE ProcessHeap; // rax
  BOOL v77; // eax
  __int64 v78; // r8
  const char *v79; // r9
  wil::details::in1diag3 *v80; // rcx
  __int64 v81; // r8
  const char *v82; // r9
  __int64 v83; // r8
  const char *v84; // r9
  __int64 v85; // r8
  const char *v86; // r9
  int lpMutexAttributes; // [rsp+20h] [rbp-E0h]
  int lpMutexAttributesa; // [rsp+20h] [rbp-E0h]
  char v89; // [rsp+40h] [rbp-C0h]
  int v90; // [rsp+44h] [rbp-BCh] BYREF
  void *v91; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v92)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v94; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL v95; // [rsp+68h] [rbp-98h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-90h] BYREF
  PCNZWCH v97; // [rsp+78h] [rbp-88h]
  __int64 v98; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL v99; // [rsp+88h] [rbp-78h] BYREF
  int v100; // [rsp+90h] [rbp-70h] BYREF
  __int16 v101; // [rsp+94h] [rbp-6Ch]
  int v102; // [rsp+98h] [rbp-68h] BYREF
  int v103; // [rsp+9Ch] [rbp-64h] BYREF
  HLOCAL v104; // [rsp+A0h] [rbp-60h] BYREF
  HLOCAL v105; // [rsp+A8h] [rbp-58h]
  PCNZWCH v106; // [rsp+B0h] [rbp-50h] BYREF
  PCNZWCH v107; // [rsp+B8h] [rbp-48h] BYREF
  HANDLE hObject; // [rsp+C0h] [rbp-40h] BYREF
  __int64 (__fastcall *v109)(HLOCAL, HSTRING *); // [rsp+C8h] [rbp-38h] BYREF
  PCNZWCH sourceString; // [rsp+D0h] [rbp-30h]
  unsigned __int16 *v111; // [rsp+D8h] [rbp-28h]
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v113[2]; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v114[2]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v115; // [rsp+120h] [rbp+20h]
  HSTRING v116[2]; // [rsp+130h] [rbp+30h] BYREF
  HSTRING v117[2]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v118; // [rsp+150h] [rbp+50h]
  void *v119; // [rsp+160h] [rbp+60h]
  __int64 *v120; // [rsp+168h] [rbp+68h]
  char v121; // [rsp+170h] [rbp+70h]
  _OWORD v122[5]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v123; // [rsp+1D0h] [rbp+D0h]
  HSTRING_HEADER hstringHeader; // [rsp+1E0h] [rbp+E0h] BYREF
  HSTRING v125; // [rsp+1F8h] [rbp+F8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  v105 = a3;
  v111 = a2;
  v98 = 0;
  v95 = 0;
  v94 = 0;
  v92 = 0;
  v91 = 0;
  memset_0(v113, 0, 0x58u);
  string = 0;
  hMem = 0;
  SystemSecurityDescriptor = anonymous_namespace_::GetSystemSecurityDescriptor(&hMem);
  v6 = SystemSecurityDescriptor;
  if ( SystemSecurityDescriptor < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2EF,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\aadhelper\\aadhelper.cpp",
      (const char *)(unsigned int)SystemSecurityDescriptor,
      lpMutexAttributes);
    if ( hMem )
      LocalFree(hMem);
LABEL_216:
    if ( v95 )
      LocalFree(v95);
    return v6;
  }
  *(_QWORD *)&MutexAttributes.nLength = 24;
  *(_QWORD *)&MutexAttributes.bInheritHandle = 0;
  MutexAttributes.lpSecurityDescriptor = hMem;
  hObject = 0;
  v7 = _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
         &hObject,
         (const WCHAR *)L"Global\\DualEnrollmentWithMMPC",
         v4,
         v5,
         &MutexAttributes);
  v6 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F6,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\aadhelper\\aadhelper.cpp",
      (const char *)(unsigned int)v7,
      lpMutexAttributesa);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v8, v9);
    if ( hMem )
      LocalFree(hMem);
    goto LABEL_216;
  }
  v10 = hObject;
  v11 = WaitForSingleObjectEx(hObject, 0xFFFFFFFF, 0);
  if ( v11 == 258 )
  {
    v14 = 0;
  }
  else
  {
    if ( (v11 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v12, v13);
    v14 = v10;
  }
  v119 = v14;
  v90 = 0;
  v99 = 0;
  if ( (int)anonymous_namespace_::IsAlreadyEnrolled(&v90, 64, &v99) < 0 || !v90 )
  {
    v6 = -2145910773;
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x200) != 0 )
      McTemplateU0zd_EventWriteTransfer(v15, "]", L"No active AAD enrollment");
    if ( v99 )
      LocalFree(v99);
    if ( v14 && !ReleaseMutex(v14) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v83, v84);
    if ( v10 && !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v85, v86);
    if ( hMem )
      LocalFree(hMem);
    if ( string )
      WindowsDeleteString(string);
    if ( v91 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v91 + 16LL))(v91);
    if ( v92 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v92)[2])(v92);
    if ( v94 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
    goto LABEL_216;
  }
  v90 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Dual_Enrollment_With_Existing_Record>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Dual_Enrollment_With_Existing_Record>::GetImpl'::`2'::impl) )
    anonymous_namespace_::CleanupMmpcEnrollments(83886080);
  if ( (int)anonymous_namespace_::IsAlreadyEnrolled(&v90, 83886080, 0) >= 0 && v90 )
  {
    v6 = -2145910774;
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x200) != 0 )
      McTemplateU0zd_EventWriteTransfer(v16, "]", L"Already has MMP-C enrollment");
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Dual_Enrollment_With_Existing_Record>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Dual_Enrollment_With_Existing_Record>::GetImpl'::`2'::impl) )
    {
      Logger = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogExistingEnrollment(Logger);
    }
    if ( v99 )
      LocalFree(v99);
    if ( v14 && !ReleaseMutex(v14) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( v10 && !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    if ( hMem )
      LocalFree(hMem);
    if ( string )
      WindowsDeleteString(string);
    if ( v91 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v91 + 16LL))(v91);
    if ( v92 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v92)[2])(v92);
    if ( v94 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
    goto LABEL_216;
  }
  JoinInfo = DsrGetJoinInfo(0, &v98);
  v6 = JoinInfo;
  if ( JoinInfo < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x316,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\aadhelper\\aadhelper.cpp",
      (const char *)(unsigned int)JoinInfo,
      lpMutexAttributesa);
    if ( v99 )
      LocalFree(v99);
    if ( v14 && !ReleaseMutex(v14) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v24, v25);
    if ( v10 && !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hMem )
      LocalFree(hMem);
    if ( string )
      WindowsDeleteString(string);
    if ( v91 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v91 + 16LL))(v91);
    if ( v92 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v92)[2])(v92);
    if ( v94 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
    goto LABEL_216;
  }
  v120 = &v98;
  v121 = 1;
  v28 = v98;
  if ( !v98 )
  {
    v6 = -2147024894;
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x200) != 0 )
    {
      McTemplateU0zd_EventWriteTransfer(v23, "]", L"could not get AADJ joined info");
      v28 = v98;
    }
    DsrFreeJoinInfo(v28);
    if ( v99 )
      LocalFree(v99);
    if ( v14 && !ReleaseMutex(v14) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v29, v30);
    if ( v10 && !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    if ( hMem )
      LocalFree(hMem);
    if ( string )
      WindowsDeleteString(string);
    if ( v91 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v91 + 16LL))(v91);
    if ( v92 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v92)[2])(v92);
    if ( v94 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
    goto LABEL_216;
  }
  v33 = *(const WCHAR **)(v98 + 40);
  sourceString = v33;
  v34 = v99;
  v35 = -1;
  if ( v33 )
  {
    v36 = -1;
    do
      ++v36;
    while ( v33[v36] );
    if ( v36 )
      goto LABEL_88;
  }
  v37 = 1;
  v89 = 1;
  if ( v99 )
  {
    do
      ++v35;
    while ( *((_WORD *)v99 + v35) );
    if ( v35 )
    {
      v33 = (const WCHAR *)v99;
      sourceString = (PCNZWCH)v99;
LABEL_88:
      v89 = 0;
      v37 = 0;
    }
  }
  v38 = &SubKey;
  if ( *(_QWORD *)(v98 + 32) )
    v38 = *(const WCHAR **)(v98 + 32);
  v97 = v38;
  v106 = 0;
  v107 = 0;
  v90 = 0;
  v104 = 0;
  v39 = OmaDmCreateInternalAcctID(0, &v104);
  v41 = v39;
  if ( v39 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x336,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\aadhelper\\aadhelper.cpp",
      (const char *)(unsigned int)v39,
      lpMutexAttributesa);
    if ( v104 )
      LocalFree(v104);
    DsrFreeJoinInfo(v98);
    if ( v34 )
      LocalFree(v34);
    if ( v14 && !ReleaseMutex(v14) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v42, v43);
    if ( v10 && !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v44, v45);
    if ( hMem )
      LocalFree(hMem);
    if ( string )
      WindowsDeleteString(string);
    if ( v91 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v91 + 16LL))(v91);
    if ( v92 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v92)[2])(v92);
    if ( v94 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
    if ( v95 )
      LocalFree(v95);
    return v41;
  }
  v47 = *(_DWORD *)Feature_DeclaredConfiguration_Allow_Custom_Endpoint_3rd_Party__descriptor;
  if ( (*(_DWORD *)Feature_DeclaredConfiguration_Allow_Custom_Endpoint_3rd_Party__descriptor & 4) == 0 )
  {
    v109 = *(__int64 (__fastcall **)(HLOCAL, HSTRING *))wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Allow_Custom_Endpoint_3rd_Party>::GetCachedFeatureEnabledState(
                                                          v40,
                                                          &v109);
    v47 = (unsigned int)v109;
  }
  v100 = 0;
  v101 = 3;
  wil::details::ReportUsageToService(&qword_14007E518, 44700043, (v47 >> 10) & 1, (v47 >> 11) & 1, &v100, 1, 3);
  v48 = (const unsigned __int16 *)v105;
  v107 = 0;
  v106 = 0;
  v49 = &SubKey;
  if ( !v105 )
    v48 = 0;
  if ( !v37 )
    v49 = v33;
  AadDeviceToken = MmpcDiscoveryUrl(
                     v49,
                     v38,
                     v48,
                     L"Device",
                     (const unsigned __int16 *)v104,
                     (unsigned __int16 **)&v106,
                     (unsigned __int16 **)&v107,
                     (enum Windows::Internal::Management::Enrollment::MDMAuthPolicy *)&v90);
  v51 = (WCHAR *)v106;
  v52 = (unsigned __int16 *)v107;
  v53 = 0;
  if ( AadDeviceToken >= 0 )
  {
    v105 = v95;
    if ( v95 )
    {
      LastError = GetLastError();
      LocalFree(v105);
      SetLastError(LastError);
    }
    v95 = 0;
    AadDeviceToken = DmGetAadDeviceToken(L"de50c81f-5f80-4771-b66b-cebd28ccdfc1", v52, 0, (unsigned __int16 **)&v95);
    if ( AadDeviceToken >= 0 )
    {
      if ( v89 )
      {
        WindowsCreateString(&SubKey, 1u, v113);
        v57 = -1;
      }
      else
      {
        v57 = -1;
        v58 = -1;
        do
          ++v58;
        while ( sourceString[v58] );
        WindowsCreateString(sourceString, v58 + 1, v113);
      }
      v59 = -1;
      do
        ++v59;
      while ( v51[v59] );
      WindowsCreateString(v51, v59 + 1, &v113[1]);
      v60 = -1;
      do
        ++v60;
      while ( *((_WORD *)v95 + v60) );
      WindowsCreateString((PCNZWCH)v95, v60 + 1, v114);
      v61 = -1;
      do
        ++v61;
      while ( v52[v61] );
      WindowsCreateString(v52, v61 + 1, v116);
      do
        ++v57;
      while ( v97[v57] );
      WindowsCreateString(v97, v57 + 1, v117);
      v114[1] = 0;
      LODWORD(v115) = 0;
      v118 = 0x100000001LL;
      v62 = v94;
      v94 = 0;
      if ( v62 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
      v125 = 0;
      v63 = WindowsCreateStringReference(
              L"Windows.Internal.Management.Enrollment.Enroller",
              0x2Fu,
              &hstringHeader,
              &v125);
      if ( v63 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v63, v64, v65);
        goto LABEL_231;
      }
      AadDeviceToken = Windows::Foundation::ActivateInstance<Windows::Internal::Management::Enrollment::IEnrollment>(
                         v125,
                         &v94);
      if ( AadDeviceToken >= 0 )
      {
        v66 = v94;
        v67 = *(const WCHAR **)(*(_QWORD *)v94 + 80LL);
        v97 = v67;
        v68 = v92;
        v92 = 0;
        if ( v68 )
        {
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), _QWORD))(*v68)[2])(v68, 0);
          v67 = v97;
        }
        v122[0] = *(_OWORD *)v113;
        v122[1] = *(_OWORD *)v114;
        v122[2] = v115;
        v122[3] = *(_OWORD *)v116;
        v122[4] = *(_OWORD *)v117;
        v123 = v118;
        AadDeviceToken = ((__int64 (__fastcall *)(__int64, _OWORD *, _QWORD))v67)(v66, v122, &v92);
        if ( AadDeviceToken >= 0 )
        {
          AadDeviceToken = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *> *>(
                             v92,
                             v69,
                             v70);
          if ( AadDeviceToken >= 0 )
          {
            v71 = v92;
            v72 = (const WCHAR *)(*v92)[8];
            v97 = v72;
            v73 = v91;
            v91 = 0;
            if ( v73 )
            {
              (*(void (__fastcall **)(void *))(*(_QWORD *)v73 + 16LL))(v73);
              v72 = v97;
            }
            AadDeviceToken = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), void **))v72)(
                               v71,
                               &v91);
            if ( AadDeviceToken >= 0 )
            {
              v102 = 0;
              AadDeviceToken = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)v91 + 64LL))(v91, &v102);
              if ( AadDeviceToken >= 0 )
              {
                v103 = 0;
                (*(void (__fastcall **)(void *, int *))(*(_QWORD *)v91 + 80LL))(v91, &v103);
                AadDeviceToken = v102;
                if ( v102 >= 0 )
                {
                  v105 = v91;
                  v109 = *(__int64 (__fastcall **)(HLOCAL, HSTRING *))(*(_QWORD *)v91 + 56LL);
                  v97 = (PCNZWCH)string;
                  if ( string )
                  {
                    v74 = GetLastError();
                    WindowsDeleteString((HSTRING)v97);
                    SetLastError(v74);
                  }
                  string = 0;
                  AadDeviceToken = v109(v105, &string);
                  if ( AadDeviceToken < 0 )
                    goto LABEL_171;
                  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                  AadDeviceToken = StringCchCopyW(v111, 0x27u, StringRawBuffer);
                }
                else if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x200) != 0 )
                {
                  McTemplateU0zd_EventWriteTransfer(v55, "]", L"get_EnrollmentErrorCode returns an failed result");
                }
                if ( AadDeviceToken >= 0 )
                  goto LABEL_173;
                goto LABEL_171;
              }
              if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x200) == 0 )
                goto LABEL_173;
              v54 = L"Failed to get enrollment error code";
            }
            else
            {
              if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x200) == 0 )
                goto LABEL_173;
              v54 = L"Failed to get enrollment result";
            }
          }
          else
          {
            if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x200) == 0 )
              goto LABEL_173;
            v54 = L"Wait for enrollment fo finish failed";
          }
        }
        else
        {
          if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x200) == 0 )
            goto LABEL_173;
          v54 = L"DeclaredConfigurationEnrollment failed";
        }
      }
      else
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x200) == 0 )
          goto LABEL_173;
        v54 = L"Failed to activate MDM enrollment instance";
      }
    }
    else
    {
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x200) == 0 )
        goto LABEL_173;
      v54 = L"DmGetAadDeviceToken failed";
    }
  }
  else
  {
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x200) == 0 )
      goto LABEL_173;
    v54 = L"MmpcDiscoveryUrl";
  }
  McTemplateU0zd_EventWriteTransfer(v53, "]", v54);
LABEL_171:
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x200) != 0 )
    McTemplateU0zd_EventWriteTransfer(v55, "]", L"DualEnrollMmpcUsingAADCredential failed");
LABEL_173:
  if ( v104 )
    LocalFree(v104);
  if ( v52 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v52);
  }
  if ( v51 )
    LocalFree(v51);
  DsrFreeJoinInfo(v98);
  if ( v34 )
    LocalFree(v34);
  if ( v14 )
  {
    v77 = ReleaseMutex(v14);
    v80 = retaddr;
    if ( !v77 )
LABEL_231:
      wil::details::in1diag3::_FailFast_GetLastError(v80, (void *)0xA15, v78, v79);
  }
  if ( hObject && !CloseHandle(hObject) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v81, v82);
  if ( hMem )
    LocalFree(hMem);
  if ( string )
    WindowsDeleteString(string);
  if ( v91 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v91 + 16LL))(v91);
  if ( v92 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v92)[2])(v92);
  if ( v94 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
  if ( v95 )
    LocalFree(v95);
  return (unsigned int)AadDeviceToken;
}

```

## disassembly

```asm
0x140053430  mov     [rsp-8+arg_0], rbx
0x140053435  push    rbp
0x140053436  push    rsi
0x140053437  push    rdi
0x140053438  push    r12
0x14005343a  push    r13
0x14005343c  push    r14
0x14005343e  push    r15
0x140053440  lea     rbp, [rsp-110h]
0x140053448  sub     rsp, 210h
0x14005344f  mov     rax, cs:__security_cookie
0x140053456  xor     rax, rsp
0x140053459  mov     [rbp+140h+var_40], rax
0x140053460  mov     [rbp+140h+var_198], r8
0x140053464  mov     [rbp+140h+var_168], rdx
0x140053468  xor     r12d, r12d
0x14005346b  mov     [rbp+140h+var_1C0], r12
0x14005346f  mov     [rsp+240h+var_1D8], r12
0x140053474  mov     [rsp+240h+var_1E0], r12
0x140053479  mov     [rsp+240h+var_1F0], r12
0x14005347e  mov     [rsp+240h+var_1F8], r12
0x140053483  xor     edx, edx; Val
0x140053485  lea     r8d, [r12+58h]; Size
0x14005348a  lea     rcx, [rbp+140h+var_140]; void *
0x14005348e  call    memset_0
0x140053493  mov     [rsp+240h+string], r12
0x140053498  mov     [rsp+240h+hMem], r12
0x14005349d  lea     rcx, [rsp+240h+hMem]; SecurityDescriptor
0x1400534a2  call    _anonymous_namespace___GetSystemSecurityDescriptor
0x1400534a7  mov     ebx, eax
0x1400534a9  test    eax, eax
0x1400534ab  jns     loc_140053539
0x1400534b1  mov     rcx, [rbp+148h]; this
0x1400534b8  mov     r9d, eax; char *
0x1400534bb  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1400534c2  mov     edx, 2EFh; void *
0x1400534c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400534cc  nop
0x1400534cd  mov     rcx, [rsp+240h+hMem]; hMem
0x1400534d2  test    rcx, rcx
0x1400534d5  jz      short loc_1400534DE
0x1400534d7  call    cs:__imp_LocalFree
0x1400534dd  nop
0x1400534de  mov     rcx, [rsp+240h+string]; string
0x1400534e3  test    rcx, rcx
0x1400534e6  jz      short loc_1400534EF
0x1400534e8  call    cs:__imp_WindowsDeleteString
0x1400534ee  nop
0x1400534ef  mov     rcx, [rsp+240h+var_1F8]
0x1400534f4  test    rcx, rcx
0x1400534f7  jz      short loc_140053506
0x1400534f9  mov     rax, [rcx]
0x1400534fc  mov     rax, [rax+10h]
0x140053500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053505  nop
0x140053506  mov     rcx, [rsp+240h+var_1F0]
0x14005350b  test    rcx, rcx
0x14005350e  jz      short loc_14005351D
0x140053510  mov     rax, [rcx]
0x140053513  mov     rax, [rax+10h]
0x140053517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005351c  nop
0x14005351d  mov     rcx, [rsp+240h+var_1E0]
0x140053522  test    rcx, rcx
0x140053525  jz      short loc_140053534
0x140053527  mov     rax, [rcx]
0x14005352a  mov     rax, [rax+10h]
0x14005352e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053533  nop
0x140053534  jmp     loc_140054233
0x140053539  mov     qword ptr [rbp+140h+MutexAttributes.nLength], 18h
0x140053541  mov     qword ptr [rbp+140h+MutexAttributes.bInheritHandle], r12
0x140053545  mov     rax, [rsp+240h+hMem]
0x14005354a  mov     [rbp+140h+MutexAttributes.lpSecurityDescriptor], rax
0x14005354e  mov     [rbp+140h+hObject], r12
0x140053552  lea     rax, [rbp+140h+MutexAttributes]
0x140053556  mov     [rsp+240h+lpMutexAttributes], rax; int
0x14005355b  lea     rdx, aGlobalDualenro; "Global\\DualEnrollmentWithMMPC"
0x140053562  lea     rcx, [rbp+140h+hObject]; int
0x140053566  call    ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x14005356b  mov     ebx, eax
0x14005356d  test    eax, eax
0x14005356f  jns     loc_14005361B
0x140053575  mov     rcx, [rbp+148h]; this
0x14005357c  mov     r9d, eax; char *
0x14005357f  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140053586  mov     edx, 2F6h; void *
0x14005358b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140053590  nop
0x140053591  mov     rcx, [rbp+140h+hObject]; hObject
0x140053595  test    rcx, rcx
0x140053598  jz      short loc_1400535AF
0x14005359a  call    cs:__imp_CloseHandle
0x1400535a0  mov     rcx, [rbp+148h]; this
0x1400535a7  test    eax, eax
0x1400535a9  jz      loc_14005427A
0x1400535af  mov     rcx, [rsp+240h+hMem]; hMem
0x1400535b4  test    rcx, rcx
0x1400535b7  jz      short loc_1400535C0
0x1400535b9  call    cs:__imp_LocalFree
0x1400535bf  nop
0x1400535c0  mov     rcx, [rsp+240h+string]; string
0x1400535c5  test    rcx, rcx
0x1400535c8  jz      short loc_1400535D1
0x1400535ca  call    cs:__imp_WindowsDeleteString
0x1400535d0  nop
0x1400535d1  mov     rcx, [rsp+240h+var_1F8]
0x1400535d6  test    rcx, rcx
0x1400535d9  jz      short loc_1400535E8
0x1400535db  mov     rax, [rcx]
0x1400535de  mov     rax, [rax+10h]
0x1400535e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400535e7  nop
0x1400535e8  mov     rcx, [rsp+240h+var_1F0]
0x1400535ed  test    rcx, rcx
0x1400535f0  jz      short loc_1400535FF
0x1400535f2  mov     rax, [rcx]
0x1400535f5  mov     rax, [rax+10h]
0x1400535f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400535fe  nop
0x1400535ff  mov     rcx, [rsp+240h+var_1E0]
0x140053604  test    rcx, rcx
0x140053607  jz      short loc_140053616
0x140053609  mov     rax, [rcx]
0x14005360c  mov     rax, [rax+10h]
0x140053610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053615  nop
0x140053616  jmp     loc_140054233
0x14005361b  mov     rdi, [rbp+140h+hObject]
0x14005361f  xor     r8d, r8d; bAlertable
0x140053622  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140053625  mov     rcx, rdi; hHandle
0x140053628  call    cs:__imp_WaitForSingleObjectEx
0x14005362e  cmp     eax, 102h
0x140053633  jz      short loc_140053645
0x140053635  test    eax, 0FFFFFF7Fh
0x14005363a  jnz     loc_140054285
0x140053640  mov     r13, rdi
0x140053643  jmp     short loc_140053648
0x140053645  mov     r13, r12
0x140053648  mov     [rbp+140h+var_E0], r13
0x14005364c  mov     [rsp+240h+var_1FC], r12d
0x140053651  mov     [rbp+140h+var_1B8], r12
0x140053655  lea     r8, [rbp+140h+var_1B8]
0x140053659  mov     edx, 40h ; '@'
0x14005365e  lea     rcx, [rsp+240h+var_1FC]
0x140053663  call    _anonymous_namespace___IsAlreadyEnrolled
0x140053668  test    eax, eax
0x14005366a  js      loc_14005415A
0x140053670  cmp     [rsp+240h+var_1FC], r12d
0x140053675  jz      loc_14005415A
0x14005367b  mov     [rsp+240h+var_1FC], r12d
0x140053680  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Dual_Enrollment_With_Existing_Record@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Dual_Enrollment_With_Existing_Record@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Dual_Enrollment_With_Existing_Record> `wil::Feature<__WilFeatureTraits_Feature_Dual_Enrollment_With_Existing_Record>::GetImpl(void)'::`2'::impl
0x140053687  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Dual_Enrollment_With_Existing_Record@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Dual_Enrollment_With_Existing_Record>::__private_IsEnabled(void)
0x14005368c  mov     ebx, 5000000h
0x140053691  test    al, al
0x140053693  jz      short loc_14005369C
0x140053695  mov     ecx, ebx
0x140053697  call    _anonymous_namespace___CleanupMmpcEnrollments
0x14005369c  xor     r8d, r8d
0x14005369f  mov     rdx, rbx
0x1400536a2  lea     rcx, [rsp+240h+var_1FC]
0x1400536a7  call    _anonymous_namespace___IsAlreadyEnrolled
0x1400536ac  test    eax, eax
0x1400536ae  js      loc_1400537BA
0x1400536b4  cmp     [rsp+240h+var_1FC], r12d
0x1400536b9  jz      loc_1400537BA
0x1400536bf  mov     ebx, 8018000Ah
0x1400536c4  mov     r15b, 2
0x1400536c7  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits+1, r15b
0x1400536ce  jz      short loc_1400536E6
0x1400536d0  mov     r9d, ebx
0x1400536d3  lea     r8, aAlreadyHasMmpC; "Already has MMP-C enrollment"
0x1400536da  lea     rdx, EnterpriseDiagnosticsDualModeFailure; "]"
0x1400536e1  call    McTemplateU0zd_EventWriteTransfer
0x1400536e6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Dual_Enrollment_With_Existing_Record@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Dual_Enrollment_With_Existing_Record@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Dual_Enrollment_With_Existing_Record> `wil::Feature<__WilFeatureTraits_Feature_Dual_Enrollment_With_Existing_Record>::GetImpl(void)'::`2'::impl
0x1400536ed  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Dual_Enrollment_With_Existing_Record@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Dual_Enrollment_With_Existing_Record>::__private_IsEnabled(void)
0x1400536f2  test    al, al
0x1400536f4  jz      short loc_140053704
0x1400536f6  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1400536fb  mov     rcx, rax; this
0x1400536fe  call    ?LogExistingEnrollment@CEnrollmentLogger@@QEAAXXZ; CEnrollmentLogger::LogExistingEnrollment(void)
0x140053703  nop
0x140053704  mov     rcx, [rbp+140h+var_1B8]; hMem
0x140053708  test    rcx, rcx
0x14005370b  jz      short loc_140053714
0x14005370d  call    cs:__imp_LocalFree
0x140053713  nop
0x140053714  test    r13, r13
0x140053717  jz      short loc_140053731
0x140053719  mov     rcx, r13; hMutex
0x14005371c  call    cs:__imp_ReleaseMutex
0x140053722  mov     rcx, [rbp+148h]; this
0x140053729  test    eax, eax
0x14005372b  jz      loc_140054297
0x140053731  test    rdi, rdi
0x140053734  jz      short loc_14005374E
0x140053736  mov     rcx, rdi; hObject
0x140053739  call    cs:__imp_CloseHandle
0x14005373f  mov     rcx, [rbp+148h]; this
0x140053746  test    eax, eax
0x140053748  jz      loc_1400542A2
0x14005374e  mov     rcx, [rsp+240h+hMem]; hMem
0x140053753  test    rcx, rcx
0x140053756  jz      short loc_14005375F
0x140053758  call    cs:__imp_LocalFree
0x14005375e  nop
0x14005375f  mov     rcx, [rsp+240h+string]; string
0x140053764  test    rcx, rcx
0x140053767  jz      short loc_140053770
0x140053769  call    cs:__imp_WindowsDeleteString
0x14005376f  nop
0x140053770  mov     rcx, [rsp+240h+var_1F8]
0x140053775  test    rcx, rcx
0x140053778  jz      short loc_140053787
0x14005377a  mov     rax, [rcx]
0x14005377d  mov     rax, [rax+10h]
0x140053781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053786  nop
0x140053787  mov     rcx, [rsp+240h+var_1F0]
0x14005378c  test    rcx, rcx
0x14005378f  jz      short loc_14005379E
0x140053791  mov     rax, [rcx]
0x140053794  mov     rax, [rax+10h]
0x140053798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005379d  nop
0x14005379e  mov     rcx, [rsp+240h+var_1E0]
0x1400537a3  test    rcx, rcx
0x1400537a6  jz      short loc_1400537B5
0x1400537a8  mov     rax, [rcx]
0x1400537ab  mov     rax, [rax+10h]
0x1400537af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400537b4  nop
0x1400537b5  jmp     loc_140054233
0x1400537ba  lea     rdx, [rbp+140h+var_1C0]
0x1400537be  xor     ecx, ecx
0x1400537c0  call    cs:__imp_DsrGetJoinInfo
0x1400537c6  mov     ebx, eax
0x1400537c8  test    eax, eax
0x1400537ca  jns     loc_1400538A2
0x1400537d0  mov     rcx, [rbp+148h]; this
0x1400537d7  mov     r9d, eax; char *
0x1400537da  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1400537e1  mov     edx, 316h; void *
0x1400537e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400537eb  nop
0x1400537ec  mov     rcx, [rbp+140h+var_1B8]; hMem
0x1400537f0  test    rcx, rcx
0x1400537f3  jz      short loc_1400537FC
0x1400537f5  call    cs:__imp_LocalFree
0x1400537fb  nop
0x1400537fc  test    r13, r13
0x1400537ff  jz      short loc_140053819
0x140053801  mov     rcx, r13; hMutex
0x140053804  call    cs:__imp_ReleaseMutex
0x14005380a  mov     rcx, [rbp+148h]; this
0x140053811  test    eax, eax
0x140053813  jz      loc_1400542AD
0x140053819  test    rdi, rdi
0x14005381c  jz      short loc_140053836
0x14005381e  mov     rcx, rdi; hObject
0x140053821  call    cs:__imp_CloseHandle
0x140053827  mov     rcx, [rbp+148h]; this
0x14005382e  test    eax, eax
0x140053830  jz      loc_1400542B8
0x140053836  mov     rcx, [rsp+240h+hMem]; hMem
0x14005383b  test    rcx, rcx
0x14005383e  jz      short loc_140053847
0x140053840  call    cs:__imp_LocalFree
0x140053846  nop
0x140053847  mov     rcx, [rsp+240h+string]; string
0x14005384c  test    rcx, rcx
0x14005384f  jz      short loc_140053858
0x140053851  call    cs:__imp_WindowsDeleteString
0x140053857  nop
0x140053858  mov     rcx, [rsp+240h+var_1F8]
0x14005385d  test    rcx, rcx
0x140053860  jz      short loc_14005386F
0x140053862  mov     rax, [rcx]
0x140053865  mov     rax, [rax+10h]
0x140053869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005386e  nop
0x14005386f  mov     rcx, [rsp+240h+var_1F0]
0x140053874  test    rcx, rcx
0x140053877  jz      short loc_140053886
0x140053879  mov     rax, [rcx]
0x14005387c  mov     rax, [rax+10h]
0x140053880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053885  nop
0x140053886  mov     rcx, [rsp+240h+var_1E0]
0x14005388b  test    rcx, rcx
0x14005388e  jz      short loc_14005389D
0x140053890  mov     rax, [rcx]
0x140053893  mov     rax, [rax+10h]
0x140053897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005389c  nop
0x14005389d  jmp     loc_140054233
0x1400538a2  lea     rax, [rbp+140h+var_1C0]
0x1400538a6  mov     [rbp+140h+var_D8], rax
0x1400538aa  mov     [rbp+140h+var_D0], 1
  ... truncated ...
```
