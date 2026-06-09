# Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData(Windows::Compat::Appraiser::RunOptions *)

- ea: `0x180039538`
- end: `0x18003b299`
- name: `?GetAlternateData@SetupAppraiser@Appraiser@Compat@Windows@@AEAAJPEAURunOptions@234@@Z`
- size: `7521`
- prototype: `__int64 __fastcall(Windows::Compat::Appraiser::SetupAppraiser *__hidden this, struct Windows::Compat::Appraiser::RunOptions *)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180041020`

## callees

- `0x1800011d0`
- `0x18000147c`
- `0x1800018a0`
- `0x180001f18`
- `0x180008570`
- `0x180011d94`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180039538`
- `0x180044bb4`
- `0x180046c7c`
- `0x18008513c`
- `0x180086ec8`
- `0x18008762c`
- `0x18008b308`
- `0x18008bfbc`
- `0x180093cfc`
- `0x1800975e4`
- `0x18009b550`
- `0x18009edb8`
- `0x1801ac054`
- `0x1801afbd0`
- `0x180217460`
- `0x1802174cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18003a418`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18003b166`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18003a418`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18003b166`
- `KERNEL32!InitOnceExecuteOnce` at `0x1800395b1`
- `KERNEL32!InitOnceExecuteOnce` at `0x180039abe`
- `KERNEL32!InitOnceExecuteOnce` at `0x180039ae3`
- `KERNEL32!InitOnceExecuteOnce` at `0x180039ccd`
- `KERNEL32!InitOnceExecuteOnce` at `0x180039e66`
- `KERNEL32!InitOnceExecuteOnce` at `0x1800395b1`
- `KERNEL32!InitOnceExecuteOnce` at `0x180039abe`
- `KERNEL32!InitOnceExecuteOnce` at `0x180039ae3`
- `KERNEL32!InitOnceExecuteOnce` at `0x180039ccd`
- `KERNEL32!InitOnceExecuteOnce` at `0x180039e66`
- `KERNEL32!MoveFileExW` at `0x18003a9b8`
- `KERNEL32!MoveFileExW` at `0x18003acac`
- `KERNEL32!MoveFileExW` at `0x18003ae64`
- `KERNEL32!MoveFileExW` at `0x18003a9b8`
- `KERNEL32!MoveFileExW` at `0x18003acac`
- `KERNEL32!MoveFileExW` at `0x18003ae64`
- `KERNEL32!DeleteFileW` at `0x18003a2a7`
- `KERNEL32!DeleteFileW` at `0x18003a2a7`
- `KERNEL32!GetSystemTime` at `0x18003971b`
- `KERNEL32!GetSystemTime` at `0x180039c12`
- `KERNEL32!GetSystemTime` at `0x180039de6`
- `KERNEL32!GetSystemTime` at `0x180039f26`
- `KERNEL32!GetSystemTime` at `0x18003a096`
- `KERNEL32!GetSystemTime` at `0x18003a20a`
- `KERNEL32!GetSystemTime` at `0x18003a366`
- `KERNEL32!GetSystemTime` at `0x18003a5ab`
- `KERNEL32!GetSystemTime` at `0x18003a763`
- `KERNEL32!GetSystemTime` at `0x18003a929`
- `KERNEL32!GetSystemTime` at `0x18003aac8`
- `KERNEL32!GetSystemTime` at `0x18003add3`
- `KERNEL32!GetSystemTime` at `0x18003971b`
- `KERNEL32!GetSystemTime` at `0x180039c12`
- `KERNEL32!GetSystemTime` at `0x180039de6`
- `KERNEL32!GetSystemTime` at `0x180039f26`
- `KERNEL32!GetSystemTime` at `0x18003a096`
- `KERNEL32!GetSystemTime` at `0x18003a20a`
- `KERNEL32!GetSystemTime` at `0x18003a366`
- `KERNEL32!GetSystemTime` at `0x18003a5ab`
- `KERNEL32!GetSystemTime` at `0x18003a763`
- `KERNEL32!GetSystemTime` at `0x18003a929`
- `KERNEL32!GetSystemTime` at `0x18003aac8`
- `KERNEL32!GetSystemTime` at `0x18003add3`
- `KERNEL32!GetLastError` at `0x18003a9c6`
- `KERNEL32!GetLastError` at `0x18003a9e3`
- `KERNEL32!GetLastError` at `0x18003ab73`
- `KERNEL32!GetLastError` at `0x18003a9c6`
- `KERNEL32!GetLastError` at `0x18003a9e3`
- `KERNEL32!GetLastError` at `0x18003ab73`
- `SHLWAPI!PathFileExistsW` at `0x18003a429`
- `SHLWAPI!PathFileExistsW` at `0x18003a48e`
- `SHLWAPI!PathFileExistsW` at `0x18003ab3a`
- `SHLWAPI!PathFileExistsW` at `0x18003ac70`
- `SHLWAPI!PathFileExistsW` at `0x18003ae42`
- `SHLWAPI!PathFileExistsW` at `0x18003aecb`
- `SHLWAPI!PathFileExistsW` at `0x18003aee0`
- `SHLWAPI!PathFileExistsW` at `0x18003a429`
- `SHLWAPI!PathFileExistsW` at `0x18003a48e`
- `SHLWAPI!PathFileExistsW` at `0x18003ab3a`
- `SHLWAPI!PathFileExistsW` at `0x18003ac70`
- `SHLWAPI!PathFileExistsW` at `0x18003ae42`
- `SHLWAPI!PathFileExistsW` at `0x18003aecb`
- `SHLWAPI!PathFileExistsW` at `0x18003aee0`

## string_xrefs

