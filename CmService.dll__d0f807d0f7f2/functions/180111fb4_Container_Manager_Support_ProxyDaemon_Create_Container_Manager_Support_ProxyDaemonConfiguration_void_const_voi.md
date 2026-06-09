# Container::Manager::Support::ProxyDaemon::Create(Container::Manager::Support::ProxyDaemonConfiguration,void (*const)(void * const,void * const),void * const)

- ea: `0x180111fb4`
- end: `0x18011319b`
- name: `?Create@ProxyDaemon@Support@Manager@Container@@QEAAJUProxyDaemonConfiguration@234@Q6AXQEAX1@Z1@Z`
- size: `4583`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a7d60`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x180005704`
- `0x180008bf0`
- `0x18000a10c`
- `0x18000da68`
- `0x18000da88`
- `0x18000dad8`
- `0x180016658`
- `0x180016774`
- `0x180023b68`
- `0x1800262e4`
- `0x18002ba5c`
- `0x18002c5b4`
- `0x18002da58`
- `0x18002dc8c`
- `0x18002e2b4`
- `0x180111ab0`
- `0x180111d70`
- `0x180111fb4`
- `0x1801131a4`
- `0x1801131d4`
- `0x180113870`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x180112516`
- `ntdll!NtQuerySystemInformation` at `0x180112516`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18011282e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180112977`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180112b37`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180112c3d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18011282e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180112977`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180112b37`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180112c3d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180112009`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180112009`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180112d87`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180112d87`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180112173`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1801122d2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1801126b0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180112a24`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180112be4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180112d3e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180112e32`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180112f1e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180112173`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1801122d2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1801126b0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180112a24`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180112be4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180112d3e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180112e32`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180112f1e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180112c5c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180112c5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180112ce2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180112d2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180112ce2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180112d2c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180112cfa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180112d4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180112cfa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180112d4c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180112ae1`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180112ae1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801126d8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801126d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011204b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801120c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112123`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112141`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801121c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801121de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011229f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801122bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112454`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112474`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011267d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112699`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112793`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801127b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801128a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801128c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801129f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112a0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112a3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112bb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112bcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112c02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112dfa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112e16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112e4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112eef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112f0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112f3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011204b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801120c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112123`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112141`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801121c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801121de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011229f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801122bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112454`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112474`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011267d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112699`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112793`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801127b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801128a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801128c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801129f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112a0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112a3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112bb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112bcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112c02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112dfa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112e16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112e4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112eef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112f0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180112f3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011281d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180112966`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180112b26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180112c2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011281d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180112966`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180112b26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180112c2c`
- `USERENV!DestroyEnvironmentBlock` at `0x18011262a`
- `USERENV!DestroyEnvironmentBlock` at `0x180112740`
- `USERENV!DestroyEnvironmentBlock` at `0x180112855`
- `USERENV!DestroyEnvironmentBlock` at `0x18011299e`
- `USERENV!DestroyEnvironmentBlock` at `0x180112b5e`
- `USERENV!DestroyEnvironmentBlock` at `0x180112da6`
- `USERENV!DestroyEnvironmentBlock` at `0x180112e9c`
- `USERENV!DestroyEnvironmentBlock` at `0x18011262a`
- `USERENV!DestroyEnvironmentBlock` at `0x180112740`
- `USERENV!DestroyEnvironmentBlock` at `0x180112855`
- `USERENV!DestroyEnvironmentBlock` at `0x18011299e`
- `USERENV!DestroyEnvironmentBlock` at `0x180112b5e`
- `USERENV!DestroyEnvironmentBlock` at `0x180112da6`
- `USERENV!DestroyEnvironmentBlock` at `0x180112e9c`
- `USERENV!CreateEnvironmentBlock` at `0x1801125f1`
- `USERENV!CreateEnvironmentBlock` at `0x1801125f1`

## string_xrefs

- `0x180113153`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1801126f3`: `onecore\base\gendrv\silos\csl\lib\CslSecurity.h`
- `0x180113095`: `onecore\base\gendrv\silos\csl\lib\CslSecurity.h`
- `0x1801130c0`: `onecore\base\gendrv\silos\csl\lib\CslSecurity.h`
- `0x1801130fd`: `onecore\base\gendrv\silos\csl\lib\CslSecurity.h`
- `0x18011313a`: `onecore\base\gendrv\silos\csl\lib\CslSecurity.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Support::ProxyDaemon::Create(
        Container::Manager::Support::ProxyDaemon *a1,
        HANDLE *a2,
        __int64 a3,
        __int64 a4)
{
  struct _TP_WAIT *ThreadpoolWait; // rsi
  const char *v6; // r9
  unsigned int LastError; // ebx
  int v9; // eax
  unsigned int v10; // r14d
  unsigned int v11; // r8d
  const char *v12; // r9
  int v13; // eax
  unsigned int v14; // r8d
  const char *v15; // r9
  unsigned int v16; // r8d
  const char *v17; // r9
  char *v18; // rcx
  unsigned int v19; // r8d
  const char *v20; // r9
  unsigned int v21; // r8d
  const char *v22; // r9
  HANDLE v23; // rdi
  HANDLE v24; // rbx
  int ProcessParameterStrings; // eax
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  int v30; // eax
  __int64 v31; // rdx
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  NTSTATUS v36; // eax
  HANDLE *v37; // r12
  HANDLE v38; // rdx
  const char *v39; // r9
  unsigned int v40; // r8d
  const char *v41; // r9
  unsigned int v42; // r8d
  const char *v43; // r9
  HANDLE v44; // rdx
  const char *v45; // r9
  int v46; // eax
  char v47; // r15
  struct _PROCESS_INFORMATION *v48; // rdx
  unsigned int v49; // r8d
  const char *v50; // r9
  unsigned int v51; // r8d
  const char *v52; // r9
  int v53; // eax
  struct _PROCESS_INFORMATION *v54; // rdx
  const char *v55; // r9
  unsigned int v56; // r8d
  const char *v57; // r9
  unsigned int v58; // r8d
  const char *v59; // r9
  HANDLE v60; // r14
  int v61; // eax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v62; // rdx
  const char *v63; // r9
  unsigned int v64; // r8d
  const char *v65; // r9
  unsigned int v66; // r8d
  const char *v67; // r9
  Container::Manager::Support *v68; // r12
  char *v69; // rcx
  struct _PROC_THREAD_ATTRIBUTE_LIST *v70; // rdx
  const char *v71; // r9
  struct _PROC_THREAD_ATTRIBUTE_LIST *v72; // rdx
  const char *v73; // r9
  unsigned int v74; // r8d
  const char *v75; // r9
  unsigned int v76; // r8d
  const char *v77; // r9
  const char *v78; // r9
  DWORD v79; // eax
  const char *v80; // r9
  Container::Manager::Support::ProxyDaemon *v81; // r14
  PTP_WAIT v82; // rax
  HANDLE *v83; // r12
  char *v84; // rcx
  char *v85; // rdx
  __int128 v86; // xmm6
  __int64 v87; // xmm7_8
  DWORD v88; // edi
  struct _PROCESS_INFORMATION *v89; // rdx
  PTP_WAIT *v90; // r15
  DWORD v91; // edi
  void *v92; // rdx
  struct _TP_WAIT *v93; // rcx
  struct _PROCESS_INFORMATION *v94; // rdx
  unsigned int v95; // r8d
  const char *v96; // r9
  unsigned int v97; // r8d
  const char *v98; // r9
  struct _PROCESS_INFORMATION *v99; // rdx
  unsigned int v100; // r8d
  const char *v101; // r9
  unsigned int v102; // r8d
  const char *v103; // r9
  int lpThreadAttributes; // [rsp+28h] [rbp-E0h]
  int lpThreadAttributesa; // [rsp+28h] [rbp-E0h]
  LPWSTR *lpThreadAttributesb; // [rsp+28h] [rbp-E0h]
  int lpThreadAttributesc; // [rsp+28h] [rbp-E0h]
  int lpThreadAttributesd; // [rsp+28h] [rbp-E0h]
  unsigned int lpThreadAttributese; // [rsp+28h] [rbp-E0h]
  HANDLE hObject; // [rsp+68h] [rbp-A0h] BYREF
  HANDLE SystemInformation; // [rsp+70h] [rbp-98h] BYREF
  LPVOID Environment; // [rsp+78h] [rbp-90h] BYREF
  HANDLE hHandle; // [rsp+80h] [rbp-88h] BYREF
  LPWSTR lpCommandLine[2]; // [rsp+88h] [rbp-80h] BYREF
  _WORD v115[8]; // [rsp+98h] [rbp-70h] BYREF
  LPCWSTR lpApplicationName[2]; // [rsp+A8h] [rbp-60h] BYREF
  _WORD v117[8]; // [rsp+B8h] [rbp-50h] BYREF
  void *v118[2]; // [rsp+C8h] [rbp-40h] BYREF
  _WORD v119[8]; // [rsp+D8h] [rbp-30h] BYREF
  HANDLE v120; // [rsp+E8h] [rbp-20h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+F0h] [rbp-18h] BYREF
  int v122; // [rsp+108h] [rbp+0h] BYREF
  PTP_WAIT pwa; // [rsp+110h] [rbp+8h]
  __int64 Value; // [rsp+118h] [rbp+10h] BYREF
  _QWORD *v125; // [rsp+120h] [rbp+18h]
  __int64 v126; // [rsp+128h] [rbp+20h]
  void *v127; // [rsp+130h] [rbp+28h] BYREF
  char *v128; // [rsp+138h] [rbp+30h]
  _WORD v129[8]; // [rsp+140h] [rbp+38h] BYREF
  void *v130[2]; // [rsp+150h] [rbp+48h] BYREF
  _WORD v131[8]; // [rsp+160h] [rbp+58h] BYREF
  Container::Manager::Support::ProxyDaemon *v132; // [rsp+170h] [rbp+68h]
  __int64 v133; // [rsp+178h] [rbp+70h]
  _QWORD v134[2]; // [rsp+180h] [rbp+78h] BYREF
  char v135; // [rsp+190h] [rbp+88h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+198h] [rbp+90h] BYREF
  HANDLE v137; // [rsp+200h] [rbp+F8h]
  _QWORD v138[4]; // [rsp+208h] [rbp+100h] BYREF
  _DWORD v139[4]; // [rsp+228h] [rbp+120h] BYREF
  _DWORD v140[4]; // [rsp+238h] [rbp+130h] BYREF
  _QWORD v141[2]; // [rsp+248h] [rbp+140h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C0h] [rbp+1B8h]

  pwa = (PTP_WAIT)a2;
  v132 = a1;
  v133 = a4;
  ThreadpoolWait = CreateThreadpoolWait(Container::Manager::Support::ProxyDaemon::OnProcessExit, a1, 0);
  if ( !ThreadpoolWait )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1E0,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
                  v6);
    if ( (char *)a2[2] - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(a2[2]);
    return LastError;
  }
  hHandle = 0;
  v120 = 0;
  Value = 24;
  v126 = 1;
  v125 = 0;
  hObject = 0;
  v9 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
         &hObject,
         1);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
      (const char *)(unsigned int)v9,
      lpThreadAttributes);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v11, v12);
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E5,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
      (const char *)v10,
      lpThreadAttributesa);
    goto LABEL_15;
  }
  SystemInformation = 0;
  v13 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
          &SystemInformation,
          1);
  v10 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12F,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
      (const char *)(unsigned int)v13,
      lpThreadAttributes);
    if ( SystemInformation && !CloseHandle(SystemInformation) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v16, v17);
    goto LABEL_14;
  }
  __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
    &hHandle,
    &hObject);
  __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
    &v120,
    &SystemInformation);
  if ( SystemInformation && !CloseHandle(SystemInformation) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v19, v20);
  if ( hObject && !CloseHandle(hObject) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
  v23 = v120;
  v24 = hHandle;
  lpApplicationName[0] = v117;
  v117[0] = 0;
  lpApplicationName[1] = v117;
  v115[0] = 0;
  lpCommandLine[0] = v115;
  lpCommandLine[1] = v115;
  lpThreadAttributesb = lpCommandLine;
  ProcessParameterStrings = Container::Manager::Support::GetProcessParameterStrings(
                              a2,
                              hHandle,
                              v120,
                              lpApplicationName);
  v10 = ProcessParameterStrings;
  if ( ProcessParameterStrings < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EF,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
      (const char *)(unsigned int)ProcessParameterStrings,
      (int)lpCommandLine);
    if ( lpCommandLine[0] != v115 )
      operator delete(lpCommandLine[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( lpApplicationName[0] != v117 )
      operator delete((void *)lpApplicationName[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v23 && !CloseHandle(v23) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( v24 && !CloseHandle(v24) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    CloseThreadpoolWait(ThreadpoolWait);
    v18 = (char *)a2[2];
    goto LABEL_199;
  }
  v119[0] = 0;
  v118[0] = v119;
  v129[0] = 0;
  v118[1] = v119;
  v127 = v129;
  v128 = (char *)v129;
  v30 = Csl::GuidToString(a2, &v127);
  v10 = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFD,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
      (const char *)(unsigned int)v30,
      (int)lpCommandLine);
LABEL_39:
    if ( v127 != v129 )
      operator delete(v127, (const struct std::nothrow_t *)&std::nothrow);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F4,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
      (const char *)v10,
      lpThreadAttributesc);
    if ( v118[0] != v119 )
      operator delete(v118[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( lpCommandLine[0] != v115 )
      operator delete(lpCommandLine[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( lpApplicationName[0] != v117 )
      operator delete((void *)lpApplicationName[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v23 && !CloseHandle(v23) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    if ( v24 && !CloseHandle(v24) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
LABEL_15:
    CloseThreadpoolWait(ThreadpoolWait);
    if ( (char *)a2[2] - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v18 = (char *)a2[2];
LABEL_200:
      CloseHandle(v18);
    }
    return v10;
  }
  v131[0] = 0;
  v130[0] = v131;
  v130[1] = v131;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v130,
                           L"CmProxyD-",
                           9) )
  {
    v31 = 256;
    goto LABEL_37;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v130,
                           v127,
                           (v128 - (_BYTE *)v127) >> 1) )
  {
    v31 = 257;
LABEL_37:
    v10 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
      (const char *)0x8007000ELL,
      (int)lpCommandLine);
    if ( v130[0] != v131 )
      operator delete(v130[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_39;
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
    v118,
    v130);
  if ( v130[0] != v131 )
    operator delete(v130[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v127 != v129 )
    operator delete(v127, (const struct std::nothrow_t *)&std::nothrow);
  v134[0] = v24;
  v134[1] = v23;
  v122 = 1;
  v141[0] = 0x1111131111111305LL;
  SystemInformation = (HANDLE)8;
  v141[1] = 272;
  v36 = NtQuerySystemInformation(MaxSystemInfoClass|SystemProcessInformation, &SystemInformation, 8u, 0);
  if ( v36 >= 0 )
  {
    if ( (BYTE4(SystemInformation) & 2) != 0 )
      v141[0] &= ~0x100000000000uLL;
  }
  else
  {
    wil::details::in1diag3::_Log_NtStatus(
      retaddr,
      (void *)0x37F,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslutils.cpp",
      (const char *)(unsigned int)v36,
      (int)lpCommandLine);
  }
  v139[0] = 513;
  v139[2] = 3;
  v37 = a2 + 2;
  v38 = a2[2];
  v140[2] = 3;
  v140[3] = 3;
  v138[0] = v139;
  v138[2] = v140;
  v139[1] = 251658240;
  v139[3] = 1;
  v140[0] = 513;
  v140[1] = 251658240;
  v138[1] = 4;
  v138[3] = 4;
  SystemInformation = a2 + 2;
  Environment = 0;
  if ( !CreateEnvironmentBlock(&Environment, v38, 0) )
  {
    v10 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x230,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
            v39);
    if ( Environment )
      DestroyEnvironmentBlock(Environment);
    if ( v118[0] != v119 )
      operator delete(v118[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( lpCommandLine[0] != v115 )
      operator delete(lpCommandLine[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( lpApplicationName[0] != v117 )
      operator delete((void *)lpApplicationName[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v23 && !CloseHandle(v23) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v40, v41);
    if ( v24 && !CloseHandle(v24) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
LABEL_73:
    CloseThreadpoolWait(ThreadpoolWait);
    v18 = (char *)*v37;
    goto LABEL_199;
  }
  v44 = *v37;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( SetThreadToken(0, v44) )
  {
    v47 = 1;
  }
  else
  {
    v46 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x126,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslSecurity.h",
            v45);
    v47 = 0;
    v10 = v46;
    if ( v46 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23D,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
        (const char *)(unsigned int)v46,
        (int)lpThreadAttributesb);
      wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v48);
      if ( Environment )
        DestroyEnvironmentBlock(Environment);
      if ( v118[0] != v119 )
        operator delete(v118[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( lpCommandLine[0] != v115 )
        operator delete(lpCommandLine[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( lpApplicationName[0] != v117 )
        operator delete((void *)lpApplicationName[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v23 && !CloseHandle(v23) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v49, v50);
      if ( v24 && !CloseHandle(v24) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v51, v52);
      goto LABEL_73;
    }
  }
  hObject = 0;
  v53 = Container::Manager::Support::CreateOrOpenAppContainerProfile<2>(v118[0], v138, &hObject);
  v10 = v53;
  if ( v53 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x244,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
      (const char *)(unsigned int)v53,
      (int)lpThreadAttributesb);
    if ( hObject )
      LocalFree(hObject);
    if ( v47 && !RevertToSelf() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x146,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslSecurity.h",
        v55);
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v54);
    if ( Environment )
      DestroyEnvironmentBlock(Environment);
    if ( v118[0] != v119 )
      operator delete(v118[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( lpCommandLine[0] != v115 )
      operator delete(lpCommandLine[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( lpApplicationName[0] != v117 )
      operator delete((void *)lpApplicationName[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v23 && !CloseHandle(v23) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v56, v57);
    if ( v24 && !CloseHandle(v24) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v58, v59);
    goto LABEL_73;
  }
  v60 = hObject;
  v125 = v138;
  v126 = 2;
  Value = (__int64)hObject;
  hHandle = 0;
  v61 = Container::Manager::Support::BuildThreadAttributeList<2>(&Value, v134, v141, &v122, (__int64)&hHandle);
  LODWORD(hObject) = v61;
  if ( v61 >= 0 )
  {
    memset_0(&StartupInfo, 0, 0x70u);
    StartupInfo.cb = 112;
    v68 = (Container::Manager::Support *)hHandle;
    StartupInfo.wShowWindow = 0;
    v69 = *(char **)SystemInformation;
    StartupInfo.dwFlags = 1;
    v137 = hHandle;
    if ( CreateProcessAsUserW(
           v69,
           lpApplicationName[0],
           lpCommandLine[0],
           0,
           0,
           1,
           0x80400u,
           Environment,
           0,
           &StartupInfo,
           &ProcessInformation) )
    {
      if ( v68 )
        Container::Manager::Support::DeleteAndFreeProcThreadAttributeList(v68, v70);
      if ( v60 )
        LocalFree(v60);
      if ( v47 && !RevertToSelf() )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x146,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslSecurity.h",
          v78);
      v79 = WaitForSingleObjectEx(v24, 0x3A98u, 0);
      if ( v79 == 258 )
      {
        Container::Manager::Support::ProxyDaemon::Terminate(v132);
        v10 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x27E,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
                (const char *)0x5B4,
                lpThreadAttributese);
        wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v99);
        if ( Environment )
          DestroyEnvironmentBlock(Environment);
        if ( v118[0] != v119 )
          operator delete(v118[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( lpCommandLine[0] != v115 )
          operator delete(lpCommandLine[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( lpApplicationName[0] != v117 )
          operator delete((void *)lpApplicationName[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v23 && !CloseHandle(v23) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v100, v101);
        if ( v24 && !CloseHandle(v24) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v102, v103);
        CloseThreadpoolWait(ThreadpoolWait);
        v18 = *(char **)SystemInformation;
LABEL_199:
        if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          goto LABEL_200;
        return v10;
      }
      if ( v79 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xB0F,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v80);
      v81 = v132;
      v82 = pwa;
      if ( v132 == pwa )
      {
        v83 = (HANDLE *)SystemInformation;
      }
      else
      {
        v83 = (HANDLE *)((char *)pwa + 16);
        v84 = (char *)v132 + 16;
        v85 = (char *)pwa + 16;
        *(_OWORD *)v132 = *(_OWORD *)pwa;
        *(GUID *)v82 = GUID_NULL;
        wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
          v84,
          v85);
      }
      __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
        (char *)v81 + 80,
        &v120);
      if ( (struct _PROCESS_INFORMATION *)((char *)v81 + 24) != &ProcessInformation )
      {
        v86 = *(_OWORD *)&ProcessInformation.hProcess;
        v87 = *(_QWORD *)&ProcessInformation.dwProcessId;
        memset(&ProcessInformation, 0, sizeof(ProcessInformation));
        v88 = GetLastError();
        wil::details::CloseProcessInformation((Container::Manager::Support::ProxyDaemon *)((char *)v81 + 24), v89);
        SetLastError(v88);
        *(_OWORD *)((char *)v81 + 24) = v86;
        *((_QWORD *)v81 + 5) = v87;
      }
      v90 = (PTP_WAIT *)((char *)v81 + 88);
      if ( (char *)v81 + 88 != &v135 )
      {
        pwa = *v90;
        if ( pwa )
        {
          v91 = GetLastError();
          CloseThreadpoolWait(pwa);
          SetLastError(v91);
        }
        *v90 = ThreadpoolWait;
        ThreadpoolWait = 0;
      }
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
        (char *)v81 + 48,
        v118);
      v92 = (void *)*((_QWORD *)v81 + 3);
      v93 = *v90;
      *((_QWORD *)v81 + 12) = Container::Manager::Core::Details::ContainerObject::OnProxyDaemonExited;
      *((_QWORD *)v81 + 13) = v133;
      SetThreadpoolWait(v93, v92, 0);
      wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v94);
      if ( Environment )
        DestroyEnvironmentBlock(Environment);
      if ( v118[0] != v119 )
        operator delete(v118[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( lpCommandLine[0] != v115 )
        operator delete(lpCommandLine[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( lpApplicationName[0] != v117 )
        operator delete((void *)lpApplicationName[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v120 && !CloseHandle(v120) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v95, v96);
      if ( v24 && !CloseHandle(v24) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v97, v98);
      if ( ThreadpoolWait )
        CloseThreadpoolWait(ThreadpoolWait);
      if ( (char *)*v83 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(*v83);
      return 0;
    }
    else
    {
      LODWORD(hObject) = wil::details::in1diag3::Return_GetLastError(
                           retaddr,
                           (void *)0x275,
                           (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
                           v71);
      if ( v68 )
        Container::Manager::Support::DeleteAndFreeProcThreadAttributeList(v68, v72);
      if ( v60 )
        LocalFree(v60);
      if ( v47 && !RevertToSelf() )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x146,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslSecurity.h",
          v73);
      wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, (struct _PROCESS_INFORMATION *)v72);
      if ( Environment )
        DestroyEnvironmentBlock(Environment);
      if ( v118[0] != v119 )
        operator delete(v118[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( lpCommandLine[0] != v115 )
        operator delete(lpCommandLine[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( lpApplicationName[0] != v117 )
        operator delete((void *)lpApplicationName[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v23 && !CloseHandle(v23) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v74, v75);
      if ( v24 && !CloseHandle(v24) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v76, v77);
      CloseThreadpoolWait(ThreadpoolWait);
      if ( (unsigned __int64)(*(_QWORD *)SystemInformation - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(*(HANDLE *)SystemInformation);
      return (unsigned int)hObject;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x255,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
      (const char *)(unsigned int)v61,
      lpThreadAttributesd);
    if ( hHandle )
      Container::Manager::Support::DeleteAndFreeProcThreadAttributeList((Container::Manager::Support *)hHandle, v62);
    if ( v60 )
      LocalFree(v60);
    if ( v47 && !RevertToSelf() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x146,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslSecurity.h",
        v63);
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, (struct _PROCESS_INFORMATION *)v62);
    if ( Environment )
      DestroyEnvironmentBlock(Environment);
    if ( v118[0] != v119 )
      operator delete(v118[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( lpCommandLine[0] != v115 )
      operator delete(lpCommandLine[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( lpApplicationName[0] != v117 )
      operator delete((void *)lpApplicationName[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v23 && !CloseHandle(v23) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v64, v65);
    if ( v24 && !CloseHandle(v24) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v66, v67);
    CloseThreadpoolWait(ThreadpoolWait);
    if ( (char *)*v37 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(*v37);
    return (unsigned int)hObject;
  }
}

```

