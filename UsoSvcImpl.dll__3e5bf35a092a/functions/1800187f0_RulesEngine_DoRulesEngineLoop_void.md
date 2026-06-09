# RulesEngine::DoRulesEngineLoop(void)

- ea: `0x1800187f0`
- end: `0x18001a37a`
- name: `?DoRulesEngineLoop@RulesEngine@@AEAAXXZ`
- size: `7050`
- prototype: `void __fastcall(RulesEngine *__hidden this)`
- caller_count: `1`
- callee_count: `46`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800141a0`

## callees

- `0x180008ea8`
- `0x18000efe8`
- `0x180010890`
- `0x1800108b4`
- `0x1800112d0`
- `0x1800114bc`
- `0x180011680`
- `0x180011948`
- `0x1800119a8`
- `0x180013084`
- `0x1800141e4`
- `0x180014650`
- `0x1800165b8`
- `0x180016670`
- `0x180018068`
- `0x1800187f0`
- `0x18001ae7c`
- `0x18001afb8`
- `0x18001b064`
- `0x18001b3d4`
- `0x18001bcf0`
- `0x18001c134`
- `0x18001c2b0`
- `0x18001c3d4`
- `0x18001c974`
- `0x18001cbdc`
- `0x18001cf40`
- `0x18001dff4`
- `0x18001e31c`
- `0x18002deb8`
- `0x18002dedc`
- `0x18002dfe4`
- `0x18002e168`
- `0x18002e27c`
- `0x18003639c`
- `0x1800420e0`
- `0x180042e00`
- `0x180042e48`
- `0x18006ea28`
- `0x18006f928`
- `0x180070188`
- `0x1800dd930`
- `0x1800dddf4`
- `0x1800de12c`
- `0x1800e4630`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180019f42`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180019f42`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800194e7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180019961`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800194e7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180019961`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180018a49`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180018b06`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180018c75`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180018edd`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180018a49`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180018b06`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180018c75`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180018edd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019509`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800199a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019509`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800199a8`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800196c0`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800196c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ef2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018fa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019fcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ef2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018fa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019fcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a000`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018fb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019fe8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a01d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018fb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019fe8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a01d`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x180018faf`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x18001a0fc`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x180018faf`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x18001a0fc`
- `IPHLPAPI!NotifyNetworkConnectivityHintChange` at `0x180018fdd`
- `IPHLPAPI!NotifyNetworkConnectivityHintChange` at `0x180018fdd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180018a00`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180018a00`
- `api-ms-win-power-base-l1-1-0!PowerUnregisterSuspendResumeNotification` at `0x18001a192`
- `api-ms-win-power-base-l1-1-0!PowerUnregisterSuspendResumeNotification` at `0x18001a192`
- `api-ms-win-power-base-l1-1-0!PowerRegisterSuspendResumeNotification` at `0x180018e75`
- `api-ms-win-power-base-l1-1-0!PowerRegisterSuspendResumeNotification` at `0x180018e75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a1fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a1fe`

## string_xrefs

- `0x18001a300`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x180018939`: `DelayedConfiguration`
- `0x180019c0e`: `FirstLogonAfterUpdateFlag`

## pseudocode

