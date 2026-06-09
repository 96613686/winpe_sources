# Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties(Windows::Compat::Appraiser::PropertyBag &)

- ea: `0x180053e24`
- end: `0x180055e62`
- name: `?AppendRegkeyRunProperties@TelemetryScheduler@Appraiser@Compat@Windows@@CAJAEAVPropertyBag@234@@Z`
- size: `8254`
- prototype: `__int64 __fastcall(struct Windows::Compat::Appraiser::PropertyBag *this)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180057afc`

## callees

- `0x18000147c`
- `0x180008570`
- `0x1800092dc`
- `0x180011c5c`
- `0x180013c7c`
- `0x1800151f4`
- `0x18001b4c0`
- `0x180026fd0`
- `0x1800291c8`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x1800530f4`
- `0x180053aec`
- `0x180053e24`
- `0x180068908`
- `0x180068bc8`
- `0x180068ce0`
- `0x180089384`
- `0x18008c378`
- `0x18008f7bc`

## import_xrefs

- `KERNEL32!InitOnceExecuteOnce` at `0x1800540e7`
- `KERNEL32!InitOnceExecuteOnce` at `0x1800550a2`
- `KERNEL32!InitOnceExecuteOnce` at `0x180055122`
- `KERNEL32!InitOnceExecuteOnce` at `0x1800554f9`
- `KERNEL32!InitOnceExecuteOnce` at `0x1800540e7`
- `KERNEL32!InitOnceExecuteOnce` at `0x1800550a2`
- `KERNEL32!InitOnceExecuteOnce` at `0x180055122`
- `KERNEL32!InitOnceExecuteOnce` at `0x1800554f9`
- `KERNEL32!GetSystemTime` at `0x180055286`
- `KERNEL32!GetSystemTime` at `0x18005564d`
- `KERNEL32!GetSystemTime` at `0x180055d30`
- `KERNEL32!GetSystemTime` at `0x180055286`
- `KERNEL32!GetSystemTime` at `0x18005564d`
- `KERNEL32!GetSystemTime` at `0x180055d30`

## string_xrefs

- `0x180055752`: `Error reading WU configuration: [0x%x].`
- `0x180055778`: `Error reading WU configuration: [0x%x].`
- `0x180055983`: `DisableWUAccess`
- `0x1800559d3`: `WUConfigChecksAllSucceeded`
- `0x180054053`: `Error reading registry value: [0x%x].`
- `0x180054096`: `Error reading registry value: [0x%x].`
- `0x180054d92`: `Error reading registry value: [0x%x].`
- `0x180054db6`: `Error reading registry value: [0x%x].`
- `0x180054a78`: `LastAttemptedRunDataVersion`
- `0x180054696`: `Error reading last attempted upload version: [0x%x].`
- `0x1800546d9`: `Error reading last attempted upload version: [0x%x].`
- `0x180054ac9`: `Error reading last attempted upload version: [0x%x].`
- `0x180054b10`: `Error reading last attempted upload version: [0x%x].`
- `0x180054645`: `LastAttemptedFullSyncRound`
- `0x1800553ff`: `LastSuccessfulFullSyncCommercialId`
- `0x1800553a2`: `CommercialId`
- `0x180053f0d`: `onecore\base\appcompat\appraiser\heads\telemetry\telemetryscheduler.cpp`
- `0x180053fae`: `onecore\base\appcompat\appraiser\heads\telemetry\telemetryscheduler.cpp`
- `0x180053f04`: `Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties`
- `0x180053fa7`: `Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties`
- `0x180053ef8`: `Error reading registry value %ls / %ls: [0x%x].`
- `0x180053fa0`: `Error reading registry value %ls / %ls: [0x%x].`
- `0x180054229`: `ManifestedUtcOnetimeSend`
- `0x180054464`: `InitialUtcAlreadySent`
- `0x1800545ba`: `Error reading last upload version: [0x%x].`
- `0x180054601`: `Error reading last upload version: [0x%x].`
- `0x180054848`: `Error reading registry value [0x%x].`
- `0x18005486c`: `Error reading registry value [0x%x].`
- `0x1800546b6`: `PreviousAttemptedFullSyncRoundNumber`
- `0x18005476e`: `Error reading last online upload version: [0x%x].`
- `0x1800547b5`: `Error reading last online upload version: [0x%x].`
- `0x180054ae9`: `PreviousAttemptedRunDataVersion`
- `0x180054ba5`: `Error reading last upload offline status: [0x%x].`
- `0x180054c0d`: `Error reading last upload offline status: [0x%x].`
- `0x1800551a8`: `Failed to get commercial ID, swallowing: [0x%x].`
- `0x18005533f`: `Failed to get commercial ID, swallowing: [0x%x].`
- `0x180055492`: `CommercialIdForPreviousSuccessfulFullSync`
- `0x180055307`: `CommercialIdIsSet`
- `0x180055429`: `Error reading if commercial ID is set: [0x%x].`
- `0x18005544f`: `Error reading if commercial ID is set: [0x%x].`
- `0x180055575`: `Arbitrary configuration key is corrupt, swallowing: [0x%x].`
- `0x1800556c2`: `Arbitrary configuration key is corrupt, swallowing: [0x%x].`
- `0x180055a7a`: `Error reading previous telemetry value: [0x%x].`
- `0x180055aa0`: `Error reading previous telemetry value: [0x%x].`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties(
        struct Windows::Compat::Appraiser::PropertyBag *this)
{
  HKEY v2; // r9
  signed int appended; // ebx
  HKEY v4; // r9
  char v5; // dl
  char v6; // dl
  HKEY v7; // r9
  int v8; // eax
  signed int v9; // eax
  __int64 v10; // r9
  int v11; // edx
  const unsigned __int16 *v12; // rax
  int v13; // eax
  signed int v14; // eax
  __int64 v15; // r9
  int v16; // edx
  int v17; // eax
  signed int v18; // eax
  __int64 v19; // r9
  int v20; // edx
  int v21; // eax
  HKEY v22; // r9
  const unsigned __int16 *v23; // r8
  int v24; // eax
  int v25; // eax
  HKEY v26; // r9
  HKEY v27; // r9
  int v28; // eax
  HKEY v29; // r9
  int v30; // eax
  const char *v31; // rcx
  unsigned __int64 v32; // rbx
  HKEY v33; // r9
  int v34; // eax
  const char *v35; // rcx
  unsigned __int64 v36; // rbx
  HKEY v37; // r9
  int v38; // eax
  HKEY v39; // r9
  int v40; // eax
  const unsigned __int16 *v41; // r8
  int v42; // eax
  char v43; // dl
  unsigned __int16 *v44; // rcx
  unsigned __int16 *v45; // r9
  __int64 v46; // rax
  __int64 v47; // r8
  unsigned __int16 *v48; // rcx
  int v49; // eax
  HKEY v50; // r9
  const char *v51; // rcx
  unsigned __int64 v52; // rax
  HKEY v53; // r9
  int v54; // eax
  HKEY v55; // r9
  int v56; // eax
  const char *v57; // rcx
  unsigned __int64 v58; // rbx
  char v59; // r12
  int v60; // eax
  unsigned __int64 v61; // rdx
  int v62; // eax
  int CommercialId; // eax
  int v64; // ebx
  volatile signed __int64 *v65; // rcx
  void **v66; // rdx
  __int64 v67; // r12
  __int64 v68; // r8
  __int64 v69; // r9
  const unsigned __int16 *v70; // r8
  int v71; // eax
  unsigned __int16 *v72; // r8
  int v73; // eax
  int String; // eax
  int v75; // eax
  int v76; // eax
  int v77; // eax
  int v78; // r12d
  volatile signed __int64 *v79; // rcx
  void **v80; // rdx
  __int64 v81; // rbx
  __int64 v82; // r8
  __int64 v83; // r9
  int WuConfigRegKeys; // eax
  const unsigned __int16 *v85; // r12
  const unsigned __int16 *v86; // r8
  int v87; // eax
  unsigned __int16 *v88; // r8
  int v89; // eax
  int v90; // eax
  const unsigned __int16 *v91; // r8
  int v92; // eax
  HKEY v93; // r9
  int v94; // eax
  int v95; // eax
  int v96; // eax
  int v97; // eax
  unsigned int v98; // ecx
  int v99; // eax
  int v100; // eax
  int v101; // r15d
  volatile signed __int64 *v102; // rcx
  void **v103; // rdx
  __int64 v104; // rbx
  __int64 v105; // r8
  __int64 v106; // r9
  char v107; // al
  int v108; // eax
  bool *v110; // [rsp+20h] [rbp-E0h]
  const char *v111; // [rsp+28h] [rbp-D8h]
  char *v112; // [rsp+30h] [rbp-D0h]
  bool *v113; // [rsp+38h] [rbp-C8h]
  unsigned int *v114; // [rsp+40h] [rbp-C0h]
  signed int v115; // [rsp+40h] [rbp-C0h]
  unsigned int pvData; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v117; // [rsp+78h] [rbp-88h] BYREF
  bool v118; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v119; // [rsp+88h] [rbp-78h] BYREF
  const char *v120; // [rsp+90h] [rbp-70h] BYREF
  bool v121; // [rsp+98h] [rbp-68h] BYREF
  bool v122; // [rsp+99h] [rbp-67h] BYREF
  bool v123; // [rsp+9Ah] [rbp-66h] BYREF
  bool v124; // [rsp+9Bh] [rbp-65h] BYREF
  bool v125; // [rsp+9Ch] [rbp-64h] BYREF
  unsigned __int64 v126; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v127; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v128; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v129; // [rsp+B4h] [rbp-4Ch] BYREF
  unsigned int v130; // [rsp+B8h] [rbp-48h] BYREF
  const char *v131; // [rsp+C0h] [rbp-40h] BYREF
  const char *v132; // [rsp+C8h] [rbp-38h] BYREF
  const char *v133[2]; // [rsp+D0h] [rbp-30h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+E0h] [rbp-20h] BYREF
  struct _SYSTEMTIME v135; // [rsp+F0h] [rbp-10h] BYREF
  GUID Guid; // [rsp+100h] [rbp+0h] BYREF
  char v137[144]; // [rsp+110h] [rbp+10h] BYREF
  char v138[144]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v139[40]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int16 v140[264]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v141[264]; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v142[264]; // [rsp+6A0h] [rbp+5A0h] BYREF
  unsigned __int16 v143[264]; // [rsp+8B0h] [rbp+7B0h] BYREF

  v125 = 0;
  v120 = 0;
  v118 = 0;
  Guid = 0;
  v121 = 0;
  v122 = 0;
  v123 = 0;
  v124 = 0;
  v128 = 0;
  v129 = 0;
  v130 = 0;
  memset_0(v139, 0, sizeof(v139));
  v126 = Windows::Compat::Appraiser::Utilities::Now();
  pvData = 0;
  v119 = 4;
  appended = Windows::Compat::Shared::Registry::ReadValue(
               &pvData,
               &v119,
               0x10u,
               v2,
               Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
               L"FailedRunCount");
  if ( appended == -2147024894 )
  {
    pvData = 0;
    appended = 0;
  }
  else if ( appended < 0 )
  {
    v6 = 0x80;
    v115 = appended;
    v113 = (bool *)L"FailedRunCount";
LABEL_11:
    LODWORD(v110) = appended;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v6,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      (const char *)v110,
      (int)"Error reading registry value %ls / %ls: [0x%x].",
      (const char *)Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
      v113,
      v115);
    return (unsigned int)appended;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x80u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error reading registry value %ls / %ls: [0x%x].",
      Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
      L"FailedRunCount",
      appended);
  appended = Windows::Compat::Appraiser::TelemetryScheduler::AppendDwordInitProperty(
               this,
               L"CurrentFailureCount",
               pvData);
  if ( appended < 0 )
  {
    v5 = -125;
LABEL_7:
    LODWORD(v112) = appended;
    v111 = "Error appending property: [0x%x].";
LABEL_8:
    LODWORD(v110) = appended;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v5,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      (const char *)v110,
      (int)v111,
      v112);
    return (unsigned int)appended;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x83u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error appending property: [0x%x].",
      appended);
  pvData = 0;
  v119 = 4;
  appended = Windows::Compat::Shared::Registry::ReadValue(
               &pvData,
               &v119,
               0x10u,
               v4,
               Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
               L"OfflineCount");
  if ( appended == -2147024894 )
  {
    pvData = 0;
    appended = 0;
  }
  else if ( appended < 0 )
  {
    LODWORD(v112) = appended;
    v111 = "Error reading registry value: [0x%x].";
    v5 = -118;
    goto LABEL_8;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x8Au,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error reading registry value: [0x%x].",
      appended);
  appended = Windows::Compat::Appraiser::TelemetryScheduler::AppendDwordInitProperty(
               this,
               L"CurrentOfflineCount",
               pvData);
  if ( appended < 0 )
  {
    v5 = -115;
    goto LABEL_7;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x8Du,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error appending property: [0x%x].",
      appended);
  InitOnceExecuteOnce(
    &Windows::Compat::Appraiser::AppraiserTestHooks::InitOnce,
    Windows::Compat::Appraiser::AppraiserTestHooks::InitOnceCallback,
    0,
    0);
  if ( Windows::Compat::Appraiser::AppraiserTestHooks::TestHookAlwaysSendUtc )
  {
    v8 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(this, L"TestHookUtcAlwaysSend", L"TRUE");
    appended = v8;
    if ( v8 < 0 )
    {
      LODWORD(v112) = v8;
      v111 = "Error adding init property to bag: [0x%x].";
      v5 = -106;
      goto LABEL_8;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x96u,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
        "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
        "Error adding init property to bag: [0x%x].",
        v8);
  }
  LODWORD(v119) = 0;
  v117 = 4;
  v9 = Windows::Compat::Shared::Registry::ReadValue(
         &v119,
         &v117,
         0x10u,
         v7,
         Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
         L"UtcOnetimeSend");
  v10 = 2147942402LL;
  appended = 0;
  v11 = 0;
  if ( v9 != -2147024894 )
  {
    v11 = v119 != 0;
    appended = v9;
  }
  LODWORD(v119) = v11;
  if ( appended < 0 )
  {
    v12 = L"UtcOnetimeSend";
    v6 = -98;
LABEL_33:
    v115 = appended;
    v113 = (bool *)v12;
    goto LABEL_11;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
  {
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x9Eu,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error reading registry value %ls / %ls: [0x%x].",
      Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
      L"UtcOnetimeSend",
      appended);
    LOBYTE(v11) = v119;
  }
  if ( (_BYTE)v11 )
  {
    v13 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(this, L"ManifestedUtcOnetimeSend", L"TRUE");
    appended = v13;
    if ( v13 < 0 )
    {
      LODWORD(v112) = v13;
      v5 = -94;
      v111 = "Error adding init property to bag: [0x%x].";
      goto LABEL_8;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xA2u,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
        "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
        "Error adding init property to bag: [0x%x].",
        v13);
  }
  LODWORD(v119) = 0;
  v117 = 4;
  v14 = Windows::Compat::Shared::Registry::ReadValue(
          &v119,
          &v117,
          0x10u,
          (HKEY)v10,
          Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
          L"GenTelUtcOnetimeSend");
  v15 = 2147942402LL;
  appended = 0;
  v16 = 0;
  if ( v14 != -2147024894 )
  {
    v16 = v119 != 0;
    appended = v14;
  }
  LODWORD(v119) = v16;
  if ( appended < 0 )
  {
    v12 = L"GenTelUtcOnetimeSend";
    v6 = -90;
    goto LABEL_33;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
  {
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xA6u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error reading registry value %ls / %ls: [0x%x].",
      Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
      L"GenTelUtcOnetimeSend",
      appended);
    LOBYTE(v16) = v119;
  }
  if ( (_BYTE)v16 )
  {
    v17 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(this, L"GenTelUtcOnetimeSend", L"TRUE");
    appended = v17;
    if ( v17 < 0 )
    {
      LODWORD(v112) = v17;
      v5 = -86;
      v111 = "Error adding init property to bag: [0x%x].";
      goto LABEL_8;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xAAu,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
        "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
        "Error adding init property to bag: [0x%x].",
        v17);
  }
  LODWORD(v119) = 0;
  v117 = 4;
  v18 = Windows::Compat::Shared::Registry::ReadValue(
          &v119,
          &v117,
          0x10u,
          (HKEY)v15,
          Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
          L"SentFirstTime");
  v19 = 2147942402LL;
  appended = 0;
  v20 = 0;
  if ( v18 != -2147024894 )
  {
    v20 = v119 != 0;
    appended = v18;
  }
  LODWORD(v119) = v20;
  if ( appended < 0 )
  {
    v12 = L"SentFirstTime";
    v6 = -78;
    goto LABEL_33;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
  {
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xB2u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error reading registry value %ls / %ls: [0x%x].",
      Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
      L"SentFirstTime",
      appended);
    LOBYTE(v20) = v119;
  }
  if ( (_BYTE)v20 )
  {
    v21 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(this, L"InitialUtcAlreadySent", L"TRUE");
    appended = v21;
    if ( v21 < 0 )
    {
      LODWORD(v112) = v21;
      v5 = -74;
      v111 = "Error adding init property to bag: [0x%x].";
      goto LABEL_8;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xB6u,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
        "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
        "Error adding init property to bag: [0x%x].",
        v21);
  }
  pvData = 0;
  v117 = 4;
  if ( (int)Windows::Compat::Shared::Registry::ReadValue(
              &pvData,
              &v117,
              0x10u,
              (HKEY)v19,
              Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
              L"DisablePerfBackoff") >= 0 )
  {
    v23 = L"TRUE";
    if ( pvData == 1 )
      v23 = L"FALSE";
    v24 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(this, L"AllowPerfBackoff", v23);
    appended = v24;
    if ( v24 < 0 )
    {
      LODWORD(v112) = v24;
      v5 = -63;
      v111 = "Error adding init property to bag: [0x%x].";
      goto LABEL_8;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xC1u,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
        "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
        "Error adding init property to bag: [0x%x].",
        v24);
  }
  pvData = 0;
  v117 = 4;
  v25 = Windows::Compat::Shared::Registry::ReadValue(
          &pvData,
          &v117,
          0x10u,
          v22,
          Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
          L"LastSuccessfulFullSyncRound");
  appended = v25;
  if ( v25 == -2147024894 )
  {
    pvData = 0;
    appended = 0;
  }
  else if ( v25 < 0 )
  {
    LODWORD(v112) = v25;
    LODWORD(v110) = v25;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      201,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      (const char *)v110,
      (int)"Error reading last upload version: [0x%x].",
      v112);
    return (unsigned int)appended;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xC9u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error reading last upload version: [0x%x].",
      appended);
  appended = Windows::Compat::Appraiser::TelemetryScheduler::AppendDwordInitProperty(
               this,
               L"PreviousFullSyncRoundNumber",
               pvData);
  if ( appended < 0 )
  {
    v5 = -52;
    goto LABEL_7;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xCCu,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error appending property: [0x%x].",
      appended);
  pvData = 0;
  v117 = 4;
  appended = Windows::Compat::Shared::Registry::ReadValue(
               &pvData,
               &v117,
               0x10u,
               v26,
               Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
               L"LastAttemptedFullSyncRound");
  if ( appended == -2147024894 )
  {
    pvData = 0;
    appended = 0;
  }
  else if ( appended < 0 )
  {
    LODWORD(v112) = appended;
    v111 = "Error reading last attempted upload version: [0x%x].";
    v5 = -45;
    goto LABEL_8;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xD3u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error reading last attempted upload version: [0x%x].",
      appended);
  appended = Windows::Compat::Appraiser::TelemetryScheduler::AppendDwordInitProperty(
               this,
               L"PreviousAttemptedFullSyncRoundNumber",
               pvData);
  if ( appended < 0 )
  {
    v5 = -42;
    goto LABEL_7;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xD6u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error appending property: [0x%x].",
      appended);
  pvData = 0;
  v117 = 4;
  v28 = Windows::Compat::Shared::Registry::ReadValue(
          &pvData,
          &v117,
          0x10u,
          v27,
          Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
          L"LastOnlineRound");
  appended = v28;
  if ( v28 == -2147024894 )
  {
    pvData = 0;
    appended = 0;
  }
  else if ( v28 < 0 )
  {
    LODWORD(v112) = v28;
    LODWORD(v110) = v28;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      221,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      (const char *)v110,
      (int)"Error reading last online upload version: [0x%x].",
      v112);
    return (unsigned int)appended;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xDDu,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error reading last online upload version: [0x%x].",
      appended);
  appended = Windows::Compat::Appraiser::TelemetryScheduler::AppendDwordInitProperty(
               this,
               L"PreviousOnlineRoundNumber",
               pvData);
  if ( appended < 0 )
  {
    v5 = -32;
    goto LABEL_7;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xE0u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error appending property: [0x%x].",
      appended);
  v120 = 0;
  v117 = 8;
  v30 = Windows::Compat::Shared::Registry::ReadValue(
          &v120,
          &v117,
          0x40u,
          v29,
          Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
          L"LastSuccessfulFullSyncTime");
  appended = v30;
  if ( v30 == -2147024894 )
  {
    v31 = 0;
    appended = 0;
    v120 = 0;
  }
  else
  {
    if ( v30 < 0 )
    {
      LODWORD(v112) = v30;
      LODWORD(v110) = v30;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        232,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
        "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
        (const char *)v110,
        (int)"Error reading registry value [0x%x].",
        v112);
      return (unsigned int)appended;
    }
    v31 = v120;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
  {
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xE8u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error reading registry value [0x%x].",
      appended);
    v31 = v120;
  }
  v32 = v126;
  if ( (unsigned __int64)v31 > v126 )
  {
    LODWORD(v110) = -2147418113;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      241,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      (const char *)v110,
      (int)"Last successful full sync time: [%llu] is greater than now: [%llu] : [0x%x].",
      v31,
      v126,
      -2147418113);
    v31 = 0;
    v120 = 0;
  }
  appended = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
               this,
               L"DaysSinceLastSuccessfulFullSync",
               (v32 - (unsigned __int64)v31) / 0xC92A69C000LL);
  if ( appended < 0 )
  {
    v5 = -7;
    goto LABEL_7;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xF9u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error appending property: [0x%x].",
      appended);
  v120 = 0;
  v117 = 8;
  v34 = Windows::Compat::Shared::Registry::ReadValue(
          &v120,
          &v117,
          0x40u,
          v33,
          Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
          L"LastOnlineTime");
  appended = v34;
  if ( v34 == -2147024894 )
  {
    v35 = 0;
    v120 = 0;
    appended = 0;
  }
  else
  {
    if ( v34 < 0 )
    {
      LODWORD(v112) = v34;
      LODWORD(v110) = v34;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        1,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
        "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
        (const char *)v110,
        (int)"Error reading registry value [0x%x].",
        v112);
      return (unsigned int)appended;
    }
    v35 = v120;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
  {
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x101u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error reading registry value [0x%x].",
      appended);
    v35 = v120;
  }
  v36 = v126;
  if ( (unsigned __int64)v35 > v126 )
  {
    LODWORD(v114) = -2147418113;
    LODWORD(v110) = -2147418113;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      10,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      (const char *)v110,
      (int)"Last online full sync time: [%llu] is greater than now: [%llu] : [0x%x].",
      v35,
      v126,
      v114);
    v35 = 0;
    v120 = 0;
  }
  appended = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
               this,
               L"DaysSinceLastOnlineRun",
               (v36 - (unsigned __int64)v35) / 0xC92A69C000LL);
  if ( appended < 0 )
  {
    v5 = 18;
    goto LABEL_7;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x112u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error appending property: [0x%x].",
      appended);
  pvData = 0;
  v117 = 4;
  v38 = Windows::Compat::Shared::Registry::ReadValue(
          &pvData,
          &v117,
          0x10u,
          v37,
          Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
          L"LastAttemptedRunDataVersion");
  appended = v38;
  if ( v38 == -2147024894 )
  {
    pvData = 0;
    appended = 0;
  }
  else if ( v38 < 0 )
  {
    LODWORD(v112) = v38;
    LODWORD(v110) = v38;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      25,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      (const char *)v110,
      (int)"Error reading last attempted upload version: [0x%x].",
      v112);
    return (unsigned int)appended;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x119u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error reading last attempted upload version: [0x%x].",
      appended);
  appended = Windows::Compat::Appraiser::TelemetryScheduler::AppendDwordInitProperty(
               this,
               L"PreviousAttemptedRunDataVersion",
               pvData);
  if ( appended < 0 )
  {
    v5 = 28;
    goto LABEL_7;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x11Cu,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error appending property: [0x%x].",
      appended);
  pvData = 0;
  v117 = 4;
  v40 = Windows::Compat::Shared::Registry::ReadValue(
          &pvData,
          &v117,
          0x10u,
          v39,
          Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
          L"BaselineIsOffline");
  appended = v40;
  if ( v40 == -2147024894 )
  {
    pvData = 0;
    appended = 0;
  }
  else if ( v40 < 0 )
  {
    LODWORD(v112) = v40;
    LODWORD(v110) = v40;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      35,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      (const char *)v110,
      (int)"Error reading last upload offline status: [0x%x].",
      v112);
    return (unsigned int)appended;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x123u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error reading last upload offline status: [0x%x].",
      appended);
  v41 = L"TRUE";
  if ( pvData != 1 )
    v41 = L"FALSE";
  v42 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(this, L"BaselineIsOffline", v41);
  appended = v42;
  if ( v42 < 0 )
  {
    LODWORD(v112) = v42;
    v5 = 38;
    v111 = "Error adding init property to bag: [0x%x].";
    goto LABEL_8;
  }
  v43 = Windows::Compat::Appraiser::WicaFactory::TestingFlags;
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
  {
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x126u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error adding init property to bag: [0x%x].",
      v42);
    v43 = Windows::Compat::Appraiser::WicaFactory::TestingFlags;
  }
  v44 = Windows::Compat::Appraiser::WicaFactory::RegistryPathAppCompatFlags;
  v45 = v141;
  v46 = 2147483646;
  v47 = 260;
  do
  {
    if ( !v46 )
      break;
    if ( !*v44 )
      break;
    *v45++ = *v44++;
    --v46;
    --v47;
  }
  while ( v47 );
  v48 = v45 - 1;
  appended = v47 == 0 ? 0x8007007A : 0;
  if ( v47 )
    v48 = v45;
  *v48 = 0;
  if ( !v47 )
  {
    LODWORD(v112) = -2147024774;
    v5 = 45;
    v111 = "Error printing string: [0x%x].";
    goto LABEL_8;
  }
  if ( (v43 & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x12Du,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error printing string: [0x%x].",
      v47 == 0 ? 0x8007007A : 0);
  v49 = StringCchCatW(v141, 0x104u, L"\\GeneralMarkers\\UNV");
  appended = v49;
  if ( v49 < 0 )
  {
    LODWORD(v112) = v49;
    v5 = 48;
    v111 = "Error printing string: [0x%x].";
    goto LABEL_8;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x130u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error printing string: [0x%x].",
      v49);
  v117 = 8;
  v120 = 0;
  appended = Windows::Compat::Shared::Registry::ReadValue(&v120, &v117, 0x40u, v50, v141, L"Timestamp");
  if ( appended == -2147024894 )
  {
    v51 = 0;
    appended = 0;
    v120 = 0;
  }
  else
  {
    if ( appended < 0 )
    {
      LODWORD(v112) = appended;
      v111 = "Error reading registry value: [0x%x].";
      v5 = 51;
      goto LABEL_8;
    }
    v51 = v120;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
  {
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x133u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error reading registry value: [0x%x].",
      appended);
    v51 = v120;
  }
  v52 = v126;
  if ( (unsigned __int64)v51 > v126 )
  {
    LODWORD(v114) = appended;
    Windows::Compat::Appraiser::WriteLog(
      0,
      59,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      0,
      (int)"General marker timestamp: [%llu] is greater than now: [%llu] : [0x%x].",
      v51,
      v126,
      v114);
    v52 = v126;
    v51 = 0;
    v120 = 0;
  }
  appended = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
               this,
               L"GenTelMarkersAge",
               (v52 - (unsigned __int64)v51) / 0xC92A69C000LL);
  if ( appended < 0 )
  {
    v5 = 67;
    goto LABEL_7;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x143u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error appending property: [0x%x].",
      appended);
  pvData = 0;
  v117 = 4;
  v54 = Windows::Compat::Shared::Registry::ReadValue(
          &pvData,
          &v117,
          0x10u,
          v53,
          Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
          L"IndicatorDataVersion");
  appended = v54;
  if ( v54 == -2147024894 )
  {
    pvData = 0;
    appended = 0;
  }
  else if ( v54 < 0 )
  {
    LODWORD(v112) = v54;
    LODWORD(v110) = v54;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      74,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      (const char *)v110,
      (int)"Error reading registry value: [0x%x].",
      v112);
    return (unsigned int)appended;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x14Au,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error reading registry value: [0x%x].",
      appended);
  appended = Windows::Compat::Appraiser::TelemetryScheduler::AppendDwordInitProperty(
               this,
               L"IndicatorDataVersion",
               pvData);
  if ( appended < 0 )
  {
    v5 = 77;
    goto LABEL_7;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x14Du,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error appending property: [0x%x].",
      appended);
  v120 = 0;
  v117 = 8;
  v56 = Windows::Compat::Shared::Registry::ReadValue(
          &v120,
          &v117,
          0x40u,
          v55,
          Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
          L"IndicatorOnesettingsEvidenceTimestamp");
  appended = v56;
  if ( v56 == -2147024894 )
  {
    v57 = 0;
    v120 = 0;
    appended = 0;
  }
  else
  {
    if ( v56 < 0 )
    {
      LODWORD(v112) = v56;
      LODWORD(v110) = v56;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        80,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
        "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
        (const char *)v110,
        (int)"Error reading registry value: [0x%x].",
        v112);
      return (unsigned int)appended;
    }
    v57 = v120;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
  {
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x150u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error reading registry value: [0x%x].",
      appended);
    v57 = v120;
  }
  v58 = v126;
  if ( (unsigned __int64)v57 <= v126 )
  {
    v59 = 0;
  }
  else
  {
    LODWORD(v114) = -2147418113;
    LODWORD(v110) = -2147418113;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      89,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      (const char *)v110,
      (int)"Indicator onesettings evidence timestamp: [%llu] is greater than now: [%llu] : [0x%x].",
      v57,
      v126,
      v114);
    v59 = 0;
    v57 = 0;
    v120 = 0;
  }
  appended = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
               this,
               L"IndicatorOnesettingsAge",
               (v58 - (unsigned __int64)v57) / 0xC92A69C000LL);
  if ( appended < 0 )
  {
    v5 = 97;
    goto LABEL_7;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x161u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error appending property: [0x%x].",
      appended);
  InitOnceExecuteOnce(
    &Windows::Compat::Appraiser::AppraiserTestHooks::InitOnce,
    Windows::Compat::Appraiser::AppraiserTestHooks::InitOnceCallback,
    0,
    0);
  if ( Windows::Compat::Appraiser::AppraiserTestHooks::TestHookRequestAllAppraiserVersions )
  {
    v60 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(this, L"AllAppraiserVersionsRequested", L"TRUE");
    appended = v60;
    if ( v60 < 0 )
    {
      LODWORD(v112) = v60;
      v5 = 106;
      v111 = "Error adding init property to bag: [0x%x].";
      goto LABEL_8;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x16Au,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
        "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
        "Error adding init property to bag: [0x%x].",
        v60);
  }
  InitOnceExecuteOnce(
    &Windows::Compat::Appraiser::AppraiserTestHooks::InitOnce,
    Windows::Compat::Appraiser::AppraiserTestHooks::InitOnceCallback,
    0,
    0);
  if ( Windows::Compat::Appraiser::AppraiserTestHooks::TestHookRequestLatestAppraiserVersion )
  {
    v62 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(this, L"LatestAppraiserVersionRequested", L"TRUE");
    appended = v62;
    if ( v62 < 0 )
    {
      LODWORD(v112) = v62;
      v5 = 116;
      v111 = "Error adding init property to bag: [0x%x].";
      goto LABEL_8;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x174u,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
        "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
        "Error adding init property to bag: [0x%x].",
        v62);
  }
  CommercialId = Windows::Compat::Appraiser::Utilities::GetCommercialId(v140, v61);
  v64 = CommercialId;
  if ( CommercialId >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x17Cu,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
        "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
        "Failed to get commercial ID, swallowing: [0x%x].",
        CommercialId);
    if ( !v64 )
      v59 = 1;
  }
  else
  {
    LODWORD(v112) = CommercialId;
    LODWORD(v110) = CommercialId;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      124,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      (const char *)v110,
      (int)"Failed to get commercial ID, swallowing: [0x%x].",
      v112);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v137);
    v65 = (volatile signed __int64 *)v137;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v65 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v65,
      _InterlockedExchangeAdd64(v65 + 17, 0),
      v138);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v66);
    v67 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      LODWORD(v119) = v64;
      v117 = (unsigned __int64)v138;
      v131 = "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties";
      v133[0] = (const char *)&szValueBuf;
      v132 = "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp";
      LODWORD(v126) = 380;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v127 = (unsigned __int64)&v135;
      v135 = SystemTime;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v67,
        (__int64)qword_1802A0A70,
        v68,
        v69,
        (__int64 *)&v127,
        (const size_t **)v133,
        (__int64)&v126,
        &v132,
        &v131,
        (__int64)&v119,
        (const char **)&v117);
    }
    v59 = 0;
  }
  v70 = L"TRUE";
  if ( !v59 )
    v70 = L"FALSE";
  v71 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(this, L"CommercialIdIsSet", v70);
  appended = v71;
  if ( v71 < 0 )
  {
    LODWORD(v112) = v71;
    v5 = -127;
    v111 = "Error adding init property to bag: [0x%x].";
    goto LABEL_8;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x181u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error adding init property to bag: [0x%x].",
      v71);
  v72 = v140;
  if ( !v59 )
    v72 = L"[VariableValueNotSet]";
  v73 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(this, L"CommercialId", v72);
  appended = v73;
  if ( v73 < 0 )
  {
    LODWORD(v112) = v73;
    v5 = -124;
    v111 = "Error adding init property to bag: [0x%x].";
    goto LABEL_8;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x184u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error adding init property to bag: [0x%x].",
      v73);
  String = Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(
             v140,
             0x104u,
             (unsigned __int16 *)&szValueBuf,
             (unsigned __int16 *)Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
             L"LastSuccessfulFullSyncCommercialId");
  appended = String;
  if ( String < 0 )
  {
    LODWORD(v112) = String;
    v111 = "Error reading if commercial ID is set: [0x%x].";
    v5 = -112;
    goto LABEL_8;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x190u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error reading if commercial ID is set: [0x%x].",
      String);
  if ( v140[0] && (int)AslGuidFromString(&Guid) >= 0 )
  {
    v75 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
            this,
            L"CommercialIdForPreviousSuccessfulFullSync",
            v140);
    appended = v75;
    if ( v75 < 0 )
    {
      LODWORD(v112) = v75;
      v5 = -103;
      v111 = "Error adding init property to bag: [0x%x].";
      goto LABEL_8;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x199u,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
        "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
        "Error adding init property to bag: [0x%x].",
        v75);
  }
  InitOnceExecuteOnce(
    &Windows::Compat::Appraiser::AppraiserTestHooks::InitOnce,
    Windows::Compat::Appraiser::AppraiserTestHooks::InitOnceCallback,
    0,
    0);
  v76 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
          this,
          L"TestHookSkipDeviceSdbForTarget",
          Windows::Compat::Appraiser::AppraiserTestHooks::TestHookSkipDeviceSdbForTarget);
  appended = v76;
  if ( v76 < 0 )
  {
    LODWORD(v112) = v76;
    v5 = -94;
    v111 = "Error adding init property to bag: [0x%x].";
    goto LABEL_8;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x1A2u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error adding init property to bag: [0x%x].",
      v76);
  v77 = Windows::Compat::Appraiser::TelemetryScheduler::AppendArbitraryConfigurationRegkeyProperties(this);
  v78 = v77;
  if ( v77 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x1A9u,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
        "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
        "Arbitrary configuration key is corrupt, swallowing: [0x%x].",
        v77);
  }
  else
  {
    LODWORD(v112) = v77;
    LODWORD(v110) = v77;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      169,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      (const char *)v110,
      (int)"Arbitrary configuration key is corrupt, swallowing: [0x%x].",
      v112);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v137);
    v79 = (volatile signed __int64 *)v137;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v79 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v79,
      _InterlockedExchangeAdd64(v79 + 17, 0),
      v138);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v80);
    v81 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      LODWORD(v126) = v78;
      v127 = (unsigned __int64)v138;
      v133[0] = "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties";
      v131 = (const char *)&szValueBuf;
      v132 = "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp";
      LODWORD(v119) = 425;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v117 = (unsigned __int64)&v135;
      v135 = SystemTime;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v81,
        (__int64)byte_1802A0AD3,
        v82,
        v83,
        (__int64 *)&v117,
        (const size_t **)&v131,
        (__int64)&v119,
        &v132,
        v133,
        (__int64)&v126,
        (const char **)&v127);
    }
  }
  WuConfigRegKeys = Windows::Compat::Appraiser::Utilities::GetWuConfigRegKeys(
                      v142,
                      &v118,
                      0x104u,
                      v143,
                      &v121,
                      0x104u,
                      &v128,
                      &v122,
                      &v129,
                      &v123,
                      &v130,
                      &v124,
                      &v125);
  appended = WuConfigRegKeys;
  if ( WuConfigRegKeys < 0 )
  {
    LODWORD(v112) = WuConfigRegKeys;
    v111 = "Error reading WU configuration: [0x%x].";
    v5 = -68;
    goto LABEL_8;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x1BCu,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error reading WU configuration: [0x%x].",
      WuConfigRegKeys);
  v85 = L"TRUE";
  v86 = L"TRUE";
  if ( !v118 )
    v86 = L"FALSE";
  v87 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(this, L"WUStatusServerIsSet", v86);
  appended = v87;
  if ( v87 < 0 )
  {
    LODWORD(v112) = v87;
    v5 = -65;
    v111 = "Error adding init property to bag: [0x%x].";
    goto LABEL_8;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x1BFu,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error adding init property to bag: [0x%x].",
      v87);
  v88 = v142;
  if ( !v118 )
    v88 = L"[VariableValueNotSet]";
  v89 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(this, L"WUStatusServer", v88);
  appended = v89;
  if ( v89 < 0 )
  {
    LODWORD(v112) = v89;
    v5 = -62;
    v111 = "Error adding init property to bag: [0x%x].";
    goto LABEL_8;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x1C2u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error adding init property to bag: [0x%x].",
      v89);
  if ( v121 )
  {
    v90 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(this, L"WUServer", v143);
    appended = v90;
    if ( v90 < 0 )
    {
      LODWORD(v112) = v90;
      v5 = -57;
      v111 = "Error adding init property to bag: [0x%x].";
      goto LABEL_8;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x1C7u,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
        "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
        "Error adding init property to bag: [0x%x].",
        v90);
  }
  if ( v122 )
  {
    appended = Windows::Compat::Appraiser::TelemetryScheduler::AppendDwordInitProperty(this, L"UseWUServer", v128);
    if ( appended < 0 )
    {
      v5 = -51;
      goto LABEL_7;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x1CDu,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
        "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
        "Error appending property: [0x%x].",
        appended);
  }
  if ( v123 )
  {
    appended = Windows::Compat::Appraiser::TelemetryScheduler::AppendDwordInitProperty(this, L"DoNotConnectToWU", v129);
    if ( appended < 0 )
    {
      v5 = -45;
      goto LABEL_7;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x1D3u,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
        "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
        "Error appending property: [0x%x].",
        appended);
  }
  if ( v124 )
  {
    appended = Windows::Compat::Appraiser::TelemetryScheduler::AppendDwordInitProperty(this, L"DisableWUAccess", v130);
    if ( appended < 0 )
    {
      v5 = -39;
      goto LABEL_7;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x1D9u,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
        "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
        "Error appending property: [0x%x].",
        appended);
  }
  v91 = L"TRUE";
  if ( !v125 )
    v91 = L"FALSE";
  v92 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(this, L"WUConfigChecksAllSucceeded", v91);
  appended = v92;
  if ( v92 < 0 )
  {
    LODWORD(v112) = v92;
    v5 = -35;
    v111 = "Error adding init property to bag: [0x%x].";
    goto LABEL_8;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x1DDu,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error adding init property to bag: [0x%x].",
      v92);
  pvData = 0;
  v127 = 4;
  v94 = Windows::Compat::Shared::Registry::ReadValue(
          &pvData,
          &v127,
          0x10u,
          v93,
          Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
          L"PreviousTelemetryOptInValue");
  appended = v94;
  if ( v94 == -2147024894 )
  {
    v99 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(this, L"PreviousTelemetryOptInFound", L"FALSE");
    appended = v99;
    if ( v99 < 0 )
    {
      LODWORD(v112) = v99;
      v5 = -12;
      v111 = "Error adding init property to bag: [0x%x].";
      goto LABEL_8;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    {
      v98 = 500;
      goto LABEL_323;
    }
  }
  else
  {
    if ( v94 < 0 )
    {
      LODWORD(v112) = v94;
      v111 = "Error reading previous telemetry value: [0x%x].";
      v5 = -26;
      goto LABEL_8;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x1E6u,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
        "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
        "Error reading previous telemetry value: [0x%x].",
        v94);
    v95 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(this, L"PreviousTelemetryOptInFound", L"TRUE");
    appended = v95;
    if ( v95 < 0 )
    {
      LODWORD(v112) = v95;
      v5 = -23;
      v111 = "Error adding init property to bag: [0x%x].";
      goto LABEL_8;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x1E9u,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
        "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
        "Error adding init property to bag: [0x%x].",
        v95);
    v96 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(this, L"PreviouslyOptedInToCoreTelemetry", pvData & 1);
    appended = v96;
    if ( v96 < 0 )
    {
      LODWORD(v112) = v96;
      v5 = -20;
      v111 = "Error adding init property to bag: [0x%x].";
      goto LABEL_8;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x1ECu,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
        "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
        "Error adding init property to bag: [0x%x].",
        v96);
    v97 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
            this,
            L"PreviouslyOptedInToGeneralTelemetry",
            (pvData & 2) != 0);
    appended = v97;
    if ( v97 < 0 )
    {
      LODWORD(v112) = v97;
      v5 = -17;
      v111 = "Error adding init property to bag: [0x%x].";
      goto LABEL_8;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    {
      v98 = 495;
LABEL_323:
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        v98,
        "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
        "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
        "Error adding init property to bag: [0x%x].",
        appended);
    }
  }
  v100 = Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(
           v139,
           0x28u,
           (unsigned __int16 *)&szValueBuf,
           (unsigned __int16 *)Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
           L"InboxTelemetryLastSuccessfulSyncId");
  v101 = v100;
  if ( v100 < 0 )
  {
    LODWORD(v112) = v100;
    LODWORD(v110) = v100;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      252,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      (const char *)v110,
      (int)"Failed to get diff sync ID, swallowing: [0x%x].",
      v112);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v137);
    v102 = (volatile signed __int64 *)v137;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v102 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v102,
      _InterlockedExchangeAdd64(v102 + 17, 0),
      v138);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v103);
    v104 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      LODWORD(v126) = v101;
      v127 = (unsigned __int64)v138;
      v133[0] = "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties";
      v131 = (const char *)&szValueBuf;
      v132 = "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp";
      LODWORD(v119) = 508;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v117 = (unsigned __int64)&v135;
      v135 = SystemTime;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v104,
        (__int64)byte_1802A0A0D,
        v105,
        v106,
        (__int64 *)&v117,
        (const size_t **)&v131,
        (__int64)&v119,
        &v132,
        v133,
        (__int64)&v126,
        (const char **)&v127);
    }
LABEL_333:
    v107 = 0;
    goto LABEL_334;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x1FCu,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Failed to get diff sync ID, swallowing: [0x%x].",
      v100);
  if ( !v139[0] )
    goto LABEL_333;
  v107 = 1;
LABEL_334:
  if ( !v107 )
    v85 = L"FALSE";
  v108 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(this, L"DiffSyncIdIsSet", v85);
  appended = v108;
  if ( v108 < 0 )
  {
    LODWORD(v112) = v108;
    v5 = 1;
    v111 = "Error adding init property to bag: [0x%x].";
    goto LABEL_8;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x201u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryscheduler.cpp",
      "Windows::Compat::Appraiser::TelemetryScheduler::AppendRegkeyRunProperties",
      "Error adding init property to bag: [0x%x].",
      v108);
  return 0;
}

```