- `0x1800395d8`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180039634`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003b03f`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180039d09`: `Error getting WIP configuration, swallowing: [0x%x].`
- `0x18003a0b4`: `Error getting WIP configuration, swallowing: [0x%x].`
- `0x180039608`: `AppraiserRes.dll`
- `0x180039624`: `Failed to combine path: [0x%x].`
- `0x18003b072`: `Failed to combine path: [0x%x].`
- `0x18003b0a9`: `Failed to combine path: [0x%x].`
- `0x1800395d1`: `Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData`
- `0x18003962d`: `Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData`
- `0x18003b038`: `Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData`
- `0x1800395c0`: `Skip ADL download registry testhook set, skipping check for latest ADL.`
- `0x1800398cf`: `Failed to override inbox data path for onesettings: [0x%x].`
- `0x1800398e9`: `Failed to override inbox data path for onesettings: [0x%x].`
- `0x18003b0d8`: `Failed to override inbox data path for onesettings: [0x%x].`
- `0x18003b0fb`: `Failed to override inbox data path for onesettings: [0x%x].`
- `0x180039922`: `Failed to check inbox data path for version: [0x%x].`
- `0x18003993f`: `Failed to check inbox data path for version: [0x%x].`
- `0x1800399b2`: `AltDataTemp.cab`
- `0x180039f9d`: `https://go.microsoft.com/fwlink/?linkid=2112329`
- `0x18003a7d6`: `Failed to download or verify new cab. Prevous cab still exists. Attempt to use the previous cab.`
- `0x18003a4d1`: `Failed to check/create directory, swallowing: [0x%x].`
- `0x18003ac4e`: `Failed to check/create directory, swallowing: [0x%x].`
- `0x18003af08`: `Failed to check downloaded data path for version: [0x%x].`
- `0x18003af25`: `Failed to check downloaded data path for version: [0x%x].`
- `0x18003a63a`: `Error downloading or extracting alternate cab, ADL link %ls; cab location %ls; Result: [0x%x]`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData(
        Windows::Compat::Appraiser::SetupAppraiser *this,
        struct Windows::Compat::Appraiser::RunOptions *a2)
{
  const WCHAR *v2; // rbx
  char v3; // di
  int ResourceToFile; // ebx
  unsigned __int8 v7; // r12
  HRESULT v8; // eax
  const char *v9; // r15
  volatile signed __int64 *v10; // rcx
  void **v11; // rdx
  __int64 v12; // r15
  const size_t *v13; // rdi
  __int64 v14; // rcx
  __int64 v15; // rax
  int v16; // ecx
  unsigned int v17; // ecx
  char v18; // dl
  const char *v19; // r9
  char v20; // dl
  unsigned int v21; // r15d
  __int64 v22; // rax
  int Random; // eax
  unsigned __int64 v24; // r9
  unsigned int v25; // r15d
  volatile signed __int64 *v26; // rcx
  void **v27; // rdx
  int v28; // ebx
  int v29; // r8d
  int v30; // r9d
  int WipConfigSettings; // eax
  unsigned int v32; // r15d
  volatile signed __int64 *v33; // rcx
  void **v34; // rdx
  int v35; // ebx
  int v36; // r8d
  int v37; // r9d
  unsigned __int8 v38; // r12
  volatile signed __int64 *v39; // rcx
  void **v40; // rdx
  int v41; // ebx
  int v42; // r8d
  int v43; // r9d
  int v44; // eax
  unsigned int v45; // r15d
  volatile signed __int64 *v46; // rcx
  void **v47; // rdx
  int v48; // ebx
  int v49; // r8d
  int v50; // r9d
  __int16 *v51; // rdx
  int v52; // eax
  unsigned int v53; // r15d
  volatile signed __int64 *v54; // rcx
  void **v55; // rdx
  volatile signed __int64 *v56; // rcx
  void **v57; // rdx
  int v58; // ebx
  int v59; // r8d
  int v60; // r9d
  const char *v61; // rax
  int v62; // eax
  __int64 v63; // r12
  const WCHAR *v64; // r15
  int v65; // eax
  volatile signed __int64 *v66; // rcx
  void **v67; // rdx
  int v68; // r15d
  int v69; // r8d
  int v70; // r9d
  int v71; // eax
  volatile signed __int64 *v72; // rcx
  void **v73; // rdx
  int v74; // r15d
  int v75; // r8d
  int v76; // r9d
  int *v77; // rdx
  struct _SYSTEMTIME *p_p_SystemTime; // rax
  int v79; // eax
  volatile signed __int64 *v80; // rcx
  void **v81; // rdx
  signed int LastError; // eax
  volatile signed __int64 *v83; // rcx
  void **v84; // rdx
  int v85; // r15d
  int v86; // r8d
  int v87; // r9d
  DWORD v88; // eax
  unsigned __int64 v89; // r9
  const char *v90; // r9
  char v91; // dl
  unsigned __int16 *v92; // r8
  void (*v93)(const unsigned __int16 *, void *); // r8
  void *v94; // r9
  HRESULT v95; // ebx
  int Cabinet; // eax
  volatile signed __int64 *v97; // rcx
  void **v98; // rdx
  int v99; // r15d
  int v100; // r8d
  int v101; // r9d
  unsigned int v102; // eax
  unsigned __int64 v103; // r9
  const unsigned __int16 *v104; // r8
  unsigned __int64 v105; // r9
  unsigned __int16 *v106; // r8
  unsigned __int64 v107; // r9
  const wchar_t *v108; // r8
  char v109; // di
  HRESULT v110; // eax
  char v111; // dl
  int v112; // eax
  char *v113; // rbx
  const wchar_t *v114; // rax
  __int64 v115; // rax
  int v116; // eax
  ULONG dwFlags; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsa; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsb; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsc; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsd; // [rsp+20h] [rbp-E0h]
  const char **v123; // [rsp+28h] [rbp-D8h]
  const char *v124; // [rsp+28h] [rbp-D8h]
  char *v125; // [rsp+30h] [rbp-D0h]
  char *v126; // [rsp+30h] [rbp-D0h]
  char *v127; // [rsp+30h] [rbp-D0h]
  char *v128; // [rsp+30h] [rbp-D0h]
  __int64 v129; // [rsp+40h] [rbp-C0h]
  const char **v130; // [rsp+40h] [rbp-C0h]
  char *v131; // [rsp+48h] [rbp-B8h]
  struct _SYSTEMTIME *v132; // [rsp+50h] [rbp-B0h]
  unsigned int v133; // [rsp+64h] [rbp-9Ch] BYREF
  bool v134; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v135; // [rsp+6Ch] [rbp-94h] BYREF
  char v136[8]; // [rsp+70h] [rbp-90h] BYREF
  struct _SYSTEMTIME *p_SystemTime; // [rsp+78h] [rbp-88h] BYREF
  char v138[8]; // [rsp+80h] [rbp-80h] BYREF
  char v139[8]; // [rsp+88h] [rbp-78h] BYREF
  PCWSTR pszPathIn[2]; // [rsp+90h] [rbp-70h] BYREF
  struct _SYSTEMTIME v141; // [rsp+A0h] [rbp-60h] BYREF
  const char *v142; // [rsp+B0h] [rbp-50h] BYREF
  const char *v143; // [rsp+B8h] [rbp-48h] BYREF
  const char *v144; // [rsp+C0h] [rbp-40h] BYREF
  bool v145; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v146; // [rsp+CCh] [rbp-34h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+D0h] [rbp-30h] BYREF
  struct _SYSTEMTIME v148; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v149[144]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v150[32]; // [rsp+180h] [rbp+80h] BYREF
  struct _SYSTEMTIME *v151; // [rsp+1A0h] [rbp+A0h]
  __int64 v152; // [rsp+1A8h] [rbp+A8h]
  const size_t *v153; // [rsp+1B0h] [rbp+B0h]
  __int64 v154; // [rsp+1B8h] [rbp+B8h]
  unsigned int *v155; // [rsp+1C0h] [rbp+C0h]
  __int64 v156; // [rsp+1C8h] [rbp+C8h]
  char *v157; // [rsp+1D0h] [rbp+D0h]
  __int64 v158; // [rsp+1D8h] [rbp+D8h]
  const size_t *v159; // [rsp+1E0h] [rbp+E0h]
  int v160; // [rsp+1E8h] [rbp+E8h]
  int v161; // [rsp+1ECh] [rbp+ECh]
  char *v162; // [rsp+1F0h] [rbp+F0h]
  __int64 v163; // [rsp+1F8h] [rbp+F8h]
  struct _SYSTEMTIME *v164; // [rsp+200h] [rbp+100h]
  __int64 v165; // [rsp+208h] [rbp+108h]
  char *v166; // [rsp+210h] [rbp+110h]
  int v167; // [rsp+218h] [rbp+118h]
  int v168; // [rsp+21Ch] [rbp+11Ch]
  unsigned __int16 v169[16]; // [rsp+220h] [rbp+120h] BYREF
  char v170[144]; // [rsp+240h] [rbp+140h] BYREF
  WCHAR pszPath[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+4E0h] [rbp+3E0h] BYREF
  WCHAR FileName[264]; // [rsp+6F0h] [rbp+5F0h] BYREF
  WCHAR NewFileName[264]; // [rsp+900h] [rbp+800h] BYREF
  WCHAR v175[264]; // [rsp+B10h] [rbp+A10h] BYREF
  WCHAR pszPathOut[264]; // [rsp+D20h] [rbp+C20h] BYREF
  WCHAR v177[264]; // [rsp+F30h] [rbp+E30h] BYREF
  unsigned __int16 v178[264]; // [rsp+1140h] [rbp+1040h] BYREF