```c
// Hidden C++ exception states: #wind=43
void __fastcall RulesEngine::DoRulesEngineLoop(RulesEngine *this)
{
  void (__fastcall ***v1)(_QWORD, __int64); // r15
  UsoScheduler *v2; // r12
  __int64 v3; // rdx
  const char *v4; // r9
  HANDLE v5; // rbx
  const char *v6; // r9
  char v7; // al
  __int64 v8; // rax
  HANDLE Event; // rbx
  __int64 v10; // r8
  const char *v11; // r9
  char v12; // al
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  int wnf_subscription; // eax
  void (__fastcall ***v17)(_QWORD, __int64); // rcx
  HANDLE v18; // rbx
  const char *v19; // r9
  char v20; // al
  void (__fastcall ***v21)(_QWORD, __int64); // rsi
  __int64 v22; // r14
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rsi
  volatile signed __int32 *v27; // rcx
  int v28; // eax
  void (__fastcall ***v29)(_QWORD, __int64); // rcx
  unsigned int v30; // eax
  void (__fastcall ***v31)(_QWORD, __int64); // r14
  const char *v32; // r9
  char v33; // al
  __int128 v34; // kr10_16
  volatile signed __int32 *v35; // rcx
  HANDLE v36; // rdi
  DWORD LastError; // ebx
  unsigned int v38; // eax
  __int64 v39; // rax
  __int64 *System; // rax
  __int64 v41; // rax
  __int64 v42; // r9
  __int64 (__fastcall *v43)(__int64, __int128 *, __int128 *); // r10
  __int64 v44; // rax
  __int64 v45; // rdx
  __int64 v46; // r8
  volatile signed __int32 *v47; // rdi
  volatile signed __int32 *v48; // rdi
  __int64 *v49; // rax
  _QWORD *v50; // rax
  __int64 *v51; // rax
  __int64 *traits_2_unsigned_short; // rax
  const char *v53; // r9
  int v54; // r11d
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  unsigned __int64 v58; // rcx
  volatile signed __int32 *v59; // rdi
  volatile signed __int32 *v60; // rdi
  volatile signed __int32 *v61; // rdi
  volatile signed __int32 *v62; // rdi
  __m128i v63; // xmm6
  __int64 v64; // rdx
  signed __int32 v65; // eax
  signed __int32 v66; // ett
  BOOL v67; // eax
  const char *v68; // r9
  bool v69; // zf
  volatile signed __int32 *v70; // xmm6_8
  void (__fastcall ***v71)(_QWORD, __int64); // rdi
  __int64 v72; // rax
  RulesEngine *v73; // rdx
  unsigned __int64 v74; // rcx
  RulesEngine *v75; // rcx
  RulesEngine *v76; // rax
  _QWORD *UpdateManager; // rax
  int v78; // eax
  const char *v79; // r9
  RulesEngine *v80; // rax
  RulesEngine *v81; // rax
  __int64 *v82; // rax
  __int64 v83; // rax
  __int64 v84; // r13
  int (__fastcall *v85)(__int64, wil::details::in1diag3 **, int *); // rbx
  __int64 v86; // rbx
  unsigned int v87; // r8d
  const char *v88; // r9
  __int64 v89; // rcx
  RulesEngine *v90; // rax
  __int64 *v91; // rax
  __int64 v92; // rax
  __int64 v93; // r9
  void (__fastcall *v94)(__int64, __int128 *, wil::details::in1diag3 **); // r10
  __int64 v95; // rax
  __int64 v96; // rdx
  __int64 *v97; // rax
  __int128 *v98; // r8
  __int64 v99; // rcx
  __int64 v100; // rdx
  __int64 *v101; // rax
  __int128 *v102; // r8
  __int64 v103; // rcx
  __int64 v104; // rdx
  int v105; // eax
  __int64 *v106; // rax
  __int64 v107; // rax
  __int64 v108; // r10
  void (__fastcall *v109)(__int64, __int128 *, unsigned __int128 *, __int128 *); // r11
  __int64 v110; // rax
  __int64 v111; // rax
  __int64 v112; // rdx
  __int64 *v113; // rax
  __int64 v114; // rax
  __int64 v115; // r10
  void (__fastcall *v116)(__int64, __int128 *, unsigned __int128 *, __int128 *); // r11
  __int64 v117; // rax
  __int64 v118; // rax
  __int64 v119; // rdx
  void *v120; // rcx
  unsigned int v121; // r8d
  const char *v122; // r9
  signed int v123; // eax
  unsigned int v124; // ecx
  void (__fastcall ***v125)(_QWORD, __int64); // r14
  DWORD v126; // ebx
  void (__fastcall ***v127)(_QWORD, __int64); // r14
  DWORD v128; // ebx
  volatile signed __int32 *v129; // r14
  volatile signed __int32 *v130; // rdi
  volatile signed __int32 *v131; // rdi
  volatile signed __int32 *v132; // rdi
  volatile signed __int32 *v133; // rdi
  volatile signed __int32 *v134; // rdi
  unsigned int bAlertable; // [rsp+20h] [rbp-4A8h]
  char v136; // [rsp+30h] [rbp-498h]
  char v137; // [rsp+31h] [rbp-497h]
  char v138; // [rsp+32h] [rbp-496h]
  int v139; // [rsp+34h] [rbp-494h] BYREF
  void (__fastcall ***v140)(_QWORD, __int64); // [rsp+38h] [rbp-490h] BYREF
  __int64 v141; // [rsp+40h] [rbp-488h] BYREF
  unsigned int v142; // [rsp+48h] [rbp-480h] BYREF
  RulesEngine *v143; // [rsp+50h] [rbp-478h]
  void (__fastcall ***v144)(_QWORD, __int64); // [rsp+58h] [rbp-470h] BYREF
  __int128 v145; // [rsp+60h] [rbp-468h] BYREF
  wil::details::in1diag3 *v146[2]; // [rsp+70h] [rbp-458h] BYREF
  char *v147; // [rsp+80h] [rbp-448h]
  __int128 v148; // [rsp+88h] [rbp-440h] BYREF
  void (__fastcall ***v149)(_QWORD, __int64); // [rsp+98h] [rbp-430h] BYREF
  void (__fastcall ***v150)(_QWORD, __int64); // [rsp+A0h] [rbp-428h] BYREF
  __int128 v151; // [rsp+A8h] [rbp-420h] BYREF
  __int128 v152; // [rsp+C0h] [rbp-408h] BYREF
  __int128 v153; // [rsp+D0h] [rbp-3F8h] BYREF
  __int128 v154; // [rsp+E0h] [rbp-3E8h] BYREF
  __int128 v155; // [rsp+F0h] [rbp-3D8h] BYREF
  __int128 v156; // [rsp+100h] [rbp-3C8h] BYREF
  unsigned __int128 v157; // [rsp+110h] [rbp-3B8h] BYREF
  __int128 v158; // [rsp+120h] [rbp-3A8h] BYREF
  unsigned __int128 v159; // [rsp+130h] [rbp-398h] BYREF
  __int128 v160; // [rsp+140h] [rbp-388h] BYREF
  __int128 v161; // [rsp+150h] [rbp-378h] BYREF
  __int128 v162; // [rsp+160h] [rbp-368h] BYREF
  void (__fastcall ***v163)(_QWORD, __int64); // [rsp+170h] [rbp-358h] BYREF
  __int128 v164; // [rsp+178h] [rbp-350h] BYREF
  unsigned __int128 v165; // [rsp+188h] [rbp-340h] BYREF
  __int128 v166; // [rsp+1A0h] [rbp-328h] BYREF
  __int64 v167; // [rsp+1B0h] [rbp-318h] BYREF
  char v168[8]; // [rsp+1B8h] [rbp-310h] BYREF
  __int64 (__fastcall **v169)(); // [rsp+1C0h] [rbp-308h] BYREF
  __int64 v170; // [rsp+1C8h] [rbp-300h]
  __int64 v171; // [rsp+1D0h] [rbp-2F8h]
  bool *v172; // [rsp+1D8h] [rbp-2F0h]
  __int64 (__fastcall ***v173)(); // [rsp+228h] [rbp-2A0h]
  UsoScheduler *v174; // [rsp+230h] [rbp-298h]
  void (__fastcall ***v175)(_QWORD, __int64); // [rsp+238h] [rbp-290h]
  RulesEngine *v176; // [rsp+240h] [rbp-288h]
  __int64 v177; // [rsp+248h] [rbp-280h] BYREF
  __int128 v178; // [rsp+250h] [rbp-278h] BYREF
  __int64 v179; // [rsp+260h] [rbp-268h]
  __int64 v180; // [rsp+268h] [rbp-260h]
  __int64 v181[2]; // [rsp+270h] [rbp-258h] BYREF
  __int128 v182; // [rsp+280h] [rbp-248h]
  unsigned __int128 v183; // [rsp+290h] [rbp-238h]
  __int128 v184; // [rsp+2A0h] [rbp-228h]
  __int128 v185; // [rsp+2B0h] [rbp-218h]
  __int128 v186; // [rsp+2C0h] [rbp-208h]
  unsigned __int128 v187; // [rsp+2D0h] [rbp-1F8h]
  __int128 v188; // [rsp+2E0h] [rbp-1E8h]
  __int128 v189; // [rsp+2F0h] [rbp-1D8h]
  __int128 v190; // [rsp+300h] [rbp-1C8h] BYREF
  __int64 v191[2]; // [rsp+310h] [rbp-1B8h] BYREF
  _BYTE v192[16]; // [rsp+320h] [rbp-1A8h] BYREF
  __int64 v193[2]; // [rsp+330h] [rbp-198h] BYREF
  _BYTE v194[16]; // [rsp+340h] [rbp-188h] BYREF
  __int64 v195[2]; // [rsp+350h] [rbp-178h] BYREF
  _BYTE v196[16]; // [rsp+360h] [rbp-168h] BYREF
  __int64 v197[2]; // [rsp+370h] [rbp-158h] BYREF
  _BYTE v198[16]; // [rsp+380h] [rbp-148h] BYREF
  __int64 v199[2]; // [rsp+390h] [rbp-138h] BYREF
  _BYTE v200[16]; // [rsp+3A0h] [rbp-128h] BYREF
  _BYTE v201[16]; // [rsp+3B0h] [rbp-118h] BYREF
  unsigned int v202[2]; // [rsp+3C0h] [rbp-108h] BYREF
  unsigned int *v203; // [rsp+3F8h] [rbp-D0h]
  char v204[16]; // [rsp+400h] [rbp-C8h] BYREF
  char v205[16]; // [rsp+410h] [rbp-B8h] BYREF
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+420h] [rbp-A8h] BYREF
  _QWORD v207[2]; // [rsp+438h] [rbp-90h] BYREF
  bool v208; // [rsp+448h] [rbp-80h] BYREF
  __int128 lpHandles; // [rsp+450h] [rbp-78h] BYREF
  __int64 v210; // [rsp+460h] [rbp-68h]
  HANDLE NotificationHandle; // [rsp+468h] [rbp-60h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+470h] [rbp-58h] BYREF
  __int64 v213; // [rsp+478h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+0h]

  v143 = this;
  v176 = this;
  v139 = 0;
  LODWORD(v147) = 0;
  lpHandles = 0;
  v210 = 0;
  *(_QWORD *)&v148 = *(_QWORD *)this;
  *((_QWORD *)&v148 + 1) = *(_QWORD *)(s_runOperationInfo + 80);
  *(_QWORD *)&v152 = &v148;
  *((_QWORD *)&v152 + 1) = &v149;
  v154 = v152;
  std::vector<void *>::vector<void *>(&lpHandles, &v154);
  v136 = 1;
  v156 = 0;
  v1 = 0;
  v149 = 0;
  v146[0] = (wil::details::in1diag3 *)operator new(0x128u);
  memset(v146[0], 0, 0x128u);
  *(_QWORD *)v202 = off_1800F5BE0;
  v203 = v202;
  v141 = 600;
  v178 = 0;
  v179 = 0;
  v180 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v178);
  v139 = 48;
  v2 = UsoScheduler::UsoScheduler(v146[0], (__int64)&v178, &v141, 0, (__int64)v202);
  v174 = v2;
  std::wstring::~wstring(&v178);
  LODWORD(v145) = 64;
  if ( v203 )
  {
    LOBYTE(v3) = v203 != v202;
    (*(void (__fastcall **)(unsigned int *, __int64))(*(_QWORD *)v203 + 32LL))(v203, v3);
  }
  v148 = 0;
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GA;;;AU)(A;;GA;;;SY)", 1u, &SecurityDescriptor, 0) )
  {
    EventAttributes.nLength = 24;
    EventAttributes.lpSecurityDescriptor = SecurityDescriptor;
    EventAttributes.bInheritHandle = 0;
    v5 = CreateEventExW(&EventAttributes, L"Global\\USORebootCancel", 1u, 0x1F0003u);
    if ( v5 )
    {
      GetLastError();
      _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
        &v148,
        v5);
      v7 = 0;
    }
    else
    {
      v7 = 1;
    }
    if ( v7 )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x564,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
        v6);
    if ( (_QWORD)v148 )
    {
      v8 = *(_QWORD *)v148;
      if ( *(_QWORD *)v148 )
      {
        v141 = *(_QWORD *)v148;
        if ( *((_QWORD *)&lpHandles + 1) == v210 )
        {
          std::vector<void *>::_Emplace_reallocate<void *>(&lpHandles, *((_QWORD *)&lpHandles + 1), &v141);
        }
        else
        {
          **((_QWORD **)&lpHandles + 1) = v8;
          *((_QWORD *)&lpHandles + 1) += 8LL;
        }
      }
    }
  }
  else
  {
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x56E,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
      v4);
  }
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
      &v156,
      Event);
    v12 = 0;
  }
  else
  {
    v12 = 1;
  }
  if ( v12 )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x571,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
      v11);
  v13 = v156;
  if ( (_QWORD)v156 )
  {
    v14 = *(_QWORD *)v156;
    if ( *(_QWORD *)v156 )
    {
      v141 = *(_QWORD *)v156;
      if ( *((_QWORD *)&lpHandles + 1) == v210 )
      {
        std::vector<void *>::_Emplace_reallocate<void *>(&lpHandles, *((_QWORD *)&lpHandles + 1), &v141);
        v13 = v156;
      }
      else
      {
        **((_QWORD **)&lpHandles + 1) = v14;
        *((_QWORD *)&lpHandles + 1) += 8LL;
      }
      v15 = *((_QWORD *)&v156 + 1);
      if ( *((_QWORD *)&v156 + 1) )
        _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v156 + 1) + 8LL), 1u);
      v169 = (__int64 (__fastcall **)())&off_1800F5ED8;
      v170 = v13;
      v171 = v15;
      v173 = &v169;
      v140 = 0;
      wnf_subscription = wil::details::make_wnf_subscription_state<_GUID>(v13, v168, v10, &v140);
      v17 = 0;
      if ( wnf_subscription >= 0 )
        v17 = v140;
      v140 = v17;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
        &v149,
        &v140);
      if ( v140 )
        (**v140)(v140, 1);
      if ( v173 )
        ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v173)[3])(v173);
      v1 = v149;
    }
  }
  v152 = 0;
  v18 = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( v18 )
  {
    GetLastError();
    _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
      &v152,
      v18);
    v20 = 0;
  }
  else
  {
    v20 = 1;
  }
  if ( v20 )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x57C,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
      v19);
  v21 = 0;
  v150 = 0;
  v208 = 0;
  v22 = v152;
  if ( (_QWORD)v152 )
  {
    v23 = *(_QWORD *)v152;
    if ( *(_QWORD *)v152 )
    {
      v141 = *(_QWORD *)v152;
      if ( *((_QWORD *)&lpHandles + 1) == v210 )
      {
        std::vector<void *>::_Emplace_reallocate<void *>(&lpHandles, *((_QWORD *)&lpHandles + 1), &v141);
      }
      else
      {
        **((_QWORD **)&lpHandles + 1) = v23;
        *((_QWORD *)&lpHandles + 1) += 8LL;
      }
      v24 = 0;
      v25 = 0;
      v26 = *((_QWORD *)&v152 + 1);
      if ( *((_QWORD *)&v152 + 1) )
      {
        v24 = v22;
        v25 = *((_QWORD *)&v152 + 1);
        _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v152 + 1) + 12LL), 1u);
      }
      s_weakUserPresentEvent = v24;
      v27 = (volatile signed __int32 *)qword_180150718;
      qword_180150718 = v25;
      if ( v27 && _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
      if ( v26 )
        _InterlockedAdd((volatile signed __int32 *)(v26 + 8), 1u);
      v169 = (__int64 (__fastcall **)())&off_1800F5EB0;
      v170 = v22;
      v171 = v26;
      v172 = &v208;
      v173 = &v169;
      v140 = 0;
      v28 = wil::details::make_wnf_subscription_state<_SEB_EVENT_HEADER>(
              &WNF_SEB_USER_PRESENT,
              v168,
              0xFFFFFFFFLL,
              &v140);
      v29 = 0;
      if ( v28 >= 0 )
        v29 = v140;
      v140 = v29;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
        &v150,
        &v140);
      if ( v140 )
        (**v140)(v140, 1);
      if ( v173 )
        ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v173)[3])(v173);
      v21 = v150;
    }
  }
  v207[0] = RulesEngine::SuspendNotificationCallback;
  v207[1] = 0;
  v213 = 0;
  v30 = PowerRegisterSuspendResumeNotification(2, v207, &v213);
  if ( v30 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x59A,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
      (const char *)v30,
      bAlertable);
  v190 = 0;
  anonymous_namespace_::InitializePowerAndBattery(&v190);
  v31 = 0;
  v140 = 0;
  v155 = 0;
  NotificationHandle = 0;
  v141 = (__int64)CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( v141 )
  {
    GetLastError();
    _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
      &v155,
      v141);
    v33 = 0;
  }
  else
  {
    v33 = 1;
  }
  if ( v33 )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x5A4,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
      v32);
  if ( (_QWORD)v155 && *(_QWORD *)v155 )
  {
    v34 = 0u;
    if ( *((_QWORD *)&v155 + 1) )
    {
      v34 = v155;
      _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v155 + 1) + 12LL), 1u);
    }
    v35 = (volatile signed __int32 *)*((_QWORD *)&xmmword_180150738 + 1);
    xmmword_180150738 = v34;
    if ( v35 && _InterlockedExchangeAdd(v35 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
    v36 = NotificationHandle;
    if ( (char *)NotificationHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      CancelMibChangeNotify2(v36);
      SetLastError(LastError);
    }
    NotificationHandle = 0;
    v38 = NotifyNetworkConnectivityHintChange(
            anonymous_namespace_::OnNetworkConnectivityChange,
            0,
            0,
            &NotificationHandle);
    if ( v38 )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x5A8,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
        (const char *)v38,
        bAlertable);
    }
    else
    {
      v39 = *(_QWORD *)v155;
      v141 = *(_QWORD *)v155;
      if ( *((_QWORD *)&lpHandles + 1) == v210 )
      {
        std::vector<void *>::_Emplace_reallocate<void *>(&lpHandles, *((_QWORD *)&lpHandles + 1), &v141);
      }
      else
      {
        **((_QWORD **)&lpHandles + 1) = v39;
        *((_QWORD *)&lpHandles + 1) += 8LL;
      }
    }
  }
  System = SystemInterface::Service::GetSystem((__int64 *)&v162);
  v41 = (*(__int64 (__fastcall **)(__int64, unsigned __int128 *))(*(_QWORD *)*System + 32LL))(*System, &v159);
  v42 = *(_QWORD *)v41;
  v43 = *(__int64 (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)v41 + 8LL);
  v44 = -1;
  do
    ++v44;
  while ( SystemInterface::Registry::USO_USCHEDULER_OOBE_ROOT[v44] );
  *(_QWORD *)&v151 = SystemInterface::Registry::USO_USCHEDULER_OOBE_ROOT;
  *((_QWORD *)&v151 + 1) = v44;
  *(_QWORD *)&v161 = SystemInterface::Registry::USOROOT_REDIRECTION_ID;
  v45 = -1;
  do
    ++v45;
  while ( SystemInterface::Registry::USOROOT_REDIRECTION_ID[v45] );
  *((_QWORD *)&v161 + 1) = v45;
  v154 = v151;
  v160 = v161;
  v138 = v43(v42, &v160, &v154);
  v47 = (volatile signed __int32 *)*((_QWORD *)&v159 + 1);
  if ( *((_QWORD *)&v159 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v159 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v47)(v47);
      if ( !_InterlockedDecrement(v47 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v47 + 8LL))(v47);
    }
  }
  v48 = (volatile signed __int32 *)*((_QWORD *)&v162 + 1);
  if ( *((_QWORD *)&v162 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v162 + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v48)(v48);
      if ( !_InterlockedDecrement(v48 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 8LL))(v48);
    }
  }
  if ( !v138 )
    goto LABEL_102;
  v49 = SystemInterface::Service::GetSystem((__int64 *)&v164);
  v139 = 65;
  v50 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, unsigned __int128 *))(*(_QWORD *)*v49 + 64LL))(*v49, &v165);
  LODWORD(v145) = 67;
  v139 = 67;
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v50 + 32LL))(*v50) )
    goto LABEL_102;
  v51 = SystemInterface::Service::GetSystem((__int64 *)&v166);
  v139 = 71;
  (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v51 + 32LL))(*v51, &v162);
  LODWORD(v145) = 79;
  v139 = 79;
  v142 = 0;
  traits_2_unsigned_short = (__int64 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                         L"OobeAppsScanRun",
                                         &qword_1800FA2B8,
                                         0);
  if ( traits_2_unsigned_short == &qword_1800FA2B8
    || (v55 = ((char *)traits_2_unsigned_short - (char *)L"OobeAppsScanRun") >> 1, v55 == -1) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v53);
  }
  *(_QWORD *)&v151 = L"OobeAppsScanRun";
  *((_QWORD *)&v151 + 1) = v55;
  v56 = -1;
  do
    ++v56;
  while ( SystemInterface::Registry::USO_USCHEDULER_ROOT[v56] );
  *(_QWORD *)&v161 = SystemInterface::Registry::USO_USCHEDULER_ROOT;
  *((_QWORD *)&v161 + 1) = v56;
  v146[0] = (wil::details::in1diag3 *)SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
  v57 = -1;
  do
    ++v57;
  while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v57] );
  v146[1] = (wil::details::in1diag3 *)v57;
  v154 = v151;
  v160 = v161;
  v159 = *(_OWORD *)v146;
  if ( (unsigned int)SystemInterface::Registry::GetSystemValueOrDefault(
                       v54,
                       (unsigned int)&v159,
                       (unsigned int)&v160,
                       (unsigned int)&v154,
                       (__int64)&v142) == 1
    || qword_1801500D8 )
  {
LABEL_102:
    v137 = 0;
  }
  else
  {
    v137 = 1;
  }
  v58 = (unsigned int)v145;
  if ( (v145 & 8) != 0 )
  {
    v58 = (unsigned int)v145 & 0xFFFFFFF7;
    LODWORD(v145) = v145 & 0xFFFFFFF7;
    v59 = (volatile signed __int32 *)*((_QWORD *)&v162 + 1);
    if ( *((_QWORD *)&v162 + 1) )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v162 + 1) + 8LL)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v59)(v59);
        if ( !_InterlockedDecrement(v59 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v59 + 8LL))(v59);
        v58 = (unsigned int)v145;
      }
    }
  }
  if ( (v58 & 4) != 0 )
  {
    v58 = (unsigned int)v58 & 0xFFFFFFFB;
    LODWORD(v145) = v58;
    v60 = (volatile signed __int32 *)*((_QWORD *)&v166 + 1);
    if ( *((_QWORD *)&v166 + 1) )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v166 + 1) + 8LL)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v60)(v60);
        if ( !_InterlockedDecrement(v60 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v60 + 8LL))(v60);
        v58 = (unsigned int)v145;
      }
    }
  }
  if ( (v58 & 2) != 0 )
  {
    v58 = (unsigned int)v58 & 0xFFFFFFFD;
    LODWORD(v145) = v58;
    v61 = (volatile signed __int32 *)*((_QWORD *)&v165 + 1);
    if ( *((_QWORD *)&v165 + 1) )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v165 + 1) + 8LL)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v61)(v61);
        if ( !_InterlockedDecrement(v61 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v61 + 8LL))(v61);
        v58 = (unsigned int)v145;
      }
    }
  }
  if ( (v58 & 1) != 0 )
  {
    v62 = (volatile signed __int32 *)*((_QWORD *)&v164 + 1);
    if ( *((_QWORD *)&v164 + 1) )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v164 + 1) + 8LL)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
        if ( !_InterlockedDecrement(v62 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 8LL))(v62);
      }
    }
  }
  if ( v137 )
  {
    v63 = 0;
    v151 = 0;
    v64 = *((_QWORD *)&s_weakRunOperationInfo + 1);
    if ( *((_QWORD *)&s_weakRunOperationInfo + 1) )
    {
      v65 = *(_DWORD *)(*((_QWORD *)&s_weakRunOperationInfo + 1) + 8LL);
      while ( v65 )
      {
        v58 = (unsigned int)(v65 + 1);
        v66 = v65;
        v65 = _InterlockedCompareExchange((volatile signed __int32 *)(v64 + 8), v58, v65);
        if ( v66 == v65 )
        {
          v63 = (__m128i)s_weakRunOperationInfo;
          v151 = s_weakRunOperationInfo;
          break;
        }
      }
    }
    if ( v63.m128i_i64[0] )
    {
      v146[0] = (wil::details::in1diag3 *)v63.m128i_i64[0];
      if ( (unsigned int)mtx_do_lock(v63.m128i_i64[0]) )
        std::_Throw_Cpp_error(5);
      if ( *(_DWORD *)(v63.m128i_i64[0] + 76) == 0x7FFFFFFF )
      {
        *(_DWORD *)(v63.m128i_i64[0] + 76) = 2147483646;
        std::_Throw_Cpp_error(6);
      }
      v142 = 7;
      std::queue<enum RulesOperation>::push(v63.m128i_i64[0] + 88, &v142);
      v67 = SetEvent(*(HANDLE *)(v63.m128i_i64[0] + 80));
      v58 = (unsigned __int64)retaddr;
      if ( !v67 )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9C7, v46, v68);
      v69 = (*(_DWORD *)(v63.m128i_i64[0] + 76))-- == 1;
      if ( v69 )
      {
        *(_DWORD *)(v63.m128i_i64[0] + 72) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)(v63.m128i_i64[0] + 16));
      }
    }
    v70 = (volatile signed __int32 *)_mm_srli_si128(v63, 8).m128i_u64[0];
    if ( v70 )
    {
      if ( !_InterlockedDecrement(v70 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v70)(v70);
        if ( !_InterlockedDecrement(v70 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v70 + 8LL))(v70);
      }
    }
  }
  if ( v138 )
    anonymous_namespace_::SetLastKnownVersionsIfNeeded();
  v169 = off_1800F5E60;
  v173 = &v169;
  v144 = 0;
  v71 = 0;
  if ( (int)wil::details::make_wnf_subscription_state<_POWER_SCENARIO_CHANGE_NOTIFICATION_DATA>(v58, v168, v46, &v144) >= 0 )
    v71 = v144;
  v175 = v71;
  if ( v173 )
    ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v173)[3])(v173);
  v141 = 0;
  v169 = off_1800F5E38;
  v173 = &v169;
  wil::make_wnf_subscription_nothrow<wil::details::empty_wnf_state>(
    &v141,
    &WNF_SHEL_DEVICE_UNLOCKED,
    v168,
    0xFFFFFFFFLL);
  if ( v173 )
    ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v173)[3])(v173);
  v163 = 0;
  v169 = off_1800F5E88;
  v173 = &v169;
  wil::make_wnf_subscription_nothrow<wil::details::empty_wnf_state>(
    &v163,
    &WNF_FCON_CFR_TERMINATION,
    v168,
    0xFFFFFFFFLL);
  if ( v173 )
    ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v173)[3])(v173);
  v72 = (__int64)(*((_QWORD *)&lpHandles + 1) - lpHandles) >> 3;
  v142 = v72;
  v73 = v143;
LABEL_154:
  v144 = (void (__fastcall ***)(_QWORD, __int64))v72;
  while ( v136 )
  {
    v74 = WaitForMultipleObjectsEx(v72, (const HANDLE *)lpHandles, 0, 0xFFFFFFFF, 0);
    if ( v74 >= (__int64)(*((_QWORD *)&lpHandles + 1) - lpHandles) >> 3 )
    {
      v136 = 0;
      v123 = GetLastError();
      v124 = (unsigned __int16)v123 | 0x80070000;
      if ( v123 <= 0 )
        v124 = v123;
      LODWORD(v147) = v124;
LABEL_222:
      LODWORD(v72) = (_DWORD)v144;
      v73 = v143;
    }
    else
    {
      v75 = *(RulesEngine **)(lpHandles + 8 * v74);
      v73 = v143;
      if ( v75 != *(RulesEngine **)v143 )
      {
        if ( v75 == *(RulesEngine **)(s_runOperationInfo + 80) )
        {
          RulesEngine::RunNextOperation(v143);
        }
        else
        {
          if ( (_QWORD)v156 )
            v76 = *(RulesEngine **)v156;
          else
            v76 = 0;
          if ( v75 == v76 )
          {
            try
            {
              UpdateManager = (_QWORD *)anonymous_namespace_::GetUpdateManager(&v167, L"RulesEngine", &S1);
              v78 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*UpdateManager + 128LL))(*UpdateManager);
              if ( v78 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x5F7,
                  (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
                  (const char *)(unsigned int)v78,
                  bAlertable);
              if ( v167 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v167 + 16LL))(v167);
            }
            catch ( ... )
            {
              wil::details::in1diag3::Log_CaughtException(
                retaddr,
                (void *)0x5F9,
                (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
                v79);
              v1 = v149;
              v2 = v174;
              v21 = v150;
              v31 = v140;
              v71 = v175;
              v72 = v142;
              v73 = v176;
              v143 = v176;
              goto LABEL_154;
            }
          }
          else
          {
            if ( (_QWORD)v152 )
              v80 = *(RulesEngine **)v152;
            else
              v80 = 0;
            if ( v75 == v80 )
            {
              RulesEngine::ProcessUserAwaySignal(v75, v208);
              RulesEngine::ScheduleUserAwaySignal(v143, !v208);
            }
            else
            {
              if ( (_QWORD)v155 )
                v81 = *(RulesEngine **)v155;
              else
                v81 = 0;
              if ( v75 == v81 )
              {
                *(_QWORD *)&v182 = L"Network connected event was set";
                *((_QWORD *)&v182 + 1) = 31;
                *(_OWORD *)v146 = v182;
                SystemInterface::Log<>(v146);
                v82 = SystemInterface::Service::GetSystem(v191);
                v83 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)*v82 + 40LL))(*v82, v201);
                v84 = *(_QWORD *)v83;
                v85 = *(int (__fastcall **)(__int64, wil::details::in1diag3 **, int *))(**(_QWORD **)v83 + 56LL);
                v139 = 120;
                *(_OWORD *)v146 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                                               v204,
                                               L"networkScanAllowedFrequencyInMinutes");
                v86 = v85(v84, v146, &v139);
                std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v201);
                std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v191);
                if ( (unsigned __int8)Time::IsFuture(&v140)
                  || (__int64)&v31[75000000 * v86] < *(_QWORD *)std::chrono::system_clock::now(&v161) )
                {
                  std::lock_guard<std::mutex>::lock_guard<std::mutex>(&v177, s_runOperationInfo);
                  LODWORD(v145) = 2;
                  std::queue<enum RulesOperation>::push(s_runOperationInfo + 88, &v145);
                  if ( !SetEvent(*(HANDLE *)(s_runOperationInfo + 80)) )
                    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9C7, v87, v88);
                  v31 = *(void (__fastcall ****)(_QWORD, __int64))std::chrono::system_clock::now(&v151);
                  v140 = v31;
                  v89 = v177;
                  v69 = (*(_DWORD *)(v177 + 76))-- == 1;
                  if ( v69 )
                  {
                    *(_DWORD *)(v89 + 72) = -1;
                    ReleaseSRWLockExclusive((PSRWLOCK)(v89 + 16));
                  }
                }
              }
              else
              {
                if ( (_QWORD)v148 )
                  v90 = *(RulesEngine **)v148;
                else
                  v90 = 0;
                if ( v75 == v90 )
                {
                  *(_QWORD *)&v184 = L"Calling cancel from blocking apps";
                  *((_QWORD *)&v184 + 1) = 33;
                  *(_OWORD *)v146 = v184;
                  SystemInterface::Log<>(v146);
                  v91 = SystemInterface::Service::GetSystem(v193);
                  v92 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)*v91 + 32LL))(*v91, v192);
                  v93 = *(_QWORD *)v92;
                  v94 = *(void (__fastcall **)(__int64, __int128 *, wil::details::in1diag3 **))(**(_QWORD **)v92 + 72LL);
                  v95 = -1;
                  do
                    ++v95;
                  while ( SystemInterface::Registry::COMMIT_STATUS_ROOT[v95] );
                  *(_QWORD *)&v189 = SystemInterface::Registry::COMMIT_STATUS_ROOT;
                  *((_QWORD *)&v189 + 1) = v95;
                  *(_QWORD *)&v186 = SystemInterface::Registry::WU_REDIRECTION_ID;
                  v96 = -1;
                  do
                    ++v96;
                  while ( SystemInterface::Registry::WU_REDIRECTION_ID[v96] );
                  *((_QWORD *)&v186 + 1) = v96;
                  *(_OWORD *)v146 = v189;
                  v145 = v186;
                  v94(v93, &v145, v146);
                  std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v192);
                  std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v193);
                  v97 = SystemInterface::Service::GetSystem(v195);
                  *(_QWORD *)&v145 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)*v97 + 32LL))(
                                                  *v97,
                                                  v194);
                  v146[0] = *(wil::details::in1diag3 **)(*(_QWORD *)v145 + 80LL);
                  v98 = (__int128 *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v205, L"StartTime");
                  v99 = -1;
                  do
                    ++v99;
                  while ( SystemInterface::Registry::UPDATE_UX_REBOOTDOWNTIME_ROOT[v99] );
                  v187 = __PAIR128__(v99, (unsigned __int64)SystemInterface::Registry::UPDATE_UX_REBOOTDOWNTIME_ROOT);
                  *(_QWORD *)&v188 = SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID;
                  v100 = -1;
                  do
                    ++v100;
                  while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v100] );
                  *((_QWORD *)&v188 + 1) = v100;
                  v158 = *v98;
                  v157 = v187;
                  v153 = v188;
                  ((void (__fastcall *)(_QWORD, __int128 *, unsigned __int128 *, __int128 *))v146[0])(
                    v145,
                    &v153,
                    &v157,
                    &v158);
                  std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v194);
                  std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v195);
                  v101 = SystemInterface::Service::GetSystem(v197);
                  v146[0] = *(wil::details::in1diag3 **)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)*v101 + 32LL))(
                                                          *v101,
                                                          v196);
                  *(_QWORD *)&v145 = *(_QWORD *)(*(_QWORD *)v146[0] + 80LL);
                  v102 = (__int128 *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                                       &v178,
                                       L"FirstLogonAfterUpdateFlag");
                  v103 = -1;
                  do
                    ++v103;
                  while ( SystemInterface::Registry::UPDATE_UX_REBOOTDOWNTIME_ROOT[v103] );
                  v183 = __PAIR128__(v103, (unsigned __int64)SystemInterface::Registry::UPDATE_UX_REBOOTDOWNTIME_ROOT);
                  *(_QWORD *)&v185 = SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID;
                  v104 = -1;
                  do
                    ++v104;
                  while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v104] );
                  *((_QWORD *)&v185 + 1) = v104;
                  v153 = *v102;
                  v157 = v183;
                  v158 = v185;
                  ((void (__fastcall *)(wil::details::in1diag3 *, __int128 *, unsigned __int128 *, __int128 *))v145)(
                    v146[0],
                    &v158,
                    &v157,
                    &v153);
                  std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v196);
                  std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v197);
                  v105 = ServiceHelpers::UnmarkInstallAtShutdown();
                  if ( v105 < 0 )
                    wil::details::in1diag3::_Log_Hr(
                      retaddr,
                      (void *)0x625,
                      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
                      (const char *)(unsigned int)v105,
                      bAlertable);
                  v106 = SystemInterface::Service::GetSystem(v199);
                  v107 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)*v106 + 32LL))(*v106, v198);
                  v108 = *(_QWORD *)v107;
                  v109 = *(void (__fastcall **)(__int64, __int128 *, unsigned __int128 *, __int128 *))(**(_QWORD **)v107 + 80LL);
                  v110 = -1;
                  do
                    ++v110;
                  while ( SystemInterface::Registry::CURRENTREBOOTSTARTTIME[v110] );
                  *(_QWORD *)&v164 = SystemInterface::Registry::CURRENTREBOOTSTARTTIME;
                  *((_QWORD *)&v164 + 1) = v110;
                  v111 = -1;
                  do
                    ++v111;
                  while ( SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT[v111] );
                  *(_QWORD *)&v165 = SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT;
                  *((_QWORD *)&v165 + 1) = v111;
                  *(_QWORD *)&v166 = SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID;
                  v112 = -1;
                  do
                    ++v112;
                  while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v112] );
                  *((_QWORD *)&v166 + 1) = v112;
                  v153 = v164;
                  v157 = v165;
                  v158 = v166;
                  v109(v108, &v158, &v157, &v153);
                  std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v198);
                  std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v199);
                  v113 = SystemInterface::Service::GetSystem(v181);
                  v114 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)*v113 + 32LL))(*v113, v200);
                  v115 = *(_QWORD *)v114;
                  v116 = *(void (__fastcall **)(__int64, __int128 *, unsigned __int128 *, __int128 *))(**(_QWORD **)v114 + 80LL);
                  v117 = -1;
                  do
                    ++v117;
                  while ( SystemInterface::Registry::CURRENTREBOOTREASON[v117] );
                  *(_QWORD *)&v162 = SystemInterface::Registry::CURRENTREBOOTREASON;
                  *((_QWORD *)&v162 + 1) = v117;
                  v118 = -1;
                  do
                    ++v118;
                  while ( SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT[v118] );
                  *(_QWORD *)&v159 = SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT;
                  *((_QWORD *)&v159 + 1) = v118;
                  *(_QWORD *)&v160 = SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID;
                  v119 = -1;
                  do
                    ++v119;
                  while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v119] );
                  *((_QWORD *)&v160 + 1) = v119;
                  v153 = v162;
                  v157 = v159;
                  v158 = v160;
                  v116(v115, &v158, &v157, &v153);
                  std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v200);
                  std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v181);
                  if ( (_QWORD)v148 )
                    v120 = *(void **)v148;
                  else
                    v120 = 0;
                  v146[0] = retaddr;
                  if ( !ResetEvent(v120) )
                    wil::details::in1diag3::_FailFast_GetLastError(v146[0], (void *)0x9CC, v121, v122);
                }
                else
                {
                  *(_QWORD *)&v154 = L"Unknown handle fired";
                  *((_QWORD *)&v154 + 1) = 20;
                  v153 = v154;
                  SystemInterface::Log<>(&v153);
                }
              }
            }
          }
        }
        goto LABEL_222;
      }
      v136 = 0;
      LODWORD(v72) = (_DWORD)v144;
    }
  }
  v125 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v73 + 3);
  if ( v125 )
  {
    v126 = GetLastError();
    (**v125)(v125, 1);
    SetLastError(v126);
    v73 = v143;
  }
  *((_QWORD *)v73 + 3) = 0;
  v127 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v73 + 5);
  if ( v127 )
  {
    v128 = GetLastError();
    (**v127)(v127, 1);
    SetLastError(v128);
    v73 = v143;
  }
  *((_QWORD *)v73 + 5) = 0;
  s_runOperationInfo = 0;
  v129 = (volatile signed __int32 *)qword_180150B10;
  qword_180150B10 = 0;
  if ( v129 )
  {
    if ( _InterlockedExchangeAdd(v129 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v129)(v129);
      if ( _InterlockedExchangeAdd(v129 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v129 + 8LL))(v129);
    }
  }
  if ( (int)v147 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x646,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\RulesEngine.cpp",
      (const char *)(unsigned int)v147,
      bAlertable);
  if ( v163 )
    (**v163)(v163, 1);
  if ( v141 )
    (**(void (__fastcall ***)(__int64, __int64))v141)(v141, 1);
  if ( v71 )
    (**v71)(v71, 1);
  if ( (char *)NotificationHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CancelMibChangeNotify2(NotificationHandle);
  v130 = (volatile signed __int32 *)*((_QWORD *)&v155 + 1);
  if ( *((_QWORD *)&v155 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v155 + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v130)(v130);
      if ( !_InterlockedDecrement(v130 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v130 + 8LL))(v130);
    }
  }
  v131 = (volatile signed __int32 *)*((_QWORD *)&v190 + 1);
  if ( *((_QWORD *)&v190 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v190 + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v131)(v131);
      if ( !_InterlockedDecrement(v131 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v131 + 8LL))(v131);
    }
  }
  if ( v213 )
    PowerUnregisterSuspendResumeNotification();
  if ( v21 )
    (**v21)(v21, 1);
  v132 = (volatile signed __int32 *)*((_QWORD *)&v152 + 1);
  if ( *((_QWORD *)&v152 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v152 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v132)(v132);
      if ( _InterlockedExchangeAdd(v132 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v132 + 8LL))(v132);
    }
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  v133 = (volatile signed __int32 *)*((_QWORD *)&v148 + 1);
  if ( *((_QWORD *)&v148 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v148 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v133)(v133);
      if ( _InterlockedExchangeAdd(v133 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v133 + 8LL))(v133);
    }
  }
  if ( v2 )
  {
    UsoScheduler::~UsoScheduler(v2);
    operator delete(v2, (const struct std::nothrow_t *)0x128);
  }
  if ( v1 )
    (**v1)(v1, 1);
  v134 = (volatile signed __int32 *)*((_QWORD *)&v156 + 1);
  if ( *((_QWORD *)&v156 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v156 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v134)(v134);
      if ( _InterlockedExchangeAdd(v134 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v134 + 8LL))(v134);
    }
  }
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(&lpHandles);
}

```

