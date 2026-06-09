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
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // esi
  int v15; // r14d
  __int64 v16; // rcx
  int Value; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // esi
  int v21; // r14d
  __int64 v22; // rcx
  int v23; // eax
  BOOL v24; // r14d
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rcx
  int v28; // esi
  BOOL v29; // eax
  int v30; // eax
  __int64 v31; // rdx
  int v32; // esi
  BOOL v33; // eax
  int IsHostOSMobile; // eax
  DWORD FileAttributesW; // esi
  BOOL v36; // esi
  __int64 v37; // rdx
  int v38; // eax
  const wchar_t *v39; // rax
  const char *v40; // r9
  const char *v41; // rcx
  int v42; // esi
  int *v43; // rax
  int v44; // r14d
  __int64 v45; // rdx
  int v46; // eax
  int v47; // eax
  int v48; // esi
  __int64 v49; // rdx
  struct ActionList *v50; // rsi
  int v51; // eax
  int v52; // eax
  const char *v53; // r9
  int v54; // eax
  int v55; // eax
  int v56; // ebx
  __int64 v57; // rdx
  int v58; // eax
  int v59; // eax
  int v60; // eax
  int ScenarioCtrl; // eax
  int v62; // ebx
  unsigned int v63; // eax
  CDeploymentDownloadRequest *v64; // rcx
  int v65; // eax
  int v66; // ebx
  __int64 v67; // rdx
  CDeploymentDownloadRequest *v68; // rax
  unsigned int v69; // eax
  int v70; // ebx
  char v71; // al
  int v72; // eax
  int IsInitialDownloadNeeded; // eax
  int *v74; // rdx
  int v75; // r14d
  unsigned int v76; // r12d
  int v77; // r13d
  int v78; // eax
  int v79; // eax
  int v80; // eax
  unsigned int v81; // eax
  int v82; // ecx
  unsigned int v83; // ebx
  int v84; // eax
  __int64 v85; // rbx
  HANDLE ProcessHeap; // rax
  int v87; // ecx
  int v88; // eax
  CDeploymentDownloadRequest *v89; // rdx
  CDeploymentDownloadRequest *v90; // rcx
  int v91; // eax
  CDeploymentDownloadRequest *v92; // rax
  CDeploymentDownloadRequest *v93; // rdx
  CDeploymentDownloadRequest *v94; // rcx
  int v95; // eax
  CDeploymentDownloadRequest *v96; // rcx
  int v97; // eax
  bool IsDownloadListEmpty; // al
  int *v99; // rdx
  __int64 v100; // r8
  CDeploymentDownloadRequest *v101; // rdx
  CDeploymentDownloadRequest *v102; // rcx
  int v103; // eax
  bool v104; // al
  int v105; // eax
  int v106; // ebx
  struct _ReportEventDownloadRequestParams *v107; // r12
  bool v108; // zf
  _DWORD *v109; // r15
  unsigned int v110; // eax
  int v111; // r14d
  int v112; // eax
  int v113; // eax
  __int64 v114; // rdx
  __int64 v115; // r12
  unsigned __int64 v116; // r15
  int v117; // r14d
  __int64 v118; // rdx
  unsigned __int64 v119; // r14
  int v120; // eax
  __int64 v121; // rax
  unsigned int v122; // ebx
  const char *v123; // r9
  _QWORD *v124; // r8
  int v125; // eax
  int v126; // ebx
  __int64 v127; // rdx
  int v128; // eax
  const char *v129; // r9
  int v130; // eax
  CDeploymentDownloadRequest *v131; // rax
  struct ActionList *v132; // [rsp+28h] [rbp-E0h]
  int *v133; // [rsp+28h] [rbp-E0h]
  int v134; // [rsp+28h] [rbp-E0h]
  int *v135; // [rsp+28h] [rbp-E0h]
  int v136; // [rsp+28h] [rbp-E0h]
  int v137; // [rsp+88h] [rbp-80h] BYREF
  int v138; // [rsp+8Ch] [rbp-7Ch] BYREF
  int v139; // [rsp+90h] [rbp-78h] BYREF
  int v140; // [rsp+94h] [rbp-74h]
  int v141; // [rsp+98h] [rbp-70h]
  struct ActionList *v142; // [rsp+A0h] [rbp-68h] BYREF
  struct _ReportEventDownloadRequestParams *v143; // [rsp+A8h] [rbp-60h] BYREF
  int v144[2]; // [rsp+B0h] [rbp-58h] BYREF
  int v145; // [rsp+B8h] [rbp-50h] BYREF
  char v146; // [rsp+BCh] [rbp-4Ch] BYREF
  int v147[2]; // [rsp+C0h] [rbp-48h] BYREF
  struct IDeploymentDownloadRequest **v148; // [rsp+C8h] [rbp-40h]
  int v149[2]; // [rsp+D0h] [rbp-38h] BYREF
  int v150[4]; // [rsp+D8h] [rbp-30h] BYREF
  int v151[2]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v152; // [rsp+F0h] [rbp-18h]
  void **v153; // [rsp+F8h] [rbp-10h]
  char *v154; // [rsp+100h] [rbp-8h]
  __int64 v155; // [rsp+108h] [rbp+0h]
  __int64 v156; // [rsp+110h] [rbp+8h]
  __int64 v157; // [rsp+118h] [rbp+10h]
  CDeploymentDownloadRequest *v158; // [rsp+120h] [rbp+18h] BYREF
  int v159; // [rsp+128h] [rbp+20h] BYREF
  wchar_t v160; // [rsp+12Ch] [rbp+24h] BYREF
  int v161; // [rsp+130h] [rbp+28h] BYREF
  int v162; // [rsp+134h] [rbp+2Ch] BYREF
  int IsRangeRequestSupported; // [rsp+138h] [rbp+30h] BYREF
  int v164; // [rsp+13Ch] [rbp+34h] BYREF
  int v165[2]; // [rsp+140h] [rbp+38h] BYREF
  int v166; // [rsp+148h] [rbp+40h] BYREF
  unsigned __int64 v167; // [rsp+150h] [rbp+48h] BYREF
  unsigned __int64 v168; // [rsp+158h] [rbp+50h] BYREF
  unsigned __int64 v169; // [rsp+160h] [rbp+58h] BYREF
  unsigned __int64 v170; // [rsp+168h] [rbp+60h] BYREF
  unsigned __int64 v171; // [rsp+170h] [rbp+68h] BYREF
  unsigned __int64 v172; // [rsp+178h] [rbp+70h] BYREF
  _QWORD v173[4]; // [rsp+180h] [rbp+78h] BYREF
  char v174; // [rsp+1A0h] [rbp+98h]
  _BYTE v175[80]; // [rsp+1A8h] [rbp+A0h] BYREF
  WCHAR szVolumeMountPoint[8]; // [rsp+1F8h] [rbp+F0h] BYREF
  WCHAR szVolumeName[56]; // [rsp+208h] [rbp+100h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C0h] [rbp+1B8h]

  v157 = -2;
  v148 = a3;
  v143 = a2;
  v5 = 0;
  v142 = 0;
  v6 = 0;
  v137 = 0;
  v140 = 0;
  v144[0] = 0;
  v141 = 0;
  v165[0] = 0;
  v150[0] = 0;
  v151[0] = 0;
  v147[0] = 0;
  v7 = 1;
  v164 = 1;
  v161 = 0;
  v166 = 0;
  v160 = 0;
  v170 = 0;
  v168 = 0;
  v171 = 0;
  v169 = 0;
  v167 = 0;
  v172 = 0;
  v158 = 0;
  IsRangeRequestSupported = 0;
  memset_0(v175, 0, 0x48u);
  v162 = 0;
  memset_0(szVolumeName, 0, 0x64u);
  wcscpy(szVolumeMountPoint, L"?:\\");
  if ( !a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C60,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)0x80004003LL,
      (int)v132);
  v8 = 0;
  v9 = CDeploymentSession::ExecuteMitigations(this);
  if ( v9 < 0 )
    LogAdapter::TraceAtLevelHr<long,>(2, (unsigned int)v9, "Error executing mitigations");
  OneSettings = CDeploymentSession::GetOneSettings(this);
  if ( OneSettings < 0 )
    LogAdapter::TraceAtLevelHr<long,>(2, (unsigned int)OneSettings, "Error getting OneSettings");
  v159 = 0;
  v138 = 0;
  v139 = 0;
  IsMoUpdateTestsEnabled = CMoUpdateHelpersT<CEmptyType>::IsMoUpdateTestsEnabled(&v159);
  v14 = IsMoUpdateTestsEnabled;
  if ( IsMoUpdateTestsEnabled < 0 )
    goto LABEL_7;
  v15 = 0;
  if ( v159 )
  {
    IsMoUpdateTestsEnabled = CRegUtilT<unsigned long,CRegType,0,1>::ValueExists(
                               v13,
                               L"SYSTEM\\Setup\\MoSetup",
                               L"ArbiterUnitTest",
                               &v138);
    v14 = IsMoUpdateTestsEnabled;
    if ( IsMoUpdateTestsEnabled < 0 )
      goto LABEL_7;
    if ( v138 )
    {
      IsMoUpdateTestsEnabled = CRegUtilT<unsigned long,CRegType,0,1>::GetValue(
                                 v16,
                                 L"SYSTEM\\Setup\\MoSetup",
                                 L"ArbiterUnitTest",
                                 &v139);
      v14 = IsMoUpdateTestsEnabled;
      if ( IsMoUpdateTestsEnabled >= 0 )
      {
        LOBYTE(v15) = v139 != 0;
        goto LABEL_13;
      }
LABEL_7:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)IsMoUpdateTestsEnabled, v12);
      goto LABEL_14;
    }
  }
