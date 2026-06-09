# CDeploymentSession::GenerateDownloadRequestForOS(_ReportEventDownloadRequestParams *,IDeploymentDownloadRequest * *)

- ea: `0x180052d40`
- end: `0x18005459f`
- name: `?GenerateDownloadRequestForOS@CDeploymentSession@@UEAAXPEAU_ReportEventDownloadRequestParams@@PEAPEAUIDeploymentDownloadRequest@@@Z`
- size: `6239`
- prototype: `void __fastcall(CDeploymentSession *__hidden this, struct _ReportEventDownloadRequestParams *, struct IDeploymentDownloadRequest **)`
- caller_count: `1`
- callee_count: `47`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002b4b8`

## callees

- `0x1800059d0`
- `0x180006a18`
- `0x18000a0e8`
- `0x18000c4c4`
- `0x180012460`
- `0x18001270c`
- `0x18001273c`
- `0x180012770`
- `0x180023b20`
- `0x1800335c4`
- `0x180037a40`
- `0x180038ecc`
- `0x18003988c`
- `0x180039f90`
- `0x18003a4b0`
- `0x18003d3b8`
- `0x18003d91c`
- `0x180041688`
- `0x1800480b4`
- `0x180048f88`
- `0x18004f0b0`
- `0x180052d40`
- `0x180054c70`
- `0x1800621cc`
- `0x1800674f0`
- `0x180068e98`
- `0x18006b114`
- `0x180073930`
- `0x180073dac`
- `0x180073f2c`
- `0x180074744`
- `0x180074c18`
- `0x1800750fc`
- `0x180077664`
- `0x18007b7c8`
- `0x18007bbb4`
- `0x18007f99c`
- `0x180084524`
- `0x18008f9a4`
- `0x180090990`
- `0x180092014`
- `0x180094d0c`
- `0x18009692c`
- `0x18009ad18`
- `0x18009b6b0`
- `0x18009d43c`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800531e8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180053501`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800531e8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180053501`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800530e5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800530e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054062`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054062`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053f09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053f09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800539d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800539d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800539e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800539e8`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180054112`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180054112`

## string_xrefs