## disassembly

```asm
0x1800187f0  mov     r11, rsp
0x1800187f3  mov     [r11+10h], rbx
0x1800187f7  mov     [r11+18h], rsi
0x1800187fb  push    rdi
0x1800187fc  push    r12
0x1800187fe  push    r13
0x180018800  push    r14
0x180018802  push    r15
0x180018804  sub     rsp, 4A0h
0x18001880b  movaps  xmmword ptr [r11-38h], xmm6
0x180018810  mov     rax, cs:__security_cookie
0x180018817  xor     rax, rsp
0x18001881a  mov     [rsp+4C8h+var_48], rax
0x180018822  mov     [rsp+4C8h+var_478], rcx
0x180018827  mov     [rsp+4C8h+var_288], rcx
0x18001882f  xor     r13d, r13d
0x180018832  mov     [rsp+4C8h+var_494], r13d
0x180018837  mov     dword ptr [rsp+4C8h+var_448], r13d
0x18001883f  xorps   xmm0, xmm0
0x180018842  xor     eax, eax
0x180018844  movups  xmmword ptr [r11-78h], xmm0
0x180018849  mov     [r11-68h], rax
0x18001884d  mov     rax, [rcx]
0x180018850  mov     [r11-440h], rax
0x180018857  mov     rax, cs:?s_runOperationInfo@@3V?$shared_ptr@URunOperationInfo@@@std@@A; std::shared_ptr<RunOperationInfo> s_runOperationInfo
0x18001885e  mov     rcx, [rax+50h]
0x180018862  mov     [r11-438h], rcx
0x180018869  lea     rax, [r11-440h]
0x180018870  mov     qword ptr [rsp+4C8h+var_408], rax
0x180018878  lea     rax, [r11-430h]
0x18001887f  mov     qword ptr [rsp+4C8h+var_408+8], rax
0x180018887  movaps  xmm0, [rsp+4C8h+var_408]
0x18001888f  movdqa  [rsp+4C8h+var_3E8], xmm0
0x180018898  lea     rdx, [r11-3E8h]
0x18001889f  lea     rcx, [r11-78h]
0x1800188a3  call    ??0?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAA@V?$initializer_list@PEAX@1@AEBV?$allocator@PEAX@1@@Z; std::vector<void *>::vector<void *>(std::initializer_list<void *>,std::allocator<void *> const &)
0x1800188a8  nop
0x1800188a9  lea     edi, [r13+1]
0x1800188ad  mov     [rsp+4C8h+var_498], dil
0x1800188b2  xorps   xmm1, xmm1
0x1800188b5  movdqu  [rsp+4C8h+var_3C8], xmm1
0x1800188be  mov     r15d, r13d
0x1800188c1  mov     [rsp+4C8h+var_430], r13
0x1800188c9  mov     esi, 128h
0x1800188ce  mov     ecx, esi; Size
0x1800188d0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800188d5  mov     rbx, rax
0x1800188d8  mov     [rsp+4C8h+var_458], rax
0x1800188dd  mov     r8d, esi; Size
0x1800188e0  xor     edx, edx; Val
0x1800188e2  mov     rcx, rax; void *
0x1800188e5  call    memset
0x1800188ea  lea     rax, off_1800F5BE0
0x1800188f1  mov     qword ptr [rsp+4C8h+var_108], rax
0x1800188f9  lea     rax, [rsp+4C8h+var_108]
0x180018901  mov     [rsp+4C8h+var_D0], rax
0x180018909  mov     [rsp+4C8h+var_494], 10h
0x180018911  mov     [rsp+4C8h+var_488], 258h
0x18001891a  xorps   xmm0, xmm0
0x18001891d  movups  [rsp+4C8h+var_278], xmm0
0x180018925  mov     [rsp+4C8h+var_268], r13
0x18001892d  mov     [rsp+4C8h+var_260], r13
0x180018935  lea     r8d, [r13+14h]
0x180018939  lea     rdx, aDelayedconfigu; "DelayedConfiguration"
0x180018940  lea     rcx, [rsp+4C8h+var_278]
0x180018948  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001894d  nop
0x18001894e  mov     [rsp+4C8h+var_494], 30h ; '0'
0x180018956  lea     rax, [rsp+4C8h+var_108]
0x18001895e  mov     qword ptr [rsp+4C8h+bAlertable], rax; unsigned int
0x180018963  xor     r9d, r9d
0x180018966  lea     r8, [rsp+4C8h+var_488]
0x18001896b  lea     rdx, [rsp+4C8h+var_278]
0x180018973  mov     rcx, rbx; this
0x180018976  call    ??0UsoScheduler@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$duration@_JU?$ratio@$00$00@std@@@chrono@2@_N$$QEAV?$function@$$A6AXXZ@2@@Z; UsoScheduler::UsoScheduler(std::wstring const &,std::chrono::duration<__int64,std::ratio<1,1>> const &,bool,std::function<void (void)> &&)
0x18001897b  mov     r12, rax
0x18001897e  mov     [rsp+4C8h+var_298], rax
0x180018986  lea     rcx, [rsp+4C8h+var_278]; void *
0x18001898e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018993  nop
0x180018994  lea     ecx, [rdi+3Fh]
0x180018997  mov     dword ptr [rsp+4C8h+var_468], ecx
0x18001899b  mov     rcx, [rsp+4C8h+var_D0]
0x1800189a3  test    rcx, rcx
0x1800189a6  jz      short loc_1800189C3
0x1800189a8  lea     rax, [rsp+4C8h+var_108]
0x1800189b0  cmp     rcx, rax
0x1800189b3  setnz   dl
0x1800189b6  mov     rax, [rcx]
0x1800189b9  mov     rax, [rax+20h]
0x1800189bd  call    _guard_dispatch_icall
0x1800189c2  nop
0x1800189c3  xorps   xmm0, xmm0
0x1800189c6  xorps   xmm1, xmm1
0x1800189c9  movdqu  [rsp+4C8h+var_440], xmm1
0x1800189d2  xor     eax, eax
0x1800189d4  movups  xmmword ptr [rsp+4C8h+EventAttributes.nLength], xmm0
0x1800189dc  mov     qword ptr [rsp+4C8h+EventAttributes.bInheritHandle], rax
0x1800189e4  mov     [rsp+4C8h+SecurityDescriptor], r13
0x1800189ec  xor     r9d, r9d; SecurityDescriptorSize
0x1800189ef  lea     r8, [rsp+4C8h+SecurityDescriptor]; SecurityDescriptor
0x1800189f7  mov     edx, edi; StringSDRevision
0x1800189f9  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;AU)(A;;GA;;;SY)"
0x180018a00  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180018a06  test    eax, eax
0x180018a08  jz      loc_180018AE0
0x180018a0e  mov     [rsp+4C8h+EventAttributes.nLength], 18h
0x180018a19  mov     rax, [rsp+4C8h+SecurityDescriptor]
0x180018a21  mov     [rsp+4C8h+EventAttributes.lpSecurityDescriptor], rax
0x180018a29  mov     [rsp+4C8h+EventAttributes.bInheritHandle], r13d
0x180018a31  mov     r9d, 1F0003h; dwDesiredAccess
0x180018a37  mov     r8d, edi; dwFlags
0x180018a3a  lea     rdx, Name; "Global\\USORebootCancel"
0x180018a41  lea     rcx, [rsp+4C8h+EventAttributes]; lpEventAttributes
0x180018a49  call    cs:__imp_CreateEventExW
0x180018a4f  mov     rbx, rax
0x180018a52  test    rax, rax
0x180018a55  jnz     short loc_180018A5C
0x180018a57  mov     al, dil
0x180018a5a  jmp     short loc_180018A75
0x180018a5c  call    cs:__imp_GetLastError
0x180018a62  mov     rdx, rbx
0x180018a65  lea     rcx, [rsp+4C8h+var_440]
0x180018a6d  call    ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x180018a72  mov     al, r13b
0x180018a75  mov     rcx, [rsp+4C8h]; this
0x180018a7d  test    al, al
0x180018a7f  jz      short loc_180018A92
0x180018a81  lea     r8, aCW1SSrcOrchest_42; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180018a88  mov     edx, 564h; void *
0x180018a8d  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180018a92  mov     rax, qword ptr [rsp+4C8h+var_440]
0x180018a9a  test    rax, rax
0x180018a9d  jz      short loc_180018AF9
0x180018a9f  mov     rax, [rax]
0x180018aa2  test    rax, rax
0x180018aa5  jz      short loc_180018AF9
0x180018aa7  mov     [rsp+4C8h+var_488], rax
0x180018aac  mov     rdx, [rsp+4C8h+var_70]
0x180018ab4  cmp     rdx, [rsp+4C8h+var_68]
0x180018abc  jz      short loc_180018ACC
0x180018abe  mov     [rdx], rax
0x180018ac1  add     [rsp+4C8h+var_70], 8
0x180018aca  jmp     short loc_180018AF9
0x180018acc  lea     r8, [rsp+4C8h+var_488]
0x180018ad1  lea     rcx, [rsp+4C8h+lpHandles]
0x180018ad9  call    ??$_Emplace_reallocate@PEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAX$$QEAPEAX@Z; std::vector<void *>::_Emplace_reallocate<void *>(void * * const,void * &&)
0x180018ade  jmp     short loc_180018AF9
0x180018ae0  mov     rcx, [rsp+4C8h]; this
0x180018ae8  lea     r8, aCW1SSrcOrchest_42; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180018aef  mov     edx, 56Eh; void *
0x180018af4  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180018af9  mov     r9d, 1F0003h; dwDesiredAccess
0x180018aff  xor     r8d, r8d; dwFlags
0x180018b02  xor     edx, edx; lpName
0x180018b04  xor     ecx, ecx; lpEventAttributes
0x180018b06  call    cs:__imp_CreateEventExW
0x180018b0c  mov     rbx, rax
0x180018b0f  test    rax, rax
0x180018b12  jnz     short loc_180018B19
0x180018b14  mov     al, dil
0x180018b17  jmp     short loc_180018B32
0x180018b19  call    cs:__imp_GetLastError
0x180018b1f  mov     rdx, rbx
0x180018b22  lea     rcx, [rsp+4C8h+var_3C8]
0x180018b2a  call    ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x180018b2f  mov     al, r13b
0x180018b32  mov     rcx, [rsp+4C8h]; this
0x180018b3a  test    al, al
0x180018b3c  jz      short loc_180018B4F
0x180018b3e  lea     r8, aCW1SSrcOrchest_42; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180018b45  mov     edx, 571h; void *
0x180018b4a  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180018b4f  mov     rcx, qword ptr [rsp+4C8h+var_3C8]
0x180018b57  test    rcx, rcx
0x180018b5a  jz      loc_180018C5C
0x180018b60  mov     rax, [rcx]
0x180018b63  test    rax, rax
0x180018b66  jz      loc_180018C5C
0x180018b6c  mov     [rsp+4C8h+var_488], rax
0x180018b71  mov     rdx, [rsp+4C8h+var_70]
0x180018b79  cmp     rdx, [rsp+4C8h+var_68]
0x180018b81  jz      short loc_180018B91
0x180018b83  mov     [rdx], rax
0x180018b86  add     [rsp+4C8h+var_70], 8
0x180018b8f  jmp     short loc_180018BAB
0x180018b91  lea     r8, [rsp+4C8h+var_488]
0x180018b96  lea     rcx, [rsp+4C8h+lpHandles]
0x180018b9e  call    ??$_Emplace_reallocate@PEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAX$$QEAPEAX@Z; std::vector<void *>::_Emplace_reallocate<void *>(void * * const,void * &&)
0x180018ba3  mov     rcx, qword ptr [rsp+4C8h+var_3C8]
0x180018bab  mov     rax, qword ptr [rsp+4C8h+var_3C8+8]
0x180018bb3  test    rax, rax
0x180018bb6  jz      short loc_180018BBC
0x180018bb8  lock add [rax+8], edi
0x180018bbc  lea     rdx, off_1800F5ED8
0x180018bc3  mov     [rsp+4C8h+var_308], rdx
0x180018bcb  mov     [rsp+4C8h+var_300], rcx
0x180018bd3  mov     [rsp+4C8h+var_2F8], rax
0x180018bdb  lea     rax, [rsp+4C8h+var_308]
0x180018be3  mov     [rsp+4C8h+var_2A0], rax
0x180018beb  mov     [rsp+4C8h+var_490], r13
0x180018bf0  lea     r9, [rsp+4C8h+var_490]
0x180018bf5  lea     rdx, [rsp+4C8h+var_310]
0x180018bfd  call    ??$make_wnf_subscription_state@U_GUID@@@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBU_GUID@@@Z@wistd@@KPEAPEAU?$wnf_subscription_state@U_GUID@@@01@@Z; wil::details::make_wnf_subscription_state<_GUID>(_WNF_STATE_NAME const &,wistd::function<void (_GUID const &)> &&,ulong,wil::details::wnf_subscription_state<_GUID> * *)
0x180018c02  mov     rcx, r13
0x180018c05  test    eax, eax
0x180018c07  cmovns  rcx, [rsp+4C8h+var_490]
0x180018c0d  mov     [rsp+4C8h+var_490], rcx
0x180018c12  lea     rdx, [rsp+4C8h+var_490]
0x180018c17  lea     rcx, [rsp+4C8h+var_430]
0x180018c1f  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x180018c24  mov     rcx, [rsp+4C8h+var_490]
0x180018c29  test    rcx, rcx
0x180018c2c  jz      short loc_180018C3B
0x180018c2e  mov     rax, [rcx]
0x180018c31  mov     edx, edi
0x180018c33  mov     rax, [rax]
0x180018c36  call    _guard_dispatch_icall
0x180018c3b  mov     rcx, [rsp+4C8h+var_2A0]
0x180018c43  test    rcx, rcx
0x180018c46  jz      short loc_180018C54
0x180018c48  mov     rax, [rcx]
0x180018c4b  mov     rax, [rax+18h]
0x180018c4f  call    _guard_dispatch_icall
0x180018c54  mov     r15, [rsp+4C8h+var_430]
0x180018c5c  xorps   xmm1, xmm1
0x180018c5f  movdqu  [rsp+4C8h+var_408], xmm1
0x180018c68  mov     r9d, 1F0003h; dwDesiredAccess
0x180018c6e  xor     r8d, r8d; dwFlags
0x180018c71  xor     edx, edx; lpName
0x180018c73  xor     ecx, ecx; lpEventAttributes
0x180018c75  call    cs:__imp_CreateEventExW
0x180018c7b  mov     rbx, rax
0x180018c7e  test    rax, rax
0x180018c81  jnz     short loc_180018C88
0x180018c83  mov     al, dil
0x180018c86  jmp     short loc_180018CA1
0x180018c88  call    cs:__imp_GetLastError
0x180018c8e  mov     rdx, rbx
0x180018c91  lea     rcx, [rsp+4C8h+var_408]
0x180018c99  call    ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x180018c9e  mov     al, r13b
0x180018ca1  mov     rcx, [rsp+4C8h]; this
0x180018ca9  test    al, al
0x180018cab  jz      short loc_180018CBE
0x180018cad  lea     r8, aCW1SSrcOrchest_42; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180018cb4  mov     edx, 57Ch; void *
0x180018cb9  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180018cbe  mov     rsi, r13
0x180018cc1  mov     [rsp+4C8h+var_428], r13
0x180018cc9  mov     [rsp+4C8h+var_80], r13b
0x180018cd1  mov     r14, qword ptr [rsp+4C8h+var_408]
0x180018cd9  test    r14, r14
0x180018cdc  jz      loc_180018E3D
0x180018ce2  mov     rax, [r14]
0x180018ce5  test    rax, rax
0x180018ce8  jz      loc_180018E3D
0x180018cee  mov     [rsp+4C8h+var_488], rax
0x180018cf3  mov     rdx, [rsp+4C8h+var_70]
0x180018cfb  cmp     rdx, [rsp+4C8h+var_68]
0x180018d03  jz      short loc_180018D13
0x180018d05  mov     [rdx], rax
0x180018d08  add     [rsp+4C8h+var_70], 8
0x180018d11  jmp     short loc_180018D25
0x180018d13  lea     r8, [rsp+4C8h+var_488]
0x180018d18  lea     rcx, [rsp+4C8h+lpHandles]
0x180018d20  call    ??$_Emplace_reallocate@PEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAX$$QEAPEAX@Z; std::vector<void *>::_Emplace_reallocate<void *>(void * * const,void * &&)
0x180018d25  mov     rcx, r13
0x180018d28  mov     rax, r13
0x180018d2b  mov     rsi, qword ptr [rsp+4C8h+var_408+8]
0x180018d33  test    rsi, rsi
0x180018d36  jz      short loc_180018D42
0x180018d38  mov     rcx, r14
0x180018d3b  mov     rax, rsi
0x180018d3e  lock add [rsi+0Ch], edi
0x180018d42  mov     cs:?s_weakUserPresentEvent@@3V?$weak_any@V?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@wil@@A, rcx
0x180018d49  mov     rcx, cs:qword_180150718
0x180018d50  mov     cs:qword_180150718, rax
0x180018d57  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180018d5b  test    rcx, rcx
0x180018d5e  jz      short loc_180018D77
0x180018d60  mov     eax, ebx
0x180018d62  lock xadd [rcx+0Ch], eax
0x180018d67  add     eax, ebx
0x180018d69  jnz     short loc_180018D77
0x180018d6b  mov     rax, [rcx]
0x180018d6e  mov     rax, [rax+8]
0x180018d72  call    _guard_dispatch_icall
0x180018d77  test    rsi, rsi
0x180018d7a  jz      short loc_180018D80
0x180018d7c  lock add [rsi+8], edi
0x180018d80  lea     rax, off_1800F5EB0
0x180018d87  mov     [rsp+4C8h+var_308], rax
0x180018d8f  mov     [rsp+4C8h+var_300], r14
0x180018d97  mov     [rsp+4C8h+var_2F8], rsi
0x180018d9f  lea     rax, [rsp+4C8h+var_80]
0x180018da7  mov     [rsp+4C8h+var_2F0], rax
0x180018daf  lea     rax, [rsp+4C8h+var_308]
0x180018db7  mov     [rsp+4C8h+var_2A0], rax
0x180018dbf  mov     [rsp+4C8h+var_490], r13
  ... truncated ...
```