  v2 = (const WCHAR *)*((_QWORD *)a2 + 6);
  v3 = 0;
  *((_QWORD *)a2 + 10) = &szValueBuf;
  *(_QWORD *)v139 = this;
  v146 = 0;
  v134 = 0;
  v135 = 0;
  v133 = 0;
  pszPathIn[0] = v2;
  InitOnceExecuteOnce(
    &Windows::Compat::Appraiser::AppraiserTestHooks::InitOnce,
    Windows::Compat::Appraiser::AppraiserTestHooks::InitOnceCallback,
    0,
    0);
  if ( Windows::Compat::Appraiser::AppraiserTestHooks::TestHookSkipADLDownload )
  {
    Windows::Compat::Appraiser::WriteLog(
      0,
      57,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
      0,
      (int)"Skip ADL download registry testhook set, skipping check for latest ADL.",
      v125);
    return 0;
  }
  v7 = 0;
  if ( *((_BYTE *)a2 + 4) )
  {
    v109 = 1;
    if ( !Windows::Compat::Appraiser::AppraiserSettings::SettingsInitializedYet )
    {
      v110 = PathCchCombineEx(ExistingFileName, 0x104u, v2, L"Appraiser_Data.ini", dwFlags);
      ResourceToFile = v110;
      if ( v110 < 0 )
      {
        LODWORD(v125) = v110;
        v124 = "Failed to combine path: [0x%x].";
        v111 = 87;
LABEL_246:
        LODWORD(dwFlagsd) = ResourceToFile;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          v111,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
          dwFlagsd,
          (int)v124,
          v125);
        return (unsigned int)ResourceToFile;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x1257u,
          "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
          "Failed to combine path: [0x%x].",
          v110);
      v112 = Windows::Compat::Appraiser::DataFile::UseAlternateInboxDataPath(ExistingFileName, 0);
      ResourceToFile = v112;
      if ( v112 < 0 )
      {
        LODWORD(v125) = v112;
        v124 = "Failed to override inbox data path for onesettings: [0x%x].";
        v111 = 90;
        goto LABEL_246;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x125Au,
          "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
          "Failed to override inbox data path for onesettings: [0x%x].",
          v112);
    }
    v113 = (char *)this + 152;
    v114 = (const wchar_t *)Windows::Compat::Appraiser::PersistedData::Get((char *)this + 152, 14);
    if ( !v114 || wcscmp_0(L"TRUE", v114) )
      v109 = 0;
    *((_BYTE *)a2 + 7) = v109;
    v115 = Windows::Compat::Appraiser::PersistedData::Get(v113, 15);
    if ( v115 )
      v116 = _o__wtoi(v115);
    else
      v116 = 0;
    *(_DWORD *)((char *)a2 + 17) = v116;
    *((_QWORD *)a2 + 10) = Windows::Compat::Appraiser::PersistedData::Get(v113, 16);
    goto LABEL_260;
  }
  v8 = PathCchCombineEx(pszPathOut, 0x104u, *((PCWSTR *)a2 + 5), L"AppraiserRes.dll", dwFlags);
  v9 = "Failed to combine path: [0x%x].";
  ResourceToFile = v8;
  if ( v8 >= 0 )
  {
    v3 = 1;
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x114Cu,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
        "Failed to combine path: [0x%x].",
        v8);
    ResourceToFile = PathCchCombineEx(ExistingFileName, 0x104u, pszPathIn[0], L"Appraiser_Data.ini", (ULONG)dwFlagsa);
    if ( ResourceToFile < 0 )
    {
      v18 = 82;
LABEL_23:
      LODWORD(v125) = ResourceToFile;
      LODWORD(dwFlagsb) = ResourceToFile;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v18,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
        dwFlagsb,
        (int)v9,
        v125);
      v7 = 0;
      goto LABEL_7;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x1152u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
        "Failed to combine path: [0x%x].",
        ResourceToFile);
    ResourceToFile = Windows::Compat::Appraiser::Utilities::ExtractResourceToFile(v17, pszPathOut, ExistingFileName);
    if ( ResourceToFile < 0 )
    {
      v19 = "Failed to extract data file resource: [0x%x].";
      v20 = 85;
LABEL_28:
      LODWORD(v125) = ResourceToFile;
      LODWORD(dwFlagsb) = ResourceToFile;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v20,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
        dwFlagsb,
        (int)v19,
        v125);
      v7 = 0;
      goto LABEL_7;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x1155u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
        "Failed to extract data file resource: [0x%x].",
        ResourceToFile);
    ResourceToFile = Windows::Compat::Appraiser::DataFile::UseAlternateInboxDataPath(ExistingFileName, 0);
    if ( ResourceToFile < 0 )
    {
      v19 = "Failed to override inbox data path for onesettings: [0x%x].";
      v20 = 88;
      goto LABEL_28;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x1158u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
        "Failed to override inbox data path for onesettings: [0x%x].",
        ResourceToFile);
    ResourceToFile = Windows::Compat::Appraiser::DataFile::GetMetadataParameterFromFile(
                       &v133,
                       ExistingFileName,
                       L"AppraiserDataVersion");
    if ( ResourceToFile < 0 )
    {
      v19 = "Failed to check inbox data path for version: [0x%x].";
      v20 = 91;
      goto LABEL_28;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x115Bu,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
        "Failed to check inbox data path for version: [0x%x].",
        ResourceToFile);
    v9 = "Concat error: [0x%x].";
    ResourceToFile = PathCchCombineEx(pszPath, 0x104u, pszPathIn[0], L"AltData.cab", (ULONG)dwFlagsb);
    if ( ResourceToFile < 0 )
    {
      v18 = 98;
      goto LABEL_23;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x1162u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
        "Concat error: [0x%x].",
        ResourceToFile);
    ResourceToFile = PathCchCombineEx(FileName, 0x104u, pszPathIn[0], L"AltDataTemp.cab", (ULONG)dwFlagsb);
    if ( ResourceToFile < 0 )
    {
      v18 = 101;
      goto LABEL_23;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x1165u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
        "Concat error: [0x%x].",
        ResourceToFile);
    ResourceToFile = PathCchCombineEx(v177, 0x104u, pszPathIn[0], L"appraiser.sdb", (ULONG)dwFlagsb);
    if ( ResourceToFile < 0 )
    {
      v18 = 104;
      goto LABEL_23;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x1168u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
        "Concat error: [0x%x].",
        ResourceToFile);
    ResourceToFile = PathCchCombineEx(v175, 0x104u, pszPathIn[0], L"Appraiser_Data.ini", (ULONG)dwFlagsb);
    if ( ResourceToFile < 0 )
    {
      v18 = 107;
      goto LABEL_23;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x116Bu,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
        "Concat error: [0x%x].",
        ResourceToFile);
    if ( Windows::Compat::Appraiser::AppraiserSettings::SettingsInitializedYet )
    {
      Windows::Compat::Appraiser::AppraiserSettings::GetSettingsInternal();
      Windows::Compat::Appraiser::AppraiserSettings::SettingsInitializedYet = 1;
    }
    InitOnceExecuteOnce(
      &Windows::Compat::Appraiser::AppraiserSettings::InitOnce,
      Windows::Compat::Appraiser::AppraiserSettings::InitOnceCallback,
      0,
      0);
    *((_QWORD *)a2 + 10) = &Windows::Compat::Appraiser::AppraiserSettings::SettingSetupAlternateDataLink;
    InitOnceExecuteOnce(
      &Windows::Compat::Appraiser::AppraiserSettings::InitOnce,
      Windows::Compat::Appraiser::AppraiserSettings::InitOnceCallback,
      0,
      0);
    v21 = Windows::Compat::Appraiser::AppraiserSettings::SettingSetupAlternateDataVersion;
    *(_QWORD *)v139 += 152LL;
    v7 = 1;
    v22 = Windows::Compat::Appraiser::PersistedData::Get(*(_QWORD *)v139, 17);
    if ( !**((_WORD **)a2 + 10) )
    {
      Random = Windows::Compat::Appraiser::Utilities::GetRandom(&v146);
      v25 = Random;
      if ( Random >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x1189u,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
            "Error generating random number, swallowing: [0x%x].",
            Random);
        if ( v146 == 100 * (v146 / 0x64) )
        {
LABEL_71:
          WipConfigSettings = Windows::Compat::Appraiser::Utilities::GetWipConfigSettings(&v134, &v145, v178, v24);
          v32 = WipConfigSettings;
          if ( WipConfigSettings >= 0 )
          {
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x118Eu,
                "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
                "Error getting WIP configuration, swallowing: [0x%x].",
                WipConfigSettings);
            if ( v134 )
            {
LABEL_81:
              v38 = 0;
              TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v149);
              v39 = (volatile signed __int64 *)v149;
              if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
                v39 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
              TraceLoggingCorrelationVector::ToStringImpl(
                (TraceLoggingCorrelationVector *)v39,
                _InterlockedExchangeAdd64(v39 + 17, 0),
                v170);
              if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
                UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v40);
              v41 = qword_1802C9628;
              if ( *(_DWORD *)qword_1802C9628 > 5u
                && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
                && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
              {
                *(_QWORD *)v139 = 0x1000000;
                p_SystemTime = (struct _SYSTEMTIME *)v170;
                pszPathIn[0] = (PCWSTR)&szValueBuf;
                v141 = 0;
                GetSystemTime(&v141);
                *(_QWORD *)v136 = &SystemTime;
                SystemTime = v141;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
                  v41,
                  (unsigned int)&dword_18029D96C,
                  v42,
                  v43,
                  (__int64)v136,
                  (__int64)pszPathIn,
                  (__int64)v139,
                  (__int64)&p_SystemTime);
              }
              Windows::Compat::Appraiser::WriteLog(
                0,
                147,
                (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
                0,
                (int)"Performing ADL test download.",
                v125);
              v44 = Windows::Compat::Appraiser::Utilities::DownloadCabFile(
                      L"https://go.microsoft.com/fwlink/?linkid=2112329",
                      FileName);
              v45 = v44;
              if ( v44 >= 0 )
              {
                if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                  Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                    0x1196u,
                    "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                    "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
                    "Error downloading default cab file, swallowing: [0x%x].",
                    v44);
                v52 = Windows::Compat::Appraiser::Utilities::VerifySignatureRecursive(0, 0, FileName);
                v53 = v52;
                if ( v52 >= 0 )
                {
                  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                      0x119Bu,
                      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                      "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
                      "Failed to verify default cab signature, swallowing: [0x%x].",
                      v52);
                  v38 = 1;
                  DeleteFileW(FileName);
                  goto LABEL_117;
                }
                LODWORD(v126) = v52;
                LODWORD(dwFlagsc) = v52;
                Windows::Compat::Appraiser::WriteLog(
                  (Windows::Compat::Appraiser *)1,
                  155,
                  (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                  "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
                  dwFlagsc,
                  (int)"Failed to verify default cab signature, swallowing: [0x%x].",
                  v126);
                TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v149);
                v54 = (volatile signed __int64 *)v149;
                if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
                  v54 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
                TraceLoggingCorrelationVector::ToStringImpl(
                  (TraceLoggingCorrelationVector *)v54,
                  _InterlockedExchangeAdd64(v54 + 17, 0),
                  v170);
                if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
                  UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v55);
                v48 = qword_1802C9628;
                if ( *(_DWORD *)qword_1802C9628 <= 5u
                  || (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) == 0
                  || (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) != *(_QWORD *)(qword_1802C9628 + 24) )
                {
LABEL_117:
                  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v149);
                  v56 = (volatile signed __int64 *)v149;
                  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
                    v56 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
                  TraceLoggingCorrelationVector::ToStringImpl(
                    (TraceLoggingCorrelationVector *)v56,
                    _InterlockedExchangeAdd64(v56 + 17, 0),
                    v170);
                  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
                    UtcThrottle::Throttle(
                      (UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler,
                      v57);
                  v58 = qword_1802C9628;
                  if ( *(_DWORD *)qword_1802C9628 > 5u
                    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
                    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
                  {
                    *(_QWORD *)v139 = 0x1000000;
                    p_SystemTime = (struct _SYSTEMTIME *)v170;
                    v133 = v38;
                    pszPathIn[0] = (PCWSTR)&szValueBuf;
                    v141 = 0;
                    GetSystemTime(&v141);
                    *(_QWORD *)v136 = &SystemTime;
                    SystemTime = v141;
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
                      v58,
                      (unsigned int)word_18029D7F2,
                      v59,
                      v60,
                      (__int64)v136,
                      (__int64)pszPathIn,
                      (__int64)&v133,
                      (__int64)v139,
                      (__int64)&p_SystemTime);
                  }
                  v61 = "Succeeded";
                  if ( !v38 )
                    v61 = "Failed";
                  Windows::Compat::Appraiser::WriteLog(
                    0,
                    165,
                    (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                    "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
                    0,
                    (int)"ADL test download %hs.",
                    v61);
                  v7 = 1;
                  goto LABEL_128;
                }
                v133 = v53;
                p_SystemTime = (struct _SYSTEMTIME *)v170;
                *(_QWORD *)v139 = "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData";
                *(_QWORD *)v136 = &szValueBuf;
                pszPathIn[0] = (PCWSTR)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
                v135 = 4507;
                v141 = 0;
                GetSystemTime(&v141);
                v51 = &word_18029D8A6;
              }
              else
              {
                LODWORD(v126) = v44;
                LODWORD(dwFlagsc) = v44;
                Windows::Compat::Appraiser::WriteLog(
                  (Windows::Compat::Appraiser *)1,
                  150,
                  (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                  "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
                  dwFlagsc,
                  (int)"Error downloading default cab file, swallowing: [0x%x].",
                  v126);
                TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v149);
                v46 = (volatile signed __int64 *)v149;
                if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
                  v46 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
                TraceLoggingCorrelationVector::ToStringImpl(
                  (TraceLoggingCorrelationVector *)v46,
                  _InterlockedExchangeAdd64(v46 + 17, 0),
                  v170);
                if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
                  UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v47);
                v48 = qword_1802C9628;
                if ( *(_DWORD *)qword_1802C9628 <= 5u
                  || (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) == 0
                  || (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) != *(_QWORD *)(qword_1802C9628 + 24) )
                {
                  goto LABEL_117;
                }
                v133 = v45;
                p_SystemTime = (struct _SYSTEMTIME *)v170;
                *(_QWORD *)v139 = "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData";
                *(_QWORD *)v136 = &szValueBuf;
                pszPathIn[0] = (PCWSTR)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
                v135 = 4502;
                v141 = 0;
                GetSystemTime(&v141);
                v51 = (__int16 *)byte_18029D843;
              }
              *(_QWORD *)v138 = &SystemTime;
              SystemTime = v141;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v48,
                (_DWORD)v51,
                v49,
                v50,
                (__int64)v138,
                (__int64)v136,
                (__int64)&v135,
                (__int64)pszPathIn,
                (__int64)v139,
                (__int64)&v133,
                (__int64)&p_SystemTime);
              goto LABEL_117;
            }
          }
          else
          {
            LODWORD(v125) = WipConfigSettings;
            LODWORD(dwFlagsb) = WipConfigSettings;
            Windows::Compat::Appraiser::WriteLog(
              (Windows::Compat::Appraiser *)1,
              142,
              (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
              dwFlagsb,
              (int)"Error getting WIP configuration, swallowing: [0x%x].",
              v125);
            TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v149);
            v33 = (volatile signed __int64 *)v149;
            if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
              v33 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
            TraceLoggingCorrelationVector::ToStringImpl(
              (TraceLoggingCorrelationVector *)v33,
              _InterlockedExchangeAdd64(v33 + 17, 0),
              v170);
            if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
              UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v34);
            v35 = qword_1802C9628;
            if ( *(_DWORD *)qword_1802C9628 > 5u
              && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
              && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
            {
              v133 = v32;
              p_SystemTime = (struct _SYSTEMTIME *)v170;
              *(_QWORD *)v139 = "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData";
              *(_QWORD *)v136 = &szValueBuf;
              pszPathIn[0] = (PCWSTR)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
              v135 = 4494;
              v141 = 0;
              GetSystemTime(&v141);
              *(_QWORD *)v138 = &SystemTime;
              SystemTime = v141;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v35,
                (unsigned int)byte_18029D909,
                v36,
                v37,
                (__int64)v138,
                (__int64)v136,
                (__int64)&v135,
                (__int64)pszPathIn,
                (__int64)v139,
                (__int64)&v133,
                (__int64)&p_SystemTime);
            }
          }
          InitOnceExecuteOnce(
            &Windows::Compat::Appraiser::AppraiserTestHooks::InitOnce,
            Windows::Compat::Appraiser::AppraiserTestHooks::InitOnceCallback,
            0,
            0);
          if ( Windows::Compat::Appraiser::AppraiserTestHooks::TestHookForceAdlDownloadTest )
            goto LABEL_81;