- `0x180054551`: `onecore\internal\sdk\inc\wil\opensource\wil\stl.h`
- `0x18005420a`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18005421f`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180054237`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18005424c`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180054261`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180054276`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18005428b`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x1800542a0`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x1800542b5`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x1800542c7`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x1800542dc`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x1800542f1`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180054306`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18005431b`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18005432d`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180054342`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180054357`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18005436c`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180054381`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180054399`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x1800543ae`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x1800543c3`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x1800543fa`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18005440c`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180054421`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180054436`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18005444b`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180054460`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180054475`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18005448a`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18005449f`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x1800544b4`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x1800544cc`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x1800544e1`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x1800544f9`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18005450e`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180054523`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180054538`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180054566`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18005457b`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18005458d`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x1800531b3`: `Prev ActionList already exits.`
- `0x180053249`: `Using Supplemental compdb for upgrade.`
- `0x180053293`: `Setting CreateActionList flag to GenerateDownloadsOnly.`
- `0x1800532c1`: `CreateActionList failed. Error`
- `0x180053662`: `GenerateDownloadRequest: Compose payload required`
- `0x180053a42`: `GenerateDownloadRequest: Empty download list with some non-install action detected. Generating empty list.`
- `0x180053b90`: `Entered the scenario with plugins `
- `0x180053de3`: `GenerateDownloadRequest: Number of times corrupt files are deleted: [{}]`
- `0x18005304a`: `UseSupplementalCompDB`
- `0x180053079`: `UseSupplementalCompDB`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall CDeploymentSession::GenerateDownloadRequestForOS(
        CDeploymentSession *this,
        struct _ReportEventDownloadRequestParams *a2,
        struct IDeploymentDownloadRequest **a3)
{
  BOOL v5; // r12d
  unsigned int v6; // ebx
  char v7; // r15
  int v8; // r13d
  int v9; // eax
  int OneSettings; // eax
  int IsMoUpdateTestsEnabled; // eax
  __int64 v12; // rcx
  int v13; // esi
  int v14; // r14d
  __int64 v15; // rcx
  int Value; // eax
  __int64 v17; // rcx
  int v18; // esi
  int v19; // r14d
  __int64 v20; // rcx
  int v21; // eax
  BOOL v22; // r14d
  int v23; // eax
  __int64 v24; // rcx
  int v25; // esi
  BOOL v26; // eax
  int v27; // eax
  int v28; // esi
  BOOL v29; // eax
  int IsHostOSMobile; // eax
  DWORD FileAttributesW; // esi
  BOOL v32; // esi
  __int64 v33; // rdx
  int v34; // eax
  const wchar_t *v35; // rax
  const char *v36; // r9
  const char *v37; // rcx
  int v38; // esi
  int *v39; // rax
  int v40; // r14d
  __int64 v41; // rdx
  int v42; // eax
  int v43; // eax
  int v44; // esi
  __int64 v45; // rdx
  struct ActionList *v46; // rsi
  int v47; // eax
  int v48; // eax
  const char *v49; // r9
  int v50; // eax
  int v51; // eax
  int v52; // ebx
  __int64 v53; // rdx
  int v54; // eax
  int v55; // eax
  int v56; // eax
  int ScenarioCtrl; // eax
  int v58; // ebx
  unsigned int v59; // eax
  CDeploymentDownloadRequest *v60; // rcx
  int v61; // eax
  int v62; // ebx
  __int64 v63; // rdx
  CDeploymentDownloadRequest *v64; // rax
  unsigned int v65; // eax
  int v66; // ebx
  char v67; // al
  int v68; // eax
  int IsInitialDownloadNeeded; // eax
  int *v70; // rdx
  int v71; // r14d
  unsigned int v72; // r12d
  int v73; // r13d
  int v74; // eax
  int v75; // eax
  int v76; // eax
  unsigned int v77; // eax
  int v78; // ecx
  unsigned int v79; // ebx
  int v80; // eax
  __int64 v81; // rbx
  HANDLE ProcessHeap; // rax
  int v83; // ecx
  int v84; // eax
  CDeploymentDownloadRequest *v85; // rdx
  CDeploymentDownloadRequest *v86; // rcx
  int v87; // eax
  CDeploymentDownloadRequest *v88; // rax
  CDeploymentDownloadRequest *v89; // rdx
  CDeploymentDownloadRequest *v90; // rcx
  int v91; // eax
  CDeploymentDownloadRequest *v92; // rcx
  int v93; // eax
  bool IsDownloadListEmpty; // al
  int *v95; // rdx
  __int64 v96; // r8
  CDeploymentDownloadRequest *v97; // rdx
  CDeploymentDownloadRequest *v98; // rcx
  int v99; // eax
  bool v100; // al
  int v101; // eax
  int v102; // ebx
  struct _ReportEventDownloadRequestParams *v103; // r12
  bool v104; // zf
  _DWORD *v105; // r15
  unsigned int v106; // eax
  int v107; // r14d
  int v108; // eax
  int v109; // eax
  __int64 v110; // r12
  unsigned __int64 v111; // r15
  int v112; // r14d
  unsigned __int64 v113; // r14
  int v114; // eax
  __int64 v115; // rax
  unsigned int v116; // ebx
  const char *v117; // r9
  _QWORD *v118; // r8
  int v119; // eax
  int v120; // ebx
  __int64 v121; // rdx
  int v122; // eax
  const char *v123; // r9
  int v124; // eax
  CDeploymentDownloadRequest *v125; // rax
  struct ActionList *v126; // [rsp+28h] [rbp-E0h]
  int *v127; // [rsp+28h] [rbp-E0h]
  int v128; // [rsp+28h] [rbp-E0h]
  int *v129; // [rsp+28h] [rbp-E0h]
  int v130; // [rsp+28h] [rbp-E0h]
  int v131; // [rsp+88h] [rbp-80h] BYREF
  int v132; // [rsp+8Ch] [rbp-7Ch] BYREF
  int v133; // [rsp+90h] [rbp-78h] BYREF
  int v134; // [rsp+94h] [rbp-74h]
  int v135; // [rsp+98h] [rbp-70h]
  struct ActionList *v136; // [rsp+A0h] [rbp-68h] BYREF
  struct _ReportEventDownloadRequestParams *v137; // [rsp+A8h] [rbp-60h] BYREF
  int v138[2]; // [rsp+B0h] [rbp-58h] BYREF
  int v139; // [rsp+B8h] [rbp-50h] BYREF
  char v140; // [rsp+BCh] [rbp-4Ch] BYREF
  int v141[2]; // [rsp+C0h] [rbp-48h] BYREF
  struct IDeploymentDownloadRequest **v142; // [rsp+C8h] [rbp-40h]
  int v143[2]; // [rsp+D0h] [rbp-38h] BYREF
  int v144[4]; // [rsp+D8h] [rbp-30h] BYREF
  int v145[2]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v146; // [rsp+F0h] [rbp-18h]
  void **v147; // [rsp+F8h] [rbp-10h]
  char *v148; // [rsp+100h] [rbp-8h]
  __int64 v149; // [rsp+108h] [rbp+0h]
  __int64 v150; // [rsp+110h] [rbp+8h]
  __int64 v151; // [rsp+118h] [rbp+10h]
  CDeploymentDownloadRequest *v152; // [rsp+120h] [rbp+18h] BYREF
  int v153; // [rsp+128h] [rbp+20h] BYREF
  wchar_t v154; // [rsp+12Ch] [rbp+24h] BYREF
  int v155; // [rsp+130h] [rbp+28h] BYREF
  int v156; // [rsp+134h] [rbp+2Ch] BYREF
  int IsRangeRequestSupported; // [rsp+138h] [rbp+30h] BYREF
  int v158; // [rsp+13Ch] [rbp+34h] BYREF
  int v159[2]; // [rsp+140h] [rbp+38h] BYREF
  int v160; // [rsp+148h] [rbp+40h] BYREF
  unsigned __int64 v161; // [rsp+150h] [rbp+48h] BYREF
  unsigned __int64 v162; // [rsp+158h] [rbp+50h] BYREF
  unsigned __int64 v163; // [rsp+160h] [rbp+58h] BYREF
  unsigned __int64 v164; // [rsp+168h] [rbp+60h] BYREF
  unsigned __int64 v165; // [rsp+170h] [rbp+68h] BYREF
  unsigned __int64 v166; // [rsp+178h] [rbp+70h] BYREF
  _QWORD v167[4]; // [rsp+180h] [rbp+78h] BYREF
  char v168; // [rsp+1A0h] [rbp+98h]
  _BYTE v169[80]; // [rsp+1A8h] [rbp+A0h] BYREF
  WCHAR szVolumeMountPoint[8]; // [rsp+1F8h] [rbp+F0h] BYREF
  WCHAR szVolumeName[56]; // [rsp+208h] [rbp+100h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C0h] [rbp+1B8h]

  v151 = -2;
  v142 = a3;
  v137 = a2;
  v5 = 0;
  v136 = 0;
  v6 = 0;
  v131 = 0;
  v134 = 0;
  v138[0] = 0;
  v135 = 0;
  v159[0] = 0;
  v144[0] = 0;
  v145[0] = 0;
  v141[0] = 0;
  v7 = 1;
  v158 = 1;
  v155 = 0;
  v160 = 0;
  v154 = 0;
  v164 = 0;
  v162 = 0;
  v165 = 0;
  v163 = 0;
  v161 = 0;
  v166 = 0;
  v152 = 0;
  IsRangeRequestSupported = 0;
  memset_0(v169, 0, 0x48u);
  v156 = 0;
  memset_0(szVolumeName, 0, 0x64u);
  wcscpy(szVolumeMountPoint, L"?:\\");
  if ( !a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C60,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)0x80004003LL,
      (int)v126);
  v8 = 0;
  v9 = CDeploymentSession::ExecuteMitigations(this);
  if ( v9 < 0 )
    LogAdapter::TraceAtLevelHr<long,>(2, (unsigned int)v9, "Error executing mitigations");
  OneSettings = CDeploymentSession::GetOneSettings(this);
  if ( OneSettings < 0 )
    LogAdapter::TraceAtLevelHr<long,>(2, (unsigned int)OneSettings, "Error getting OneSettings");
  v153 = 0;
  v132 = 0;
  v133 = 0;
  IsMoUpdateTestsEnabled = CMoUpdateHelpersT<CEmptyType>::IsMoUpdateTestsEnabled(&v153);
  v13 = IsMoUpdateTestsEnabled;
  if ( IsMoUpdateTestsEnabled < 0 )
    goto LABEL_7;
  v14 = 0;
  if ( v153 )
  {
    IsMoUpdateTestsEnabled = CRegUtilT<unsigned long,CRegType,0,1>::ValueExists(
                               v12,
                               L"SYSTEM\\Setup\\MoSetup",
                               L"ArbiterUnitTest",
                               &v132);
    v13 = IsMoUpdateTestsEnabled;
    if ( IsMoUpdateTestsEnabled < 0 )
      goto LABEL_7;
    if ( v132 )
    {
      IsMoUpdateTestsEnabled = CRegUtilT<unsigned long,CRegType,0,1>::GetValue(
                                 v15,
                                 L"SYSTEM\\Setup\\MoSetup",
                                 L"ArbiterUnitTest",
                                 &v133);
      v13 = IsMoUpdateTestsEnabled;
      if ( IsMoUpdateTestsEnabled >= 0 )
      {
        LOBYTE(v14) = v133 != 0;
        goto LABEL_13;
      }
LABEL_7:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)IsMoUpdateTestsEnabled);
      goto LABEL_14;
    }
  }
LABEL_13:
  v8 = v14;
LABEL_14:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C6C,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)v13,
      (int)v126);
  v143[0] = 0;
  v133 = 0;
  v132 = 0;
  v153 = 0;
  Value = CMoUpdateHelpersT<CEmptyType>::IsMoUpdateTestsEnabled(&v133);
  v18 = Value;
  if ( Value < 0 )
    goto LABEL_16;
  v19 = 0;
  if ( v133 )
  {
    Value = CRegUtilT<unsigned long,CRegType,0,1>::ValueExists(
              v17,
              L"SYSTEM\\Setup\\MoSetup",
              L"SkipExpressDiskspaceCheck",
              &v132);
    v18 = Value;
    if ( Value < 0 )
      goto LABEL_16;
    if ( v132 )
    {
      Value = CRegUtilT<unsigned long,CRegType,0,1>::GetValue(
                v20,
                L"SYSTEM\\Setup\\MoSetup",
                L"SkipExpressDiskspaceCheck",
                &v153);
      v18 = Value;
      if ( Value >= 0 )
      {
        LOBYTE(v19) = v153 != 0;
        goto LABEL_22;
      }
LABEL_16:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Value);
      goto LABEL_23;
    }
  }
LABEL_22:
  v143[0] = v19;
LABEL_23:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v18);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C6D,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)v18,
      (int)v126);
  v21 = CDeploymentSession::IsSkipPreDownloadCheck(this, &v155);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C6E,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)v21,
      (int)v126);
  v22 = 0;
  v133 = 0;
  v132 = 0;
  v23 = CRegUtilT<unsigned long,CRegType,0,1>::ValueExists(
          retaddr,
          L"SYSTEM\\Setup\\MoSetup",
          L"UseServicingForUpgrade",
          &v133);
  v25 = v23;
  if ( v23 < 0 )
    goto LABEL_26;
  v26 = 0;
  if ( v133 )
  {
    v23 = CRegUtilT<unsigned long,CRegType,0,1>::GetValue(
            v24,
            L"SYSTEM\\Setup\\MoSetup",
            L"UseServicingForUpgrade",
            &v132);
    v25 = v23;
    if ( v23 < 0 )
    {
LABEL_26:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v23);
      goto LABEL_31;
    }
    v26 = v132 != 0;
  }
  v5 = v26;
LABEL_31:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v25);
  if ( v25 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C6F,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)v25,
      (int)v126);
  v133 = 0;
  v132 = 0;
  v27 = CRegUtilT<unsigned long,CRegType,0,1>::ValueExists(
          retaddr,
          L"SYSTEM\\Setup\\MoSetup",
          L"UseSupplementalCompDB",
          &v133);
  v28 = v27;
  if ( v27 < 0 )
    goto LABEL_33;
  v29 = 0;
  if ( v133 )
  {
    v27 = CRegUtilT<unsigned long,CRegType,0,1>::GetValue(0, L"SYSTEM\\Setup\\MoSetup", L"UseSupplementalCompDB", &v132);
    v28 = v27;
    if ( v27 < 0 )
    {
LABEL_33:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v27);
      goto LABEL_38;
    }
    v29 = v132 != 0;
  }
  v22 = v29;
LABEL_38:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v28);
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C70,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)v28,
      (int)v126);
  IsHostOSMobile = CMoUpdateHelpersT<CEmptyType>::IsHostOSMobile(&IsRangeRequestSupported, *((_QWORD *)this + 70));
  if ( IsHostOSMobile < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C75,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)IsHostOSMobile,
      (int)v126);
  if ( IsRangeRequestSupported )
    goto LABEL_67;
  FileAttributesW = GetFileAttributesW(*((LPCWSTR *)this + 63));
  v32 = FileAttributesW != -1 && ((FileAttributesW >> 4) & 1) == 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  IsRangeRequestSupported = CDeploymentSession::IsRangeRequestSupported(
                              this,
                              v138,
                              (enum MoUpdateRangeRequestState *)v159);
  if ( IsRangeRequestSupported >= 0 )
  {
    v35 = L"TRUE";
    v134 = v138[0];
    if ( !v138[0] )
      v35 = L"FALSE";
    *(_QWORD *)v138 = v35;
    LogAdapter::TraceInfo<wchar_t const *>("Range Request Supported: [{}]", v138);
    v34 = v134;
  }
  else
  {
    *(_QWORD *)v138 = &IsRangeRequestSupported;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      v126 = (struct ActionList *)v138;
      LOBYTE(v33) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v33,
        3,
        "IsRangeRequestSupported failed with: [{}]. Setting RangeRequestSupported to FALSE ");
    }
    v34 = 0;
    v134 = 0;
  }
  *((_DWORD *)this + 54) = v34;
  if ( v34 )
  {
    v6 = 2049;
    v131 = 2049;
    if ( v32 )
    {
      LogAdapter::TraceInfo<>("Prev ActionList already exits.");
      v135 = 5;
      goto LABEL_58;
    }
  }
  else if ( v32 )
  {
    if ( *((_DWORD *)this + 61) )
    {
      LogAdapter::TraceInfo<>("Deleting prev ActionList since it contained Express packages.");
      if ( !DeleteFileW(*((LPCWSTR *)this + 63)) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x1C98,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          v36);
    }
  }
  v135 = v159[0];
LABEL_58:
  if ( *((_BYTE *)this + 328) || v5 )
  {
    v6 |= 0x40u;
    v131 = v6;
    v37 = "Using servicing for upgrade.";
  }
  else
  {
    v37 = "Not using servicing for upgrade.";
  }
  LogAdapter::TraceInfo<>(v37);
  if ( *((_DWORD *)this + 75) || v22 )
  {
    v6 |= 0x20u;
    v131 = v6;
    LogAdapter::TraceInfo<>("Using Supplemental compdb for upgrade.");
  }
  if ( *((_DWORD *)this + 76) )
  {
    v6 |= 0x400u;
    v131 = v6;
    LogAdapter::TraceInfo<>("Enabling trimming unused language packs.");
  }
LABEL_67:
  if ( v8 )
  {
    v6 |= 4u;
    v131 = v6;
  }
  if ( (*((_BYTE *)this + 372) & 8) != 0 && *((_QWORD *)this + 71) )
  {
    LogAdapter::TraceInfo<>("Setting CreateActionList flag to GenerateDownloadsOnly.");
    v6 |= 0x80u;
    v131 = v6;
  }
  v38 = CDeploymentSession::CallCreateActionList(this, v6, &v136);
  v139 = -2146467824;
  v39 = &v139;
  do
  {
    if ( v38 == *v39 )
    {
      v40 = 0;
      goto LABEL_79;
    }
    ++v39;
  }
  while ( v39 != (int *)&v140 );
  v40 = v38;
  if ( v38 < 0 )
  {
    v159[0] = v38;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "CreateActionList failed. Error");
      *(_QWORD *)v138 = v159;
      v126 = (struct ActionList *)v138;
      LOBYTE(v41) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v41,
        3,
        ": {}");
    }
  }
LABEL_79:
  if ( v40 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CCD,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)v40,
      (int)v126);
  if ( v38 < 0 )
  {
    v42 = CDeploymentSession::AcquireMetadataFromCurrentOSUpdate(this, &v156);
    if ( v42 < 0 )
      LogAdapter::TraceAtLevelHr<long,>(2, (unsigned int)v42, "Failed to get current OS upgrade metadata. Error");
    if ( !v156 )
    {
      LogAdapter::TraceInfo<>("Could not find reverse-delta metadata.");
      v6 &= ~0x10u;
      v131 = v6;
      v135 = 9;
    }
    if ( v136 )
    {
      (**(void (__fastcall ***)(struct ActionList *))v136)(v136);
      v136 = 0;
    }
    v43 = CDeploymentSession::CallCreateActionList(this, v6, &v136);
    v44 = v43;
    if ( v43 < 0 )
    {
      v156 = v43;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "CreateActionList failed. Error");
        *(_QWORD *)v159 = &v156;
        v126 = (struct ActionList *)v159;
        LOBYTE(v45) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v45,
          3,
          ": {}");
      }
    }
    if ( v44 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CE3,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
        (const char *)(unsigned int)v44,
        (int)v126);
  }
  CDeploymentSession::CopyArbiterGeneratedFilesWithRegularActionList(this);
  v46 = v136;
  v47 = CDeploymentSession::DeterminePackageTypesPresence(this, v136);
  if ( v47 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CE8,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)v47,
      (int)v126);
  if ( !*((_QWORD *)this + 58) && !*((_DWORD *)this + 114) )
  {
    if ( *((_DWORD *)v46 + 13) != 2 || (v6 & 1) == 0 )
    {
LABEL_116:
      v55 = CDeploymentSession::SetScenarioFromActionList(this, *((unsigned int *)v46 + 13));
      if ( v55 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D22,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v55,
          (int)v126);
      v56 = CDeploymentSession::ExecuteMitigations(this);
      if ( v56 < 0 )
        LogAdapter::TraceAtLevelHr<long,>(2, (unsigned int)v56, "Error executing mitigations");
      ScenarioCtrl = CDeploymentSession::CreateScenarioCtrl(this);
      if ( ScenarioCtrl < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D2B,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)ScenarioCtrl,
          (int)v126);
      goto LABEL_120;
    }
    if ( *((_DWORD *)this + 72) )
    {
      LogAdapter::TraceInfo<>("Express disabled via forcing canonical packages.");
      v135 = 7;
    }
    else if ( *((_DWORD *)this + 90) > *((_DWORD *)this + 87) )
    {
      if ( v143[0] )
        goto LABEL_105;
      v48 = CDeploymentSession::CheckFreeDiskspaceForExpress(this, &v158);
      if ( v48 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D02,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v48,
          (int)v126);
      if ( v158 )
        goto LABEL_105;
      LogAdapter::TraceInfo<>("Not enough space for Express support.");
      v135 = 4;
    }
    else
    {
      LogAdapter::TraceInfo<>("Express disabled via download count.");
      v135 = 8;
    }
    v6 &= ~1u;
    v131 = v6;
LABEL_105:
    if ( (v6 & 1) != 0 )
    {
      LogAdapter::TraceInfo<>("Enough space is detected for Express support.");
    }
    else
    {
      LogAdapter::TraceInfo<>("Deleting prev ActionList since it contained Express packages.");
      if ( !DeleteFileW(*((LPCWSTR *)this + 63)) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x1D10,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          v49);
      v50 = CDeploymentSession::CleanExpressFolders(this);
      if ( v50 < 0 )
        LogAdapter::TraceAtLevelHr<long,>(1, (unsigned int)v50, "Cleaning express folders failed");
      (**(void (__fastcall ***)(struct ActionList *))v46)(v46);
      v136 = 0;
      v51 = CDeploymentSession::CallCreateActionList(this, v6, &v136);
      v52 = v51;
      if ( v51 < 0 )
      {
        v158 = v51;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "CreateActionList failed. Error");
          *(_QWORD *)v143 = &v158;
          v126 = (struct ActionList *)v143;
          LOBYTE(v53) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v53,
            3,
            ": {}");
        }
      }
      if ( v52 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D16,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v52,
          (int)v126);
      CDeploymentSession::CopyArbiterGeneratedFilesWithRegularActionList(this);
      v46 = v136;
      v54 = CDeploymentSession::DeterminePackageTypesPresence(this, v136);
      if ( v54 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D1A,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v54,
          (int)v126);
    }
    goto LABEL_116;
  }
LABEL_120:
  v58 = 20971544;
  if ( v46 )
  {
    if ( *((_DWORD *)v46 + 60) )
    {
      v59 = *((_DWORD *)this + 114);
      if ( v59 <= 0x18 )
      {
        if ( _bittest(&v58, v59) )
        {
          LogAdapter::TraceInfo<>("GenerateDownloadRequest: Compose payload required");
          *(_QWORD *)((char *)this + 236) = 1;
          *((_DWORD *)v137 + 33) = 1;
        }
      }
    }
  }
  if ( (*((_BYTE *)this + 740) & 1) != 0 )
  {
    LogAdapter::TraceInfo<>("GenerateDownloadRequest: Caller requested only for Predownload content");
    v60 = v152;
    v152 = 0;
    if ( v60 )
      (*(void (__fastcall **)(CDeploymentDownloadRequest *))(*(_QWORD *)v60 + 16LL))(v60);
    v61 = CDeploymentSession::Predownload(this, &v152);
    v62 = v61;
    if ( v61 < 0 )
    {
      v155 = v61;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Predownload failed. Error");
        v137 = (struct _ReportEventDownloadRequestParams *)&v155;
        v126 = (struct ActionList *)&v137;
        LOBYTE(v63) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v63,
          3,
          ": {}");
      }
    }
    if ( v62 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1D3D,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
        (const char *)(unsigned int)v62,
        (int)v126);
    v64 = v152;
    v152 = 0;
    *v142 = v64;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UpdateAgentWUSARebaseMultiMSU>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_UpdateAgentWUSARebaseMultiMSU>::GetImpl'::`2'::impl) )
    {
      if ( *((_DWORD *)v46 + 13)
        && (*((_DWORD *)v46 + 18)
         || *((_DWORD *)v46 + 24)
         || *((_DWORD *)v46 + 28)
         || *((_DWORD *)v46 + 32)
         || *((_DWORD *)v46 + 36)
         || *((_DWORD *)v46 + 56)) )
      {
        v7 = 0;
      }
      if ( v7 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D45,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)0xC1900401LL,
          (int)v126);
    }
    if ( v152 )
      (*(void (__fastcall **)(CDeploymentDownloadRequest *))(*(_QWORD *)v152 + 16LL))(v152);
    if ( v46 )
      (**(void (__fastcall ***)(struct ActionList *))v46)(v46);
    return;
  }
  if ( (*((_BYTE *)this + 372) & 0x20) != 0 && (v65 = *((_DWORD *)this + 114), v65 <= 0x18) && _bittest(&v58, v65) )
  {
    v66 = v134;
  }
  else
  {
    v66 = v134;
    if ( *((_DWORD *)this + 114) != 20 || v134 )
    {
      v67 = 0;
      goto LABEL_152;
    }
  }
  v67 = 1;