## disassembly

```asm
0x180111fb4  mov     rax, rsp
0x180111fb7  mov     [rax+18h], rbx
0x180111fbb  push    rbp
0x180111fbc  push    rsi
0x180111fbd  push    rdi
0x180111fbe  push    r12
0x180111fc0  push    r13
0x180111fc2  push    r14
0x180111fc4  push    r15
0x180111fc6  lea     rbp, [rax-1B8h]
0x180111fcd  sub     rsp, 280h
0x180111fd4  movaps  xmmword ptr [rax-48h], xmm6
0x180111fd8  movaps  xmmword ptr [rax-58h], xmm7
0x180111fdc  mov     rax, cs:__security_cookie
0x180111fe3  xor     rax, rsp
0x180111fe6  mov     [rbp+1B0h+var_60], rax
0x180111fed  mov     r15, rdx
0x180111ff0  mov     [rbp+1B0h+pwa], rdx
0x180111ff4  mov     rdx, rcx; pv
0x180111ff7  mov     [rbp+1B0h+var_148], rcx
0x180111ffb  lea     rcx, ?OnProcessExit@ProxyDaemon@Support@Manager@Container@@CAXQEAU_TP_CALLBACK_INSTANCE@@QEAXQEAU_TP_WAIT@@J@Z; pfnwa
0x180112002  mov     [rbp+1B0h+var_140], r9
0x180112006  xor     r8d, r8d; pcbe
0x180112009  call    cs:__imp_CreateThreadpoolWait
0x180112010  nop     dword ptr [rax+rax+00h]
0x180112015  xor     r12d, r12d
0x180112018  mov     rsi, rax
0x18011201b  test    rax, rax
0x18011201e  jnz     short loc_18011205E
0x180112020  mov     rcx, [rbp+1B8h]; this
0x180112027  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\pro"...
0x18011202e  mov     edx, 1E0h; void *
0x180112033  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180112038  mov     rdx, [r15+10h]
0x18011203c  mov     ebx, eax
0x18011203e  lea     rcx, [rdx-1]
0x180112042  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180112046  ja      short loc_180112057
0x180112048  mov     rcx, rdx; hObject
0x18011204b  call    cs:__imp_CloseHandle
0x180112052  nop     dword ptr [rax+rax+00h]
0x180112057  mov     eax, ebx
0x180112059  jmp     loc_180112F4B
0x18011205e  mov     r13d, 1
0x180112064  mov     [rsp+2B0h+hHandle], r12
0x180112069  mov     edx, r13d
0x18011206c  mov     [rbp+1B0h+var_1D0], r12
0x180112070  lea     r9, [rbp+1B0h+Value]
0x180112074  mov     [rbp+1B0h+Value], 18h
0x18011207c  lea     rcx, [rsp+2B0h+hObject]
0x180112081  mov     [rbp+1B0h+var_190], 1
0x180112089  mov     [rbp+1B0h+var_198], r12
0x18011208d  mov     [rsp+2B0h+hObject], r12
0x180112092  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180112097  mov     r14d, eax
0x18011209a  test    eax, eax
0x18011209c  jns     short loc_1801120DD
0x18011209e  mov     rcx, [rbp+1B8h]; this
0x1801120a5  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\pro"...
0x1801120ac  mov     r9d, eax; char *
0x1801120af  mov     edx, 12Ch; void *
0x1801120b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801120b9  mov     rcx, [rsp+2B0h+hObject]; hObject
0x1801120be  test    rcx, rcx
0x1801120c1  jz      loc_180112155
0x1801120c7  call    cs:__imp_CloseHandle
0x1801120ce  nop     dword ptr [rax+rax+00h]
0x1801120d3  test    eax, eax
0x1801120d5  jz      loc_180112F92
0x1801120db  jmp     short loc_180112155
0x1801120dd  lea     r9, [rbp+1B0h+Value]
0x1801120e1  mov     [rsp+2B0h+SystemInformation], r12
0x1801120e6  mov     edx, r13d
0x1801120e9  lea     rcx, [rsp+2B0h+SystemInformation]
0x1801120ee  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1801120f3  mov     r14d, eax
0x1801120f6  test    eax, eax
0x1801120f8  jns     loc_180112199
0x1801120fe  mov     rcx, [rbp+1B8h]; this
0x180112105  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\pro"...
0x18011210c  mov     r9d, eax; char *
0x18011210f  mov     edx, 12Fh; void *
0x180112114  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180112119  mov     rcx, [rsp+2B0h+SystemInformation]; hObject
0x18011211e  test    rcx, rcx
0x180112121  jz      short loc_180112137
0x180112123  call    cs:__imp_CloseHandle
0x18011212a  nop     dword ptr [rax+rax+00h]
0x18011212f  test    eax, eax
0x180112131  jz      loc_180112FDA
0x180112137  mov     rcx, [rsp+2B0h+hObject]; hObject
0x18011213c  test    rcx, rcx
0x18011213f  jz      short loc_180112155
0x180112141  call    cs:__imp_CloseHandle
0x180112148  nop     dword ptr [rax+rax+00h]
0x18011214d  test    eax, eax
0x18011214f  jz      loc_180112FEC
0x180112155  mov     rcx, [rbp+1B8h]; this
0x18011215c  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\pro"...
0x180112163  mov     r9d, r14d; char *
0x180112166  mov     edx, 1E5h; void *
0x18011216b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180112170  mov     rcx, rsi; pwa
0x180112173  call    cs:__imp_CloseThreadpoolWait
0x18011217a  nop     dword ptr [rax+rax+00h]
0x18011217f  mov     rax, [r15+10h]
0x180112183  lea     rcx, [rax-1]
0x180112187  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18011218b  ja      loc_180112F48
0x180112191  mov     rcx, rax
0x180112194  jmp     loc_180112F3C
0x180112199  lea     rdx, [rsp+2B0h+hObject]
0x18011219e  lea     rcx, [rsp+2B0h+hHandle]
0x1801121a3  call    ??4?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x1801121a8  lea     rdx, [rsp+2B0h+SystemInformation]
0x1801121ad  lea     rcx, [rbp+1B0h+var_1D0]
0x1801121b1  call    ??4?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x1801121b6  mov     rcx, [rsp+2B0h+SystemInformation]; hObject
0x1801121bb  test    rcx, rcx
0x1801121be  jz      short loc_1801121D4
0x1801121c0  call    cs:__imp_CloseHandle
0x1801121c7  nop     dword ptr [rax+rax+00h]
0x1801121cc  test    eax, eax
0x1801121ce  jz      loc_180112FFE
0x1801121d4  mov     rcx, [rsp+2B0h+hObject]; hObject
0x1801121d9  test    rcx, rcx
0x1801121dc  jz      short loc_1801121F2
0x1801121de  call    cs:__imp_CloseHandle
0x1801121e5  nop     dword ptr [rax+rax+00h]
0x1801121ea  test    eax, eax
0x1801121ec  jz      loc_180113010
0x1801121f2  mov     rdi, [rbp+1B0h+var_1D0]
0x1801121f6  lea     rax, [rbp+1B0h+var_200]
0x1801121fa  mov     rbx, [rsp+2B0h+hHandle]
0x1801121ff  lea     r9, [rbp+1B0h+lpApplicationName]
0x180112203  mov     [rbp+1B0h+lpApplicationName], rax
0x180112207  mov     r8, rdi
0x18011220a  lea     rax, [rbp+1B0h+var_200]
0x18011220e  mov     [rbp+1B0h+var_200], r12w
0x180112213  mov     [rbp+1B0h+var_208], rax
0x180112217  mov     rdx, rbx
0x18011221a  lea     rax, [rbp+1B0h+var_220]
0x18011221e  mov     [rbp+1B0h+var_220], r12w
0x180112223  mov     [rbp+1B0h+lpCommandLine], rax
0x180112227  mov     rcx, r15
0x18011222a  lea     rax, [rbp+1B0h+var_220]
0x18011222e  mov     [rbp+1B0h+var_228], rax
0x180112232  lea     rax, [rbp+1B0h+lpCommandLine]
0x180112236  mov     [rsp+2B0h+lpThreadAttributes], rax; int
0x18011223b  call    ?GetProcessParameterStrings@Support@Manager@Container@@YAJAEBU_GUID@@QEAX1AEAVPath@Csl@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Container::Manager::Support::GetProcessParameterStrings(_GUID const &,void * const,void * const,Csl::Path &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180112240  mov     r14d, eax
0x180112243  test    eax, eax
0x180112245  jns     loc_1801122E7
0x18011224b  mov     rcx, [rbp+1B8h]; this
0x180112252  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\pro"...
0x180112259  mov     r9d, eax; char *
0x18011225c  mov     edx, 1EFh; void *
0x180112261  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180112266  mov     rcx, [rbp+1B0h+lpCommandLine]; void *
0x18011226a  lea     rax, [rbp+1B0h+var_220]
0x18011226e  lea     r13, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180112275  cmp     rcx, rax
0x180112278  jz      short loc_180112282
0x18011227a  mov     rdx, r13; struct std::nothrow_t *
0x18011227d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180112282  mov     rcx, [rbp+1B0h+lpApplicationName]; void *
0x180112286  lea     rax, [rbp+1B0h+var_200]
0x18011228a  cmp     rcx, rax
0x18011228d  jz      short loc_180112297
0x18011228f  mov     rdx, r13; struct std::nothrow_t *
0x180112292  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180112297  test    rdi, rdi
0x18011229a  jz      short loc_1801122B3
0x18011229c  mov     rcx, rdi; hObject
0x18011229f  call    cs:__imp_CloseHandle
0x1801122a6  nop     dword ptr [rax+rax+00h]
0x1801122ab  test    eax, eax
0x1801122ad  jz      loc_180113022
0x1801122b3  test    rbx, rbx
0x1801122b6  jz      short loc_1801122CF
0x1801122b8  mov     rcx, rbx; hObject
0x1801122bb  call    cs:__imp_CloseHandle
0x1801122c2  nop     dword ptr [rax+rax+00h]
0x1801122c7  test    eax, eax
0x1801122c9  jz      loc_180113034
0x1801122cf  mov     rcx, rsi; pwa
0x1801122d2  call    cs:__imp_CloseThreadpoolWait
0x1801122d9  nop     dword ptr [rax+rax+00h]
0x1801122de  mov     rcx, [r15+10h]
0x1801122e2  jmp     loc_180112F32
0x1801122e7  lea     rax, [rbp+1B0h+var_1E0]
0x1801122eb  mov     [rbp+1B0h+var_1E0], r12w
0x1801122f0  mov     [rbp+1B0h+var_1F0], rax
0x1801122f4  lea     rdx, [rbp+1B0h+var_188]
0x1801122f8  lea     rax, [rbp+1B0h+var_1E0]
0x1801122fc  mov     [rbp+1B0h+var_178], r12w
0x180112301  mov     [rbp+1B0h+var_1E8], rax
0x180112305  mov     rcx, r15
0x180112308  lea     rax, [rbp+1B0h+var_178]
0x18011230c  mov     [rbp+1B0h+var_188], rax
0x180112310  lea     rax, [rbp+1B0h+var_178]
0x180112314  mov     [rbp+1B0h+var_180], rax
0x180112318  call    ?GuidToString@Csl@@YAJAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::GuidToString(_GUID const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18011231d  mov     r14d, eax
0x180112320  test    eax, eax
0x180112322  jns     short loc_18011234B
0x180112324  mov     rcx, [rbp+1B8h]; this
0x18011232b  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\pro"...
0x180112332  mov     r9d, eax; char *
0x180112335  mov     edx, 0FDh; void *
0x18011233a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011233f  lea     r13, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180112346  jmp     loc_1801123DD
0x18011234b  lea     rax, [rbp+1B0h+var_158]
0x18011234f  mov     [rbp+1B0h+var_158], r12w
0x180112354  mov     [rbp+1B0h+var_168], rax
0x180112358  lea     rdx, aCmproxyd; "CmProxyD-"
0x18011235f  lea     rax, [rbp+1B0h+var_158]
0x180112363  mov     r8d, 9
0x180112369  lea     rcx, [rbp+1B0h+var_168]
0x18011236d  mov     [rbp+1B0h+var_160], rax
0x180112371  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180112376  test    al, al
0x180112378  jnz     short loc_180112381
0x18011237a  mov     edx, 100h
0x18011237f  jmp     short loc_1801123A5
0x180112381  mov     r8, [rbp+1B0h+var_180]
0x180112385  lea     rcx, [rbp+1B0h+var_168]
0x180112389  mov     rdx, [rbp+1B0h+var_188]
0x18011238d  sub     r8, rdx
0x180112390  sar     r8, 1
0x180112393  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180112398  test    al, al
0x18011239a  jnz     loc_18011248D
0x1801123a0  mov     edx, 101h; void *
0x1801123a5  mov     rcx, [rbp+1B8h]; this
0x1801123ac  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\pro"...
0x1801123b3  mov     r14d, 8007000Eh
0x1801123b9  mov     r9d, r14d; char *
0x1801123bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801123c1  mov     rcx, [rbp+1B0h+var_168]; void *
0x1801123c5  lea     rax, [rbp+1B0h+var_158]
0x1801123c9  lea     r13, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1801123d0  cmp     rcx, rax
0x1801123d3  jz      short loc_1801123DD
0x1801123d5  mov     rdx, r13; struct std::nothrow_t *
0x1801123d8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801123dd  mov     rcx, [rbp+1B0h+var_188]; void *
0x1801123e1  lea     rax, [rbp+1B0h+var_178]
0x1801123e5  cmp     rcx, rax
0x1801123e8  jz      short loc_1801123F2
0x1801123ea  mov     rdx, r13; struct std::nothrow_t *
0x1801123ed  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801123f2  mov     rcx, [rbp+1B8h]; this
0x1801123f9  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\pro"...
0x180112400  mov     r9d, r14d; char *
0x180112403  mov     edx, 1F4h; void *
0x180112408  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011240d  mov     rcx, [rbp+1B0h+var_1F0]; void *
0x180112411  lea     rax, [rbp+1B0h+var_1E0]
0x180112415  cmp     rcx, rax
0x180112418  jz      short loc_180112422
0x18011241a  mov     rdx, r13; struct std::nothrow_t *
0x18011241d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180112422  mov     rcx, [rbp+1B0h+lpCommandLine]; void *
0x180112426  lea     rax, [rbp+1B0h+var_220]
0x18011242a  cmp     rcx, rax
0x18011242d  jz      short loc_180112437
0x18011242f  mov     rdx, r13; struct std::nothrow_t *
0x180112432  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180112437  mov     rcx, [rbp+1B0h+lpApplicationName]; void *
0x18011243b  lea     rax, [rbp+1B0h+var_200]
0x18011243f  cmp     rcx, rax
0x180112442  jz      short loc_18011244C
0x180112444  mov     rdx, r13; struct std::nothrow_t *
0x180112447  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18011244c  test    rdi, rdi
0x18011244f  jz      short loc_180112468
0x180112451  mov     rcx, rdi; hObject
0x180112454  call    cs:__imp_CloseHandle
0x18011245b  nop     dword ptr [rax+rax+00h]
0x180112460  test    eax, eax
0x180112462  jz      loc_180113046
0x180112468  test    rbx, rbx
0x18011246b  jz      loc_180112170
0x180112471  mov     rcx, rbx; hObject
0x180112474  call    cs:__imp_CloseHandle
0x18011247b  nop     dword ptr [rax+rax+00h]
0x180112480  test    eax, eax
0x180112482  jz      loc_180112FA4
0x180112488  jmp     loc_180112170
0x18011248d  lea     rdx, [rbp+1B0h+var_168]
0x180112491  lea     rcx, [rbp+1B0h+var_1F0]
0x180112495  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x18011249a  mov     rcx, [rbp+1B0h+var_168]; void *
0x18011249e  lea     rax, [rbp+1B0h+var_158]
0x1801124a2  lea     r13, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1801124a9  cmp     rcx, rax
0x1801124ac  jz      short loc_1801124B6
0x1801124ae  mov     rdx, r13; struct std::nothrow_t *
  ... truncated ...
```