LABEL_128:
          ResourceToFile = 1;
          goto LABEL_7;
        }
      }
      else
      {
        LODWORD(v125) = Random;
        LODWORD(dwFlagsb) = Random;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          137,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
          dwFlagsb,
          (int)"Error generating random number, swallowing: [0x%x].",
          v125);
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v149);
        v26 = (volatile signed __int64 *)v149;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v26 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v26,
          _InterlockedExchangeAdd64(v26 + 17, 0),
          v170);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v27);
        v28 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 > 5u
          && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
        {
          v133 = v25;
          *(_QWORD *)v139 = v170;
          pszPathIn[0] = (PCWSTR)"Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData";
          *(_QWORD *)v138 = &szValueBuf;
          *(_QWORD *)v136 = "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
          v135 = 4489;
          v141 = 0;
          GetSystemTime(&v141);
          p_SystemTime = &SystemTime;
          SystemTime = v141;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v28,
            (unsigned int)byte_18029D9B1,
            v29,
            v30,
            (__int64)&p_SystemTime,
            (__int64)v138,
            (__int64)&v135,
            (__int64)v136,
            (__int64)pszPathIn,
            (__int64)&v133,
            (__int64)v139);
        }
      }
      InitOnceExecuteOnce(
        &Windows::Compat::Appraiser::AppraiserTestHooks::InitOnce,
        Windows::Compat::Appraiser::AppraiserTestHooks::InitOnceCallback,
        0,
        0);
      if ( !Windows::Compat::Appraiser::AppraiserTestHooks::TestHookForceAdlDownloadTest )
        goto LABEL_128;
      goto LABEL_71;
    }
    *(_DWORD *)((char *)a2 + 17) = v21;
    if ( v22 )
      v62 = _o__wtoi(v22);
    else
      v62 = 0;
    *(_DWORD *)((char *)a2 + 21) = v62;
    if ( PathFileExistsW(pszPath)
      && (int)Windows::Compat::Appraiser::Utilities::VerifySignatureRecursive(0, 0, pszPath) >= 0 )
    {
      if ( *(_DWORD *)((char *)a2 + 21) == *(_DWORD *)((char *)a2 + 17) )
      {
        Windows::Compat::Appraiser::WriteLog(
          0,
          182,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
          0,
          (int)"Previously downloaded cab is identical to Onesettings ADL, skipping download and using previous cab.",
          v125);
LABEL_136:
        v63 = *(_QWORD *)v139;
LABEL_137:
        if ( !PathFileExistsW(pszPath)
          || (int)Windows::Compat::Appraiser::Utilities::VerifySignatureRecursive(0, 0, pszPath) < 0 )
        {
LABEL_148:
          LODWORD(v129) = ResourceToFile;
          LODWORD(dwFlagsb) = ResourceToFile;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            40,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
            dwFlagsb,
            (int)"Error downloading or extracting alternate cab, ADL link %ls; cab location %ls; Result: [0x%x]",
            *((const char **)a2 + 10),
            pszPath,
            v129);
          if ( *(_DWORD *)((char *)a2 + 17) <= v133 )
            ResourceToFile = 1;
          goto LABEL_6;
        }
        v64 = pszPathIn[0];
        v65 = Windows::Compat::Appraiser::Utilities::EnsureDirectoryExists(pszPathIn[0]);
        ResourceToFile = v65;
        if ( v65 < 0 )
        {
          LODWORD(v125) = v65;
          LODWORD(dwFlagsb) = v65;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            250,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
            dwFlagsb,
            (int)"Failed to check/create directory, swallowing: [0x%x].",
            v125);
          TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v149);
          v66 = (volatile signed __int64 *)v149;
          if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
            v66 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
          TraceLoggingCorrelationVector::ToStringImpl(
            (TraceLoggingCorrelationVector *)v66,
            _InterlockedExchangeAdd64(v66 + 17, 0),
            v170);
          if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
            UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v67);
          v68 = qword_1802C9628;
          if ( *(_DWORD *)qword_1802C9628 > 5u
            && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
            && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
          {
            *(_DWORD *)v136 = ResourceToFile;
            *(_QWORD *)&v141.wYear = v170;
            v144 = "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData";
            v142 = (const char *)&szValueBuf;
            v143 = "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
            *(_DWORD *)v138 = 4602;
            SystemTime = 0;
            GetSystemTime(&SystemTime);
            p_SystemTime = &v148;
            v148 = SystemTime;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v68,
              (unsigned int)byte_18029D603,
              v69,
              v70,
              (__int64)&p_SystemTime,
              (__int64)&v142,
              (__int64)v138,
              (__int64)&v143,
              (__int64)&v144,
              (__int64)v136,
              (__int64)&v141);
          }
          goto LABEL_148;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x11FAu,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
            "Failed to check/create directory, swallowing: [0x%x].",
            v65);
        if ( PathFileExistsW(ExistingFileName) )
        {
          v95 = PathCchCombineEx(NewFileName, 0x104u, v64, L"Alt_Appraiser_Data.ini", (ULONG)dwFlagsb);
          if ( v95 >= 0 && !MoveFileExW(ExistingFileName, NewFileName, 1u) )
          {
            LODWORD(dwFlagsb) = v95;
            Windows::Compat::Appraiser::WriteLog(
              (Windows::Compat::Appraiser *)1,
              11,
              (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
              dwFlagsb,
              (int)"Error moving existing resource file.",
              v125);
          }
        }
        Cabinet = DiagExtractCabinet(pszPath, v64, v93, v94);
        ResourceToFile = Cabinet;
        if ( Cabinet < 0 )
        {
          LODWORD(v125) = Cabinet;
          LODWORD(dwFlagsb) = Cabinet;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            17,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
            dwFlagsb,
            (int)"Failed to extract cab file: [0x%x].",
            v125);
          TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v149);
          v97 = (volatile signed __int64 *)v149;
          if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
            v97 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
          TraceLoggingCorrelationVector::ToStringImpl(
            (TraceLoggingCorrelationVector *)v97,
            _InterlockedExchangeAdd64(v97 + 17, 0),
            v170);
          if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
            UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v98);
          v99 = qword_1802C9628;
          if ( *(_DWORD *)qword_1802C9628 > 5u
            && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
            && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
          {
            *(_DWORD *)v136 = ResourceToFile;
            *(_QWORD *)&v141.wYear = v170;
            v144 = "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData";
            v142 = (const char *)&szValueBuf;
            v143 = "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
            *(_DWORD *)v138 = 4625;
            SystemTime = 0;
            GetSystemTime(&SystemTime);
            p_SystemTime = &v148;
            v148 = SystemTime;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v99,
              (unsigned int)&word_18029D666,
              v100,
              v101,
              (__int64)&p_SystemTime,
              (__int64)&v142,
              (__int64)v138,
              (__int64)&v143,
              (__int64)&v144,
              (__int64)v136,
              (__int64)&v141);
          }
          if ( PathFileExistsW(NewFileName) && !MoveFileExW(NewFileName, ExistingFileName, 1u) )
          {
            LODWORD(dwFlagsb) = ResourceToFile;
            Windows::Compat::Appraiser::WriteLog(
              (Windows::Compat::Appraiser *)1,
              29,
              (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
              dwFlagsb,
              (int)"Error moving existing resource file back.",
              v128);
          }
          goto LABEL_148;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x1211u,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
            "Failed to extract cab file: [0x%x].",
            Cabinet);
        *((_BYTE *)a2 + 7) = 0;
        if ( PathFileExistsW(v177) && PathFileExistsW(v175) )
        {
          ResourceToFile = Windows::Compat::Appraiser::DataFile::GetMetadataParameterFromFile(
                             &v135,
                             v175,
                             L"AppraiserDataVersion");
          if ( ResourceToFile < 0 )
          {
            v90 = "Failed to check downloaded data path for version: [0x%x].";
            v91 = 58;
            goto LABEL_195;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x123Au,
              "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
              "Failed to check downloaded data path for version: [0x%x].",
              ResourceToFile);
          v102 = *(_DWORD *)((char *)a2 + 17);
          if ( v102 < v135 )
            v102 = v135;
          *(_DWORD *)((char *)a2 + 17) = v102;
          if ( v133 <= v102 )
            *((_BYTE *)a2 + 7) = 1;
        }
        ResourceToFile = StringCchPrintfW(v169, 0xBu, L"%d", *(unsigned int *)((char *)a2 + 17));
        if ( ResourceToFile < 0 )
        {
          v90 = "Error printing value: [0x%x].";
          v91 = 69;
          goto LABEL_195;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x1245u,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
            "Error printing value: [0x%x].",
            ResourceToFile);
        v104 = L"FALSE";
        if ( *((_BYTE *)a2 + 7) )
          v104 = L"TRUE";
        RtlStringArray::Set((RtlStringArray *)(v63 + 168), 0xEu, v104, v103);
        v106 = L"_NONE_";
        if ( v169[0] )
          v106 = v169;
        RtlStringArray::Set((RtlStringArray *)(v63 + 168), 0xFu, v106, v105);
        v108 = (const wchar_t *)*((_QWORD *)a2 + 10);
        if ( !v108 || !*v108 )
          v108 = L"_NONE_";
        RtlStringArray::Set((RtlStringArray *)(v63 + 168), 0x10u, v108, v107);
        v7 = 1;