LABEL_152:
  *((_BYTE *)this + 329) = v67;
  v68 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 60) + 8LL))(*((_QWORD *)this + 60), 2);
  if ( v68 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D4F,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)v68,
      (int)v126);
  IsInitialDownloadNeeded = CDeploymentSession::IsInitialDownloadNeeded(this, v46, v66, v144, v145);
  if ( IsInitialDownloadNeeded < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D54,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)IsInitialDownloadNeeded,
      (int)v127);
  v71 = 0;
  v72 = 100;
  v73 = v144[0];
  if ( *((_BYTE *)this + 329) )
  {
    LogAdapter::TraceInfo<>("Requesting Download Full Payloads.");
  }
  else if ( v144[0] )
  {
    LogAdapter::TraceInfo<>("Requesting Initial Download Only.");
    v71 = 1;
    v72 = 1;
  }
  else
  {
    v74 = *((_DWORD *)this + 114);
    if ( v74 != 22 && v74 != 4 || !*((_BYTE *)this + 339) )
    {
      v75 = CDeploymentSession::HandleExpressMetadataPayload(this, &v136, (enum CreateActionListFlags *)&v131, v141);
      v153 = v75;
      if ( v75 < 0 )
      {
        *(_QWORD *)v144 = &v153;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          v127 = v144;
          LOBYTE(v70) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v70,
            3,
            "GenerateDownloadRequest: Failed with error [{}]");
          v75 = v153;
        }
        if ( CDeploymentSession::ShouldForceCanonical(this, v75) )
        {
          LogAdapter::TraceInfo<>("GenerateDownloadRequest: This error will force a canonical retry.");
          *((_DWORD *)this + 87) = *((_DWORD *)this + 90);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1D6F,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
            (const char *)0x8024200DLL,
            (int)v127);
        }
        if ( v153 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1D73,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
            (const char *)(unsigned int)v153,
            (int)v127);
      }
      *((_BYTE *)this + 339) = 1;
      v46 = v136;
    }
  }
  v76 = CDeploymentSession::CheckCancelRequested(this, v70);
  if ( v76 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D7B,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)v76,
      (int)v127);
  if ( v141[0] )
  {
    v77 = *((_DWORD *)this + 114);
    if ( v77 > 0x16 || (v78 = 4195440, v79 = 1, !_bittest(&v78, v77)) )
      v79 = 0;
    UpdateAgentMisc::ConvertWinDirToDefaultBootDir(v141, *((_QWORD *)this + 70));
    v127 = (int *)*((_QWORD *)this + 64);
    v80 = CProgressHandler::InitializeForExpander(*((_QWORD *)this + 60), 0, v46, v79);
    if ( v80 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1D8C,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
        (const char *)(unsigned int)v80,
        (int)v127);
    v81 = *(_QWORD *)v141;
    if ( *(_QWORD *)v141 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)(v81 - 4));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    }
    v66 = v134;
  }
  v83 = *((_DWORD *)v46 + 18);
  if ( !v83 )
  {
    v84 = *((_DWORD *)this + 114);
    if ( v84 == 1 )
    {
      if ( *((_DWORD *)v46 + 28) || *((_DWORD *)v46 + 36) || *((_DWORD *)v46 + 52) || *((_DWORD *)v46 + 56) )
        goto LABEL_187;
    }
    else if ( v84 == 2 )
    {
LABEL_187:
      LogAdapter::TraceInfo<>("GenerateDownloadRequest: Empty download list with some non-install action detected. Generating empty list.");
      v85 = v152;
      v86 = 0;
      v152 = 0;
      if ( v85 )
      {
        (*(void (__fastcall **)(CDeploymentDownloadRequest *))(*(_QWORD *)v85 + 16LL))(v85);
        v86 = v152;
      }
      v152 = 0;
      if ( v86 )
        (*(void (__fastcall **)(CDeploymentDownloadRequest *))(*(_QWORD *)v86 + 16LL))(v86);
      v87 = CDeploymentSession::GenerateEmptyDownloadList(this, *((const wchar_t **)this + 63), &v152);
      if ( v87 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D9B,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v87,
          (int)v127);
LABEL_192:
      v88 = v152;
      v152 = 0;
      *v142 = v88;
      (**(void (__fastcall ***)(struct ActionList *))v46)(v46);
      return;
    }
  }
  if ( *((_DWORD *)this + 81) )
    goto LABEL_187;
  if ( !v83 && (*((_DWORD *)v46 + 32) || *((_DWORD *)v46 + 36) || *((_DWORD *)v46 + 40)) )
  {
    LogAdapter::TraceInfo<>("GenerateDownloadRequest: Empty download list with some non-download action detected. Generating empty list.");
    v89 = v152;
    v90 = 0;
    v152 = 0;
    if ( v89 )
    {
      (*(void (__fastcall **)(CDeploymentDownloadRequest *))(*(_QWORD *)v89 + 16LL))(v89);
      v90 = v152;
    }
    v152 = 0;
    if ( v90 )
      (*(void (__fastcall **)(CDeploymentDownloadRequest *))(*(_QWORD *)v90 + 16LL))(v90);
    v91 = CDeploymentSession::GenerateEmptyDownloadList(this, *((const wchar_t **)this + 63), &v152);
    if ( v91 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1DA5,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
        (const char *)(unsigned int)v91,
        (int)v127);
    goto LABEL_192;
  }
  if ( *((_BYTE *)v46 + 48) && !v83 || *((_DWORD *)this + 114) == 21 )
  {
    LogAdapter::TraceInfo<>("Entered the scenario with plugins ");
    *((_DWORD *)this + 114) = 21;
    if ( v152 )
      (*(void (__fastcall **)(CDeploymentDownloadRequest *))(*(_QWORD *)v152 + 16LL))(v152);
    (**(void (__fastcall ***)(struct ActionList *))v46)(v46);
  }
  else
  {
    v92 = v152;
    v152 = 0;
    if ( v92 )
      (*(void (__fastcall **)(CDeploymentDownloadRequest *, _QWORD))(*(_QWORD *)v92 + 16LL))(v92, 0);
    v93 = CDeploymentSession::GenerateDownloadList(
            this,
            v46,
            v71,
            v66,
            0,
            *((unsigned __int8 *)this + 329),
            *((const wchar_t **)this + 66),
            v72,
            &v164,
            &v162,
            &v163,
            &v161,
            (struct _DUPackageInfo *)v169,
            v137,
            &v152);
    if ( v93 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1DC6,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
        (const char *)(unsigned int)v93,
        v128);
    IsDownloadListEmpty = CDeploymentSession::IsDownloadListEmpty(this, v152);
    v96 = 0;
    if ( IsDownloadListEmpty )
    {
      v97 = v152;
      v98 = 0;
      v152 = 0;
      if ( v97 )
      {
        (*(void (__fastcall **)(CDeploymentDownloadRequest *, CDeploymentDownloadRequest *, _QWORD))(*(_QWORD *)v97 + 16LL))(
          v97,
          v97,
          0);
        v98 = v152;
      }
      v152 = 0;
      if ( v98 )
        (*(void (__fastcall **)(CDeploymentDownloadRequest *, CDeploymentDownloadRequest *, _QWORD))(*(_QWORD *)v98 + 16LL))(
          v98,
          v97,
          0);
      v99 = CDeploymentSession::GenerateDownloadList(
              this,
              v46,
              v71,
              v66,
              1,
              *((unsigned __int8 *)this + 329),
              *((const wchar_t **)this + 66),
              v72,
              &v164,
              &v165,
              &v163,
              &v166,
              (struct _DUPackageInfo *)v169,
              v137,
              &v152);
      if ( v99 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DD9,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v99,
          v128);
      if ( v162 <= v165 )
        v162 = v165;
      if ( v161 <= v166 )
        v161 = v166;
      v100 = CDeploymentSession::IsDownloadListEmpty(this, v152);
      v96 = 0;
      if ( v100 )
      {
        v101 = CDeploymentSession::ReportDownloadInfo(this, v46);
        v96 = 0;
        if ( v101 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1DDE,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
            (const char *)(unsigned int)v101,
            v128);
      }
    }
    v102 = -2147024362;
    v103 = v137;
    v104 = (v145[0] | *((_DWORD *)v137 + 6)) == 0;
    *((_DWORD *)v137 + 6) |= v145[0];
    if ( !v104 )
    {
      v105 = (_DWORD *)((char *)this + 344);
      v106 = *((_DWORD *)this + 86);
      if ( v106 + 1 < v106 )
      {
        v107 = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
      }
      else
      {
        *v105 = v106 + 1;
        v107 = 0;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v107);
      if ( v107 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DE5,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v107,
          v128);
      LogAdapter::TraceInfo<unsigned long>(
        "GenerateDownloadRequest: Number of times corrupt files are deleted: [{}]",
        (char *)this + 344);
      if ( *((_DWORD *)this + 89) <= *v105 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DE7,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)0xC1900403LL,
          v128);
    }
    v108 = *((_DWORD *)this + 114);
    if ( (v108 == 3 || v108 == 24) && !v73 && !*((_DWORD *)this + 55) && !v155 )
    {
      v109 = CDeploymentSession::CheckCancelRequested(this, v95);
      if ( v109 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DF2,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v109,
          v128);
      v110 = *((_QWORD *)this + 58);
      if ( !v110 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DF3,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)0x8000FFFFLL,
          v128);
      v111 = v163 + v161;
      if ( v163 + v161 < v163 )
      {
        v111 = 0;
        v112 = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
      }
      else
      {
        v112 = 0;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v112);
      if ( v112 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DF6,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v112,
          v128);
      v113 = v164 + v162;
      if ( v164 + v162 < v164 )
      {
        v113 = 0;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
      }
      else
      {
        v102 = 0;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v102);
      if ( v102 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DF7,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v102,
          v128);
      v150 = 0;
      v149 = 0;
      v148 = (char *)this + 400;
      v147 = &CDlpAutoLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable';
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 408));
      LODWORD(v149) = 1;
      v114 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 58) + 80LL))(*((_QWORD *)this + 58), &v160);
      if ( v114 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DFD,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v114,
          v128);
      *((_DWORD *)this + 50) = v160 & 1;
      v115 = *((_QWORD *)this + 61);
      if ( v115 )
        v116 = *(_DWORD *)(v115 - 4);
      else
        v116 = 0;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      if ( *(_WORD *)(*((_QWORD *)this + 61) + 2LL * v116) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xB6,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\stl.h",
          v117);
      *(_QWORD *)v145 = *((_QWORD *)this + 61);
      v146 = v116;
      CDeploymentSession::PrepareSetupDUDirectory(v116, v167, v46, v145);
      *((_DWORD *)this + 50) = 0;
      if ( v168 )
      {
        v118 = v167;
        if ( v167[3] > 7u )
          v118 = (_QWORD *)v167[0];
      }
      else
      {
        v118 = 0;
      }
      v129 = (int *)&v154;
      v119 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD *, _QWORD))(*(_QWORD *)v110 + 200LL))(
               v110,
               v111,
               v118,
               *((_QWORD *)this + 63));
      v120 = v119;
      if ( v119 < 0 )
      {
        v155 = v119;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Predownload exited. Error");
          *(_QWORD *)v145 = &v155;
          v129 = v145;
          LOBYTE(v121) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v121,
            3,
            ": {}");
        }
      }
      if ( v120 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1E09,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v120,
          (int)v129);
      if ( v168 )
        std::wstring::~wstring(v167);
      if ( (_DWORD)v149 )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 408));
        LODWORD(v149) = 0;
      }
      LogAdapter::TraceInfo<>("Pruning DU content...");
      v103 = v137;
      v122 = CDeploymentSession::PruneDownloadList(
               this,
               v113,
               v111,
               v154,
               v46,
               (struct _DUPackageInfo *)v169,
               v137,
               v152);
      if ( v122 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1E13,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v122,
          v130);
      LogAdapter::TraceInfo<>("Download Request pruned.");
      if ( v154 )
      {
        szVolumeMountPoint[0] = v154;
        memset_0(szVolumeName, 0, 0x64u);
        if ( !GetVolumeNameForVolumeMountPointW(szVolumeMountPoint, szVolumeName, 0x32u) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x1E1C,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
            v123);
        v137 = (struct _ReportEventDownloadRequestParams *)szVolumeName;
        LogAdapter::TraceInfo<wchar_t const *>("Setting Download volume as external drive [{}]", &v137);
        v124 = CDeploymentDownloadRequest::SetDownloadVolume(v152, szVolumeName);
        if ( v124 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1E1F,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
            (const char *)(unsigned int)v124,
            v130);
      }
      *((_DWORD *)this + 55) = 1;
    }
    if ( *((_DWORD *)this + 61) )
    {
      LogAdapter::TraceInfo<>("GenerateDownloadRequest: Expansion will be required");
      *((_DWORD *)this + 56) = 1;
    }
    *((_DWORD *)v103 + 5) = v135;
    *((_DWORD *)v103 + 7) = *((_DWORD *)this + 61);
    *((_DWORD *)v103 + 8) = *((_DWORD *)this + 62);
    *((_DWORD *)v103 + 9) = *((_DWORD *)this + 64);
    v125 = v152;
    v152 = 0;
    *v142 = v125;
    (**(void (__fastcall ***)(struct ActionList *, int *, __int64))v46)(v46, v95, v96);
  }
}

