# UxUpdateManager::CommitAndRebootWithLoggedOnUser(std::vector<UxUpdateManager::UxUpdateIdentifier,std::allocator<UxUpdateManager::UxUpdateIdentifier>> const &,bool,bool)

- ea: `0x18003cf2c`
- end: `0x18003ddd6`
- name: `?CommitAndRebootWithLoggedOnUser@UxUpdateManager@@AEAA?AW4DeferReason@@AEBV?$vector@UUxUpdateIdentifier@UxUpdateManager@@V?$allocator@UUxUpdateIdentifier@UxUpdateManager@@@std@@@std@@_N1@Z`
- size: `3754`
- prototype: `__int64 __fastcall(__int64, __int64, char, char)`
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003b5e0`

## callees

- `0x180008ea8`
- `0x180009074`
- `0x18000ef80`
- `0x18000efe8`
- `0x18000f3a8`
- `0x180010890`
- `0x1800108b4`
- `0x180010e80`
- `0x180010f24`
- `0x1800112d0`
- `0x180011320`
- `0x18001151c`
- `0x180011680`
- `0x1800116fc`
- `0x18001b064`
- `0x18001dff4`
- `0x18002dedc`
- `0x18003cc10`
- `0x18003cf2c`
- `0x18003ecb8`
- `0x18003fc64`
- `0x180040160`
- `0x1800401d0`
- `0x1800420e0`
- `0x180064ed4`
- `0x180068874`
- `0x18006ea28`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003d68e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003d68e`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18003d001`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18003d001`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d3d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d3d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d420`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d420`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18003d533`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18003d533`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d3e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d408`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d448`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d46b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d5c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d5e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d60b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d6c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d6e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d70e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d7aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d7cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d7f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d925`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d94a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d96f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003da00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003da25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003da4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003dac0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003dae3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003db08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d3e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d408`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d448`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d46b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d5c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d5e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d60b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d6c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d6e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d70e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d7aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d7cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d7f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d925`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d94a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d96f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003da00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003da25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003da4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003dac0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003dae3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003db08`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18003d4cb`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18003d4cb`

## string_xrefs

- `0x18003ddad`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18003d036`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003db75`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003dbd6`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003dbef`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003dc00`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003dd1e`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003dd67`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003d15b`: `UpdateUX`
- `0x18003cf9d`: `Flag that controls FU install- skipFeatureUpdateInstall = {}`
- `0x18003d1d9`: `CommitAndRebootWithLoggedOnUser`
- `0x18003d1ee`: `CommitAndRebootWithLoggedOnUser`
- `0x18003d56a`: `UsoSession: Reboot with blocking apps UX completed`
- `0x18003d4f3`: `UsoSession: Reboot with blocking apps could not complete due to UX process launch timeout`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UxUpdateManager::CommitAndRebootWithLoggedOnUser(__int64 a1, __int64 a2, char a3, char a4)
{
  int v6; // eax
  HANDLE v7; // rax
  const char *v8; // r9
  char v9; // r12
  char v10; // al
  __int64 v11; // rcx
  __int64 v12; // r8
  __m128i v13; // xmm6
  _QWORD *System; // rax
  _QWORD *v15; // rax
  char v16; // r14
  volatile signed __int32 *v17; // rsi
  volatile signed __int32 *v18; // rsi
  int v19; // r9d
  int v20; // ecx
  UxUpdateManager *v21; // rcx
  _QWORD *v22; // rax
  __int64 (__fastcall *v23)(__int64, _BYTE *, __int128 *); // rsi
  wchar_t *traits_2_unsigned_short; // rax
  const char *v25; // r9
  __int64 v26; // r11
  __int64 v27; // rax
  _QWORD *v28; // rax
  __int64 v29; // r8
  volatile signed __int32 *v30; // rsi
  volatile signed __int32 *v31; // rsi
  wchar_t *Src; // rdx
  unsigned __int64 v33; // rcx
  WCHAR *v34; // rax
  LPHANDLE v35; // rax
  __m128i v36; // xmm7
  HANDLE v37; // xmm8_8
  DWORD LastError; // esi
  void *v39; // rcx
  unsigned int v40; // r8d
  const char *v41; // r9
  unsigned int v42; // r8d
  const char *v43; // r9
  unsigned int v44; // r8d
  const char *v45; // r9
  HANDLE *v46; // r14
  void *v47; // rax
  void *v48; // rsi
  signed int v49; // eax
  wil *v50; // rcx
  const char *v51; // r9
  __int64 v52; // r8
  __int64 v53; // rcx
  const char *v54; // r9
  unsigned int v55; // r8d
  const char *v56; // r9
  void *v57; // rcx
  unsigned int v58; // r8d
  const char *v59; // r9
  volatile signed __int32 *v60; // rsi
  DWORD v62; // eax
  unsigned int v63; // r8d
  const char *v64; // r9
  void *v65; // rcx
  unsigned int v66; // r8d
  const char *v67; // r9
  volatile signed __int32 *v68; // rsi
  unsigned int v69; // r8d
  const char *v70; // r9
  void *v71; // rcx
  unsigned int v72; // r8d
  const char *v73; // r9
  volatile signed __int32 *v74; // rsi
  __int64 **v75; // rax
  __int64 *v76; // rcx
  __int64 v77; // rax
  volatile signed __int32 *v78; // r14
  unsigned int v79; // r8d
  const char *v80; // r9
  void *v81; // rcx
  unsigned int v82; // r8d
  const char *v83; // r9
  volatile signed __int32 *v84; // rsi
  unsigned int v85; // r8d
  const char *v86; // r9
  void *v87; // rcx
  unsigned int v88; // r8d
  const char *v89; // r9
  volatile signed __int32 *v90; // rsi
  unsigned int v91; // r8d
  const char *v92; // r9
  unsigned int v93; // r8d
  const char *v94; // r9
  volatile signed __int32 *v95; // rsi
  __int64 v96; // rcx
  const char *v97; // r9
  __int64 v98; // rax
  __int64 v99; // rcx
  __int64 v100; // r8
  __int64 v101; // rcx
  __int64 v102; // r8
  __int64 v103; // rcx
  unsigned int v104; // eax
  __int64 v105; // r8
  __int64 v106; // rcx
  int v107; // [rsp+20h] [rbp-1C8h]
  unsigned int v108; // [rsp+20h] [rbp-1C8h]
  char v109[8]; // [rsp+40h] [rbp-1A8h] BYREF
  char v110; // [rsp+48h] [rbp-1A0h]
  __int128 v111; // [rsp+50h] [rbp-198h] BYREF
  HANDLE v112; // [rsp+60h] [rbp-188h] BYREF
  __int64 v113; // [rsp+68h] [rbp-180h] BYREF
  __int128 v114; // [rsp+70h] [rbp-178h] BYREF
  __int128 v115; // [rsp+80h] [rbp-168h] BYREF
  WCHAR *v116; // [rsp+90h] [rbp-158h] BYREF
  volatile signed __int32 *v117; // [rsp+98h] [rbp-150h]
  HANDLE v118[2]; // [rsp+A0h] [rbp-148h] BYREF
  HANDLE v119; // [rsp+B0h] [rbp-138h]
  char v120[8]; // [rsp+B8h] [rbp-130h] BYREF
  volatile signed __int32 *v121; // [rsp+C0h] [rbp-128h]
  HANDLE hObject; // [rsp+C8h] [rbp-120h] BYREF
  HANDLE v123; // [rsp+D0h] [rbp-118h]
  WCHAR v124[16]; // [rsp+E0h] [rbp-108h] BYREF
  _BYTE v125[32]; // [rsp+100h] [rbp-E8h] BYREF
  char v126[32]; // [rsp+120h] [rbp-C8h] BYREF
  __int64 v127; // [rsp+140h] [rbp-A8h] BYREF
  DWORD ExitCode[2]; // [rsp+148h] [rbp-A0h] BYREF
  __int128 v129; // [rsp+150h] [rbp-98h] BYREF
  unsigned int v130[4]; // [rsp+160h] [rbp-88h]
  HANDLE Handles[2]; // [rsp+170h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  v110 = a3;
  v113 = a2;
  *(_QWORD *)ExitCode = a2;
  v109[0] = a4;
  LODWORD(v116) = 0;
  v127 = 0;
  wil::CoCreateInstance<IUsoSvc,wil::err_exception_policy>(&v127);
  *(_QWORD *)&v114 = L"Flag that controls FU install- skipFeatureUpdateInstall = {}";
  *((_QWORD *)&v114 + 1) = 60;
  SystemInterface::Log<bool &>(&v114, v109);
  if ( !a4 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v127 + 48LL))(v127);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3BB,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
        (const char *)(unsigned int)v6,
        v107);
  }
  v114 = 0;
  v7 = OpenEventW(0x100002u, 0, L"Global\\USORebootCancel");
  if ( v7 )
  {
    _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
      &v114,
      v7);
    v10 = 0;
    v9 = 1;
  }
  else
  {
    v9 = 1;
    v10 = 1;
  }
  if ( v10 )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x3BF,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
      v8);
  v112 = 0;
  Windows::CallerToken::GetMostPreferredLoggedOnSessionToken(&v112);
  if ( (((unsigned __int64)v112 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LOBYTE(v12) = a4;
    UxUpdateManager::CommitAndReboot(v11, a2, v12);
  }
  v13 = 0;
  *(_OWORD *)v118 = 0;
  v119 = 0;
  try
  {
    System = (_QWORD *)SystemInterface::Service::GetSystem(&v116);
    v15 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*System + 56LL))(*System, &v111);
    v16 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 16LL))(*v15);
    v17 = (volatile signed __int32 *)*((_QWORD *)&v111 + 1);
    if ( *((_QWORD *)&v111 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v111 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
    v18 = v117;
    if ( v117 )
    {
      if ( _InterlockedExchangeAdd(v117 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    v129 = 0;
    *(_OWORD *)v130 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v129);
    LOBYTE(v19) = v16;
    UxUpdateManager::LogRebootInvokedEvent(v20, v113, (unsigned int)&v129, v19, 0);
    std::wstring::~wstring(&v129);
    UxUpdateManager::PersistRebootStartTimeValues(v21);
    v22 = (_QWORD *)SystemInterface::Service::GetSystem(&v115);
    v23 = *(__int64 (__fastcall **)(__int64, _BYTE *, __int128 *))(**(_QWORD **)(*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v22 + 8LL))(
                                                                                  *v22,
                                                                                  v120)
                                                                 + 48LL);
    traits_2_unsigned_short = (wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                           L"CommitAndRebootWithLoggedOnUser",
                                           L" /RebootWithUXForceOthers",
                                           0);
    if ( traits_2_unsigned_short == L" /RebootWithUXForceOthers"
      || (v27 = traits_2_unsigned_short - L"CommitAndRebootWithLoggedOnUser", v27 == -1) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v25);
    }
    *(_QWORD *)&v111 = L"CommitAndRebootWithLoggedOnUser";
    *((_QWORD *)&v111 + 1) = v27;
    v28 = (_QWORD *)v23(v26, v125, &v111);
    if ( v28[3] > 7u )
      v28 = (_QWORD *)*v28;
    v129 = 0;
    *(_OWORD *)v130 = 0;
    v29 = -1;
    do
      ++v29;
    while ( *((_WORD *)v28 + v29) );
    std::wstring::_Construct<1,wchar_t const *>(&v129);
    std::wstring::~wstring(v125);
    v30 = v121;
    if ( v121 )
    {
      if ( _InterlockedExchangeAdd(v121 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
        if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
      }
    }
    v31 = (volatile signed __int32 *)*((_QWORD *)&v115 + 1);
    if ( *((_QWORD *)&v115 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v115 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
        if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
      }
    }
    v116 = v124;
    Src = L" /RebootWithUX";
    if ( v110 )
      Src = L" /RebootWithUXForceOthers";
    v33 = -1;
    do
      ++v33;
    while ( Src[v33] );
    if ( 0x7FFFFFFFFFFFFFFELL - *(_QWORD *)v130 < v33 )
      std::_Xlen_string();
    std::wstring::wstring(v124, *(__int64 *)v130, Src, v33);
    v34 = (WCHAR *)std::wstring::wstring(v126, &v129);
    v35 = Windows::ProcessHelpers::CreateProcessAsUserToken(&hObject, &v112, v34, v124);
    if ( v118 != v35 )
    {
      v36 = *(__m128i *)v35;
      v37 = v35[2];
      *(_OWORD *)v35 = 0;
      v35[2] = 0;
      LastError = GetLastError();
      v39 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      if ( v39 && !CloseHandle(v39) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v40, v41);
      SetLastError(LastError);
      v13 = v36;
      *(__m128i *)v118 = v36;
      v119 = v37;
    }
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v42, v43);
    if ( v123 && !CloseHandle(v123) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v44, v45);
    std::wstring::~wstring(&v129);
    v46 = (HANDLE *)v114;
    if ( (_QWORD)v114 )
      v47 = *(void **)v114;
    else
      v47 = 0;
    Handles[0] = v47;
    v48 = (void *)v13.m128i_i64[0];
    Handles[1] = (HANDLE)v13.m128i_i64[0];
    v49 = WaitForMultipleObjects(2u, Handles, 0, 0x493E0u);
  }
  catch ( ... )
  {
    if ( (unsigned int)wil::ResultFromCaughtException(v50) != -2147024894 )
      throw;
    *(_QWORD *)&v111 = L"Reboot triggered through normal restart path";
    *((_QWORD *)&v111 + 1) = 44;
    v115 = v111;
    SystemInterface::Log<>(&v115);
    LOBYTE(v105) = v109[0];
    UxUpdateManager::CommitAndReboot(v106, *(_QWORD *)ExitCode, v105);
    if ( v118[0] && !CloseHandle(v118[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v91, v92);
    if ( v118[1] && !CloseHandle(v118[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v93, v94);
    if ( (char *)v112 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(v112);
    v95 = (volatile signed __int32 *)*((_QWORD *)&v114 + 1);
    if ( *((_QWORD *)&v114 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v114 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v95)(v95);
        if ( _InterlockedExchangeAdd(v95 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v95 + 8LL))(v95);
      }
    }
    if ( v127 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 16LL))(v127);
    return 0;
  }
  if ( v49 )
  {
    if ( v49 != 1 )
    {
      if ( v49 != 258 )
      {
        if ( v49 != -1 )
        {
          v96 = (unsigned __int16)v49 | 0x80070000;
          if ( v49 <= 0 )
            v96 = (unsigned int)v49;
          v97 = (const char *)(unsigned int)wil::verify_hresult(v96);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x441,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
            v97,
            v108);
        }
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x437,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
          v51);
      }
      *(_QWORD *)&v111 = L"UsoSession: Reboot with blocking apps could not complete due to UX process launch timeout";
      *((_QWORD *)&v111 + 1) = 89;
      SystemInterface::Log<>(&v111);
      LOBYTE(v52) = a4;
      UxUpdateManager::CommitAndReboot(v53, v113, v52);
      goto LABEL_93;
    }
    ExitCode[0] = 0;
    if ( !GetExitCodeProcess(v48, ExitCode) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x3FB,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
        v54);
    if ( ExitCode[0] == 1073807364 || ExitCode[0] == -1073741510 )
    {
      if ( v46 && *v46 )
      {
        v62 = WaitForSingleObject(*v46, 0x57E40u);
        if ( v62 )
        {
          if ( v62 != 258 )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x410,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
              (const char *)v62,
              v108);
          *(_QWORD *)&v111 = L"MoNotificationUx exited, reboot was not canceled";
          *((_QWORD *)&v111 + 1) = 48;
          SystemInterface::Log<>(&v111);
          goto LABEL_93;
        }
        *(_QWORD *)&v111 = L"MoNotificationUx exited, reboot canceled";
        *((_QWORD *)&v111 + 1) = 40;
        SystemInterface::Log<>(&v111);
        if ( v48 && !CloseHandle(v48) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v63, v64);
        v65 = (void *)_mm_srli_si128(v13, 8).m128i_u64[0];
        if ( v65 && !CloseHandle(v65) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v66, v67);
        if ( (char *)v112 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(v112);
        v68 = (volatile signed __int32 *)*((_QWORD *)&v114 + 1);
        if ( *((_QWORD *)&v114 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v114 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v68)(v68);
            if ( _InterlockedExchangeAdd(v68 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v68 + 8LL))(v68);
          }
        }
        if ( v127 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 16LL))(v127);
        return 2048;
      }
      else
      {
        v75 = (__int64 **)SystemInterface::Service::GetSystem(&v115);
        v76 = *v75;
        v77 = **v75;
        v113 = 360000;
        (*(void (__fastcall **)(__int64 *, __int64 *))(v77 + 248))(v76, &v113);
        v78 = (volatile signed __int32 *)*((_QWORD *)&v115 + 1);
        if ( *((_QWORD *)&v115 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v115 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v78)(v78);
            if ( _InterlockedExchangeAdd(v78 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v78 + 8LL))(v78);
          }
        }
        *(_QWORD *)&v111 = L"MoNotificationUx exited, reboot canceled";
        *((_QWORD *)&v111 + 1) = 40;
        SystemInterface::Log<>(&v111);
        if ( v48 && !CloseHandle(v48) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v79, v80);
        v81 = (void *)_mm_srli_si128(v13, 8).m128i_u64[0];
        if ( v81 && !CloseHandle(v81) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v82, v83);
        if ( (char *)v112 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(v112);
        v84 = (volatile signed __int32 *)*((_QWORD *)&v114 + 1);
        if ( *((_QWORD *)&v114 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v114 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v84)(v84);
            if ( _InterlockedExchangeAdd(v84 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v84 + 8LL))(v84);
          }
        }
        if ( v127 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 16LL))(v127);
        return 2048;
      }
    }
    else
    {
      if ( (ExitCode[0] & 0x80000000) == 0 )
      {
        *(_QWORD *)&v111 = L"UsoSession: Reboot with blocking apps UX completed";
        *((_QWORD *)&v111 + 1) = 50;
        SystemInterface::Log<>(&v111);
LABEL_93:
        if ( v48 && !CloseHandle(v48) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v69, v70);
        v71 = (void *)_mm_srli_si128(v13, 8).m128i_u64[0];
        if ( v71 && !CloseHandle(v71) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v72, v73);
        if ( (char *)v112 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(v112);
        v74 = (volatile signed __int32 *)*((_QWORD *)&v114 + 1);
        if ( *((_QWORD *)&v114 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v114 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v74)(v74);
            if ( _InterlockedExchangeAdd(v74 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v74 + 8LL))(v74);
          }
        }
        if ( v127 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 16LL))(v127);
        return 0;
      }
      if ( ExitCode[0] != -2147023705 )
      {
        v98 = SystemInterface::Service::GetSystem(&v115);
        LODWORD(v116) = 3;
        v99 = std::shared_ptr<SystemInterface::Service::System>::operator-><SystemInterface::Service::System,0>(v98);
        if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v99 + 168LL))(v99) || ExitCode[0] != -2147024891 )
          v9 = 0;
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v115);
        if ( v9 )
        {
          v115 = *(_OWORD *)std::wstring_view::basic_string_view<wchar_t,std::char_traits<wchar_t>>(
                              v120,
                              L"Reboot from user context is not permitted on server SKU");
          SystemInterface::Log<>(&v115);
          LOBYTE(v100) = a4;
          UxUpdateManager::CommitAndReboot(v101, v113, v100);
        }
        else if ( ExitCode[0] == -2147023625 )
        {
          v115 = *(_OWORD *)std::wstring_view::basic_string_view<wchar_t,std::char_traits<wchar_t>>(
                              v120,
                              L"Reboot for active user failed due to machine locked, try force reboot");
          SystemInterface::Log<>(&v115);
          LOBYTE(v102) = a4;
          UxUpdateManager::CommitAndReboot(v103, v113, v102);
        }
        v104 = wil::verify_hresult(ExitCode[0]);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x431,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
          (const char *)v104,
          v108);
      }
      *(_QWORD *)&v111 = L"Reboot was canceled due to other users being logged in.";
      *((_QWORD *)&v111 + 1) = 55;
      SystemInterface::Log<>(&v111);
      if ( v48 && !CloseHandle(v48) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v55, v56);
      v57 = (void *)_mm_srli_si128(v13, 8).m128i_u64[0];
      if ( v57 && !CloseHandle(v57) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v58, v59);
      if ( (char *)v112 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(v112);
      v60 = (volatile signed __int32 *)*((_QWORD *)&v114 + 1);
      if ( *((_QWORD *)&v114 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v114 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v60)(v60);
          if ( _InterlockedExchangeAdd(v60 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v60 + 8LL))(v60);
        }
      }
      if ( v127 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 16LL))(v127);
      return 0x2000;
    }
  }
  else
  {
    *(_QWORD *)&v111 = L"Reboot canceled due to blocking apps";
    *((_QWORD *)&v111 + 1) = 36;
    SystemInterface::Log<>(&v111);
    if ( v48 && !CloseHandle(v48) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v85, v86);
    v87 = (void *)_mm_srli_si128(v13, 8).m128i_u64[0];
    if ( v87 && !CloseHandle(v87) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v88, v89);
    if ( (char *)v112 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(v112);
    v90 = (volatile signed __int32 *)*((_QWORD *)&v114 + 1);
    if ( *((_QWORD *)&v114 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v114 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v90)(v90);
        if ( _InterlockedExchangeAdd(v90 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v90 + 8LL))(v90);
      }
    }
    if ( v127 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 16LL))(v127);
    return 2048;
  }
}

```