LABEL_260:
        ResourceToFile = 0;
        if ( !v7 )
          return (unsigned int)ResourceToFile;
        goto LABEL_7;
      }
    }
    else
    {
      v7 = 0;
    }
    v71 = Windows::Compat::Appraiser::Utilities::DownloadCabFile(*((const unsigned __int16 **)a2 + 10), FileName);
    ResourceToFile = v71;
    if ( v71 >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x11BFu,
          "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
          "Error downloading new cab file, swallowing: [0x%x].",
          v71);
      v79 = Windows::Compat::Appraiser::Utilities::VerifySignatureRecursive(0, 0, FileName);
      ResourceToFile = v79;
      if ( v79 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x11C7u,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
            "Failed to verify cab signature, swallowing: [0x%x].",
            v79);
        if ( MoveFileExW(FileName, pszPath, 1u) )
        {
          *(_DWORD *)((char *)a2 + 21) = *(_DWORD *)((char *)a2 + 17);
          ResourceToFile = StringCchPrintfW(v169, 0xBu, L"%d");
          if ( ResourceToFile < 0 )
          {
            v90 = "Error printing PreviousDownloadedADLVersion value: [0x%x].";
            v91 = -32;
LABEL_195:
            LODWORD(v125) = ResourceToFile;
            LODWORD(dwFlagsb) = ResourceToFile;
            Windows::Compat::Appraiser::WriteLog(
              (Windows::Compat::Appraiser *)1,
              v91,
              (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
              dwFlagsb,
              (int)v90,
              v125);
            goto LABEL_6;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x11E0u,
              "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
              "Error printing PreviousDownloadedADLVersion value: [0x%x].",
              ResourceToFile);
          v63 = *(_QWORD *)v139;
          v92 = L"_NONE_";
          if ( v169[0] )
            v92 = v169;
          RtlStringArray::Set((RtlStringArray *)(*(_QWORD *)v139 + 168LL), 0x11u, v92, v89);
          goto LABEL_137;
        }
        LastError = GetLastError();
        ResourceToFile = LastError;
        if ( LastError > 0 )
          ResourceToFile = (unsigned __int16)LastError | 0x80070000;
        if ( ResourceToFile >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          {
            v88 = GetLastError();
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x11D1u,
              "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
              "Error saving downloaded cab file, swallowing: [%d].",
              v88);
          }
        }
        else
        {
          LODWORD(v125) = GetLastError();
          LODWORD(dwFlagsb) = ResourceToFile;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            209,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
            dwFlagsb,
            (int)"Error saving downloaded cab file, swallowing: [%d].",
            v125);
          TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v149);
          v83 = (volatile signed __int64 *)v149;
          if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
            v83 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
          TraceLoggingCorrelationVector::ToStringImpl(
            (TraceLoggingCorrelationVector *)v83,
            _InterlockedExchangeAdd64(v83 + 17, 0),
            v170);
          if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
            UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v84);
          v85 = qword_1802C9628;
          if ( *(_DWORD *)qword_1802C9628 > 5u
            && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
            && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
          {
            *(_DWORD *)v136 = ResourceToFile;
            *(_QWORD *)&v141.wYear = v170;
            v144 = "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData";
            v142 = (const char *)&szValueBuf;
            v143 = "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
            *(_DWORD *)v138 = 4561;
            SystemTime = 0;
            GetSystemTime(&SystemTime);
            p_SystemTime = &v148;
            v148 = SystemTime;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v85,
              (unsigned int)byte_18029D6C9,
              v86,
              v87,
              (__int64)&p_SystemTime,
              (__int64)&v142,
              (__int64)v138,
              (__int64)&v143,
              (__int64)&v144,
              (__int64)v136,
              (__int64)&v141);
          }
        }
        if ( PathFileExistsW(pszPath)
          && (int)Windows::Compat::Appraiser::Utilities::VerifySignatureRecursive(0, 0, pszPath) >= 0 )
        {
          goto LABEL_162;
        }
        v7 = 0;
      }
      else
      {
        LODWORD(v125) = v79;
        LODWORD(dwFlagsb) = v79;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          199,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
          dwFlagsb,
          (int)"Failed to verify cab signature, swallowing: [0x%x].",
          v125);
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v149);
        v80 = (volatile signed __int64 *)v149;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v80 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v80,
          _InterlockedExchangeAdd64(v80 + 17, 0),
          v170);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v81);
        v74 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 > 5u
          && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
        {
          *(_DWORD *)v136 = ResourceToFile;
          *(_QWORD *)&v141.wYear = v170;
          v144 = "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData";
          v142 = (const char *)&szValueBuf;
          v143 = "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
          *(_DWORD *)v138 = 4551;
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          p_SystemTime = &v148;
          v77 = (int *)&byte_18029D78F;
          v132 = &v141;
          v131 = v136;
          v130 = &v144;
          v127 = v138;
          v123 = &v142;
          p_p_SystemTime = (struct _SYSTEMTIME *)&p_SystemTime;
          goto LABEL_160;
        }
      }
    }
    else
    {
      LODWORD(v125) = v71;
      LODWORD(dwFlagsb) = v71;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        191,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
        dwFlagsb,
        (int)"Error downloading new cab file, swallowing: [0x%x].",
        v125);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v149);
      v72 = (volatile signed __int64 *)v149;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v72 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v72,
        _InterlockedExchangeAdd64(v72 + 17, 0),
        v170);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v73);
      v74 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        *(_DWORD *)v138 = ResourceToFile;
        p_SystemTime = (struct _SYSTEMTIME *)v170;
        v142 = "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData";
        v144 = (const char *)&szValueBuf;
        v143 = "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
        *(_DWORD *)v136 = 4543;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        *(_QWORD *)&v141.wYear = &v148;
        v77 = &dword_18029D72C;
        v132 = (struct _SYSTEMTIME *)&p_SystemTime;
        v131 = v138;
        v130 = &v142;
        v127 = v136;
        v123 = &v144;
        p_p_SystemTime = &v141;