LABEL_13:
  v8 = v15;
LABEL_14:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v14);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C6C,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)v14,
      (int)v132);
  v149[0] = 0;
  v139 = 0;
  v138 = 0;
  v159 = 0;
  Value = CMoUpdateHelpersT<CEmptyType>::IsMoUpdateTestsEnabled(&v139);
  v20 = Value;
  if ( Value < 0 )
    goto LABEL_16;
  v21 = 0;
  if ( v139 )
  {
    Value = CRegUtilT<unsigned long,CRegType,0,1>::ValueExists(
              v19,
              L"SYSTEM\\Setup\\MoSetup",
              L"SkipExpressDiskspaceCheck",
              &v138);
    v20 = Value;
    if ( Value < 0 )
      goto LABEL_16;
    if ( v138 )
    {
      Value = CRegUtilT<unsigned long,CRegType,0,1>::GetValue(
                v22,
                L"SYSTEM\\Setup\\MoSetup",
                L"SkipExpressDiskspaceCheck",
                &v159);
      v20 = Value;
      if ( Value >= 0 )
      {
        LOBYTE(v21) = v159 != 0;
        goto LABEL_22;
      }
LABEL_16:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Value, v18);
      goto LABEL_23;
    }
  }
LABEL_22:
  v149[0] = v21;
