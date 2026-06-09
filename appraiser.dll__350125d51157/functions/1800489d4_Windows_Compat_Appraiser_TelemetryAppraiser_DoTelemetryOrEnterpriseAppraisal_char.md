# Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal(char *)

- ea: `0x1800489d4`
- end: `0x180049ea8`
- name: `?DoTelemetryOrEnterpriseAppraisal@TelemetryAppraiser@Appraiser@Compat@Windows@@SAJPEAD@Z`
- size: `5332`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `1`
- callee_count: `34`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014090`

## callees

- `0x18000147c`
- `0x180008570`
- `0x180011d94`
- `0x180013c7c`
- `0x180013f90`
- `0x1800144c4`
- `0x180014a34`
- `0x180014ac8`
- `0x180014be8`
- `0x1800151f4`
- `0x180029258`
- `0x18002a778`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180047acc`
- `0x180048504`
- `0x1800489d4`
- `0x18004ba00`
- `0x18004c2cc`
- `0x18004c83c`
- `0x18004dc14`
- `0x180051b54`
- `0x180052ae4`
- `0x1800670a4`
- `0x180067124`
- `0x180068908`
- `0x180068ce0`
- `0x180068d90`
- `0x18008a1ec`
- `0x18009282c`
- `0x1800952d8`
- `0x180095850`
- `0x18009b30c`
- `0x1801d8be8`

## import_xrefs

- `ntdll!WinSqmIsOptedInEx` at `0x180048f4f`
- `ntdll!WinSqmIsOptedInEx` at `0x180048ffd`
- `ntdll!WinSqmIsOptedInEx` at `0x180048f4f`
- `ntdll!WinSqmIsOptedInEx` at `0x180048ffd`
- `RPCRT4!UuidCreate` at `0x180048bf2`
- `RPCRT4!UuidCreate` at `0x180048bf2`
- `KERNEL32!GetSystemTime` at `0x180049387`
- `KERNEL32!GetSystemTime` at `0x180049502`
- `KERNEL32!GetSystemTime` at `0x1800496ca`
- `KERNEL32!GetSystemTime` at `0x18004985c`
- `KERNEL32!GetSystemTime` at `0x180049a9d`
- `KERNEL32!GetSystemTime` at `0x180049c3b`
- `KERNEL32!GetSystemTime` at `0x180049dc4`
- `KERNEL32!GetSystemTime` at `0x180049387`
- `KERNEL32!GetSystemTime` at `0x180049502`
- `KERNEL32!GetSystemTime` at `0x1800496ca`
- `KERNEL32!GetSystemTime` at `0x18004985c`
- `KERNEL32!GetSystemTime` at `0x180049a9d`
- `KERNEL32!GetSystemTime` at `0x180049c3b`
- `KERNEL32!GetSystemTime` at `0x180049dc4`
- `KERNEL32!CreateEventW` at `0x180048c06`
- `KERNEL32!CreateEventW` at `0x180048c06`
- `KERNEL32!GetProcessHeap` at `0x180048a55`
- `KERNEL32!GetProcessHeap` at `0x180048a9e`
- `KERNEL32!GetProcessHeap` at `0x180048b6d`
- `KERNEL32!GetProcessHeap` at `0x180048b93`
- `KERNEL32!GetProcessHeap` at `0x180048a55`
- `KERNEL32!GetProcessHeap` at `0x180048a9e`
- `KERNEL32!GetProcessHeap` at `0x180048b6d`
- `KERNEL32!GetProcessHeap` at `0x180048b93`
- `KERNEL32!CloseHandle` at `0x180048c28`
- `KERNEL32!CloseHandle` at `0x180049e63`
- `KERNEL32!CloseHandle` at `0x180048c28`
- `KERNEL32!CloseHandle` at `0x180049e63`
- `KERNEL32!GetLastError` at `0x180048c18`
- `KERNEL32!GetLastError` at `0x180048c18`
- `KERNEL32!HeapFree` at `0x180048c47`
- `KERNEL32!HeapFree` at `0x180049e82`
- `KERNEL32!HeapFree` at `0x180049e9c`
- `KERNEL32!HeapFree` at `0x180048c47`
- `KERNEL32!HeapFree` at `0x180049e82`
- `KERNEL32!HeapFree` at `0x180049e9c`

## string_xrefs