LABEL_160:
        v148 = SystemTime;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v74,
          (_DWORD)v77,
          v75,
          v76,
          (__int64)p_p_SystemTime,
          (__int64)v123,
          (__int64)v127,
          (__int64)&v143,
          (__int64)v130,
          (__int64)v131,
          (__int64)v132);
      }
    }
    if ( !v7 )
      goto LABEL_136;
LABEL_162:
    Windows::Compat::Appraiser::WriteLog(
      0,
      237,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
      0,
      (int)"Failed to download or verify new cab. Prevous cab still exists. Attempt to use the previous cab.",
      v125);
    *(_DWORD *)((char *)a2 + 17) = *(_DWORD *)((char *)a2 + 21);
    goto LABEL_136;
  }
  LODWORD(v125) = v8;
  LODWORD(dwFlagsa) = v8;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    76,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
    "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
    dwFlagsa,
    (int)"Failed to combine path: [0x%x].",
    v125);
LABEL_6:
  v7 = v3;
LABEL_7:
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v149);
  v10 = (volatile signed __int64 *)v149;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v10 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v10,
    _InterlockedExchangeAdd64(v10 + 17, 0),
    v170);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v11);
  v12 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    v13 = (const size_t *)*((_QWORD *)a2 + 10);
    *(_DWORD *)v136 = *((unsigned __int8 *)a2 + 7);
    *(_DWORD *)v138 = v7;
    *(_QWORD *)&v141.wYear = 0x1000000;
    v133 = ResourceToFile;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v14 = -1;
    v148 = SystemTime;
    v15 = -1;
    do
      ++v15;
    while ( v170[v15] );
    v168 = 0;
    v167 = v15 + 1;
    v164 = &v141;
    v162 = v136;
    v166 = v170;
    v165 = 8;
    v163 = 4;
    if ( v13 )
    {
      do
        ++v14;
      while ( *((_WORD *)v13 + v14) );
      v16 = 2 * v14 + 2;
    }
    else
    {
      v13 = &szValueBuf;
      v16 = 2;
    }
    v160 = v16;
    v157 = v138;
    v154 = 2;
    v155 = &v133;
    v159 = v13;
    v153 = &szValueBuf;
    v161 = 0;
    v151 = &v148;
    v158 = 4;
    v156 = 4;
    v152 = 16;
    tlgWriteTransfer_EventWriteTransfer(v12, &dword_18029D584, 0, 0, 10, v150);
  }
  LODWORD(v129) = ResourceToFile;
  LODWORD(v125) = *((_BYTE *)a2 + 7) != 0;
  Windows::Compat::Appraiser::WriteLog(
    0,
    106,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
    "Windows::Compat::Appraiser::SetupAppraiser::GetAlternateData",
    0,
    (int)"Setup alternate data in use [%d], Url [%ls], Result [0x%x].",
    v125,
    *((_QWORD *)a2 + 10),
    v129);
  return (unsigned int)ResourceToFile;
}

