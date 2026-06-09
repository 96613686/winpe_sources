# Microsoft::Diagnostics::RunExeHelperDef::RunExecutable(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,Microsoft::Diagnostics::ScenarioInst const &,Microsoft::Diagnostics::EscalationWorkItemState &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,bool,unsigned __int64 *)

- ea: `0x18033272c`
- end: `0x180335013`
- name: `?RunExecutable@RunExeHelperDef@Diagnostics@Microsoft@@IEBAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBVScenarioInst@23@AEAVEscalationWorkItemState@23@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@_NPEA_K@Z`
- size: `10471`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, int, PULONG64 CycleTime)`
- caller_count: `1`
- callee_count: `57`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180314c00`

## callees

- `0x180004bec`
- `0x18000bd98`
- `0x18001b510`
- `0x180020e6c`
- `0x18002110c`
- `0x180027c28`
- `0x180027e50`
- `0x18002967c`
- `0x18002abec`
- `0x18002ac10`
- `0x18002b770`
- `0x18002b7c0`
- `0x18002cb04`
- `0x18002df00`
- `0x18003c66c`
- `0x180049d00`
- `0x18004add0`
- `0x18005fb44`
- `0x180064e34`
- `0x180064e6c`
- `0x180064e8c`
- `0x180069268`
- `0x18008a4ec`
- `0x18008a51c`
- `0x18008a580`
- `0x18008a5d8`
- `0x18008ab10`
- `0x18008abf4`
- `0x18009c8c0`
- `0x1800afab0`
- `0x1800b47f0`
- `0x1800bc658`
- `0x1800be65c`
- `0x1800be80c`
- `0x1800c5130`
- `0x1800c582c`
- `0x1800c5d5c`
- `0x1800cf7d8`
- `0x1800d1484`
- `0x1800e9a00`
- `0x1800f7b34`
- `0x180102bbc`
- `0x180129fe0`
- `0x18012f380`
- `0x1801385c0`
- `0x18013cca4`
- `0x180142fcc`
- `0x18016323c`
- `0x1801b2084`
- `0x1801dd408`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18033406c`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18033406c`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1803341c3`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1803341c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180332b37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180333aea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180333eaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180332b37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180333aea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180333eaf`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1803342c4`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1803342c4`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180333adc`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180333adc`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1803348b7`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1803348b7`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180332a16`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180332a16`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180332850`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180332949`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180332850`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180332949`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180332b29`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180332b29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180332b13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180332b13`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180333ea9`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180333ea9`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x180334514`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x1803347cb`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x1803348ff`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x180334c9a`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x180334e6e`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x180334514`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x1803347cb`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x1803348ff`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x180334c9a`
- `api-ms-win-core-realtime-l1-1-0!QueryProcessCycleTime` at `0x180334e6e`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18033434c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18033434c`
- `USERENV!DestroyEnvironmentBlock` at `0x180332e87`
- `USERENV!DestroyEnvironmentBlock` at `0x180334f4d`
- `USERENV!DestroyEnvironmentBlock` at `0x180332e87`
- `USERENV!DestroyEnvironmentBlock` at `0x180334f4d`
- `USERENV!CreateEnvironmentBlock` at `0x180332d0f`
- `USERENV!CreateEnvironmentBlock` at `0x180332d0f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180332c79`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180332c79`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x180333809`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x180333809`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x18033437e`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x1803345fa`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x1803349e6`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x18033437e`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x1803345fa`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x1803349e6`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x180333937`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x180333937`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x180333e90`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x180333e90`

## string_xrefs

- `0x180333084`: `ExpandedCommandLine`
- `0x18033278c`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180332b57`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180332c8b`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180332d21`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180333128`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180333149`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180333324`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x1803334d4`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18033383f`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180333950`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180333c65`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180333c89`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180333ec8`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180334094`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x1803341d9`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x1803344b4`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x1803344d5`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18033476b`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x18033478c`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x1803348cd`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180334c3a`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180334c69`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180334ff2`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180335002`: `onecore\base\telemetry\utc\service\scenarios\actions\runexehelper.cpp`
- `0x180334384`: `RunExeWithArgsAction_ExeTerminated_ServiceShuttingDown_0`
- `0x180333e37`: `IsValid(childProcessMainThread)`
- `0x180333652`: `Action is running as SYSTEM and targets %temp%.  Redirecting to UTC temp path.\n`
- `0x18033326f`: `Redirecting CiDiag output to UTC temp path.\n`
- `0x180333b04`: `RunExeWithArgsAction_FailedToCreateProcess_0`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
__int64 __fastcall Microsoft::Diagnostics::RunExeHelperDef::RunExecutable(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        PULONG64 CycleTime)
{
  __int64 result; // rax
  _QWORD *v9; // rax
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  int v12; // ecx
  int v13; // r8d
  const char *v14; // r9
  ULONG_PTR v15; // rdx
  Microsoft::Diagnostics::LifetimeManager *v16; // rcx
  Microsoft::Diagnostics::TelemetryAssert *TelemetryAssert; // rax
  int v18; // eax
  int v19; // ecx
  int v20; // r8d
  const char *v21; // r9
  Microsoft::Diagnostics::LifetimeManager *v22; // rcx
  Microsoft::Diagnostics::TelemetryAssert *v23; // rax
  int v24; // eax
  char v25; // bl
  __int64 v26; // r8
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  unsigned int v29; // ebx
  const struct std::nothrow_t *v30; // rdx
  const char *v31; // r9
  const struct std::nothrow_t *v32; // rdx
  const char *v33; // r9
  unsigned int v34; // ebx
  const struct std::nothrow_t *v35; // rdx
  __int64 v36; // r8
  const char *v37; // r9
  unsigned int v38; // ebx
  const struct std::nothrow_t *v39; // rdx
  __int64 v40; // r8
  _OWORD *v41; // rax
  __int64 v42; // rbx
  const char *v43; // r9
  __int64 v44; // rbx
  __int64 v45; // r8
  __int64 v46; // r8
  _QWORD *v47; // rax
  int v48; // eax
  const struct std::nothrow_t *v49; // rdx
  __int64 v50; // rbx
  __int64 v51; // r8
  __int64 v52; // r8
  int v53; // eax
  __int64 v54; // r8
  unsigned int v55; // ebx
  const struct std::nothrow_t *v56; // rdx
  _QWORD *v57; // rax
  __int64 v58; // r8
  __int64 v59; // r8
  __int64 v60; // r8
  int v61; // eax
  unsigned int v62; // ebx
  const struct std::nothrow_t *v63; // rdx
  int v64; // r8d
  int v65; // r9d
  WCHAR *v66; // rax
  _QWORD *v67; // rax
  void *appended; // rax
  WCHAR *v69; // rcx
  __int64 v70; // r8
  __int64 v71; // rax
  void *v72; // r8
  void *v73; // rax
  void *v74; // rax
  __int64 v75; // rax
  void *v76; // r8
  HANDLE JobObjectW; // rax
  const char *v78; // r9
  HANDLE v79; // rbx
  unsigned int v80; // ebx
  const struct std::nothrow_t *v81; // rdx
  unsigned int v82; // ebx
  const struct std::nothrow_t *v83; // rdx
  WCHAR *v84; // r8
  const WCHAR *v85; // rdx
  int v86; // eax
  int v87; // eax
  DWORD v88; // ebx
  const struct std::nothrow_t *v89; // rdx
  Microsoft::Diagnostics::LifetimeManager *v90; // rcx
  int v91; // r8d
  int v92; // r9d
  Microsoft::Diagnostics::TelemetryAssert *v93; // rax
  Microsoft::Diagnostics::LifetimeManager *v94; // rcx
  Microsoft::Diagnostics::TelemetryAssert *v95; // rax
  DWORD v96; // eax
  unsigned int v97; // ebx
  const struct std::nothrow_t *v98; // rdx
  const struct std::nothrow_t *v99; // rdx
  HANDLE WaitableTimer; // rdi
  const char *v101; // r9
  unsigned int v102; // ebx
  const struct std::nothrow_t *v103; // rdx
  DWORD v104; // eax
  const char *v105; // r9
  unsigned int v106; // ebx
  const struct std::nothrow_t *v107; // rdx
  __int64 v108; // rdi
  __int64 *v109; // rcx
  DWORD v110; // eax
  int v111; // eax
  const struct std::nothrow_t *v112; // rdx
  int v113; // eax
  const char *v114; // r9
  unsigned int v115; // ebx
  const struct std::nothrow_t *v116; // rdx
  int v117; // ecx
  int v118; // r8d
  int v119; // r9d
  __int128 *v120; // rax
  WCHAR *v121; // rax
  void *v122; // rax
  void *v123; // rax
  __int64 v124; // r8
  int v125; // eax
  const struct std::nothrow_t *v126; // rdx
  _QWORD *v127; // rdx
  const struct std::nothrow_t *v128; // rdx
  const struct std::nothrow_t *v129; // rdx
  int cbSize; // [rsp+20h] [rbp-878h]
  unsigned int cbSizea; // [rsp+20h] [rbp-878h]
  int cbSizeb; // [rsp+20h] [rbp-878h]
  unsigned int cbSizec; // [rsp+20h] [rbp-878h]
  int cbSized; // [rsp+20h] [rbp-878h]
  int cbSizee; // [rsp+20h] [rbp-878h]
  int cbSizef; // [rsp+20h] [rbp-878h]
  int cbSizeg; // [rsp+20h] [rbp-878h]
  __m128i v138; // [rsp+60h] [rbp-838h] BYREF
  DWORD ExitCode; // [rsp+70h] [rbp-828h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp-820h] BYREF
  void *phNewToken; // [rsp+80h] [rbp-818h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+88h] [rbp-810h] BYREF
  _BYTE Value[8]; // [rsp+90h] [rbp-808h] BYREF
  HANDLE hProcess; // [rsp+98h] [rbp-800h] BYREF
  unsigned int v145[4]; // [rsp+A0h] [rbp-7F8h] BYREF
  LPVOID Environment[2]; // [rsp+B0h] [rbp-7E8h] BYREF
  LARGE_INTEGER DueTime[2]; // [rsp+C0h] [rbp-7D8h] BYREF
  __int128 v148; // [rsp+D0h] [rbp-7C8h] BYREF
  __int64 v149; // [rsp+E0h] [rbp-7B8h]
  ULONG_PTR Size; // [rsp+E8h] [rbp-7B0h] BYREF
  __int128 v151; // [rsp+F0h] [rbp-7A8h] BYREF
  _BYTE v152[16]; // [rsp+100h] [rbp-798h] BYREF
  _QWORD v153[2]; // [rsp+110h] [rbp-788h] BYREF
  char v154; // [rsp+120h] [rbp-778h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+128h] [rbp-770h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+140h] [rbp-758h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST v157; // [rsp+1A8h] [rbp-6F0h]
  _BYTE v158[72]; // [rsp+1B0h] [rbp-6E8h] BYREF
  __int64 v159; // [rsp+1F8h] [rbp-6A0h]
  WCHAR v160[12]; // [rsp+200h] [rbp-698h] BYREF
  unsigned __int64 v161; // [rsp+218h] [rbp-680h]
  _QWORD Src[2]; // [rsp+220h] [rbp-678h] BYREF
  __int64 v163; // [rsp+230h] [rbp-668h]
  unsigned __int64 v164; // [rsp+238h] [rbp-660h]
  WCHAR v165[8]; // [rsp+240h] [rbp-658h] BYREF
  __int64 v166; // [rsp+250h] [rbp-648h]
  unsigned __int64 v167; // [rsp+258h] [rbp-640h]
  HANDLE hJob[4]; // [rsp+260h] [rbp-638h] BYREF
  LPCWSTR lpApplicationName[4]; // [rsp+280h] [rbp-618h] BYREF
  __int128 v170; // [rsp+2A0h] [rbp-5F8h] BYREF
  __m128i v171; // [rsp+2B0h] [rbp-5E8h]
  LPWSTR lpCommandLine[2]; // [rsp+2C0h] [rbp-5D8h] BYREF
  __m128i si128; // [rsp+2D0h] [rbp-5C8h]
  _QWORD v174[4]; // [rsp+2F0h] [rbp-5A8h] BYREF
  _QWORD JobObjectInformation[2]; // [rsp+310h] [rbp-588h] BYREF
  int v176; // [rsp+320h] [rbp-578h]
  char v177; // [rsp+350h] [rbp-548h]
  _QWORD v178[7]; // [rsp+360h] [rbp-538h] BYREF
  _QWORD *v179; // [rsp+398h] [rbp-500h]
  int v180[282]; // [rsp+3A0h] [rbp-4F8h] BYREF
  int v181[14]; // [rsp+808h] [rbp-90h] BYREF
  HANDLE Handles[2]; // [rsp+840h] [rbp-58h] BYREF
  __int64 v183; // [rsp+850h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+898h] [rbp+0h]

  *(_QWORD *)v145 = a4;
  *(_QWORD *)&v151 = a1;
  v159 = a5;
  if ( !*(_QWORD *)(a2 + 8) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
      (const char *)0x8007010BLL,
      cbSize);
    std::wstring::_Tidy_deallocate(a5);
    return 2147942667LL;
  }
  try
  {
    std::wstring::wstring(Src, a2);
    Microsoft::Diagnostics::Utils::String::PrependLongPathUnicodePrefix(Src);
    v9 = Src;
    if ( v164 > 7 )
      v9 = (_QWORD *)Src[0];
    if ( *((_WORD *)v9 + v163 - 1) == 92 )
    {
      v10 = --v163;
      v11 = Src;
      if ( v164 > 7 )
        v11 = (_QWORD *)Src[0];
      *((_WORD *)v11 + v10) = 0;
    }
    ExitCode = 0;
    ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
      Value,
      &ExitCode);
    Size = 0;
    InitializeProcThreadAttributeList(0, 1u, 0, &Size);
    v15 = Size;
    if ( Size )
      goto LABEL_16;
    if ( (unsigned int)dword_1804543B0 > 2 )
    {
      DueTime[0].QuadPart = (LONGLONG)"RunExecutable";
      Environment[0] = "attributesSize > 0";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v12,
        (unsigned int)word_180403672,
        v13,
        (_DWORD)v14,
        (__int64)Environment,
        (__int64)DueTime);
    }
    if ( Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager) )
    {
      TelemetryAssert = Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(v16);
      Microsoft::Diagnostics::TelemetryAssert::Assert(TelemetryAssert);
    }
    v15 = Size;
    if ( Size )