- `0x180048cda`: `Enterprise mode and indicator generation mode are incompatible in the same run.`
- `0x180048cf9`: `onecore\base\appcompat\appraiser\heads\telemetry\telemetryappraiser.cpp`
- `0x180048d45`: `onecore\base\appcompat\appraiser\heads\telemetry\telemetryappraiser.cpp`
- `0x180048cef`: `Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal`
- `0x180048d3e`: `Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal(char *a1)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 v4; // rdx
  __int64 v5; // r8
  HANDLE EventW; // rdi
  int appended; // ebx
  const unsigned __int16 *v9; // r15
  bool v10; // r13
  bool v11; // r12
  const unsigned __int16 *v12; // r8
  char v13; // dl
  const unsigned __int16 *v14; // r8
  const unsigned __int16 *v15; // r8
  bool v16; // r12
  int v17; // eax
  char v18; // dl
  int v19; // eax
  const char *v20; // r9
  char IsWin10TelemetryTypeAllowed; // al
  bool v22; // r8
  int v23; // eax
  char v24; // al
  int v25; // eax
  unsigned int DeviceFamily; // eax
  int v27; // eax
  int v28; // eax
  unsigned __int64 v29; // rdx
  int v30; // eax
  int v31; // r15d
  volatile signed __int64 *v32; // rcx
  void **v33; // rdx
  int v34; // r14d
  int v35; // r8d
  int v36; // r9d
  int v37; // eax
  int v38; // r15d
  volatile signed __int64 *v39; // rcx
  void **v40; // rdx
  int v41; // r14d
  int v42; // r8d
  int v43; // r9d
  int v44; // eax
  int v45; // r15d
  volatile signed __int64 *v46; // rcx
  void **v47; // rdx
  int v48; // r14d
  int v49; // r8d
  int v50; // r9d
  int v51; // eax
  int v52; // r15d
  volatile signed __int64 *v53; // rcx
  void **v54; // rdx
  int v55; // r14d
  int v56; // r8d
  int v57; // r9d
  int v58; // eax
  int v59; // eax
  int v60; // r15d
  volatile signed __int64 *v61; // rcx
  void **v62; // rdx
  int v63; // r14d
  int v64; // r8d
  int v65; // r9d
  int v66; // eax
  int v67; // r15d
  volatile signed __int64 *v68; // rcx
  void **v69; // rdx
  int v70; // r14d
  int v71; // r8d
  int v72; // r9d
  int v73; // eax
  int v74; // r15d
  volatile signed __int64 *v75; // rcx
  void **v76; // rdx
  int v77; // r14d
  int v78; // r8d
  int v79; // r9d
  struct RtlStringArray *v80; // [rsp+20h] [rbp-E0h]
  char *v81; // [rsp+28h] [rbp-D8h]
  char *v82; // [rsp+30h] [rbp-D0h]
  bool v83; // [rsp+60h] [rbp-A0h] BYREF
  int v84; // [rsp+64h] [rbp-9Ch] BYREF
  int v85; // [rsp+68h] [rbp-98h] BYREF
  bool v86; // [rsp+6Ch] [rbp-94h] BYREF
  bool v87; // [rsp+6Dh] [rbp-93h] BYREF
  bool v88; // [rsp+6Eh] [rbp-92h] BYREF
  char *v89; // [rsp+70h] [rbp-90h] BYREF
  const char *v90; // [rsp+78h] [rbp-88h] BYREF
  const char *v91; // [rsp+80h] [rbp-80h] BYREF
  const char *v92; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v93[2]; // [rsp+90h] [rbp-70h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE hHeap[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v96; // [rsp+C0h] [rbp-40h]
  LPVOID lpMem[2]; // [rsp+D0h] [rbp-30h]
  int v98; // [rsp+E0h] [rbp-20h]
  HANDLE v99[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v100; // [rsp+F8h] [rbp-8h]
  LPVOID v101[2]; // [rsp+108h] [rbp+8h]
  HANDLE hObject; // [rsp+118h] [rbp+18h]
  _BYTE v103[80]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v104[3]; // [rsp+170h] [rbp+70h] BYREF
  __int16 v105; // [rsp+188h] [rbp+88h]
  __int128 v106; // [rsp+190h] [rbp+90h]
  __int128 v107; // [rsp+1A0h] [rbp+A0h]
  __int128 v108; // [rsp+1B0h] [rbp+B0h]
  __int128 v109; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v110; // [rsp+1D0h] [rbp+D0h]
  __int128 v111; // [rsp+1E0h] [rbp+E0h]
  int v112; // [rsp+1F0h] [rbp+F0h]
  __int64 v113; // [rsp+1F8h] [rbp+F8h]
  __int64 v114; // [rsp+200h] [rbp+100h]
  __int64 v115; // [rsp+208h] [rbp+108h]
  int v116; // [rsp+210h] [rbp+110h]
  int v117; // [rsp+214h] [rbp+114h]
  int v118; // [rsp+218h] [rbp+118h]
  int v119; // [rsp+21Ch] [rbp+11Ch]
  _OWORD v120[3]; // [rsp+220h] [rbp+120h] BYREF
  __int64 v121; // [rsp+250h] [rbp+150h]
  __int64 v122; // [rsp+258h] [rbp+158h]
  _BYTE v123[656]; // [rsp+260h] [rbp+160h] BYREF
  struct _SYSTEMTIME v124; // [rsp+4F0h] [rbp+3F0h] BYREF
  __int64 v125; // [rsp+500h] [rbp+400h] BYREF
  char v126; // [rsp+508h] [rbp+408h]
  __int64 v127; // [rsp+510h] [rbp+410h]
  __int64 v128; // [rsp+518h] [rbp+418h]
  __int16 v129; // [rsp+520h] [rbp+420h]
  char v130; // [rsp+728h] [rbp+628h]
  char v131[144]; // [rsp+730h] [rbp+630h] BYREF
  unsigned __int16 v132[264]; // [rsp+7C0h] [rbp+6C0h] BYREF
  unsigned __int16 v133[264]; // [rsp+9D0h] [rbp+8D0h] BYREF
  unsigned __int16 v134[264]; // [rsp+BE0h] [rbp+AE0h] BYREF

  v122 = -2;
  v127 = 0;
  v128 = 0;
  v129 = 0;
  v125 = 0;
  v126 = 0;
  v130 = 0;
  v106 = 0;
  v107 = 0;
  v108 = 0;
  *(_QWORD *)&v106 = GetProcessHeap();
  v108 = 0x10u;
  v107 = 0;
  *((_QWORD *)&v106 + 1) = 8;
  v109 = 0;
  v110 = 0;
  v111 = 0;
  *(_QWORD *)&v109 = GetProcessHeap();
  v111 = 0x10u;
  v110 = 0;
  *((_QWORD *)&v109 + 1) = 16;
  v112 = 0;
  RtlArray<RtlStringArray::RTL_STRING_ITEM>::Initialize(&v109, v2, v3, 16);
  memset(v104, 0, sizeof(v104));
  v113 = 0;
  v115 = -1;
  v114 = 0;
  v105 = 1;
  v116 = 0;
  v117 = 1024;
  v118 = 64;
  v119 = 84;
  v83 = 0;
  v87 = 0;
  v86 = 0;
  v88 = 0;
  Windows::Compat::Appraiser::DataFile::DataFile((Windows::Compat::Appraiser::DataFile *)v123);
  Windows::Compat::Appraiser::PropertyBag::PropertyBag((Windows::Compat::Appraiser::PropertyBag *)v103);
  *(_OWORD *)v101 = 0;
  v99[0] = GetProcessHeap();
  v101[0] = (LPVOID)16;
  v100 = 0;
  v101[1] = 0;
  v99[1] = (HANDLE)8;
  hHeap[0] = GetProcessHeap();
  lpMem[0] = (LPVOID)16;
  v96 = 0;
  lpMem[1] = 0;
  hHeap[1] = (HANDLE)16;
  v98 = 0;
  RtlArray<RtlStringArray::RTL_STRING_ITEM>::Initialize(hHeap, v4, v5, 16);
  memset(v120, 0, sizeof(v120));
  v121 = 0;
  Windows::Compat::Appraiser::WicaFactory::SyncId = 0;
  UuidCreate(&Windows::Compat::Appraiser::WicaFactory::SyncId);
  EventW = CreateEventW(0, 0, 0, L"Global\\AppraiserExclusiveEvent");
  hObject = EventW;
  if ( !EventW )
    goto LABEL_4;
  if ( GetLastError() == 183 )
  {
    CloseHandle(EventW);
LABEL_4:
    RtlStringArray::Clear((RtlStringArray *)hHeap);
    if ( lpMem[1] )
      HeapFree(hHeap[0], 0, lpMem[1]);
    appended = -2147024863;
    goto LABEL_7;
  }
  Windows::Compat::Appraiser::TelemetryAppraiser::ParseCommandLine(
    &v83,
    &v87,
    &v86,
    &v88,
    (struct RtlStringArray *)hHeap,
    a1);
  v9 = L"TRUE";
  v10 = v86;
  v11 = v83;
  if ( !v83 )
  {
    v12 = L"FALSE";
LABEL_13:
    appended = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
                 (Windows::Compat::Appraiser::PropertyBag *)v103,
                 L"EnterpriseForceSync",
                 v12);
    if ( appended < 0 )
    {
      v13 = 76;
LABEL_15:
      LODWORD(v82) = appended;
      LODWORD(v80) = appended;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v13,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
        "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
        (const char *)v80,
        (int)"Error adding init property to bag: [0x%x].",
        v82);
      goto LABEL_90;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x4Cu,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
        "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
        "Error adding init property to bag: [0x%x].",
        appended);
    v14 = L"TRUE";
    if ( !v87 )
      v14 = L"FALSE";
    appended = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
                 (Windows::Compat::Appraiser::PropertyBag *)v103,
                 L"EnterpriseForceSyncActuallyForced",
                 v14);
    if ( appended < 0 )
    {
      v13 = 79;
      goto LABEL_15;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x4Fu,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
        "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
        "Error adding init property to bag: [0x%x].",
        appended);
    BYTE4(v120[0]) = v11;
    v15 = L"TRUE";
    v16 = v88;
    if ( !v88 )
      v15 = L"FALSE";
    v17 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
            (Windows::Compat::Appraiser::PropertyBag *)v103,
            L"ExpressMode",
            v15);
    appended = v17;
    if ( v17 >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x54u,
          "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
          "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
          "Error adding init property to bag: [0x%x].",
          v17);
      HIBYTE(v120[0]) = v16;
      if ( v16 )
        Windows::Compat::Appraiser::AppraiserSettings::FeatureType = 2;
      if ( !v10 )
        v9 = L"FALSE";
      v19 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
              (Windows::Compat::Appraiser::PropertyBag *)v103,
              L"OptimizeForIndicatorGen",
              v9);
      appended = v19;
      if ( v19 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x5Eu,
            "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
            "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
            "Error adding init property to bag: [0x%x].",
            v19);
        appended = Windows::Compat::Appraiser::TelemetryAppraiser::AppendArbitraryCommandLineProperties(
                     (struct Windows::Compat::Appraiser::PropertyBag *)v103,
                     (struct RtlStringArray *)hHeap);
        if ( appended >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x61u,
              "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
              "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
              "Error adding init properties to bag: [0x%x].",
              appended);
          if ( `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore'::`2'::AlreadyChecked )
          {
            IsWin10TelemetryTypeAllowed = `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore'::`2'::IsOptedIn;
          }
          else
          {
            if ( IsWindowsVersionOrGreater(0xAu, 0, 0) )
              IsWin10TelemetryTypeAllowed = Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(1u);
            else
              IsWin10TelemetryTypeAllowed = (unsigned int)WinSqmIsOptedInEx(4) == 1;
            `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore'::`2'::IsOptedIn = IsWin10TelemetryTypeAllowed;
            `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore'::`2'::AlreadyChecked = 1;
          }
          v22 = IsWin10TelemetryTypeAllowed
             || Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial(0);
          v23 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
                  (Windows::Compat::Appraiser::PropertyBag *)v103,
                  L"MachineOptedInToCoreTelemetry",
                  v22);
          appended = v23;
          if ( v23 < 0 )
          {
            LODWORD(v82) = v23;
            v81 = "Error adding init property to bag: [0x%x].";
            v18 = 100;
            goto LABEL_89;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x64u,
              "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
              "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
              "Error adding init property to bag: [0x%x].",
              v23);
          if ( `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoGeneral'::`2'::AlreadyChecked )
          {
            v24 = `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoGeneral'::`2'::IsOptedIn;
          }
          else
          {
            if ( IsWindowsVersionOrGreater(0xAu, 0, 0) )
              v24 = Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(2u);
            else
              v24 = (unsigned int)WinSqmIsOptedInEx(4) == 1;
            `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoGeneral'::`2'::IsOptedIn = v24;
            `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoGeneral'::`2'::AlreadyChecked = 1;
          }
          v25 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
                  (Windows::Compat::Appraiser::PropertyBag *)v103,
                  L"MachineOptedInToGeneralTelemetry",
                  v24);
          appended = v25;
          if ( v25 < 0 )
          {
            LODWORD(v82) = v25;
            v81 = "Error adding init property to bag: [0x%x].";
            v18 = 103;
            goto LABEL_89;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x67u,
              "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
              "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
              "Error adding init property to bag: [0x%x].",
              v25);
          DeviceFamily = Windows::Compat::Appraiser::Utilities::GetDeviceFamily();
          appended = StringCchPrintfW(v133, 0x104u, L"0x%08X", DeviceFamily);
          if ( appended >= 0 )
          {
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x6Au,
                "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
                "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
                "Error printing value: [0x%x].",
                appended);
            v27 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
                    (Windows::Compat::Appraiser::PropertyBag *)v103,
                    L"HostOsFamily",
                    v133);
            appended = v27;
            if ( v27 < 0 )
            {
              LODWORD(v82) = v27;
              v81 = "Error adding init property to bag: [0x%x].";
              v18 = 109;
              goto LABEL_89;
            }
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x6Du,
                "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
                "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
                "Error adding init property to bag: [0x%x].",
                v27);
            v28 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
                    (Windows::Compat::Appraiser::PropertyBag *)v103,
                    L"SVOverrideTargetXY",
                    L"XY30H1");
            appended = v28;
            if ( v28 < 0 )
            {
              LODWORD(v82) = v28;
              v81 = "Error adding init property to bag: [0x%x].";
              v18 = 112;
              goto LABEL_89;
            }
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x70u,
                "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
                "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
                "Error adding init property to bag: [0x%x].",
                v28);
            appended = Windows::Compat::Appraiser::TelemetryAppraiser::ValidateOutputDirectories(v132, v29);
            if ( appended >= 0 )
            {
              if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                  0x77u,
                  "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
                  "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
                  "Failed to validate integrity of output directories: [0x%x].",
                  appended);
              appended = Windows::Compat::Appraiser::TelemetryAppraiser::InitializeVerboseModeDataAndLoggers(
                           (struct Windows::Compat::Appraiser::LogToFile *)&v125,
                           (struct Windows::Compat::Shared::UtcJson *)v104,
                           (struct Windows::Compat::Appraiser::TelemetryRunHealth *)v120,
                           (struct Windows::Compat::Appraiser::PropertyBag *)v103,
                           v132);
              if ( appended >= 0 )
              {
                if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                  Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                    0x7Eu,
                    "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
                    "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
                    "Failed to initialize verbose mode data or loggers: [0x%x].",
                    appended);
                appended = Windows::Compat::Appraiser::TelemetryAppraiser::InitializeData(
                             (struct Windows::Compat::Appraiser::DataFile *)v123,
                             v134,
                             260,
                             (struct Windows::Compat::Appraiser::PropertyBag *)v103,
                             (struct Windows::Compat::Appraiser::TelemetryRunHealth *)v120);
                if ( appended >= 0 )
                {
                  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                      0x85u,
                      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
                      "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
                      "Failed to initialize data file: [0x%x].",
                      appended);
                  v58 = Windows::Compat::Appraiser::TelemetryAppraiser::TelemetryAppraisalHelper(
                          (struct Windows::Compat::Appraiser::PropertyBag *)v103,
                          (struct Windows::Compat::Appraiser::TelemetryRunHealth *)v120,
                          v134,
                          (struct Windows::Compat::Appraiser::DataFile *)v123);
                  appended = v58;
                  if ( v58 >= 0 )
                  {
                    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                    {
                      LODWORD(v80) = v58;
                      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                        0x8Du,
                        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
                        "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
                        "Failed to do telemetry appraisal: [0x%x].",
                        v80);
                    }
                  }
                  else
                  {
                    LODWORD(v82) = v58;
                    LODWORD(v80) = v58;
                    Windows::Compat::Appraiser::WriteLog(
                      (Windows::Compat::Appraiser *)1,
                      141,
                      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
                      "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
                      (const char *)v80,
                      (int)"Failed to do telemetry appraisal: [0x%x].",
                      v82);
                  }
                  goto LABEL_141;
                }
                v20 = "Failed to initialize data file: [0x%x].";
                v18 = -123;
              }
              else
              {
                v20 = "Failed to initialize verbose mode data or loggers: [0x%x].";
                v18 = 126;
              }
            }
            else
            {
              v20 = "Failed to validate integrity of output directories: [0x%x].";
              v18 = 119;
            }
          }
          else
          {
            v20 = "Error printing value: [0x%x].";
            v18 = 106;
          }
        }
        else
        {
          v20 = "Error adding init properties to bag: [0x%x].";
          v18 = 97;
        }
        LODWORD(v82) = appended;
        LODWORD(v81) = (_DWORD)v20;
        goto LABEL_89;
      }
      LODWORD(v82) = v19;
      v81 = "Error adding init property to bag: [0x%x].";
      v18 = 94;
    }
    else
    {
      LODWORD(v82) = v17;
      v81 = "Error adding init property to bag: [0x%x].";
      v18 = 84;
    }