```

## disassembly

```asm
0x180039538  mov     [rsp-8+arg_10], rbx
0x18003953d  push    rbp
0x18003953e  push    rsi
0x18003953f  push    rdi
0x180039540  push    r12
0x180039542  push    r13
0x180039544  push    r14
0x180039546  push    r15
0x180039548  lea     rbp, [rsp-1260h]
0x180039550  mov     eax, 1360h
0x180039555  call    _alloca_probe
0x18003955a  sub     rsp, rax
0x18003955d  mov     rax, cs:__security_cookie
0x180039564  xor     rax, rsp
0x180039567  mov     [rbp+1290h+var_40], rax
0x18003956e  mov     rbx, [rdx+30h]
0x180039572  lea     rax, szValueBuf
0x180039579  xor     edi, edi
0x18003957b  mov     [rdx+50h], rax
0x18003957f  mov     r13, rdx
0x180039582  mov     qword ptr [rbp+1290h+var_1308], rcx
0x180039586  mov     r15, rcx
0x180039589  mov     [rbp+1290h+var_12C4], edi
0x18003958c  lea     rdx, ?InitOnceCallback@AppraiserTestHooks@Appraiser@Compat@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180039593  mov     [rsp+1390h+var_1328], dil
0x180039598  xor     r9d, r9d; Context
0x18003959b  mov     [rsp+1390h+var_1324], edi
0x18003959f  xor     r8d, r8d; Parameter
0x1800395a2  mov     [rsp+1390h+var_132C], edi
0x1800395a6  lea     rcx, ?InitOnce@AppraiserTestHooks@Appraiser@Compat@Windows@@0T_RTL_RUN_ONCE@@A; InitOnce
0x1800395ad  mov     [rbp+1290h+pszPathIn], rbx
0x1800395b1  call    cs:__imp_InitOnceExecuteOnce
0x1800395b7  cmp     cs:?TestHookSkipADLDownload@AppraiserTestHooks@Appraiser@Compat@Windows@@0_NA, dil; bool Windows::Compat::Appraiser::AppraiserTestHooks::TestHookSkipADLDownload
0x1800395be  jz      short loc_1800395F2
0x1800395c0  lea     rax, aSkipAdlDownloa; "Skip ADL download registry testhook set"...
0x1800395c7  mov     edx, 1139h; bool
0x1800395cc  mov     qword ptr [rsp+1390h+var_1368], rax; int
0x1800395d1  lea     r9, aWindowsCompatA_636; "Windows::Compat::Appraiser::SetupApprai"...
0x1800395d8  lea     r8, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800395df  mov     qword ptr [rsp+1390h+dwFlags], rdi; char *
0x1800395e4  xor     ecx, ecx; this
0x1800395e6  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800395eb  mov     ebx, edi
0x1800395ed  jmp     loc_18003B26D
0x1800395f2  mov     r12b, dil
0x1800395f5  mov     [rsp+1390h+var_1330], dil
0x1800395fa  cmp     [r13+4], dil
0x1800395fe  jnz     loc_18003B031
0x180039604  mov     r8, [r13+28h]; pszPathIn
0x180039608  lea     r9, pszMore; "AppraiserRes.dll"
0x18003960f  mov     r12d, 104h
0x180039615  lea     rcx, [rbp+1290h+pszPathOut]; pszPathOut
0x18003961c  mov     edx, r12d; cchPathOut
0x18003961f  call    PathCchCombineEx
0x180039624  lea     r15, aFailedToCombin_2; "Failed to combine path: [0x%x]."
0x18003962b  mov     ebx, eax
0x18003962d  lea     rsi, aWindowsCompatA_636; "Windows::Compat::Appraiser::SetupApprai"...
0x180039634  lea     r14, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x18003963b  test    eax, eax
0x18003963d  jns     loc_1800397B3
0x180039643  mov     dword ptr [rsp+1390h+var_1360], eax; char *
0x180039647  mov     r9, rsi; char *
0x18003964a  mov     qword ptr [rsp+1390h+var_1368], r15; int
0x18003964f  mov     r8, r14; unsigned int
0x180039652  mov     edx, 114Ch; bool
0x180039657  mov     [rsp+1390h+dwFlags], eax; char *
0x18003965b  mov     ecx, 1; this
0x180039660  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180039665  xor     r15d, r15d
0x180039668  mov     r12b, dil
0x18003966b  lea     rcx, [rbp+1290h+var_12A0]; this
0x18003966f  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180039674  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x18003967b  lea     rcx, [rbp+1290h+var_12A0]
0x18003967f  test    rax, rax
0x180039682  mov     rdx, r15
0x180039685  cmovnz  rcx, rax; this
0x180039689  lock xadd [rcx+88h], rdx; unsigned __int64
0x180039692  lea     r8, [rbp+1290h+var_1150]; char *
0x180039699  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18003969e  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r15b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1800396a5  jz      short loc_1800396B3
0x1800396a7  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x1800396ae  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x1800396b3  mov     r15, cs:qword_1802C9628
0x1800396ba  mov     eax, [r15]
0x1800396bd  cmp     eax, 5
0x1800396c0  jbe     loc_18003B22E
0x1800396c6  mov     rcx, [r15+18h]
0x1800396ca  mov     rdx, 200000000000h
0x1800396d4  mov     rax, [r15+10h]
0x1800396d8  test    rdx, rax
0x1800396db  jz      loc_18003B22E
0x1800396e1  mov     rax, rcx
0x1800396e4  and     rax, rdx
0x1800396e7  cmp     rax, rcx
0x1800396ea  jnz     loc_18003B22E
0x1800396f0  movzx   eax, byte ptr [r13+7]
0x1800396f5  lea     rcx, [rbp+1290h+SystemTime]; lpSystemTime
0x1800396f9  mov     rdi, [r13+50h]
0x1800396fd  xorps   xmm0, xmm0
0x180039700  mov     dword ptr [rsp+1390h+var_1320], eax
0x180039704  movzx   eax, r12b
0x180039708  mov     dword ptr [rbp+1290h+var_1310], eax
0x18003970b  mov     qword ptr [rbp+1290h+var_12F0.wYear], 1000000h
0x180039713  mov     [rsp+1390h+var_132C], ebx
0x180039717  movups  xmmword ptr [rbp+1290h+SystemTime.wYear], xmm0
0x18003971b  call    cs:__imp_GetSystemTime
0x180039721  movaps  xmm0, xmmword ptr [rbp+1290h+SystemTime.wYear]
0x180039725  lea     rdx, [rbp+1290h+var_1150]
0x18003972c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180039730  movdqa  [rbp+1290h+var_12B0], xmm0
0x180039735  mov     rax, rcx
0x180039738  xor     r8d, r8d
0x18003973b  inc     rax
0x18003973e  cmp     [rdx+rax], r8b
0x180039742  jnz     short loc_18003973B
0x180039744  inc     eax
0x180039746  mov     [rbp+1290h+var_1174], r8d
0x18003974d  mov     [rbp+1290h+var_1178], eax
0x180039753  lea     rax, [rbp+1290h+var_12F0]
0x180039757  mov     [rbp+1290h+var_1190], rax
0x18003975e  lea     rax, [rsp+1390h+var_1320]
0x180039763  mov     [rbp+1290h+var_11A0], rax
0x18003976a  lea     rdx, [rbp+1290h+var_1150]
0x180039771  mov     [rbp+1290h+var_1180], rdx
0x180039778  mov     r9d, 2
0x18003977e  mov     [rbp+1290h+var_1188], 8
0x180039789  mov     [rbp+1290h+var_1198], 4
0x180039794  test    rdi, rdi
0x180039797  jz      loc_18003B192
0x18003979d  inc     rcx
0x1800397a0  cmp     [rdi+rcx*2], r8w
0x1800397a5  jnz     short loc_18003979D
0x1800397a7  lea     ecx, ds:2[rcx*2]
0x1800397ae  jmp     loc_18003B19C
0x1800397b3  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800397b9  mov     edi, 1
0x1800397be  and     eax, edi
0x1800397c0  test    al, al
0x1800397c2  jz      short loc_1800397DB
0x1800397c4  mov     r9, r15; char *
0x1800397c7  mov     [rsp+1390h+dwFlags], ebx; dwFlags
0x1800397cb  mov     r8, rsi; char *
0x1800397ce  mov     rdx, r14; char *
0x1800397d1  mov     ecx, 114Ch; unsigned int
0x1800397d6  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800397db  mov     r8, [rbp+1290h+pszPathIn]; pszPathIn
0x1800397df  lea     r9, aAppraiserDataI; "Appraiser_Data.ini"
0x1800397e6  mov     rdx, r12; cchPathOut
0x1800397e9  lea     rcx, [rbp+1290h+ExistingFileName]; pszPathOut
0x1800397f0  call    PathCchCombineEx
0x1800397f5  mov     ebx, eax
0x1800397f7  test    eax, eax
0x1800397f9  jns     short loc_180039827
0x1800397fb  mov     edx, 1152h; bool
0x180039800  mov     dword ptr [rsp+1390h+var_1360], ebx; char *
0x180039804  mov     r9, rsi; char *
0x180039807  mov     qword ptr [rsp+1390h+var_1368], r15; int
0x18003980c  mov     r8, r14; unsigned int
0x18003980f  mov     ecx, edi; this
0x180039811  mov     [rsp+1390h+dwFlags], ebx; char *
0x180039815  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18003981a  mov     r12b, [rsp+1390h+var_1330]
0x18003981f  xor     r15d, r15d
0x180039822  jmp     loc_18003966B
0x180039827  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003982d  and     eax, edi
0x18003982f  test    al, al
0x180039831  jz      short loc_18003984A
0x180039833  mov     r9, r15; char *
0x180039836  mov     [rsp+1390h+dwFlags], ebx
0x18003983a  mov     r8, rsi; char *
0x18003983d  mov     rdx, r14; char *
0x180039840  mov     ecx, 1152h; unsigned int
0x180039845  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18003984a  lea     r8, [rbp+1290h+ExistingFileName]; unsigned __int16 *
0x180039851  lea     rdx, [rbp+1290h+pszPathOut]; unsigned __int16 *
0x180039858  call    ?ExtractResourceToFile@Utilities@Appraiser@Compat@Windows@@SAJKPEBG0@Z; Windows::Compat::Appraiser::Utilities::ExtractResourceToFile(ulong,ushort const *,ushort const *)
0x18003985d  xor     r15d, r15d
0x180039860  mov     ebx, eax
0x180039862  test    eax, eax
0x180039864  jns     short loc_180039894
0x180039866  lea     r9, aFailedToExtrac_1; "Failed to extract data file resource: ["...
0x18003986d  mov     edx, 1155h; bool
0x180039872  mov     dword ptr [rsp+1390h+var_1360], ebx; char *
0x180039876  mov     r8, r14; unsigned int
0x180039879  mov     qword ptr [rsp+1390h+var_1368], r9; int
0x18003987e  mov     ecx, edi; this
0x180039880  mov     r9, rsi; char *
0x180039883  mov     [rsp+1390h+dwFlags], ebx; char *
0x180039887  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18003988c  mov     r12b, r15b
0x18003988f  jmp     loc_18003966B
0x180039894  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003989a  and     eax, edi
0x18003989c  test    al, al
0x18003989e  jz      short loc_1800398BB
0x1800398a0  lea     r9, aFailedToExtrac_1; "Failed to extract data file resource: ["...
0x1800398a7  mov     [rsp+1390h+dwFlags], ebx
0x1800398ab  mov     r8, rsi; char *
0x1800398ae  mov     rdx, r14; char *
0x1800398b1  mov     ecx, 1155h; unsigned int
0x1800398b6  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800398bb  xor     edx, edx; bool
0x1800398bd  lea     rcx, [rbp+1290h+ExistingFileName]; unsigned __int16 *
0x1800398c4  call    ?UseAlternateInboxDataPath@DataFile@Appraiser@Compat@Windows@@SAJPEBG_N@Z; Windows::Compat::Appraiser::DataFile::UseAlternateInboxDataPath(ushort const *,bool)
0x1800398c9  mov     ebx, eax
0x1800398cb  test    eax, eax
0x1800398cd  jns     short loc_1800398DD
0x1800398cf  lea     r9, aFailedToOverri_0; "Failed to override inbox data path for "...
0x1800398d6  mov     edx, 1158h
0x1800398db  jmp     short loc_180039872
0x1800398dd  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800398e3  and     eax, edi
0x1800398e5  test    al, al
0x1800398e7  jz      short loc_180039904
0x1800398e9  lea     r9, aFailedToOverri_0; "Failed to override inbox data path for "...
0x1800398f0  mov     [rsp+1390h+dwFlags], ebx
0x1800398f4  mov     r8, rsi; char *
0x1800398f7  mov     rdx, r14; char *
0x1800398fa  mov     ecx, 1158h; unsigned int
0x1800398ff  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180039904  lea     r8, aAppraiserdatav; "AppraiserDataVersion"
0x18003990b  lea     rdx, [rbp+1290h+ExistingFileName]; unsigned __int16 *
0x180039912  lea     rcx, [rsp+1390h+var_132C]; unsigned int *
0x180039917  call    ?GetMetadataParameterFromFile@DataFile@Appraiser@Compat@Windows@@SAJAEAKPEBG1@Z; Windows::Compat::Appraiser::DataFile::GetMetadataParameterFromFile(ulong &,ushort const *,ushort const *)
0x18003991c  mov     ebx, eax
0x18003991e  test    eax, eax
0x180039920  jns     short loc_180039933
0x180039922  lea     r9, aFailedToCheckI_6; "Failed to check inbox data path for ver"...
0x180039929  mov     edx, 115Bh
0x18003992e  jmp     loc_180039872
0x180039933  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180039939  and     eax, edi
0x18003993b  test    al, al
0x18003993d  jz      short loc_18003995A
0x18003993f  lea     r9, aFailedToCheckI_6; "Failed to check inbox data path for ver"...
0x180039946  mov     [rsp+1390h+dwFlags], ebx; dwFlags
0x18003994a  mov     r8, rsi; char *
0x18003994d  mov     rdx, r14; char *
0x180039950  mov     ecx, 115Bh; unsigned int
0x180039955  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18003995a  mov     r8, [rbp+1290h+pszPathIn]; pszPathIn
0x18003995e  lea     r9, aAltdataCab; "AltData.cab"
0x180039965  mov     rdx, r12; cchPathOut
0x180039968  lea     rcx, [rbp+1290h+pszPath]; pszPathOut
0x18003996f  call    PathCchCombineEx
0x180039974  lea     r15, aConcatError0xX; "Concat error: [0x%x]."
0x18003997b  mov     ebx, eax
0x18003997d  test    eax, eax
0x18003997f  jns     short loc_18003998B
0x180039981  mov     edx, 1162h
0x180039986  jmp     loc_180039800
0x18003998b  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180039991  and     eax, edi
0x180039993  test    al, al
0x180039995  jz      short loc_1800399AE
0x180039997  mov     r9, r15; char *
0x18003999a  mov     [rsp+1390h+dwFlags], ebx; dwFlags
0x18003999e  mov     r8, rsi; char *
0x1800399a1  mov     rdx, r14; char *
0x1800399a4  mov     ecx, 1162h; unsigned int
0x1800399a9  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800399ae  mov     r8, [rbp+1290h+pszPathIn]; pszPathIn
0x1800399b2  lea     r9, aAltdatatempCab; "AltDataTemp.cab"
0x1800399b9  mov     rdx, r12; cchPathOut
0x1800399bc  lea     rcx, [rbp+1290h+FileName]; pszPathOut
0x1800399c3  call    PathCchCombineEx
0x1800399c8  mov     ebx, eax
0x1800399ca  test    eax, eax
0x1800399cc  jns     short loc_1800399D8
0x1800399ce  mov     edx, 1165h
0x1800399d3  jmp     loc_180039800
0x1800399d8  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800399de  and     eax, edi
0x1800399e0  test    al, al
0x1800399e2  jz      short loc_1800399FB
0x1800399e4  mov     r9, r15; char *
0x1800399e7  mov     [rsp+1390h+dwFlags], ebx; dwFlags
0x1800399eb  mov     r8, rsi; char *
0x1800399ee  mov     rdx, r14; char *
0x1800399f1  mov     ecx, 1165h; unsigned int
0x1800399f6  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800399fb  mov     r8, [rbp+1290h+pszPathIn]; pszPathIn
0x1800399ff  lea     r9, aAppraiserSdb; "appraiser.sdb"
0x180039a06  mov     rdx, r12; cchPathOut
0x180039a09  lea     rcx, [rbp+1290h+var_460]; pszPathOut
0x180039a10  call    PathCchCombineEx
0x180039a15  mov     ebx, eax
0x180039a17  test    eax, eax
0x180039a19  jns     short loc_180039A25
0x180039a1b  mov     edx, 1168h
0x180039a20  jmp     loc_180039800
0x180039a25  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180039a2b  and     eax, edi
0x180039a2d  test    al, al
0x180039a2f  jz      short loc_180039A48
0x180039a31  mov     r9, r15; char *
0x180039a34  mov     [rsp+1390h+dwFlags], ebx; dwFlags
  ... truncated ...
```