LABEL_23:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v20);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C6D,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)v20,
      (int)v132);
  v23 = CDeploymentSession::IsSkipPreDownloadCheck(this, &v161);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C6E,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)v23,
      (int)v132);
  v24 = 0;
  v139 = 0;
  v138 = 0;
  v25 = CRegUtilT<unsigned long,CRegType,0,1>::ValueExists(
          retaddr,
          L"SYSTEM\\Setup\\MoSetup",
          L"UseServicingForUpgrade",
          &v139);
  v28 = v25;
  if ( v25 < 0 )
    goto LABEL_26;
  v29 = 0;
  if ( v139 )
  {
    v25 = CRegUtilT<unsigned long,CRegType,0,1>::GetValue(
            v27,
            L"SYSTEM\\Setup\\MoSetup",
            L"UseServicingForUpgrade",
            &v138);
    v28 = v25;
    if ( v25 < 0 )
    {
LABEL_26:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v25, v26);
      goto LABEL_31;
    }
    v29 = v138 != 0;
  }
  v5 = v29;
LABEL_31:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v28);
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C6F,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)v28,
      (int)v132);
  v139 = 0;
  v138 = 0;
  v30 = CRegUtilT<unsigned long,CRegType,0,1>::ValueExists(
          retaddr,
          L"SYSTEM\\Setup\\MoSetup",
          L"UseSupplementalCompDB",
          &v139);
  v32 = v30;
  if ( v30 < 0 )
    goto LABEL_33;
  v33 = 0;
  if ( v139 )
  {
    v30 = CRegUtilT<unsigned long,CRegType,0,1>::GetValue(0, L"SYSTEM\\Setup\\MoSetup", L"UseSupplementalCompDB", &v138);
    v32 = v30;
    if ( v30 < 0 )
    {
LABEL_33:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v30, v31);
      goto LABEL_38;
    }
    v33 = v138 != 0;
  }
  v24 = v33;