LABEL_89:
    LODWORD(v80) = appended;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v18,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
      (const char *)v80,
      (int)v81,
      v82);
    v11 = v83;
    goto LABEL_90;
  }
  if ( !v86 )
  {
    v12 = L"TRUE";
    goto LABEL_13;
  }
  appended = -2147024809;
  LODWORD(v80) = -2147024809;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    72,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
    "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
    (const char *)v80,
    (int)"Enterprise mode and indicator generation mode are incompatible in the same run.",
    v82);
LABEL_90:
  v30 = RtlArray<JsonValue *>::Append(
          v99,
          &Windows::Compat::Appraiser::WicaFactory::RegistryPathCspRunResultsCategoryLastRun);
  v31 = v30;
  if ( v30 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x99u,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
        "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
        "RtlArray Append failed: [0x%x].",
        v30);
  }
  else
  {
    LODWORD(v82) = v30;
    LODWORD(v80) = v30;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      153,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
      (const char *)v80,
      (int)"RtlArray Append failed: [0x%x].",
      v82);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v132);
    v32 = (volatile signed __int64 *)v132;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v32 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v32,
      _InterlockedExchangeAdd64(v32 + 17, 0),
      v131);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v33);
    v34 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      v89 = v131;
      v84 = v31;
      v90 = "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal";
      v91 = "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp";
      v85 = 153;
      v92 = (const char *)&szValueBuf;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v124 = SystemTime;
      v93[0] = &v124;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v34,
        (unsigned int)&byte_1802A0947,
        v35,
        v36,
        (__int64)v93,
        (__int64)&v92,
        (__int64)&v85,
        (__int64)&v91,
        (__int64)&v90,
        (__int64)&v84,
        (__int64)&v89);
    }
  }
  if ( v11 )
  {
    v37 = RtlArray<JsonValue *>::Append(
            v99,
            &Windows::Compat::Appraiser::WicaFactory::RegistryPathCspRunResultsCategoryLastEnterpriseRun);
    v38 = v37;
    if ( v37 >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x9Eu,
          "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
          "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
          "RtlArray Append failed: [0x%x].",
          v37);
    }
    else
    {
      LODWORD(v82) = v37;
      LODWORD(v80) = v37;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        158,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
        "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
        (const char *)v80,
        (int)"RtlArray Append failed: [0x%x].",
        v82);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v132);
      v39 = (volatile signed __int64 *)v132;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v39 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v39,
        _InterlockedExchangeAdd64(v39 + 17, 0),
        v131);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v40);
      v41 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        v93[0] = v131;
        v85 = v38;
        v92 = "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal";
        v91 = "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp";
        v84 = 158;
        v90 = (const char *)&szValueBuf;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v124 = SystemTime;
        v89 = (char *)&v124;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v41,
          (unsigned int)byte_1802A0881,
          v42,
          v43,
          (__int64)&v89,
          (__int64)&v90,
          (__int64)&v84,
          (__int64)&v91,
          (__int64)&v92,
          (__int64)&v85,
          (__int64)v93);
      }
    }
  }
  v44 = RtlArray<JsonValue *>::Append(
          v99,
          &Windows::Compat::Appraiser::WicaFactory::RegistryPathCspRunResultsCategoryLastFatallyErroredRun);
  v45 = v44;
  if ( v44 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xA4u,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
        "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
        "RtlArray Append failed: [0x%x].",
        v44);
  }
  else
  {
    LODWORD(v82) = v44;
    LODWORD(v80) = v44;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      164,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
      (const char *)v80,
      (int)"RtlArray Append failed: [0x%x].",
      v82);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v132);
    v46 = (volatile signed __int64 *)v132;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v46 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v46,
      _InterlockedExchangeAdd64(v46 + 17, 0),
      v131);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v47);
    v48 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      v93[0] = v131;
      v85 = v45;
      v92 = "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal";
      v91 = "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp";
      v84 = 164;
      v90 = (const char *)&szValueBuf;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v124 = SystemTime;
      v89 = (char *)&v124;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v48,
        (unsigned int)&dword_1802A08E4,
        v49,
        v50,
        (__int64)&v89,
        (__int64)&v90,
        (__int64)&v84,
        (__int64)&v91,
        (__int64)&v92,
        (__int64)&v85,
        (__int64)v93);
    }
  }
  v51 = Windows::Compat::Appraiser::Utilities::SetImmediateExitRunStateTracker((int)v99);
  v52 = v51;
  if ( v51 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    {
      LODWORD(v80) = v51;
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xA7u,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
        "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
        "Failed to set run state tracker: [0x%x].",
        v80);
    }
  }
  else
  {
    LODWORD(v82) = v51;
    LODWORD(v80) = v51;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      167,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
      (const char *)v80,
      (int)"Failed to set run state tracker: [0x%x].",
      v82);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v132);
    v53 = (volatile signed __int64 *)v132;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v53 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v53,
      _InterlockedExchangeAdd64(v53 + 17, 0),
      v131);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v54);
    v55 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      v93[0] = v131;
      v85 = v52;
      v92 = "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal";
      v91 = "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp";
      v84 = 167;
      v90 = (const char *)&szValueBuf;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v124 = SystemTime;
      v89 = (char *)&v124;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v55,
        (unsigned int)&word_1802A081E,
        v56,
        v57,
        (__int64)&v89,
        (__int64)&v90,
        (__int64)&v84,
        (__int64)&v91,
        (__int64)&v92,
        (__int64)&v85,
        (__int64)v93);
    }
  }