## disassembly

```asm
0x180053e24  push    rbp
0x180053e26  push    rbx
0x180053e27  push    rsi
0x180053e28  push    rdi
0x180053e29  push    r12
0x180053e2b  push    r13
0x180053e2d  push    r14
0x180053e2f  push    r15
0x180053e31  lea     rbp, [rsp-9D8h]
0x180053e39  sub     rsp, 0AD8h
0x180053e40  mov     rax, cs:__security_cookie
0x180053e47  xor     rax, rsp
0x180053e4a  mov     [rbp+0A10h+var_50], rax
0x180053e51  xor     r15d, r15d
0x180053e54  mov     r13, rcx
0x180053e57  xorps   xmm0, xmm0
0x180053e5a  mov     [rbp+0A10h+var_A74], r15b
0x180053e5e  xor     edx, edx; Val
0x180053e60  mov     [rsp+0B10h+pvData], r15d
0x180053e65  lea     rcx, [rbp+0A10h+var_8E0]; void *
0x180053e6c  mov     [rbp+0A10h+var_A80], r15
0x180053e70  lea     r8d, [r15+50h]; Size
0x180053e74  mov     [rbp+0A10h+var_A90], r15b
0x180053e78  movups  xmmword ptr [rbp+0A10h+Guid.Data1], xmm0
0x180053e7c  mov     [rbp+0A10h+var_A78], r15b
0x180053e80  mov     [rbp+0A10h+var_A77], r15b
0x180053e84  mov     [rbp+0A10h+var_A76], r15b
0x180053e88  mov     [rbp+0A10h+var_A75], r15b
0x180053e8c  mov     [rbp+0A10h+var_A60], r15d
0x180053e90  mov     [rbp+0A10h+var_A5C], r15d
0x180053e94  mov     [rbp+0A10h+var_A58], r15d
0x180053e98  call    memset_0
0x180053e9d  call    ?Now@Utilities@Appraiser@Compat@Windows@@SA_KXZ; Windows::Compat::Appraiser::Utilities::Now(void)
0x180053ea2  mov     [rbp+0A10h+var_A70], rax
0x180053ea6  lea     rdi, aFailedruncount; "FailedRunCount"
0x180053ead  mov     rax, cs:?RegistryPathAppraiser@WicaFactory@Appraiser@Compat@Windows@@2PEAGEA; ushort * Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser
0x180053eb4  lea     r8d, [r15+10h]; unsigned int
0x180053eb8  mov     [rsp+0B10h+var_AE8], rdi; unsigned __int16 *
0x180053ebd  lea     rdx, [rbp+0A10h+var_A88]; unsigned __int64 *
0x180053ec1  lea     rcx, [rsp+0B10h+pvData]; pvData
0x180053ec6  mov     [rsp+0B10h+var_AF0], rax; unsigned __int16 *
0x180053ecb  mov     [rsp+0B10h+pvData], r15d
0x180053ed0  mov     [rbp+0A10h+var_A88], 4
0x180053ed8  call    ?ReadValue@Registry@Shared@Compat@Windows@@SAJPEAEAEA_KKPEAUHKEY__@@PEBG3@Z; Windows::Compat::Shared::Registry::ReadValue(uchar *,unsigned __int64 &,ulong,HKEY__ *,ushort const *,ushort const *)
0x180053edd  mov     ebx, eax
0x180053edf  cmp     eax, 80070002h
0x180053ee4  jnz     loc_180053F8A
0x180053eea  mov     [rsp+0B10h+pvData], r15d
0x180053eef  mov     ebx, r15d
0x180053ef2  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180053ef8  lea     r12, aErrorReadingRe_0; "Error reading registry value %ls / %ls:"...
0x180053eff  mov     edi, 1
0x180053f04  lea     rsi, aWindowsCompatA_287; "Windows::Compat::Appraiser::TelemetrySc"...
0x180053f0b  and     eax, edi
0x180053f0d  lea     r14, aOnecoreBaseApp_78; "onecore\\base\\appcompat\\appraiser\\he"...
0x180053f14  test    al, al
0x180053f16  jz      short loc_180053F45
0x180053f18  lea     rax, aFailedruncount; "FailedRunCount"
0x180053f1f  mov     dword ptr [rsp+0B10h+var_AE0], ebx
0x180053f23  mov     [rsp+0B10h+var_AE8], rax
0x180053f28  lea     ecx, [rdi+7Fh]; unsigned int
0x180053f2b  mov     rax, cs:?RegistryPathAppraiser@WicaFactory@Appraiser@Compat@Windows@@2PEAGEA; ushort * Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser
0x180053f32  mov     r9, r12; char *
0x180053f35  mov     r8, rsi; char *
0x180053f38  mov     [rsp+0B10h+var_AF0], rax
0x180053f3d  mov     rdx, r14; char *
0x180053f40  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180053f45  mov     r8d, [rsp+0B10h+pvData]; unsigned int
0x180053f4a  lea     rdx, aCurrentfailure; "CurrentFailureCount"
0x180053f51  mov     rcx, r13; this
0x180053f54  call    ?AppendDwordInitProperty@TelemetryScheduler@Appraiser@Compat@Windows@@CAJAEAVPropertyBag@234@PEBGK@Z; Windows::Compat::Appraiser::TelemetryScheduler::AppendDwordInitProperty(Windows::Compat::Appraiser::PropertyBag &,ushort const *,ulong)
0x180053f59  lea     r15, aErrorAppending_2; "Error appending property: [0x%x]."
0x180053f60  mov     ebx, eax
0x180053f62  test    eax, eax
0x180053f64  jns     short loc_180053FD7
0x180053f66  mov     edx, 83h; bool
0x180053f6b  mov     dword ptr [rsp+0B10h+var_AE0], ebx; char *
0x180053f6f  mov     [rsp+0B10h+var_AE8], r15; int
0x180053f74  mov     dword ptr [rsp+0B10h+var_AF0], ebx; char *
0x180053f78  mov     r9, rsi; char *
0x180053f7b  mov     r8, r14; unsigned int
0x180053f7e  mov     ecx, edi; this
0x180053f80  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180053f85  jmp     loc_180055E3D
0x180053f8a  test    ebx, ebx
0x180053f8c  jns     loc_180053EF2
0x180053f92  mov     edx, 80h; bool
0x180053f97  mov     dword ptr [rsp+0B10h+var_AD0], ebx
0x180053f9b  mov     [rsp+0B10h+var_AD8], rdi
0x180053fa0  lea     r12, aErrorReadingRe_0; "Error reading registry value %ls / %ls:"...
0x180053fa7  lea     r9, aWindowsCompatA_287; "Windows::Compat::Appraiser::TelemetrySc"...
0x180053fae  lea     r8, aOnecoreBaseApp_78; "onecore\\base\\appcompat\\appraiser\\he"...
0x180053fb5  lea     ecx, [rdx-7Fh]; this
0x180053fb8  mov     rax, cs:?RegistryPathAppraiser@WicaFactory@Appraiser@Compat@Windows@@2PEAGEA; ushort * Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser
0x180053fbf  mov     [rsp+0B10h+var_AE0], rax; char *
0x180053fc4  mov     [rsp+0B10h+var_AE8], r12; int
0x180053fc9  mov     dword ptr [rsp+0B10h+var_AF0], ebx; char *
0x180053fcd  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180053fd2  jmp     loc_180055E3D
0x180053fd7  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180053fdd  and     eax, edi
0x180053fdf  test    al, al
0x180053fe1  jz      short loc_180053FFA
0x180053fe3  mov     r9, r15; char *
0x180053fe6  mov     dword ptr [rsp+0B10h+var_AF0], ebx
0x180053fea  mov     r8, rsi; char *
0x180053fed  mov     rdx, r14; char *
0x180053ff0  mov     ecx, 83h; unsigned int
0x180053ff5  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180053ffa  mov     rax, cs:?RegistryPathAppraiser@WicaFactory@Appraiser@Compat@Windows@@2PEAGEA; ushort * Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser
0x180054001  lea     rcx, aOfflinecount; "OfflineCount"
0x180054008  mov     [rsp+0B10h+var_AE8], rcx; unsigned __int16 *
0x18005400d  lea     rdx, [rbp+0A10h+var_A88]; unsigned __int64 *
0x180054011  lea     rcx, [rsp+0B10h+pvData]; pvData
0x180054016  mov     [rsp+0B10h+pvData], 0
0x18005401e  mov     r8d, 10h; unsigned int
0x180054024  mov     [rbp+0A10h+var_A88], 4
0x18005402c  mov     [rsp+0B10h+var_AF0], rax; unsigned __int16 *
0x180054031  call    ?ReadValue@Registry@Shared@Compat@Windows@@SAJPEAEAEA_KKPEAUHKEY__@@PEBG3@Z; Windows::Compat::Shared::Registry::ReadValue(uchar *,unsigned __int64 &,ulong,HKEY__ *,ushort const *,ushort const *)
0x180054036  mov     ebx, eax
0x180054038  cmp     eax, 80070002h
0x18005403d  jnz     short loc_180054092
0x18005403f  xor     eax, eax
0x180054041  mov     [rsp+0B10h+pvData], eax
0x180054045  mov     ebx, eax
0x180054047  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18005404d  and     eax, edi
0x18005404f  test    al, al
0x180054051  jz      short loc_18005406E
0x180054053  lea     r9, aErrorReadingRe; "Error reading registry value: [0x%x]."
0x18005405a  mov     dword ptr [rsp+0B10h+var_AF0], ebx
0x18005405e  mov     r8, rsi; char *
0x180054061  mov     rdx, r14; char *
0x180054064  mov     ecx, 8Ah; unsigned int
0x180054069  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18005406e  mov     r8d, [rsp+0B10h+pvData]; unsigned int
0x180054073  lea     rdx, aCurrentoffline; "CurrentOfflineCount"
0x18005407a  mov     rcx, r13; this
0x18005407d  call    ?AppendDwordInitProperty@TelemetryScheduler@Appraiser@Compat@Windows@@CAJAEAVPropertyBag@234@PEBGK@Z; Windows::Compat::Appraiser::TelemetryScheduler::AppendDwordInitProperty(Windows::Compat::Appraiser::PropertyBag &,ushort const *,ulong)
0x180054082  mov     ebx, eax
0x180054084  test    eax, eax
0x180054086  jns     short loc_1800540B0
0x180054088  mov     edx, 8Dh
0x18005408d  jmp     loc_180053F6B
0x180054092  test    ebx, ebx
0x180054094  jns     short loc_180054047
0x180054096  lea     rax, aErrorReadingRe; "Error reading registry value: [0x%x]."
0x18005409d  mov     dword ptr [rsp+0B10h+var_AE0], ebx
0x1800540a1  mov     [rsp+0B10h+var_AE8], rax
0x1800540a6  mov     edx, 8Ah
0x1800540ab  jmp     loc_180053F74
0x1800540b0  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800540b6  and     eax, edi
0x1800540b8  test    al, al
0x1800540ba  jz      short loc_1800540D3
0x1800540bc  mov     r9, r15; char *
0x1800540bf  mov     dword ptr [rsp+0B10h+var_AF0], ebx
0x1800540c3  mov     r8, rsi; char *
0x1800540c6  mov     rdx, r14; char *
0x1800540c9  mov     ecx, 8Dh; unsigned int
0x1800540ce  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800540d3  xor     r9d, r9d; Context
0x1800540d6  lea     rdx, ?InitOnceCallback@AppraiserTestHooks@Appraiser@Compat@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800540dd  xor     r8d, r8d; Parameter
0x1800540e0  lea     rcx, ?InitOnce@AppraiserTestHooks@Appraiser@Compat@Windows@@0T_RTL_RUN_ONCE@@A; InitOnce
0x1800540e7  call    cs:__imp_InitOnceExecuteOnce
0x1800540ed  cmp     cs:?TestHookAlwaysSendUtc@AppraiserTestHooks@Appraiser@Compat@Windows@@0_NA, 0; bool Windows::Compat::Appraiser::AppraiserTestHooks::TestHookAlwaysSendUtc
0x1800540f4  jz      short loc_180054153
0x1800540f6  lea     r8, aTrue_2; "TRUE"
0x1800540fd  mov     rcx, r13; this
0x180054100  lea     rdx, aTesthookutcalw; "TestHookUtcAlwaysSend"
0x180054107  call    ?AppendProperty@PropertyBag@Appraiser@Compat@Windows@@QEAAJPEBG0@Z; Windows::Compat::Appraiser::PropertyBag::AppendProperty(ushort const *,ushort const *)
0x18005410c  mov     ebx, eax
0x18005410e  test    eax, eax
0x180054110  jns     short loc_18005412C
0x180054112  lea     r9, aErrorAddingIni; "Error adding init property to bag: [0x%"...
0x180054119  mov     dword ptr [rsp+0B10h+var_AE0], eax
0x18005411d  mov     [rsp+0B10h+var_AE8], r9
0x180054122  mov     edx, 96h
0x180054127  jmp     loc_180053F74
0x18005412c  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180054132  and     eax, edi
0x180054134  test    al, al
0x180054136  jz      short loc_180054153
0x180054138  lea     r9, aErrorAddingIni; "Error adding init property to bag: [0x%"...
0x18005413f  mov     dword ptr [rsp+0B10h+var_AF0], ebx
0x180054143  mov     r8, rsi; char *
0x180054146  mov     rdx, r14; char *
0x180054149  mov     ecx, 96h; unsigned int
0x18005414e  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180054153  lea     rax, aUtconetimesend; "UtcOnetimeSend"
0x18005415a  mov     dword ptr [rbp+0A10h+var_A88], 0
0x180054161  mov     [rsp+0B10h+var_AE8], rax; unsigned __int16 *
0x180054166  lea     rdx, [rsp+0B10h+var_A98]; unsigned __int64 *
0x18005416b  mov     rax, cs:?RegistryPathAppraiser@WicaFactory@Appraiser@Compat@Windows@@2PEAGEA; ushort * Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser
0x180054172  lea     rcx, [rbp+0A10h+var_A88]; pvData
0x180054176  mov     r8d, 10h; unsigned int
0x18005417c  mov     [rsp+0B10h+var_AF0], rax; unsigned __int16 *
0x180054181  mov     [rsp+0B10h+var_A98], 4
0x18005418a  call    ?ReadValue@Registry@Shared@Compat@Windows@@SAJPEAEAEA_KKPEAUHKEY__@@PEBG3@Z; Windows::Compat::Shared::Registry::ReadValue(uchar *,unsigned __int64 &,ulong,HKEY__ *,ushort const *,ushort const *)
0x18005418f  xor     r8d, r8d
0x180054192  mov     r9d, 80070002h
0x180054198  cmp     dword ptr [rbp+0A10h+var_A88], r8d
0x18005419c  mov     ebx, r8d
0x18005419f  mov     edx, r8d
0x1800541a2  setnz   cl
0x1800541a5  cmp     eax, r9d
0x1800541a8  movzx   ecx, cl
0x1800541ab  cmovnz  edx, ecx
0x1800541ae  cmovnz  ebx, eax
0x1800541b1  mov     dword ptr [rbp+0A10h+var_A88], edx
0x1800541b4  test    ebx, ebx
0x1800541b6  jns     short loc_1800541DA
0x1800541b8  lea     rax, aUtconetimesend; "UtcOnetimeSend"
0x1800541bf  mov     edx, 9Eh
0x1800541c4  mov     dword ptr [rsp+0B10h+var_AD0], ebx
0x1800541c8  mov     r9, rsi
0x1800541cb  mov     [rsp+0B10h+var_AD8], rax
0x1800541d0  mov     r8, r14
0x1800541d3  mov     ecx, edi
0x1800541d5  jmp     loc_180053FB8
0x1800541da  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800541e0  and     eax, edi
0x1800541e2  test    al, al
0x1800541e4  jz      short loc_18005421B
0x1800541e6  lea     rax, aUtconetimesend; "UtcOnetimeSend"
0x1800541ed  mov     dword ptr [rsp+0B10h+var_AE0], ebx
0x1800541f1  mov     [rsp+0B10h+var_AE8], rax
0x1800541f6  mov     r9, r12; char *
0x1800541f9  mov     rax, cs:?RegistryPathAppraiser@WicaFactory@Appraiser@Compat@Windows@@2PEAGEA; ushort * Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser
0x180054200  mov     r8, rsi; char *
0x180054203  mov     rdx, r14; char *
0x180054206  mov     [rsp+0B10h+var_AF0], rax
0x18005420b  mov     ecx, 9Eh; unsigned int
0x180054210  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180054215  mov     edx, dword ptr [rbp+0A10h+var_A88]
0x180054218  xor     r8d, r8d
0x18005421b  test    dl, dl
0x18005421d  jz      short loc_180054282
0x18005421f  lea     r8, aTrue_2; "TRUE"
0x180054226  mov     rcx, r13; this
0x180054229  lea     rdx, aManifestedutco; "ManifestedUtcOnetimeSend"
0x180054230  call    ?AppendProperty@PropertyBag@Appraiser@Compat@Windows@@QEAAJPEBG0@Z; Windows::Compat::Appraiser::PropertyBag::AppendProperty(ushort const *,ushort const *)
0x180054235  xor     r8d, r8d
0x180054238  mov     ebx, eax
0x18005423a  test    eax, eax
0x18005423c  jns     short loc_180054258
0x18005423e  mov     dword ptr [rsp+0B10h+var_AE0], eax
0x180054242  mov     edx, 0A2h
0x180054247  lea     rax, aErrorAddingIni; "Error adding init property to bag: [0x%"...
0x18005424e  mov     [rsp+0B10h+var_AE8], rax
0x180054253  jmp     loc_180053F74
0x180054258  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18005425e  and     eax, edi
0x180054260  test    al, al
0x180054262  jz      short loc_180054282
0x180054264  lea     r9, aErrorAddingIni; "Error adding init property to bag: [0x%"...
0x18005426b  mov     dword ptr [rsp+0B10h+var_AF0], ebx
0x18005426f  mov     r8, rsi; char *
0x180054272  mov     rdx, r14; char *
0x180054275  mov     ecx, 0A2h; unsigned int
0x18005427a  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18005427f  xor     r8d, r8d
0x180054282  lea     rax, aGentelutconeti; "GenTelUtcOnetimeSend"
0x180054289  mov     dword ptr [rbp+0A10h+var_A88], r8d
0x18005428d  mov     [rsp+0B10h+var_AE8], rax; unsigned __int16 *
0x180054292  lea     rdx, [rsp+0B10h+var_A98]; unsigned __int64 *
0x180054297  mov     rax, cs:?RegistryPathAppraiser@WicaFactory@Appraiser@Compat@Windows@@2PEAGEA; ushort * Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser
0x18005429e  lea     rcx, [rbp+0A10h+var_A88]; pvData
0x1800542a2  mov     r8d, 10h; unsigned int
0x1800542a8  mov     [rsp+0B10h+var_AF0], rax; unsigned __int16 *
0x1800542ad  mov     [rsp+0B10h+var_A98], 4
0x1800542b6  call    ?ReadValue@Registry@Shared@Compat@Windows@@SAJPEAEAEA_KKPEAUHKEY__@@PEBG3@Z; Windows::Compat::Shared::Registry::ReadValue(uchar *,unsigned __int64 &,ulong,HKEY__ *,ushort const *,ushort const *)
0x1800542bb  xor     r8d, r8d
0x1800542be  mov     r9d, 80070002h
0x1800542c4  cmp     dword ptr [rbp+0A10h+var_A88], r8d
0x1800542c8  mov     ebx, r8d
0x1800542cb  mov     edx, r8d
0x1800542ce  setnz   cl
0x1800542d1  cmp     eax, r9d
0x1800542d4  movzx   ecx, cl
0x1800542d7  cmovnz  edx, ecx
0x1800542da  cmovnz  ebx, eax
0x1800542dd  mov     dword ptr [rbp+0A10h+var_A88], edx
0x1800542e0  test    ebx, ebx
0x1800542e2  jns     short loc_1800542F5
0x1800542e4  lea     rax, aGentelutconeti; "GenTelUtcOnetimeSend"
0x1800542eb  mov     edx, 0A6h
0x1800542f0  jmp     loc_1800541C4
0x1800542f5  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800542fb  and     eax, edi
0x1800542fd  test    al, al
0x1800542ff  jz      short loc_180054338
0x180054301  mov     rax, cs:?RegistryPathAppraiser@WicaFactory@Appraiser@Compat@Windows@@2PEAGEA; ushort * Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser
0x180054308  mov     r9, r12; char *
0x18005430b  mov     dword ptr [rsp+0B10h+var_AE0], ebx
0x18005430f  mov     r8, rsi; char *
0x180054312  lea     rbx, aGentelutconeti; "GenTelUtcOnetimeSend"
0x180054319  mov     rdx, r14; char *
0x18005431c  mov     [rsp+0B10h+var_AE8], rbx
  ... truncated ...
```