LABEL_38:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v32);
  if ( v32 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C70,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)v32,
      (int)v132);
  IsHostOSMobile = CMoUpdateHelpersT<CEmptyType>::IsHostOSMobile(&IsRangeRequestSupported, *((_QWORD *)this + 70));
  if ( IsHostOSMobile < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C75,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)IsHostOSMobile,
      (int)v132);
  if ( IsRangeRequestSupported )
    goto LABEL_67;
  FileAttributesW = GetFileAttributesW(*((LPCWSTR *)this + 63));
  v36 = FileAttributesW != -1 && ((FileAttributesW >> 4) & 1) == 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  IsRangeRequestSupported = CDeploymentSession::IsRangeRequestSupported(
                              this,
                              v144,
                              (enum MoUpdateRangeRequestState *)v165);
  if ( IsRangeRequestSupported >= 0 )
  {
    v39 = L"TRUE";
    v140 = v144[0];
    if ( !v144[0] )
      v39 = L"FALSE";
    *(_QWORD *)v144 = v39;
    LogAdapter::TraceInfo<wchar_t const *>("Range Request Supported: [{}]", v144);
    v38 = v140;
  }
  else
  {
    *(_QWORD *)v144 = &IsRangeRequestSupported;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      v132 = (struct ActionList *)v144;
      LOBYTE(v37) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v37,
        3,
        "IsRangeRequestSupported failed with: [{}]. Setting RangeRequestSupported to FALSE ");
    }
    v38 = 0;
    v140 = 0;
  }
  *((_DWORD *)this + 54) = v38;
  if ( v38 )
  {
    v6 = 2049;
    v137 = 2049;
    if ( v36 )
    {
      LogAdapter::TraceInfo<>("Prev ActionList already exits.");
      v141 = 5;
      goto LABEL_58;
    }
  }
  else if ( v36 )
  {
    if ( *((_DWORD *)this + 61) )
    {
      LogAdapter::TraceInfo<>("Deleting prev ActionList since it contained Express packages.");
      if ( !DeleteFileW(*((LPCWSTR *)this + 63)) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x1C98,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          v40);
    }
  }
  v141 = v165[0];
LABEL_58:
  if ( *((_BYTE *)this + 328) || v5 )
  {
    v6 |= 0x40u;
    v137 = v6;
    v41 = "Using servicing for upgrade.";
  }
  else
  {
    v41 = "Not using servicing for upgrade.";
  }
  LogAdapter::TraceInfo<>(v41);
  if ( *((_DWORD *)this + 75) || v24 )
  {
    v6 |= 0x20u;
    v137 = v6;
    LogAdapter::TraceInfo<>("Using Supplemental compdb for upgrade.");
  }
  if ( *((_DWORD *)this + 76) )
  {
    v6 |= 0x400u;
    v137 = v6;
    LogAdapter::TraceInfo<>("Enabling trimming unused language packs.");
  }
LABEL_67:
  if ( v8 )
  {
    v6 |= 4u;
    v137 = v6;
  }
  if ( (*((_BYTE *)this + 372) & 8) != 0 && *((_QWORD *)this + 71) )
  {
    LogAdapter::TraceInfo<>("Setting CreateActionList flag to GenerateDownloadsOnly.");
    v6 |= 0x80u;
    v137 = v6;
  }
  v42 = CDeploymentSession::CallCreateActionList(this, v6, &v142);
  v145 = -2146467824;
  v43 = &v145;
  do
  {
    if ( v42 == *v43 )
    {
      v44 = 0;
      goto LABEL_79;
    }
    ++v43;
  }
  while ( v43 != (int *)&v146 );
  v44 = v42;
  if ( v42 < 0 )
  {
    v165[0] = v42;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "CreateActionList failed. Error");
      *(_QWORD *)v144 = v165;
      v132 = (struct ActionList *)v144;
      LOBYTE(v45) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v45,
        3,
        ": {}");
    }
  }