LABEL_141:
  Windows::Compat::Appraiser::PropertyBag::Clear((Windows::Compat::Appraiser::PropertyBag *)v103);
  v59 = Windows::Compat::Appraiser::DataFile::UnInitialize((Windows::Compat::Appraiser::DataFile *)v123);
  v60 = v59;
  if ( v59 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xADu,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
        "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
        "Error uninitializing data file: [0x%x].",
        v59);
  }
  else
  {
    LODWORD(v82) = v59;
    LODWORD(v80) = v59;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      173,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
      (const char *)v80,
      (int)"Error uninitializing data file: [0x%x].",
      v82);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v132);
    v61 = (volatile signed __int64 *)v132;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v61 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v61,
      _InterlockedExchangeAdd64(v61 + 17, 0),
      v131);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v62);
    v63 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      v93[0] = v131;
      v85 = v60;
      v92 = "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal";
      v91 = "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp";
      v84 = 173;
      v90 = (const char *)&szValueBuf;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v124 = SystemTime;
      v89 = (char *)&v124;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v63,
        (unsigned int)qword_1802A0758,
        v64,
        v65,
        (__int64)&v89,
        (__int64)&v90,
        (__int64)&v84,
        (__int64)&v91,
        (__int64)&v92,
        (__int64)&v85,
        (__int64)v93);
    }
  }
  v66 = Windows::Compat::Appraiser::TelemetryAppraiser::UnInitializeVerboseModeLoggers(
          (struct Windows::Compat::Appraiser::LogToFile *)&v125,
          (struct Windows::Compat::Shared::UtcJson *)v104);
  v67 = v66;
  if ( v66 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xB0u,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
        "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
        "Error uninitializing verbose mode loggers: [0x%x].",
        v66);
  }
  else
  {
    LODWORD(v82) = v66;
    LODWORD(v80) = v66;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      176,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
      (const char *)v80,
      (int)"Error uninitializing verbose mode loggers: [0x%x].",
      v82);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v132);
    v68 = (volatile signed __int64 *)v132;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v68 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v68,
      _InterlockedExchangeAdd64(v68 + 17, 0),
      v131);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v69);
    v70 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      v93[0] = v131;
      v85 = v67;
      v92 = "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal";
      v91 = "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp";
      v84 = 176;
      v90 = (const char *)&szValueBuf;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v124 = SystemTime;
      v89 = (char *)&v124;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v70,
        (unsigned int)byte_1802A07BB,
        v71,
        v72,
        (__int64)&v89,
        (__int64)&v90,
        (__int64)&v84,
        (__int64)&v91,
        (__int64)&v92,
        (__int64)&v85,
        (__int64)v93);
    }
  }
  v73 = Windows::Compat::Appraiser::TelemetryAppraiser::CleanOutputFiles();
  v74 = v73;
  if ( v73 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xB3u,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
        "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
        "Error cleaning output files: [0x%x].",
        v73);
  }
  else
  {
    LODWORD(v82) = v73;
    LODWORD(v80) = v73;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      179,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal",
      (const char *)v80,
      (int)"Error cleaning output files: [0x%x].",
      v82);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v132);
    v75 = (volatile signed __int64 *)v132;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v75 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v75,
      _InterlockedExchangeAdd64(v75 + 17, 0),
      v131);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v76);
    v77 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      v93[0] = v131;
      v85 = v74;
      v92 = "Windows::Compat::Appraiser::TelemetryAppraiser::DoTelemetryOrEnterpriseAppraisal";
      v91 = "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp";
      v84 = 179;
      v90 = (const char *)&szValueBuf;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v124 = SystemTime;
      v89 = (char *)&v124;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v77,
        (unsigned int)byte_1802A06F5,
        v78,
        v79,
        (__int64)&v89,
        (__int64)&v90,
        (__int64)&v84,
        (__int64)&v91,
        (__int64)&v92,
        (__int64)&v85,
        (__int64)v93);
    }
  }
  CloseHandle(hObject);
  RtlStringArray::Clear((RtlStringArray *)hHeap);
  if ( lpMem[1] )
    HeapFree(hHeap[0], 0, lpMem[1]);
  if ( v101[1] )
    HeapFree(v99[0], 0, v101[1]);