LABEL_16:
      v18 = 1;
    else
      v18 = 0;
    if ( !v18 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x2E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
        v14);
    std::make_unique<unsigned char [0],0>(&lpAttributeList, v15);
    InitializeProcThreadAttributeList(lpAttributeList, 1u, 0, &Size);
    if ( Size )
      goto LABEL_25;
    if ( (unsigned int)dword_1804543B0 > 2 )
    {
      DueTime[0].QuadPart = (LONGLONG)"RunExecutable";
      Environment[0] = "attributesSize > 0";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v19,
        (unsigned int)&byte_180403637,
        v20,
        (_DWORD)v21,
        (__int64)Environment,
        (__int64)DueTime);
    }
    if ( Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager) )
    {
      v23 = Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(v22);
      Microsoft::Diagnostics::TelemetryAssert::Assert(v23);
    }
    if ( Size )
LABEL_25:
      v24 = 1;
    else
      v24 = 0;
    if ( !v24 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
        v21);
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      Value,
      0);
    UpdateProcThreadAttribute(lpAttributeList, 0, 0x20002u, Value, 8u, 0, 0);
    memset_0(&StartupInfo, 0, 0x70u);
    StartupInfo.cb = 112;
    StartupInfo.dwFlags = 256;
    v157 = lpAttributeList;
    phNewToken = 0;
    v148 = 0;
    v149 = 0;
    v25 = 0;
    v138 = *(__m128i *)&Microsoft::Diagnostics::RunExeHelperDef::k_hcsdiagPath;
    *(_OWORD *)&DueTime[0].LowPart = *(_OWORD *)std::wstring::operator std::wstring_view(v151 + 128, hJob, v26);
    if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(DueTime, &v138) )
    {
      if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_1804543B0,
          byte_1804036AD);
      v25 = 1;
    }
    TokenHandle = 0;
    if ( !v25 )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &TokenHandle,
        0);
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
      {
        LastError = GetLastError();
        if ( LastError != 1008 )
        {
          if ( LastError )
          {
            v29 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x67,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
                    (const char *)LastError,
                    cbSizea);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
            std::vector<wchar_t>::_Tidy(&v148);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
            std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&lpAttributeList, v30);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
            std::wstring::_Tidy_deallocate(Src);
            std::wstring::_Tidy_deallocate(a5);
            return v29;
          }
          else
          {
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
            std::vector<wchar_t>::_Tidy(&v148);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
            std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&lpAttributeList, v32);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
            std::wstring::_Tidy_deallocate(Src);
            std::wstring::_Tidy_deallocate(a5);
            return 0;
          }
        }
      }
    }
    Environment[0] = 0;
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &phNewToken,
        0);
      if ( !DuplicateTokenEx(TokenHandle, 0xF01FFu, 0, SecurityImpersonation, TokenPrimary, &phNewToken) )
      {
        v34 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x79,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
                v33);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        std::vector<wchar_t>::_Tidy(&v148);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&lpAttributeList, v35);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
        std::wstring::_Tidy_deallocate(Src);
        std::wstring::_Tidy_deallocate(a5);
        return v34;
      }
    }
    if ( !CreateEnvironmentBlock(Environment, phNewToken, 0) )
    {
      v38 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x7C,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
              v37);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      std::vector<wchar_t>::_Tidy(&v148);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&lpAttributeList, v39);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(a5);
      return v38;
    }
    v138.m128i_i64[0] = (__int64)Environment;
    v138.m128i_i8[8] = 1;
    *(_OWORD *)&DueTime[0].LowPart = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v153, v36);
    v41 = (_OWORD *)std::wstring::operator std::wstring_view(qword_1804635E8, v152, v40);
    try
    {
      *(_OWORD *)hJob = *v41;
      v42 = Microsoft::Diagnostics::Utils::String::AddEnvironmentVariableToBlock(v174);
      if ( &v148 == (__int128 *)v42 )
      {
        DueTime[0].QuadPart = v148;
      }
      else
      {
        std::vector<wchar_t>::_Tidy(&v148);
        DueTime[0] = *(LARGE_INTEGER *)v42;
        *(LARGE_INTEGER *)&v148 = DueTime[0];
        *((_QWORD *)&v148 + 1) = *(_QWORD *)(v42 + 8);
        v149 = *(_QWORD *)(v42 + 16);
        *(_QWORD *)v42 = 0;
        *(_QWORD *)(v42 + 8) = 0;
        *(_QWORD *)(v42 + 16) = 0;
      }
      std::vector<wchar_t>::_Tidy(v174);
      DestroyEnvironmentBlock(Environment[0]);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    }
    catch ( ... )
    {
      v145[0] = wil::details::in1diag3::Return_CaughtException(
                  retaddr,
                  (void *)0x86,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
                  v43);
      DestroyEnvironmentBlock(Environment[0]);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      std::vector<wchar_t>::_Tidy(&v148);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&lpAttributeList, v129);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(v159);
      return v145[0];
    }
    std::wstring::wstring(lpApplicationName, &Microsoft::Diagnostics::RunExeHelperDef::k_runExeHelperPath);
    v44 = v151 + 128;
    std::wstring::wstring(v165, v151 + 128);
    std::wstring::wstring(v160, a5);
    Microsoft::Diagnostics::WideStringStream::WideStringStream((Microsoft::Diagnostics::WideStringStream *)lpCommandLine);
    v138 = *(__m128i *)&Microsoft::Diagnostics::RunExeHelperDef::k_hcsdiagPath;
    *(_OWORD *)Environment = *(_OWORD *)std::wstring::operator std::wstring_view(v44, v152, v45);
    if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(Environment, &v138) )
    {
      v138 = *(__m128i *)std::wstring::operator std::wstring_view(v160, v152, v46);
      v47 = Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(a3, JobObjectInformation, &v138);
      std::wstring::operator=(v160, v47);
      std::wstring::_Tidy_deallocate(JobObjectInformation);
      ExitCode = Microsoft::Diagnostics::AgentManager::ResolveContainerId(v160);
      if ( (ExitCode & 0x80000000) != 0 )
      {
        v138.m128i_i64[0] = (__int64)L"RunExeWithArgsAction_FailedToResolveContainerId";
        v138.m128i_i64[1] = 47;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
          (unsigned int)v180,
          (unsigned int)&v138,
          0x1000000,
          0,
          0,
          0,
          0);
        v138.m128i_i64[0] = (__int64)L"ExeName";
        v138.m128i_i64[1] = 7;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v180, v181, &v138, v44);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a3 + 56) + 72LL))(*(_QWORD *)(a3 + 56));
        v138.m128i_i64[0] = (__int64)L"ScenarioId";
        v138.m128i_i64[1] = 10;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((int)v180, (int)v181);
        v138.m128i_i64[0] = (__int64)L"ScenarioInstanceId";
        v138.m128i_i64[1] = 18;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((int)v180, (int)v181);
        v138.m128i_i64[0] = (__int64)L"ExpandedCommandLine";
        v138.m128i_i64[1] = 19;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v180, v181, &v138, v160);
        v138.m128i_i64[0] = (__int64)L"ErrorCode";
        v138.m128i_i64[1] = 9;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<long>((int)v180, (int)v181);
        v138 = 0;
        Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(v145, &v138);
        v48 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v180);
        if ( v48 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xA6,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
            (const char *)(unsigned int)v48,
            cbSizeb);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA8,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
          (const char *)0x87C51036LL,
          cbSizeb);
        Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v180);
        std::wstring::_Tidy_deallocate(lpCommandLine);
        std::wstring::_Tidy_deallocate(v160);
        std::wstring::_Tidy_deallocate(v165);
        std::wstring::_Tidy_deallocate(lpApplicationName);
        std::vector<wchar_t>::_Tidy(&v148);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&lpAttributeList, v49);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
        std::wstring::_Tidy_deallocate(Src);
        std::wstring::_Tidy_deallocate(a5);
        return 2277838902LL;
      }
    }
    v50 = *(_QWORD *)v145;
    if ( ((*(_QWORD *)(*(_QWORD *)v145 + 224LL) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v138 = *(__m128i *)&Microsoft::Diagnostics::RunExeHelperDef::k_cidiagCommandLineNoOutputPath;
      *(_OWORD *)Environment = *(_OWORD *)std::wstring::operator std::wstring_view(v160, v152, v46);
      if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(Environment, &v138) )
      {
        std::wstring::assign(v160, Microsoft::Diagnostics::RunExeHelperDef::k_cidiagCommandLineWithOutputPath);
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(v50 + 168));
      }
    }
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString((LPCWSTR)lpApplicationName);
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v165);
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v160);
    v138 = *(__m128i *)std::wstring::operator std::wstring_view(Src, v152, v51);
    *(_OWORD *)Environment = *(_OWORD *)std::wstring::operator std::wstring_view(qword_180463608, v153, v52);
    v53 = Microsoft::Diagnostics::Utils::String::ReplaceAllImpl<wchar_t>(v160);
    v55 = v53;
    if ( v53 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC0,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
        (const char *)(unsigned int)v53,
        cbSizea);
      std::wstring::_Tidy_deallocate(lpCommandLine);
      std::wstring::_Tidy_deallocate(v160);
      std::wstring::_Tidy_deallocate(v165);
      std::wstring::_Tidy_deallocate(lpApplicationName);
      std::vector<wchar_t>::_Tidy(&v148);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&lpAttributeList, v56);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(a5);
      return v55;
    }
    v138 = *(__m128i *)std::wstring::operator std::wstring_view(v160, v152, v54);
    v57 = Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(a3, JobObjectInformation, &v138);
    std::wstring::operator=(v160, v57);
    std::wstring::_Tidy_deallocate(JobObjectInformation);
    if ( ((*(_QWORD *)(*(_QWORD *)v145 + 224LL) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      std::wstring::wstring(v174, v160);
      Microsoft::Diagnostics::Utils::FileSystem::GetWindowsTemporaryPath(JobObjectInformation);
      Microsoft::Diagnostics::Utils::FileSystem::GetUtcTemporaryPath((LPCWSTR)hJob);
      v138 = *(__m128i *)std::wstring::operator std::wstring_view(hJob, v152, v59);
      *(_OWORD *)Environment = *(_OWORD *)std::wstring::operator std::wstring_view(JobObjectInformation, v153, v60);
      v61 = Microsoft::Diagnostics::Utils::String::ReplaceAllImpl<wchar_t>(v160);
      v62 = v61;
      if ( v61 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCF,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
          (const char *)(unsigned int)v61,
          cbSizea);
        std::wstring::_Tidy_deallocate(hJob);
        std::wstring::_Tidy_deallocate(JobObjectInformation);
        std::wstring::_Tidy_deallocate(v174);
        std::wstring::_Tidy_deallocate(lpCommandLine);
        std::wstring::_Tidy_deallocate(v160);
        std::wstring::_Tidy_deallocate(v165);
        std::wstring::_Tidy_deallocate(lpApplicationName);
        std::vector<wchar_t>::_Tidy(&v148);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&lpAttributeList, v63);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
        std::wstring::_Tidy_deallocate(Src);
        std::wstring::_Tidy_deallocate(a5);
        return v62;
      }
      if ( (unsigned __int8)std::operator!=<wchar_t>(v160, v174) )
      {
        if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4) )
        {
          v66 = v160;
          if ( v161 > 7 )
            v66 = *(WCHAR **)v160;
          Environment[0] = v66;
          v67 = v174;
          if ( v174[3] > 7u )
            v67 = (_QWORD *)v174[0];
          TokenHandle = v67;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
            (unsigned int)&dword_1804543B0,
            (unsigned int)byte_1804035CB,
            v64,
            v65,
            (__int64)&TokenHandle,
            (__int64)Environment);
        }
        Microsoft::Diagnostics::WideStringStream::operator<<((void *)(*(_QWORD *)v145 + 168LL));
      }
      std::wstring::_Tidy_deallocate(hJob);
      std::wstring::_Tidy_deallocate(JobObjectInformation);
      std::wstring::_Tidy_deallocate(v174);
    }
    v138 = *(__m128i *)std::wstring::operator std::wstring_view(lpApplicationName, v152, v58);
    appended = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(lpCommandLine);
    Microsoft::Diagnostics::WideStringStream::operator<<(appended);
    v69 = v165;
    if ( v167 > 7 )
      v69 = *(WCHAR **)v165;
    if ( std::_Traits_find_ch<std::char_traits<wchar_t>>(v69, v166, 0, 32) == -1 )
    {
      v138 = *(__m128i *)std::wstring::operator std::wstring_view(v165, v152, v70);
      v74 = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(lpCommandLine);
    }
    else
    {
      v71 = Microsoft::Diagnostics::WideStringStream::operator<<(lpCommandLine);
      v138 = *(__m128i *)std::wstring::operator std::wstring_view(v165, v152, v71);
      v73 = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(v72);
      v74 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v73);
    }
    v75 = Microsoft::Diagnostics::WideStringStream::operator<<(v74);
    v138 = *(__m128i *)std::wstring::operator std::wstring_view(v160, v153, v75);
    Microsoft::Diagnostics::WideStringStream::AppendString(v76);
    hJob[0] = 0;
    JobObjectW = CreateJobObjectW(0, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      hJob,
      JobObjectW);
    v79 = hJob[0];
    if ( (((unsigned __int64)hJob[0] + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v80 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xF0,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
              v78);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
      std::wstring::_Tidy_deallocate(lpCommandLine);
      std::wstring::_Tidy_deallocate(v160);
      std::wstring::_Tidy_deallocate(v165);
      std::wstring::_Tidy_deallocate(lpApplicationName);
      std::vector<wchar_t>::_Tidy(&v148);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&lpAttributeList, v81);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(a5);
      return v80;
    }
    memset_0(JobObjectInformation, 0, 0x40u);
    JobObjectInformation[0] = 10000LL * *(_QWORD *)(v151 + 160);
    v176 = 2;
    if ( !SetInformationJobObject(v79, JobObjectBasicLimitInformation, JobObjectInformation, 0x40u) )
    {
      v82 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xFD,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
              0);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
      std::wstring::_Tidy_deallocate(lpCommandLine);
      std::wstring::_Tidy_deallocate(v160);
      std::wstring::_Tidy_deallocate(v165);
      std::wstring::_Tidy_deallocate(lpApplicationName);
      std::vector<wchar_t>::_Tidy(&v148);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&lpAttributeList, v83);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(a5);
      return v82;
    }
    v170 = *(_OWORD *)lpCommandLine;
    v171 = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(lpCommandLine[0]) = 0;
    hProcess = 0;
    TokenHandle = 0;
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    v84 = (WCHAR *)&v170;
    if ( _mm_srli_si128(v171, 8).m128i_u64[0] > 7 )
      v84 = (WCHAR *)v170;
    v85 = (const WCHAR *)lpApplicationName;
    if ( lpApplicationName[3] > (LPCWSTR)7 )
      v85 = lpApplicationName[0];
    if ( !CreateProcessAsUserW(
            phNewToken,
            v85,
            v84,
            0,
            0,
            1,
            0x8080404u,
            (LPVOID)DueTime[0].QuadPart,
            0,
            &StartupInfo,
            &ProcessInformation) )
    {
      v86 = GetLastError();
      if ( v86 > 0 )
        v86 = (unsigned __int16)v86 | 0x80070000;
      ExitCode = v86;
      v138.m128i_i64[0] = (__int64)L"RunExeWithArgsAction_FailedToCreateProcess_0";
      v138.m128i_i64[1] = 44;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
        (unsigned int)v180,
        (unsigned int)&v138,
        0x1000000,
        0,
        0,
        0,
        0);
      v138.m128i_i64[0] = (__int64)L"ExeName";
      v138.m128i_i64[1] = 7;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v180, v181, &v138, v151 + 128);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a3 + 56) + 72LL))(*(_QWORD *)(a3 + 56));
      v138.m128i_i64[0] = (__int64)L"ScenarioId";
      v138.m128i_i64[1] = 10;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((int)v180, (int)v181);
      v138.m128i_i64[0] = (__int64)L"ScenarioInstanceId";
      v138.m128i_i64[1] = 18;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((int)v180, (int)v181);
      v138.m128i_i64[0] = (__int64)L"ErrorCode";
      v138.m128i_i64[1] = 9;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<long>((int)v180, (int)v181);
      v138 = 0;
      Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(v145, &v138);
      v87 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v180);
      if ( v87 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x11F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
          (const char *)(unsigned int)v87,
          cbSized);
      v88 = ExitCode;
      if ( (ExitCode & 0x80000000) != 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x121,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
          (const char *)ExitCode,
          cbSized);
      Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v180);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
      std::wstring::_Tidy_deallocate(&v170);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
      std::wstring::_Tidy_deallocate(lpCommandLine);
      std::wstring::_Tidy_deallocate(v160);
      std::wstring::_Tidy_deallocate(v165);
      std::wstring::_Tidy_deallocate(lpApplicationName);
      std::vector<wchar_t>::_Tidy(&v148);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&lpAttributeList, v89);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(a5);
      return v88;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hProcess,
      ProcessInformation.hProcess);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      ProcessInformation.hThread);
    if ( (((unsigned __int64)hProcess + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( (unsigned int)dword_1804543B0 > 2 )
      {
        DueTime[0].QuadPart = (LONGLONG)"RunExecutable";
        Environment[0] = "IsValid(childProcess)";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)v90,
          (unsigned int)&unk_180403590,
          v91,
          v92,
          (__int64)Environment,
          (__int64)DueTime);
      }
      if ( Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager) )
      {
        v93 = Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(v90);
        Microsoft::Diagnostics::TelemetryAssert::Assert(v93);
      }
    }
    if ( (((unsigned __int64)TokenHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( (unsigned int)dword_1804543B0 > 2 )
      {
        DueTime[0].QuadPart = (LONGLONG)"RunExecutable";
        Environment[0] = "IsValid(childProcessMainThread)";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)v90,
          (unsigned int)&dword_1804034F4,
          v91,
          v92,
          (__int64)Environment,
          (__int64)DueTime);
      }
      if ( Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager) )
      {
        v95 = Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(v94);
        Microsoft::Diagnostics::TelemetryAssert::Assert(v95);
      }
    }
    if ( !AssignProcessToJobObject(v79, hProcess) )
    {
      TerminateProcess(ProcessInformation.hProcess, 1u);
      v96 = GetLastError();
      if ( v96 )
      {
        v97 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x133,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
                (const char *)v96,
                cbSizec);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
        std::wstring::_Tidy_deallocate(&v170);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
        std::wstring::_Tidy_deallocate(lpCommandLine);
        std::wstring::_Tidy_deallocate(v160);
        std::wstring::_Tidy_deallocate(v165);
        std::wstring::_Tidy_deallocate(lpApplicationName);
        std::vector<wchar_t>::_Tidy(&v148);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&lpAttributeList, v98);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
        std::wstring::_Tidy_deallocate(Src);
        std::wstring::_Tidy_deallocate(a5);
        return v97;
      }
      else
      {
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
        std::wstring::_Tidy_deallocate(&v170);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
        std::wstring::_Tidy_deallocate(lpCommandLine);
        std::wstring::_Tidy_deallocate(v160);
        std::wstring::_Tidy_deallocate(v165);
        std::wstring::_Tidy_deallocate(lpApplicationName);
        std::vector<wchar_t>::_Tidy(&v148);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&lpAttributeList, v99);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
        std::wstring::_Tidy_deallocate(Src);
        std::wstring::_Tidy_deallocate(a5);
        return 0;
      }
    }
    WaitableTimer = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
    Environment[0] = WaitableTimer;
    if ( (((unsigned __int64)WaitableTimer + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v102 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x139,
               (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
               v101);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(Environment);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
      std::wstring::_Tidy_deallocate(&v170);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
      std::wstring::_Tidy_deallocate(lpCommandLine);
      std::wstring::_Tidy_deallocate(v160);
      std::wstring::_Tidy_deallocate(v165);
      std::wstring::_Tidy_deallocate(lpApplicationName);
      std::vector<wchar_t>::_Tidy(&v148);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&lpAttributeList, v103);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(a5);
      return v102;
    }
    v104 = -10000 * *(_DWORD *)(v151 + 160);
    DueTime[0].HighPart = (-10000LL * (unsigned __int64)*(unsigned int *)(v151 + 160)) >> 32;
    DueTime[0].LowPart = v104;
    if ( !SetWaitableTimer(WaitableTimer, DueTime, 0, 0, 0, 0) )
    {
      v106 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x140,
               (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
               v105);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(Environment);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
      std::wstring::_Tidy_deallocate(&v170);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
      std::wstring::_Tidy_deallocate(lpCommandLine);
      std::wstring::_Tidy_deallocate(v160);
      std::wstring::_Tidy_deallocate(v165);
      std::wstring::_Tidy_deallocate(lpApplicationName);
      std::vector<wchar_t>::_Tidy(&v148);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&lpAttributeList, v107);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(a5);
      return v106;
    }
    ResumeThread(ProcessInformation.hThread);
    v183 = 0;
    Handles[0] = hProcess;
    Handles[1] = WaitableTimer;
    v108 = *(_QWORD *)v145;
    v109 = *(__int64 **)(*(_QWORD *)v145 + 216LL);
    v183 = *v109;
    LODWORD(v109) = (*v109 != 0) + 2;
    v153[0] = &CycleTime;
    v153[1] = &hProcess;
    v154 = 1;
    v110 = WaitForMultipleObjects((DWORD)v109, Handles, 0, 0xFFFFFFFF);
    if ( v110 == 2 )
    {
      if ( !Microsoft::Diagnostics::Utils::Os::WaitOrTimeout(hProcess, 0x1388u) )
      {
        TerminateJobObject(v79, 1u);
        v138.m128i_i64[0] = (__int64)L"RunExeWithArgsAction_ExeTerminated_ServiceShuttingDown_0";
        v138.m128i_i64[1] = 56;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
          (unsigned int)v180,
          (unsigned int)&v138,
          0x1000000,
          0,
          0,
          0,
          0);
        v138.m128i_i64[0] = (__int64)L"ExeName";
        v138.m128i_i64[1] = 7;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v180, v181, &v138, v151 + 128);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a3 + 56) + 72LL))(*(_QWORD *)(a3 + 56));
        v138.m128i_i64[0] = (__int64)L"ScenarioId";
        v138.m128i_i64[1] = 10;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((int)v180, (int)v181);
        v138.m128i_i64[0] = (__int64)L"ScenarioInstanceId";
        v138.m128i_i64[1] = 18;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((int)v180, (int)v181);
        v138 = 0;
        Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(v145, &v138);
        v111 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v180);
        if ( v111 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x16D,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
            (const char *)(unsigned int)v111,
            cbSizef);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x16F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
          (const char *)0x87C5101ALL,
          cbSizef);
        Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v180);
        if ( CycleTime && (char *)hProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          QueryProcessCycleTime(hProcess, CycleTime);
LABEL_117:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(Environment);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
        std::wstring::_Tidy_deallocate(&v170);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
        std::wstring::_Tidy_deallocate(lpCommandLine);
        std::wstring::_Tidy_deallocate(v160);
        std::wstring::_Tidy_deallocate(v165);
        std::wstring::_Tidy_deallocate(lpApplicationName);
        std::vector<wchar_t>::_Tidy(&v148);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&lpAttributeList, v112);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
        std::wstring::_Tidy_deallocate(Src);
        std::wstring::_Tidy_deallocate(a5);
        return 2277838874LL;
      }
    }
    else if ( v110 == 1 )
    {
      TerminateJobObject(v79, 1u);
      v138.m128i_i64[0] = (__int64)L"RunExeWithArgsAction_ExeTerminated_0";
      v138.m128i_i64[1] = 36;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
        (unsigned int)v180,
        (unsigned int)&v138,
        0x1000000,
        0,
        0,
        0,
        0);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a3 + 56) + 72LL))(*(_QWORD *)(a3 + 56));
      v138.m128i_i64[0] = (__int64)L"ScenarioId";
      v138.m128i_i64[1] = 10;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((int)v180, (int)v181);
      v138.m128i_i64[0] = (__int64)L"ScenarioInstanceId";
      v138.m128i_i64[1] = 18;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((int)v180, (int)v181);
      v138.m128i_i64[0] = (__int64)L"ExpandedExeName";
      v138.m128i_i64[1] = 15;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v180, v181, &v138, v165);
      v138.m128i_i64[0] = (__int64)L"MaximumRuntimeMs";
      v138.m128i_i64[1] = 16;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((int)v180, (int)v181);
      v138 = 0;
      Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(v145, &v138);
      v113 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v180);
      if ( v113 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x181,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
          (const char *)(unsigned int)v113,
          cbSizeg);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x183,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
        (const char *)0x87C5101ALL,
        cbSizeg);
      Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v180);
      if ( CycleTime && (char *)hProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        QueryProcessCycleTime(hProcess, CycleTime);
      goto LABEL_117;
    }
    ExitCode = 0;
    if ( GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
    {
      if ( ExitCode == 259 )
      {
        TerminateJobObject(v79, 1u);
        ExitCode = 0;
      }
      if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4) )
      {
        v145[0] = ExitCode;
        v120 = &v170;
        if ( v171.m128i_i64[1] > 7uLL )
          v120 = (__int128 *)v170;
        DueTime[0].QuadPart = (LONGLONG)v120;
        v121 = v165;
        if ( v167 > 7 )
          v121 = *(WCHAR **)v165;
        v138.m128i_i64[0] = (__int64)v121;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v117,
          (unsigned int)&byte_18040352F,
          v118,
          v119,
          (__int64)&v138,
          (__int64)DueTime,
          (__int64)v145);
      }
      v122 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<((void *)(v108 + 168));
      v123 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v122);
      Microsoft::Diagnostics::WideStringStream::operator<<(v123);
      if ( ExitCode )
      {
        if ( !*(_BYTE *)(v151 + 56) )
        {
          v138.m128i_i64[0] = (__int64)L"RunExeWithArgsAction_ProcessReturnedNonZeroExitCode";
          v138.m128i_i64[1] = 51;
          Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
            (unsigned int)v180,
            (unsigned int)&v138,
            0x1000000,
            0,
            0,
            0,
            0);
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a3 + 56) + 72LL))(*(_QWORD *)(a3 + 56));
          v138.m128i_i64[0] = (__int64)L"ScenarioId";
          v138.m128i_i64[1] = 10;
          Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((int)v180, (int)v181);
          v138.m128i_i64[0] = (__int64)L"ScenarioInstanceId";
          v138.m128i_i64[1] = 18;
          Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((int)v180, (int)v181);
          v138.m128i_i64[0] = (__int64)L"ExpandedExeName";
          v138.m128i_i64[1] = 15;
          Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(v180, v181, &v138, v165);
          v138.m128i_i64[0] = (__int64)L"ExitCode";
          v138.m128i_i64[1] = 8;
          Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>(v180, v181, &v138, &ExitCode);
          v138 = 0;
          Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(v145, &v138);
          v125 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v180);
          if ( v125 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1B1,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
              (const char *)(unsigned int)v125,
              cbSizee);
          Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v180);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B5,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
          (const char *)0x87C5101DLL,
          cbSizee);
        if ( CycleTime && (char *)hProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          QueryProcessCycleTime(hProcess, CycleTime);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(Environment);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
        std::wstring::_Tidy_deallocate(&v170);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
        std::wstring::_Tidy_deallocate(lpCommandLine);
        std::wstring::_Tidy_deallocate(v160);
        std::wstring::_Tidy_deallocate(v165);
        std::wstring::_Tidy_deallocate(lpApplicationName);
        std::vector<wchar_t>::_Tidy(&v148);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&lpAttributeList, v126);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
        std::wstring::_Tidy_deallocate(Src);
        std::wstring::_Tidy_deallocate(a5);
        result = 2277838877LL;
      }
      else
      {
        v177 = 0;
        v158[64] = 0;
        v178[0] = off_180381998;
        v178[1] = v108;
        v179 = v178;
        v138.m128i_i64[0] = (__int64)L"*";
        v138.m128i_i64[1] = 1;
        DueTime[0].QuadPart = (LONGLONG)L"*";
        DueTime[1].QuadPart = 1;
        v151 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v152, v124);
        Microsoft::Diagnostics::Utils::FileSystem::DoForEachFileAndDirectoryRecursivelyInPattern(
          (unsigned int)&v151,
          (unsigned int)DueTime,
          (unsigned int)&v138,
          (unsigned int)v178,
          (__int64)v158,
          (__int64)JobObjectInformation);
        if ( v179 )
        {
          v127 = v178;
          LOBYTE(v127) = v179 != v178;
          (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v179 + 32LL))(v179, v127);
        }
        if ( CycleTime && (char *)hProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          QueryProcessCycleTime(hProcess, CycleTime);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(Environment);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
        std::wstring::_Tidy_deallocate(&v170);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
        std::wstring::_Tidy_deallocate(lpCommandLine);
        std::wstring::_Tidy_deallocate(v160);
        std::wstring::_Tidy_deallocate(v165);
        std::wstring::_Tidy_deallocate(lpApplicationName);
        std::vector<wchar_t>::_Tidy(&v148);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
        std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&lpAttributeList, v128);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
        std::wstring::_Tidy_deallocate(Src);
        std::wstring::_Tidy_deallocate(a5);
        result = 0;
      }
    }
    else
    {
      v115 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x189,
               (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
               v114);
      if ( CycleTime && (char *)hProcess - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        QueryProcessCycleTime(hProcess, CycleTime);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(Environment);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
      std::wstring::_Tidy_deallocate(&v170);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hJob);
      std::wstring::_Tidy_deallocate(lpCommandLine);
      std::wstring::_Tidy_deallocate(v160);
      std::wstring::_Tidy_deallocate(v165);
      std::wstring::_Tidy_deallocate(lpApplicationName);
      std::vector<wchar_t>::_Tidy(&v148);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
      std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&lpAttributeList, v116);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(Value);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(a5);
      result = v115;
    }
  }
  catch ( ... )
  {
    v145[0] = wil::details::in1diag3::Return_CaughtException(
                retaddr,
                (void *)0x1C5,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\runexehelper.cpp",
                v31);
    std::wstring::_Tidy_deallocate(v159);
    return v145[0];
  }
  return result;
}