## disassembly

```asm
0x18003cf2c  mov     rax, rsp
0x18003cf2f  mov     [rax+8], rbx
0x18003cf33  push    rsi
0x18003cf34  push    rdi
0x18003cf35  push    r12
0x18003cf37  push    r13
0x18003cf39  push    r14
0x18003cf3b  sub     rsp, 1C0h
0x18003cf42  movaps  xmmword ptr [rax-38h], xmm6
0x18003cf46  movaps  xmmword ptr [rax-48h], xmm7
0x18003cf4a  movaps  xmmword ptr [rax-58h], xmm8
0x18003cf4f  mov     rax, cs:__security_cookie
0x18003cf56  xor     rax, rsp
0x18003cf59  mov     [rsp+1E8h+var_68], rax
0x18003cf61  mov     r13b, r9b
0x18003cf64  mov     [rsp+1E8h+var_1A0], r8b
0x18003cf69  mov     rdi, rdx
0x18003cf6c  mov     [rsp+1E8h+var_180], rdx
0x18003cf71  mov     qword ptr [rsp+1E8h+ExitCode], rdx
0x18003cf79  mov     [rsp+1E8h+var_1A8], r9b
0x18003cf7e  xor     ebx, ebx
0x18003cf80  mov     dword ptr [rsp+1E8h+var_158], ebx
0x18003cf87  mov     [rsp+1E8h+var_A8], rbx
0x18003cf8f  lea     rcx, [rsp+1E8h+var_A8]
0x18003cf97  call    ??$CoCreateInstance@UIUsoSvc@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIUsoSvc@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<IUsoSvc,wil::err_exception_policy>(_GUID const &,ulong)
0x18003cf9c  nop
0x18003cf9d  lea     rax, aFlagThatContro; "Flag that controls FU install- skipFeat"...
0x18003cfa4  mov     qword ptr [rsp+1E8h+var_178], rax
0x18003cfa9  mov     qword ptr [rsp+1E8h+var_178+8], 3Ch ; '<'
0x18003cfb2  lea     rdx, [rsp+1E8h+var_1A8]
0x18003cfb7  lea     rcx, [rsp+1E8h+var_178]
0x18003cfbc  call    ??$Log@AEA_N@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEA_N@Z; SystemInterface::Log<bool &>(std::wstring_view,bool &)
0x18003cfc1  test    r13b, r13b
0x18003cfc4  jnz     short loc_18003CFEA
0x18003cfc6  mov     rcx, [rsp+1E8h+var_A8]
0x18003cfce  mov     rax, [rcx]
0x18003cfd1  mov     rax, [rax+30h]
0x18003cfd5  call    _guard_dispatch_icall
0x18003cfda  mov     rcx, [rsp+1E8h]; this
0x18003cfe2  test    eax, eax
0x18003cfe4  js      loc_18003DB72
0x18003cfea  xorps   xmm1, xmm1
0x18003cfed  movdqu  [rsp+1E8h+var_178], xmm1
0x18003cff3  lea     r8, Name; "Global\\USORebootCancel"
0x18003cffa  xor     edx, edx; bInheritHandle
0x18003cffc  mov     ecx, 100002h; dwDesiredAccess
0x18003d001  call    cs:__imp_OpenEventW
0x18003d007  test    rax, rax
0x18003d00a  jnz     short loc_18003D015
0x18003d00c  lea     r12d, [rax+1]
0x18003d010  mov     al, r12b
0x18003d013  jmp     short loc_18003D02A
0x18003d015  mov     rdx, rax
0x18003d018  lea     rcx, [rsp+1E8h+var_178]
0x18003d01d  call    ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x18003d022  mov     al, bl
0x18003d024  mov     r12d, 1
0x18003d02a  mov     rcx, [rsp+1E8h]; this
0x18003d032  test    al, al
0x18003d034  jz      short loc_18003D047
0x18003d036  lea     r8, aCW1SSrcOrchest_4; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x18003d03d  mov     edx, 3BFh; void *
0x18003d042  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18003d047  mov     [rsp+1E8h+var_188], rbx
0x18003d04c  lea     rcx, [rsp+1E8h+var_188]
0x18003d051  call    ?GetMostPreferredLoggedOnSessionToken@CallerToken@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; Windows::CallerToken::GetMostPreferredLoggedOnSessionToken(void)
0x18003d056  nop
0x18003d057  mov     rax, [rsp+1E8h+var_188]
0x18003d05c  inc     rax
0x18003d05f  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003d065  jnz     short loc_18003D072
0x18003d067  mov     r8b, r13b
0x18003d06a  mov     rdx, rdi
0x18003d06d  call    ?CommitAndReboot@UxUpdateManager@@AEAAXAEBV?$vector@UUxUpdateIdentifier@UxUpdateManager@@V?$allocator@UUxUpdateIdentifier@UxUpdateManager@@@std@@@std@@_N@Z; UxUpdateManager::CommitAndReboot(std::vector<UxUpdateManager::UxUpdateIdentifier> const &,bool)
0x18003d072  xorps   xmm6, xmm6
0x18003d075  xor     eax, eax
0x18003d077  movups  xmmword ptr [rsp+1E8h+var_148], xmm6
0x18003d07f  mov     [rsp+1E8h+var_138], rax
0x18003d087  lea     rcx, [rsp+1E8h+var_158]
0x18003d08f  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18003d094  nop
0x18003d095  mov     rcx, [rax]
0x18003d098  mov     rax, [rcx]
0x18003d09b  lea     rdx, [rsp+1E8h+var_198]
0x18003d0a0  mov     rax, [rax+38h]
0x18003d0a4  call    _guard_dispatch_icall
0x18003d0a9  nop
0x18003d0aa  mov     rcx, [rax]
0x18003d0ad  mov     rax, [rcx]
0x18003d0b0  mov     rax, [rax+10h]
0x18003d0b4  call    _guard_dispatch_icall
0x18003d0b9  mov     r14b, al
0x18003d0bc  mov     rsi, [rsp+1E8h+var_190]
0x18003d0c1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003d0c5  test    rsi, rsi
0x18003d0c8  jz      short loc_18003D0FE
0x18003d0ca  mov     ecx, edi
0x18003d0cc  lock xadd [rsi+8], ecx
0x18003d0d1  add     ecx, edi
0x18003d0d3  jnz     short loc_18003D0FE
0x18003d0d5  mov     rax, [rsi]
0x18003d0d8  mov     rcx, rsi
0x18003d0db  mov     rax, [rax]
0x18003d0de  call    _guard_dispatch_icall
0x18003d0e3  mov     eax, edi
0x18003d0e5  lock xadd [rsi+0Ch], eax
0x18003d0ea  add     eax, edi
0x18003d0ec  jnz     short loc_18003D0FE
0x18003d0ee  mov     rax, [rsi]
0x18003d0f1  mov     rcx, rsi
0x18003d0f4  mov     rax, [rax+8]
0x18003d0f8  call    _guard_dispatch_icall
0x18003d0fd  nop
0x18003d0fe  mov     rsi, [rsp+1E8h+var_150]
0x18003d106  test    rsi, rsi
0x18003d109  jz      short loc_18003D13E
0x18003d10b  mov     eax, edi
0x18003d10d  lock xadd [rsi+8], eax
0x18003d112  add     eax, edi
0x18003d114  jnz     short loc_18003D13E
0x18003d116  mov     rax, [rsi]
0x18003d119  mov     rcx, rsi
0x18003d11c  mov     rax, [rax]
0x18003d11f  call    _guard_dispatch_icall
0x18003d124  mov     eax, edi
0x18003d126  lock xadd [rsi+0Ch], eax
0x18003d12b  add     eax, edi
0x18003d12d  jnz     short loc_18003D13E
0x18003d12f  mov     rax, [rsi]
0x18003d132  mov     rcx, rsi
0x18003d135  mov     rax, [rax+8]
0x18003d139  call    _guard_dispatch_icall
0x18003d13e  xorps   xmm0, xmm0
0x18003d141  movups  [rsp+1E8h+var_98], xmm0
0x18003d149  xorps   xmm1, xmm1
0x18003d14c  movdqu  xmmword ptr [rsp+1E8h+var_88], xmm1
0x18003d155  mov     r8d, 8
0x18003d15b  lea     rdx, aUpdateux; "UpdateUX"
0x18003d162  lea     rcx, [rsp+1E8h+var_98]
0x18003d16a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003d16f  nop
0x18003d170  mov     byte ptr [rsp+1E8h+var_1C8], bl
0x18003d174  mov     r9b, r14b
0x18003d177  lea     r8, [rsp+1E8h+var_98]
0x18003d17f  mov     rdx, [rsp+1E8h+var_180]
0x18003d184  call    ?LogRebootInvokedEvent@UxUpdateManager@@AEAAXAEBV?$vector@UUxUpdateIdentifier@UxUpdateManager@@V?$allocator@UUxUpdateIdentifier@UxUpdateManager@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@E_N@Z; UxUpdateManager::LogRebootInvokedEvent(std::vector<UxUpdateManager::UxUpdateIdentifier> const &,std::wstring const &,uchar,bool)
0x18003d189  nop
0x18003d18a  lea     rcx, [rsp+1E8h+var_98]; void *
0x18003d192  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d197  call    ?PersistRebootStartTimeValues@UxUpdateManager@@AEAAXXZ; UxUpdateManager::PersistRebootStartTimeValues(void)
0x18003d19c  lea     rcx, [rsp+1E8h+var_168]
0x18003d1a4  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18003d1a9  nop
0x18003d1aa  mov     rcx, [rax]
0x18003d1ad  mov     rax, [rcx]
0x18003d1b0  lea     rdx, [rsp+1E8h+var_130]
0x18003d1b8  mov     rax, [rax+8]
0x18003d1bc  call    _guard_dispatch_icall
0x18003d1c1  nop
0x18003d1c2  mov     r11, [rax]
0x18003d1c5  mov     rax, [r11]
0x18003d1c8  mov     rsi, [rax+30h]
0x18003d1cc  xor     r8d, r8d
0x18003d1cf  lea     r14, aRebootwithuxfo; " /RebootWithUXForceOthers"
0x18003d1d6  mov     rdx, r14
0x18003d1d9  lea     rcx, aCommitandreboo; "CommitAndRebootWithLoggedOnUser"
0x18003d1e0  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18003d1e5  cmp     rax, r14
0x18003d1e8  jz      loc_18003DDA5
0x18003d1ee  lea     rcx, aCommitandreboo; "CommitAndRebootWithLoggedOnUser"
0x18003d1f5  sub     rax, rcx
0x18003d1f8  sar     rax, 1
0x18003d1fb  cmp     rax, rdi
0x18003d1fe  jz      loc_18003DDA5
0x18003d204  mov     [rsp+1E8h+var_198], rcx
0x18003d209  mov     [rsp+1E8h+var_190], rax
0x18003d20e  lea     r8, [rsp+1E8h+var_198]
0x18003d213  lea     rdx, [rsp+1E8h+var_E8]
0x18003d21b  mov     rcx, r11
0x18003d21e  mov     rax, rsi
0x18003d221  call    _guard_dispatch_icall
0x18003d226  nop
0x18003d227  cmp     qword ptr [rax+18h], 7
0x18003d22c  jbe     short loc_18003D231
0x18003d22e  mov     rax, [rax]
0x18003d231  xorps   xmm0, xmm0
0x18003d234  movups  [rsp+1E8h+var_98], xmm0
0x18003d23c  xorps   xmm1, xmm1
0x18003d23f  movdqu  xmmword ptr [rsp+1E8h+var_88], xmm1
0x18003d248  mov     r8, rdi
0x18003d24b  inc     r8
0x18003d24e  cmp     [rax+r8*2], bx
0x18003d253  jnz     short loc_18003D24B
0x18003d255  mov     rdx, rax
0x18003d258  lea     rcx, [rsp+1E8h+var_98]
0x18003d260  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003d265  nop
0x18003d266  lea     rcx, [rsp+1E8h+var_E8]; void *
0x18003d26e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d273  nop
0x18003d274  mov     rsi, [rsp+1E8h+var_128]
0x18003d27c  test    rsi, rsi
0x18003d27f  jz      short loc_18003D2B5
0x18003d281  mov     eax, edi
0x18003d283  lock xadd [rsi+8], eax
0x18003d288  add     eax, edi
0x18003d28a  jnz     short loc_18003D2B5
0x18003d28c  mov     rax, [rsi]
0x18003d28f  mov     rcx, rsi
0x18003d292  mov     rax, [rax]
0x18003d295  call    _guard_dispatch_icall
0x18003d29a  mov     eax, edi
0x18003d29c  lock xadd [rsi+0Ch], eax
0x18003d2a1  add     eax, edi
0x18003d2a3  jnz     short loc_18003D2B5
0x18003d2a5  mov     rax, [rsi]
0x18003d2a8  mov     rcx, rsi
0x18003d2ab  mov     rax, [rax+8]
0x18003d2af  call    _guard_dispatch_icall
0x18003d2b4  nop
0x18003d2b5  mov     rsi, qword ptr [rsp+1E8h+var_168+8]
0x18003d2bd  test    rsi, rsi
0x18003d2c0  jz      short loc_18003D2F5
0x18003d2c2  mov     eax, edi
0x18003d2c4  lock xadd [rsi+8], eax
0x18003d2c9  add     eax, edi
0x18003d2cb  jnz     short loc_18003D2F5
0x18003d2cd  mov     rax, [rsi]
0x18003d2d0  mov     rcx, rsi
0x18003d2d3  mov     rax, [rax]
0x18003d2d6  call    _guard_dispatch_icall
0x18003d2db  mov     eax, edi
0x18003d2dd  lock xadd [rsi+0Ch], eax
0x18003d2e2  add     eax, edi
0x18003d2e4  jnz     short loc_18003D2F5
0x18003d2e6  mov     rax, [rsi]
0x18003d2e9  mov     rcx, rsi
0x18003d2ec  mov     rax, [rax+8]
0x18003d2f0  call    _guard_dispatch_icall
0x18003d2f5  lea     rax, [rsp+1E8h+var_108]
0x18003d2fd  mov     [rsp+1E8h+var_158], rax
0x18003d305  lea     rax, aRebootwithuxfo; " /RebootWithUXForceOthers"
0x18003d30c  lea     rdx, aRebootwithux; " /RebootWithUX"
0x18003d313  cmp     [rsp+1E8h+var_1A0], bl
0x18003d317  cmovnz  rdx, rax
0x18003d31b  mov     rcx, rdi
0x18003d31e  inc     rcx
0x18003d321  cmp     [rdx+rcx*2], bx
0x18003d325  jnz     short loc_18003D31E
0x18003d327  mov     rax, 7FFFFFFFFFFFFFFEh
0x18003d331  mov     r8, qword ptr [rsp+1E8h+var_88]
0x18003d339  sub     rax, r8
0x18003d33c  cmp     rax, rcx
0x18003d33f  jb      loc_18003DB87
0x18003d345  lea     r9, [rsp+1E8h+var_98]
0x18003d34d  cmp     qword ptr [rsp+1E8h+var_88+8], 7
0x18003d356  cmova   r9, qword ptr [rsp+1E8h+var_98]
0x18003d35f  mov     [rsp+1E8h+var_1B8], rcx; __int64
0x18003d364  mov     [rsp+1E8h+Src], rdx; Src
0x18003d369  mov     qword ptr [rsp+1E8h+var_1C8], r8; unsigned int
0x18003d36e  lea     rcx, [rsp+1E8h+var_108]; void *
0x18003d376  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18003d37b  nop
0x18003d37c  lea     rdx, [rsp+1E8h+var_98]
0x18003d384  lea     rcx, [rsp+1E8h+var_C8]
0x18003d38c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003d391  nop
0x18003d392  lea     r9, [rsp+1E8h+var_108]
0x18003d39a  mov     r8, rax
0x18003d39d  lea     rdx, [rsp+1E8h+var_188]
0x18003d3a2  lea     rcx, [rsp+1E8h+hObject]; lpTargetHandle
0x18003d3aa  call    ?CreateProcessAsUserToken@ProcessHelpers@Windows@@YA?AV?$unique_struct@U_PROCESS_INFORMATION@@P6AXPEAU1@@Z$1?CloseProcessInformation@details@wil@@YAX0@Z$$T$0A@@wil@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@4@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; Windows::ProcessHelpers::CreateProcessAsUserToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,std::wstring,std::wstring)
0x18003d3af  lea     rcx, [rsp+1E8h+var_148]
0x18003d3b7  cmp     rcx, rax
0x18003d3ba  jz      short loc_18003D43B
0x18003d3bc  movups  xmm7, xmmword ptr [rax]
0x18003d3bf  movsd   xmm8, qword ptr [rax+10h]
0x18003d3c5  xorps   xmm0, xmm0
0x18003d3c8  xor     ecx, ecx
0x18003d3ca  movups  xmmword ptr [rax], xmm0
0x18003d3cd  mov     [rax+10h], rcx
0x18003d3d1  call    cs:__imp_GetLastError
0x18003d3d7  mov     esi, eax
0x18003d3d9  movq    rcx, xmm6; hObject
0x18003d3de  test    rcx, rcx
0x18003d3e1  jz      short loc_18003D3F9
0x18003d3e3  call    cs:__imp_CloseHandle
0x18003d3e9  mov     rcx, [rsp+1E8h]; this
0x18003d3f1  test    eax, eax
0x18003d3f3  jz      loc_18003DB8C
0x18003d3f9  psrldq  xmm6, 8
0x18003d3fe  movq    rcx, xmm6; hObject
0x18003d403  test    rcx, rcx
0x18003d406  jz      short loc_18003D41E
0x18003d408  call    cs:__imp_CloseHandle
0x18003d40e  mov     rcx, [rsp+1E8h]; this
0x18003d416  test    eax, eax
0x18003d418  jz      loc_18003DB97
0x18003d41e  mov     ecx, esi; dwErrCode
0x18003d420  call    cs:__imp_SetLastError
  ... truncated ...
```