LABEL_7:
  Windows::Compat::Appraiser::PropertyBag::~PropertyBag((Windows::Compat::Appraiser::PropertyBag *)v103);
  Windows::Compat::Appraiser::DataFile::~DataFile((Windows::Compat::Appraiser::DataFile *)v123);
  Windows::Compat::Shared::UtcJson::~UtcJson((Windows::Compat::Shared::UtcJson *)v104);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1800489d4  push    rbp
0x1800489d6  push    rbx
0x1800489d7  push    rsi
0x1800489d8  push    rdi
0x1800489d9  push    r12
0x1800489db  push    r13
0x1800489dd  push    r14
0x1800489df  push    r15
0x1800489e1  lea     rbp, [rsp-0D08h]
0x1800489e9  sub     rsp, 0E08h
0x1800489f0  mov     [rbp+0D40h+var_BE8], 0FFFFFFFFFFFFFFFEh
0x1800489fb  mov     rax, cs:__security_cookie
0x180048a02  xor     rax, rsp
0x180048a05  mov     [rbp+0D40h+var_50], rax
0x180048a0c  mov     rbx, rcx
0x180048a0f  xor     r14d, r14d
0x180048a12  mov     [rbp+0D40h+var_930], r14
0x180048a19  mov     [rbp+0D40h+var_928], r14
0x180048a20  mov     [rbp+0D40h+var_920], r14w
0x180048a28  mov     [rbp+0D40h+var_940], r14
0x180048a2f  mov     [rbp+0D40h+var_938], r14b
0x180048a36  mov     [rbp+0D40h+var_718], r14b
0x180048a3d  xorps   xmm0, xmm0
0x180048a40  movups  [rbp+0D40h+var_CB0], xmm0
0x180048a47  movups  [rbp+0D40h+var_CA0], xmm0
0x180048a4e  movups  [rbp+0D40h+var_C90], xmm0
0x180048a55  call    cs:__imp_GetProcessHeap
0x180048a5b  mov     qword ptr [rbp+0D40h+var_CB0], rax
0x180048a62  lea     esi, [r14+10h]
0x180048a66  mov     qword ptr [rbp+0D40h+var_C90], rsi
0x180048a6d  xorps   xmm0, xmm0
0x180048a70  movdqa  [rbp+0D40h+var_CA0], xmm0
0x180048a78  mov     qword ptr [rbp+0D40h+var_C90+8], r14
0x180048a7f  lea     edi, [rsi-8]
0x180048a82  mov     qword ptr [rbp+0D40h+var_CB0+8], rdi
0x180048a89  movups  [rbp+0D40h+var_C80], xmm0
0x180048a90  movups  [rbp+0D40h+var_C70], xmm0
0x180048a97  movups  [rbp+0D40h+var_C60], xmm0
0x180048a9e  call    cs:__imp_GetProcessHeap
0x180048aa4  mov     qword ptr [rbp+0D40h+var_C80], rax
0x180048aab  mov     qword ptr [rbp+0D40h+var_C60], rsi
0x180048ab2  xorps   xmm0, xmm0
0x180048ab5  movdqa  [rbp+0D40h+var_C70], xmm0
0x180048abd  mov     qword ptr [rbp+0D40h+var_C60+8], r14
0x180048ac4  mov     qword ptr [rbp+0D40h+var_C80+8], rsi
0x180048acb  mov     [rbp+0D40h+var_C50], r14d
0x180048ad2  mov     r9d, esi
0x180048ad5  lea     rcx, [rbp+0D40h+var_C80]
0x180048adc  call    ?Initialize@?$RtlArray@URTL_STRING_ITEM@RtlStringArray@@@@QEAAJPEAX_K1H@Z; RtlArray<RtlStringArray::RTL_STRING_ITEM>::Initialize(void *,unsigned __int64,unsigned __int64,int)
0x180048ae1  mov     [rbp+0D40h+var_CD0], r14
0x180048ae5  mov     [rbp+0D40h+var_C48], r14
0x180048aec  mov     [rbp+0D40h+var_C38], 0FFFFFFFFFFFFFFFFh
0x180048af7  mov     [rbp+0D40h+var_C40], r14
0x180048afe  mov     [rbp+0D40h+var_CC8], r14
0x180048b02  mov     [rbp+0D40h+var_CC0], r14
0x180048b09  mov     [rbp+0D40h+var_CB8], 1
0x180048b12  mov     [rbp+0D40h+var_C30], r14d
0x180048b19  mov     [rbp+0D40h+var_C2C], 400h
0x180048b23  mov     [rbp+0D40h+var_C28], 40h ; '@'
0x180048b2d  mov     [rbp+0D40h+var_C24], 54h ; 'T'
0x180048b37  mov     [rsp+0E40h+var_DE0], r14b
0x180048b3c  mov     [rsp+0E40h+var_DD3], r14b
0x180048b41  mov     [rsp+0E40h+var_DD4], r14b
0x180048b46  mov     [rsp+0E40h+var_DD2], r14b
0x180048b4b  lea     rcx, [rbp+0D40h+var_BE0]; this
0x180048b52  call    ??0DataFile@Appraiser@Compat@Windows@@QEAA@XZ; Windows::Compat::Appraiser::DataFile::DataFile(void)
0x180048b57  nop
0x180048b58  lea     rcx, [rbp+0D40h+var_D20]; this
0x180048b5c  call    ??0PropertyBag@Appraiser@Compat@Windows@@QEAA@XZ; Windows::Compat::Appraiser::PropertyBag::PropertyBag(void)
0x180048b61  nop
0x180048b62  xorps   xmm0, xmm0
0x180048b65  movups  xmmword ptr [rbp+0D40h+var_D58], xmm0
0x180048b69  movups  xmmword ptr [rbp+0D40h+var_D38], xmm0
0x180048b6d  call    cs:__imp_GetProcessHeap
0x180048b73  mov     [rbp+0D40h+var_D58], rax
0x180048b77  mov     [rbp+0D40h+var_D38], rsi
0x180048b7b  xorps   xmm0, xmm0
0x180048b7e  movdqu  [rbp+0D40h+var_D48], xmm0
0x180048b83  mov     [rbp+0D40h+var_D38+8], r14
0x180048b87  mov     [rbp+0D40h+var_D58+8], rdi
0x180048b8b  movups  xmmword ptr [rbp+0D40h+hHeap], xmm0
0x180048b8f  movups  xmmword ptr [rbp+0D40h+lpMem], xmm0
0x180048b93  call    cs:__imp_GetProcessHeap
0x180048b99  mov     [rbp+0D40h+hHeap], rax
0x180048b9d  mov     [rbp+0D40h+lpMem], rsi
0x180048ba1  xorps   xmm0, xmm0
0x180048ba4  movdqu  [rbp+0D40h+var_D80], xmm0
0x180048ba9  mov     [rbp+0D40h+lpMem+8], r14
0x180048bad  mov     [rbp+0D40h+hHeap+8], rsi
0x180048bb1  mov     [rbp+0D40h+var_D60], r14d
0x180048bb5  mov     r9d, esi
0x180048bb8  lea     rcx, [rbp+0D40h+hHeap]
0x180048bbc  call    ?Initialize@?$RtlArray@URTL_STRING_ITEM@RtlStringArray@@@@QEAAJPEAX_K1H@Z; RtlArray<RtlStringArray::RTL_STRING_ITEM>::Initialize(void *,unsigned __int64,unsigned __int64,int)
0x180048bc1  nop
0x180048bc2  xorps   xmm0, xmm0
0x180048bc5  xor     eax, eax
0x180048bc7  movups  [rbp+0D40h+var_C20], xmm0
0x180048bce  movups  [rbp+0D40h+var_C10], xmm0
0x180048bd5  movups  [rbp+0D40h+var_C00], xmm0
0x180048bdc  mov     [rbp+0D40h+var_BF0], rax
0x180048be3  movdqu  xmmword ptr cs:?SyncId@WicaFactory@Appraiser@Compat@Windows@@2U_GUID@@A.Data1, xmm0; _GUID Windows::Compat::Appraiser::WicaFactory::SyncId ...
0x180048beb  lea     rcx, ?SyncId@WicaFactory@Appraiser@Compat@Windows@@2U_GUID@@A; Uuid
0x180048bf2  call    cs:__imp_UuidCreate
0x180048bf8  lea     r9, Name; "Global\\AppraiserExclusiveEvent"
0x180048bff  xor     r8d, r8d; bInitialState
0x180048c02  xor     edx, edx; bManualReset
0x180048c04  xor     ecx, ecx; lpEventAttributes
0x180048c06  call    cs:__imp_CreateEventW
0x180048c0c  mov     rdi, rax
0x180048c0f  mov     [rbp+0D40h+hObject], rax
0x180048c13  test    rax, rax
0x180048c16  jz      short loc_180048C2F
0x180048c18  call    cs:__imp_GetLastError
0x180048c1e  cmp     eax, 0B7h
0x180048c23  jnz     short loc_180048C98
0x180048c25  mov     rcx, rdi; hObject
0x180048c28  call    cs:__imp_CloseHandle
0x180048c2e  nop
0x180048c2f  lea     rcx, [rbp+0D40h+hHeap]; this
0x180048c33  call    ?Clear@RtlStringArray@@QEAAXXZ; RtlStringArray::Clear(void)
0x180048c38  mov     r8, [rbp+0D40h+lpMem+8]; lpMem
0x180048c3c  test    r8, r8
0x180048c3f  jz      short loc_180048C4E
0x180048c41  xor     edx, edx; dwFlags
0x180048c43  mov     rcx, [rbp+0D40h+hHeap]; hHeap
0x180048c47  call    cs:__imp_HeapFree
0x180048c4d  nop
0x180048c4e  mov     ebx, 80070021h
0x180048c53  lea     rcx, [rbp+0D40h+var_D20]; this
0x180048c57  call    ??1PropertyBag@Appraiser@Compat@Windows@@UEAA@XZ; Windows::Compat::Appraiser::PropertyBag::~PropertyBag(void)
0x180048c5c  nop
0x180048c5d  lea     rcx, [rbp+0D40h+var_BE0]; this
0x180048c64  call    ??1DataFile@Appraiser@Compat@Windows@@QEAA@XZ; Windows::Compat::Appraiser::DataFile::~DataFile(void)
0x180048c69  nop
0x180048c6a  lea     rcx, [rbp+0D40h+var_CD0]; this
0x180048c6e  call    ??1UtcJson@Shared@Compat@Windows@@QEAA@XZ; Windows::Compat::Shared::UtcJson::~UtcJson(void)
0x180048c73  mov     eax, ebx
0x180048c75  mov     rcx, [rbp+0D40h+var_50]
0x180048c7c  xor     rcx, rsp; StackCookie
0x180048c7f  call    __security_check_cookie
0x180048c84  add     rsp, 0E08h
0x180048c8b  pop     r15
0x180048c8d  pop     r14
0x180048c8f  pop     r13
0x180048c91  pop     r12
0x180048c93  pop     rdi
0x180048c94  pop     rsi
0x180048c95  pop     rbx
0x180048c96  pop     rbp
0x180048c97  retn
0x180048c98  mov     [rsp+0E40h+var_E18], rbx; char *
0x180048c9d  lea     rax, [rbp+0D40h+hHeap]
0x180048ca1  mov     [rsp+0E40h+var_E20], rax; struct RtlStringArray *
0x180048ca6  lea     r9, [rsp+0E40h+var_DD2]; bool *
0x180048cab  lea     r8, [rsp+0E40h+var_DD4]; bool *
0x180048cb0  lea     rdx, [rsp+0E40h+var_DD3]; bool *
0x180048cb5  lea     rcx, [rsp+0E40h+var_DE0]; bool *
0x180048cba  call    ?ParseCommandLine@TelemetryAppraiser@Appraiser@Compat@Windows@@CAXAEA_N000PEAVRtlStringArray@@PEAD@Z; Windows::Compat::Appraiser::TelemetryAppraiser::ParseCommandLine(bool &,bool &,bool &,bool &,RtlStringArray *,char *)
0x180048cbf  lea     r15, aTrue_2; "TRUE"
0x180048cc6  mov     r13b, [rsp+0E40h+var_DD4]
0x180048ccb  mov     r12b, [rsp+0E40h+var_DE0]
0x180048cd0  test    r12b, r12b
0x180048cd3  jz      short loc_180048D1E
0x180048cd5  test    r13b, r13b
0x180048cd8  jz      short loc_180048D19
0x180048cda  lea     rax, aEnterpriseMode; "Enterprise mode and indicator generatio"...
0x180048ce1  mov     [rsp+0E40h+var_E18], rax; int
0x180048ce6  mov     ebx, 80070057h
0x180048ceb  mov     dword ptr [rsp+0E40h+var_E20], ebx; char *
0x180048cef  lea     rdi, aWindowsCompatA_293; "Windows::Compat::Appraiser::TelemetryAp"...
0x180048cf6  mov     r9, rdi; char *
0x180048cf9  lea     rsi, aOnecoreBaseApp_75; "onecore\\base\\appcompat\\appraiser\\he"...
0x180048d00  mov     r8, rsi; unsigned int
0x180048d03  mov     edx, 48h ; 'H'; bool
0x180048d08  lea     r13d, [rdx-47h]
0x180048d0c  mov     ecx, r13d; this
0x180048d0f  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180048d14  jmp     loc_180049283
0x180048d19  mov     r8, r15
0x180048d1c  jmp     short loc_180048D25
0x180048d1e  lea     r8, aFalse_1; "FALSE"
0x180048d25  lea     rdx, aEnterpriseforc; "EnterpriseForceSync"
0x180048d2c  lea     rcx, [rbp+0D40h+var_D20]; this
0x180048d30  call    ?AppendProperty@PropertyBag@Appraiser@Compat@Windows@@QEAAJPEBG0@Z; Windows::Compat::Appraiser::PropertyBag::AppendProperty(ushort const *,ushort const *)
0x180048d35  mov     ebx, eax
0x180048d37  lea     r14, aErrorAddingIni; "Error adding init property to bag: [0x%"...
0x180048d3e  lea     rdi, aWindowsCompatA_293; "Windows::Compat::Appraiser::TelemetryAp"...
0x180048d45  lea     rsi, aOnecoreBaseApp_75; "onecore\\base\\appcompat\\appraiser\\he"...
0x180048d4c  test    eax, eax
0x180048d4e  jns     short loc_180048D7B
0x180048d50  mov     edx, 4Ch ; 'L'; bool
0x180048d55  mov     dword ptr [rsp+0E40h+var_E10], ebx; char *
0x180048d59  mov     [rsp+0E40h+var_E18], r14; int
0x180048d5e  mov     r8, rsi; unsigned int
0x180048d61  mov     r9, rdi; char *
0x180048d64  mov     dword ptr [rsp+0E40h+var_E20], ebx; char *
0x180048d68  mov     r13d, 1
0x180048d6e  mov     ecx, r13d; this
0x180048d71  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180048d76  jmp     loc_180049283
0x180048d7b  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180048d81  test    al, 1
0x180048d83  jz      short loc_180048D9C
0x180048d85  mov     dword ptr [rsp+0E40h+var_E20], ebx
0x180048d89  mov     r9, r14; char *
0x180048d8c  mov     r8, rdi; char *
0x180048d8f  mov     rdx, rsi; char *
0x180048d92  mov     ecx, 4Ch ; 'L'; unsigned int
0x180048d97  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180048d9c  mov     r8, r15
0x180048d9f  cmp     [rsp+0E40h+var_DD3], 0
0x180048da4  lea     rax, aFalse_1; "FALSE"
0x180048dab  cmovz   r8, rax; unsigned __int16 *
0x180048daf  lea     rdx, aEnterpriseforc_0; "EnterpriseForceSyncActuallyForced"
0x180048db6  lea     rcx, [rbp+0D40h+var_D20]; this
0x180048dba  call    ?AppendProperty@PropertyBag@Appraiser@Compat@Windows@@QEAAJPEBG0@Z; Windows::Compat::Appraiser::PropertyBag::AppendProperty(ushort const *,ushort const *)
0x180048dbf  mov     ebx, eax
0x180048dc1  test    eax, eax
0x180048dc3  jns     short loc_180048DCC
0x180048dc5  mov     edx, 4Fh ; 'O'
0x180048dca  jmp     short loc_180048D55
0x180048dcc  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180048dd2  test    al, 1
0x180048dd4  jz      short loc_180048DED
0x180048dd6  mov     dword ptr [rsp+0E40h+var_E20], ebx
0x180048dda  mov     r9, r14; char *
0x180048ddd  mov     r8, rdi; char *
0x180048de0  mov     rdx, rsi; char *
0x180048de3  mov     ecx, 4Fh ; 'O'; unsigned int
0x180048de8  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180048ded  mov     byte ptr [rbp+0D40h+var_C20+4], r12b
0x180048df4  mov     r8, r15
0x180048df7  mov     r12b, [rsp+0E40h+var_DD2]
0x180048dfc  test    r12b, r12b
0x180048dff  lea     rax, aFalse_1; "FALSE"
0x180048e06  cmovz   r8, rax; unsigned __int16 *
0x180048e0a  lea     rdx, aExpressmode; "ExpressMode"
0x180048e11  lea     rcx, [rbp+0D40h+var_D20]; this
0x180048e15  call    ?AppendProperty@PropertyBag@Appraiser@Compat@Windows@@QEAAJPEBG0@Z; Windows::Compat::Appraiser::PropertyBag::AppendProperty(ushort const *,ushort const *)
0x180048e1a  mov     ebx, eax
0x180048e1c  test    eax, eax
0x180048e1e  jns     short loc_180048E37
0x180048e20  mov     dword ptr [rsp+0E40h+var_E10], eax
0x180048e24  mov     [rsp+0E40h+var_E18], r14
0x180048e29  mov     edx, 54h ; 'T'
0x180048e2e  lea     r13d, [rdx-53h]
0x180048e32  jmp     loc_18004926C
0x180048e37  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180048e3d  test    al, 1
0x180048e3f  jz      short loc_180048E58
0x180048e41  mov     dword ptr [rsp+0E40h+var_E20], ebx
0x180048e45  mov     r9, r14; char *
0x180048e48  mov     r8, rdi; char *
0x180048e4b  mov     rdx, rsi; char *
0x180048e4e  mov     ecx, 54h ; 'T'; unsigned int
0x180048e53  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180048e58  mov     byte ptr [rbp+0D40h+var_C20+0Fh], r12b
0x180048e5f  test    r12b, r12b
0x180048e62  jz      short loc_180048E6E
0x180048e64  mov     cs:?FeatureType@AppraiserSettings@Appraiser@Compat@Windows@@0W4OnesettingsFeatureType@1234@A, 2; Windows::Compat::Appraiser::AppraiserSettings::OnesettingsFeatureType Windows::Compat::Appraiser::AppraiserSettings::FeatureType
0x180048e6e  test    r13b, r13b
0x180048e71  lea     rax, aFalse_1; "FALSE"
0x180048e78  cmovz   r15, rax
0x180048e7c  mov     r8, r15; unsigned __int16 *
0x180048e7f  lea     rdx, aOptimizeforind; "OptimizeForIndicatorGen"
0x180048e86  lea     rcx, [rbp+0D40h+var_D20]; this
0x180048e8a  call    ?AppendProperty@PropertyBag@Appraiser@Compat@Windows@@QEAAJPEBG0@Z; Windows::Compat::Appraiser::PropertyBag::AppendProperty(ushort const *,ushort const *)
0x180048e8f  mov     ebx, eax
0x180048e91  mov     r13d, 1
0x180048e97  test    eax, eax
0x180048e99  jns     short loc_180048EAD
0x180048e9b  mov     dword ptr [rsp+0E40h+var_E10], eax
0x180048e9f  mov     [rsp+0E40h+var_E18], r14
0x180048ea4  lea     edx, [r13+5Dh]
0x180048ea8  jmp     loc_18004926C
0x180048ead  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180048eb3  and     eax, r13d
0x180048eb6  test    al, al
0x180048eb8  jz      short loc_180048ED1
0x180048eba  mov     dword ptr [rsp+0E40h+var_E20], ebx
0x180048ebe  mov     r9, r14; char *
0x180048ec1  mov     r8, rdi; char *
0x180048ec4  mov     rdx, rsi; char *
0x180048ec7  mov     ecx, 5Eh ; '^'; unsigned int
0x180048ecc  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180048ed1  lea     rdx, [rbp+0D40h+hHeap]; struct RtlStringArray *
0x180048ed5  lea     rcx, [rbp+0D40h+var_D20]; this
0x180048ed9  call    ?AppendArbitraryCommandLineProperties@TelemetryAppraiser@Appraiser@Compat@Windows@@CAJAEAVPropertyBag@234@AEAVRtlStringArray@@@Z; Windows::Compat::Appraiser::TelemetryAppraiser::AppendArbitraryCommandLineProperties(Windows::Compat::Appraiser::PropertyBag &,RtlStringArray &)
0x180048ede  mov     ebx, eax
0x180048ee0  test    eax, eax
0x180048ee2  jns     short loc_180048EF5
0x180048ee4  lea     r9, aErrorAddingIni_0; "Error adding init properties to bag: [0"...
0x180048eeb  mov     edx, 61h ; 'a'
0x180048ef0  jmp     loc_180049263
0x180048ef5  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180048efb  and     eax, r13d
0x180048efe  test    al, al
0x180048f00  jz      short loc_180048F1D
0x180048f02  mov     dword ptr [rsp+0E40h+var_E20], ebx
0x180048f06  lea     r9, aErrorAddingIni_0; "Error adding init properties to bag: [0"...
  ... truncated ...
```