```

## disassembly

```asm
0x18033272c  push    rbx
0x18033272e  push    rsi
0x18033272f  push    rdi
0x180332730  push    r12
0x180332732  push    r13
0x180332734  push    r14
0x180332736  push    r15
0x180332738  sub     rsp, 860h
0x18033273f  mov     rax, cs:__security_cookie
0x180332746  xor     rax, rsp
0x180332749  mov     [rsp+898h+var_40], rax
0x180332751  mov     qword ptr [rsp+898h+var_7F8], r9
0x180332759  mov     r15, r8
0x18033275c  mov     qword ptr [rsp+898h+var_7A8], rcx
0x180332764  mov     rsi, [rsp+898h+arg_20]
0x18033276c  mov     [rsp+898h+var_6A0], rsi
0x180332774  xor     ebx, ebx
0x180332776  cmp     [rdx+8], rbx
0x18033277a  jnz     short loc_1803327AD
0x18033277c  mov     rcx, [rsp+898h]; this
0x180332784  mov     ebx, 8007010Bh
0x180332789  mov     r9d, ebx; char *
0x18033278c  lea     r8, aOnecoreBaseTel_90; "onecore\\base\\telemetry\\utc\\service"...
0x180332793  mov     edx, 1Dh; void *
0x180332798  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033279d  nop
0x18033279e  mov     rcx, rsi
0x1803327a1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1803327a6  mov     eax, ebx
0x1803327a8  jmp     loc_180334FCF
0x1803327ad  lea     rcx, [rsp+898h+Src]
0x1803327b5  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x1803327ba  nop
0x1803327bb  lea     rcx, [rsp+898h+Src]; Src
0x1803327c3  call    ?PrependLongPathUnicodePrefix@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::PrependLongPathUnicodePrefix(std::wstring &)
0x1803327c8  lea     rax, [rsp+898h+Src]
0x1803327d0  cmp     [rsp+898h+var_660], 7
0x1803327d9  cmova   rax, [rsp+898h+Src]
0x1803327e2  mov     rdx, [rsp+898h+var_668]
0x1803327ea  mov     r14d, 1
0x1803327f0  cmp     word ptr [rax+rdx*2-2], 5Ch ; '\'
0x1803327f6  jnz     short loc_180332821
0x1803327f8  sub     rdx, r14
0x1803327fb  mov     [rsp+898h+var_668], rdx
0x180332803  lea     rcx, [rsp+898h+Src]
0x18033280b  cmp     [rsp+898h+var_660], 7
0x180332814  cmova   rcx, [rsp+898h+Src]
0x18033281d  mov     [rcx+rdx*2], bx
0x180332821  mov     [rsp+898h+ExitCode], ebx
0x180332825  lea     rdx, [rsp+898h+ExitCode]
0x18033282a  lea     rcx, [rsp+898h+Value]
0x180332832  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x180332837  nop
0x180332838  mov     [rsp+898h+Size], rbx
0x180332840  lea     r9, [rsp+898h+Size]; lpSize
0x180332848  xor     r8d, r8d; dwFlags
0x18033284b  mov     edx, r14d; dwAttributeCount
0x18033284e  xor     ecx, ecx; lpAttributeList
0x180332850  call    cs:__imp_InitializeProcThreadAttributeList
0x180332856  mov     rdx, [rsp+898h+Size]
0x18033285e  mov     r12d, 2
0x180332864  test    rdx, rdx
0x180332867  jnz     loc_1803328FD
0x18033286d  mov     eax, cs:dword_1804543B0
0x180332873  cmp     eax, r12d
0x180332876  jbe     short loc_1803328BE
0x180332878  lea     r13, aRunexecutable; "RunExecutable"
0x18033287f  mov     qword ptr [rsp+898h+DueTime], r13
0x180332887  lea     rbx, aAttributessize; "attributesSize > 0"
0x18033288e  mov     [rsp+898h+Environment], rbx
0x180332896  lea     rax, [rsp+898h+DueTime]
0x18033289e  mov     [rsp+898h+lpPreviousValue], rax
0x1803328a3  lea     rax, [rsp+898h+Environment]
0x1803328ab  mov     [rsp+898h+cbSize], rax
0x1803328b0  lea     rdx, word_180403672
0x1803328b7  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1803328bc  jmp     short loc_1803328CC
0x1803328be  lea     r13, aRunexecutable; "RunExecutable"
0x1803328c5  lea     rbx, aAttributessize; "attributesSize > 0"
0x1803328cc  lea     rdi, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; Microsoft::Diagnostics::LifetimeManager gs_lifetimeManager
0x1803328d3  mov     rcx, rdi; this
0x1803328d6  call    ?IsTelemetryAssertReady@LifetimeManager@Diagnostics@Microsoft@@QEAA_NXZ; Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady(void)
0x1803328db  test    al, al
0x1803328dd  jz      short loc_1803328EC
0x1803328df  call    ?GetTelemetryAssert@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVTelemetryAssert@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(void)
0x1803328e4  mov     rcx, rax; this
0x1803328e7  call    ?Assert@TelemetryAssert@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::TelemetryAssert::Assert(void)
0x1803328ec  mov     rdx, [rsp+898h+Size]
0x1803328f4  test    rdx, rdx
0x1803328f7  jnz     short loc_180332912
0x1803328f9  xor     eax, eax
0x1803328fb  jmp     short loc_180332915
0x1803328fd  lea     r13, aRunexecutable; "RunExecutable"
0x180332904  lea     rbx, aAttributessize; "attributesSize > 0"
0x18033290b  lea     rdi, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; Microsoft::Diagnostics::LifetimeManager gs_lifetimeManager
0x180332912  mov     eax, r14d
0x180332915  mov     rcx, [rsp+898h]; this
0x18033291d  test    eax, eax
0x18033291f  jz      loc_180334FF2
0x180332925  lea     rcx, [rsp+898h+lpAttributeList]
0x18033292d  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x180332932  nop
0x180332933  lea     r9, [rsp+898h+Size]; lpSize
0x18033293b  xor     r8d, r8d; dwFlags
0x18033293e  mov     edx, r14d; dwAttributeCount
0x180332941  mov     rcx, [rsp+898h+lpAttributeList]; lpAttributeList
0x180332949  call    cs:__imp_InitializeProcThreadAttributeList
0x18033294f  cmp     [rsp+898h+Size], 0
0x180332958  ja      short loc_1803329C6
0x18033295a  mov     eax, cs:dword_1804543B0
0x180332960  cmp     eax, r12d
0x180332963  jbe     short loc_18033299B
0x180332965  mov     qword ptr [rsp+898h+DueTime], r13
0x18033296d  mov     [rsp+898h+Environment], rbx
0x180332975  lea     rax, [rsp+898h+DueTime]
0x18033297d  mov     [rsp+898h+lpPreviousValue], rax
0x180332982  lea     rax, [rsp+898h+Environment]
0x18033298a  mov     [rsp+898h+cbSize], rax
0x18033298f  lea     rdx, byte_180403637
0x180332996  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18033299b  mov     rcx, rdi; this
0x18033299e  call    ?IsTelemetryAssertReady@LifetimeManager@Diagnostics@Microsoft@@QEAA_NXZ; Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady(void)
0x1803329a3  xor     r13d, r13d
0x1803329a6  test    al, al
0x1803329a8  jz      short loc_1803329B7
0x1803329aa  call    ?GetTelemetryAssert@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVTelemetryAssert@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(void)
0x1803329af  mov     rcx, rax; this
0x1803329b2  call    ?Assert@TelemetryAssert@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::TelemetryAssert::Assert(void)
0x1803329b7  cmp     [rsp+898h+Size], r13
0x1803329bf  ja      short loc_1803329C9
0x1803329c1  mov     eax, r13d
0x1803329c4  jmp     short loc_1803329CC
0x1803329c6  xor     r13d, r13d
0x1803329c9  mov     eax, r14d
0x1803329cc  mov     rcx, [rsp+898h]; this
0x1803329d4  test    eax, eax
0x1803329d6  jz      loc_180335002
0x1803329dc  xor     edx, edx
0x1803329de  lea     rcx, [rsp+898h+Value]
0x1803329e6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1803329eb  mov     [rsp+898h+lpReturnSize], r13; lpReturnSize
0x1803329f0  mov     [rsp+898h+lpPreviousValue], r13; lpPreviousValue
0x1803329f5  mov     [rsp+898h+cbSize], 8; int
0x1803329fe  lea     r9, [rsp+898h+Value]; lpValue
0x180332a06  xor     edx, edx; dwFlags
0x180332a08  mov     r8d, 20002h; Attribute
0x180332a0e  mov     rcx, [rsp+898h+lpAttributeList]; lpAttributeList
0x180332a16  call    cs:__imp_UpdateProcThreadAttribute
0x180332a1c  mov     ebx, 70h ; 'p'
0x180332a21  mov     r8d, ebx; Size
0x180332a24  xor     edx, edx; Val
0x180332a26  lea     rcx, [rsp+898h+StartupInfo]; void *
0x180332a2e  call    memset_0
0x180332a33  mov     [rsp+898h+StartupInfo.cb], ebx
0x180332a3a  mov     [rsp+898h+StartupInfo.dwFlags], 100h
0x180332a45  mov     rax, [rsp+898h+lpAttributeList]
0x180332a4d  mov     [rsp+898h+var_6F0], rax
0x180332a55  mov     [rsp+898h+phNewToken], r13
0x180332a5d  xorps   xmm0, xmm0
0x180332a60  movdqu  [rsp+898h+var_7C8], xmm0
0x180332a69  mov     [rsp+898h+var_7B8], r13
0x180332a71  mov     bl, r13b
0x180332a74  mov     rcx, qword ptr [rsp+898h+var_7A8]
0x180332a7c  sub     rcx, 0FFFFFFFFFFFFFF80h
0x180332a80  movups  xmm0, xmmword ptr cs:?k_hcsdiagPath@RunExeHelperDef@Diagnostics@Microsoft@@2V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::RunExeHelperDef::k_hcsdiagPath
0x180332a87  movdqu  [rsp+898h+var_838], xmm0
0x180332a8d  lea     rdx, [rsp+898h+hJob]
0x180332a95  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180332a9a  movups  xmm0, xmmword ptr [rax]
0x180332a9d  movdqu  xmmword ptr [rsp+898h+DueTime], xmm0
0x180332aa6  lea     rdx, [rsp+898h+var_838]
0x180332aab  lea     rcx, [rsp+898h+DueTime]
0x180332ab3  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x180332ab8  mov     r13d, 4
0x180332abe  test    eax, eax
0x180332ac0  jnz     short loc_180332AF6
0x180332ac2  mov     eax, cs:dword_1804543B0
0x180332ac8  cmp     eax, r13d
0x180332acb  jbe     short loc_180332AF3
0x180332acd  mov     edx, r13d
0x180332ad0  lea     rcx, dword_1804543B0
0x180332ad7  call    _tlgKeywordOn
0x180332adc  test    al, al
0x180332ade  jz      short loc_180332AF3
0x180332ae0  lea     rdx, byte_1804036AD
0x180332ae7  lea     rcx, dword_1804543B0
0x180332aee  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180332af3  mov     bl, r14b
0x180332af6  mov     [rsp+898h+TokenHandle], 0
0x180332aff  test    bl, bl
0x180332b01  jnz     loc_180332C2A
0x180332b07  xor     edx, edx
0x180332b09  lea     rcx, [rsp+898h+TokenHandle]
0x180332b0e  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180332b13  call    cs:__imp_GetCurrentThread
0x180332b19  lea     r9, [rsp+898h+TokenHandle]; TokenHandle
0x180332b1e  mov     r8d, r14d; OpenAsSelf
0x180332b21  mov     edx, 0F01FFh; DesiredAccess
0x180332b26  mov     rcx, rax; ThreadHandle
0x180332b29  call    cs:__imp_OpenThreadToken
0x180332b2f  test    eax, eax
0x180332b31  jnz     loc_180332C2A
0x180332b37  call    cs:__imp_GetLastError
0x180332b3d  cmp     eax, 3F0h
0x180332b42  jz      loc_180332C2A
0x180332b48  test    eax, eax
0x180332b4a  jz      short loc_180332BCA
0x180332b4c  mov     rcx, [rsp+898h]; this
0x180332b54  mov     r9d, eax; char *
0x180332b57  lea     r8, aOnecoreBaseTel_90; "onecore\\base\\telemetry\\utc\\service"...
0x180332b5e  mov     edx, 67h ; 'g'; void *
0x180332b63  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180332b68  mov     ebx, eax
0x180332b6a  lea     rcx, [rsp+898h+TokenHandle]
0x180332b6f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180332b74  nop
0x180332b75  lea     rcx, [rsp+898h+var_7C8]
0x180332b7d  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x180332b82  nop
0x180332b83  lea     rcx, [rsp+898h+phNewToken]
0x180332b8b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180332b90  nop
0x180332b91  lea     rcx, [rsp+898h+lpAttributeList]
0x180332b99  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x180332b9e  nop
0x180332b9f  lea     rcx, [rsp+898h+Value]
0x180332ba7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180332bac  nop
0x180332bad  lea     rcx, [rsp+898h+Src]
0x180332bb5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180332bba  nop
0x180332bbb  mov     rcx, rsi
0x180332bbe  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180332bc3  mov     eax, ebx
0x180332bc5  jmp     loc_180334FCF
0x180332bca  lea     rcx, [rsp+898h+TokenHandle]
0x180332bcf  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180332bd4  nop
0x180332bd5  lea     rcx, [rsp+898h+var_7C8]
0x180332bdd  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x180332be2  nop
0x180332be3  lea     rcx, [rsp+898h+phNewToken]
0x180332beb  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180332bf0  nop
0x180332bf1  lea     rcx, [rsp+898h+lpAttributeList]
0x180332bf9  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x180332bfe  nop
0x180332bff  lea     rcx, [rsp+898h+Value]
0x180332c07  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180332c0c  nop
0x180332c0d  lea     rcx, [rsp+898h+Src]
0x180332c15  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180332c1a  nop
0x180332c1b  mov     rcx, rsi
0x180332c1e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180332c23  xor     eax, eax
0x180332c25  jmp     loc_180334FCF
0x180332c2a  mov     [rsp+898h+Environment], 0
0x180332c36  mov     rax, [rsp+898h+TokenHandle]
0x180332c3b  dec     rax
0x180332c3e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180332c42  ja      loc_180332CFC
0x180332c48  xor     edx, edx
0x180332c4a  lea     rcx, [rsp+898h+phNewToken]
0x180332c52  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180332c57  lea     rax, [rsp+898h+phNewToken]
0x180332c5f  mov     [rsp+898h+lpPreviousValue], rax; phNewToken
0x180332c64  mov     dword ptr [rsp+898h+cbSize], r14d; TokenType
0x180332c69  mov     r9d, r12d; ImpersonationLevel
0x180332c6c  xor     r8d, r8d; lpTokenAttributes
0x180332c6f  mov     edx, 0F01FFh; dwDesiredAccess
0x180332c74  mov     rcx, [rsp+898h+TokenHandle]; hExistingToken
0x180332c79  call    cs:__imp_DuplicateTokenEx
0x180332c7f  test    eax, eax
0x180332c81  jnz     short loc_180332CFC
0x180332c83  mov     rcx, [rsp+898h]; this
0x180332c8b  lea     r8, aOnecoreBaseTel_90; "onecore\\base\\telemetry\\utc\\service"...
0x180332c92  lea     edx, [rax+79h]; void *
0x180332c95  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180332c9a  mov     ebx, eax
0x180332c9c  lea     rcx, [rsp+898h+TokenHandle]
0x180332ca1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180332ca6  nop
0x180332ca7  lea     rcx, [rsp+898h+var_7C8]
0x180332caf  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x180332cb4  nop
0x180332cb5  lea     rcx, [rsp+898h+phNewToken]
0x180332cbd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180332cc2  nop
0x180332cc3  lea     rcx, [rsp+898h+lpAttributeList]
0x180332ccb  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x180332cd0  nop
0x180332cd1  lea     rcx, [rsp+898h+Value]
0x180332cd9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180332cde  nop
0x180332cdf  lea     rcx, [rsp+898h+Src]
0x180332ce7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180332cec  nop
0x180332ced  mov     rcx, rsi
0x180332cf0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
  ... truncated ...
```