```

## disassembly

```asm
0x180052d40  mov     rax, rsp
0x180052d43  push    rbp
0x180052d44  push    rsi
0x180052d45  push    rdi
0x180052d46  push    r12
0x180052d48  push    r13
0x180052d4a  push    r14
0x180052d4c  push    r15
0x180052d4e  lea     rbp, [rax-1B8h]
0x180052d55  sub     rsp, 280h
0x180052d5c  mov     [rbp+1B0h+var_1A0], 0FFFFFFFFFFFFFFFEh
0x180052d64  mov     [rax+20h], rbx
0x180052d68  mov     rax, cs:__security_cookie
0x180052d6f  xor     rax, rsp
0x180052d72  mov     [rbp+1B0h+var_40], rax
0x180052d79  mov     rsi, r8
0x180052d7c  mov     [rbp+1B0h+var_1F0], r8
0x180052d80  mov     [rbp+1B0h+var_210], rdx
0x180052d84  mov     rdi, rcx
0x180052d87  xor     r12d, r12d
0x180052d8a  mov     [rbp+1B0h+var_218], r12
0x180052d8e  mov     ebx, r12d
0x180052d91  mov     [rbp+1B0h+var_230], ebx
0x180052d94  mov     ecx, r12d
0x180052d97  mov     [rbp+1B0h+var_224], ecx
0x180052d9a  mov     [rbp+1B0h+var_208], ecx
0x180052d9d  mov     eax, r12d
0x180052da0  mov     [rbp+1B0h+var_220], eax
0x180052da3  mov     [rbp+1B0h+var_178], eax
0x180052da6  mov     [rbp+1B0h+var_1E0], r12d
0x180052daa  mov     [rbp+1B0h+var_1D0], r12d
0x180052dae  mov     [rbp+1B0h+var_1F8], r12d
0x180052db2  lea     r15d, [r12+1]
0x180052db7  mov     [rbp+1B0h+var_17C], r15d
0x180052dbb  mov     [rbp+1B0h+var_188], r12d
0x180052dbf  mov     [rbp+1B0h+var_170], r12d
0x180052dc3  mov     word ptr [rbp+1B0h+var_190+4], r12w
0x180052dc8  mov     [rbp+1B0h+var_150], r12
0x180052dcc  mov     [rbp+1B0h+var_160], r12
0x180052dd0  mov     [rbp+1B0h+var_148], r12
0x180052dd4  mov     [rbp+1B0h+var_158], r12
0x180052dd8  mov     [rbp+1B0h+var_168], r12
0x180052ddc  mov     [rbp+1B0h+var_140], r12
0x180052de0  mov     [rbp+1B0h+var_198], r12
0x180052de4  mov     [rbp+1B0h+var_180], r12d
0x180052de8  xor     edx, edx; Val
0x180052dea  lea     r8d, [r12+48h]; Size
0x180052def  lea     rcx, [rbp+1B0h+var_110]; void *
0x180052df6  call    memset_0
0x180052dfb  mov     [rbp+1B0h+var_184], r12d
0x180052dff  xor     edx, edx; Val
0x180052e01  lea     r8d, [r12+64h]; Size
0x180052e06  lea     rcx, [rbp+1B0h+szVolumeName]; void *
0x180052e0d  call    memset_0
0x180052e12  lea     eax, [r12+3Fh]
0x180052e17  mov     [rbp+1B0h+szVolumeMountPoint], ax
0x180052e1e  mov     eax, dword ptr cs:asc_1802DB8D8+2; ":\\"
0x180052e24  mov     [rbp+1B0h+var_BE], eax
0x180052e2a  movzx   eax, word ptr cs:asc_1802DB8D8+6; ""
0x180052e31  mov     [rbp+1B0h+var_BA], ax
0x180052e38  mov     rcx, [rbp+1B8h]; this
0x180052e3f  test    rsi, rsi
0x180052e42  jz      loc_180054231
0x180052e48  mov     r13d, r12d
0x180052e4b  mov     rcx, rdi; this
0x180052e4e  call    ?ExecuteMitigations@CDeploymentSession@@QEAAJXZ; CDeploymentSession::ExecuteMitigations(void)
0x180052e53  lea     esi, [r12+2]
0x180052e58  test    eax, eax
0x180052e5a  jns     short loc_180052E6C
0x180052e5c  lea     r8, aErrorExecuting; "Error executing mitigations"
0x180052e63  mov     edx, eax
0x180052e65  mov     ecx, esi
0x180052e67  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x180052e6c  mov     rcx, rdi; this
0x180052e6f  call    ?GetOneSettings@CDeploymentSession@@QEAAJXZ; CDeploymentSession::GetOneSettings(void)
0x180052e74  test    eax, eax
0x180052e76  jns     short loc_180052E88
0x180052e78  lea     r8, aErrorGettingOn_0; "Error getting OneSettings"
0x180052e7f  mov     edx, eax
0x180052e81  mov     ecx, esi
0x180052e83  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x180052e88  mov     dword ptr [rbp+1B0h+var_190], r12d
0x180052e8c  mov     [rbp+1B0h+var_22C], r12d
0x180052e90  mov     [rbp+1B0h+var_228], r12d
0x180052e94  lea     rcx, [rbp+1B0h+var_190]
0x180052e98  call    ?IsMoUpdateTestsEnabled@?$CMoUpdateHelpersT@VCEmptyType@@@@SAJPEAH@Z; CMoUpdateHelpersT<CEmptyType>::IsMoUpdateTestsEnabled(int *)
0x180052e9d  mov     esi, eax
0x180052e9f  test    eax, eax
0x180052ea1  jns     short loc_180052EAC
0x180052ea3  mov     ecx, eax
0x180052ea5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180052eaa  jmp     short loc_180052F00
0x180052eac  mov     r14d, r12d
0x180052eaf  cmp     dword ptr [rbp+1B0h+var_190], r12d
0x180052eb3  jz      short loc_180052EFD
0x180052eb5  lea     r9, [rbp+1B0h+var_22C]
0x180052eb9  lea     r8, aArbiterunittes; "ArbiterUnitTest"
0x180052ec0  lea     rdx, aSystemSetupMos_0; "SYSTEM\\Setup\\MoSetup"
0x180052ec7  call    ?ValueExists@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEB_W1PEAH@Z; CRegUtilT<ulong,CRegType,0,1>::ValueExists(HKEY__ *,wchar_t const *,wchar_t const *,int *)
0x180052ecc  mov     esi, eax
0x180052ece  test    eax, eax
0x180052ed0  js      short loc_180052EA3
0x180052ed2  cmp     [rbp+1B0h+var_22C], r12d
0x180052ed6  jz      short loc_180052EFD
0x180052ed8  lea     r9, [rbp+1B0h+var_228]
0x180052edc  lea     r8, aArbiterunittes; "ArbiterUnitTest"
0x180052ee3  lea     rdx, aSystemSetupMos_0; "SYSTEM\\Setup\\MoSetup"
0x180052eea  call    ?GetValue@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEB_W1PEAK@Z; CRegUtilT<ulong,CRegType,0,1>::GetValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong *)
0x180052eef  mov     esi, eax
0x180052ef1  test    eax, eax
0x180052ef3  js      short loc_180052EA3
0x180052ef5  cmp     [rbp+1B0h+var_228], r12d
0x180052ef9  setnz   r14b
0x180052efd  mov     r13d, r14d
0x180052f00  mov     ecx, esi
0x180052f02  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180052f07  mov     rcx, [rbp+1B8h]; this
0x180052f0e  test    esi, esi
0x180052f10  js      loc_180054249
0x180052f16  mov     [rbp+1B0h+var_1E8], r12d
0x180052f1a  mov     [rbp+1B0h+var_228], r12d
0x180052f1e  mov     [rbp+1B0h+var_22C], r12d
0x180052f22  mov     dword ptr [rbp+1B0h+var_190], r12d
0x180052f26  lea     rcx, [rbp+1B0h+var_228]
0x180052f2a  call    ?IsMoUpdateTestsEnabled@?$CMoUpdateHelpersT@VCEmptyType@@@@SAJPEAH@Z; CMoUpdateHelpersT<CEmptyType>::IsMoUpdateTestsEnabled(int *)
0x180052f2f  mov     esi, eax
0x180052f31  test    eax, eax
0x180052f33  jns     short loc_180052F3E
0x180052f35  mov     ecx, eax
0x180052f37  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180052f3c  jmp     short loc_180052F93
0x180052f3e  mov     r14d, r12d
0x180052f41  cmp     [rbp+1B0h+var_228], r12d
0x180052f45  jz      short loc_180052F8F
0x180052f47  lea     r9, [rbp+1B0h+var_22C]
0x180052f4b  lea     r8, aSkipexpressdis; "SkipExpressDiskspaceCheck"
0x180052f52  lea     rdx, aSystemSetupMos_0; "SYSTEM\\Setup\\MoSetup"
0x180052f59  call    ?ValueExists@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEB_W1PEAH@Z; CRegUtilT<ulong,CRegType,0,1>::ValueExists(HKEY__ *,wchar_t const *,wchar_t const *,int *)
0x180052f5e  mov     esi, eax
0x180052f60  test    eax, eax
0x180052f62  js      short loc_180052F35
0x180052f64  cmp     [rbp+1B0h+var_22C], r12d
0x180052f68  jz      short loc_180052F8F
0x180052f6a  lea     r9, [rbp+1B0h+var_190]
0x180052f6e  lea     r8, aSkipexpressdis; "SkipExpressDiskspaceCheck"
0x180052f75  lea     rdx, aSystemSetupMos_0; "SYSTEM\\Setup\\MoSetup"
0x180052f7c  call    ?GetValue@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEB_W1PEAK@Z; CRegUtilT<ulong,CRegType,0,1>::GetValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong *)
0x180052f81  mov     esi, eax
0x180052f83  test    eax, eax
0x180052f85  js      short loc_180052F35
0x180052f87  cmp     dword ptr [rbp+1B0h+var_190], r12d
0x180052f8b  setnz   r14b
0x180052f8f  mov     [rbp+1B0h+var_1E8], r14d
0x180052f93  mov     ecx, esi
0x180052f95  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180052f9a  mov     rcx, [rbp+1B8h]; this
0x180052fa1  test    esi, esi
0x180052fa3  js      loc_18005425E
0x180052fa9  lea     rdx, [rbp+1B0h+var_188]; int *
0x180052fad  mov     rcx, rdi; this
0x180052fb0  call    ?IsSkipPreDownloadCheck@CDeploymentSession@@QEAAJPEAH@Z; CDeploymentSession::IsSkipPreDownloadCheck(int *)
0x180052fb5  mov     rcx, [rbp+1B8h]; this
0x180052fbc  test    eax, eax
0x180052fbe  js      loc_180054273
0x180052fc4  xor     r14d, r14d
0x180052fc7  mov     [rbp+1B0h+var_228], r14d
0x180052fcb  mov     [rbp+1B0h+var_22C], r14d
0x180052fcf  lea     r9, [rbp+1B0h+var_228]
0x180052fd3  lea     r8, aUseservicingfo; "UseServicingForUpgrade"
0x180052fda  lea     rdx, aSystemSetupMos_0; "SYSTEM\\Setup\\MoSetup"
0x180052fe1  call    ?ValueExists@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEB_W1PEAH@Z; CRegUtilT<ulong,CRegType,0,1>::ValueExists(HKEY__ *,wchar_t const *,wchar_t const *,int *)
0x180052fe6  mov     esi, eax
0x180052fe8  test    eax, eax
0x180052fea  jns     short loc_180052FF5
0x180052fec  mov     ecx, eax
0x180052fee  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180052ff3  jmp     short loc_180053028
0x180052ff5  mov     eax, r14d
0x180052ff8  cmp     [rbp+1B0h+var_228], r14d
0x180052ffc  jz      short loc_180053025
0x180052ffe  lea     r9, [rbp+1B0h+var_22C]
0x180053002  lea     r8, aUseservicingfo; "UseServicingForUpgrade"
0x180053009  lea     rdx, aSystemSetupMos_0; "SYSTEM\\Setup\\MoSetup"
0x180053010  call    ?GetValue@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEB_W1PEAK@Z; CRegUtilT<ulong,CRegType,0,1>::GetValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong *)
0x180053015  mov     esi, eax
0x180053017  test    eax, eax
0x180053019  js      short loc_180052FEC
0x18005301b  mov     eax, r14d
0x18005301e  cmp     [rbp+1B0h+var_22C], r14d
0x180053022  setnz   al
0x180053025  mov     r12d, eax
0x180053028  mov     ecx, esi
0x18005302a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18005302f  mov     rcx, [rbp+1B8h]; this
0x180053036  test    esi, esi
0x180053038  js      loc_180054288
0x18005303e  mov     [rbp+1B0h+var_228], r14d
0x180053042  mov     [rbp+1B0h+var_22C], r14d
0x180053046  lea     r9, [rbp+1B0h+var_228]
0x18005304a  lea     r8, aUsesupplementa_0; "UseSupplementalCompDB"
0x180053051  lea     rdx, aSystemSetupMos_0; "SYSTEM\\Setup\\MoSetup"
0x180053058  call    ?ValueExists@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEB_W1PEAH@Z; CRegUtilT<ulong,CRegType,0,1>::ValueExists(HKEY__ *,wchar_t const *,wchar_t const *,int *)
0x18005305d  mov     esi, eax
0x18005305f  xor     ecx, ecx
0x180053061  test    eax, eax
0x180053063  jns     short loc_18005306E
0x180053065  mov     ecx, eax
0x180053067  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18005306c  jmp     short loc_18005309F
0x18005306e  mov     eax, ecx
0x180053070  cmp     [rbp+1B0h+var_228], ecx
0x180053073  jz      short loc_18005309C
0x180053075  lea     r9, [rbp+1B0h+var_22C]
0x180053079  lea     r8, aUsesupplementa_0; "UseSupplementalCompDB"
0x180053080  lea     rdx, aSystemSetupMos_0; "SYSTEM\\Setup\\MoSetup"
0x180053087  call    ?GetValue@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEB_W1PEAK@Z; CRegUtilT<ulong,CRegType,0,1>::GetValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong *)
0x18005308c  mov     esi, eax
0x18005308e  xor     ecx, ecx
0x180053090  test    eax, eax
0x180053092  js      short loc_180053065
0x180053094  mov     eax, ecx
0x180053096  cmp     [rbp+1B0h+var_22C], ecx
0x180053099  setnz   al
0x18005309c  mov     r14d, eax
0x18005309f  mov     ecx, esi
0x1800530a1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800530a6  mov     rcx, [rbp+1B8h]; this
0x1800530ad  test    esi, esi
0x1800530af  js      loc_18005429D
0x1800530b5  mov     rdx, [rdi+230h]
0x1800530bc  lea     rcx, [rbp+1B0h+var_180]
0x1800530c0  call    ?IsHostOSMobile@?$CMoUpdateHelpersT@VCEmptyType@@@@SAJPEAHPEB_W@Z; CMoUpdateHelpersT<CEmptyType>::IsHostOSMobile(int *,wchar_t const *)
0x1800530c5  mov     rcx, [rbp+1B8h]; this
0x1800530cc  test    eax, eax
0x1800530ce  js      loc_1800542B2
0x1800530d4  cmp     [rbp+1B0h+var_180], 0
0x1800530d8  jnz     loc_180053273
0x1800530de  mov     rcx, [rdi+1F8h]; lpFileName
0x1800530e5  call    cs:__imp_GetFileAttributesW
0x1800530ec  nop     dword ptr [rax+rax+00h]
0x1800530f1  mov     esi, eax
0x1800530f3  cmp     eax, 0FFFFFFFFh
0x1800530f6  jz      short loc_180053102
0x1800530f8  shr     esi, 4
0x1800530fb  not     esi
0x1800530fd  and     esi, r15d
0x180053100  jmp     short loc_180053104
0x180053102  xor     esi, esi
0x180053104  xor     ecx, ecx
0x180053106  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18005310b  xor     ecx, ecx
0x18005310d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180053112  lea     r8, [rbp+1B0h+var_178]; enum MoUpdateRangeRequestState *
0x180053116  lea     rdx, [rbp+1B0h+var_208]; int *
0x18005311a  mov     rcx, rdi; this
0x18005311d  call    ?IsRangeRequestSupported@CDeploymentSession@@QEAAJPEAHPEAW4MoUpdateRangeRequestState@@@Z; CDeploymentSession::IsRangeRequestSupported(int *,MoUpdateRangeRequestState *)
0x180053122  mov     [rbp+1B0h+var_180], eax
0x180053125  xor     r8d, r8d
0x180053128  test    eax, eax
0x18005312a  jns     short loc_180053169
0x18005312c  lea     rax, [rbp+1B0h+var_180]
0x180053130  mov     qword ptr [rbp+1B0h+var_208], rax
0x180053134  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005313b  test    rcx, rcx
0x18005313e  jz      short loc_180053161
0x180053140  lea     rax, [rbp+1B0h+var_208]
0x180053144  mov     [rsp+2B0h+var_290], rax
0x180053149  lea     r9, aIsrangerequest_1; "IsRangeRequestSupported failed with: [{"...
0x180053150  mov     r8d, 3
0x180053156  mov     dl, r15b
0x180053159  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005315e  xor     r8d, r8d
0x180053161  mov     eax, r8d
0x180053164  mov     [rbp+1B0h+var_224], eax
0x180053167  jmp     short loc_18005319D
0x180053169  lea     rax, aTrue_3; "TRUE"
0x180053170  lea     rdx, aFalse_2; "FALSE"
0x180053177  mov     ecx, [rbp+1B0h+var_208]
0x18005317a  mov     [rbp+1B0h+var_224], ecx
0x18005317d  test    ecx, ecx
0x18005317f  cmovz   rax, rdx
0x180053183  mov     qword ptr [rbp+1B0h+var_208], rax
0x180053187  lea     rdx, [rbp+1B0h+var_208]
0x18005318b  lea     rcx, aRangeRequestSu_0; "Range Request Supported: [{}]"
0x180053192  call    ??$TraceInfo@PEB_W@LogAdapter@@YAXQEBDAEBQEB_W@Z; LogAdapter::TraceInfo<wchar_t const *>(char const * const,wchar_t const * const &)
0x180053197  mov     eax, [rbp+1B0h+var_224]
0x18005319a  xor     r8d, r8d
0x18005319d  mov     [rdi+0D8h], eax
0x1800531a3  test    eax, eax
0x1800531a5  jz      short loc_1800531C8
0x1800531a7  mov     ebx, 801h
0x1800531ac  mov     [rbp+1B0h+var_230], ebx
0x1800531af  test    esi, esi
0x1800531b1  jz      short loc_180053203
0x1800531b3  lea     rcx, aPrevActionlist; "Prev ActionList already exits."
0x1800531ba  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x1800531bf  mov     [rbp+1B0h+var_220], 5
0x1800531c6  jmp     short loc_180053209
0x1800531c8  test    esi, esi
0x1800531ca  jz      short loc_180053203
  ... truncated ...
```