LABEL_79:
  if ( v44 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CCD,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)v44,
      (int)v132);
  if ( v42 < 0 )
  {
    v46 = CDeploymentSession::AcquireMetadataFromCurrentOSUpdate(this, &v162);
    if ( v46 < 0 )
      LogAdapter::TraceAtLevelHr<long,>(2, (unsigned int)v46, "Failed to get current OS upgrade metadata. Error");
    if ( !v162 )
    {
      LogAdapter::TraceInfo<>("Could not find reverse-delta metadata.");
      v6 &= ~0x10u;
      v137 = v6;
      v141 = 9;
    }
    if ( v142 )
    {
      (**(void (__fastcall ***)(struct ActionList *))v142)(v142);
      v142 = 0;
    }
    v47 = CDeploymentSession::CallCreateActionList(this, v6, &v142);
    v48 = v47;
    if ( v47 < 0 )
    {
      v162 = v47;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "CreateActionList failed. Error");
        *(_QWORD *)v165 = &v162;
        v132 = (struct ActionList *)v165;
        LOBYTE(v49) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v49,
          3,
          ": {}");
      }
    }
    if ( v48 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CE3,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
        (const char *)(unsigned int)v48,
        (int)v132);
  }
  CDeploymentSession::CopyArbiterGeneratedFilesWithRegularActionList(this);
  v50 = v142;
  v51 = CDeploymentSession::DeterminePackageTypesPresence(this, v142);
  if ( v51 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CE8,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)v51,
      (int)v132);
  if ( !*((_QWORD *)this + 58) && !*((_DWORD *)this + 114) )
  {
    if ( *((_DWORD *)v50 + 13) != 2 || (v6 & 1) == 0 )
    {
LABEL_116:
      v59 = CDeploymentSession::SetScenarioFromActionList(this, *((unsigned int *)v50 + 13));
      if ( v59 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D22,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v59,
          (int)v132);
      v60 = CDeploymentSession::ExecuteMitigations(this);
      if ( v60 < 0 )
        LogAdapter::TraceAtLevelHr<long,>(2, (unsigned int)v60, "Error executing mitigations");
      ScenarioCtrl = CDeploymentSession::CreateScenarioCtrl(this);
      if ( ScenarioCtrl < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D2B,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)ScenarioCtrl,
          (int)v132);
      goto LABEL_120;
    }
    if ( *((_DWORD *)this + 72) )
    {
      LogAdapter::TraceInfo<>("Express disabled via forcing canonical packages.");
      v141 = 7;
    }
    else if ( *((_DWORD *)this + 90) > *((_DWORD *)this + 87) )
    {
      if ( v149[0] )
        goto LABEL_105;
      v52 = CDeploymentSession::CheckFreeDiskspaceForExpress(this, &v164);
      if ( v52 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D02,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v52,
          (int)v132);
      if ( v164 )
        goto LABEL_105;
      LogAdapter::TraceInfo<>("Not enough space for Express support.");
      v141 = 4;
    }
    else
    {
      LogAdapter::TraceInfo<>("Express disabled via download count.");
      v141 = 8;
    }
    v6 &= ~1u;
    v137 = v6;
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
          v53);
      v54 = CDeploymentSession::CleanExpressFolders(this);
      if ( v54 < 0 )
        LogAdapter::TraceAtLevelHr<long,>(1, (unsigned int)v54, "Cleaning express folders failed");
      (**(void (__fastcall ***)(struct ActionList *))v50)(v50);
      v142 = 0;
      v55 = CDeploymentSession::CallCreateActionList(this, v6, &v142);
      v56 = v55;
      if ( v55 < 0 )
      {
        v164 = v55;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "CreateActionList failed. Error");
          *(_QWORD *)v149 = &v164;
          v132 = (struct ActionList *)v149;
          LOBYTE(v57) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v57,
            3,
            ": {}");
        }
      }
      if ( v56 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D16,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v56,
          (int)v132);
      CDeploymentSession::CopyArbiterGeneratedFilesWithRegularActionList(this);
      v50 = v142;
      v58 = CDeploymentSession::DeterminePackageTypesPresence(this, v142);
      if ( v58 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D1A,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v58,
          (int)v132);
    }
    goto LABEL_116;
  }
LABEL_120:
  v62 = 20971544;
  if ( v50 )
  {
    if ( *((_DWORD *)v50 + 60) )
    {
      v63 = *((_DWORD *)this + 114);
      if ( v63 <= 0x18 )
      {
        if ( _bittest(&v62, v63) )
        {
          LogAdapter::TraceInfo<>("GenerateDownloadRequest: Compose payload required");
          *(_QWORD *)((char *)this + 236) = 1;
          *((_DWORD *)v143 + 33) = 1;
        }
      }
    }
  }
  if ( (*((_BYTE *)this + 740) & 1) != 0 )
  {
    LogAdapter::TraceInfo<>("GenerateDownloadRequest: Caller requested only for Predownload content");
    v64 = v158;
    v158 = 0;
    if ( v64 )
      (*(void (__fastcall **)(CDeploymentDownloadRequest *))(*(_QWORD *)v64 + 16LL))(v64);
    v65 = CDeploymentSession::Predownload(this, &v158);
    v66 = v65;
    if ( v65 < 0 )
    {
      v161 = v65;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Predownload failed. Error");
        v143 = (struct _ReportEventDownloadRequestParams *)&v161;
        v132 = (struct ActionList *)&v143;
        LOBYTE(v67) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v67,
          3,
          ": {}");
      }
    }
    if ( v66 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1D3D,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
        (const char *)(unsigned int)v66,
        (int)v132);
    v68 = v158;
    v158 = 0;
    *v148 = v68;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UpdateAgentWUSARebaseMultiMSU>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_UpdateAgentWUSARebaseMultiMSU>::GetImpl'::`2'::impl) )
    {
      if ( *((_DWORD *)v50 + 13)
        && (*((_DWORD *)v50 + 18)
         || *((_DWORD *)v50 + 24)
         || *((_DWORD *)v50 + 28)
         || *((_DWORD *)v50 + 32)
         || *((_DWORD *)v50 + 36)
         || *((_DWORD *)v50 + 56)) )
      {
        v7 = 0;
      }
      if ( v7 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D45,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)0xC1900401LL,
          (int)v132);
    }
    if ( v158 )
      (*(void (__fastcall **)(CDeploymentDownloadRequest *))(*(_QWORD *)v158 + 16LL))(v158);
    if ( v50 )
      (**(void (__fastcall ***)(struct ActionList *))v50)(v50);
    return;
  }
  if ( (*((_BYTE *)this + 372) & 0x20) != 0 && (v69 = *((_DWORD *)this + 114), v69 <= 0x18) && _bittest(&v62, v69) )
  {
    v70 = v140;
  }
  else
  {
    v70 = v140;
    if ( *((_DWORD *)this + 114) != 20 || v140 )
    {
      v71 = 0;
      goto LABEL_152;
    }
  }
  v71 = 1;
LABEL_152:
  *((_BYTE *)this + 329) = v71;
  v72 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 60) + 8LL))(*((_QWORD *)this + 60), 2);
  if ( v72 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D4F,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)v72,
      (int)v132);
  IsInitialDownloadNeeded = CDeploymentSession::IsInitialDownloadNeeded(this, v50, v70, v150, v151);
  if ( IsInitialDownloadNeeded < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D54,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)IsInitialDownloadNeeded,
      (int)v133);
  v75 = 0;
  v76 = 100;
  v77 = v150[0];
  if ( *((_BYTE *)this + 329) )
  {
    LogAdapter::TraceInfo<>("Requesting Download Full Payloads.");
  }
  else if ( v150[0] )
  {
    LogAdapter::TraceInfo<>("Requesting Initial Download Only.");
    v75 = 1;
    v76 = 1;
  }
  else
  {
    v78 = *((_DWORD *)this + 114);
    if ( v78 != 22 && v78 != 4 || !*((_BYTE *)this + 339) )
    {
      v79 = CDeploymentSession::HandleExpressMetadataPayload(this, &v142, (enum CreateActionListFlags *)&v137, v147);
      v159 = v79;
      if ( v79 < 0 )
      {
        *(_QWORD *)v150 = &v159;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          v133 = v150;
          LOBYTE(v74) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v74,
            3,
            "GenerateDownloadRequest: Failed with error [{}]");
          v79 = v159;
        }
        if ( CDeploymentSession::ShouldForceCanonical(this, v79) )
        {
          LogAdapter::TraceInfo<>("GenerateDownloadRequest: This error will force a canonical retry.");
          *((_DWORD *)this + 87) = *((_DWORD *)this + 90);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1D6F,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
            (const char *)0x8024200DLL,
            (int)v133);
        }
        if ( v159 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1D73,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
            (const char *)(unsigned int)v159,
            (int)v133);
      }
      *((_BYTE *)this + 339) = 1;
      v50 = v142;
    }
  }
  v80 = CDeploymentSession::CheckCancelRequested(this, v74);
  if ( v80 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D7B,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)v80,
      (int)v133);
  if ( v147[0] )
  {
    v81 = *((_DWORD *)this + 114);
    if ( v81 > 0x16 || (v82 = 4195440, v83 = 1, !_bittest(&v82, v81)) )
      v83 = 0;
    UpdateAgentMisc::ConvertWinDirToDefaultBootDir(v147, *((_QWORD *)this + 70));
    v133 = (int *)*((_QWORD *)this + 64);
    v84 = CProgressHandler::InitializeForExpander(*((_QWORD *)this + 60), 0, v50, v83);
    if ( v84 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1D8C,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
        (const char *)(unsigned int)v84,
        (int)v133);
    v85 = *(_QWORD *)v147;
    if ( *(_QWORD *)v147 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)(v85 - 4));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    }
    v70 = v140;
  }
  v87 = *((_DWORD *)v50 + 18);
  if ( !v87 )
  {
    v88 = *((_DWORD *)this + 114);
    if ( v88 == 1 )
    {
      if ( *((_DWORD *)v50 + 28) || *((_DWORD *)v50 + 36) || *((_DWORD *)v50 + 52) || *((_DWORD *)v50 + 56) )
        goto LABEL_187;
    }
    else if ( v88 == 2 )
    {
LABEL_187:
      LogAdapter::TraceInfo<>("GenerateDownloadRequest: Empty download list with some non-install action detected. Generating empty list.");
      v89 = v158;
      v90 = 0;
      v158 = 0;
      if ( v89 )
      {
        (*(void (__fastcall **)(CDeploymentDownloadRequest *))(*(_QWORD *)v89 + 16LL))(v89);
        v90 = v158;
      }
      v158 = 0;
      if ( v90 )
        (*(void (__fastcall **)(CDeploymentDownloadRequest *))(*(_QWORD *)v90 + 16LL))(v90);
      v91 = CDeploymentSession::GenerateEmptyDownloadList(this, *((const wchar_t **)this + 63), &v158);
      if ( v91 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D9B,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v91,
          (int)v133);
LABEL_192:
      v92 = v158;
      v158 = 0;
      *v148 = v92;
      (**(void (__fastcall ***)(struct ActionList *))v50)(v50);
      return;
    }
  }
  if ( *((_DWORD *)this + 81) )
    goto LABEL_187;
  if ( !v87 && (*((_DWORD *)v50 + 32) || *((_DWORD *)v50 + 36) || *((_DWORD *)v50 + 40)) )
  {
    LogAdapter::TraceInfo<>("GenerateDownloadRequest: Empty download list with some non-download action detected. Generating empty list.");
    v93 = v158;
    v94 = 0;
    v158 = 0;
    if ( v93 )
    {
      (*(void (__fastcall **)(CDeploymentDownloadRequest *))(*(_QWORD *)v93 + 16LL))(v93);
      v94 = v158;
    }
    v158 = 0;
    if ( v94 )
      (*(void (__fastcall **)(CDeploymentDownloadRequest *))(*(_QWORD *)v94 + 16LL))(v94);
    v95 = CDeploymentSession::GenerateEmptyDownloadList(this, *((const wchar_t **)this + 63), &v158);
    if ( v95 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1DA5,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
        (const char *)(unsigned int)v95,
        (int)v133);
    goto LABEL_192;
  }
  if ( *((_BYTE *)v50 + 48) && !v87 || *((_DWORD *)this + 114) == 21 )
  {
    LogAdapter::TraceInfo<>("Entered the scenario with plugins ");
    *((_DWORD *)this + 114) = 21;
    if ( v158 )
      (*(void (__fastcall **)(CDeploymentDownloadRequest *))(*(_QWORD *)v158 + 16LL))(v158);
    (**(void (__fastcall ***)(struct ActionList *))v50)(v50);
  }
  else
  {
    v96 = v158;
    v158 = 0;
    if ( v96 )
      (*(void (__fastcall **)(CDeploymentDownloadRequest *, _QWORD))(*(_QWORD *)v96 + 16LL))(v96, 0);
    v97 = CDeploymentSession::GenerateDownloadList(
            this,
            v50,
            v75,
            v70,
            0,
            *((unsigned __int8 *)this + 329),
            *((const wchar_t **)this + 66),
            v76,
            &v170,
            &v168,
            &v169,
            &v167,
            (struct _DUPackageInfo *)v175,
            v143,
            &v158);
    if ( v97 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1DC6,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
        (const char *)(unsigned int)v97,
        v134);
    IsDownloadListEmpty = CDeploymentSession::IsDownloadListEmpty(this, v158);
    v100 = 0;
    if ( IsDownloadListEmpty )
    {
      v101 = v158;
      v102 = 0;
      v158 = 0;
      if ( v101 )
      {
        (*(void (__fastcall **)(CDeploymentDownloadRequest *, CDeploymentDownloadRequest *, _QWORD))(*(_QWORD *)v101 + 16LL))(
          v101,
          v101,
          0);
        v102 = v158;
      }
      v158 = 0;
      if ( v102 )
        (*(void (__fastcall **)(CDeploymentDownloadRequest *, CDeploymentDownloadRequest *, _QWORD))(*(_QWORD *)v102 + 16LL))(
          v102,
          v101,
          0);
      v103 = CDeploymentSession::GenerateDownloadList(
               this,
               v50,
               v75,
               v70,
               1,
               *((unsigned __int8 *)this + 329),
               *((const wchar_t **)this + 66),
               v76,
               &v170,
               &v171,
               &v169,
               &v172,
               (struct _DUPackageInfo *)v175,
               v143,
               &v158);
      if ( v103 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DD9,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v103,
          v134);
      if ( v168 <= v171 )
        v168 = v171;
      if ( v167 <= v172 )
        v167 = v172;
      v104 = CDeploymentSession::IsDownloadListEmpty(this, v158);
      v100 = 0;
      if ( v104 )
      {
        v105 = CDeploymentSession::ReportDownloadInfo(this, v50);
        v100 = 0;
        if ( v105 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1DDE,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
            (const char *)(unsigned int)v105,
            v134);
      }
    }
    v106 = -2147024362;
    v107 = v143;
    v108 = (v151[0] | *((_DWORD *)v143 + 6)) == 0;
    *((_DWORD *)v143 + 6) |= v151[0];
    if ( !v108 )
    {
      v109 = (_DWORD *)((char *)this + 344);
      v110 = *((_DWORD *)this + 86);
      if ( v110 + 1 < v110 )
      {
        v111 = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v99);
      }
      else
      {
        *v109 = v110 + 1;
        v111 = 0;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v111);
      if ( v111 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DE5,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v111,
          v134);
      LogAdapter::TraceInfo<unsigned long>(
        "GenerateDownloadRequest: Number of times corrupt files are deleted: [{}]",
        (char *)this + 344);
      if ( *((_DWORD *)this + 89) <= *v109 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DE7,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)0xC1900403LL,
          v134);
    }
    v112 = *((_DWORD *)this + 114);
    if ( (v112 == 3 || v112 == 24) && !v77 && !*((_DWORD *)this + 55) && !v161 )
    {
      v113 = CDeploymentSession::CheckCancelRequested(this, v99);
      if ( v113 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DF2,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v113,
          v134);
      v115 = *((_QWORD *)this + 58);
      if ( !v115 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DF3,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)0x8000FFFFLL,
          v134);
      v116 = v169 + v167;
      if ( v169 + v167 < v169 )
      {
        v116 = 0;
        v117 = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v114);
      }
      else
      {
        v117 = 0;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v117);
      if ( v117 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DF6,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v117,
          v134);
      v119 = v170 + v168;
      if ( v170 + v168 < v170 )
      {
        v119 = 0;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v118);
      }
      else
      {
        v106 = 0;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v106);
      if ( v106 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DF7,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v106,
          v134);
      v156 = 0;
      v155 = 0;
      v154 = (char *)this + 400;
      v153 = &CDlpAutoLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable';
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 408));
      LODWORD(v155) = 1;
      v120 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 58) + 80LL))(*((_QWORD *)this + 58), &v166);
      if ( v120 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DFD,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v120,
          v134);
      *((_DWORD *)this + 50) = v166 & 1;
      v121 = *((_QWORD *)this + 61);
      if ( v121 )
        v122 = *(_DWORD *)(v121 - 4);
      else
        v122 = 0;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      if ( *(_WORD *)(*((_QWORD *)this + 61) + 2LL * v122) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xB6,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\stl.h",
          v123);
      *(_QWORD *)v151 = *((_QWORD *)this + 61);
      v152 = v122;
      CDeploymentSession::PrepareSetupDUDirectory(v122, v173, v50, v151);
      *((_DWORD *)this + 50) = 0;
      if ( v174 )
      {
        v124 = v173;
        if ( v173[3] > 7u )
          v124 = (_QWORD *)v173[0];
      }
      else
      {
        v124 = 0;
      }
      v135 = (int *)&v160;
      v125 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD *, _QWORD))(*(_QWORD *)v115 + 200LL))(
               v115,
               v116,
               v124,
               *((_QWORD *)this + 63));
      v126 = v125;
      if ( v125 < 0 )
      {
        v161 = v125;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Predownload exited. Error");
          *(_QWORD *)v151 = &v161;
          v135 = v151;
          LOBYTE(v127) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v127,
            3,
            ": {}");
        }
      }
      if ( v126 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1E09,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v126,
          (int)v135);
      if ( v174 )
        std::wstring::~wstring(v173);
      if ( (_DWORD)v155 )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 408));
        LODWORD(v155) = 0;
      }
      LogAdapter::TraceInfo<>("Pruning DU content...");
      v107 = v143;
      v128 = CDeploymentSession::PruneDownloadList(
               this,
               v119,
               v116,
               v160,
               v50,
               (struct _DUPackageInfo *)v175,
               v143,
               v158);
      if ( v128 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1E13,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v128,
          v136);
      LogAdapter::TraceInfo<>("Download Request pruned.");
      if ( v160 )
      {
        szVolumeMountPoint[0] = v160;
        memset_0(szVolumeName, 0, 0x64u);
        if ( !GetVolumeNameForVolumeMountPointW(szVolumeMountPoint, szVolumeName, 0x32u) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x1E1C,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
            v129);
        v143 = (struct _ReportEventDownloadRequestParams *)szVolumeName;
        LogAdapter::TraceInfo<wchar_t const *>("Setting Download volume as external drive [{}]", &v143);
        v130 = CDeploymentDownloadRequest::SetDownloadVolume(v158, szVolumeName);
        if ( v130 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1E1F,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
            (const char *)(unsigned int)v130,
            v136);
      }
      *((_DWORD *)this + 55) = 1;
    }
    if ( *((_DWORD *)this + 61) )
    {
      LogAdapter::TraceInfo<>("GenerateDownloadRequest: Expansion will be required");
      *((_DWORD *)this + 56) = 1;
    }
    *((_DWORD *)v107 + 5) = v141;
    *((_DWORD *)v107 + 7) = *((_DWORD *)this + 61);
    *((_DWORD *)v107 + 8) = *((_DWORD *)this + 62);
    *((_DWORD *)v107 + 9) = *((_DWORD *)this + 64);
    v131 = v158;
    v158 = 0;
    *v148 = v131;
    (**(void (__fastcall ***)(struct ActionList *, int *, __int64))v50)(v50, v99, v100);
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
